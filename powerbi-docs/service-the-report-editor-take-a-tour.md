---
title: "Edytor raportu: krótki przewodnik"
description: "Edytor raportu: krótki przewodnik."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
featuredvideoid: IkJda4O7oGs
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/30/2017
ms.author: mihart
ms.openlocfilehash: e5ee6db22fe0fa7fd1e61ebbfb7dbee9d3458159
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="the-report-editortake-a-tour"></a>Edytor raportu: krótki przewodnik
Edytor raportu w usłudze Power BI i edytor raportu w programie Power BI Desktop są bardzo podobne. Film pokazuje edytor raportu w programie Power BI Desktop, a ten artykuł przedstawia edytor raportu w usłudze Power BI. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

W usłudze Power BI *edytor raportu* jest dostępny tylko w [widoku do edycji](service-reading-view-and-editing-view.md). Aby otworzyć raport w widoku do edycji, musisz być właścicielem raportu.

Edytor raportu usługi Power BI składa się z 3 sekcji:  

1. okienek **Pola**, **Wizualizacje** i **Filtry**
2. górne paski nawigacyjne    
3. kanwa raportu     

![](media/service-the-report-editor-take-a-tour/power-bi-report-canvas.png)

## <a name="1-the-report-editor-panes"></a>1. Okienka edytora raportu
![](media/service-the-report-editor-take-a-tour/power-bi-report-panes.png)

Przy pierwszym otwarciu raportu będą widoczne 3 okienka: Wizualizacje, Filtry i Pola. Okienka po lewej stronie, Wizualizacje i Filtry, kontrolują wygląd Twoich wizualizacji — typ, kolory, filtrowanie, formatowanie.  A okienko po prawej stronie, Pola, zarządza podstawowymi danymi używanymi w wizualizacjach. 

Zawartość wyświetlana w edytorze raportu jest zależna od wyborów dokonanych na kanwie raportu.  Na przykład po wybraniu oddzielnego elementu wizualnego, 

|  |  |
| --- | --- |
| ![](media/service-the-report-editor-take-a-tour/power-bi-panes.png) |<ul><li>Górna część okienka wizualizacji identyfikuje typ używanego elementu wizualnego; w tym przykładzie jest to wykres słupkowy grupowany.<br><br></li> <li>Dolna część okienka wizualizacji (może okazać się konieczne przewinięcie) wyświetla pola używane w elemencie wizualnym. Ten wykres używa pól FiscalMonth, DistrictManager i Total Sales Variance. <br><br></li><li>Okienko filtry (może okazać się konieczne przewinięcie) wyświetla wszelkie filtry, które zostały zastosowane. <br><br></li><li>Okienko pól zawiera listę dostępnych tabel, a jeśli rozwiniesz nazwę tabeli, pola, które tworzą daną tabelę. Żółta czcionka informuje, że co najmniej jedno pole z tej tabeli jest używane do wizualizacji.<br><br></li><li>![](media/service-the-report-editor-take-a-tour/power-bi-paint-roller-icon.png) Aby wyświetlić okienko formatowania dla wybranej wizualizacji, wybierz ikonę wałka do malowania.<br><br></li><li>![](media/service-the-report-editor-take-a-tour/power-bi-magnifying-icon.png) Aby wyświetlić okienko analizy, wybierz ikonę lupy.</ul> |
|  | |

## <a name="the-visualizations-pane-from-top-to-bottom"></a>Okienko Wizualizacje (od góry do dołu)
![](media/service-the-report-editor-take-a-tour/selectviz.png)

To właśnie tutaj wybierasz typ wizualizacji. Małe obrazki są nazywane *szablonami*. Na ilustracji powyżej jest wybrany wykres słupkowy grupowany. Jeśli nie wybierzesz najpierw typu wizualizacji, ale zamiast tego zaczniesz tworzenie wizualizacji, wybierając pola, usługa Power BI sama wybierze typ wizualizacji. Możesz zachować wybór usługi Power BI lub zmienić typ, wybierając inny szablon. Możesz się przełączać tyle razy, ile trzeba, aby znaleźć typ wizualizacji, który najlepiej reprezentuje Twoje dane.

