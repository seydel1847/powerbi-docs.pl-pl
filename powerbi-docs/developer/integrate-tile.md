---
title: "Integrowanie kafelka usługi Power BI z aplikacją dla organizacji"
description: "Przewodnik po integrowaniu kafelka z aplikacją — przykładowy kod"
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: c4c1b9223554491968a541c9d6b698a9655eded5
ms.sourcegitcommit: 2ceea44d3606c15b57142c37649c9d481ec4becc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2018
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>Integrowanie kafelka z aplikacją (dane należą do użytkownika)
Dowiedz się, jak integrować lub osadzać kafelek w aplikacji internetowej przy użyciu wywołań interfejsu API REST wraz z interfejsem API języka JavaScript usługi Power BI podczas osadzania dla organizacji.

![Osadzony kafelek w aplikacji internetowej](media/integrate-tile/powerbi-embedded-tile.png)

Do rozpoczęcia pracy z tym przewodnikiem jest wymagane konto usługi **Power BI**. Jeśli nie masz konta, możesz [utworzyć bezpłatne konto usługi Power BI](../service-self-service-signup-for-power-bi.md) lub utworzyć własną [dzierżawę usługi Azure Active Directory](create-an-azure-active-directory-tenant.md) do celów testowych.

> [!NOTE]
> Chcesz zamiast tego osadzić kafelek dla klientów przy użyciu tokenu osadzania? Zobacz [Integrowanie pulpitu nawigacyjnego, kafelka lub raportu w aplikacji dla klientów](embed-sample-for-customers.md).
> 
> 

Aby zintegrować kafelek z aplikacją internetową, należy użyć interfejsu API REST usługi **Power BI** lub zestawu SDK C# usługi Power BI oraz **tokenu dostępu** uwierzytelniania usługi Azure Active Directory (AD) w celu uzyskania kafelka. Następnie należy załadować kafelek przy użyciu tego samego tokenu dostępu. Interfejs API usługi **Power BI** zapewnia dostęp programowy do określonych zasobów usługi **Power BI**. Aby uzyskać więcej informacji, zobacz [Omówienie interfejsu API REST usługi Power BI](https://msdn.microsoft.com/library/dn877544.aspx) i [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) (Interfejs API języka JavaScript usługi Power BI).

## <a name="download-the-sample"></a>Pobieranie przykładu
W tym artykule przedstawiono kod używany w aplikacji [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) w witrynie GitHub. Aby korzystać z tego przewodnika, możesz pobrać przykład.

## <a name="step-1---register-an-app-in-azure-ad"></a>Krok 1. Rejestrowanie aplikacji w usłudze Azure AD
Aplikację należy zarejestrować w usłudze Azure AD, aby móc wykonywać wywołania interfejsu API REST. Aby uzyskać więcej informacji, zobacz [Rejestrowanie aplikacji usługi Azure AD, aby osadzić zawartość usługi Power BI](register-app.md).

Jeśli pobrano przykład [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app), użyj **identyfikatora klienta** i **klucza tajnego klienta** otrzymanego po zarejestrowaniu, aby przykład mógł uwierzytelniać się w usłudze Azure AD. Aby skonfigurować przykład, zmień wartości **Client ID** (Identyfikator klienta) i **Client Secret** (Klucz tajny klienta) w pliku *cloud.config*.

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Krok 2. Uzyskiwanie tokenu dostępu z usługi Azure AD
W aplikacji należy najpierw uzyskać **token dostępu** z usługi Azure AD, aby móc wykonywać wywołania interfejsu API REST usługi Power BI. Aby uzyskać więcej informacji, zobacz [Uwierzytelnianie użytkowników i uzyskiwanie tokenów dostępu usługi Azure AD dla aplikacji usługi Power BI](get-azuread-access-token.md).

## <a name="step-3---get-a-tile"></a>Krok 3. Uzyskiwanie kafelka
Aby uzyskać kafelek usługi **Power BI**, należy użyć operacji [uzyskiwania kafelków](https://msdn.microsoft.com/library/mt465741.aspx) zwracającej listę kafelków usługi **Power BI**. Z listy kafelków można uzyskać identyfikator kafelka i adres URL osadzania.

Zanim będzie można uzyskać kafelek, należy pobrać identyfikator pulpitu nawigacyjnego. Aby uzyskać informacje dotyczące pobierania pulpitu nawigacyjnego, zobacz [Integrowanie pulpitu nawigacyjnego w aplikacji (dane należą do użytkownika)](integrate-dashboard.md).

### <a name="get-tiles-using-an-access-token"></a>Uzyskiwanie kafelków przy użyciu tokenu dostępu
Możesz użyć **tokenu dostępu** pobranego w [kroku 2.](#step-2-get-an-access-token-from-azure-ad), wywołując operację [uzyskiwania kafelków](https://msdn.microsoft.com/library/mt465741.aspx). Operacja [uzyskiwania kafelków](https://msdn.microsoft.com/library/mt465741.aspx) zwraca listę kafelków. Z tej listy kafelków można uzyskać pojedynczy kafelek. Poniżej przedstawiono całą metodę języka C# umożliwiającą uzyskanie kafelka. 

Aby wykonać wywołanie interfejsu API REST, należy użyć nagłówka *Authorization* w formacie *Bearer {token dostępu}*.

#### <a name="get-tiles-with-the-rest-api"></a>Uzyskiwanie kafelków za pomocą interfejsu API REST
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>Uzyskiwanie kafelków za pomocą zestawu SDK .NET
Listę pulpitów nawigacyjnych można uzyskać przy użyciu zestawu SDK .NET zamiast bezpośredniego wywoływania interfejsu API REST.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>Krok 4. Ładowanie kafelka przy użyciu języka JavaScript
Do załadowania kafelka do elementu div na stronie internetowej można użyć języka JavaScript.

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Jeśli pobrano i uruchomiono przykład [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app), będzie on wyglądać podobnie jak na poniższej ilustracji.

![Osadzony kafelek w aplikacji internetowej](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>Praca z grupami (obszarami roboczymi aplikacji)
Aby osadzić kafelek z grupy (obszaru roboczego aplikacji), należy uzyskać listę wszystkich dostępnych kafelków na pulpicie nawigacyjnym grupy przy użyciu następującego wywołania interfejsu API REST. Aby uzyskać więcej informacji na temat tego wywołania interfejsu API REST, zobacz [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) (Uzyskiwanie kafelków). Aby żądanie zwróciło wyniki, musisz mieć uprawnienia w tej grupie.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

Powyższe wywołanie interfejsu API zwraca listę wszystkich dostępnych kafelków. Każdy kafelek ma właściwość EmbedUrl skonstruowaną tak, aby obsługiwać osadzanie z grup.

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>Następne kroki
[Osadzanie kafelka](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed) w witrynie typu Wiki środowiska Power BI-JavaScript

[Interfejs API JavaScript usługi Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

Przykład [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) w witrynie GitHub.

Więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

