---
title: Podstawowy wykres warstwowy (samouczek)
description: 'Samouczek: podstawowy wykres warstwowy.'
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
ms.openlocfilehash: 42e068b11c22c32f1a6736a6ca8f9020594fb40a
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="basic-area-chart-tutorial"></a>Podstawowy wykres warstwowy (samouczek)
Podstawowy wykres warstwowy (zwany również wykresem warstwowym) jest oparty na wykresie liniowym. Obszar pomiędzy osią i linią jest wypełniony kolorami wskazującymi ilość. 

Wykresy warstwowe podkreślają znaczenie zmiany w czasie. Można ich używać do zwracania uwagi na wartość całkowitą w trendzie. Na przykład dane reprezentujące zysk w czasie można przedstawić na wykresie warstwowym, aby podkreślić łączny zysk.

![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)

## <a name="when-to-use-a-basic-area-chart"></a>Kiedy należy używać podstawowego wykresu warstwowego
Podstawowe wykresy warstwowe są doskonałym wyborem:

* W przypadku wyświetlania i porównywania trendu ilościowego w serii czasu. 
* W przypadku poszczególnych serii przedstawiających fizycznie zliczany zestaw.

## <a name="create-a-basic-area-chart"></a>Tworzenie podstawowego wykresu warstwowego
Aby móc wykonywać te instrukcje, zaloguj się w usłudze Power BI, a następnie wybierz pozycję **Pobierz dane \> Przykłady \> Retail Analysis Sample**. 

1. Na pulpicie nawigacyjnym „Przykład analizy detalicznej” wybierz kafelek **Magazyny razem**, aby otworzyć raport „Przykład analizy detalicznej”.
2. Wybierz pozycję **Edytuj raport**, aby otworzyć raport w widoku do edycji.
3. Dodaj nową stronę raportu.
4. Utwórz wykres warstwowy wyświetlający sprzedaż w tym roku i sprzedaż w zeszłym roku według miesięcy.
   
   a.  W okienku **Pola** wybierz pozycję **Sales \> Last Year Sales** oraz **This Year Sales > Wartość**.
   
   b.  Skonwertuj wykres na podstawowy wykres warstwowy.    
   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  Wybierz pozycje **Czas\> Miesiąc**, aby ją dodać do źródła **Oś**.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Aby wyświetlić wykres według miesięcy, wybierz wielokropek (prawy górny róg wizualizacji) i wybierz pozycję **Sortuj według miesięcy**.

## <a name="highlighting-and-cross-filtering"></a>Wyróżnianie i filtrowanie krzyżowe
Aby uzyskać informacje o korzystaniu z okienka filtrów, zobacz [Dodawanie filtru do raportu](power-bi-report-add-filter.md).

Aby wybrać obszar, kliknij wewnątrz tego obszaru lub wzdłuż górnej linii.  Podstawowe wykresy warstwowe nie filtrują krzyżowo innych wizualizacji na stronie raportu. Jednak wykresy warstwowe są celem filtrowania krzyżowego wyzwalanego przez inne wizualizacje na stronie raportu.

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów
* Podstawowe wykresy warstwowe nie są efektywne w przypadku porównywania wartości ze względu na zamknięcia w obszarach warstwowych. Usługa Power BI używa przezroczystości, aby wskazywać obszary nachodzące na siebie. Jednak działa to dobrze tylko w przypadku dwóch lub trzech różnych obszarów. Jeśli chcesz porównać trend składający się z ponad trzech miar, spróbuj użyć wykresów liniowych. Jeśli chcesz porównać ilość wobec więcej niż trzech miar, spróbuj użyć mapy drzewa.

## <a name="next-steps"></a>Następne kroki
[Raporty w usłudze Power BI](service-reports.md)  
[Wizualizacje w raportach usługi Power BI](power-bi-report-visualizations.md)  
[Power BI — podstawowe pojęcia](service-basic-concepts.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

