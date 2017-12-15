---
title: "Wykres kombi w usłudze Power BI (samouczek)"
description: "Niniejsza dokumentacja jest samouczkiem (z wideo) pokazującym, dlaczego i jak tworzyć wykres kombi w usłudze Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: lnv66cTZ5ho
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: c00ba74501a411743036c4514750bccbbae3eb00
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="combo-chart-in-power--tutorial"></a>Wykres kombi w usłudze Power BI (samouczek)
W usłudze Power BI wykres kombi to pojedyncza wizualizacja łącząca wykres liniowy i kolumnowy. Łączenie 2 wykresów w jednym umożliwia szybsze porównywanie danych.

Wykresy kombi mogą mieć jedną lub dwie osie Y.

## <a name="when-to-use-a-combo-chart"></a>Kiedy należy używać wykresu kombi
Wykresy kombi są doskonałym wyborem:

* gdy masz wykres liniowy i kolumnowy o takiej samej osi X.
* aby porównać wiele miar z różnymi zakresami wartości.
* aby zilustrować korelację między dwoma miarami w jednej wizualizacji.
* aby sprawdzić, czy jedna miara realizuje cel, który jest definiowany przez inną miarę
* aby zaoszczędzić miejsce na kanwie.

## <a name="create-a-basic-single-axis-combo-chart"></a>Tworzenie podstawowego, jednoosiowego wykresu kombi
Obejrzyj, jak Will tworzy wykres kombi przy użyciu przykładu sprzedaży i marketingu.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


Aby utworzyć własny wykres kombi, zaloguj się w usłudze Power BI, a następnie wybierz pozycje **Pobierz dane \> Przykłady \> Przykład analizy detalicznej**. 

1. Na pulpicie nawigacyjnym „Przykład analizy detalicznej” wybierz kafelek **Magazyny razem**, aby otworzyć raport „Przykład analizy detalicznej”.
2. Wybierz pozycję **Edytuj raport**, aby otworzyć raport w widoku do edycji.
3. [Dodaj nową stronę raportu](power-bi-report-add-page.md).
4. Utwórz wykres kolumnowy wyświetlający marżę sprzedaży i marżę brutto według miesięcy za bieżący rok.
   
    a.  W okienku Pola wybierz pozycje **Sprzedaż** \> **Sprzedaż tegoroczna** > **Wartość**.
   
    b.  Przeciągnij pozycję **Sprzedaż** \> **Marża brutto w tym roku** do źródła **Wartość**.
   
    c.  Wybierz pozycje **Czas** \> **Miesiąc obrachunkowy**, aby je dodać do źródła **Oś**. 
   
    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Wybierz wielokropek (...) w górnym prawym rogu wizualizacji, a następnie wybierz pozycję **Sortuj według miesiąca obrachunkowego**.
6. Przekształć wykres kolumnowy w wykres kombi. Po wybraniu wykresu kolumnowego z okienka **Wizualizacje** wybierz pozycję **Wykres liniowy i kolumnowy grupowany**.
   
    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. Z okienka **Pola** przeciągnij pozycje **Sprzedaż** \> **Sprzedaż zeszłoroczna** do zasobnika **Wartości wiersza**.
   
   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)
   
   Twój wykres kombi powinien wyglądać następująco:
   
   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Tworzenie wykresu kombi z dwoma osiami
W tym zadaniu porównamy marżę brutto i sprzedaż.

1. Utwórz nowy wykres liniowy, który śledzi % marży brutto za ostatni rok według miesiąca.  W styczniu % marży brutto był równy 35%, miał szczyt 45% w kwietniu, spadł w lipcu i ponownie miał szczyt w sierpniu. Czy podobny zeszłoroczny wzorzec sprzedaży zobaczymy w tym roku?
   
   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. Dodaj pozycje **Sprzedaż tegoroczna > Wartość** i **Sprzedaż zeszłoroczna** do wykresu liniowego. Skala **Zeszłoroczny % marży brutto** jest znacznie mniejsza niż skala **Sprzedaży** co utrudnia porównanie.      
   
   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. Aby ułatwić odczytanie i interpretację elementu wizualnego, przekonwertuj wykres liniowy w wykres liniowy i skumulowany kolumnowy.
   
   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. Przeciągnij pozycję **Zeszłoroczny % marży brutto** z pozycji **Wartości w kolumnie** do **Wartości liniowe**. Usługa Power BI utworzy dwie osie, dzięki czemu zestawy danych można skalować w różny sposób, czyli po lewej stronie są mierzone pieniądze, po prawej stronie są mierzone procenty.
   
   ![](media/power-bi-visualization-combo-chart/power-bi-combochart.png)    

## <a name="add-titles-to-the-axes"></a>Dodawanie tytułów do osi
1. Wybierz ikonę wałka do malowania ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png), aby otworzyć okienko Formatowanie.
2. Wybierz strzałkę w dół, aby rozwinąć opcje **Osi Y**.
3. W pozycji **Oś Y (Kolumna)** ustaw wartość **Pozycja** na **Lewo**, ustaw wartość **Tytuł** na **Wł.**, wartość **Styl** na **Pokaż tylko tytuł** i wartość **Wyświetlanie** na **Miliony**.
   
   ![](media/power-bi-visualization-combo-chart/power-bi-y-axis-column.png)
4. W obszarze **Oś Y (Kolumna)** upewnij się również, że wartość **Pokaż dodatkowe** jest ustawiona na **Wł**. Spowoduje to wyświetlenie opcji formatowania fragmentu wykresu liniowego wykresu kombi.
   
   ![](media/power-bi-visualization-combo-chart/power-bi-show-secondary.png)
5. Dla pozycji **Oś Y (Linia)** pozostaw wartość **Pozycja** równą **Prawo**, ustaw wartość **Tytuł** na **Wł.** i ustaw wartość **Styl** na **Pokaż tylko tytuł**.
   
   Wykres kombi wyświetli teraz dwie osie, obie z tytułami.
   
   ![](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

W tym miejscu możesz chcieć:

* [Dodać wykres kombi jako kafelek pulpitu nawigacyjnego](service-dashboard-tiles.md).
* [Zapisać raport](service-report-save.md).

## <a name="highlighting-and-cross-filtering"></a>Wyróżnianie i filtrowanie krzyżowe
Aby uzyskać informacje o korzystaniu z okienka filtrów, zobacz [Dodawanie filtra do raportu](power-bi-report-add-filter.md).

Wyróżnianie kolumny lub linii na wykresie kombi powoduje krzyżowe filtrowanie innych wizualizacji na stronie raportu... i na odwrót.

## <a name="next-steps"></a>Następne kroki
[Dodawanie wizualizacji do raportu](power-bi-report-add-visualizations-i.md)

[Wizualizacje w raportach usługi Power BI](power-bi-report-visualizations.md)

[Typy wizualizacji w usłudze Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

[Wypróbuj bezpłatnie!](https://powerbi.com/)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

