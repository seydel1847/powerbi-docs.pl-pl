---
title: "Zmienianie sposobu sortowania wykresu w raporcie usługi Power BI"
description: "Zmienianie sposobu sortowania wykresu w raporcie usługi Power BI"
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
ms.date: 09/08/2017
ms.author: mihart
ms.openlocfilehash: 37161fab1e19e6ce00eb0f02c96b6e5cbdd60f18
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Zmienianie sposobu sortowania wykresu w raporcie usługi Power BI
W usłudze Power BI wykresy można sortować alfabetycznie według nazw kategorii na wykresie lub według wartości liczbowych poszczególnych kategorii. Na przykład ten wykres jest posortowany według nazw sklepów.

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

Zamiast tego można łatwo posortować go od największej do najmniejszej wartości sprzedaży na metr kwadratowy.

1. Wybierz wielokropek (...), a następnie wybierz pozycję **Sort by Sales Per Sq Ft** (Sortuj według sprzedaży na metr kw.).
2. Jeśli to konieczne, wybierz ikonę sortowania ![](media/power-bi-report-change-sort/sorticon.png), aby zmienić sposób sortowania na **Malejąco**.
   
   ![](media/power-bi-report-change-sort/sortby.gif)
   
   **UWAGA**: Nie wszystkie wizualizacje można sortować.  Nie można sortować na przykład następujących wizualizacji: Mapa drzewa, Mapa, Kartogram, Punktowy, Miernik, Karta, Karta z wieloma wierszami, Wykres kaskadowy.

## <a name="sorting-using-other-criteria"></a>Sortowanie przy użyciu innych kryteriów
Czasami może się okazać, że wizualizację trzeba posortować przy użyciu innego pola lub innych kryteriów.  Możesz na przykład chcieć posortować według miesięcy (ale nie w kolejności alfabetycznej) lub według całych liczb, a nie poszczególnych cyfr (0, 1, 9, 20 a nie 0, 1, 20, 9).  

W niektórych przypadkach może się udać posortować wizualizacje w odpowiedni sposób, na przykład według miesięcy.  Jeśli nie jest to możliwe, być może bazowy zestaw danych raportu wymaga nieco dostosowania. Poniżej przedstawiono kilka rozwiązań:

* W programie Power BI Desktop [użyj karty Modelowanie narzędzi danych, aby posortować według innej kolumny](desktop-sort-by-column.md).
* W programie Excel, jeśli jesteś właścicielem zestawu danych, dodaj nową kolumnę, która łączy nazwę miesiąca i liczbę. Następnie odśwież zestaw danych lub zaimportuj go ponownie, aby wyświetlić nową kolumnę w obszarze Pola.
* W programie Excel upewnij się, że kolumny liczbowe zostały oznaczone jako „liczba całkowita” lub „liczba dziesiętna”, a nie jako „tekst”.

## <a name="next-steps"></a>Następne kroki
Więcej informacji o [wizualizacjach w raportach usługi Power BI](power-bi-report-visualizations.md).

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

