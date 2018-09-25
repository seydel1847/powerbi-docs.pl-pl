---
title: Omówienie okienka Filtry usługi Power BI
description: Omówienie okienka Filtry raportu w usłudze Power BI i na pulpicie nawigacyjnym usługi Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 19ca2c1fa04d5d2cde06d850d3d6813fa6928783
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565204"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Zapoznaj się z przewodnikiem dotyczącym okienka filtrów raportu
Ten artykuł szczegółowo opisuje okienko Filtry raportu. Okienko zostanie wyświetlone w [widoku do edycji i widoku do czytania usługi Power BI](end-user-reading-view.md) oraz [widoku raportu w programie Power BI Desktop](../desktop-report-view.md).

Istnieje wiele sposobów, aby filtrować dane w usłudze Power BI i zalecamy zapoznać się najpierw z artykułem [Informacje o filtrach i wyróżnianiu](../power-bi-reports-filters-and-highlighting.md).

## <a name="working-with-the-report-filters-pane"></a>Praca z okienkiem Filtry raportu
W programie Power BI Desktop raporty są otwierane w widoku raportu. W usłudze Power BI raporty można otwierać w [widoku do edycji lub widoku do czytania](end-user-reading-view.md). W widoku do edycji i w widoku raportu w programie Desktop właściciele raportów mogą [dodawać filtry do raportu](../power-bi-report-add-filter.md). Te filtry są zapisywane razem z raportem. Osoby wyświetlające raport w widoku do czytania mogą wchodzić w interakcje z filtrami i zapisywać swoje zmiany, nie mogą jednak dodawać nowych filtrów do raportu.

W usłudze Power BI raporty zachowują wszelkie zmiany wprowadzone w okienku Filtry. Te zmiany są przekazywane do mobilnej wersji raportu. Aby zresetować okienko Filtry do wartości domyślnych dla twórców, wybierz pozycję **Przywróć domyślne** z górnego paska menu.     

## <a name="open-the-filters-pane"></a>Otwieranie okienka Filtry
Po otwarciu raportu okienko Filtry jest wyświetlane wzdłuż prawej strony kanwy raportu. Jeśli okienko nie jest widoczne, wybierz strzałkę w prawym górnym rogu, aby je rozwinąć. W widoku do czytania w usłudze Power BI jedynym okienkiem dostępnym po prawej stronie jest okienko Filtry.

W tym przykładzie wybraliśmy wizualizację, która ma 6 filtrów. Strona raportu ma także filtry wyświetlane w pozycji **Filtry na poziomie strony**. Istnieje też jeden [filtr przeglądania szczegółowego](../power-bi-report-add-filter.md), zaś cały raport ma też filtr: **FiscalYear** to 2013 lub 2014.

![](media/end-user-report-filter/power-bi-filter-list.png)

Obok nazwy niektórych filtrów wyświetla się słowo **Wszystkie**, co oznacza, że filtr uwzględnia wszystkie wartości.  Na przykład wartość **Chain (Wszystkie)** na poniższym zrzucie ekranu informuje nas, że ta strona raportu uwzględnia dane dotyczące wszystkich sieci sklepów.  Z drugiej strony filtr na poziomie strony **FiscalYear to 2013 lub 2014** informuje nas, że raport uwzględnia tylko dane za lata obrachunkowe 2013 i 2014.

Każda osoba wyświetlająca ten raport może wchodzić w interakcje z tymi filtrami.

* Wyświetlenie szczegółów filtru przez umieszczenie nad nim kursora i wybranie strzałki obok filtru.
  
   ![](media/end-user-report-filter/power-bi-expan-filter.png)
* Zmiana filtru, na przykład zmiana sieci z **Lindseys** na **Fashions Direct**.
  
     ![](media/end-user-report-filter/power-bi-filter-chain.png)

* Zresetowanie filtrów do pierwotnego stanu przez wybranie pozycji **Przywróć domyślne** z górnego paska menu.    
    ![](media/end-user-report-filter/power-bi-reset-to-default.png)
    
