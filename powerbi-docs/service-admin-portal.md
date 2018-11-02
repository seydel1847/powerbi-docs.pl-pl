---
title: Portal administracyjny usługi Power BI
description: Portal administracyjny umożliwia zarządzanie dzierżawą usługi Power BI w organizacji. Zawiera on kluczowe elementy, takie jak metryki użycia, dostęp do centrum administracyjnego usługi Office 365 oraz ustawienia.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/30/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 02829adb386cc746715a34300a42aba616dc2d60
ms.sourcegitcommit: 862faf948468d7f6d464b83f4e0b040d5213a580
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2018
ms.locfileid: "50252496"
---
# <a name="power-bi-admin-portal"></a>Portal administracyjny usługi Power BI

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

## <a name="tenant-settings"></a>Ustawienia dzierżawy

Karta **Ustawienia dzierżawy** umożliwia szczegółowe kontrolowanie funkcji udostępnionych w organizacji. Jeśli masz obawy związane z poufnymi danymi, niektóre z funkcji mogą nie być odpowiednie dla Twojej organizacji. Możesz też zdecydować, że określona funkcja będzie dostępna tylko dla wybranej grupy.

Na poniższej ilustracji przedstawiono dwie pierwsze sekcje karty **Ustawienia dzierżawy**.

