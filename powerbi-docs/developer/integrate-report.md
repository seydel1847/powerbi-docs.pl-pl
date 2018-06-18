---
title: Integrowanie raportu usługi Power BI z aplikacją dla organizacji
description: Dowiedz się, jak integrować lub osadzać raport w aplikacji internetowej przy użyciu interfejsów API usługi Power BI.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 032e0ed05d56d2d7f1e2b41cfd922999ff43ea94
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/06/2018
ms.locfileid: "34813371"
---
# <a name="integrate-a-report-into-an-app-for-your-organization"></a>Integrowanie raportu z aplikacją dla organizacji
Dowiedz się, jak integrować lub osadzać raport w aplikacji internetowej przy użyciu wywołań interfejsu API REST wraz z interfejsem API języka JavaScript usługi Power BI podczas osadzania dla organizacji.

![Przykładowy osadzony raport](media/integrate-report/powerbi-embedded-report.png)

Do rozpoczęcia pracy z tym przewodnikiem jest wymagane konto usługi **Power BI**. Jeśli nie masz konta, możesz [utworzyć bezpłatne konto usługi Power BI](../service-self-service-signup-for-power-bi.md) lub utworzyć własną [dzierżawę usługi Azure Active Directory](create-an-azure-active-directory-tenant.md) do celów testowych.

> [!NOTE]
> Chcesz zamiast tego osadzić raport dla klientów przy użyciu tokenu osadzania? Zobacz [Integrowanie pulpitu nawigacyjnego, kafelka lub raportu w aplikacji dla klientów](embed-sample-for-customers.md).
> 
> 

Aby zintegrować raport z aplikacją internetową, należy użyć interfejsu API REST usługi **Power BI** lub zestawu SDK C# usługi Power BI oraz **tokenu dostępu** uwierzytelniania usługi Azure Active Directory (AD) w celu uzyskania raportu. Następnie należy załadować raport przy użyciu tego samego tokenu dostępu. Interfejs API usługi **Power BI** zapewnia dostęp programowy do określonych zasobów usługi **Power BI**. Aby uzyskać więcej informacji, zobacz [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) (Interfejs API REST usługi Power BI) i [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) (Interfejs API języka JavaScript usługi Power BI).

## <a name="download-the-sample"></a>Pobieranie przykładu
W tym artykule przedstawiono kod używany w aplikacji [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) w witrynie GitHub. Aby korzystać z tego przewodnika, możesz pobrać przykład.

Możesz także użyć [narzędzia obsługi dołączania](https://aka.ms/embedsetup/UserOwnsData), aby szybko rozpocząć pracę i pobrać przykładową aplikację.

Jeśli jednak chcesz ręcznie skonfigurować środowisko, kontynuuj czytanie.

## <a name="step-1---register-an-app-in-azure-ad"></a>Krok 1. Rejestrowanie aplikacji w usłudze Azure AD
Aplikację należy zarejestrować w usłudze Azure AD, aby móc wykonywać wywołania interfejsu API REST. Aby uzyskać więcej informacji, zobacz [Rejestrowanie aplikacji usługi Azure AD, aby osadzić zawartość usługi Power BI](register-app.md).

Jeśli pobrano przykład [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), użyj **identyfikatora klienta** i **klucza tajnego klienta** otrzymanego po zarejestrowaniu, aby przykład mógł uwierzytelniać się w usłudze Azure AD. Aby skonfigurować przykład, zmień wartości **Client ID** (Identyfikator klienta) i **Client Secret** (Klucz tajny klienta) w pliku *cloud.config*.

![](media/integrate-report/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Krok 2. Uzyskiwanie tokenu dostępu z usługi Azure AD
W aplikacji należy najpierw uzyskać **token dostępu** z usługi Azure AD, aby móc wykonywać wywołania interfejsu API REST usługi Power BI. Aby uzyskać więcej informacji, zobacz [Uwierzytelnianie użytkowników i uzyskiwanie tokenów dostępu usługi Azure AD dla aplikacji usługi Power BI](get-azuread-access-token.md).

## <a name="step-3---get-a-report"></a>Krok 3. Uzyskiwanie raportu
Aby uzyskać raport usługi **Power BI**, należy użyć operacji [uzyskiwania raportów](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) zwracającej listę raportów usługi **Power BI**. Z listy raportów można uzyskać identyfikator raportu.

### <a name="get-reports-using-an-access-token"></a>Uzyskiwanie raportów przy użyciu tokenu dostępu
Możesz użyć **tokenu dostępu** pobranego w [kroku 2.](#step-2-get-an-access-token-from-azure-ad), wywołując operację [uzyskiwania raportów](https://docs.microsoft.com/rest/api/power-bi/reports/getreports). Operacja [uzyskiwania raportów](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) zwraca listę raportów. Z tej listy raportów można uzyskać pojedynczy raport. Poniżej przedstawiono całą metodę języka C# umożliwiającą uzyskanie raportu. 

Aby wykonać wywołanie interfejsu API REST, należy użyć nagłówka *Authorization* w formacie *Bearer {token dostępu}*.

#### <a name="get-reports-with-the-rest-api"></a>Uzyskiwanie raportów za pomocą interfejsu API REST
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>Uzyskiwanie raportów za pomocą zestawu SDK .NET
Listę raportów możesz uzyskać przy użyciu zestawu SDK .NET zamiast bezpośredniego wywoływania interfejsu API REST.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## <a name="step-4---load-a-report-using-javascript"></a>Krok 4. Ładowanie raportu przy użyciu języka JavaScript
Do załadowania raportu do elementu div na stronie internetowej można użyć języka JavaScript.

**Default.aspx**

```
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

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
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Jeśli pobrano i uruchomiono przykład [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), będzie on wyglądać podobnie jak na poniższej ilustracji.

![Przykładowy osadzony raport](media/integrate-report/powerbi-embedded-report.png)

## <a name="working-with-groups-app-workspaces"></a>Praca z grupami (obszarami roboczymi aplikacji)
Aby osadzić raport z grupy (obszaru roboczego aplikacji), należy uzyskać listę wszystkich dostępnych raportów na pulpicie nawigacyjnym grupy przy użyciu następującego wywołania interfejsu API REST. Aby uzyskać więcej informacji na temat tego wywołania interfejsu API REST, zobacz [Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) (Uzyskiwanie raportów). Aby żądanie zwróciło wyniki, musisz mieć uprawnienia w tej grupie.

```
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

Powyższe wywołanie interfejsu API zwraca listę wszystkich dostępnych raportów. Każdy raport ma właściwość EmbedUrl skonstruowaną tak, aby obsługiwać osadzanie z grup.

```
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

## <a name="next-steps"></a>Następne kroki
Przykładowa aplikacja jest dostępna w witrynie GitHub do przeglądu. Aby uzyskać więcej informacji, zobacz [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app).

Aby uzyskać więcej informacji dotyczących interfejsu API języka JavaScript, zobacz [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) (Interfejs API języka JavaScript usługi Power BI).

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

