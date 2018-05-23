---
title: Rejestrowanie aplikacji, aby osadzić zawartość usługi Power BI
description: Dowiedz się, jak zarejestrować aplikację w usłudze Azure Active Directory, a następnie użyć jej w celu osadzenia zawartości usługi Power BI.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 04/23/2018
ms.author: maghan
ms.openlocfilehash: 8c40ccac8eff2775b09cf9761fba52e6f8a6cd45
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="register-an-azure-ad-app-to-embed-power-bi-content"></a>Rejestrowanie aplikacji usługi Azure AD, aby osadzić zawartość usługi Power BI
Dowiedz się, jak zarejestrować aplikację w usłudze Azure Active Directory (Azure AD), a następnie użyć jej w celu osadzenia zawartości usługi Power BI.

Aplikację można zarejestrować w usłudze Azure AD, aby zapewnić aplikacji dostęp do interfejsów API REST usługi Power BI. Dzięki temu można dla aplikacji ustanowić tożsamość i określić dla niej uprawnienia do zasobów REST usługi Power BI.

> [!IMPORTANT]
> Do zarejestrowania aplikacji usługi Power BI potrzebna jest [dzierżawa i konto użytkownika organizacyjnego usługi Azure Active Directory](create-an-azure-active-directory-tenant.md). Jeśli nie zarejestrujesz się w usłudze Power BI, korzystając z konta użytkownika z Twojej dzierżawy, pomyślne zarejestrowanie aplikacji będzie niemożliwe.
> 
> 

