---
title: Część 2, dodawanie wizualizacji do raportu usługi Power BI
description: Część 2, dodawanie wizualizacji do raportu usługi Power BI
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 01/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 5c3f98635d188aa1857be9c8d8e36dc296339ad7
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34292230"
---
# <a name="part-2-add-visualizations-to-a-power-bi-report"></a>Część 2, dodawanie wizualizacji do raportu usługi Power BI
W [części 1](power-bi-report-add-visualizations-ii.md) utworzono podstawową wizualizację przez zaznaczenie pól wyboru obok nazw pól.  W części 2 dowiesz się, jak używać metody przeciągania i upuszczania oraz jak w pełni korzystać z okienek **Pola** i **Wizualizacje** na potrzeby tworzenia i modyfikowania wizualizacji.

### <a name="prerequisites"></a>Wymagania wstępne
- [Część 1](power-bi-report-add-visualizations-ii.md)
- Usługa Power BI — wizualizacje można dodać do raportów za pomocą usługi Power BI lub programu Power BI Desktop. W tym samouczku wykorzystywana jest usługa Power BI. 
- Przykład Retail Analysis

## <a name="create-a-new-visualization"></a>Tworzenie nowej wizualizacji
W tym samouczku skorzystamy z naszego zestawu danych Retail Analysis i utworzymy kilka kluczowych wizualizacji.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Otwieranie raportu i dodawanie nowej, pustej strony
1. Otwórz obszar roboczy, w którym zapisano przykład Retail Analysis. Wybierz **Przykład Retail Analysis**, aby otworzyć raport w widoku do czytania.
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-report.png)
2. Wybierz pozycję **Edytuj raport**, aby otworzyć raport w widoku do edycji.
   
   ![](media/power-bi-report-add-visualizations-ii/editreport1.png)
3. [Dodaj nową stronę](power-bi-report-add-page.md), wybierając żółtą ikonę ze znakiem plus w dolnej części obszaru roboczego.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_addreportpage.png)

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Dodawanie wizualizacji z porównaniem sprzedaży z bieżącego roku i z ostatniego roku
1. Z tabeli **Sales** (Sprzedaż) wybierz pozycje **This Year Sales** > **Value** (Sprzedaż z bieżącego roku > Wartość) i **Last Year Sales** (Sprzedaż z ostatniego roku). Usługa Power BI utworzy wykres kolumnowy.  Okazuje się to być całkiem interesujące, więc warto dokonać szczegółowej analizy. Jakie są wyniki sprzedaży w poszczególnych miesiącach?  
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_4bnew.png)
2. Z tabeli Time (Czas) przeciągnij pozycję **Month** (Miesiąc) do obszaru **Oś**.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_5newnew.png)
3. [Zmień wizualizację](power-bi-report-change-visualization-type.md) na wykres warstwowy.  Istnieje wiele typów wizualizacji do wyboru. Jeśli potrzebujesz pomocy w zdecydowaniu, którego typu użyć, zapoznaj się z [opisem każdego z nich, wskazówkami dotyczącymi najlepszych rozwiązań i samouczkami](power-bi-visualization-types-for-reports-and-q-and-a.md). W okienku Wizualizacje wybierz ikonę Wykres warstwowy.
4. Posortuj wizualizację, wybierając wielokropek i pozycję **Sortuj według miesięcy**.
5. [Zmień rozmiar wizualizacji](power-bi-visualization-move-and-resize.md), wybierając wizualizację, chwytając jeden z okręgów konturu i przeciągając do nowej pozycji. Rozszerz ją do takich rozmiarów, aby nie wyświetlał się już pasek przewijania, ale aby pozostało dość miejsca na dodanie kolejnej wizualizacji.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Zapisz raport](service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Dodawanie wizualizacji mapy z porównaniem sprzedaży według lokalizacji
1. Z tabeli **Store** (Sklep) wybierz pozycję **Territory** (Terytorium). Usługa Power BI rozpozna, że terytorium to lokalizacja, i utworzy wizualizację mapy.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_8newnew.png)
2. Przeciągnij pozycję **Total Stores** (Łączna liczba sklepów) do obszaru Rozmiar.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-reportnew.png)
3. Dodaj legendę.  Aby wyświetlić dane według nazw sklepów, przeciągnij pozycję **Chain** (Sieć) do obszaru Legenda.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-report-3new.png)

## <a name="next-steps"></a>Następne kroki
* Aby uzyskać więcej informacji na temat okienka Pola, zobacz [The report editor... take a tour](service-the-report-editor-take-a-tour.md) (Edytor raportów — przewodnik).   
* Aby dowiedzieć się, jak filtrować i wyróżniać wizualizacje, zobacz [Filtry i wyróżnianie w raportach usługi Power BI](power-bi-reports-filters-and-highlighting.md).  
* Więcej informacji o [wizualizacjach w raportach usługi Power BI](power-bi-report-visualizations.md).  
* Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

