---
title: "Fragmentatory w usłudze Power BI (samouczek)"
description: "Samouczek: fragmentatory w usłudze Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/05/2018
ms.author: v-thepet
LocalizationGroup: Visualizations
ms.openlocfilehash: cfa4c0f17c67a036b7d01744da1b5247345c493a
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2018
---
# <a name="slicers-in-power-bi-tutorial"></a>Fragmentatory w usłudze Power BI (samouczek)
Załóżmy, że wiceprezes ds. sprzedaży chce mieć wgląd w kilka metryk dotyczących całego działu oraz poszczególnych menedżerów regionalnych. Można utworzyć osobny raport dla każdego menedżera lub użyć fragmentatora. Fragmentator zawęża część zestawu danych wyświetlanego w innych wizualizacjach w raporcie. Fragmentatory to alternatywny sposób filtrowania.

W tym samouczku używany jest [przykład Retail Analysis](sample-retail-analysis.md), aby przeprowadzić użytkownika przez proces tworzenia i formatowania fragmentatora i używania go do filtrowania raportu. Baw się dobrze, odkrywając sposoby formatowania i korzystania z fragmentatorów. 

![slicer (fragmentator)](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Kiedy użyć fragmentatora
Fragmentatory są doskonałym wyborem, jeśli chcesz:

* Wyświetlić często używane lub ważne filtry na kanwie raportu w celu ułatwienia dostępu.
* Ułatwić wyświetlanie bieżącego stanu przefiltrowanego bez konieczności otwierania listy rozwijanej. 
* Filtrować według kolumn, które są niepotrzebne i ukryte w tabelach danych.
* Utworzyć bardziej ukierunkowane raporty, ustawiając fragmentatory obok ważnych wizualizacji.

Fragmentatory usługi Power BI mają następujące ograniczenia:

- Fragmentatory nie obsługują pól danych wejściowych.
- Nie można przypiąć fragmentatora do pulpitu nawigacyjnego.
- Przechodzenie do szczegółów nie jest obsługiwane w przypadku fragmentatorów.
- Fragmentatory nie obsługują filtrów na poziomie wizualizacji.

## <a name="create-a-slicer"></a>Tworzenie fragmentatora

W tym samouczku używany jest fragmentator listy. Typy danych liczbowych i daty/godziny mogą mieć fragmentatory zakresu. Zobacz [Używanie fragmentatora zakresu liczbowego w programie Power BI Desktop](desktop-slicer-numeric-range.md) lub dostępny poniżej film wideo, aby uzyskać więcej informacji na temat tworzenia i używania fragmentatorów zakresu.
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>

1. W usłudze Power BI Desktop lub Power BI, otwórz [Przykład Retail Analysis](sample-retail-analysis.md) w [Widoku do edycji](service-interact-with-a-report-in-editing-view.md) i [dodaj nową stronę raportu](power-bi-report-add-page.md).
2. W okienku Pola w obszarze District (Region) wybierz pozycję **District Manager** (Menedżer regionalny), aby utworzyć nową wizualizację.
    
    ![nowy wykres](media/power-bi-visualization-slicers/1-new-vis.png)
    
3. Wybierz ikonę **Fragmentator** ![ikona fragmentatora](media/power-bi-visualization-slicers/slicer-icon.png) w okienku Wizualizacje, aby przekonwertować nową wizualizację na fragmentator. 
    
    ![konwertowanie na fragmentator](media/power-bi-visualization-slicers/2-slicer.png)

Możesz również wybrać ikonę Fragmentator, aby utworzyć nowy fragmentator, a następnie wybierz lub przeciągnij pole danych, aby je wypełnić.

>[!TIP]
>Elementy listy fragmentatora można sortować według wartości danych. Aby posortować elementy fragmentatora w odwrotnej kolejności alfabetycznej, wybierz wielokropek (...) w prawym górnym rogu fragmentatora i wybierz opcję **Sort by District Manager** (Sortowanie według menedżera regionalnego). Ustawieniem domyślnym jest rosnący porządek alfabetyczny, ale z możliwością przełączenia między porządkiem rosnącym i malejącym. 

## <a name="format-the-slicer"></a>Formatowanie fragmentatora
Zastosuj formatowanie wizualizacji do fragmentatora Menedżera regionalnego.
1. Po wybraniu fragmentatora wybierz ikonę Format ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) w okienku Wizualizacje, aby wyświetlić kontrolki formatowania. 
    
    ![formatowanie](media/power-bi-visualization-slicers/3-format.png)
    