Istnieją dwa sposoby rejestrowania aplikacji. Pierwszy sposób obejmuje użycie [narzędzia rejestrowania aplikacji usługi Power BI](https://dev.powerbi.com/apps/), a drugi polega na dokonaniu rejestracji bezpośrednio w witrynie Azure Portal. Narzędzie rejestrowania aplikacji usługi Power BI to opcja najłatwiejsza, ponieważ wystarczy wypełnić tylko kilka pól. Jeśli chcesz wprowadzić zmiany w aplikacji, użyj witryny Azure Portal.

## <a name="register-with-the-power-bi-app-registration-tool"></a>Rejestracja za pomocą narzędzia rejestrowania aplikacji usługi Power BI
Aplikację należy zarejestrować w usłudze **Azure Active Directory**, aby ustanowić dla niej tożsamość i określić uprawnienia do zasobów REST usługi Power BI. Gdy rejestrujesz aplikację, np. aplikację konsolową lub witrynę internetową, otrzymujesz identyfikator, którym aplikacja posługuje się, aby się identyfikować dla użytkowników, od których aplikacja żąda uprawnień.

Oto sposób rejestrowania aplikacji za pomocą narzędzia rejestrowania aplikacji usługi Power BI:

1. Przejdź do witryny [dev.powerbi.com/apps](https://dev.powerbi.com/apps).
2. Wybierz pozycję **Zaloguj się przy użyciu istniejącego konta**.
3. Podaj nazwę w polu **Nazwa aplikacji**.
4. Wybór w polu Typ aplikacji zależy od typu używanej aplikacji.
   
   * W przypadku aplikacji internetowych lub internetowych interfejsów API wybierz typ **Aplikacja internetowa po stronie serwera**.
   * W przypadku aplikacji, które działają na urządzeniach klienckich, wybierz typ **Aplikacja natywna**. ***Typ **Aplikacja natywna** należy wybrać także w przypadku osadzania zawartości dla klientów — bez względu na to, jaka jest rzeczywista aplikacja. Dotyczy to nawet aplikacji internetowych.***
5. Wprowadź **Adres URL przekierowania** i **Adres URL strony głównej**. Każdy prawidłowy adres URL będzie działać.
   
    Pole **Adres URL strony głównej** jest dostępne tylko po wybraniu typu aplikacji **Aplikacja internetowa po stronie serwera**.
   
    W przykładach dotyczących *osadzania zawartości dla klientów* i *integrowania aplikacji internetowej pulpitu nawigacyjnego* adresem URL przekierowania będzie `http://localhost:13526/redirect`. W przykładzie dotyczącym raportów i kafelków adresem URL przekierowania będzie `http://localhost:13526/`.
6. Wybierz interfejsy API, do których ta aplikacja będzie miała dostęp. Więcej informacji o uprawnieniach dostępu do usługi Power BI zawiera temat [Uprawnienia usługi Power BI](power-bi-permissions.md).
   
    ![](media/register-app/app-registration-apis.png)
7. Wybierz przycisk **Zarejestruj aplikację**.
   
    Otrzymasz **Identyfikator klienta**. W przypadku wybrania typu **Aplikacja internetowa po stronie serwera** otrzymasz także **Klucz tajny klienta**. **Identyfikator klienta** można później, w razie potrzeby, pobrać z witryny Azure Portal. W przypadku utraty **Klucza tajnego klienta** musisz utworzyć nowy klucz w witrynie Azure Portal.

8. Musisz przejść do platformy Azure, aby wybrać pozycję **Udziel uprawnień**.
> [!Note]
    > Tylko administrator globalny w dzierżawie platformy Azure może wykonać tę czynność
>

* Przejdź do platformy Azure.
* Wyszukaj i wybierz pozycję **Rejestracje aplikacji**.
* Wybierz aplikację.
* Wybierz pozycję **Ustawienia**.
* Wybierz pozycję **Wymagane uprawnienia**.
* Wybierz pozycję **Usługa Power BI**, aby zweryfikować uprawnienia wybrane w witrynie rejestracji aplikacji.
* Wybierz pozycję **Udziel uprawnień**.

Teraz możesz używać zarejestrowanej aplikacji jako części aplikacji niestandardowej na potrzeby interakcji z usługą Power BI.

> [!IMPORTANT]
> Jeśli osadzasz zawartość dla klientów, musisz skonfigurować dodatkowe uprawnienia w witrynie Azure Portal. Więcej informacji zawiera sekcja [Stosowanie uprawnień do Twojej aplikacji](#apply-permissions-to-your-application).
> 
> 

## <a name="register-with-the-azure-portal"></a>Rejestrowanie za pomocą witryny Azure Portal
Drugą opcją rejestracji aplikacji jest dokonanie rejestracji bezpośrednio w witrynie Azure Portal. Aby zarejestrować aplikację, wykonaj następujące kroki.

1. Zaakceptuj [Warunki interfejsu API usługi Microsoft Power BI](https://powerbi.microsoft.com/api-terms).
2. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com).
3. Wybierz dzierżawę usługi Azure AD, wybierając swoje konto w prawym górnym rogu strony.
4. W okienku nawigacji po lewej stronie wybierz pozycję **Więcej usług**, wybierz pozycję **Rejestracje aplikacji** w obszarze **Bezpieczeństwo i obsługa tożsamości**, a następnie wybierz przycisk **Rejestrowanie nowej aplikacji**.
   
    ![](media/register-app/azuread-new-app-registration.png)
5. Postępuj zgodnie z monitami i utwórz nową aplikację.
   
   * W przypadku aplikacji internetowych podaj adres URL logowania, czyli podstawowy adres URL Twojej aplikacji, pod którym użytkownicy mogą się logować, np. http://localhost:13526.
   * W przypadku aplikacji natywnych podaj Identyfikator URI przekierowania, którego usługa Azure AD używa do zwracania odpowiedzi tokenu. Wprowadź wartość specyficzną dla Twojej aplikacji, np. http://myapplication/redirect

Więcej informacji o sposobie rejestrowania aplikacji w usłudze Azure Active Directory zawiera temat [Integrowanie aplikacji z usługą Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)

## <a name="how-to-get-the-client-id"></a>Jak uzyskać identyfikator klienta
Gdy zarejestrujesz aplikację, otrzymasz **Identyfikator klienta**.  Za pomocą **Identyfikatora klienta** aplikacja identyfikuje się dla użytkowników, od których żąda uprawnień.

Oto jak uzyskać identyfikator klienta:

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com).
2. Wybierz dzierżawę usługi Azure AD, wybierając swoje konto w prawym górnym rogu strony.
3. W okienku nawigacji po lewej stronie wybierz pozycję **Więcej usług** i pozycję **Rejestracje aplikacji**.
4. Wybierz aplikację, dla której chcesz uzyskać identyfikator klienta.
5. Zobaczysz **Identyfikator aplikacji**, który będzie widoczny jako identyfikator GUID. To jest identyfikator klienta dla tej aplikacji.
   
    ![Identyfikator klienta na liście jako identyfikator aplikacji w rejestracji aplikacji](media/register-app/powerbi-embedded-app-registration-client-id.png)

## <a name="apply-permissions-to-your-application-within-azure-ad"></a>Stosowanie uprawnień do Twojej aplikacji w usłudze Azure AD
> [!IMPORTANT]
> Ta sekcja dotyczy tylko aplikacji, które **osadzają zawartość dla Twojej organizacji**.
> 
> 

Konieczne będzie włączenie dodatkowych uprawnień aplikacji, oprócz tych, które zostały zapewnione na stronie rejestracji aplikacji. W tym celu można się posłużyć portalem usługi Azure AD lub zrobić to programowo.

Musisz się zalogować na *konto główne* używane do osadzania albo na konto administratora globalnego.

### <a name="using-the-azure-ad-portal"></a>Korzystanie z portalu usługi Azure AD
1. Przejdź do obszaru [Rejestracje aplikacji](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) w witrynie Azure Portal i wybierz aplikację, której używasz do osadzania.
   
    ![](media/register-app/powerbi-embedded-azuread-registered-apps.png)
2. Wybierz pozycję **Wymagane uprawnienia** w obszarze **Dostęp do interfejsu API**.
   
    ![](media/register-app/powerbi-embedded-azuread-app-required-permissions.png)
3. Wybierz pozycję **Windows Azure Active Directory**, a następnie upewnij się, że wybrana jest pozycja **Uzyskuj dostęp do katalogu jako zalogowany użytkownik**. Wybierz pozycję **Zapisz**.
   
    ![](media/register-app/powerbi-embedded-azuread-app-permissions01.png)
4. W obszarze **Wymagane uprawnienia** wybierz pozycję **Usługa Power BI (Power BI)**.
   
    ![](media/register-app/powerbi-embedded-azuread-app-permissions03.png)
   
   > [!NOTE]
   > Jeśli aplikacja została utworzona bezpośrednio w portalu usługi Azure AD, pozycja **Usługa Power BI (Power BI)** może być niedostępna. W takim przypadku wybierz pozycję **+ Dodaj**, a następnie pozycję **1 Wybierz interfejs API**. Na liście interfejsów API wybierz pozycję **Usługa Power BI**, a następnie pozycję **Wybierz**.  Jeśli pozycja **Usługa Power BI (Power BI)** jest niedostępna w obszarze **+ Dodaj**, zarejestruj co najmniej jednego użytkownika w usłudze Power BI.
   > 
   > 
5. Wybierz wszystkie uprawnienia w obszarze **Delegowane uprawnienia**. W celu zapisania wyborów musisz je zaznaczać pojedynczo. Po zakończeniu wybierz pozycję **Zapisz**.
   
    ![](media/register-app/powerbi-embedded-azuread-app-permissions04.png)
6. W obszarze **Wymagane uprawnienia** wybierz pozycję **Udziel uprawnień**.
   
    Wykonanie akcji **Udziel uprawnień** jest konieczne, aby usługa Azure AD nie wysyłała do *konta głównego* monitów o wyrażenie zgody. Jeśli konto, z którego wykonywana jest ta akcja, jest kontem administratora globalnego, udzielisz uprawnień do tej aplikacji wszystkim użytkownikom w swojej organizacji. Jeśli jest to *konto główne*, które nie ma uprawnień administratora globalnego, udzielisz uprawnień do tej aplikacji tylko *kontu głównemu*.
   
    ![Udzielanie uprawnień w oknie dialogowym Wymagane uprawnienia](media/register-app/powerbi-embedded-azuread-app-grant-permissions.png)

### <a name="applying-permissions-programmatically"></a>Stosowanie uprawnień programowo
1. Musisz uzyskać jednostki usług (użytkowników) w swojej dzierżawie. Więcej informacji o tym, jak to zrobić, zawiera temat [Get servicePrincipal](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/serviceprincipal_get).
   
    Interfejs API *Get servicePrincipal* możesz wywołać bez podawania parametru {id}, dzięki czemu uzyskasz wszystkie jednostki usług w danej dzierżawie.
2. Znajdź jednostkę usługi o właściwości **appId** równej identyfikatorowi klienta Twojej aplikacji.
3. Utwórz nowy plan usługi, jeśli taki plan nie istnieje jeszcze dla Twojej aplikacji.
   
    ```
    Post https://graph.microsoft.com/beta/servicePrincipals
    Authorization: Bearer ey..qw
    Content-Type: application/json
    {
    "accountEnabled" : true,
    "appId" : "{App_Client_ID}",
    "displayName" : "{App_DisplayName}"
    }
    ```
4. Udziel uprawnienia do aplikacji interfejsowi API usługi PowerBI.
   
    ```
    Post https://graph.microsoft.com/beta/OAuth2PermissionGrants
    Authorization: Bearer ey..qw
    Content-Type: application/json
    { 
    "clientId":"{Service_Plan_ID}",
    "consentType":"AllPrincipals",
    "resourceId":"c78b2585-1df6-41de-95f7-dc5aeb7dc98e",
    "scope":"Dataset.ReadWrite.All Dashboard.Read.All Report.Read.All Group.Read Group.Read.All Content.Create Metadata.View_Any Dataset.Read.All Data.Alter_Any",
    "expiryTime":"2018-03-29T14:35:32.4943409+03:00",
    "startTime":"2017-03-29T14:35:32.4933413+03:00"
    }
    ```
5. Udziel uprawnienia do aplikacji usłudze AAD.
   
    Wartość **consentType** będzie zależeć od użytkownika wykonującego żądanie. Możesz podać wartość **AllPrincipals** lub **Principal**. Typ **AllPrincipals** może być używany tylko przez administratora w celu udzielenia uprawnień wszystkim użytkownikom. Typ **Principal** służy do udzielania uprawnienia konkretnemu użytkownikowi. 
   
    Udzielenie uprawnienia jest konieczne, aby usługa Azure AD nie wysyłała do *konta głównego* monitów o wyrażenie zgody. 
   
    Jeśli używasz istniejącej dzierżawy i nie interesuje Cię udzielanie uprawnień w imieniu wszystkich użytkowników dzierżawy, możesz udzielić uprawnień konkretnemu użytkownikowi, zmieniając wartość właściwości **contentType** na **Principal**.
   
    ```
    Post https://graph.microsoft.com/beta/OAuth2PermissionGrants
    Authorization: Bearer ey..qw
    Content-Type: application/json
    { 
    "clientId":"{Service_Plan_ID}",
    "consentType":"AllPrincipals",
    "resourceId":"61e57743-d5cf-41ba-bd1a-2b381390a3f1",
    "scope":"User.Read Directory.AccessAsUser.All",
    "expiryTime":"2018-03-29T14:35:32.4943409+03:00",
    "startTime":"2017-03-29T14:35:32.4933413+03:00"
    }
    ```

## <a name="next-steps"></a>Następne kroki
Po zarejestrowaniu aplikacji w usłudze Azure AD musisz uwierzytelnić użytkowników w swojej aplikacji. Aby dowiedzieć się więcej, zapoznaj się z tematem [Uwierzytelnianie użytkowników i uzyskiwanie tokenu dostępu usługi Azure AD dla aplikacji usługi Power BI](get-azuread-access-token.md).

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)


