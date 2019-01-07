---
title: Portal administracyjny usługi Power BI
description: Portal administracyjny umożliwia zarządzanie dzierżawą usługi Power BI w organizacji. Zawiera on kluczowe elementy, takie jak metryki użycia, dostęp do centrum administracyjnego usługi Office 365 oraz ustawienia.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/30/2018
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 6fff11d37b0f099effeafb6b88dbfa68af88f3d6
ms.sourcegitcommit: f5e39e9ead37445bbeab795890b3d80633383032
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2018
ms.locfileid: "53735574"
---
# <a name="administering-power-bi-in-the-admin-portal"></a>Administrowanie usługą Power BI w portalu administracyjnym

Portal administracyjny pozwala na zarządzanie *dzierżawą* usługi Power BI w organizacji. Portal zawiera elementy, takie jak metryki użycia, dostęp do centrum administracyjnego usługi Office 365 oraz ustawienia.

Pełny portal administracyjny jest dostępny dla wszystkich użytkowników, którzy są administratorami globalnymi w usłudze Office 365 lub którym przydzielono rolę administratora usługi Power BI. Jeśli nie pełnisz żadnej z tych ról, w portalu są widoczne tylko **ustawienia pojemności**. Aby uzyskać więcej informacji o roli administratora usługi Power BI, zobacz [Opis roli administratora usługi Power BI](service-admin-role.md).

## <a name="how-to-get-to-the-admin-portal"></a>Jak uzyskać dostęp do portalu administracyjnego

Twoje konto musi być oznaczone jako **Administrator globalny**, w usłudze Office 365 lub Azure Active Directory, albo musisz uzyskać przydział do roli administratora usługi Power BI, aby uzyskać dostęp do portalu administracyjnego usługi Power BI. Aby uzyskać więcej informacji o roli administratora usługi Power BI, zobacz [Opis roli administratora usługi Power BI](service-admin-role.md). Aby uzyskać dostęp do portalu administracyjnego usługi Power BI, wykonaj następujące czynności.

1. Wybierz koło zębate ustawień w prawym górnym rogu usługi Power BI.

1. Wybierz pozycję **Portal administracyjny**.

    ![Ustawienia portalu administracyjnego](media/service-admin-portal/powerbi-admin-settings.png)

Portal zawiera siedem kart. W pozostałej części tego artykułu przedstawiono informacje na temat każdej z tych kart.

![Nawigacja w portalu administracyjnym](media/service-admin-portal/powerbi-admin-landing-page.png)

