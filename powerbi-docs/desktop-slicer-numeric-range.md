---
title: Używanie fragmentatora zakresu liczbowego w programie Power BI Desktop
description: Dowiedz się, jak za pomocą fragmentatora ograniczać zakresy liczbowe w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1e380a6821db7207d14e719fa5e070af38196b97
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34286939"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Używanie fragmentatora zakresu liczbowego w programie Power BI Desktop
Używając **fragmentatora zakresu liczbowego**, możesz zastosować wszelkiego rodzaju filtry do dowolnej kolumny liczbowej w modelu danych. Możesz filtrować liczby **między** wartościami, **mniejsze niż lub równe** określonej liczbie albo **większe niż lub równe** określonej liczbie. Chociaż może to brzmieć prosto, jest to bardzo zaawansowana metoda filtrowania danych.

![Wizualizacja z fragmentatorem zakresu liczbowego](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="using-the-numeric-range-slicer"></a>Używanie fragmentatora zakresu liczbowego
Fragmentatora zakresu liczbowego możesz używać podobnie jak każdego innego fragmentatora. Po prostu utwórz wizualizację **fragmentatora** dla raportu, a następnie dla wartości **Pole** wybierz wartość liczbową. Na poniższej ilustracji jest zaznaczone pole *LineTotal*.

![Tworzenie fragmentatora zakresu liczbowego](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

Wybierz strzałkę w dół w prawym górnym rogu **fragmentatora zakresu liczbowego**, aby wyświetlić menu.

![Menu fragmentatora zakresu liczbowego](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

W przypadku zakresu liczbowego możesz wybrać jedną z następujących trzech opcji:

* Między
* Mniejsze niż lub równe
* Większe niż lub równe

Gdy wybierzesz z menu pozycję **Między**, zostanie wyświetlony suwak i będzie można filtrować wartości liczbowe mieszczące się między liczbami. Zamiast używać paska suwaka, możesz kliknąć jedno z pól i wpisać wartość. Jest to wygodne, gdy chcesz utworzyć wycinek między określonymi liczbami, ale stopień szczegółowości przesunięcia paska fragmentatora utrudnia trafienie dokładnie w tę liczbę.

Na poniższej ilustracji strona raportu jest filtrowana według wartości *LineTotal* mieszczących się w zakresie od 2500,00 do 6000,00.

![Fragmentator zakresu liczbowego z użyciem opcji Między](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

Gdy wybierzemy pozycję **Mniejsze niż lub równe**, zniknie lewy uchwyt (dolna wartość) paska suwaka i będziemy mogli dostosować tylko górną granicę paska suwaka. Na poniższej ilustracji ustawiliśmy górną granicę paska suwaka na 5928,19.

![Fragmentator zakresu liczbowego z użyciem opcji Mniejsze niż](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

Natomiast gdy wybierzemy pozycję **Większe niż lub równe**, zniknie prawy uchwyt paska suwaka (górna wartość) i będziemy mogli dostosować dolną wartość, jak widać na poniższej ilustracji. Teraz w wizualizacjach na stronie raportu są wyświetlane tylko elementy, których wartość *LineTotal* jest większa niż 4902,99 lub równa tej liczbie.

![Fragmentator zakresu liczbowego z użyciem opcji Większe niż](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>Przyciąganie do liczb całkowitych przy użyciu fragmentatora zakresu liczbowego

Fragmentator zakresu liczbowego ma funkcję przyciągania do liczb całkowitych, o ile nie ma zakresu dziesiętnego. Pozwala to fragmentatorowi prawidłowo dopasować liczby całkowite. 


## <a name="limitations-and-considerations"></a>Ograniczenia i istotne zagadnienia
Obecnie obowiązują poniższe ograniczenia i istotne zagadnienia dotyczące **fragmentatora zakresu liczbowego**:

* **Fragmentator zakresu liczbowego** filtruje obecnie każdy wiersz podstawowy w danych, ale nie filtruje żadnej wartości zagregowanej. Jeśli na przykład jest używane pole *Kwota sprzedaży*, każda transakcja związana z polem *Kwota sprzedaży* będzie filtrowana w oparciu o to pole, a nie o sumę wartości *Kwota sprzedaży* dla każdego punktu danych wizualizacji.
* Obecnie fragmentator nie współpracuje z miarami.
