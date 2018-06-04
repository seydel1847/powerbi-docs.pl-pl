---
title: Uwierzytelnianie użytkowników i uzyskiwanie tokenów dostępu usługi Azure AD dla aplikacji
description: Dowiedz się, jak zarejestrować aplikację w usłudze Azure Active Directory, a następnie użyć jej w celu osadzenia zawartości usługi Power BI.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 08/11/2017
ms.author: maghan
ms.openlocfilehash: 339390bba2e35101bdd42f7f51ab059473231575
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290895"
---
# <a name="authenticate-users-and-get-an-azure-ad-access-token-for-your-power-bi-app"></a>Uwierzytelnianie użytkowników i uzyskiwanie tokenów dostępu usługi Azure AD dla aplikacji usługi Power BI
Dowiedz się, jak uwierzytelniać użytkowników w aplikacji usługi Power BI i pobrać token dostępu do użycia z interfejsem API REST.

Przed wywołaniem interfejsu API REST usługi Power BI musisz pobrać **token dostępu uwierzytelniania** (token dostępu) usługi Azure Active Directory (Azure AD). **Token dostępu** umożliwia aplikacji dostęp do pulpitów, kafelków i raportów **usługi Power BI**. Aby dowiedzieć się więcej o przepływie **tokenów dostępu** usługi Azure Active Directory, zobacz [Azure AD Authorization Code Grant Flow](https://msdn.microsoft.com/library/azure/dn645542.aspx) (Przepływ przyznawania kodu autoryzacji usługi Azure AD).

W zależności od tego, jak osadzana jest dostępność, token dostępu będzie pobierany inaczej. W tym artykule używane są dwa różne podejścia.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Token dostępu dla użytkowników usługi Power BI (użytkownik jest właścicielem danych)
Ten przykład dotyczy sytuacji, gdy użytkownicy będą ręcznie logować się do usługi Azure AD za pomocą swoich loginów w organizacji. Jest to używane przy osadzaniu zawartości dla użytkowników usługi Power BI, do której mają oni dostęp w usłudze Power BI.

### <a name="get-an-authorization-code-from-azure-ad"></a>Pobieranie kodu autoryzacji z usługi Azure AD
Pierwszym krokiem do pobrania **kodu dostępu** jest uzyskanie kodu autoryzacji z usługi **Azure AD**. W tym celu należy utworzyć ciąg zapytania z następującymi właściwościami i utworzyć przekierowanie do usługi **Azure AD**.

**Ciąg zapytania o kod autoryzacji**

```
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code. 
    //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
    //You get the client id when you register your Azure app.
    {"client_id", Properties.Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    // https://analysis.windows.net/powerbi/api
    {"resource", Properties.Settings.Default.PowerBiAPI},

    //After user authenticates, Azure AD will redirect back to the web app
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

Po utworzeniu ciągu zapytania należy utworzyć przekierowanie do usługi **Azure AD** w celu uzyskania **kodu autoryzacji**.  Poniżej znajduje się kompletna metoda w języku C# do konstruowania ciągu zapytania **kodu autoryzacji** i utworzenia przekierowania do usługi **Azure AD**. Gdy uzyskasz **kod autoryzacji**, za jego pomocą uzyskasz **token dostępu**.

W pliku redirect.aspx.cs zostanie następnie wywołana metoda [AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx) w celu wygenerowania tokenu.

**Uzyskiwanie kodu autoryzacji**

```
protected void signInButton_Click(object sender, EventArgs e)
{
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code. 
        //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
        //You get the client id when you register your Azure app.
        {"client_id", Properties.Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        // https://analysis.windows.net/powerbi/api
        {"resource", Properties.Settings.Default.PowerBiAPI},

        //After user authenticates, Azure AD will redirect back to the web app
        {"redirect_uri", "http://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.windows.net/common/oauth2/authorize/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>Uzyskiwanie tokenu dostępu na podstawie kodu autoryzacji
W tej chwili usługa Azure AD powinna już dostarczyć kod autoryzacji. Gdy usługa **Azure AD** wykona przekierowanie z powrotem do Twojej aplikacji internetowej z **kodem autoryzacji**, użyjesz **kodu autoryzacji** do uzyskania tokenu dostępu. Poniżej znajduje się przykładowy kod w języku C#, którego można użyć na stronie przekierowania i w zdarzeniu Page_Load dla strony default.aspx.

Przestrzeń nazw **Microsoft.IdentityModel.Clients.ActiveDirectory** można uzyskać z pakietu NuGet o nazwie [Active Directory Authentication Library](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

```
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

**Redirect.aspx.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    string redirectUri = String.Format("{0}Redirect", Properties.Settings.Default.RedirectUrl);
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;

    // Get the auth code
    string code = Request.Params.GetValues(0)[0];

    // Get auth token from auth code
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ClientCredential cc = new ClientCredential
        (Properties.Settings.Default.ClientID,
        Properties.Settings.Default.ClientSecret);

    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

    //Set Session "authResult" index string to the AuthenticationResult
    Session[_Default.authResultString] = AR;

    //Redirect back to Default.aspx
    Response.Redirect("/Default.aspx");
}
```

**Default.aspx**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{

    //Test for AuthenticationResult
    if (Session[authResultString] != null)
    {
        //Get the authentication result from the session
        authResult = (AuthenticationResult)Session[authResultString];

        //Show Power BI Panel
        signInStatus.Visible = true;
        signInButton.Visible = false;

        //Set user and token from authentication result
        userLabel.Text = authResult.UserInfo.DisplayableId;
        accessTokenTextbox.Text = authResult.AccessToken;
    }
}
```

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>Token dostępu dla użytkowników niekorzystających z usługi Power BI (aplikacja jest właścicielem danych)
Takie podejście zwykle jest używane dla aplikacji niezależnych dostawców oprogramowania, gdzie o dostępie do danych decyduje aplikacja. Użytkownicy nie muszą być koniecznie użytkownikami usługi Power BI, a uwierzytelnianiem użytkowników końcowych i dostępem do danych steruje aplikacja.

W tym podejściu będzie używane pojedyncze konto *główne*, które jest użytkownikiem usługi Power BI Pro. Poświadczenia dla tego konta są przechowywane w aplikacji. Aplikacja będzie za pomocą tych przechowywanych poświadczeń uwierzytelniać się w usłudze Azure AD. Przykładowy kod pokazany poniżej pochodzi z przykładu [App Owns Data](https://github.com/guyinacube/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

**HomeController.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

// Create a user password cradentials.
var credential = new UserPasswordCredential(Username, Password);

// Authenticate using created credentials
var authenticationContext = new AuthenticationContext(AuthorityUrl);
var authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, ClientId, credential);

if (authenticationResult == null)
{
    return View(new EmbedConfig()
    {
        ErrorMessage = "Authentication Failed."
    });
}

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

Aby uzyskać informacje na temat tego, jak korzystać z operatora **await**, zobacz [await (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) (await [dokumentacja języka C#]).

## <a name="next-steps"></a>Następne kroki
Teraz, gdy masz token dostępu, możesz wywołać interfejs API REST usługi Power BI w celu osadzenia zawartości. Aby uzyskać informacje na temat osadzania zawartości, zobacz [Jak osadzić pulpity nawigacyjne, raporty i kafelki usługi Power BI](embedding-content.md#step-2-embed-your-content).

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