* Usunięcie filtru przez wybranie symbolu **x** obok jego nazwy.
  
  Usunięcie filtru spowoduje usunięcie go z listy, ale nie spowoduje usunięcia danych z raportu.  Jeśli na przykład usuniesz filtr **FiscalYear to 2013 lub 2014**, dane roku obrachunkowego pozostaną w raporcie, ale nie będzie on już filtrowany, aby wyświetlać tylko dane dla roku 2013 i 2014. Będą wyświetlane dane dostępne dla wszystkich lat obrachunkowych.  Jednak po usunięciu filtru nie będzie można go modyfikować, ponieważ zostanie usunięty z listy. Lepszym rozwiązaniem jest wyczyszczenie filtru przy użyciu ikony gumki ![](media/end-user-report-filter/power-bi-eraser-icon.png).
  
  ![](media/end-user-report-filter/power-bi-delete-filter.png)

## <a name="filters-in-editing-view"></a>Filtry w widoku do edycji
Po otwarciu raportu w programie Desktop lub w widoku do edycji usługi Power BI okienko Filtry będzie wyświetlane wzdłuż prawej strony kanwy raportu w dolnej części okienka **Wizualizacja**. Jeśli okienko nie jest widoczne, wybierz strzałkę w prawym górnym rogu, aby je rozwinąć.

![](media/end-user-report-filter/power-bi-all-filters.png)  

Jeśli na kanwie nie wybrano wizualizacji, okienko Filtry będzie zawierać tylko filtry dotyczące całej strony raportu lub całego raportu, a także filtry przeglądania szczegółowego (jeśli zostały ustawione). W poniższym przykładzie nie została wybrana wizualizacja, nie ma także filtrów na poziomie strony ani filtrów przeglądania szczegółowego, za to widoczny jest filtr na poziomie raportu.  

![](media/end-user-report-filter/power-bi-no-visual.png)  

Po wybraniu wizualizacji na kanwie wyświetlone zostaną także filtry mające zastosowanie tylko do tej wizualizacji:   

![](media/end-user-report-filter/power-bi-visual-filters.png)

Aby wyświetlić opcje dla konkretnego filtru, wybierz strzałkę w dół obok jego nazwy.  W poniższym przykładzie dla filtru na poziomie raportu wybrano wartości 2013 i 2014. To przykład **filtrowania podstawowego**.  Aby wyświetlić opcje zaawansowane, wybierz pozycję **Filtrowanie zaawansowane**.

![](media/end-user-report-filter/pbi_filterlistdropdown.jpg)

## <a name="clear-a-filter"></a>Czyszczenie filtru
 W zaawansowanym lub podstawowym trybie filtrowania wybierz ikonę gumki ![](media/end-user-report-filter/pbi_erasericon.jpg), aby wyczyścić filtr. 

## <a name="add-a-filter"></a>Dodawanie filtru
* W programie Desktop lub w widoku do edycji usługi Power BI dodaj filtr do wizualizacji, strony, przeglądania szczegółowego lub raportu, zaznaczając pole w okienku Pola i przeciągając je do odpowiedniego obszaru filtrów, gdzie widać słowa **Przeciągnij pola tutaj**. Po dodaniu pola jako filtru dostosuj go za pomocą kontrolek Filtrowanie podstawowe i Filtrowanie zaawansowane (opisanych poniżej).

* **Przeciągnięcie nowego pola do obszaru Filtry na poziomie wizualizacji nie powoduje dodania tego pola do wizualizacji**, pozwala jednak filtrować wizualizację za pomocą tego nowego pola. W poniższym przykładzie pole **Chain** zostało dodane jako nowy filtr do wizualizacji. Zwróć uwagę, że samo dodanie pola **Chain** jako filtru nie zmienia wizualizacji, dopóki nie użyjesz kontrolek Filtrowanie podstawowe i Filtrowanie zaawansowane.

    ![](media/end-user-report-filter/power-bi-visual-filter.gif)

