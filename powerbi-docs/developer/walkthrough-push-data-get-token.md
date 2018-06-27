---
title: Uzyskiwanie tokenu dostępu do uwierzytelniania
description: Przewodnik dotyczący wypychania danych — uzyskiwanie tokenu dostępu do uwierzytelniania
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 238d068e5083c8f46ac3299faddd4e0872f0654d
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34812634"
---
# <a name="step-2-get-an-authentication-access-token"></a>Krok 2. Uzyskiwanie tokenu dostępu do uwierzytelniania
Ten artykuł jest częścią przewodnika krok po kroku dotyczącego [wypychania danych do zestawu danych](walkthrough-push-data.md).

W **kroku 1** wypychania danych do zestawu danych, [Rejestrowanie aplikacji w usłudze Azure AD](walkthrough-push-data-register-app-with-azure-ad.md), zarejestrowaliśmy aplikację kliencką w usłudze Azure AD. W ramach tego kroku uzyskamy token dostępu do uwierzytelniania. Aplikacje usługi Power BI są zintegrowane z usługą **Azure AD** w celu zapewnienia bezpiecznego procesu logowania i autoryzacji dla aplikacji. Token jest używany do uwierzytelniania w usłudze **Azure AD** i uzyskiwania dostępu do zasobów usługi Power BI.

Poniżej przedstawiono, jak można uzyskać token dostępu do uwierzytelniania.

## <a name="get-an-authentication-access-token"></a>Uzyskiwanie tokenu dostępu do uwierzytelniania
> **UWAGA**: Przed rozpoczęciem upewnij się, że zostały wykonane poprzednie kroki przewodnika [wypychania danych do zestawu danych](walkthrough-push-data.md).
> 
> 

1. W programie Visual Studio 2015 utwórz projekt **Aplikacja konsolowa**.
2. Zainstaluj [bibliotekę Azure AD Authentication Library dla pakietu NuGet programu .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/). Aby uzyskać token zabezpieczający uwierzytelniania w aplikacji .NET, należy użyć tego pakietu. Poniżej przedstawiono sposób instalacji pakietu:
   
     a. W programie Visual Studio 2015 wybierz pozycję **Narzędzia** > **Menedżer pakietów NuGet** > **Konsola menedżera pakietów**.
   
     b. W **Konsoli menedżera pakietów** wprowadź polecenie Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612.
3. Dodaj poniższy kod do klasy Program {...}.
4. Zamień ciąg „{ClientID}” na **identyfikator klienta** uzyskany przy rejestracji aplikacji. Zobacz [Rejestrowanie aplikacji w usłudze Azure AD](walkthrough-push-data-register-app-with-azure-ad.md).
5. Po zainstalowaniu pakietu Microsoft.IdentityModel.Clients.ActiveDirectory dodaj kod **using Microsoft.IdentityModel.Clients.ActiveDirectory;** do pliku Program.cs.
6. Uruchom aplikację konsoli i zaloguj się do konta usługi Power BI. W oknie konsoli powinien zostać wyświetlony ciąg tokenu.

**Przykładowy kod, aby uzyskać token zabezpieczający uwierzytelniania**

Dodaj ten kod do klasy Program {...}.

* Zmienna tokenu do wywoływania operacji:
  
  ```
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* W statycznej funkcji void Main(string[] args):
  
  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* Dodaj metodę GetToken():

```
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.windows.net/common/oauth2/authorize";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

Po uzyskaniu tokenu uwierzytelniania można wywołać dowolną operację usługi Power BI. W następnym kroku przedstawiono, w jaki sposób wywołać operację [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets), aby utworzyć zestaw danych na potrzeby wypychania danych do pulpitu nawigacyjnego.

W następnym kroku opisano, jak [utworzyć zestaw danych w usłudze Power BI](walkthrough-push-data-create-dataset.md).

Poniżej znajduje się [kompletna lista kodu](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Kompletna lista kodu
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

            }

            #region Get an authentication access token
            private static string GetToken()
            {
                // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
                // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

                //The client id that Azure AD created when you registered your client app.
                string clientID = "{Client_ID}";

                //RedirectUri you used when you register your app.
                //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
                // You can use this redirect uri for your client app
                string redirectUri = "https://login.live.com/oauth20_desktop.srf";

                //Resource Uri for Power BI API
                string resourceUri = "https://analysis.windows.net/powerbi/api";

                //OAuth2 authority Uri
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

                //Get access token:
                // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
                // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
                // To install the Active Directory Authentication Library NuGet package in Visual Studio,
                //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

                // AcquireToken will acquire an Azure access token
                // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
                AuthenticationContext authContext = new AuthenticationContext(authorityUri);
                string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

                Console.WriteLine(token);
                Console.ReadLine();

                return token;
            }

            #endregion

        }
    }


[Następny krok >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>Następne kroki
[Tworzenie zestawu danych w usłudze Power BI](walkthrough-push-data-create-dataset.md)  
[Rejestrowanie aplikacji w usłudze Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)  
[Biblioteka Azure AD Authentication Library dla pakietu NuGet programu .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Wypychanie danych do zestawu danych usługi Power BI](walkthrough-push-data.md)  
[Omówienie interfejsu API REST usługi Power BI](overview-of-power-bi-rest-api.md)  
[Dokumentacja interfejsu API REST usługi Power BI](https://docs.microsoft.com/rest/api/power-bi/)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

