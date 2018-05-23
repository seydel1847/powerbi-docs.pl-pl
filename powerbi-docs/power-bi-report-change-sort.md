---
title: Zmienianie sposobu sortowania wykresu w raporcie usługi Power BI
description: Zmienianie sposobu sortowania wykresu w raporcie usługi Power BI
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 6b70a9ef7774d1ba49bc5bf825a5c1cde47197f2
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Zmienianie sposobu sortowania wykresu w raporcie usługi Power BI
W raporcie usługi Power BI większość wizualizacji można sortować alfabetycznie według nazw kategorii na wykresie lub według wartości liczbowych poszczególnych kategorii. Na przykład ten wykres jest posortowany według nazw sklepów.

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

W zamian można prosto zmienić sortowanie z kategorii (nazwa sklepu) na wartość (sprzedaż na metr kw.).

1. Wybierz wielokropek (...), a następnie wybierz pozycję **Sort by Sales Per Sq Ft** (Sortuj według sprzedaży na metr kw.).
2. Jeśli to konieczne, wybierz ikonę sortowania ![](media/power-bi-report-change-sort/sorticon.png), aby zmienić sposób sortowania na **Malejąco**.

   ![](media/power-bi-report-change-sort/sortby.gif)

   **UWAGA**: Nie wszystkie wizualizacje można sortować.  Nie można sortować na przykład następujących wizualizacji: Mapa drzewa, Mapa, Kartogram, Punktowy, Miernik, Karta, Karta z wieloma wierszami, Wykres kaskadowy.

<a name="other"></a>
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
