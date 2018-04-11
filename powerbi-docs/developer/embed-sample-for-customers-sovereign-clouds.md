---
title: Osadzanie zawartości usługi Power BI w aplikacji dla klientów w suwerennych chmurach
description: Dowiedz się, jak integrować lub osadzać pulpit nawigacyjny, kafelek lub raport w aplikacji internetowej przy użyciu interfejsów API usługi Power BI dla klientów.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/28/2018
ms.author: maghan
ms.openlocfilehash: bef0748f1431a29c96d7aa23ab457683e247724a
ms.sourcegitcommit: e571de2afa3f34fac06a6aab0df0e8940cb00a0d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/05/2018
---
# <a name="embed-a-power-bi-dashboard-tile-or-report-into-your-application-for-sovereign-clouds"></a>Osadzanie pulpitu nawigacyjnego, kafelka lub raportu usługi Power BI w aplikacji dla suwerennych chmur
Dowiedz się, jak integrować lub osadzać pulpit nawigacyjny, kafelek albo raport w aplikacji internetowej przy użyciu zestawu .NET SDK usługi Power BI wraz z interfejsem API języka JavaScript programu Power BI podczas osadzania dla klientów. Jest to zwykle scenariusz niezależnego dostawcy oprogramowania.

Usługa Power BI obsługuje również suwerenne (prywatne) chmury. Każda suwerenna chmura ma własną przynależność. Suwerenne chmury to:

* U.S. Government Community Cloud (GCC)

* U. S. Military Contractors (DoDCON)

* U. S. Military (DoD)

* Power BI for Germany Cloud

