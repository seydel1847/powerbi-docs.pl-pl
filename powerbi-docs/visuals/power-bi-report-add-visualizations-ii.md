---
title: Część 2, dodawanie wizualizacji do raportu usługi Power BI
description: Część 2, dodawanie wizualizacji do raportu usługi Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: a15975f456bab94fd04fa7501760c9874fabf952
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44736901"
---
# <a name="part-2-add-visualizations-to-a-power-bi-report"></a>Część 2, dodawanie wizualizacji do raportu usługi Power BI
W [części 1](power-bi-report-add-visualizations-ii.md) utworzono podstawową wizualizację przez zaznaczenie pól wyboru obok nazw pól.  W części 2 dowiesz się, jak używać metody przeciągania i upuszczania oraz jak w pełni korzystać z okienek **Pola** i **Wizualizacje** na potrzeby tworzenia i modyfikowania wizualizacji.

### <a name="prerequisites"></a>Wymagania wstępne
- [Część 1](power-bi-report-add-visualizations-ii.md)
- Power BI Desktop — wizualizacje można dodać do raportów za pomocą usługi Power BI lub programu Power BI Desktop. W tym samouczku wykorzystywany jest program Power BI Desktop. 
- [Przykład Retail Analysis](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

## <a name="create-a-new-visualization"></a>Tworzenie nowej wizualizacji
W tym samouczku skorzystamy z naszego zestawu danych Retail Analysis i utworzymy kilka kluczowych wizualizacji.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Otwieranie raportu i dodawanie nowej, pustej strony
1. Otwórz plik PBIX przykładu Retail Analysis w programie Power BI Desktop. 
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-desktop.png)   

2.  [Dodaj nową stronę](../power-bi-report-add-page.md), wybierając żółtą ikonę ze znakiem plus w dolnej części obszaru roboczego.

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Dodawanie wizualizacji z porównaniem sprzedaży z bieżącego roku i z ostatniego roku
1. Z tabeli **Sales** (Sprzedaż) wybierz pozycje **This Year Sales** > **Value** (Sprzedaż z bieżącego roku > Wartość) i **Last Year Sales** (Sprzedaż z ostatniego roku). Usługa Power BI utworzy wykres kolumnowy.  Okazuje się to być całkiem interesujące, więc warto dokonać szczegółowej analizy. Jakie są wyniki sprzedaży w poszczególnych miesiącach?  
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-barchart.png)
2. Z tabeli Time (Czas) przeciągnij pozycję **FiscalMonth** (Miesiąc obrachunkowy) do obszaru **Oś**.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-month.png)
3. [Zmień wizualizację](power-bi-report-change-visualization-type.md) na wykres warstwowy.  Istnieje wiele typów wizualizacji do wyboru. Jeśli potrzebujesz pomocy w zdecydowaniu, którego typu użyć, zapoznaj się z [opisem każdego z nich, wskazówkami dotyczącymi najlepszych rozwiązań i samouczkami](power-bi-visualization-types-for-reports-and-q-and-a.md). W okienku Wizualizacje wybierz ikonę Wykres warstwowy ![](media/power-bi-report-add-visualizations-ii/power-bi-areachart.png).
4. Posortuj wizualizację, wybierając wielokropek i pozycję **Sortuj według: FiscalMonth (Miesiąc obrachunkowy)**.
5. [Zmień rozmiar wizualizacji](power-bi-visualization-move-and-resize.md), wybierając wizualizację, chwytając jeden z okręgów konturu i przeciągając do nowej pozycji. Rozszerz ją do takich rozmiarów, aby nie wyświetlał się już pasek przewijania, ale aby pozostało dość miejsca na dodanie kolejnej wizualizacji.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Zapisz raport](../service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Dodawanie wizualizacji mapy z porównaniem sprzedaży według lokalizacji
1. Z tabeli **Store** (Sklep) wybierz pozycję **Territory** (Terytorium). Usługa Power BI rozpozna, że terytorium to lokalizacja, i utworzy wizualizację mapy.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map.png)
2. Przeciągnij pozycję **Total Stores** (Łączna liczba sklepów) do obszaru Rozmiar.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map2.png)
3. Dodaj legendę.  Aby wyświetlić dane według nazw sklepów, przeciągnij pozycję **Chain** (Sieć) do obszaru Legenda.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-legend.png)

## <a name="next-steps"></a>Następne kroki
* Więcej informacji o [wizualizacjach w raportach usługi Power BI](power-bi-report-visualizations.md).  
* Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