### <a name="manage-the-fields-used-in-your-visual"></a>Zarządzaj polami użytymi w Twoim elemencie wizualnym.
![](media/service-the-report-editor-take-a-tour/power-bi-field-list.png)

Zasobniki (czasem nazywane *źródłami*) pokazane w tym okienku różnią się w zależności od wybranego typu wizualizacji.  Na przykład, jeśli wybierzesz wykres słupkowy, zobaczysz zasobniki dla: wartości, osi i legendy. Gdy wybierasz pole lub przeciągasz je na kanwie, usługa Power BI dodaje to pole do jednego z zasobników.  Możesz też przeciągać pola z listy pól bezpośrednio do zasobników.  Niektóre zasobniki są ograniczone do pewnych typów danych.  Na przykład **wartości** nie akceptują pól nienumerycznych. Dlatego, jeśli przeciągniesz pole **employeename** pole do zasobnika **Wartości**, usługa Power BI zmieni go na **liczba employeename**.

### <a name="remove-a-field"></a>Usuwanie pola
Aby usunąć pole z wizualizacji, wybierz znak **X** z prawej strony nazwy pola.

![](media/service-the-report-editor-take-a-tour/deletefield.png)

Aby uzyskać więcej informacji, zobacz [Dodawanie wizualizacji do raportu usługi Power BI](power-bi-report-add-visualizations-i.md)

### <a name="format-your-visuals"></a>Formatowanie elementów wizualnych
Wybierz ikonę wałka do malowania, aby wyświetlić okienko Format. Dostępność opcji zależy od wybranego typu wizualizacji.

![](media/service-the-report-editor-take-a-tour/power-bi-formatting.png)

Możliwości formatowania są prawie nieskończone.  Aby dowiedzieć się więcej, rozpocznij samodzielną eksplorację lub zapoznaj się z następującymi artykułami:

* [Dostosowywanie tytułu, tła i legendy wizualizacji](power-bi-visualization-customize-title-background-and-legend.md)
* [Formatowanie koloru](service-getting-started-with-color-formatting-and-axis-properties.md)
* [Dostosowywanie właściwości osi x i y](power-bi-visualization-customize-x-axis-and-y-axis.md)

### <a name="add-analytics-to-your-visualizations"></a>Dodawanie analizy do wizualizacji
Aby wyświetlić okienko analizy, wybierz ikonę lupy. Dostępność opcji zależy od wybranego typu wizualizacji.

![](media/service-the-report-editor-take-a-tour/power-bi-analytics.png)    
Za pomocą okienka analizy w usłudze Power BI możesz dodać linie odwołania dynamicznego do wizualizacji i skoncentrować się na ważnych trendach lub szczegółowych informacjach. Aby dowiedzieć się więcej, zobacz [Okienko analizy w usłudze Power BI](service-analytics-pane.md) lub [Okienko analizy w programie Power BI Desktop](desktop-analytics-pane.md).

- - -
## <a name="the-filters-pane"></a>Okienko Filtry
Wyświetlaj, ustawiaj i modyfikuj stronę, raport, przeglądanie szczegółowe i filtry poziomu wizualnego.

![](media/service-the-report-editor-take-a-tour/power-bi-formatting-pane.png)

Aby uzyskać więcej informacji, zobacz [Dodawanie filtru do raportu](power-bi-report-add-filter.md).

- - -
## <a name="the-fields-pane"></a>Okienko Pola
W okienku pól są wyświetlane tabele i pola, które istnieją w Twoich danych i których możesz używać do tworzenia wizualizacji.

