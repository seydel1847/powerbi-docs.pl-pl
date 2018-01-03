---
title: "Interakcje z raportem w widoku do czytania w usłudze Power BI"
description: "Interakcje z raportem w widoku do czytania w usłudze Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/15/2017
ms.author: mihart
ms.openlocfilehash: 54de712e0743801b3e8c565ca997bbc56e254c69
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="interact-with-a-report-in-reading-view-in-power-bi"></a>Interakcje z raportem w widoku do czytania w usłudze Power BI
## <a name="reading-view"></a>Widok do czytania
Widok do czytania nie jest tak interaktywny, jak [Widok do edycji](service-interact-with-a-report-in-editing-view.md), ale nadal udostępnia wiele opcji eksplorowania danych. Ujawnia on swoją przydatność podczas przeglądania [udostępnionych Ci](service-share-dashboards.md) raportów, które mogą być otwierane tylko w widoku do czytania.

Widok do czytania to przyjemny i bezpieczny sposób zabawy i poznawania swoich danych. W widoku do czytania możesz krzyżowo zaznaczać i krzyżowo filtrować elementy wizualne na stronie.  Po prostu zaznacz lub wybierz wartość w jednym elemencie wizualnym i natychmiast zobacz jej wpływ na inne elementy wizualne. Okienko Filtr umożliwia dodawanie i modyfikowanie filtrów na stronie raportu oraz zmianę sposobu sortowania wartości w wizualizacji. Wszelkie zmiany filtrowania i zaznaczenia nie są zapisywane wraz z raportem.

## <a name="cross-highlight-the-related-visualizations-on-a-page"></a>Krzyżowe zaznaczanie powiązanych wizualizacji na stronie
Wizualizacje na pojedynczej stronie raportu są wszystkie „połączone” ze sobą.  Oznacza to, że w przypadku wybrania przynajmniej jednej wartości w jednej wizualizacji inne wizualizacje, które używają tej samej wartości, ulegną zmianie na podstawie tego wyboru.

![](media/service-interact-with-a-report-in-reading-view/pagefilter3b.gif)

> [!NOTE]
> Aby wybrać więcej niż jeden element wizualizacji, przytrzymaj naciśnięty klawisz CTRL.
> 
> 

## <a name="hover-over-visual-elements-to-see-the-details"></a>Umieszczanie kursora nad elementami wizualnymi, aby wyświetlić szczegóły
![](media/service-interact-with-a-report-in-reading-view/amarillachart.png)

## <a name="sort-the-data-in-a-visualization"></a>Sortowanie danych w wizualizacji
Wybierz wielokropek (...), aby otworzyć pozycję **Sortuj według**. Wybierz strzałkę listy rozwijanej, aby wybrać pole, według którego ma się odbywać sortowanie, lub wybierz ikonę AZ, aby się przełączać między kolejnością rosnącą lub malejącą. 

![](media/service-interact-with-a-report-in-reading-view/pbi_changechartsort.gif) 

## <a name="interact-with-filters"></a>Interakcja z filtrami
Jeśli autor raportu dodał filtry do strony w raporcie, możesz wchodzić z nimi w interakcje w widoku do czytania. Wprowadzone zmiany nie zostaną zapisane z raportem.

1. Wybierz ikonę filtra w prawym górnym rogu.
   
   ![](media/service-interact-with-a-report-in-reading-view/filters.png)  
2. Zobaczysz wszystkie filtry, które zostały zastosowane do wybranego elementu wizualnego (filtry poziomu elementu wizualnego), do całej strony raportu (filtry poziomu strony) i do całego raportu (filtry poziomu raportu).
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-reading-filters.png)
3. Umieść kursor nad filtrem i rozwiń go, wybierając strzałkę w dół.
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-expan-filter.png)
4. Wprowadź zmiany do filtrów i zobacz ich wpływ na elementy wizualne.  
   
   * W tym przykładzie mamy filtr poziomu strony dla **sieci**. Zmień go na **Fashions Direct** zamiast **Lindseys**, usuwając znacznik wyboru z jednego i dodając go do drugiego.
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-filter-chain.png)
   * Lub całkowicie usuń filtrowanie **sieci**, wybierając ikonę gumki ![](media/service-interact-with-a-report-in-reading-view/power-bi-eraser-icon.png) lub wybierając obie sieci sklepów.
   * Wybierz filtr poziomu strony **Okręg** i przejdź do **zaawansowanego filtrowania**. Przefiltruj, aby pokazać tylko okręgi rozpoczynające się od **FD** i niezawierające liczby 4.
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-advanced-filter.png)

Aby uzyskać więcej informacji, zobacz [Dodawanie filtra do raportu](power-bi-report-add-filter.md) i [Informacje o filtrach i zaznaczaniu w raportach](power-bi-reports-filters-and-highlighting.md).

## <a name="zoom-in-on-individual-visuals"></a>Powiększanie poszczególnych elementów wizualnych
Umieść kursor na elemencie wizualnym i wybierz ikonę **trybu koncentracji uwagi** ![](media/service-interact-with-a-report-in-reading-view/pbi_popouticon.jpg). Po wyświetleniu wizualizacji w trybie koncentracji uwagi rozszerza on ją tak, aby wypełniła całą kanwę raportu, jak pokazano poniżej.

![](media/service-interact-with-a-report-in-reading-view/powerbi-focus-mode.png)

Aby wyświetlić tę samą wizualizację bez przeszkadzającego paska menu, okienka filtra i innych elementów — wybierz ikonę **Pełny ekran** z najwyższego paska menu ![](media/service-interact-with-a-report-in-reading-view/power-bi-focus-icon.png).

![](media/service-interact-with-a-report-in-reading-view/power-bi-full-screen.png)

Aby dowiedzieć się więcej, zobacz [Tryb koncentracji uwagi dla raportów](service-focus-mode.md) i [Tryb pełnoekranowy dla raportów](service-fullscreen-mode.md)

## <a name="adjust-the-display-dimensions"></a>Dostosowywanie wymiarów wyświetlania
Raporty są wyświetlane na wielu różnych urządzeniach mających różne rozmiary ekranu i współczynniki proporcji.  Domyślne renderowanie może nie być tym, co chcesz zobaczyć na swoim urządzeniu.  Aby dostosować, wybierz pozycję **Widok**, a następnie wybierz pozycję:

* Dopasuj do strony: skalowanie zawartości tak, aby najlepiej dopasować się do strony
* Dopasuj do szerokości: skalowanie zawartości tak, aby dopasować się do szerokości strony
* Rozmiar rzeczywisty: wyświetla zawartość w pełnym rozmiarze  

![](media/service-interact-with-a-report-in-reading-view/power-bi-view.png)

  W widoku do czytania wybrana opcja wyświetlania jest tymczasowa — nie jest zapisywana, gdy zamkniesz raport.

  Aby dowiedzieć się więcej, zobacz [Samouczek: Zmienianie ustawień wyświetlania w raporcie](power-bi-change-report-display-settings.md).

## <a name="next-steps"></a>Następne kroki
[Raporty w usłudze Power BI](service-reports.md)

[Otwieranie widoku do edycji](service-reading-view-and-editing-view.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)
