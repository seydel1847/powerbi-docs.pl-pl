---
title: "Wyświetlanie danych i rekordów za pomocą wizualizacji programu Power BI Desktop"
description: "Funkcje Pokaż dane i Pokaż rekordy programu Power BI Desktop umożliwiają przechodzenie do szczegółów"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 02/22/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: c44a5140fe40217aac170abb0b351197803b6299
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Używanie funkcji Pokaż dane i Pokaż rekordy w programie Power BI Desktop
W programie **Power BI Desktop** możliwe jest przejście do szczegółów dowolnej wizualizacji i wyświetlenie tekstowej reprezentacji danych lub poszczególnych elementów danych dla wybranej wizualizacji. Te funkcje są czasami określane jako *kliknięcie*, *przejście* lub *przejście do szczegółów*.

Funkcji **Pokaż rekordy** można użyć, aby wyświetlić źródłowe wiersze dla jednego wybranego elementu danych z poziomu wizualizacji. Użycie funkcji **Pokaż dane** umożliwia natomiast wyświetlenie tekstowej wersji wartości użytych w wizualizacji. Istnieją pewne ograniczenia związane z używaniem funkcji **Pokaż dane** i **Pokaż rekordy** — zostały one omówione na końcu tego artykułu.

![](media/desktop-see-data-see-records/see-data-see-records_1.png)

## <a name="using-see-data-in-power-bi-desktop"></a>Używanie funkcji Pokaż dane w programie Power BI Desktop
Przycisk **Pokaż dane** znajduje na karcie **Dane/przejście** w sekcji **Narzędzia wizualne** wstążki.

![](media/desktop-see-data-see-records/see-data-see-records_2.png)

Funkcję **Pokaż dane** można również użyć, klikając prawym przyciskiem myszy wizualizację, a następnie wybierając pozycję **Pokaż dane** z wyświetlonego menu.

![](media/desktop-see-data-see-records/see-data-see-records_3.png)

> [!NOTE]
> Kursor myszy musi być umieszczony nad punktem danych w ramach wizualizacji, aby menu kontekstowe było dostępne.
> 
> 

Po wybraniu pozycji **Pokaż dane** program **Power BI Desktop** ustawia fokus na wybranej wizualizacji oraz wybranych danych i przeznacza obszar kanwy na wyświetlenie wizualnej oraz tekstowej reprezentacji danych. Wizualizacja jest wyświetlana w górnej połowie kanwy, a dane w dolnej, co przedstawiono na poniższym obrazie. Jest to widok *poziomy*.

![](media/desktop-see-data-see-records/see-data-see-records_4.png)

Można również przełączyć się na *widok pionowy* (lub z powrotem do *widoku poziomego*), wybierając ikonę w prawym górnym rogu.

![](media/desktop-see-data-see-records/see-data-see-records_5.png)

Aby wrócić do raportu, wybierz pozycję **< Wróć do raportu** w lewym górnym rogu kanwy.

![](media/desktop-see-data-see-records/see-data-see-records_6.png)

## <a name="using-see-records-in-power-bi-desktop"></a>Używanie funkcji Pokaż rekordy w programie Power BI Desktop
Istnieje również możliwość ustawienia fokusu na pojedynczym elemencie danych w wizualizacji, a następnie przejście do związanych z nim danych. Po wybraniu wizualizacji istnieją dwa sposoby użycia funkcji **Pokaż rekordy**: można włączyć przycisk przełącznika **Pokaż rekordy** na wstążce **Dane/przejście**, a następnie kliknąć element danych, lub kliknąć prawym przyciskiem myszy element danych, a następnie wybrać pozycję **Pokaż rekordy** z wyświetlonego menu.

![](media/desktop-see-data-see-records/see-data-see-records_7.png)

> [!NOTE]
> Jeśli wybrana wizualizacja nie obsługuje funkcji **Pokaż rekordy**, to przycisk na wstążce będzie szary.
> 
> 

Jeśli pozycja **Pokaż rekordy** jest wybrana, program **Power BI Desktop** ustawia fokus na danym elemencie danych i przeznacza obszar kanwy na wyświetlenie danych dla tego elementu, jak pokazano na poniższym obrazie.

![](media/desktop-see-data-see-records/see-data-see-records_8.png)

> [!NOTE]
> W raporcie nie można zapisać zmian danych wyświetlanych (lub modyfikowanych przez użytkowników) w widoku **Zobacz rekordy**.

Aby wrócić do raportu, wybierz przycisk **Wróć do raportu** w lewym górnym rogu kanwy.

## <a name="limitations"></a>Ograniczenia
Istnieją pewne ograniczenia, które należy wziąć pod uwagę podczas używania funkcji **Pokaż dane** lub **Pokaż rekordy**:

* Obsługiwane są tylko następujące typy wizualizacji:
  * **Słupek**
  * **Kolumna**
  * **Mapa**
  * **Mapa drzewa**
  * **Kartogram**
  * **Koło**
  * **Pierścień**
  * **Lejek**
* Nie można użyć funkcji **Pokaż rekordy**, jeśli wizualizacja używa miary obliczanej
* Nie można użyć funkcji **Pokaż rekordy**, jeśli nawiązano połączenie z wielowymiarowym modelem na żywo

## <a name="next-steps"></a>Następne kroki
W programie **Power BI Desktop** istnieją różne rodzaje funkcji służących do formatowania raportu i zarządzania danymi. Skorzystaj z następujących zasobów, aby uzyskać kilka przykładów:

* [Używanie grupowania i kwantowania w programie Power BI Desktop](desktop-grouping-and-binning.md)
* [Używanie linii siatki, przyciągania do siatki, kolejności na osi Z, wyrównania i dystrybucji w raportach programu Power BI Desktop](desktop-gridlines-snap-to-grid.md)

