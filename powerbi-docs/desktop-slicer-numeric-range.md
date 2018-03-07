---
title: "Używanie fragmentatora zakresu liczbowego w programie Power BI Desktop"
description: "Dowiedz się, jak za pomocą fragmentatora ograniczać zakresy liczbowe w programie Power BI Desktop"
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
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f6e0433e8862e2acb6f0e7a72a1293e37f2185eb
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Używanie fragmentatora zakresu liczbowego w programie Power BI Desktop
Używając **fragmentatora zakresu liczbowego**, możesz zastosować wszelkiego rodzaju filtry do dowolnej kolumny liczbowej w modelu danych. Możesz filtrować liczby **między** wartościami, **mniejsze niż lub równe** określonej liczbie albo **większe niż lub równe** określonej liczbie. Chociaż może to brzmieć prosto, jest to bardzo zaawansowana metoda filtrowania danych.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_2.png)

## <a name="using-the-numeric-range-slicer"></a>Używanie fragmentatora zakresu liczbowego
Fragmentatora zakresu liczbowego możesz używać podobnie jak każdego innego fragmentatora. Po prostu utwórz wizualizację **fragmentatora** dla raportu, a następnie dla wartości **Pole** wybierz wartość liczbową. Na poniższej ilustracji jest zaznaczone pole *UnitPrice*.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_3.png)

Wybierz strzałkę w prawym górnym rogu **fragmentatora zakresu liczbowego**, aby wyświetlić menu.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_4.png)

W przypadku zakresu liczbowego możesz wybrać jedną z następujących trzech opcji:

* Między
* Mniejsze niż lub równe
* Większe niż lub równe

Gdy wybierzesz z menu pozycję **Między**, zostanie wyświetlony suwak i będzie można filtrować wartości liczbowe mieszczące się między liczbami. Zamiast używać paska suwaka, możesz kliknąć jedno z pól i wpisać wartość. Jest to wygodne, gdy chcesz utworzyć wycinek między określonymi liczbami całkowitymi, ale stopień szczegółowości przesunięcia paska fragmentatora utrudnia trafienie dokładnie w tę liczbę.

Na poniższej ilustracji strona raportu jest filtrowana według wartości *UnitPrice* mieszczących się w zakresie od 500 do 1500.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_5.png)

Gdy wybierzemy pozycję **Mniejsze niż lub równe**, zniknie lewy uchwyt (dolna wartość) paska suwaka i będziemy mogli dostosować tylko górną granicę paska suwaka. Na poniższej ilustracji ustawiliśmy suwak na 497,17.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_6.png)

Natomiast gdy wybierzemy pozycję **Większe niż lub równe**, zniknie prawy uchwyt paska suwaka (górna wartość) i będziemy mogli dostosować dolną wartość, jak widać na poniższej ilustracji. Teraz w wizualizacjach na stronie raportu są wyświetlane tylko elementy, których wartość *UnitPrice* jest większa niż 750,56 lub równa tej liczbie.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_7.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer-preview"></a>Przyciąganie do liczb całkowitych przy użyciu fragmentatora zakresu liczbowego (wersja zapoznawcza)

W wersji programu **Power BI Desktop** z lutego 2018 r. fragmentator zakresu liczbowego będzie przyciągać do liczb całkowitych. Pozwala to fragmentatorowi prawidłowo dopasować liczby całkowite. Przyciąganie do liczb całkowitych nie dotyczy filtrów dziesiętnych.


## <a name="limitations-and-considerations"></a>Ograniczenia i istotne zagadnienia
Obecnie obowiązują poniższe ograniczenia i istotne zagadnienia dotyczące **fragmentatora zakresu liczbowego**.

* **Fragmentator zakresu liczbowego** filtruje obecnie każdy wiersz podstawowy w danych, ale nie filtruje żadnej wartości zagregowanej. Jeśli na przykład jest używane pole *Kwota sprzedaży*, każda transakcja związana z polem *Kwota sprzedaży* będzie filtrowana w oparciu o to pole, a nie o sumę wartości *Kwota sprzedaży* dla każdego punktu danych wizualizacji.
* Obecnie fragmentator nie współpracuje z miarami.
* Obecnie **fragmentator zakresu liczbowego** jest dostępny tylko w programie **Power BI Desktop**. Jeśli raport korzystający z **fragmentatora zakresu liczbowego** zostanie opublikowany w **usłudze Power BI**, filtr nadal będzie stosowany, ale będzie wyświetlany jako fragmentator listy.

