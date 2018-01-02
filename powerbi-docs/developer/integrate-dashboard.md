---
title: "Integrowanie pulpitu nawigacyjnego z aplikacją dla organizacji"
description: "Dowiedz się, jak integrować lub osadzać pulpit nawigacyjny w aplikacji internetowej przy użyciu interfejsów API usługi Power BI."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 10/05/2017
ms.author: asaxton
ms.openlocfilehash: f3968fd9fb89e868754bb6025a23fdbd028a3965
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>Integrowanie pulpitu nawigacyjnego z aplikacją dla organizacji
Dowiedz się, jak integrować lub osadzać pulpit nawigacyjny w aplikacji internetowej przy użyciu wywołań interfejsu API REST wraz z interfejsem API języka JavaScript usługi Power BI podczas osadzania dla organizacji.

![Osadzony pulpit nawigacyjny](media/integrate-dashboard/powerbi-embed-dashboard.png)

Do rozpoczęcia pracy z tym przewodnikiem jest wymagane konto usługi **Power BI**. Jeśli nie masz konta, możesz [utworzyć bezpłatne konto usługi Power BI](../service-self-service-signup-for-power-bi.md) lub utworzyć własną [dzierżawę usługi Azure Active Directory](create-an-azure-active-directory-tenant.md) do celów testowych.

> [!NOTE]
> Chcesz zamiast tego osadzić pulpit nawigacyjny dla klientów przy użyciu tokenu osadzania? Zobacz [Integrowanie pulpitu nawigacyjnego, kafelka lub raportu w aplikacji dla klientów](embed-sample-for-customers.md).
> 
> 

Aby zintegrować pulpit nawigacyjny z aplikacją internetową, należy użyć interfejsu API REST usługi **Power BI** lub zestawu SDK C# usługi Power BI oraz **tokenu dostępu** uwierzytelniania usługi Azure Active Directory (AD) w celu uzyskania pulpitu nawigacyjnego. Następnie należy załadować pulpit nawigacyjny przy użyciu tego samego tokenu dostępu. Interfejs API usługi **Power BI** zapewnia dostęp programowy do określonych zasobów usługi **Power BI**. Aby uzyskać więcej informacji, zobacz [Omówienie interfejsu API REST usługi Power BI](https://msdn.microsoft.com/library/dn877544.aspx) i [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) (Interfejs API języka JavaScript usługi Power BI).

## <a name="download-the-sample"></a>Pobieranie przykładu
W tym artykule przedstawiono kod używany w aplikacji [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) w witrynie GitHub. Aby korzystać z tego przewodnika, możesz pobrać przykład.

## <a name="step-1---register-an-app-in-azure-ad"></a>Krok 1. Rejestrowanie aplikacji w usłudze Azure AD
Aplikację należy zarejestrować w usłudze Azure AD, aby móc wykonywać wywołania interfejsu API REST. Aby uzyskać więcej informacji, zobacz [Rejestrowanie aplikacji usługi Azure AD, aby osadzić zawartość usługi Power BI](register-app.md).

Jeśli pobrano [przykład integrowania pulpitu nawigacyjnego](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), użyj **identyfikatora klienta** i **klucza tajnego klienta** otrzymanego po zarejestrowaniu, aby przykład mógł uwierzytelniać się w usłudze Azure AD. Aby skonfigurować przykład, zmień wartości **Client ID** (Identyfikator klienta) i **Client Secret** (Klucz tajny klienta) w pliku *cloud.config*.

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Krok 2. Uzyskiwanie tokenu dostępu z usługi Azure AD
W aplikacji należy najpierw uzyskać **token dostępu** z usługi Azure AD, aby móc wykonywać wywołania interfejsu API REST usługi Power BI. Aby uzyskać więcej informacji, zobacz [Uwierzytelnianie użytkowników i uzyskiwanie tokenów dostępu usługi Azure AD dla aplikacji usługi Power BI](get-azuread-access-token.md).