* Wszystkie pola użyte do utworzenia wizualizacji są także dostępne jako filtry. Wybierz wizualizację, aby ją uaktywnić. Pola, które są używane w wizualizacji, są wyświetlane w okienku Wizualizacje i w okienku Filtry w obszarze **Filtry na poziomie wizualizacji**.
  
   ![](media/end-user-report-filter/power-bi-visual-filter.png)  
  
   Dowolne pola możesz dostosować za pomocą kontrolek Filtrowanie podstawowe i Filtrowanie zaawansowane (opisanych poniżej).

## <a name="types-of-filters-text-field-filters"></a>Typy filtrów: filtry pól tekstowych
### <a name="list-mode"></a>Tryb listy
Zaznaczenie pola wyboru powoduje wybranie lub anulowanie wyboru wartości. Pola wyboru **Wszystkie** można użyć do przełączenia stanu (zaznaczenia lub usunięcia zaznaczenia) wszystkich pól wyboru. Pola wyboru reprezentują wszystkie dostępne wartości dla danego pola.  Dostosowanie filtru powoduje aktualizację instrukcji w oparciu o wybrane opcje. 

![](media/end-user-report-filter/pbi_restatement.png)

Zwróć uwagę na zmianę instrukcji na „to Amarilla lub Carretera”

### <a name="advanced-mode"></a>Tryb zaawansowany
Wybierz pozycję **Filtrowanie zaawansowane**, aby przejść do trybu zaawansowanego. Wskaż pola do uwzględnienia za pomocą kontrolek list rozwijanych i pól tekstowych. Wybierając pozycję **I** albo **Lub**, można tworzyć złożone wyrażenia filtrowania. Po ustawieniu odpowiednich wartości wybierz przycisk **Zastosuj filtr**.  

![](media/end-user-report-filter/aboutfilters.png)

## <a name="types-of-filters-numeric-field-filters"></a>Typy filtrów: filtry pól liczbowych
### <a name="list-mode"></a>Tryb listy
Jeśli wartości są wartościami skończonymi, po wybraniu nazwy pola zostanie wyświetlona lista.  Zobacz **Filtry pól testowych** &gt; **Tryb listy** powyżej, aby uzyskać pomoc dotyczącą używania pól wyboru.   

### <a name="advanced-mode"></a>Tryb zaawansowany
Jeśli wartości są wartościami nieskończonymi lub reprezentują zakres, po wybraniu nazwy pola zostanie otwarty zaawansowany tryb filtru. Określ zakres wartości, które mają być wyświetlane, za pomocą listy rozwijanej i pól tekstowych. 

![](media/end-user-report-filter/pbi_dropdown-and-text.png)

Wybierając pozycję **I** albo **Lub**, można tworzyć złożone wyrażenia filtrowania. Po ustawieniu odpowiednich wartości wybierz przycisk **Zastosuj filtr**.

## <a name="types-of-filters-date-and-time"></a>Typy filtrów: data i godzina
### <a name="list-mode"></a>Tryb listy
Jeśli wartości są wartościami skończonymi, po wybraniu nazwy pola zostanie wyświetlona lista.  Zobacz **Filtry pól testowych** &gt; **Tryb listy** powyżej, aby uzyskać pomoc dotyczącą używania pól wyboru.   

### <a name="advanced-mode"></a>Tryb zaawansowany
Jeśli wartości pól reprezentują datę lub godzinę, przy użyciu filtrów daty/godziny można określić czas rozpoczęcia i zakończenia.  

![](media/end-user-report-filter/pbi_date-time-filters.png)

## <a name="next-steps"></a>Następne kroki
[Filtry i wyróżnianie w raportach](../power-bi-reports-filters-and-highlighting.md)  
[Interakcja z filtrami i wyróżnianie w widoku do czytania raportu](end-user-reading-view.md)  
[Tworzenie filtrów w widoku do edycji](../power-bi-report-add-filter.md)  
[Zmiana sposobu wzajemnego filtrowania i wyróżniania krzyżowego wizualizacji raportu](end-user-interactions.md)

Przeczytaj więcej na temat [raportów w usłudze Power BI](end-user-reports.md)  
[Power BI — podstawowe pojęcia](end-user-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)