2. Kliknij strzałkę listy rozwijanej obok każdej kategorii, aby wyświetlić i edytować opcje. 

### <a name="general-options"></a>Opcje ogólne
1. Wybierz kolor czerwony w obszarze **Kolor konturu** i zmień ustawienie **Grubość konturu** na „2”. Powoduje to ustawienie koloru i grubości konturów lub podkreśleń nagłówka i elementu, jeśli są włączone. 
2. W obszarze Orientacja domyślnym ustawieniem jest Pionowa, tworzące fragmentator listy poziomej, z polami wyboru przed elementami. Wybierz ustawienie **Pozioma**, aby wygenerować fragmentator z elementami ułożonymi poziomo. Orientacja pozioma może tworzyć różne rozmieszczenia tekstu, przycisków lub kafelków, w zależności od rozmiaru i kształtu fragmentatora oraz formatowania elementu. 
    
    ![pozioma](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. Włącz układ **Dynamiczny**, który zmienia rozmiar i rozmieszczenie poziomych elementów fragmentatora, aby dopasować rozmiar i kształt fragmentatora. Przy bardzo małym rozmiarze fragmentator staje się ikoną filtru. 
    
    ![dynamiczny](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >Zmiany układu dynamicznego mogą zastępować określone formatowanie nagłówka i elementów ustawione przez użytkownika. 
    
4. Ustaw położenie i rozmiar fragmentatora z dokładnością liczbową w **pozycji X**, **położeniu Y**, **szerokości** i **wysokości** lub przenieś i zmień rozmiar fragmentatora bezpośrednio w obszarze roboczym, aby utworzyć inne rozmiary i rozmieszczenia elementów, takich jak poziomy wiersz przycisków. 

    ![przyciski poziome](media/power-bi-visualization-slicers/6-buttons.png)

Zobacz [Tworzenie fragmentatora dynamicznego z możliwością zmiany rozmiaru w usłudze Power BI](power-bi-slicer-filter-responsive.md), aby uzyskać więcej informacji na temat orientacji poziomej i formatowania dynamicznego.

### <a name="selection-controls-options"></a>Opcje wyboru kontrolek
1. Pokazywanie elementu Zaznacz wszystko jest domyślnie wyłączone. Ustaw je na **Włącz**, aby dodać element Zaznacz wszystko do fragmentatora, który zaznacza wszystkie elementy lub usuwa ich zaznaczenie, gdy jest włączony. Kiedy wszystkie elementy są zaznaczone, kliknięcie jednego elementu usuwa jego zaznaczenie, umożliwiając zastosowanie filtru typu „nie jest”. 
    
    ![wybierz wszystko](media/power-bi-visualization-slicers/7-select-all.png)
    
2. Wybór pojedynczego elementu jest domyślnie włączony. Kliknięcie każdego elementu zaznacza go, a przytrzymanie wciśniętego klawisza CTRL podczas klikania umożliwia zaznaczenie wielu elementów. Ustaw opcję Wybór pojedynczego elementu na **Wyłączone**, aby umożliwić zaznaczanie wielu elementów bez przytrzymywania klawisza CTRL. Ponowne kliknięcie każdego elementu usuwa jego zaznaczenie. 

### <a name="header-options"></a>Opcje nagłówka
Nagłówek jest domyślnie włączony, wyświetlając u góry fragmentatora nazwę pola danych. 
1. Sformatuj tekst nagłówka, aby ustawić **Kolor czcionki** czerwony, **Rozmiar tekstu** 14 punktów i **Rodzinę czcionek** Arial Black. 
2. W obszarze konturu wybierz pozycję **Tylko dół**, aby utworzyć podkreślenie o rozmiarze i kolorze ustawionych w obszarze Opcje ogólne. 

### <a name="item-options"></a>Opcje elementu
1. Sformatuj tekst i tło elementu, aby ustawić **Kolor czcionki** czarny, **Tło** jasnoczerwone, **Rozmiar tekstu** 10 punktów i **Rodzinę czcionek** Arial. 
2. W obszarze Konspekt wybierz pozycję **Ramka**, aby narysować dookoła każdego elementu obramowanie o rozmiarze i kolorze ustawionych w obszarze Opcje ogólne. 
    
    ![sformatowane](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- W przypadku orientacji poziomej elementy niezaznaczone są wyświetlane przy użyciu wybranych kolorów tekstu i tła, natomiast elementy zaznaczone używają systemowych ustawień domyślnych, zazwyczaj czarnego tła i białego tekstu. 
    >- W przypadku orientacji pionowej elementy zawsze wyświetlają ustawione kolory, a pola wyboru są zawsze czarne po zaznaczeniu. 

### <a name="other-formatting-options"></a>Inne opcje formatowania
Inne opcje formatowania są domyślnie wyłączone. Po **włączeniu**: 
- **Tytuł:** dodaje i formatuje tytuł (dodatkowy i niezależny od nagłówka) w górnej części fragmentatora. 
- **Tło:** dodaje kolor tła do ogólnego fragmentatora i ustawia jego przezroczystość.
- **Blokuj proporcje:** zachowuje kształt fragmentatora w przypadku zmiany jego rozmiaru.
- **Obramowanie:** dodaje 1-pikselowe obramowanie wokół fragmentatora i ustawia jego kolor. (To obramowanie fragmentatora jest oddzielne i niezależne od ustawień ogólnych konturu). 

## <a name="sync-and-use-the-slicer-on-other-pages"></a>Synchronizacja i używanie fragmentatora na innych stronach
Począwszy od aktualizacji usługi Power BI w lutym 2018, można synchronizować fragmentator i używać go na dowolnych lub wszystkich stronach w raporcie. 
1. Z wybranym fragmentatorem menedżera regionalnego wybierz w menu Widok polecenie **Synchronizuj fragmentatory** w programie Power BI Desktop lub włącz **okienko fragmentatorów synchronizacji** w usłudze Power BI. Zostanie wyświetlone okienko Fragmentatory synchronizacji. 
    
    ![fragmentatory synchronizacji](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
2. W pierwszej kolumnie wybierz pozycję **Omówienie** i inne strony, z którymi ma być synchronizowany fragmentator, lub kliknij przycisk **Dodaj do wszystkich**, aby fragmentator wykonywał synchronizację ze wszystkimi stronami raportu.  
3. W następnej kolumnie wybierz pozycję **Omówienie** i inne strony, na których ma być widoczny fragmentator. 
4. Przełącz się do strony **Omówienie** i zanotuj fragmentator oraz jego wpływ na elementy wizualne innej strony. 
    - Wybierz różne elementy i usuń ich zaznaczenie i zwróć uwagę, jak inne wizualizacje na stronie odpowiednio się zmieniają. Wybór elementów na każdej stronie jest odzwierciedlany na wszystkich zsynchronizowanych stronach.
    - Zmień rozmiar, kształt, położenie i/lub formatowanie fragmentatora na stronie Przegląd. Formatowanie fragmentatora na innych synchronizowanych stronach nie zmienia się. 

### <a name="control-which-page-visuals-are-affected-by-the-slicer"></a>Kontrolowanie wizualizacji strony, na które ma wpływ fragmentator
Domyślnie fragmentator na stronie raportu ma wpływ na wszystkie inne wizualizacje na tej stronie. Użyj opcji **Interakcje wizualne**, aby zapobiec wpływowi na niektóre wizualizacje strony.

1. Na stronie **Omówienie** z wybranym fragmentatorem:
    - W programie Power BI Desktop kliknij menu Format w obszarze Narzędzia wizualizacji, a następnie wybierz pozycję **Edytuj interakcje**.
    - W usłudze Power BI rozwiń listę rozwijaną **Interakcje wizualne** z paska menu i włącz opcję **Edytuj interakcje**. 
    
    Kontrolki filtrowania pojawią się nad innymi wizualizacjami na stronie. ![kontrolki filtrowania](media/power-bi-visualization-slicers/filter-controls.png)
    
2. Wybierz ikonę **Brak** nad wizualizacją, aby zatrzymać jej filtrowanie przez fragmentator. Wybierz ikonę **Filtruj**, aby fragmentator zaczął ponownie filtrować wizualizację. 

Aby uzyskać więcej informacji na temat edytowania interakcji, zobacz temat [Interakcje wizualizacji w raporcie Power BI](service-reports-visual-interactions.md).

## <a name="next-steps"></a>Następne kroki
[Wypróbuj bezpłatnie!](https://powerbi.com/)

Masz pomysły dotyczące poprawy usługi Power BI? [Prześlij pomysł](https://ideas.powerbi.com/forums/265200-power-bi-ideas).

Więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

[Dodawanie wizualizacji do raportu](power-bi-report-add-visualizations-i.md)

[Typy wizualizacji w usłudze Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

