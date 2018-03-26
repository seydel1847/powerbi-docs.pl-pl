---
title: Tworzenie fragmentatora dynamicznego z możliwością zmiany rozmiaru w usłudze Power BI
description: Dowiedz się, jak utworzyć fragmentator dynamiczny, którego rozmiar można zmieniać, aby pasował do raportu
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/08/2017
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 2ab907dd15e43892147967902fbb94d09ef4125b
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2018
---
# <a name="create-a-responsive-slicer-you-can-resize-in-power-bi-preview"></a>Tworzenie fragmentatora dynamicznego z możliwością zmiany rozmiaru w usłudze Power BI (wersja zapoznawcza)

Fragmentatory dynamiczne dopasowują swój rozmiar do dowolnego obszaru w raporcie. Fragmentatory dynamiczne można dopasowywać do różnych rozmiarów i kształtów — od poziomych, przez kwadratowe, do pionowych — a rozmieszczenie wartości we fragmentatorze zmienia się automatycznie. W programie Power BI Desktop i w usłudze Power BI dynamiczne mogą być fragmentatory poziome i fragmentatory dat/zakresu. Fragmentatory dat/zakresu mają także ulepszone obszary dotykowe, dzięki czemu zmienianie ich za pomocą palca jest łatwiejsze. Fragmentatory dynamicznie mogą być dowolnie duże lub małe. Ponadto ich rozmiar zmienia się automatycznie w celu dopasowania do raportów w usłudze Power BI i w aplikacjach mobilnych Power BI. 

![Fragmentatory dynamiczne mogą mieć różnorodne kształty](media/power-bi-slicer-filter-responsive/responsive-slicer-gif.gif)

## <a name="create-a-slicer"></a>Tworzenie fragmentatora

Pierwszym krokiem do utworzenia fragmentatora dynamicznego jest utworzenie fragmentatora podstawowego. 

1. Wybierz ikonę **Fragmentator** ![ikona fragmentatora](media/power-bi-slicer-filter-responsive/power-bi-slicer-icon.png) w okienku **Wizualizacje**.
2. Przeciągnij pole, według którego chcesz filtrować, do obszaru **Pole**.

    ![Dodawanie pola do fragmentatora](media/power-bi-slicer-filter-responsive/power-bi-slicer-field.png)

## <a name="convert-to-a-horizontal-slicer"></a>Konwertowanie na fragmentator poziomy

1. Po wybraniu fragmentatora w okienku **Wizualizacje** wybierz kartę **Format**.
2. Rozwiń sekcję **Ogólne**, a następnie w polu **Orientacja** wybierz pozycję **Pozioma**.

    ![Ustawianie poziomej orientacji fragmentatora](media/power-bi-slicer-filter-responsive/power-bi-slicer-horizontal.png) 

1.  Prawdopodobnie trzeba będzie go poszerzyć, aby pokazać więcej wartości.

     ![Poszerzanie fragmentatora](media/power-bi-slicer-filter-responsive/power-bi-slicer-wide-horizontal.png)

## <a name="make-it-responsive-and-experiment-with-it"></a>Tworzenie fragmentatora dynamicznego i eksperymentowanie z nim

Ten krok jest łatwy. 

1. Tuż poniżej pola **Orientacja** w sekcji **Ogólne** karty **Format** przesuń suwak **Dynamiczny (wersja zapoznawcza)** na pozycję **Włączone**.  

    ![Fragmentator jest teraz dynamiczny](media/power-bi-slicer-filter-responsive/power-bi-slicer-wide-responsive.png)

1. Teraz możesz z nim poeksperymentować. Przeciągnij narożniki, aby stał się niski, wysoki, szeroki lub wąski. Jeśli odpowiednio go zmniejszysz, stanie się jedynie ikoną filtru.

    ![Fragmentator dynamiczny tak mały, że jest ikoną filtru](media/power-bi-slicer-filter-responsive/power-bi-slicer-small-filter-icon.png)

## <a name="add-it-to-a-phone-report-layout"></a>Dodawanie go do układu raportu na telefon

W programie Power BI Desktop można utworzyć układ telefonu dla każdej strony raportu. Jeśli strona ma układ telefonu, jest wyświetlana na telefonie komórkowym w orientacji pionowej. W przeciwnym razie trzeba ją wyświetlać w orientacji poziomej. 

1. W menu **Widok** wybierz pozycję **Układ telefonu**.

     ![Ikona układu telefonu, menu Widok](media/power-bi-slicer-filter-responsive/power-bi-phone-layout-menu.png)
    
1. Przeciągnij na siatkę wszystkie wizualizacje, które mają się znaleźć w raporcie na telefon. Gdy przeciągniesz fragmentator dynamiczny, ustaw dla niego dowolny rozmiar — w tym przypadku jest to ikona filtru.

    ![Dodawanie fragmentatora do układu raportu na telefon](media/power-bi-slicer-filter-responsive/power-bi-slicer-phone-layout.png)

Dowiedz się więcej o tworzeniu [raportów zoptymalizowanych pod kątem aplikacji mobilnych Power BI](desktop-create-phone-report.md).

## <a name="make-a-time-or-range-slicer-responsive"></a>Tworzenie fragmentatora dynamicznego z fragmentatora czasu lub zakresu

Możesz wykonać te same czynności, aby fragmentator czasu lub zakresu stał się dynamiczny. Po ustawieniu suwaka **Dynamiczny** na pozycję **Włączone** zauważysz kilka rzeczy:

- Kolejność pól wejściowych w wizualizacjach jest optymalizowana w zależności od rozmiaru dozwolonego na kanwie. 
- Wyświetlanie elementów danych jest zoptymalizowane pod kątem maksymalnej użyteczności fragmentatora w zależności od rozmiaru dozwolonego na kanwie. 
- Nowe zaokrąglone paski uchwytu na fragmentatorach optymalizują interakcje dotykowe. 
- Jeśli wizualizacja jest zbyt mała, aby była użyteczna, staje się ona ikoną przedstawiającą typ wizualizacji znajdującej się w danym miejscu. Aby z niej skorzystać, wystarczy nacisnąć ją dwukrotnie w celu otwarcia w trybie koncentracji uwagi. Pozwala to zaoszczędzić cenne miejsce na stronie raportu bez utraty funkcjonalności.

## <a name="next-steps"></a>Następne kroki

- [Samouczek: fragmentatory w usłudze Power BI](power-bi-visualization-slicers.md)
- Więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)