---
title: Co nowego w serwerze raportów usługi Power BI
description: Dowiedz się, co nowego w serwerze raportów usługi Power BI. Obejmuje to obszary najważniejszych funkcji i jest aktualizowane w miarę, jak są wydawane nowe elementy.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 08/16/2018
ms.openlocfilehash: a365cab0420fdf373d62f5b1774a4d86985adfe3
ms.sourcegitcommit: 60fb46b61ac73806987847d9c606993c0e14fb30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2018
ms.locfileid: "50101260"
---
# <a name="whats-new-in-power-bi-report-server"></a>Co nowego w serwerze raportów usługi Power BI

Dowiedz się, co nowego w serwerze raportów usługi Power BI. Ten artykuł obejmuje obszary najważniejszych funkcji i jest aktualizowany w miarę, jak są wydawane nowe elementy.

Aby pobrać serwer raportów usługi Power BI i program Power BI Desktop zoptymalizowany pod kątem serwera raportów usługi Power BI, przejdź do [Lokalne raportowanie za pomocą serwera raportów usługi Power BI](https://powerbi.microsoft.com/report-server/).

Sprawdź również poniższe źródła, aby uzyskać aktualne informacje o nowych funkcjach serwera raportów usługi Power BI.

* [Blog usługi Microsoft Power BI](https://powerbi.microsoft.com/blog/)
* [Blog zespołu usług SQL Server Reporting Services](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [Kanał Guy in a Cube (YouTube)](https://aka.ms/guyinacube)

Powiązane nowości w usłudze Power BI zostały opisane w następujących artykułach:

* [Co nowego w usłudze Power BI](../service-whats-new.md)
* [Co nowego w programie Power BI Desktop](../desktop-latest-update.md)
* [Co nowego w aplikacjach mobilnych dla usługi Power BI](../consumer/mobile/mobile-whats-new-in-the-mobile-apps.md)

## <a name="august-2018"></a>Sierpień 2018 r.

W sierpniu 2018 r. wprowadzono wiele nowych funkcji w wersji programu Power BI Desktop zoptymalizowanej pod kątem serwera raportów usługi Power BI. Oto one, podzielone według obszaru:

- [Raportowanie](#reporting)
- [Analiza](#analytics)
- [Modelowanie](#modeling)

### <a name="highlights-of-the-august-2018-release"></a>Najważniejsze funkcje w wersji z sierpnia 2018 r.

Spośród całej, długiej listy nowych funkcji poniższe wydają się szczególnie interesujące. Aby uzyskać więcej informacji, zobacz nasz [wpis w blogu](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/).

#### <a name="report-theming"></a>Motywy raportów

Motywy raportów zostały dodane w wersji serwera raportów usługi Power BI z sierpnia 2018 r. i umożliwiają szybką zmianę kolorów całego raportu, aby dopasować je do motywu lub znakowania firmowego. Po zaimportowaniu motywu wszystkie wykresy są automatycznie aktualizowane w celu użycia kolorów motywu, a dostęp do kolorów motywu jest możliwy z poziomu palety kolorów. Plik motywu możesz przekazać przy użyciu opcji **Importuj motyw** w ramach przycisku **Przełącz motyw**.

Plik motywu to plik w formacie JSON zawierający wszystkie kolory, których chcesz używać w raporcie oraz formatowanie domyślne, które ma być stosowane w przypadku wizualizacji.
Oto prosty przykładowy motyw JSON, który tylko aktualizuje domyślne kolory raportu:

```json
{
"name": "waveform",
"dataColors": [ "#31B6FD", "#4584D3", "#5BD078", "#A5D028", "#F5C040", "#05E0DB", "#3153FD", "#4C45D3", "#5BD0B0", "#54D028", "#D0F540", "#057BE0" ],
"background":"#FFFFFF",
"foreground": "#F2F2F2",
"tableAccent":"#5BD078"
}
```

#### <a name="conditional-formatting-by-a-different-field"></a>Formatowanie warunkowe według innego pola

Możliwość formatowania kolumny według innego pola w modelu jest jednym z istotnych ulepszeń formatowania warunkowego.

#### <a name="conditional-formatting-by-values"></a>Formatowanie warunkowe według wartości

Inny nowy typ formatowania warunkowego to **Formatowanie według wartości pola**. Formatowanie według wartości pola pozwala używać miary lub kolumny określającej kolor (za pomocą kodu szesnastkowego lub nazwy) i stosuje ten kolor jako kolor tła lub czcionki.

#### <a name="report-page-tooltips"></a>Etykietki narzędzi strony raportu

Funkcja etykietek narzędzi strony raportu została uwzględniona w aktualizacji serwera raportów usługi Power BI z sierpnia 2018 r. Ta funkcja umożliwia zaprojektowanie strony raportu, która ma być używana jako niestandardowa etykietka narzędzia w przypadku innych wizualizacji w raporcie.

#### <a name="log-axis-improvements"></a>Ulepszenia osi skali logarytmicznej

Znacznie udoskonaliliśmy oś skali logarytmicznej na wykresach w układzie kartezjańskim. Teraz powinno być możliwe wybranie skali logarytmicznej dla osi liczbowej dowolnego wykresu w układzie kartezjańskim, w tym wykresu kombi, gdy wszystkie są dodatnie lub wszystkie dane są ujemne.

#### <a name="sap-hana-sso-direct-query"></a>Tryb DirectQuery w przypadku logowania jednokrotnego na platformie SAP HANA

Obsługa trybu DirectQuery w przypadku logowania jednokrotnego na platformie SAP HANA przy użyciu protokołu Kerberos jest teraz dostępna dla raportów usługi Power BI.

>[!Note]
>Ten scenariusz jest obsługiwany tylko wtedy, gdy platforma SAP HANA jest traktowana jako relacyjne źródło danych z raportami utworzonymi w programie Power BI Desktop.  Aby włączyć tę funkcję w programie Power BI Desktop, w menu DirectQuery, w obszarze Opcje zaznacz pozycję „Traktuj platformę SAP HANA jako źródło relacyjne”, a następnie kliknij przycisk OK.

#### <a name="custom-visuals"></a>Wizualizacje niestandardowe

- Wersja interfejsu API dostarczana w tej wersji to 1.13.0.

- Teraz wizualizacje niestandardowe mogą w razie potrzeby korzystać z wcześniejszej wersji zgodnej z bieżącą wersją interfejsu API serwera (jeśli jest dostępna).

### <a name="reporting"></a>Raportowanie 

- [Motywy raportów](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#theming)
- [Przyciski do wyzwalania akcji](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#buttons)
- [Style linii wykresu kombi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLines)
- [Ulepszone domyślne sortowanie wizualizacji](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sort)
- [Fragmentator liczbowy](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#numericSlicer)
- [Zaawansowane synchronizowanie fragmentatora](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerSync)
- [Ulepszenia osi skali logarytmicznej](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#logAxis)
- [Opcje etykiet danych dla wykresu lejkowego](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#funnelChart)
- [Ustawianie szerokości pociągnięcia linii na zero](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#lineStroke)
- [Obsługa dużego kontrastu dla raportów](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#highContrast)
- [Kontrolka promienia pierścienia](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#donutRadius)
- [Kontrolka pozycji etykiet szczegółów wykresów kołowych i pierścieniowych](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#detailLabels)
- [Formatowanie etykiet danych oddzielnie dla każdej miary na wykresie kombi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLabels)
- [Nowy nagłówek wizualizacji o większej elastyczności i większych możliwościach formatowania](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#visualHeader)
- [Formatowanie tapety](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#wallpaper)
- [Etykietki narzędzi dla tabeli i macierzy](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tableTooltips)
- [Wyłączanie etykietek narzędzi w wizualizacjach](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tooltips)
- [Ułatwienia dostępu fragmentatorów](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerAccessibility)
- [Ulepszenia okienka formatowania](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#formattingPane)
- [Obsługa linii schodkowej na wykresach liniowych i kombi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#steppedLine)
- [Ulepszenia środowiska sortowania](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sorting)
- [Drukowanie raportów za pomocą funkcji eksportowania do pliku PDF (w programie Power BI Desktop)](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#print)
- [Tworzenie grup zakładek](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#bookmarks)
- [Ponowne określanie fragmentatora](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicer)
- [Etykietki narzędzi strony raportu](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#reportPageTooltips)

### <a name="analytics"></a>Analiza

- [Nowa funkcja języka DAX: COMBINEVALUES()](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#combineValues)
- [Przeglądanie szczegółowe przy użyciu miar](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#measureDrillthrough)
- [Formatowanie warunkowe według innego pola](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingField)
- [Formatowanie warunkowe według wartości](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingValue)

### <a name="modeling"></a>Modelowanie

- [Filtrowanie i sortowanie w widoku danych](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#filterAndSort)
- [Ulepszone formatowanie ustawień regionalnych](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#locale)
- [Kategorie danych dla miar](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dataCategory)
- [Statystyczne funkcje języka DAX](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dax)

## <a name="may-2018"></a>Maj 2018

### <a name="configure-power-bi-ios-mobile-apps-for-report-servers-remotely"></a>Zdalne konfigurowanie aplikacji mobilnych Power BI dla systemu iOS na potrzeby serwerów raportów

Jako administrator IT możesz teraz zdalnie konfigurować dostęp aplikacji mobilnej Power BI dla systemu iOS do serwera raportów za pomocą narzędzia do zarządzania urządzeniami przenośnymi używanego w organizacji. Szczegółowe informacje zawiera artykuł [Zdalne konfigurowanie dostępu aplikacji mobilnej Power BI dla systemu iOS do serwera raportów](configure-powerbi-mobile-apps-remote.md).

## <a name="march-2018"></a>Marzec 2018

W marcu 2018 r. wprowadzono wiele nowych funkcji w nowej wersji programu Power BI Desktop zoptymalizowanej pod kątem serwera raportów usługi Power BI. Oto one, podzielone według obszaru:

- [Wizualizacje](#visuals-updates)
- [Raportowanie](#reporting)
- [Analiza](#analytics)
- [Wydajność](#performance)
- [Serwer raportów](#report-server)
- [Inne](#other-improvements)

### <a name="highlights-of-the-march-2018-release"></a>Najważniejsze funkcje w wersji z marca 2018 r.

Spośród całej, długiej listy nowych funkcji poniższe wydają się szczególnie interesujące.

#### <a name="rule-based-conditional-formatting-for-table-and-matrixhttpspowerbimicrosoftcomblogpower-bi-desktop-november-2017-feature-summaryconditionalformatting"></a>[Oparte na regułach formatowanie warunkowe dla wizualizacji Tabela i Macierz](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)

Twórz reguły, aby warunkowo kolorować tło lub czcionkę w kolumnie w oparciu o konkretną logikę biznesową w tabeli lub macierzy.

#### <a name="show-and-hide-pageshttpspowerbimicrosoftcomblogpower-bi-desktop-january-2018-feature-summaryhidepages"></a>[Pokazywanie i ukrywanie stron](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

Chcesz, aby czytelnicy zyskali dostęp do raportu, ale niektóre strony nie są jeszcze w pełni ukończone. Teraz możesz je ukryć do momentu, w którym będą gotowe. Możesz też ukryć strony z normalnej nawigacji, a czytelnicy będą mogli przejść na stronę za pośrednictwem zakładek lub przeglądania szczegółowego.

#### <a name="bookmarkinghttpspowerbimicrosoftcomblogpower-bi-desktop-march-2018-feature-summarybookmarking"></a>[Tworzenie zakładek](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

Jeżeli już mowa o tworzeniu zakładek, możesz utworzyć zakładki, aby opowiedzieć historię przy użyciu danych w raporcie.

- [Wyróżnianie krzyżowe między zakładkami](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): zakładki zachowują i wyświetlają stan wyróżniania krzyżowego strony raportu z momentu utworzenia zakładki.
- [Większa elastyczność zakładek](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): zakładki odzwierciedlają właściwości ustawione w raporcie i mają wpływ wyłącznie na wybrane wizualizacje.

#### <a name="multi-select-data-points-across-multiple-chartshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarycrosshighlight"></a>[Punkty danych wielokrotnego wyboru w wielu wykresach](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

Możesz wybrać wiele punktów danych w wielu wykresach i zastosować filtrowanie krzyżowe wobec całej strony.

#### <a name="sync-slicers-across-multiple-pages-of-your-reporthttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarysyncslicers"></a>[Fragmentatory synchronizacji na wielu stronach raportu](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

Fragmentator można zastosować do jednej, dwóch lub większej liczby stron w raporcie.

#### <a name="quick-measureshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summaryquickmeasures"></a>[Szybkie miary](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

Utwórz nowe miary w oparciu o istniejące miary i kolumny liczbowe w tabeli.

#### <a name="drilling-down-filters-other-visualshttpspowerbimicrosoftcomblogpower-bi-desktop-december-feature-summarydrillfiltersothervisuals"></a>[Przechodzenie do szczegółów filtruje inne wizualizacje](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

Podczas przechodzenia do szczegółów w danej kategorii w jednej wizualizacji możesz odfiltrować wszystkie wizualizacje na stronie według tej samej kategorii.

### <a name="visuals-updates"></a>Aktualizacje wizualizacji

- [Wyrównywanie komórek dla tabeli i macierzy](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [Wyświetlanie jednostek i sterowanie dokładnością w kolumnach tabeli i macierzy](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [Przepełnione etykiety danych dla wizualizacji wykresów słupkowych i kolumnowych](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [Kolor tła etykiety danych sterujących dla kartezjańskich wizualizacji i wizualizacji z mapami](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [Kontrolka dopełnienia paska/kolumny](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [Zwiększanie obszaru używanego do etykiet osi na wykresach](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [Wizualizacja wykresu punktowego na podstawie grupowań osi x i y](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [Próbkowanie o wysokiej gęstości dla map w oparciu o długość i szerokość geograficzną](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [Fragmentatory dynamiczne](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [Dodawanie daty zakotwiczenia dla fragmentatora względnej daty](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>Raportowanie

- [Wyłączanie nagłówka wizualizacji w trybie odczytu raportu](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [Opcje raportów dla powolnych źródeł danych](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [Ulepszona domyślna lokalizacja wizualizacji](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [Sterowanie kolejnością wizualizacji za pomocą okienka zaznaczenia](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [Blokowanie obiektów w raporcie](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [Wyszukiwanie w okienkach formatowania i analizy](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [Okienko właściwości pola i opisy pól](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>Analiza

- [UTCNOW() i UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [Oznaczanie niestandardowej tabeli dat](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [Przechodzenie do szczegółów filtrów innych wizualizacji](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [Formatowanie na poziomie komórek dla wielowymiarowych modeli AS w przypadku kart wielowierszowych](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)

### <a name="performance"></a>Wydajność

- [Ulepszenia wydajności filtrowania](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [Ulepszenia wydajności zapytania bezpośredniego](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [Poprawa wydajności operacji otwierania i zapisywania](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [Ulepszenia funkcji „Pokaż elementy bez danych”](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)

### <a name="report-server"></a>Serwer raportów

#### <a name="export-to-accessible-pdf"></a>Eksportowanie do dostępnych plików PDF

Podczas eksportowania raportu podzielonego na strony (RDL) do pliku PDF możesz teraz uzyskać dostępny/oznakowany plik PDF. Jego rozmiar jest większy, ale też plik jest łatwiejszy do odczytania i nawigowania na ekranach czytników lub przy użyciu innych technologii ułatwiających dostęp. Możesz włączyć dostępny plik PDF, ustawiając opcję informacji o urządzeniu **AccessiblePDF** na wartość **True**. Zobacz [Ustawienia informacji o urządzeniu PDF](https://docs.microsoft.com/sql/reporting-services/pdf-device-information-settings) oraz [Zmiana ustawień informacji o urządzeniu](https://docs.microsoft.com/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings).

### <a name="other-improvements"></a>Inne ulepszenia

- [Ulepszenia funkcji Dodaj kolumnę z przykładów](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [Szybki link do usług doradczych](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [Poprawione raportowanie błędów](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [Wyświetlanie wcześniej napotkanych błędów](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

## <a name="october-2017"></a>Październik 2017

### <a name="power-bi-report-data-sources"></a>Źródła danych raportu usługi Power BI

Raporty usługi Power BI na serwerze raportów usługi Power BI można połączyć z różnymi źródłami danych. Możesz importować dane i planować odświeżanie danych lub bezpośrednio wysłać do nich zapytanie przy użyciu zapytania bezpośredniego lub połączenia na żywo usług SQL Server Analysis Services. Zobacz listę źródeł danych, które obsługują zaplanowane odświeżanie, i tych, które obsługują zapytanie bezpośrednie w „Źródła danych raportu usługi Power BI na serwerze raportów usługi Power BI”.

### <a name="scheduled-data-refresh-for-imported-data"></a>Zaplanowane odświeżanie danych dla importowanych danych

Na serwerze raportów usługi Power BI możesz ustawić zaplanowane odświeżanie danych, aby zapewnić aktualność danych w raportach usługi Power BI z osadzonym modelem, zamiast połączenia na żywo lub trybu DirectQuery. W przypadku importowania danych w modelu zagnieżdżonym zostanie on odłączony od oryginalnego źródła danych. Musi ono zostać zaktualizowane, aby dane były aktualne, a zaplanowane odświeżanie jest sposobem, aby to zrobić. Przeczytaj więcej na temat „zaplanowanego odświeżania raportów usługi Power BI na serwerze raportów usługi Power BI”.

### <a name="editing-power-bi-reports-from-the-server"></a>Edytowanie raportów usługi Power BI z serwera

Możesz otwierać i edytować pliki raportu usługi Power BI (pbix) z serwera, ale wrócisz do oryginalnego pliku, który został przekazany.  Oznacza to, że **jeśli dane zostały odświeżone przez serwer, nie zostaną one odświeżone przy pierwszym otwarciu pliku**. Musisz ręcznie odświeżyć je lokalnie, aby zobaczyć zmianę.

### <a name="large-file-uploaddownload"></a>Pobieranie/przekazywanie dużego pliku

Możesz przekazać pliki do 2 GB, chociaż domyślnie ten limit jest ustawiony na 1 GB w ustawieniach serwera raportów w programie SQL Server Management Studio (SSMS).  Te pliki są przechowywane w bazie danych, tak samo, jak w programie SharePoint i nie jest wymagana żadna specjalna konfiguracja katalogu programu SQL Server.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Uzyskiwanie dostępu do udostępnionych zestawów danych jako źródeł danych usługi OData

Możesz uzyskać dostęp do udostępnionych zestawów danych z programu Power BI Desktop ze źródłem danych usługi OData. Aby uzyskać więcej informacji, zobacz [Uzyskiwanie dostępu do udostępnionych zestawów danych jako źródeł danych usługi OData na serwerze raportów usługi Power BI](access-dataset-odata.md).

### <a name="scale-out"></a>Skalowanie w poziomie

Ta wersja obsługuje skalowanie w poziomie. Użyj modułu równoważenia obciążenia i ustaw koligację serwera w celu uzyskania najlepszych wyników. Należy pamiętać, że scenariusz nie jest jeszcze zoptymalizowany dla skalowania w poziomie, więc zobaczysz modele potencjalnie replikowane w wielu węzłach. Scenariusz będzie działać bez modułu równoważenia obciążenia sieciowego i trwałych sesji. Jednak zobaczysz nie tylko nadmierne wykorzystanie pamięci między węzłami, gdy model będzie ładowany N razy, ale wydajność spadnie między połączeniami, ponieważ model jest przesyłany strumieniowo, gdy trafia do nowego węzła między żądaniami.  

### <a name="administrator-settings"></a>Ustawienia administratora

Administratorzy mogą ustawić następujące właściwości w zaawansowanych właściwościach programu SSMS dla farmy serwerów:

* EnableCustomVisuals: Prawda/Fałsz
* EnablePowerBIReportEmbeddedModels: Prawda/Fałsz
* EnablePowerBIReportExportData: Prawda/Fałsz
* MaxFileSizeMb: Domyślnie teraz wynosi 1000
* ModelCleanupCycleMinutes: Jak często sprawdza, czy wykluczyć modele z pamięci
* ModelExpirationMinutes: Jak długo trwa aż model wygaśnie i zostanie usunięty na podstawie czasu ostatniego użycia
* ScheduleRefreshTimeoutMinutes: Jak długo może trwać odświeżanie długich danych dla modelu. Domyślnie są to dwie godziny.  Nie ma żadnego sztywnego, górnego limitu.

**Plik konfiguracji rsreportserver.config**

```
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>Interfejs API dewelopera

Interfejs API dewelopera (API REST) wprowadzony w wersji SSRS 2017 został rozszerzony dla serwera raportów usługi Power BI do pracy z zarówno z plikami programu Excel, jak i plikami pbix. Jednym potencjalnym przypadkiem użycia jest programowe pobieranie plików z serwera, odświeżanie ich i ponownie ich opublikowanie. Na przykład jest to jedyny sposób odświeżania skoroszytów programu Excel z modelami programu PowerPivot.

Należy pamiętać, że istnieje nowy, oddzielny interfejs API dla dużych plików, które zostaną zaktualizowane w wersji serwera raportów usługi Power BI struktury Swagger. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>Usługi SQL Server Analysis Services (SSAS) i zużycie pamięci serwera raportów usługi Power BI

Serwer raportów usługi Power BI hostuje teraz wewnętrznie usługi SQL Server Analysis Services (SSAS). To nie jest specyficzne dla zaplanowanego odświeżania. Hosting usług SSAS może znacznie rozszerzyć zużycie pamięci serwera raportów. Plik konfiguracji AS.ini jest dostępny w węzłach serwerów, więc jeśli znasz usługi SSAS, możesz chcieć zaktualizować ustawienia, a w tym maksymalny limit pamięci i buforowania dysku itp. Aby uzyskać szczegółowe informacje, zobacz [Właściwości serwera w usługach Analysis Services](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services).

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Wyświetlanie i interakcje ze skoroszytami programu Excel

Program Excel i usługa Power BI zawierają ofertę narzędzi, która jest unikatowa w branży. Razem umożliwiają one analitykom biznesowym łatwiejsze zbieranie, kształtowanie, analizowanie i wizualne eksplorowanie ich danych. Oprócz wyświetlania raportów usługi Power BI w portalu internetowym, użytkownicy biznesowi mogą teraz wykonywać te same operacje ze skoroszytami programu Excel na serwerze raportów usługi Power BI, zapewniając im jedną lokalizację do publikowania i wyświetlania zawartości ich samoobsługowej analizy biznesowej firmy Microsoft.

Opublikowaliśmy [przewodnik, jak dodać serwer programu Office Online Server (OOS) do środowiska serwera raportów usługi Power BI w wersji zapoznawczej](excel-oos.md). Klienci z kontem licencji zbiorczej mogą pobrać program OOS z Centrum obsługi licencji zbiorczej bez ponoszenia kosztów i będą mieć tylko funkcje wyświetlania. Po skonfigurowaniu użytkownicy mogą wyświetlać i wchodzić w interakcje ze skoroszytami programu Excel które:

* Nie mają zależności od zewnętrznych źródeł danych
* Mają aktywne połączenie z zewnętrznym źródłem danych usług SQL Server Analysis Services
* Mają model danych programu PowerPivot

### <a name="support-for-new-table-and-matrix-visuals"></a>Obsługiwanie nowych elementów wizualnych tabeli i macierzy

Serwer raportów usługi Power BI obsługuje obecnie nowe elementy wizualne tabeli i macierzy usługi Power BI. Aby utworzyć raporty z tymi elementami wizualnymi, konieczne będzie zaktualizowanie programu Power BI Desktop do wersji z października 2017 r. Nie można jej zainstalować obok wersji programu Power BI Desktop z czerwca 2017 r. Dla najnowszej wersji programu Power BI Desktop na [stronie pobierania serwera raportów usługi Power BI](https://powerbi.microsoft.com/report-server/) wybierz pozycję **Zaawansowane opcje pobierania**.

## <a name="june-2017"></a>Czerwiec 2017

* Ogólnodostępna wersja serwera raportów usługi Power BI (GA).

## <a name="may-2017"></a>Maj 2017 r.

* Udostępniono wersję zapoznawczą serwera raportów usługi Power BI
* Możliwość lokalnego publikowania raportów usługi Power BI
  * obsługa wizualizacji niestandardowych
  * Obsługa **połączeń na żywo usług Analysis Services** tylko z większą liczbą źródeł danych w przyszłości.
  * Aplikacja mobilna usługi Power BI zaktualizowana w celu wyświetlania raportów usługi Power BI hostowanych na serwerze raportów usługi Power BI
* Rozszerzona współpraca przy raportach z komentarzami

## <a name="next-steps"></a>Następne kroki

[Co to jest serwer raportów usługi Power BI?](get-started.md) 
[Podręcznik administratora](admin-handbook-overview.md)  
[Instalacja serwera raportów usługi Power BI](install-report-server.md)  
[Pobieranie programu Report Builder](https://www.microsoft.com/download/details.aspx?id=53613)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)