---
title: "Wykresy pierścieniowe w usłudze Power BI (samouczek)"
description: "Samouczek: Wykresy pierścieniowe w usłudze Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/23/2017
ms.author: mihart
ms.openlocfilehash: f3401fac7b0e7e6b5b5404a5a837822772e1d70f
ms.sourcegitcommit: 74fbbca81a056dda19b3647ae058005aba5296f5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/03/2018
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Wykresy pierścieniowe w usłudze Power BI (samouczek)
Wykres pierścieniowy jest podobny do wykresu kołowego, ponieważ również pokazuje zależność poszczególnych części względem całości. Jedyna różnica polega na tym, że jego środek jest pusty, dlatego możliwe jest dodanie etykiety lub ikony.

## <a name="create-a-doughnut-chart"></a>Tworzenie wykresu pierścieniowego
W poniższych instrukcjach użyto przykładu Retail Analysis, aby utworzyć wykres pierścieniowy przedstawiający tegoroczne dane sprzedaży według kategorii. Aby je wykonać, [pobierz przykład](sample-datasets.md) dla usługi Power BI (app.powerbi.com) lub dla programu Power BI Desktop.

1. Rozpocznij od [pustej strony raportu](power-bi-report-add-page.md) i wybierz pole **SalesStage** \> **Sales Stage**. Jeśli używasz usługi Power BI, upewnij się, że raport jest otwarty w [widoku do edycji](service-interact-with-a-report-in-editing-view.md).

2. W okienku Pola wybierz pozycję **Sales** \> **Last Year Sales**.  
   
3. W okienku Wizualizacje wybierz ikonę wykresu pierścieniowego ![Ikona wykresu pierścieniowego](), aby przekonwertować wykres słupkowy na wykres pierścieniowy. Jeśli pozycja **Last Year Sales** nie znajduje się w obszarze **Wartości**, przeciągnij ją w to miejsce.
     
   ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. Wybierz pozycję **Element** \> **Kategoria**, aby dodać ją do obszaru **Legenda**. 
     
    ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. Opcjonalnie [dostosuj rozmiar i kolor tekstu wykresu](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów
* Suma wartości wykresu pierścieniowego musi wynosić 100%.
* Zbyt wiele kategorii utrudnia odczyt i interpretację.
* Wykresy pierścieniowe najlepiej sprawdzają się w przypadku porównywania poszczególnych sekcji w odniesieniu do całości, a nie porównywania ich między sobą. 

## <a name="next-steps"></a>Następne kroki
[Raporty w usłudze Power BI](service-reports.md)

[Typy wizualizacji w usłudze Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Wizualizacje w raportach usługi Power BI](power-bi-report-visualizations.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

