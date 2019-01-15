---
title: Widok danych w programie Power BI Desktop
description: Widok danych w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: c8a96918049f2f1898ab80a9368a8d2f0a8fe53a
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54286142"
---
# <a name="data-view-in-power-bi-desktop"></a>Widok danych w programie Power BI Desktop
**Widok danych** ułatwia sprawdzanie, przeglądanie i interpretację danych w modelu programu **Power BI Desktop**. Sposób wyświetlania tabel, kolumn i danych jest inny niż w **Edytorze zapytań**. W widoku danych widzisz dane *po* ich załadowaniu do modelu.

Gdy modelujesz dane, czasami chcesz zobaczyć, co faktycznie znajduje się w tabeli lub kolumnie bez tworzenia wizualizacji na kanwie raportu, często aż na poziomie wiersza. Jest to szczególnie przydatne, gdy tworzysz miary i kolumny obliczeniowe albo musisz określić typ danych lub kategorię danych.

Przyjrzyjmy się bliżej niektórym elementom znajdującym się w **widoku danych**.

![Widok danych w programie Power BI Desktop](media/desktop-data-view/dataview_fullscreen.png)

1. **Ikona widoku danych** — wybierz tę ikonę, aby przejść do widoku danych.

2. **Siatka danych** — pokazuje wybraną tabelę oraz wszystkie znajdujące się w niej kolumny i wiersze. Kolumny ukryte w **widoku raportu** są wyszarzone. Klikając kolumnę prawym przyciskiem myszy, możesz uzyskać opcje.

3. **Wstążka modelowania** — w tym miejscu możesz zarządzać relacjami, tworzyć obliczenia, zmieniać typ danych, format i kategorię danych dla kolumny.

4. **Pasek formuły** — wprowadzaj formuły języka DAX dla miar i kolumn obliczeniowych.

5. **Wyszukiwanie** — wyszukaj tabelę lub kolumnę w modelu.

6. **Lista pól** — wybierz tabelę lub kolumnę do wyświetlenia w siatce danych.

## <a name="filtering-in-data-view"></a>Filtrowanie w widoku danych

Możesz również filtrować i sortować dane w **widoku danych**. Każda kolumna zawiera ikonę, która identyfikuje kierunek sortowania (jeśli je zastosowano).

![Sortowanie i filtrowanie w widoku danych w programie Power BI Desktop](media/desktop-data-view/dataview_sort-and-filter.png)

Możesz filtrować poszczególne wartości lub używać filtrowania zaawansowanego opartego na danych w kolumnie. 

> [!NOTE]
> Gdy model usługi Power BI zostanie utworzony w innej kulturze niż Twój bieżący interfejs użytkownika, na przykład model został utworzony w kulturze Angielski (amerykański), a wyświetlasz go w kulturze Hiszpański, pole wyszukiwania nie będzie wyświetlane w interfejsie użytkownika widoku danych dla żadnych innych elementów niż pola tekstowe.