![Ustawienia dzierżawy](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> Zastosowanie zmiany ustawienia dla wszystkich użytkowników w dzierżawie może zająć do 10 minut.

Ustawienia mogą mieć trzy stany:

* **Wyłączone w całej organizacji**: nikt w organizacji nie może używać tej funkcji.

    ![Ustawienie oznaczające wyłączenie dla wszystkich](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

* **Włączone w całej organizacji**: wszyscy w organizacji mogą używać tej funkcji.

    ![Ustawienie oznaczające włączenie dla wszystkich](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

* **Włączone w podzestawie organizacji**: określony podzestaw użytkowników lub grup w organizacji może używać tej funkcji.

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

Użytkownicy w organizacji mogą udostępniać pulpity nawigacyjne użytkownikom spoza organizacji.

![Ustawienie Zewnętrzni użytkownicy](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

Na poniższej ilustracji przedstawiono komunikat, który jest wyświetlany w przypadku udostępniania użytkownikowi zewnętrznemu.

![Udostępnianie użytkownikowi zewnętrznemu](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Publikuj w Internecie

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

![](media/service-admin-portal/powerbi-admin-print-dashboard.png)

![](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-settings"></a>Ustawienia pakietu zawartości

### <a name="publish-content-packs-to-the-entire-organization"></a>Publikowanie pakietów zawartości w całej organizacji

Użytkownicy w organizacji mogą publikować pakiety zawartości w całej organizacji.

![](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs"></a>Tworzenie szablonów pakietów zawartości w organizacji

Użytkownicy w organizacji mogą tworzyć szablony pakietów zawartości, które używają zestawów danych wbudowanych w jednym źródle danych w aplikacji Power BI Desktop.

### <a name="push-apps-to-end-users"></a>Wypychanie aplikacji do użytkowników końcowych

Administrator dzierżawy umożliwia wypychanie aplikacji w **ustawieniach dzierżawy**.

   ![Włączanie wypychania aplikacji](media/service-create-distribute-apps/power-bi-apps-pushapps01.png)

Możesz zmienić ustawienie na **Włączone**, a następnie określić, kto dysponuje tą możliwością (cała organizacja lub konkretne grupy zabezpieczeń).

> [!NOTE]
> Należy pamiętać o tym, że uwzględnienie zmian ustawień dzierżawy może zabrać trochę czasu.

Przejdź tutaj, aby dowiedzieć się więcej o [wypychaniu aplikacji](service-create-distribute-apps.md).

## <a name="integration-settings"></a>Ustawienia integracji

### <a name="ask-questions-about-data-using-cortana"></a>Zadawanie pytań o dane przy użyciu Cortany

Użytkownicy w organizacji mogą zadawać pytania dotyczące danych przy użyciu Cortany.

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

To ustawienie musi być włączone, aby można było rejestrować wpisy dziennika inspekcji. Od momentu włączenia inspekcji do czasu, kiedy możliwe będzie wyświetlenie danych inspekcji, może wystąpić opóźnienie do 48 godzin. Jeśli dane nie są natychmiast widoczne, sprawdź dzienniki inspekcji później. Podobne opóźnienie może występować między uzyskaniem uprawnień do wyświetlania dzienników inspekcji a możliwością uzyskania do nich dostępu.

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do określonych grup.

### <a name="usage-metrics-for-content-creators"></a>Metryki użycia dla twórców zawartości
Użytkownicy w organizacji widzą metryki użycia dla utworzonych przez siebie pulpitów nawigacyjnych i raportów. [Dowiedz się więcej](service-usage-metrics.md).

Ustawienie możesz zmienić na **Włączone**, a następnie określić, kto może wyświetlać metryki użycia (cała organizacja lub konkretne grupy zabezpieczeń).

> [!NOTE]
> Należy pamiętać o tym, że uwzględnienie zmian ustawień dzierżawy może zabrać trochę czasu.

### <a name="per-user-data-in-usage-metrics-for-content-creators"></a>Dane dotyczące poszczególnych użytkowników w metrykach użycia dla twórców zawartości
Metryki użycia dla twórców zawartości będą ujawniać nazwy wyświetlane i adresy e-mail użytkowników, którzy uzyskują dostęp do zawartości. [Dowiedz się więcej](service-usage-metrics.md).

Ustawienie możesz zmienić na **Włączone**, a następnie określić, kto może wyświetlać nazwy wyświetlane i adresy e-mail w metrykach użycia (cała organizacja lub konkretne grupy zabezpieczeń).

Domyślnie dane poszczególnych użytkowników są włączone dla metryk użycia, a informacje o koncie twórcy zawartości są uwzględniane w raporcie metryk. Jeśli nie chcesz uwzględnić tych informacji dla niektórych lub wszystkich użytkowników, wyłączyć funkcję dla określonych grup zabezpieczeń lub całej organizacji. Informacje o koncie będą wyświetlane w raporcie jako *Bez nazwy*.

> [!NOTE]
> Należy pamiętać o tym, że uwzględnienie zmian ustawień dzierżawy może zabrać trochę czasu.


## <a name="dashboard-settings"></a>Ustawienia pulpitu nawigacyjnego

### <a name="data-classification-for-dashboards"></a>Klasyfikacja danych dla pulpitów nawigacyjnych

Użytkownicy w organizacji mogą tagować pulpity nawigacyjne przy użyciu klasyfikacji, aby wskazywać poziomy zabezpieczeń pulpitów nawigacyjnych. [Dowiedz się więcej](service-data-classification.md)

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do określonych grup.

## <a name="developer-settings"></a>Ustawienia dewelopera

### <a name="embed-content-in-apps"></a>Osadzanie zawartości w aplikacjach

Użytkownicy w organizacji mogą osadzać pulpity nawigacyjne i raporty usługi Power BI w aplikacjach oprogramowania jako usługi (SaaS). Wyłączenie tego ustawienia sprawia, że użytkownicy nie mogą używać interfejsów API REST do osadzania zawartości usługi Power BI w swoich aplikacjach.

## <a name="capacity-settings"></a>Ustawienia pojemności

### <a name="premium-settings"></a>Ustawienia — wersja Premium

Karta Ustawienia — wersja Premium umożliwia zarządzanie dowolną pojemnością usługi Power BI Premium (Em lub SKU P) zakupioną przez organizację. Wszyscy użytkownicy w organizacji widzą kartę ustawień wersji Premium, ale zobaczą zawartość na karcie tylko wtedy, jeśli przydzielono im rolę **administratora pojemności** lub użytkownika z uprawnieniami do przypisywania. Jeśli użytkownik nie ma żadnych uprawnień, jest wyświetlany poniższy komunikat.

![Ustawienia administratora usługi Power BI Premium](media/service-admin-portal/premium-settings-no-access.png "Brak dostępu do ustawień wersji Premium")

Aby uzyskać więcej informacji o sposobach zarządzania ustawieniami wersji Premium, zobacz [Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md).

### <a name="power-bi-embedded-settings"></a>Ustawienia usługi Power BI Embedded

Karta ustawień usługi Power BI Embedded służy do wyświetlania pojemności usługi Power BI Embedded (SKU A) zakupionych dla klienta. Ponieważ jednostki SKU A można kupić tylko na platformie Azure, możesz [zarządzać osadzonymi pojemnościami na platformie Azure](developer/azure-pbie-create-capacity.md) z poziomu witryny **Azure Portal**.

![Ustawienia administratora usługi Power BI Embedded](media/service-admin-portal/manage-pbie-capacities-01.png)

![Szczegółowe ustawienia administratora usługi Power BI Embedded](media/service-admin-portal/manage-pbie-capacities-02.png)

Aby uzyskać więcej informacji na temat zarządzania ustawieniami usługi Power BI Embedded (SKU A), zobacz [Co to jest usługa Power BI Embedded](developer/azure-pbie-what-is-power-bi-embedded.md).

## <a name="embed-codes"></a>Kody osadzania

![Kody osadzania w portalu administracyjnym usługi Power BI](media/service-admin-portal/embed-codes.png)

Jako administrator możesz wyświetlać kody osadzania, które są generowane dla dzierżawy. Do dyspozycji masz akcje wyświetlenia raportu i usunięcia kodu osadzania w celu odwołania go.

## <a name="organization-visuals"></a>Wizualizacje organizacji

Karta wizualizacji organizacji umożliwia wdrażanie niestandardowych wizualizacji oraz zarządzanie nimi w ramach organizacji. Pozwala łatwo implementować własne wizualizacje niestandardowe w organizacji, tak aby autorzy raportów mogli je w prosty sposób odnajdować i importować bezpośrednio z programu Power BI Desktop do swoich raportów.

Na stronie znajdują się wszystkie wizualizacje niestandardowe, które są aktualnie zaimplementowane w repozytorium organizacji.

![Wizualizacja administratora organizacji](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>Dodawanie nowej wizualizacji niestandardowej

Aby dodać nową wizualizację niestandardową do listy, wybierz pozycję **Importuj niestandardową wizualizację**.

![](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

> [!WARNING]
> Wizualizacja niestandardowa może zawierać kod zagrażający bezpieczeństwu lub prywatności. Przed jej wdrożeniem w repozytorium pochodzenia upewnij się, że autor i źródło wizualizacji niestandardowej należą do zaufanych.

Wypełnij pola:

* Wybierz plik pbiviz (wymagane): wybierz plik wizualizacji niestandardowej do przekazania. Obsługiwane są tylko wersjonowane niestandardowe wizualizacje interfejsu API (przeczytaj tutaj, co to oznacza).

Przed przekazaniem wizualizacji niestandardowej należy ją sprawdzić pod kątem zabezpieczeń i prywatności, aby zapewnić jej zgodność ze standardami organizacji. Przeczytaj więcej o zabezpieczeniach wizualizacji niestandardowych.

* Nazwij swoją wizualizację niestandardową (wymagane): nadaj wizualizacji krótki tytuł, by użytkownicy programu Power BI Desktop mogli łatwo poznać jej zastosowanie

* Ikona (wymagane): plik ikony wyświetlany w interfejsie użytkownika programu Power BI Desktop.

* Opis: krótki opis wizualizacji zapewniający użytkownikowi więcej informacji i kontekst

Wybierz opcję „Zastosuj”, aby zainicjować żądanie przekazania. Jeśli operacja zostanie wykonana pomyślnie, na liście pojawia się nowy element. Jeśli operacja zakończy się niepowodzeniem, jest wyświetlany odpowiedni komunikat o błędzie.

### <a name="delete-a-custom-visual-from-the-list"></a>Usuwanie wizualizacji niestandardowej z listy

Wybierz ikonę kosza, aby trwale usunąć wizualizację z repozytorium.
Ważne: usunięcie elementu jest nieodwracalne. Usunięcie wizualizacji powoduje natychmiastowe zakończenie renderowania w istniejących raportach. Nawet w przypadku ponownego przekazania tej samej wizualizacji nie zastąpi ona poprzedniej, która została usunięta. Użytkownicy mogą ponownie zaimportować nową wizualizację i zastąpić wystąpienie w raportach.

### <a name="disable-a-custom-visual-in-the-list"></a>Wyłączanie wizualizacji niestandardowej na liście

Aby wyłączyć wizualizację z magazynu organizacyjnego, wybierz ikonę koła zębatego. W sekcji **Dostęp** wyłącz wizualizację niestandardową.

Wyłączona wizualizacja nie będzie renderowana w istniejących raportach i spowoduje wyświetlenie poniższego komunikatu o błędzie.

*Ta wizualizacja niestandardowa jest już niedostępna. Aby uzyskać więcej informacji, skontaktuj się z administratorem.*

Wizualizacje oznaczone zakładkami będą jednak nadal działać.

Po każdej aktualizacji lub zmianie wprowadzonej przez administratora użytkownicy usługi Power BI Desktop powinni ponownie uruchomić aplikację lub odświeżyć przeglądarkę w usłudze Power BI, aby zobaczyć aktualizacje.

### <a name="how-to-update-a-visual"></a>Jak zaktualizować wizualizację

Jeśli chcesz zaktualizować wizualizację w repozytorium, ponieważ dostępna jest jej nowa wersja (np. zawierająca poprawki błędów, nowe funkcje itp.), wybierz ikonę **Aktualizuj** i przekaż nowy plik. Upewnij się, że identyfikator wizualizacji pozostał niezmieniony. Nowy plik zastępuje jego poprzednią wersję dla wszystkich raportów w całej organizacji. Jednak jeśli nowa wersja wizualizacji może uniemożliwić użycie wcześniejszej wersji wizualizacji lub zaburzyć jej strukturę danych, nie zastępuj poprzedniej wersji. Zamiast tego utwórz nową listę z nową wersją wizualizacji. Na przykład dodaj numer nowej wersji (wersja X.X) do tytułu umieszczonej na liście nowej wizualizacji. Dzięki temu wyraźnie widać, że jest to ta sama wizualizacja ze zaktualizowanym numerem wersji, dlatego funkcjonalność istniejących raportów nie zostaje zakłócona. I tym razem upewnij się, że identyfikator wizualizacji pozostał niezmieniony. Następnym razem, gdy użytkownicy przejdą do repozytorium organizacji z programu Power BI Desktop, mogą zaimportować nową wersję, co powoduje wyświetlenie monitu o zastąpienie bieżącej wersji zawartej w raporcie.

## <a name="next-steps"></a>Następne kroki

[Opis roli administratora usługi Power BI](service-admin-role.md)  
[Inspekcja usługi Power BI w organizacji](service-admin-auditing.md)  
[Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md)  
[Administrowanie usługą Power BI w organizacji](service-admin-administering-power-bi-in-your-organization.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)