|  |  |
| --- | --- |
| ![](media/service-the-report-editor-take-a-tour/reportfields.png) |<ul><li>Przeciągnij pole na stronę, aby rozpocząć nową wizualizację.  Możesz również przeciągnąć pole na istniejącą wizualizację, aby dodać pole do tej wizualizacji.<br><br></li> <li>Po dodaniu znacznika wyboru obok pola usługa Power BI dodaje to pole do aktywnej (lub nowej) wizualizacji. A także decyduje, w którym zasobniku należy umieścić to pole.  Na przykład, czy pole powinno być używane jako legenda, oś lub wartość? Usługa Power BI ułatwia podjęcie decyzji i w razie potrzeby możesz przenieść je z tego zasobnika do innego. <br><br></li><li>W każdym przypadku każde wybrane pole jest dodawane do okienka Wizualizacje w edytorze raportu.</li></ul> |

**UWAGA**: Jeśli używasz programu Power BI Desktop, będą również dostępne opcje pokazywania/ukrywania pól, dodawania obliczeń itd.

### <a name="what-do-the-field-icons-mean"></a>Co oznaczają ikony pól?
* **Agregaty ∑** Agregat jest wartością numeryczną, która będzie na przykład sumowana lub uśredniana. Agregaty są importowane z danymi (zdefiniowanymi w modelu danych, na którym jest oparty Twój raport).
  Aby uzyskać więcej informacji, zobacz [Wartości zagregowane w raportach usługi Power BI](service-aggregates.md).
* ![](media/service-the-report-editor-take-a-tour/pbi_calculated_icon.png) **Obliczane miary (nazywane również polami obliczeniowymi)**  
   Każde pole obliczeniowe ma własną ustaloną formułę. Nie możesz zmienić obliczenia, jeśli, na przykład, jest to suma, pozostanie sumą. Aby uzyskać więcej informacji, przeczytaj [Opis miar](desktop-measures.md)
* ![](media/service-the-report-editor-take-a-tour/icon.png) **Unikatowe pola**  
   Pola z tą ikoną zostały zaimportowane z programu Excel i są ustawione na pokazywanie wszystkich wartości, nawet jeśli mają one duplikaty. Na przykład Twoje dane mogą mieć dwa rekordy dla osób o nazwisku „Jan Kowalski” i każdy z nich będzie traktowany jako unikatowy — nie zostaną one zsumowane.  
*  **![](media/service-the-report-editor-take-a-tour/pbi_geo_icon.png)Pola geograficzne**  
   Pola lokalizacji mogą służyć do tworzenia wizualizacji map. 
* **![](media/service-the-report-editor-take-a-tour/power-bi-hierarchy-icon.png) Hierarchia**  
   Wybierz strzałkę, aby ujawnić pola, które tworzą hierarchię. 

- - -
## <a name="2-the-top-navigation-bar"></a>2. Górny pasek nawigacyjny
Na górnym pasku nawigacyjnym są dostępne liczne akcje, przy czym cały czas są dodawane nowe akcje. Aby uzyskać informacje o określonej akcji, użyj spisu treści lub pola wyszukiwania dokumentacji usługi Power BI.

## <a name="3-the-report-canvas"></a>3. Kanwa raportu
Kanwa raportu jest miejscem, gdzie jest wyświetlana Twoja praca. Gdy używasz okienek pól, filtrów i wizualizacji do tworzenia elementów wizualnych, są one budowane i wyświetlane na kanwie Twojego raportu. Każda karta w dolnej części kanwy reprezentuje stronę raportu. Wybierz kartę, aby otworzyć tę stronę. 

## <a name="next-steps"></a>Następne kroki:
[Tworzenie raportu](service-report-create-new.md)

[Edytowanie raportu](service-interact-with-a-report-in-editing-view.md)

Przeczytaj więcej na temat [raportów w usłudze Power BI](service-reports.md)

[Wprowadzenie do usługi Power BI](service-get-started.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)
