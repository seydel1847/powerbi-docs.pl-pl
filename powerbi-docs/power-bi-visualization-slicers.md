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
ms.date: 05/30/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 619f694e6e3ed167a14262994c1c978d5b4ea2e0
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="slicers-in-power-bi-service-tutorial"></a>Fragmentatory w usłudze Power BI (samouczek)
Załóżmy, że wiceprezes ds. sprzedaży chce mieć wgląd w różne metryki dotyczące całego działu oraz poszczególnych menedżerów regionalnych. Można utworzyć osobną stronę raportu dla każdego menedżera lub użyć fragmentatora. Fragmentator zawęża część zestawu danych wyświetlanego w innych wizualizacjach na stronie.  Fragmentatory to alternatywny sposób filtrowania.

![](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Kiedy użyć fragmentatora
Fragmentatory są doskonałym rozwiązaniem w następujących sytuacjach:

* Aby wyświetlić często używane lub ważne filtry na kanwie raportu w celu ułatwienia dostępu.
* Aby ułatwić wyświetlanie bieżącego stanu przefiltrowanego bez konieczności otwierania listy rozwijanej w celu znalezienia szczegółów filtrowania.
* Jeśli chcesz ukryć kolumny, których nie potrzebujesz, ale chcesz nadal mieć możliwość używania ich do filtrowania — dzięki temu tabele są zawężone i oczyszczone.
* Aby utworzyć więcej raportów z możliwością koncentracji uwagi — fragmentatory są obiektami ruchomymi, więc można je umieścić obok interesujących części raportu, na których użytkownicy mają się skoncentrować.

## <a name="create-a-slicer"></a>Tworzenie fragmentatora
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>


1. Otwórz pozycję [Przykład Retail Analysis](sample-retail-analysis.md) w [widoku do edycji](service-interact-with-a-report-in-editing-view.md) i [dodaj nową stronę raportu](power-bi-report-add-page.md).
2. W okienku Pola wybierz pozycję **District > District Manager** (Region > Menedżer regionalny).
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_chartfirst.png)
3. Przekonwertuj wizualizację na fragmentator. W okienku Wizualizacje wybierz ikonę fragmentatora.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_select.png)

## <a name="format-the-slicer"></a>Formatowanie fragmentatora
1. Po wybraniu fragmentatora w okienku Wizualizacje wybierz ikonę wałka do malowania ![](media/power-bi-visualization-slicers/power-bi-paintroller.png), aby wyświetlić opcje formatowania.
2. Wybierz pozycje **Ogólne > Kolor konturu** i wybierz kolor ciemnoniebieski oraz zmień **grubość** na wartość **6**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_outline2.png)
3. W obszarze **Kontrolki wyboru** pozycja **Zaznacz wszystko** jest domyślnie **wyłączona**, a pozycja **Wybór pojedynczego elementu** jest **włączona**. Oznacza to, że trzeba użyć klawisza CTRL, aby wybrać więcej niż jedną nazwę jednocześnie. Zmień ustawienie pozycji **Zaznacz wszystko** na **Włączone**, a pozycji **Wybór pojedynczego elementu** na **Wyłączone**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_selectioncontrols2.png)
   
   * Zauważ, że fragmentator ma teraz opcję **Zaznacz wszystko** na górze listy. Przełącz pozycję **Zaznacz wszystko**, aby zaznaczyć lub odznaczyć wszystkie nazwy.
   * Teraz możesz wybrać więcej niż jedną nazwę bez konieczności używania klawisza CTRL.
4. W obszarze **Elementy** zwiększ rozmiar tekstu do 14 punktów.  Robimy to, aby mieć pewność, że współpracownicy zauważą fragmentator.
5. Na koniec ustaw **kolor czcionki** na ciemnoczerwony.  Pozwoli to odróżnić nazwy zaznaczone od niezaznaczonych we fragmentatorze.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_font2.png)
6. Baw się dobrze, odkrywając inne opcje dostępne dla fragmentatorów.

## <a name="use-the-slicer-in-a-report"></a>Używanie fragmentatora w raporcie
1. Dodaj niektóre dodatkowe wizualizacje do strony raportu lub otwórz [raport przykładu Retail Analysis](sample-retail-analysis.md) i wybierz kartę **District Monthly Sales** (Miesięczna sprzedaż według regionu).
   
    ![](media/power-bi-visualization-slicers/power-bi-retail-sample.png)
2. Utwórz wycinek strony raportu dla menedżera o imieniu Carlos. Zwróć uwagę, jak inne wizualizacje aktualizują się, odzwierciedlając ten wybór.
   
    ![](media/power-bi-visualization-slicers/slicer2.gif)
3. Posortuj fragmentator alfabetycznie według nazwiska menedżera regionalnego.  W prawym górnym rogu fragmentatora wybierz wielokropek (...) i wybierz pozycję **District Manager** (Menedżer regionalny).
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sort2.png)
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sorted.png)

## <a name="control-what-effect-the-slicer-has-on-other-visuals-on-the-page"></a>Kontrola wpływu fragmentatora na inne elementy wizualne na stronie
Czy chcesz, aby fragmentator filtrował tylko niektóre elementy wizualne na stronie raportu?  Użyj kontrolki **Interakcje wizualne**, aby to skonfigurować.

**UWAGA**: jeśli nie widzisz pozycji **Interakcje wizualne**, poszukaj tej ikony ![](media/power-bi-visualization-slicers/power-bi-slicer-visual-interactions.png). Jeśli nie widzisz żadnego z tych elementów, upewnij się, że jesteś w [widoku raportu do edycji](service-reading-view-and-editing-view.md).

1. Wybierz fragmentator, aby go uaktywnić, a następnie z paska menu wybierz pozycję **Interakcje wizualne**.
   
    ![](media/power-bi-visualization-slicers/pbi-slicer-interactions.png)
2. Kontrolki filtrowania pojawią się nad innymi wizualizacjami na stronie. Jeśli fragmentator powinien filtrować wizualizację, wybierz ikonę **Filtrowanie**.  Jeśli fragmentator nie powinien wpływać na wizualizację, wybierz ikonę **Brak**.
   
    ![](media/power-bi-visualization-slicers/filter-controls.png)

Aby uzyskać więcej informacji, zobacz temat [Interakcje wizualizacji w raporcie Power BI](service-reports-visual-interactions.md).

## <a name="considerations-and-troubleshooting-slicers-in-power-bi"></a>Zagadnienia dotyczące fragmentatorów w usłudze Power BI i rozwiązywanie problemów
Istnieją pewne ograniczenia dotyczące używania fragmentatorów w usłudze Power BI:

1. Fragmentatory nie obsługują pól danych wejściowych.
2. Nie można użyć pojedynczego fragmentatora w całym raporcie. Fragmentator ma wpływ tylko na bieżącą stronę.
3. Nie można przypiąć fragmentatora do pulpitu nawigacyjnego.
4. Przechodzenie do szczegółów nie jest obsługiwane w przypadku fragmentatorów.    
5. Fragmentatory nie obsługują filtrów na poziomie wizualizacji.

Masz pomysły dotyczące poprawy usługi Power BI? [Prześlij pomysł](https://ideas.powerbi.com/forums/265200-power-bi-ideas).

## <a name="next-steps"></a>Następne kroki
 [Dodawanie wizualizacji do raportu](power-bi-report-add-visualizations-i.md)

 [Typy wizualizacji w usłudze Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

 [Power BI — podstawowe pojęcia](service-basic-concepts.md)

[Wypróbuj bezpłatnie!](https://powerbi.com/)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

