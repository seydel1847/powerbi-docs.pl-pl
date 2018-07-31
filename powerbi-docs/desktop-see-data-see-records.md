---
title: Wyświetlanie danych i rekordów za pomocą wizualizacji programu Power BI Desktop
description: Funkcje Pokaż dane i Pokaż rekordy programu Power BI Desktop umożliwiają przechodzenie do szczegółów
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: b635f464126addaf952adf5d8af1d0407899c0b9
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39328066"
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Używanie funkcji Pokaż dane i Pokaż rekordy w programie Power BI Desktop
W programie **Power BI Desktop** możliwe jest przejście do szczegółów wizualizacji i wyświetlenie tekstowej reprezentacji odpowiednich danych lub poszczególnych rekordów danych dla wybranej wizualizacji. Te funkcje są czasami określane jako *kliknięcie*, *przejście* lub *przejście do szczegółów*.

Można użyć funkcji **Pokaż dane**, aby wyświetlić tekstową wersję wartości użytych w wybranej wizualizacji, lub funkcji **Pokaż rekordy**, aby wyświetlić wszystkie dane jednego wybranego rekordu lub punktu danych. 

![Pokaż dane i Pokaż rekordy](media/desktop-see-data-see-records/see-data-record.png)

>[!IMPORTANT]
>Funkcje **Pokaż dane** i **Pokaż rekordy** obsługują tylko następujące typy wizualizacji:
>  - Wykres słupkowy
>  - Wykres kolumnowy
>  - Wykres pierścieniowy
>  - Kartogram
>  - Lejek
>  - Mapa
>  - Wykres kołowy
>  - Mapa drzewa

## <a name="use-see-data-in-power-bi-desktop"></a>Używanie funkcji Pokaż dane w programie Power BI Desktop

Funkcja **Pokaż dane** powoduje wyświetlenie podstawowych danych wizualizacji. Pozycja **Pokaż dane** pojawia się na karcie **Dane/przechodzenie do szczegółów** w sekcji **Narzędzia wizualne** wstążki po wybraniu wizualizacji.

![Pozycja Pokaż dane na wstążce](media/desktop-see-data-see-records/see-data1.png)

Dane można również wyświetlić, klikając wizualizację prawym przyciskiem myszy, a następnie wybierając pozycję **Pokaż dane** w wyświetlonym menu; lub wybierając ikonę wielokropka (...) **Więcej opcji** w prawym górnym rogu wizualizacji, a następnie wybierając pozycję **Pokaż dane**.

![Kliknięcie pozycji Pokaż dane prawym przyciskiem myszy](media/desktop-see-data-see-records/see-data2.png)&nbsp;&nbsp;![Pokaż dane — Więcej opcji](media/desktop-see-data-see-records/see-data3.png)

> [!NOTE]
> Kursor myszy musi być umieszczony nad punktem danych w wizualizacji, aby menu kontekstowe było dostępne.

Po wybraniu pozycji **Pokaż dane** lub **Zobacz dane** na kanwie programu Power BI Desktop zostanie wyświetlona wizualna i tekstowa reprezentacja danych. W *widoku poziomym* wizualizacja jest wyświetlana w górnej połowie kanwy, a dane w dolnej. 

![widok poziomy](media/desktop-see-data-see-records/see-data4a.png)

Można również przełączać się między widokiem poziomym i *widokiem pionowym*, wybierając ikonę w prawym górnym rogu kanwy.

![przełącznik widoku pionowego](media/desktop-see-data-see-records/see-data4.png)

Aby wrócić do raportu, wybierz pozycję **< Wróć do raportu** w lewym górnym rogu kanwy.

![Wróć do raportu](media/desktop-see-data-see-records/see-data5.png)

## <a name="use-see-records-in-power-bi-desktop"></a>Używanie funkcji Pokaż rekordy w programie Power BI Desktop

Istnieje również możliwość skoncentrowania uwagi na pojedynczym rekordzie danych w wizualizacji, a następnie przejście do związanych z nim danych. Aby skorzystać z funkcji **Pokaż rekordy**, wybierz wizualizację, a następnie wybierz pozycję **Pokaż rekordy** na karcie **Dane/przechodzenie do szczegółów** w sekcji **Narzędzia wizualne** na wstążce, a następnie wybierz punkt danych lub wiersz w wizualizacji. 

![Pozycja Pokaż rekordy na wstążce](media/desktop-see-data-see-records/see-record1.png)

> [!NOTE]
> Jeśli przycisk **Pokaż rekordy** na wstążce jest wyłączony i nieaktywny, oznacza to, że wybrana wizualizacja nie obsługuje funkcji **Pokaż rekordy**.

Możesz również kliknąć prawym przyciskiem myszy element danych i wybrać polecenie **Pokaż rekordy** w wyświetlonym menu.

![Pozycja Pokaż rekordy wyświetlana po kliknięciu prawym przyciskiem myszy](media/desktop-see-data-see-records/see-record2.png)

Po wybraniu pozycji **Pokaż rekordy** dla elementu danych na kanwie programu Power BI Desktop zostaną wyświetlone wszystkie dane skojarzone z wybranym elementem. 

![](media/desktop-see-data-see-records/see-record3.png)

Aby wrócić do raportu, wybierz pozycję **< Wróć do raportu** w lewym górnym rogu kanwy.

![](media/desktop-see-data-see-records/see-record4.png)

> [!NOTE]
>Funkcja **Pokaż rekordy** ma następujące ograniczenia:
> - Nie można zmienić danych w widoku **Pokaż rekordy** ani zapisać ich ponownie w raporcie.
> - Nie można użyć funkcji **Pokaż rekordy**, jeśli wizualizacja używa miary obliczanej.
> - Nie można użyć funkcji **Pokaż rekordy**, jeśli nawiązano połączenie z wielowymiarowym modelem na żywo.

## <a name="next-steps"></a>Następne kroki
W programie **Power BI Desktop** istnieją różne rodzaje funkcji służących do formatowania raportu i zarządzania danymi. Skorzystaj z następujących zasobów, aby uzyskać kilka przykładów:

* [Używanie grupowania i kwantowania w programie Power BI Desktop](desktop-grouping-and-binning.md)
* [Używanie linii siatki, przyciągania do siatki, kolejności na osi Z, wyrównania i dystrybucji w raportach programu Power BI Desktop](desktop-gridlines-snap-to-grid.md)

