---
title: Zmienianie sposobu sortowania wykresu w raporcie
description: Zmienianie sposobu sortowania wykresu w raporcie usługi Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: Conceptual
ms.date: 01/17/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: e648257ecd657b07d02fbff69a3424159b636059
ms.sourcegitcommit: ccbe76a0a43c5c5e87354a33e617bf3cb291608e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/18/2019
ms.locfileid: "54394685"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Zmienianie sposobu sortowania wykresu w raporcie usługi Power BI
W raporcie usługi Power BI większość wizualizacji można sortować alfabetycznie według nazw kategorii na wykresie lub według wartości liczbowych poszczególnych kategorii. Na przykład ten wykres jest posortowany według kategorii **nazwa sklepów**.

![wykres słupkowy alfa posortowany według osi X](media/end-user-change-sort/pbi_chartsortcategory.png)

W zamian można prosto zmienić sortowanie z kategorii (nazwa sklepu) na wartość (sprzedaż na metr kw.).

1. Wybierz wielokropek (...), a następnie wybierz pozycję **Sort by > Sales Per Sq Ft** (Sortuj według > Sprzedaż na metr kw.).
2. Jeśli to konieczne, ponownie wybierz wielokropek i wybierz pozycję **Sortuj malejąco**.

   ![wideo przedstawiające wybieranie opcji sortowania według, a następnie wartości rosnąco lub malejąco](media/end-user-change-sort/sort.gif)

   **UWAGA**: Nie wszystkie wizualizacje można sortować.  Na przykład nie można sortować następujących wizualizacji: mapa drzewa, mapa, kartogram, wykres punktowy, miernik, karta, karta z wieloma wierszami, wykres kaskadowy.

## <a name="saving-changes-you-make-to-sort-order"></a>Zapisywanie zmian kolejności sortowania
Raporty usługi Power BI zachowują filtry, fragmentatory, sortowanie i inne wprowadzone zmiany widoku danych. Dlatego w przypadku opuszczenia raportu i późniejszego powrotu do niego zmiany są zachowywane.  Aby cofnąć swoje zmiany i przywrócić ustawienia projektanta raportu, wybierz pozycję **Przywróć domyślne** z górnego paska menu. 

![trwałe sortowanie](media/end-user-change-sort/power-bi-reset-to-default.png)

Jeśli jednak przycisk **Przywróć domyślne** jest wyszarzony, oznacza to, że projektant raportu wyłączył możliwość zapisywania (utrwalania) zmian.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Sortowanie przy użyciu innych kryteriów
Czasami może się okazać, że wizualizację trzeba posortować przy użyciu innego pola lub innych kryteriów.  Możesz na przykład chcieć posortować według miesięcy (ale nie w kolejności alfabetycznej) lub według całych liczb, a nie poszczególnych cyfr (0, 1, 9, 20 a nie 0, 1, 20, 9).  

W niektórych przypadkach może się udać posortować wizualizacje w odpowiedni sposób, na przykład według miesięcy.  Jeśli nie jest to możliwe, być może bazowy zestaw danych raportu wymaga nieco dostosowania. Poproś projektanta raportu o zaktualizowanie zestawu danych.

## <a name="next-steps"></a>Następne kroki
Więcej informacji o [wizualizacjach w raportach usługi Power BI](end-user-visualizations.md).

[Power BI — podstawowe pojęcia](end-user-basic-concepts.md)