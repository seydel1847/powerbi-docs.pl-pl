---
title: Osadzanie zawartości usługi Power BI w aplikacji dla organizacji
description: Dowiedz się, jak integrować albo osadzać raport, pulpit nawigacyjny lub kafelek w aplikacji internetowej przy użyciu interfejsów API usługi Power BI dla organizacji.
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: cfc450216202f332f518955d28cb71df6aa0b800
ms.sourcegitcommit: f2b106b5eb338a64f903e8ce6793bccb07f9440a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2018
ms.locfileid: "39105274"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-organization"></a>Samouczek: osadzanie raportu, pulpitu nawigacyjnego lub kafelka usługi Power BI w aplikacji dla organizacji
W tym samouczku przedstawiono sposób integrowania raportu w aplikacji przy użyciu **zestawu .NET SDK usługi Power BI** z **interfejsem API języka JavaScript usługi Power BI** w przypadku osadzania usługi **Power BI** w aplikacji dla organizacji. Usługa **Power BI** umożliwia osadzanie raportów, pulpitów nawigacyjnych lub kafelków w aplikacji przy użyciu struktury **user owns data** (użytkownik jest właścicielem danych). Struktura **user owns data** umożliwia Twojej aplikacji rozszerzenie usługi Power BI.

![Wyświetlanie aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

Z tego samouczka dowiesz się, jak wykonywać następujące czynności:
>[!div class="checklist"]
>* Rejestrowanie aplikacji na platformie Azure.
>* Osadzanie raportu usługi Power BI w aplikacji.

## <a name="prerequisites"></a>Wymagania wstępne
Do rozpoczęcia pracy potrzebne jest konto usługi **Power BI Pro** i subskrypcja platformy **Microsoft Azure**.

* Jeśli nie masz konta usługi **Power BI Pro**, na początku [zacznij korzystać z bezpłatnej wersji próbnej](https://powerbi.microsoft.com/en-us/pricing/).
* Jeśli nie masz subskrypcji platformy Azure, przed rozpoczęciem utwórz [bezpłatne konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).
* Musisz mieć własną konfigurację [dzierżawy usługi Azure Active Directory](create-an-azure-active-directory-tenant.md).
* Musisz mieć zainstalowany program [Visual Studio](https://www.visualstudio.com/) (w wersji 2013 lub nowszej).

## <a name="setup-your-embedded-analytics-development-environment"></a>Konfigurowanie środowiska deweloperskiego analizy osadzonej

Przed rozpoczęciem osadzania raportów, pulpitów nawigacyjnych lub kafelków w aplikacji należy upewnić się, że środowisko skonfigurowano w sposób umożliwiający osadzanie. W ramach konfiguracji należy wykonać następujące działania.

Możesz użyć [narzędzia obsługi dołączania](https://aka.ms/embedsetup/UserOwnsData), aby szybko zacząć pracę i pobrać przykładową aplikację, która pomoże przeprowadzić Cię przez proces tworzenia środowiska i osadzania raportu.

Jeśli jednak chcesz ręcznie skonfigurować środowisko, kontynuuj czytanie.
### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>Rejestrowanie aplikacji w usłudze Azure Active Directory (Azure AD)

Aplikację można zarejestrować w usłudze Azure Active Directory, aby zapewnić aplikacji dostęp do interfejsów API REST usługi Power BI. Dzięki temu można ustanowić tożsamość aplikacji i określić jej uprawnienia do zasobów REST usługi Power BI.

1. Zaakceptuj [Warunki interfejsu API usługi Microsoft Power BI](https://powerbi.microsoft.com/api-terms).

2. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com).

    ![Główna część witryny Azure Portal](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

3. W okienku nawigacji po lewej stronie wybierz kolejno pozycje **Wszystkie usługi** i **Rejestracje aplikacji**, a następnie kliknij przycisk **Rejestrowanie nowej aplikacji**.

    ![Wyszukiwanie rejestracji aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)</br>
    ![Nowa rejestracja aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-004.png)

4. Postępuj zgodnie z monitami i utwórz nową aplikację. W przypadku struktury **user owns data** użyj typu aplikacji **Interfejs API/aplikacja internetowa**. Podaj również **Adres URL logowania**, którego usługa **Azure AD** używa do zwracania odpowiedzi tokenu. Wprowadź wartość specyficzną dla Twojej aplikacji (na przykład http://localhost:13526/)

    ![Tworzenie aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>Stosowanie uprawnień do aplikacji w usłudze Azure Active Directory

Musisz włączyć dodatkowe uprawnienia aplikacji oprócz tych, które zostały podane na stronie rejestrowania aplikacji. Aby włączyć uprawnienia, musisz się zalogować przy użyciu konta *administratora globalnego*.

### <a name="use-the-azure-active-directory-portal"></a>Korzystanie z portalu usługi Azure Active Directory

1. Przejdź do obszaru [Rejestracje aplikacji](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) w witrynie Azure Portal i wybierz aplikację, której używasz do osadzania.

    ![Wybieranie aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

2. Wybierz pozycję **Ustawienia**, a następnie w obszarze **Dostęp do interfejsu API** wybierz pozycję **Wymagane uprawnienia**.

    ![Wymagane uprawnienia](media/embed-sample-for-your-organization/embed-sample-for-your-organization-008.png)

3. Wybierz pozycję **Windows Azure Active Directory**, a następnie upewnij się, że wybrana jest pozycja **Uzyskuj dostęp do katalogu jako zalogowany użytkownik**. Wybierz pozycję **Zapisz**.

    ![Uprawnienia usługi Windows Azure AD](media/embed-sample-for-your-organization/embed-sample-for-your-organization-011.png)

4. Wybierz pozycję **Dodaj**.

    ![Dodawanie uprawnień](media/embed-sample-for-your-organization/embed-sample-for-your-organization-012.png)

5. Wybierz pozycję **Wybierz interfejs API**.

    ![Dodawanie dostępu do interfejsu API](media/embed-sample-for-your-organization/embed-sample-for-your-organization-013.png)

6. Wybierz pozycję **Usługa Power BI**, a następnie wybierz pozycję **Wybierz**.

    ![Wybieranie usług PBI](media/embed-sample-for-your-organization/embed-sample-for-your-organization-014.png)

7. Wybierz wszystkie uprawnienia w obszarze **Delegowane uprawnienia**. W celu zapisania wyborów musisz je zaznaczać pojedynczo. Po zakończeniu wybierz pozycję **Zapisz**.

    ![Wybieranie delegowanych uprawnień](media/embed-sample-for-your-organization/embed-sample-for-your-organization-015.png)

## <a name="setup-your-power-bi-environment"></a>Konfigurowanie środowiska usługi Power BI

### <a name="create-an-app-workspace"></a>Tworzenie obszaru roboczego aplikacji

W przypadku osadzania raportów, pulpitów nawigacyjnych lub kafelków dla klientów należy umieścić zawartość w obszarze roboczym aplikacji.

1. Rozpocznij od utworzenia obszaru roboczego. Wybierz pozycję **Obszary robocze** > **Utwórz obszar roboczy aplikacji**. W tym miejscu jest umieszczana zawartość, do której aplikacja musi uzyskiwać dostęp.

    ![Tworzenie obszaru roboczego](media/embed-sample-for-your-organization/embed-sample-for-your-organization-020.png)

2. Nadaj nazwę obszarowi roboczemu. Jeśli odpowiedni **Identyfikator obszaru roboczego** nie jest dostępny, edytuj go, aby skorzystać z unikatowego identyfikatora. Musi to być również nazwa aplikacji.

    ![Nazywanie obszaru roboczego](media/embed-sample-for-your-organization/embed-sample-for-your-organization-021.png)

3. Istnieje kilka opcji do ustawienia. Jeśli wybierzesz opcję **Publiczny**, wszystkie osoby w organizacji będą mogły zobaczyć zawartość tego obszaru roboczego. Z drugiej strony opcja **Prywatny** oznacza, że tylko członkowie obszaru roboczego będą mogli wyświetlić jego zawartość.

    ![Prywatny/Publiczny](media/embed-sample-for-your-organization/embed-sample-for-your-organization-022.png)

    Nie możesz zmienić ustawienia Publiczny/Prywatny po utworzeniu grupy.

4. Ponadto możesz zdecydować, czy członkowie uzyskają dostęp do **edycji** lub **tylko do wyświetlania**.

    ![Dodawanie członków](media/embed-sample-for-your-organization/embed-sample-for-your-organization-023.png)

5. Dodaj adresy e-mail osób, które mają mieć dostęp do obszaru roboczego, a następnie wybierz opcję **Dodaj**. Nie można dodawać aliasów grupy, tylko osoby.

6. Zdecyduj wobec każdej osoby, czy jest członkiem, czy administratorem. Administratorzy mogą edytować obszar roboczy, w tym dodawać innych członków. Członkowie mogą edytować zawartość w obszarze roboczym, chyba że mają dostęp tylko do wyświetlania. Administratorzy i członkowie mogą opublikować aplikację.

    Teraz możesz wyświetlić nowy obszar roboczy. Usługa Power BI tworzy obszar roboczy i otwiera go. Zostanie on wyświetlony na liście obszarów roboczych, których członkiem jesteś. Jako że jesteś administratorem, możesz wybrać wielokropek (...), aby powrócić i wprowadzić zmiany, dodając nowych członków lub zmieniając ich uprawnienia.

    ![Tworzenie obszaru roboczego](media/embed-sample-for-your-organization/embed-sample-for-your-organization-025.png)

### <a name="create-and-publish-your-reports"></a>Tworzenie i publikowanie raportów

Raporty i zestawy danych można tworzyć przy użyciu programu Power BI Desktop, a następnie publikować je w obszarze roboczym aplikacji. Aby móc publikować raporty w obszarze roboczym aplikacji, użytkownik końcowy publikujący je musi mieć licencję usługi Power BI Pro.

1. Pobierz przykład [Blog Demo](https://github.com/Microsoft/powerbi-desktop-samples) (Pokaz bloga) z usługi GitHub.

    ![przykładowy raport](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026-1.png)

2. Otwórz przykładowy raport PBIX w programie **Power BI Desktop**.

   ![Raport programu PBI Desktop](media/embed-sample-for-your-organization/embed-sample-for-your-organization-027.png)

3. Opublikuj w **obszarze roboczym aplikacji**.

   ![Raport programu PBI Desktop](media/embed-sample-for-your-organization/embed-sample-for-your-organization-028.png)

    Teraz możesz przeglądać raport w trybie online za pomocą usługi Power BI.

   ![Raport programu PBI Desktop](media/embed-sample-for-your-organization/embed-sample-for-your-organization-029.png)

## <a name="embed-your-content-using-the-sample-application"></a>Osadzanie zawartości za pomocą przykładowej aplikacji

Wykonaj następujące kroki, aby rozpocząć osadzanie zawartości za pomocą przykładowej aplikacji.

1. Pobierz [przykład User Owns Data](https://github.com/Microsoft/PowerBI-Developer-Samples) z usługi GitHub, aby rozpocząć pracę.  Istnieją 3 różne przykładowe aplikacje, jedna dla [raportów](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), druga dla [pulpitów nawigacyjnych](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) i trzecia dla [kafelków](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app).  Ten artykuł dotyczy aplikacji dla **raportów**, która jest omawiana w poniższych krokach.

    ![Przykład aplikacji User Owns Data](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026.png)

2. Otwórz plik Cloud.config w przykładowej aplikacji. Aby pomyślnie uruchomić aplikację, należy wypełnić kilka pól. Pola **ClientID** i **ClientSecret**.

    ![Plik Cloud.config](media/embed-sample-for-your-organization/embed-sample-for-your-organization-030.png)

    W polu **ClientID** podaj **Identyfikator aplikacji** z platformy **Azure**. Za pomocą wartości **ClientID** aplikacja identyfikuje się dla użytkowników, od których żądasz uprawnień.

    Aby uzyskać wartość **ClientID**, wykonaj następujące czynności:

    Zaloguj się w witrynie [Azure Portal](https://portal.azure.com).

    ![Główna część witryny Azure Portal](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    W okienku nawigacji po lewej stronie wybierz pozycję **Wszystkie usługi** i pozycję **Rejestracje aplikacji**.

    ![Wyszukiwanie rejestracji aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    Wybierz aplikację, która ma używać wartości **ClientID**.

    ![Wybieranie aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    Powinien zostać wyświetlony **identyfikator aplikacji** wymieniony jako identyfikator GUID. Użyj tego **identyfikatora aplikacji** jako wartości **ClientID** dla aplikacji.

    ![Identyfikator_klienta](media/embed-sample-for-your-organization/embed-sample-for-your-organization-007.png)

    W polu **ClientSecret** podaj informacje z sekcji **Klucze** obszaru **Rejestracje aplikacji** na platformie **Azure**.

    Aby uzyskać wartość **ClientSecret**, wykonaj następujące czynności:

    Zaloguj się w witrynie [Azure Portal](https://portal.azure.com).

    ![Główna część witryny Azure Portal](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    W okienku nawigacji po lewej stronie wybierz pozycję **Wszystkie usługi** i pozycję **Rejestracje aplikacji**.

    ![Wyszukiwanie rejestracji aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    Wybierz aplikację, która musi używać wartości **ClientSecret**.

    ![Wybieranie aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    Wybierz pozycję **Ustawienia**.

    ![Ustawienia](media/embed-sample-for-your-organization/embed-sample-for-your-organization-038.png)

    Wybierz sekcję **Klucze**.

    ![Klucze](media/embed-sample-for-your-organization/embed-sample-for-your-organization-039.png)

    W polu **Opis** podaj nazwę i wybierz opcję w polu **Czas trwania**, a następnie wybierz przycisk **Zapisz**, aby uzyskać **Wartość** dla aplikacji. Gdy zamkniesz blok **Klucze** po zapisaniu **wartości klucza**, pole będzie zawierało jedynie wartość **_Ukryta_** i od tego momentu nie będzie można pobrać **wartości klucza**. W przypadku utraty **wartości klucza** musisz utworzyć nowy klucz w witrynie **Azure Portal**.

    ![Klucze](media/embed-sample-for-your-organization/embed-sample-for-your-organization-031.png)

     W polu **groupId** podaj **identyfikator GUID obszaru roboczego aplikacji** z usługi Power BI.

    ![groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    W polu **reportId** podaj **identyfikator GUID** z usługi Power BI.

    ![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

3. Uruchom aplikację!

    Najpierw wybierz pozycję **Uruchom** w programie **Visual Studio**.

    ![Uruchamianie aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-033.png)

    Następnie wybierz pozycję **Pobierz raport**.

    ![Wybieranie zawartości](media/embed-sample-for-your-organization/embed-sample-for-your-organization-034.png)

    Teraz możesz przeglądać raport w przykładowej aplikacji.

    ![Wyświetlanie aplikacji](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

## <a name="embed-your-content-within-your-application"></a>Osadzanie zawartości w aplikacji
Mimo że kroki osadzania zawartości można wykonać przy użyciu [interfejsów API REST usługi Power BI](https://docs.microsoft.com/rest/api/power-bi/), przykładowe kody opisane w tym artykule są tworzone przy użyciu **zestawu SDK platformy .NET**.

Aby zintegrować raport z aplikacją internetową, należy użyć **interfejsu API REST usługi Power BI** lub **zestawu SDK C# usługi Power BI** oraz **tokenu dostępu** autoryzacji usługi Azure Active Directory (AD) w celu uzyskania raportu. Następnie należy załadować raport przy użyciu tego samego **tokenu dostępu**. **Interfejs API REST usługi Power BI** zapewnia dostęp programowy do określonych zasobów usługi **Power BI**. Aby uzyskać więcej informacji, zobacz [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) (Interfejs API REST usługi Power BI) i [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) (Interfejs API języka JavaScript usługi Power BI).

### <a name="get-an-access-token-from-azure-ad"></a>Uzyskiwanie tokenu dostępu z usługi Azure AD
W aplikacji należy najpierw uzyskać **token dostępu** z usługi Azure AD, aby móc wykonywać wywołania interfejsu API REST usługi Power BI. Aby uzyskać więcej informacji, zobacz [Uwierzytelnianie użytkowników i uzyskiwanie tokenów dostępu usługi Azure AD dla aplikacji usługi Power BI](get-azuread-access-token.md).

### <a name="get-a-report"></a>Uzyskiwanie raportu
Aby uzyskać raport usługi **Power BI**, należy użyć operacji [uzyskiwania raportów](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) zwracającej listę **raportów usługi Power BI**. Z listy raportów można uzyskać identyfikator raportu.

### <a name="get-reports-using-an-access-token"></a>Uzyskiwanie raportów przy użyciu tokenu dostępu
Operacja [uzyskiwania raportów](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) zwraca listę raportów. Z tej listy raportów można uzyskać pojedynczy raport.

Aby wykonać wywołanie interfejsu API REST, należy użyć nagłówka *Authorization* w formacie *Bearer {token dostępu}*.

#### <a name="get-reports-with-the-rest-api"></a>Uzyskiwanie raportów za pomocą interfejsu API REST

Oto przykład kodu służącego do pobierania raportów za pomocą **interfejsu API REST**.

*Przykład pobierania elementu zawartości do osadzenia (raport, pulpit nawigacyjny lub kafelek) jest dostępny w pliku **_Default.aspx.cs_** w [przykładowej aplikacji](#embed-your-content-using-the-sample-application).*

```csharp
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
Listę raportów możesz uzyskać przy użyciu zestawu SDK .NET zamiast bezpośredniego wywoływania interfejsu API REST. Oto przykład kodu służącego do sporządzania listy raportów.

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It is used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

### <a name="load-a-report-using-javascript"></a>Ładowanie raportu przy użyciu języka JavaScript
Do załadowania raportu do elementu div na stronie internetowej można użyć języka JavaScript.

Oto przykład kodu służącego do pobierania raportu z danego obszaru roboczego.

*Przykład ładowania elementu zawartości — raportu, pulpitu nawigacyjnego lub kafelka — do osadzenia jest dostępny w pliku **_Default.aspx_** w [przykładowej aplikacji](#embed-your-content-using-the-sample-application).*

```javascript
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

```javascript
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
    }
  );
}
```

## <a name="using-a-power-bi-premium-dedicated-capacity"></a>Używanie dedykowanej pojemności usługi Power BI Premium

Tworzenie aplikacji zakończyło się i należy teraz zapewnić dedykowaną pojemność w obszarze roboczym aplikacji.

### <a name="create-a-dedicated-capacity"></a>Tworzenie pojemności dedykowanej
Utworzenie pojemności dedykowanej pozwala skorzystać z zalet zasobu dedykowanego dla zawartości w obszarze roboczym aplikacji. Jeśli obszar roboczy nie jest przypisany do pojemności dedykowanej, jest to pojemność udostępniona. Pojemność dedykowaną możesz utworzyć przy użyciu usługi [Power BI Premium](../service-admin-premium-purchase.md).

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>Przypisywanie obszaru roboczego aplikacji do pojemności dedykowanej

Po utworzeniu pojemności dedykowanej możesz do niej przypisać obszar roboczy aplikacji. Aby zakończyć ten proces, wykonaj następujące kroki.

1. W ramach **usługi Power BI** rozwiń obszary robocze i wybierz przycisk wielokropka dla obszaru roboczego, za pomocą którego osadzasz zawartość. Następnie wybierz pozycję **Edytuj obszary robocze**.

    ![Edytowanie obszaru roboczego](media/embed-sample-for-your-organization/embed-sample-for-your-organization-036.png)

2. Rozwiń węzeł **Zaawansowane**, włącz pozycję **Pojemność dedykowana**, a następnie wybierz utworzoną pojemność dedykowaną. Następnie wybierz pozycję **Zapisz**.

    ![Przypisywanie pojemności dedykowanej](media/embed-sample-for-your-organization/embed-sample-for-your-organization-024.png)

3. Po wybraniu pozycji **Zapisz** obok nazwy obszaru roboczego aplikacji powinna zostać wyświetlona ikona **diamentu**.

    ![obszar roboczy aplikacji powiązany z pojemnością](media/embed-sample-for-your-organization/embed-sample-for-your-organization-037.png)

## <a name="next-steps"></a>Następne kroki
W tym samouczku przedstawiono sposób osadzania zawartości usługi Power BI w aplikacji za pomocą **konta organizacji usługi Power BI**. Teraz możesz spróbować osadzić zawartość usługi Power BI w aplikacji przy użyciu aplikacji.  Zawartość usługi Power BI możesz również spróbować osadzić dla klientów innych firm.

> [!div class="nextstepaction"]
> [Osadź z aplikacji](embed-from-apps.md)

> [!div class="nextstepaction"]
>[Osadź dla klientów innych firm](embed-sample-for-customers.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)