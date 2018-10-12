---
title: Wykresy pierścieniowe w usłudze Power BI
description: Wykresy pierścieniowe w usłudze Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: ab292964bb1b6b1f4218d41c46eb2c28c82a034c
ms.sourcegitcommit: ce8332a71d4d205a1f005b703da4a390d79c98b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2018
ms.locfileid: "47416756"
---
# <a name="doughnut-charts-in-power-bi"></a>Wykresy pierścieniowe w usłudze Power BI
Wykres pierścieniowy jest podobny do wykresu kołowego, ponieważ również pokazuje zależność poszczególnych części względem całości. Jedyna różnica polega na tym, że jego środek jest pusty, dlatego możliwe jest dodanie etykiety lub ikony.

## <a name="create-a-doughnut-chart"></a>Tworzenie wykresu pierścieniowego
W poniższych instrukcjach użyto przykładu Retail Analysis, aby utworzyć wykres pierścieniowy przedstawiający tegoroczne dane sprzedaży według kategorii. Aby je wykonać, [pobierz przykład](../sample-datasets.md) dla usługi Power BI lub dla programu Power BI Desktop.

1. Rozpocznij na [pustej stronie raportu](../power-bi-report-add-page.md). Jeśli używasz usługi Power BI, upewnij się, że raport jest otwarty w [widoku do edycji](../service-interact-with-a-report-in-editing-view.md).

2. W okienku Pola wybierz pozycję **Sales** \> **Last Year Sales**.  
   
3. W okienku Wizualizacje wybierz ikonę wykresu pierścieniowego ![Ikona wykresu pierścieniowego](media/power-bi-visualization-doughnut-charts/power-bi-icon.png), aby przekonwertować wykres słupkowy na wykres pierścieniowy. Jeśli pozycja **Last Year Sales** nie znajduje się w obszarze **Wartości**, przeciągnij ją w to miejsce.
     
   ![Okienko Wizualizacje z wybranym wykresem pierścieniowym](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. Wybierz pozycję **Element** \> **Kategoria**, aby dodać ją do obszaru **Legenda**. 
     
    ![wykres pierścieniowy obok okienka Pola](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. Opcjonalnie [dostosuj rozmiar i kolor tekstu wykresu](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów
* Suma wartości wykresu pierścieniowego musi wynosić 100%.
* Zbyt wiele kategorii utrudnia odczyt i interpretację.
* Wykresy pierścieniowe najlepiej sprawdzają się w przypadku porównywania poszczególnych sekcji w odniesieniu do całości, a nie porównywania ich między sobą. 

## <a name="next-steps"></a>Następne kroki
[Wykresy lejkowe w usłudze Power BI](power-bi-visualization-funnel-charts.md)

[Typy wizualizacji w usłudze Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)