## <a name="step-3---get-a-dashboard"></a>Krok 3. Uzyskiwanie pulpitu nawigacyjnego
Aby uzyskać pulpit nawigacyjny usługi **Power BI**, należy użyć operacji [uzyskiwania pulpitów nawigacyjnych](https://msdn.microsoft.com/library/mt465739.aspx), zwracającej listę pulpitów nawigacyjnych usługi **Power BI**. Z listy pulpitów nawigacyjnych możesz uzyskać identyfikator pulpitu nawigacyjnego.

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>Uzyskiwanie pulpitów nawigacyjnych przy użyciu tokenu dostępu
Możesz użyć **tokenu dostępu** pobranego w [kroku 2.](#step-2-get-an-access-token-from-azure-ad), wywołując operację [uzyskiwania pulpitów nawigacyjnych](https://msdn.microsoft.com/library/mt465739.aspx). Operacja [uzyskiwania pulpitów nawigacyjnych](https://msdn.microsoft.com/library/mt465739.aspx) zwraca listę pulpitów nawigacyjnych. Z listy pulpitów nawigacyjnych możesz uzyskać wybrany pulpit nawigacyjny. Poniżej przedstawiono całą metodę języka C# umożliwiającą uzyskanie pulpitu nawigacyjnego. Przykłady korzystania z interfejsu API REST usługi Power BI można znaleźć w artykule [Power BI REST API](http://docs.powerbi.apiary.io/) (Interfejs API REST usługi Power BI) w witrynie APIARY.

Aby wykonać wywołanie interfejsu API REST, należy użyć nagłówka *Authorization* w formacie *Bearer {token dostępu}*.

#### <a name="get-dashboards-with-the-rest-api"></a>Uzyskiwanie pulpitów nawigacyjnych przy użyciu interfejsu API REST
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>Uzyskiwanie pulpitów nawigacyjnych przy użyciu zestawu SDK .NET
Listę pulpitów nawigacyjnych możesz uzyskać przy użyciu zestawu SDK .NET zamiast bezpośredniego wywoływania interfejsu API REST.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>Krok 4. Ładowanie pulpitu nawigacyjnego przy użyciu języka JavaScript
Języka JavaScript można użyć do załadowania pulpitu nawigacyjnego do elementu div na stronie internetowej.

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

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
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Jeśli pobrano i uruchomiono [przykład integrowania pulpitu nawigacyjnego](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), będzie on wyglądać podobnie jak na poniższej ilustracji.

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>Zdarzenia po kliknięciu kafelka
Jak widać w powyższym przykładzie, można obsługiwać zdarzenia w przypadku kliknięcia kafelka na pulpicie nawigacyjnym. Aby uzyskać więcej informacji na temat zdarzeń, zobacz [Handling Events within the JavaScript API (Obsługa zdarzeń w interfejsie API języka JavaScript)](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

Jeśli pobrano i uruchomiono [przykład integrowania pulpitu nawigacyjnego](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app), kliknięcie kafelka spowoduje wyświetlenie tekstu wyjściowego pod pulpitem nawigacyjnym. Tekst będzie wyglądał mniej więcej tak. To umożliwia zarejestrowanie kliknięcia kafelka i skierowanie użytkownika do określonej lokalizacji.

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>Praca z grupami (obszarami roboczymi aplikacji)
Aby osadzić pulpit nawigacyjny z grupy (obszaru roboczego aplikacji), należy uzyskać listę wszystkich dostępnych pulpitów nawigacyjnych w grupie przy użyciu następującego wywołania interfejsu API REST. Aby uzyskać więcej informacji na temat tego wywołania interfejsu API REST, zobacz [Get Dashboards (Uzyskiwanie pulpitów nawigacyjnych)](https://msdn.microsoft.com/library/mt465739.aspx). Aby żądanie zwróciło wyniki, musisz mieć uprawnienia w tej grupie.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

Powyższe wywołanie interfejsu API zwraca listę wszystkich dostępnych pulpitów nawigacyjnych. Każdy pulpit nawigacyjny ma właściwość EmbedUrl, skonstruowaną tak, aby obsługiwać osadzanie z grup.

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>Ograniczenia
* Użytkownicy końcowi korzystający z osadzonego pulpitu nawigacyjnego muszą mieć konta usługi Power BI oraz dostęp do tego pulpitu nawigacyjnego. Pulpit nawigacyjny może zostać im udostępniony lub mogą oni być jego właścicielami.
* W przypadku osadzonych pulpitów nawigacyjnych funkcja pytań i odpowiedzi nie jest obsługiwana.
* W związku z tymczasowym ograniczeniem podczas udostępniania pulpitu nawigacyjnego z użyciem grup zabezpieczeń użytkownicy muszą najpierw uzyskać dostęp do pulpitu nawigacyjnego w witrynie PowerBI.com, aby móc wyświetlić osadzony pulpit nawigacyjny.

## <a name="next-steps"></a>Następne kroki
Przykładowa aplikacja jest dostępna w witrynie GitHub do przeglądu. Powyższe przykłady są oparte na tym przykładzie. Aby uzyskać więcej informacji, zobacz [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app).

Aby uzyskać więcej informacji dotyczących interfejsu API języka JavaScript, zobacz [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) (Interfejs API języka JavaScript usługi Power BI).

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

