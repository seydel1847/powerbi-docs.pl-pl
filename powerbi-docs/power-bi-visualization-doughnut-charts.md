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
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 2f428095eb57c5358770f1d6d8572316d2b84c37
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Wykresy pierścieniowe w usłudze Power BI (samouczek)
Wykres pierścieniowy jest podobny do wykresu kołowego, ponieważ również pokazuje zależność poszczególnych części względem całości. Jedyna różnica polega na tym, że jego środek jest pusty, dlatego możliwe jest dodanie etykiety lub ikony.

## <a name="create-a-doughnut-chart"></a>Tworzenie wykresu pierścieniowego
Aby móc wykonać te instrukcje, zaloguj się w usłudze Power BI, a następnie wybierz pozycję **Pobierz dane** \> **Przykłady** \> **Retail Analysis Sample** \> **Połącz**. 

1. Na pulpicie nawigacyjnym wybierz kafelek **Total Stores**, aby otworzyć raport „Przykład Retail Analysis”.
2. Wybierz pozycję **Edytuj raport**, aby otworzyć raport w widoku do edycji.
3. [Dodaj nową stronę raportu](power-bi-report-add-page.md).
4. Utwórz wykres pierścieniowy, który będzie wyświetlał tegoroczne dane sprzedaży według kategorii.
   
   * W okienku **Pola** wybierz pozycję **Sales** \> **Last Year Sales**.
   * Przekonwertuj na wykres pierścieniowy. Jeśli pozycja Last Year Sales nie znajduje się w obszarze **Wartości**, przeciągnij ją w to miejsce.
     
       ![](media/power-bi-visualization-doughnut-charts/convertdonut.png)
   * Wybierz pozycję **Element** \> **Kategoria**, aby dodać ją do obszaru **Legenda**. 
     
       ![](media/power-bi-visualization-doughnut-charts/doughnuttutorial.png)

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

