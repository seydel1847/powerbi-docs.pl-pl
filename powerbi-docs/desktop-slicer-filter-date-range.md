---
title: "Używanie fragmentatora lub filtru dat względnych w programie Power BI Desktop"
description: "Dowiedz się, jak za pomocą fragmentatora lub filtru ograniczać zakresy dat względnych w programie Power BI Desktop"
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
ms.date: 07/20/2017
ms.author: davidi
ms.openlocfilehash: f3138e45386c07e20342b495938ea84022c072c2
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi-desktop"></a>Używanie fragmentatora i filtru dat względnych w programie Power BI Desktop
Używając **fragmentatora dat względnych** lub **filtru dat względnych**, możesz stosować filtry oparte na czasie do dowolnej kolumny daty w modelu danych. Na przykład przy użyciu **fragmentatora dat względnych** możesz wyświetlić tylko dane sprzedaży, która miała miejsce w ciągu ostatnich 30 dni (lub miesiąca, miesięcy kalendarzowych itd). Podczas odświeżania danych okres względny automatycznie zastosuje odpowiednie ograniczenie dat względnych.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_01.png)

## <a name="using-the-relative-date-range-slicer"></a>Używanie fragmentatora zakresów dat względnych
Fragmentatora dat względnych możesz używać podobnie jak każdego innego fragmentatora. Po prostu utwórz wizualizację **fragmentatora** dla raportu, a następnie dla wartości **Pole** wybierz wartość daty. Na poniższej ilustracji jest zaznaczone pole *OrderDate*.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_02.png)

Wybierz strzałkę w prawym górnym rogu **fragmentatora dat względnych**, aby wyświetlić menu.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_03.png)

W przypadku fragmentatora dat względnych wybierz pozycję *Względne*.

Następnie możesz wybrać ustawienia. Z pierwszej listy rozwijanej w oknie *fragmentatora dat względnych* możesz wybrać jedną z następujących opcji:

* Ostatnie
* Następne
* Te

Te opcje pokazano na poniższej ilustracji.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_04.png)

Następne (środkowe) ustawienie w oknie *fragmentatora dat względnych* umożliwia wpisanie liczby w celu zdefiniowania zakresu dat względnych.

Trzecie ustawienie umożliwia wybranie pomiaru dat. Możesz wybrać jedną z następujących opcji:

* Dni
* Tygodnie
* Tygodnie (kalendarzowe)
* Miesiące
* Miesiące (kalendarzowe)
* Lata
* Lata (kalendarzowe)

Te opcje pokazano na poniższej ilustracji.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_05.png)

Załóżmy, że wybierzesz z listy pozycję *Miesiące* i w środkowym ustawieniu wprowadzisz wartość 2. Będzie to miało następujący skutek: jeśli bieżąca data to 20 lipca, w wizualizacjach ograniczonych przez fragmentator będą wyświetlane dane z ostatnich dwóch miesięcy, począwszy od 20 maja i skończywszy na 20 lipca (bieżąca data).

Dla porównania, jeśli wybierzesz pozycję *Miesiące (kalendarzowe)*, w ograniczonych wizualizacjach będą wyświetlane dane od 1 maja do 30 czerwca (ostatnie dwa pełne miesiące kalendarzowe).

## <a name="using-the-relative-date-range-filter"></a>Używanie filtru zakresów dat względnych
Filtr zakresów dat względnych możesz również utworzyć dla strony raportu lub całego raportu. Aby to zrobić, po prostu przeciągnij pole daty do obszaru **Filtry na poziomie strony** lub **Filtry na poziomie raportu** w okienku **Pole**, jak pokazano na poniższej ilustracji.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_06.png)

W tym miejscu możesz zmodyfikować zakres dat względnych podobnie jak w przypadku dostosowywania **fragmentatora dat względnych**. Wybierz pozycję **Filtrowanie dat względnych** z listy rozwijanej **Typ filtru**.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_07.png)

Po wybraniu pozycji **Filtrowanie dat względnych** zostaną wyświetlone trzy sekcje, które można zmodyfikować, w tym środkowe pole liczbowe, podobnie jak w przypadku fragmentatora.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_08.png)

I to tyle na temat stosowania ograniczeń dat względnych w raportach.

## <a name="limitations-and-considerations"></a>Ograniczenia i istotne zagadnienia
Obecnie obowiązują poniższe ograniczenia i istotne zagadnienia dotyczące **fragmentatora i filtru zakresów dat względnych**.

* Modele danych w usłudze **Power BI** nie zawierają informacji o strefie czasowej. Modele mogą przechowywać czas, ale bez informacji o odpowiednich strefach czasowych.
* Fragmentator i filtr zawsze bazują na czasie w formacie UTC, dlatego jeśli skonfigurujesz filtr w raporcie i wyślesz go do współpracownika w innej strefie czasowej, będą wyświetlane te same dane. Jednak jeśli nie jesteś w strefie czasowej UTC, możesz zobaczyć dane dla innego przesunięcia czasowego niż oczekiwane.
* Dane zarejestrowane w lokalnej strefie czasowej można przekonwertować na format UTC przy użyciu **Edytora zapytań**.
