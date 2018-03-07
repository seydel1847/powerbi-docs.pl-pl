---
title: "Samouczek — Wykres kombi"
description: "Ten samouczek dotyczący wykresów kombi objaśnia, kiedy ich używać i jak je tworzyć w usłudze Power BI i programie Power BI Desktop."
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
ms.date: 01/21/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: a52a50b647e743bfd29eecd970c1f381098bd344
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
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

### <a name="prerequisites"></a>Wymagania wstępne
Wykresy kombi są dostępne w usłudze Power BI i w programie Power BI Desktop. W tym samouczku do utworzenia wykresu kombi jest używana usługa Power BI. Aby samodzielnie wykonywać odpowiednie czynności, otwórz usługę Power BI i połącz się z przykładem „Retail Analysis” ([instrukcje znajdują się poniżej](#create)).


## <a name="create-a-basic-single-axis-combo-chart"></a>Tworzenie podstawowego, jednoosiowego wykresu kombi
Obejrzyj, jak Will tworzy wykres kombi przy użyciu przykładu sprzedaży i marketingu.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

<a name="create"></a> Aby utworzyć własny wykres kombi, zaloguj się w usłudze Power BI, a następnie wybierz pozycję **Pobierz dane \> Przykłady \> Przykład Retail Analysis > Połącz > Przejdź do pulpitu nawigacyjnego**.

1. Na pulpicie nawigacyjnym „Przykład analizy detalicznej” wybierz kafelek **Magazyny razem**, aby otworzyć raport „Przykład analizy detalicznej”.
2. Wybierz pozycję **Edytuj raport**, aby otworzyć raport w widoku do edycji.
3. [Dodaj nową stronę raportu](power-bi-report-add-page.md).
4. Utwórz wykres kolumnowy wyświetlający marżę sprzedaży i marżę brutto według miesięcy za bieżący rok.

    a.  W okienku Pola wybierz pozycje **Sprzedaż** \> **Sprzedaż tegoroczna** > **Wartość**.

    b.  Przeciągnij pozycję **Sprzedaż** \> **Marża brutto w tym roku** do źródła **Wartość**.

    c.  Wybierz pozycje **Czas** \> **Miesiąc obrachunkowy**, aby je dodać do źródła **Oś**.

    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Wybierz wielokropek (...) w górnym prawym rogu wizualizacji, a następnie wybierz pozycję **Sortuj według miesiąca obrachunkowego**. Może być konieczne dwukrotne wybranie tej pozycji, aby posortować dane w kolejności rosnącej lub malejącej.

6. Przekształć wykres kolumnowy w wykres kombi. Po wybraniu wykresu kolumnowego z okienka **Wizualizacje** wybierz pozycję **Wykres liniowy i kolumnowy grupowany**.

    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. Z okienka **Pola** przeciągnij pozycje **Sprzedaż** \> **Sprzedaż zeszłoroczna** do zasobnika **Wartości wiersza**.

   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   Twój wykres kombi powinien wyglądać następująco:

   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Tworzenie wykresu kombi z dwoma osiami
W tym zadaniu porównamy marżę brutto i sprzedaż.

1. Utwórz nowy wykres liniowy, który śledzi wartość **Gross Margin last year %** względem wartości **Month**.  W styczniu % marży brutto był równy 35%, wzrósł do 45% w kwietniu, spadł w lipcu i ponownie wzrósł w sierpniu. Czy podobny wzorzec sprzedaży wystąpił w poprzednim i bieżącym roku?

   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. Dodaj pozycje **This Year Sales > Value** i **Last Year Sales** do wykresu liniowego. Skala wartości **Gross Margin Last Year %** jest znacznie mniejsza niż skala wartości **Sales**, co utrudnia porównanie.      

   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. Aby ułatwić odczytanie i interpretację wizualizacji, przekonwertuj wykres liniowy na wykres liniowy i skumulowany kolumnowy.

   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. Przeciągnij pozycję **Gross Margin Last Year %** z obszaru **Wartości w kolumnie** do obszaru **Wartości liniowe**. Usługa Power BI utworzy dwie osie, dzięki czemu zestawy danych można skalować w różny sposób, czyli po lewej stronie jest mierzona wartość sprzedaży w dolarach, a po prawej — procent.

   ![](media/power-bi-visualization-combo-chart/power-bi-combochart.png)    

## <a name="add-titles-to-the-axes"></a>Dodawanie tytułów do osi
1. Wybierz ikonę wałka do malowania ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png), aby otworzyć okienko Formatowanie.
2. Wybierz strzałkę w dół, aby rozwinąć opcje **Osi Y**.
3. W pozycji **Oś Y (Kolumna)** ustaw wartość **Pozycja** na **Lewo**, ustaw wartość **Tytuł** na **Wł.**, wartość **Styl** na **Pokaż tylko tytuł** i wartość **Wyświetlanie** na **Miliony**.

   ![](media/power-bi-visualization-combo-chart/power-bi-y-axis-column.png)
4. W obszarze **Oś Y (kolumna)** przewiń w dół i upewnij się, że opcja **Pokaż dodatkowe** ma wartość **Wł**. Spowoduje to wyświetlenie opcji formatowania fragmentu wykresu liniowego wykresu kombi.

   ![](media/power-bi-visualization-combo-chart/power-bi-show-secondary.png)
5. Dla pozycji **Oś Y (Linia)** pozostaw wartość **Pozycja** równą **Prawo**, ustaw wartość **Tytuł** na **Wł.** i ustaw wartość **Styl** na **Pokaż tylko tytuł**.

   Wykres kombi wyświetli teraz dwie osie, obie z tytułami.

   ![](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

6. Opcjonalnie zmodyfikuj czcionkę, rozmiar i kolor tekstu oraz ustaw inne opcje formatowania, aby poprawić widoczność i czytelność wykresu.

W tym miejscu możesz chcieć:

* [Dodać wykres kombi jako kafelek pulpitu nawigacyjnego](service-dashboard-tiles.md).
* [Zapisz raport](service-report-save.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Wyróżnianie i filtrowanie krzyżowe

Wyróżnienie kolumny lub linii na wykresie kombi powoduje wyróżnienie i filtrowanie krzyżowe innych wizualizacji na stronie raportu... i na odwrót. To zachowanie domyślne można zmienić za pomocą [interakcji wizualizacji](service-reports-visual-interactions.md).

## <a name="next-steps"></a>Następne kroki

[Omówienie wizualizacji w raportach usługi Power BI](power-bi-report-visualizations.md)

[Typy wizualizacji w usłudze Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)
