---
title: Podstawowy wykres warstwowy
description: Podstawowy wykres warstwowy.
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/27/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 09322a1ead6ae4c3a00dc42e2b4a642dcc2d6181
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34584144"
---
# <a name="basic-area-chart"></a>Podstawowy wykres warstwowy
Podstawowy wykres warstwowy (zwany również wykresem warstwowym) jest oparty na wykresie liniowym. Obszar pomiędzy osią i linią jest wypełniony kolorami wskazującymi ilość. 

Wykresy warstwowe podkreślają znaczenie zmiany w czasie. Można ich używać do zwracania uwagi na wartość całkowitą w trendzie. Na przykład dane reprezentujące zysk w czasie można przedstawić na wykresie warstwowym, aby podkreślić łączny zysk.

![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)

## <a name="when-to-use-a-basic-area-chart"></a>Kiedy należy używać podstawowego wykresu warstwowego
Podstawowe wykresy warstwowe są doskonałym wyborem:

* W przypadku wyświetlania i porównywania trendu ilościowego w serii czasu. 
* W przypadku poszczególnych serii przedstawiających fizycznie zliczany zestaw.

### <a name="prerequisites"></a>Wymagania wstępne
 - Usługa Power BI
 - Przykład Retail Analysis

Aby móc wykonać te instrukcje, zaloguj się w usłudze Power BI, wybierz pozycję **Pobierz dane \> Przykłady \> Przykład Retail Analysis > Połącz**, a następnie wybierz pozycję **Przejdź do pulpitu nawigacyjnego**. 

## <a name="create-a-basic-area-chart"></a>Tworzenie podstawowego wykresu warstwowego
 

1. Na pulpicie nawigacyjnym „Przykład analizy detalicznej” wybierz kafelek **Magazyny razem**, aby otworzyć raport „Przykład analizy detalicznej”.
2. Wybierz pozycję **Edytuj raport**, aby otworzyć raport w widoku do edycji.
3. Dodaj nową stronę raportu, wybierając żółtą ikonę ze znakiem plus (+) w dolnej części raportu.
4. Utwórz wykres warstwowy wyświetlający sprzedaż w tym roku i sprzedaż w zeszłym roku według miesięcy.
   
   a. W okienku POLA wybierz pozycję **Sales \> Last Year Sales** oraz **This Year Sales > Value**.

   ![](media/power-bi-visualization-basic-area-chart/power-bi-bar-chart.png)

   b.  Przekonwertuj wykres na podstawowy wykres warstwowy, wybierając ikonę wykresu warstwowego w okienku WIZUALIZACJE.

   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  Wybierz pozycje **Czas\> Miesiąc**, aby ją dodać do źródła **Oś**.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Aby wyświetlić wykres według miesięcy, wybierz wielokropek (prawy górny róg wizualizacji) i wybierz pozycję **Sortuj według miesięcy**.

## <a name="highlighting-and-cross-filtering"></a>Wyróżnianie i filtrowanie krzyżowe
Aby uzyskać informacje o korzystaniu z okienka FILTRY, zobacz [Dodawanie filtru do raportu](power-bi-report-add-filter.md).

Aby wyróżnić jeden określony obszar swojego wykresu, zaznacz ten obszar lub jego górną krawędź.  W odróżnieniu od innych typów wizualizacji, jeśli na tej samej stronie istnieją inne wizualizacje, wyróżnienie podstawowego wykresu warstwowego nie powoduje filtrowania krzyżowego innych wizualizacji na stronie raportu. Jednak wykresy warstwowe są celem filtrowania krzyżowego wyzwalanego przez inne wizualizacje na stronie raportu. Aby dowiedzieć się więcej, zobacz [Interakcje wizualne w raportach](service-reports-visual-interactions.md)


## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów   
* [Zwiększanie dostępności raportu dla osób niepełnosprawnych](desktop-accessibility.md)
* Podstawowe wykresy warstwowe nie są efektywne w przypadku porównywania wartości ze względu na zamknięcia w obszarach warstwowych. Usługa Power BI używa przezroczystości, aby wskazywać obszary nachodzące na siebie. Jednak działa to dobrze tylko w przypadku dwóch lub trzech różnych obszarów. Jeśli chcesz porównać trend składający się z ponad trzech miar, spróbuj użyć wykresów liniowych. Jeśli chcesz porównać ilość wobec więcej niż trzech miar, spróbuj użyć mapy drzewa.

## <a name="next-steps"></a>Następne kroki
[Raporty w usłudze Power BI](service-reports.md)  
[Wizualizacje w raportach usługi Power BI](power-bi-report-visualizations.md)  
[Power BI — podstawowe pojęcia](service-basic-concepts.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