* [Metryki użycia](#usage-metrics)
* [Użytkownicy](#users)
* [Dzienniki inspekcji](#audit-logs)
* [Ustawienia dzierżawy](#tenant-settings)
* [Ustawienia — wersja Premium](#premium-settings)
* [Kody osadzania](#embed-codes)
* [Organization visuals](#organization-visuals) (Wizualizacje organizacji)

## <a name="usage-metrics"></a>Metryki użycia

Karta **Metryki użycia** umożliwia monitorowanie użycia usługi Power BI w organizacji. Ponadto zapewnia możliwość wyświetlania najbardziej aktywnych użytkowników i grup w usłudze Power BI w ramach organizacji.

> [!NOTE]
> Przy pierwszym uzyskaniu dostępu do pulpitu nawigacyjnego lub po powrocie do pulpitu nawigacyjnego po długim czasie najprawdopodobniej zobaczysz ekran ładowania, gdy będziemy ładować pulpit nawigacyjny.

Po załadowaniu pulpitu nawigacyjnego zobaczysz dwie sekcje kafelków. Pierwsza sekcja obejmuje dane użycia dla poszczególnych użytkowników, a druga sekcja zawiera podobne informacje dotyczące grup w organizacji.

Oto podział elementów, które możesz zobaczyć w każdym kafelków:

* Unikatowy licznik dla wszystkich pulpitów nawigacyjnych, raportów i zestawów danych w obszarze roboczym użytkownika
  
    ![Unikatowy licznik dla pulpitów nawigacyjnych, raportów i zestawów danych](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* Najczęściej używany pulpit nawigacyjny według liczby użytkowników, którzy mogą do niego uzyskać dostęp. Jeśli na przykład masz pulpit nawigacyjny, który został udostępniony 3 użytkownikom oraz został dodany do pakietu zawartości, z którym łączy się dwóch różnych użytkowników, licznik będzie wskazywać 6 (1 + 3 +2)
  
    ![Najczęściej używane pulpity nawigacyjne](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* Najpopularniejsza zawartość, z którą łączą się użytkownicy. Będzie to wszystko to, z czym użytkownicy mogą się połączyć za pośrednictwem procesu Pobierz dane, a więc pakiety zawartości SaaS, pakiety zawartości organizacji, pliki lub bazy danych.
  
    ![Najczęściej używane pakiety](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* Widok użytkowników oparty na liczbie posiadanych przez nich pulpitów nawigacyjnych, zarówno utworzonych przez użytkowników, jak i tych udostępnionych.
  
    ![Najaktywniejsi użytkownicy — pulpity nawigacyjne](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* Widok użytkowników oparty na liczbie posiadanych raportów
  
    ![Najaktywniejsi użytkownicy — raporty](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

Druga sekcja wyświetla informacje tego samego typu, ale w oparciu o grupy. Dzięki temu możesz zobaczyć, które grupy w organizacji są najaktywniejsze i z jakiej zawartości korzystają.

Przy użyciu tych informacji można uzyskiwać faktyczny wgląd w to, jak użytkownicy korzystają z usługi Power BI w organizacji, a także rozpoznawać w organizacji użytkowników i grupy charakteryzujące się dużą aktywnością.

## <a name="users"></a>Użytkownicy

Do zarządzania użytkownikami, grupami i administratorami usługi Power BI służy centrum administracyjne usługi Office 365. Karta **Użytkownicy** zawiera link do centrum administracyjnego dla dzierżawy.

![Przejdź do Centrum administracyjnego usługi O365](media/service-admin-portal/powerbi-admin-manage-users.png)

## <a name="audit-logs"></a>Dzienniki inspekcji

Do zarządzania dziennikami inspekcji usługi Power BI służy centrum zabezpieczeń i zgodności usługi Office 365. Karta **Dzienniki inspekcji**  zawiera link do centrum zabezpieczeń i zgodności dla dzierżawy. [Dowiedz się więcej](service-admin-auditing.md)

Aby korzystać z dzienników inspekcji, upewnij się, że ustawienie [**Twórz dzienniki inspekcji na potrzeby wewnętrznych inspekcji działań i sprawdzania zgodności**](#create-audit-logs-for-internal-activity-auditing-and-compliance) zostało włączone.

## <a name="tenant-settings"></a>Ustawienia dzierżawy

Karta **Ustawienia dzierżawy** umożliwia szczegółowe kontrolowanie funkcji udostępnionych w organizacji. Jeśli masz obawy związane z poufnymi danymi, niektóre z funkcji mogą nie być odpowiednie dla Twojej organizacji. Możesz też zdecydować, że określona funkcja będzie dostępna tylko dla wybranej grupy.

Na poniższej ilustracji przedstawiono dwie pierwsze sekcje karty **Ustawienia dzierżawy**.

![Ustawienia dzierżawy](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> Zastosowanie zmiany ustawienia dla wszystkich użytkowników w dzierżawie może zająć do 10 minut.

Ustawienia mogą mieć trzy stany:

* **Wyłączone dla całej organizacji**: Nikt w Twojej organizacji nie może używać tej funkcji.

    ![Ustawienie oznaczające wyłączenie dla wszystkich](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

* **Włączone dla całej organizacji**: Każdy w Twojej organizacji może używać tej funkcji.

    ![Ustawienie oznaczające włączenie dla wszystkich](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

* **Włączone dla podzbioru organizacji**: Określony podzestaw użytkowników lub grup w organizacji może używać tej funkcji.

    Funkcję możesz włączyć dla całej organizacji poza wybraną grupą użytkowników.

    ![Ustawienie oznaczające włączenie dla podzestawu](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

    Ponadto możesz włączyć funkcję tylko dla wybranej grupy użytkowników, jednocześnie wyłączając ją dla innej grupy użytkowników. Dzięki zastosowaniu takiego podejścia upewnisz się, że wybrani użytkownicy nie będą mieć dostępu do funkcji, nawet kiedy znajdą się w grupie dozwolonych użytkowników.

    ![Ustawienie oznaczające włączenie z wyjątkami](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

W kilku kolejnych sekcjach omówiono różne typy ustawień dzierżawy.

## <a name="workspace-settings"></a>Ustawienia obszaru roboczego

### <a name="create-workspaces-preview"></a>Tworzenie obszarów roboczych (wersja zapoznawcza)

Użytkownicy w organizacji mogą tworzyć obszary robocze aplikacji, aby współpracować nad pulpitami nawigacyjnymi, raportami i inną zawartością. [Dowiedz się więcej](service-create-the-new-workspaces.md)

## <a name="export-and-sharing-settings"></a>Ustawienia eksportowania i udostępniania

### <a name="share-content-to-external-users"></a>Udostępnianie zawartości użytkownikom zewnętrznym

Użytkownicy w organizacji mogą udostępniać pulpity nawigacyjne użytkownikom spoza organizacji. [Dowiedz się więcej](service-share-dashboards.md#share-a-dashboard-or-report-with-people-outside-your-organization)

![Ustawienie Zewnętrzni użytkownicy](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

Na poniższej ilustracji przedstawiono komunikat, który jest wyświetlany w przypadku udostępniania użytkownikowi zewnętrznemu.

![Udostępnianie użytkownikowi zewnętrznemu](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Publikuj w sieci Web

Użytkownicy w organizacji mogą publikować raporty w Internecie. [Dowiedz się więcej](service-publish-to-web.md)

Na poniższej ilustracji przedstawiono menu **Plik** raportu po włączeniu ustawienia **Publikuj w Internecie**.

![Ustawienie Publikuj w Internecie](media/service-admin-portal/powerbi-admin-publish-to-web.png)

Użytkownicy widzą różne opcje w interfejsie użytkownika w zależności od tego, jakie jest ustawienie **Publikuj w Internecie**.

|Promowanie |Włączone dla całej organizacji |Wyłączone dla całej organizacji |Określone grupy zabezpieczeń   |
|---------|---------|---------|---------|
|Opcja **Publikuj w sieci Web** w menu **Plik** raportu.|Włączone dla wszystkich|Nie jest widoczne dla wszystkich|Widoczne tylko dla autoryzowanych użytkowników lub grup.|
|Opcja **Zarządzaj kodami osadzania** w obszarze **Ustawienia**|Włączone dla wszystkich|Włączone dla wszystkich|Włączone dla wszystkich<br><br>Opcja * **Usuń** tylko dla autoryzowanych użytkowników lub grup.<br>Opcja * **Uzyskaj kody** włączona dla wszystkich.|
|**Kody osadzania** w portalu administracyjnym|Stan odzwierciedla jedną z następujących sytuacji:<br>* Aktywne<br>* Nieobsługiwane<br>* Zablokowane|Wyświetlany stan to **Wyłączone**|Stan odzwierciedla jedną z następujących sytuacji:<br>* Aktywne<br>* Nieobsługiwane<br>* Zablokowane<br><br>Jeśli zgodnie z ustawieniami dzierżawy użytkownik nie ma autoryzacji, jest wyświetlany stan **Naruszenie**.|
|Istniejące opublikowane raporty|Wszystko włączone|Wszystko wyłączone|Raporty w dalszym ciągu są renderowane dla wszystkich.|

### <a name="export-data"></a>Eksportuj dane

Użytkownicy w organizacji mogą eksportować dane z kafelka lub wizualizacji. [Dowiedz się więcej](visuals/power-bi-visualization-export-data.md)

Na poniższej ilustracji przedstawiono opcję eksportowania danych z kafelka.

![Eksportowanie danych z kafelka](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> Wyłączenie funkcji **Eksportowanie danych** ponadto uniemożliwia użytkownikom korzystanie z funkcji **Analizuj w programie Excel** oraz połączenia na żywo usługi Power BI.

### <a name="export-reports-as-powerpoint-presentations"></a>Eksportuj raporty jako prezentacje programu PowerPoint

Użytkownicy w organizacji mogą eksportować raporty usługi Power BI jako pliki programu PowerPoint. [Dowiedz się więcej](consumer/end-user-powerpoint.md)

Na poniższej ilustracji przedstawiono menu **Plik** raportu po włączeniu ustawienia **Eksportuj raporty jako prezentacje programu PowerPoint**.

![Eksportuj raporty jako prezentacje programu PowerPoint](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Drukuj pulpity nawigacyjne i raporty

Użytkownicy w organizacji mogą drukować pulpity nawigacyjne i raporty. [Dowiedz się więcej](consumer/end-user-print.md)

Na poniższej ilustracji przedstawiono opcję drukowania pulpitu nawigacyjnego.

![Drukuj pulpit nawigacyjny](media/service-admin-portal/powerbi-admin-print-dashboard.png)

Na poniższej ilustracji przedstawiono menu **Plik** raportu po włączeniu ustawienia **Drukuj pulpity nawigacyjne i raporty**.

![Drukowanie raportu](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-and-app-settings"></a>Ustawienia pakietu zawartości i aplikacji

### <a name="publish-content-packs-and-apps-to-the-entire-organization"></a>Publikowanie pakietów zawartości i aplikacji dla całej organizacji

Użytkownicy w organizacji mogą publikować pakiety zawartości i aplikacje dla całej organizacji, zamiast tylko dla określonych grup. [Dowiedz się więcej](service-organizational-content-pack-manage-update-delete.md)

Na poniższej ilustracji przedstawiono opcję **Cała moja organizacja** dostępną podczas tworzenia pakietu zawartości.

![Publikowanie pakietu zawartości do organizacji](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs-and-apps"></a>Tworzenie aplikacji i pakietów zawartości organizacji w formie szablonów

Użytkownicy w organizacji mogą tworzyć szablony pakietów zawartości, które używają zestawów danych wbudowanych w programie Power BI Desktop. [Dowiedz się więcej](template-content-pack-authoring.md)

### <a name="push-apps-to-end-users"></a>Wypychanie aplikacji do użytkowników końcowych

Użytkownicy mogą bezpośrednio udostępniać aplikacje użytkownikom końcowym bez konieczności instalacji z usługi AppSource. [Dowiedz się więcej](service-create-distribute-apps.md)

## <a name="integration-settings"></a>Ustawienia integracji

### <a name="ask-questions-about-data-using-cortana"></a>Zadawanie pytań o dane przy użyciu Cortany

Użytkownicy w organizacji mogą zadawać pytania dotyczące danych przy użyciu Cortany. [Dowiedz się więcej](service-cortana-enable.md)

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do określonych grup.

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Używanie funkcji Analizuj w programie Excel z lokalnymi zestawami danych

Użytkownicy w organizacji mogą używać programu Excel, aby wyświetlać lokalne zestawy danych usługi Power BI i wchodzić z nimi w interakcje. [Dowiedz się więcej](service-analyze-in-excel.md)

> [!NOTE]
> Wyłączenie funkcji **Eksportowanie danych** również uniemożliwia użytkownikom korzystanie z funkcji **Analizuj w programie Excel**.

### <a name="use-arcgis-maps-for-power-bi"></a>Używanie wizualizacji ArcGIS Maps for Power BI

Użytkownicy w organizacji mogą używać wizualizacji ArcGIS Maps for Power BI oferowanej przez firmę Esri. [Dowiedz się więcej](power-bi-visualization-arcgis.md)

### <a name="use-global-search-for-power-bi-preview"></a>Używanie wyszukiwania globalnego dla usługi Power BI (wersja zapoznawcza)

Użytkownicy w organizacji mogą używać zewnętrznych funkcji wyszukiwania, które korzystają z usługi Azure Search. Na przykład użytkownicy mogą korzystać z Cortany, aby pobierać kluczowe informacje bezpośrednio z pulpitów nawigacyjnych i raportów usługi Power BI. [Dowiedz się więcej](service-cortana-intro.md)

## <a name="custom-visuals-settings"></a>Ustawienia wizualizacji niestandardowych

### <a name="enable-custom-visuals-for-the-entire-organization"></a>Umożliwiają włączenie niestandardowych elementów wizualnych w całej organizacji

Użytkownicy w organizacji mogą interaktywnie współpracować przy użyciu niestandardowych elementów wizualnych oraz je udostępniać. [Dowiedz się więcej](power-bi-custom-visuals.md)

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do określonych grup.

## <a name="r-visuals-settings"></a>Ustawienia elementów wizualnych języka R

### <a name="interact-with-and-share-r-visuals"></a>Korzystaj z wizualizacji języka R i udostępniaj je

Użytkownicy w organizacji mogą wchodzić w interakcje z elementami wizualnymi utworzonymi przy użyciu skryptów języka R oraz je udostępniać. [Dowiedz się więcej](visuals/service-r-visuals.md)

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do określonych grup.

## <a name="audit-and-usage-settings"></a>Ustawienia inspekcji i użycia

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>Twórz dzienniki inspekcji na potrzeby wewnętrznych inspekcji działań i sprawdzania zgodności

Użytkownicy w organizacji mogą używać inspekcji, aby monitorować działania podejmowane w usłudze Power BI przez innych użytkowników w organizacji. [Dowiedz się więcej](service-admin-auditing.md)

To ustawienie musi zostać włączone, aby można było rejestrować wpisy dziennika inspekcji. Od momentu włączenia inspekcji do czasu, kiedy możliwe będzie wyświetlenie danych inspekcji, może wystąpić opóźnienie do 48 godzin. Jeśli dane nie są natychmiast widoczne, sprawdź dzienniki inspekcji później. Podobne opóźnienie może występować między uzyskaniem uprawnień do wyświetlania dzienników inspekcji a możliwością uzyskania do nich dostępu.

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do określonych grup.

### <a name="usage-metrics-for-content-creators"></a>Metryki użycia dla twórców zawartości

Użytkownicy w organizacji widzą metryki użycia dla tworzonych przez siebie pulpitów nawigacyjnych i raportów. [Dowiedz się więcej](service-usage-metrics.md)

### <a name="per-user-data-in-usage-metrics-for-content-creators"></a>Dane dotyczące poszczególnych użytkowników w metrykach użycia dla twórców zawartości

Metryki użycia dla twórców zawartości będą ujawniać nazwy wyświetlane i adresy e-mail użytkowników, którzy uzyskują dostęp do zawartości. [Dowiedz się więcej](service-usage-metrics.md)

Domyślnie dane poszczególnych użytkowników są włączone dla metryk użycia, a informacje o koncie twórcy zawartości są uwzględniane w raporcie metryk. Jeśli nie chcesz uwzględnić tych informacji dla niektórych lub wszystkich użytkowników, wyłączyć funkcję dla określonych grup zabezpieczeń lub całej organizacji. Informacje o koncie będą wyświetlane w raporcie jako *Bez nazwy*.

## <a name="dashboard-settings"></a>Ustawienia pulpitu nawigacyjnego

### <a name="data-classification-for-dashboards"></a>Klasyfikacja danych dla pulpitów nawigacyjnych

Użytkownicy w organizacji mogą tagować pulpity nawigacyjne przy użyciu klasyfikacji, które wskazują poziomy zabezpieczeń pulpitów nawigacyjnych. [Dowiedz się więcej](service-data-classification.md)

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do określonych grup.

## <a name="developer-settings"></a>Ustawienia dewelopera

### <a name="embed-content-in-apps"></a>Osadzanie zawartości w aplikacjach

Użytkownicy w organizacji mogą osadzać pulpity nawigacyjne i raporty usługi Power BI w aplikacjach oprogramowania jako usługi (SaaS). Wyłączenie tego ustawienia sprawia, że użytkownicy nie mogą używać interfejsów API REST do osadzania zawartości usługi Power BI w swoich aplikacjach. [Dowiedz się więcej](developer/embedding.md)

## <a name="workspaces-and-import-settings"></a>Ustawienia obszarów roboczych i importowania

### <a name="author-content-in-workspaces"></a>Tworzenie treści w obszarach roboczych

Użytkownicy w organizacji mogą uzyskiwać dostęp do obszarów roboczych, aby łączyć się z danymi i tworzyć zawartość. [Dowiedz się więcej](service-create-the-new-workspaces.md)

### <a name="import-data-into-power-bi"></a>Importowanie danych do usługi Power BI

Użytkownicy w organizacji mogą importować dane do usługi, na przykład publikując raporty z programu Power BI Desktop, przekazując pliki raportów usługi Power BI i łącząc się z danymi bezpośrednio z usługi. [Dowiedz się więcej](desktop-upload-desktop-files.md)

## <a name="dataflow-settings-preview"></a>Ustawienia przepływu danych (wersja zapoznawcza)

### <a name="create-and-use-dataflows-preview"></a>Tworzenie i używanie przepływów danych (wersja zapoznawcza)

Użytkownicy w organizacji mogą tworzyć przepływy danych i ich używać. Aby zapoznać się z omówieniem przepływów danych, zobacz [Przygotowywanie danych samoobsługi w usłudze Power BI (wersja zapoznawcza)](service-dataflows-overview.md). Aby włączyć przepływy danych w pojemności Premium, zobacz [Konfigurowanie obciążeń](service-admin-premium-manage.md#configure-workloads).

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do określonych grup.

## <a name="capacity-settings"></a>Ustawienia pojemności

### <a name="power-bi-premium"></a>Power BI Premium

Karta **Power BI Premium** umożliwia zarządzanie dowolnymi pojemnościami usługi Power BI Premium (jednostki SKU EM lub P) zakupionymi przez organizację. Wszyscy użytkownicy w organizacji widzą kartę **Power BI Premium**, ale zobaczą zawartość na karcie tylko wtedy, jeśli przypisano im rolę *administratora pojemności* lub użytkownika z uprawnieniami do przypisywania. Jeśli użytkownik nie ma żadnych uprawnień, jest wyświetlany poniższy komunikat.

![Brak dostępu do ustawień wersji Premium](media/service-admin-portal/premium-settings-no-access.png)

Aby uzyskać więcej informacji o sposobach zarządzania ustawieniami wersji Premium, zobacz [Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md).

### <a name="power-bi-embedded"></a>Power BI Embedded

Karta **Power BI Embedded** służy do wyświetlania pojemności usługi Power BI Embedded (jednostka SKU A) zakupionych dla klienta. Ponieważ jednostki SKU A można kupić tylko na platformie Azure, [zarządzasz osadzonymi pojemnościami na platformie Azure](developer/azure-pbie-create-capacity.md) z poziomu witryny **Azure Portal**.

Aby uzyskać więcej informacji na temat zarządzania ustawieniami usługi Power BI Embedded (SKU A), zobacz [Co to jest usługa Power BI Embedded](developer/azure-pbie-what-is-power-bi-embedded.md).

## <a name="embed-codes"></a>Kody osadzania

Jako administrator możesz wyświetlać kody osadzania, które są generowane dla dzierżawy. Możesz również wycofywać lub usuwać kody. [Dowiedz się więcej](service-publish-to-web.md)

![Kody osadzania w portalu administracyjnym usługi Power BI](media/service-admin-portal/embed-codes.png)

## <a name="organization-visuals"></a>Wizualizacje organizacji

Karta **Wizualizacje organizacji** umożliwia wdrażanie wizualizacji niestandardowych i zarządzanie nimi wewnątrz organizacji. Dzięki wizualizacjom organizacji można łatwo wdrażać własne wizualizacje w organizacji. Autorzy raportów mogą je następnie odnajdywać i importować do swoich raportów z poziomu programu Power BI Desktop. [Dowiedz się więcej](power-bi-custom-visuals-organization.md)

> [!WARNING]
> Wizualizacja niestandardowa może zawierać kod zagrażający bezpieczeństwu lub prywatności. Przed jej wdrożeniem w repozytorium organizacji upewnij się, że autor i źródło wizualizacji niestandardowej należą do zaufanych.

Na poniższej ilustracji znajdują się wszystkie wizualizacje niestandardowe, które zostały aktualnie wdrożone w repozytorium organizacji.

![Wizualizacja administratora organizacji](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>Dodawanie nowej wizualizacji niestandardowej

Aby dodać nową wizualizację niestandardową do listy, wykonaj poniższe kroki. 

1. W okienku po prawej stronie wybierz pozycję **Dodaj wizualizację niestandardową**.

    ![Formularz wizualizacji niestandardowych](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

1. Wypełnij formularz **Dodawanie wizualizacji niestandardowej**:

    * **Wybierz plik pbiviz** (wymagane): wybierz plik wizualizacji niestandardowej do przekazania. Obsługiwane są tylko wersjonowane niestandardowe wizualizacje interfejsu API (przeczytaj tutaj, co to oznacza).

    Przed przekazaniem wizualizacji niestandardowej należy ją sprawdzić pod kątem zabezpieczeń i prywatności, aby zapewnić jej zgodność ze standardami organizacji.

    * **Nazwij swoją wizualizację niestandardową** (wymagane): nadaj wizualizacji krótki tytuł, by użytkownicy programu Power BI Desktop mogli łatwo poznać jej zastosowanie.

    * **Ikona**: plik ikony wyświetlany w interfejsie użytkownika programu Power BI Desktop.

    * **Opis**: krótki opis wizualizacji zapewniający użytkownikowi więcej informacji i kontekst.

1. Wybierz pozycję **Dodaj**, aby zainicjować żądanie przekazania. Jeśli operacja zostanie wykonana pomyślnie, na liście pojawia się nowy element. Jeśli operacja zakończy się niepowodzeniem, jest wyświetlany odpowiedni komunikat o błędzie.

### <a name="delete-a-custom-visual-from-the-list"></a>Usuwanie wizualizacji niestandardowej z listy

Aby trwale usunąć wizualizację, wybierz ikonę kosza dla wizualizacji w repozytorium.

> [!IMPORTANT]
> Usunięcie jest nieodwracalne. Usunięcie wizualizacji powoduje natychmiastowe zakończenie renderowania w istniejących raportach. Nawet jeśli wizualizacja zostanie przekazana ponownie, nie zastąpi ona poprzedniej, już usuniętej wizualizacji. Użytkownicy mogą jednak ponownie zaimportować nową wizualizację i zastąpić wystąpienie w swoich raportach.

### <a name="disable-a-custom-visual-in-the-list"></a>Wyłączanie wizualizacji niestandardowej na liście

Aby wyłączyć wizualizację z magazynu organizacyjnego, wybierz ikonę koła zębatego. W sekcji **Dostęp** wyłącz wizualizację niestandardową.

Wyłączona wizualizacja nie będzie renderowana w istniejących raportach i spowoduje wyświetlenie poniższego komunikatu o błędzie.

*Ta wizualizacja niestandardowa jest już niedostępna. Aby uzyskać więcej informacji, skontaktuj się z administratorem.*

Wizualizacje oznaczone zakładkami będą jednak nadal działać.

Po każdej aktualizacji lub zmianie wprowadzonej przez administratora użytkownicy usługi Power BI Desktop powinni ponownie uruchomić aplikację lub odświeżyć przeglądarkę w usłudze Power BI, aby zobaczyć aktualizacje.

### <a name="update-a-visual"></a>Aktualizowanie wizualizacji

Aby zaktualizować wizualizację z poziomu magazynu organizacyjnego, wybierz ikonę koła zębatego. Przejdź do nowej wersji wizualizacji i przekaż ją.

Upewnij się, że identyfikator wizualizacji pozostał niezmieniony. Nowy plik zastępuje jego poprzednią wersję dla wszystkich raportów w całej organizacji. Jednak jeśli nowa wersja wizualizacji może uniemożliwić użycie wcześniejszej wersji wizualizacji lub zaburzyć jej strukturę danych, nie zastępuj poprzedniej wersji. Zamiast tego utwórz nową listę z nową wersją wizualizacji. Na przykład dodaj numer nowej wersji (wersja X.X) do tytułu umieszczonej na liście nowej wizualizacji. Dzięki temu wyraźnie widać, że jest to ta sama wizualizacja ze zaktualizowanym numerem wersji, dlatego funkcjonalność istniejących raportów nie zostaje zakłócona. I tym razem upewnij się, że identyfikator wizualizacji pozostał niezmieniony. Następnym razem, gdy użytkownicy przejdą do repozytorium organizacji z programu Power BI Desktop, mogą zaimportować nową wersję, co powoduje wyświetlenie monitu o zastąpienie bieżącej wersji zawartej w raporcie.

Aby uzyskać więcej informacji, odwiedź stronę [często zadawanych pytań dotyczących wizualizacji niestandardowych organizacji](https://docs.microsoft.com/en-us/power-bi/power-bi-custom-visuals-faq#organizational-custom-visuals)

## <a name="dataflow-storage-preview"></a>Magazyn przepływów danych (wersja zapoznawcza)

Domyślnie dane używane z usługą Power BI są przechowywane w magazynie wewnętrznym oferowanym przez usługę Power BI. Dzięki integracji przepływów danych i usługi Azure Data Lake Storage Gen2 (ADLS Gen2) można przechowywać swoje przepływy danych na koncie usługi Azure Data Lake Storage Gen2 organizacji. Aby uzyskać więcej informacji, zobacz [Integracja przepływów danych z usługą Azure Data Lake (wersja zapoznawcza)](service-dataflows-azure-data-lake-integration.md).

## <a name="workspaces-preview"></a>Obszary robocze (wersja zapoznawcza)

Jako administrator możesz wyświetlać obszary robocze, które istnieją w Twojej dzierżawie. Listę obszarów roboczych można sortować i filtrować. Można również wyświetlać szczegóły poszczególnych obszarów roboczych. Należy zwrócić uwagę, że kolumny tabeli odpowiadają właściwościom zwracanym przez [interfejs API REST administratora usługi Power BI](/rest/api/power-bi/admin) dla obszarów roboczych. Osobiste obszary robocze są typu **PersonalGroup**, starsze obszary robocze są typu **Group**, a nowoczesne obszary robocze są typu **Workspace**. Aby uzyskać więcej informacji, zobacz [Tworzenie nowych obszarów roboczych (wersja zapoznawcza) w usłudze Power BI](service-create-the-new-workspaces.md).

![Lista obszarów roboczych](media/service-admin-portal/workspaces-list.png)

## <a name="next-steps"></a>Następne kroki

[Administrowanie usługą Power BI w organizacji](service-admin-administering-power-bi-in-your-organization.md) [Opis roli administratora usługi Power BI](service-admin-role.md)  
[Inspekcja usługi Power BI w organizacji](service-admin-auditing.md)  
[Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)