![Osadzony pulpit nawigacyjny](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

Do rozpoczęcia pracy z tym przewodnikiem jest wymagane **konto usługi Power BI**. Jeśli nie masz skonfigurowanego konta, w zależności od typu instytucji rządowych możesz [utworzyć nowe konto usługi Power BI dla instytucji rządowej USA](../service-govus-signup.md) lub [konto usługi Power BI for Germany Cloud](https://powerbi.microsoft.com/en-us/power-bi-germany/?ru=https%3A%2F%2Fapp.powerbi.de%2F%3FnoSignUpCheck%3D1).

> [!NOTE]
> Chcesz osadzić pulpit nawigacyjny dla swojej organizacji? Zobacz [Integrate a dashboard into an app for your organization (Integrowanie pulpitu nawigacyjnego z aplikacją dla organizacji)](integrate-dashboard.md).
>

Aby zintegrować pulpit nawigacyjny z aplikacją internetową, należy użyć interfejsu API usługi **Power BI** oraz **tokenu dostępu** autoryzacji usługi Azure Active Directory (AD) w celu uzyskania pulpitu nawigacyjnego. Następnie należy załadować pulpit nawigacyjny przy użyciu tokenu osadzania. Interfejs API usługi **Power BI** zapewnia dostęp programowy do określonych zasobów usługi **Power BI**. Aby uzyskać więcej informacji, zobacz [Overview of Power BI REST API (Omówienie interfejsu API REST usługi Power BI)](https://msdn.microsoft.com/library/dn877544.aspx), [Power BI .NET SDK (Zestaw SDK platformy .NET dla usługi Power BI)](https://github.com/Microsoft/PowerBI-CSharp) i [Power BI JavaScript API (Interfejs API języka JavaScript usługi Power BI)](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Pobieranie przykładu
W tym artykule przedstawiono kod używany w [przykładzie osadzania na potrzeby klienta](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data/PowerBIEmbedded_AppOwnsData) i dostępny w witrynie GitHub. Aby korzystać z tego przewodnika, możesz pobrać przykład.

* Government Community Cloud (GCC):
    1. Zastąp plik Cloud.config plikiem GCCCloud.config.
    2. Zaktualizuj elementy clientid (identyfikator klienta aplikacji natywnej), groupid, user (użytkownik główny) i password w pliku Web.config.
    3. Dodaj parametry chmury GCC do pliku web.config w następujący sposób.

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://analysis.usgovcloudapi.net/powerbi/api" />

<add key="apiUrl" value="https://api.powerbigov.us/" />

<add key="embedUrlBase" value="https://app.powerbigov.us" />
```

* Military Contractors (DoDCON):
    1. Zastąp plik Cloud.config plikiem TBCloud.config.
    2. Zaktualizuj elementy clientid (identyfikator klienta aplikacji natywnej), groupid, user (użytkownik główny) i password w pliku Web.config.
    3. Dodaj parametry chmury DoDCON do pliku web.config w następujący sposób.

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://high.analysis.usgovcloudapi.net/powerbi/api" />

<add key="apiUrl" value="https://api.high.powerbigov.us/" />

<add key="embedUrlBase" value="https://app.high.powerbigov.us" />
```

* Military (DoD):
    1. Zastąp plik Cloud.config plikiem PFCloud.config.
    2. Zaktualizuj elementy clientid (identyfikator klienta aplikacji natywnej), groupid, user (użytkownik główny) i password w pliku Web.config.
    3. Dodaj parametry chmury DoDCON do pliku web.config w następujący sposób.

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://mil.analysis.usgovcloudapi.net/powerbi/api" />

<add key="apiUrl" value="https://api.mil.powerbigov.us/" />

<add key="embedUrlBase" value="https://app.mil.powerbigov.us" />
```

* Parametry usługi Power BI for Germany Cloud
    1. Zastąp plik Cloud.config zawartością usługi Power BI for Germany Cloud.
    2. Zaktualizuj elementy clientid (identyfikator klienta aplikacji natywnej), groupid, user (użytkownik główny) i password w pliku Web.config.
    3. Dodaj parametry usługi Power BI for Germany Cloud do pliku web.config w następujący sposób.

```xml
<add key="authorityUrl" value=https://login.microsoftonline.de/common/oauth2/authorize/" />

<add key="resourceUrl" value="https://analysis.cloudapi.de/powerbi/api" />

<add key="apiUrl" value="https://api.powerbi.de/" />

<add key="embedUrlBase" value="https://app.powerbi.de" />
```

## <a name="step-1---register-an-app-in-azure-ad"></a>Krok 1. Rejestrowanie aplikacji w usłudze Azure AD
Musisz zarejestrować aplikację w usłudze Azure AD, aby móc wywoływać interfejs API REST. Aby uzyskać więcej informacji, zobacz [Rejestrowanie aplikacji usługi Azure AD, aby osadzić zawartość usługi Power BI](register-app.md). Ze względu na to, że istnieją różne przynależności suwerennych chmur, do rejestrowania aplikacji są używane oddzielne adresy URL.

* Government Community Cloud (GCC) — https://app.powerbigov.us/apps 

* Military Contractors (DoDCON) — https://app.high.powerbigov.us/apps 

* Military (DoD) — https://app.mil.powerbigov.us/apps

* Power BI for Germany Cloud — https://app.powerbi.de/apps

Jeśli pobrano [przykład osadzania na potrzeby klienta](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data), użyj **identyfikatora klienta** otrzymanego po zarejestrowaniu, aby przykład mógł uwierzytelnić się w usłudze Azure AD. Aby skonfigurować próbkę, zmień parametr **clientId** w pliku *web.config*.


## <a name="step-2---get-an-access-token-from-azure-ad"></a>Krok 2. Uzyskiwanie tokenu dostępu z usługi Azure AD
W aplikacji należy najpierw uzyskać **token dostępu** z usługi Azure AD, aby móc wykonywać wywołania interfejsu API REST usługi Power BI. Aby uzyskać więcej informacji, zobacz [Uwierzytelnianie użytkowników i uzyskiwanie tokenów dostępu usługi Azure AD dla aplikacji usługi Power BI](get-azuread-access-token.md). Ze względu na to, że istnieją różne przynależności suwerennych chmur, do uzyskiwania dostępu do tokenu aplikacji są używane oddzielne adresy URL.

* Government Community Cloud (GCC) — https://login.microsoftonline.com

* Military Contractors (DoDCON) — http://login.microsoftonline.us

* Military (DoD) — https://login.microsoftonline.us

* Power BI for Germany Cloud — https://login.microsoftonline.de

Przykłady tego można zobaczyć w każdym zadaniu elementu zawartości w klasie **Controllers\HomeController.cs**.

## <a name="step-3---get-a-content-item"></a>Krok 3. Pobieranie elementu zawartości
Aby osadzić zawartość usługi Power BI, należy wykonać kilka czynności w celu zapewnienia, że zostanie ona osadzona poprawnie. Wszystkie te kroki można wykonać bezpośrednio w interfejsie API REST, jednak przykładowa aplikacja i podane tutaj przykłady utworzono przy użyciu zestawu .NET SDK.

### <a name="create-the-power-bi-client-with-your-access-token"></a>Tworzenie klienta programu Power BI przy użyciu tokenu dostępu
Token dostępu umożliwia utworzenie obiektu klienta usługi Power BI, który pozwoli na interakcję z interfejsami API usługi Power BI. Jest to realizowane przez opakowywanie tokenu AccessToken w obiekt *Microsoft.Rest.TokenCredentials*.

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>Pobieranie elementu zawartości, który ma zostać osadzony
Użyj obiektu klienta usługi Power BI do pobrania odwołania do elementu, który ma zostać osadzony. Można osadzać pulpity nawigacyjne, kafelki lub raporty. Oto przykład pobierania pierwszego pulpitu nawigacyjnego, kafelka lub raportu z danego obszaru roboczego.

Próbka jest dostępna w klasie **Controllers\HomeController.cs** [próbki danych posiadanych przez aplikację](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

**Pulpity nawigacyjne**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**Kafelek**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**Raport**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>Tworzenie tokenu osadzania
Należy wygenerować token osadzania, którego można używać z poziomu interfejsu API języka JavaScript. Token osadzania będzie specyficzny dla osadzanego elementu. Oznacza to, że za każdym razem, gdy osadzasz fragment zawartości usługi Power BI, musisz utworzyć dla niego nowy token. Aby uzyskać więcej informacji, łącznie z tym, którego parametru **accessLevel** używać, zobacz [GenerateToken API (Interfejs API generowania tokenu)](https://msdn.microsoft.com/library/mt784614.aspx).

> [!IMPORTANT]
> Ponieważ tokeny osadzania są przeznaczone tylko do celów testowania podczas programowania, liczba tokenów osadzania, które może wygenerować konto główne usługi Power BI, jest ograniczona. Dla scenariuszy osadzania w środowisku produkcyjnym [należy kupić pojemność](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical). Nie ma żadnego ograniczenia generowania tokenów osadzania, gdy zostanie kupiona pojemność.

Próbka jest dostępna w klasie **Controllers\HomeController.cs** [próbki osadzania dla organizacji](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

Założono, że utworzono klasę **EmbedConfig** i **TileEmbedConfig**. Próbka jest dostępna w klasach **Models\EmbedConfig.cs** i **Models\TileEmbedConfig.cs**.

**Pulpit nawigacyjny**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**Kafelek**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**Raport**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```
## <a name="step-4---load-an-item-using-javascript"></a>Krok 4. Ładowanie elementu przy użyciu języka JavaScript
Języka JavaScript można użyć do załadowania pulpitu nawigacyjnego do elementu div na stronie internetowej. W próbce użyto modelu EmbedConfig/TileEmbedConfig wraz z widokami dla pulpitu nawigacyjnego, kafelka lub raportu. Aby uzyskać pełną próbkę użycia interfejsu API języka JavaScript, można użyć [próbki usługi Microsoft Power BI Embedded](https://microsoft.github.io/PowerBI-JavaScript/demo).

Próbka takiej aplikacji jest dostępna w [próbce osadzania dla organizacji](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

**Views\Home\EmbedDashboard.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="next-steps"></a>Następne kroki

* Przykładowa aplikacja jest dostępna w witrynie GitHub do przeglądu. Powyższe przykłady są oparte na tym przykładzie. Aby uzyskać więcej informacji, zobacz [próbkę osadzania dla organizacji](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).
* Aby uzyskać więcej informacji na temat interfejsu API języka JavaScript, zapoznaj się z tematem dotyczącym [interfejsu API języka JavaScript w usłudze Power BI](https://github.com/Microsoft/PowerBI-JavaScript).
* Aby uzyskać więcej informacji o usłudze Power BI for Germany Cloud, zapoznaj się z tematem [Usługa Power BI for Germany Cloud — często zadawane pytania](https://docs.microsoft.com/en-us/power-bi/service-govde-faq)
* [Jak migrować zawartość kolekcji obszarów roboczych usługi Power BI do usługi Power BI](migrate-from-powerbi-embedded.md)

Ograniczenia i istotne zagadnienia
* Obecnie konta GCC obsługują tylko możliwości P i EM

Więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)
