---
title: "Wykresy punktowe w usłudze Power BI (samouczek)"
description: "Samouczek: Wykresy punktowe w usłudze Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: PVcfPoVE3Ys
qualityfocus: identified
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/23/2017
ms.author: mihart
ms.openlocfilehash: 2d8ed3c30d289646504071daca098df1f41f6aab
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="scatter-charts-and-bubble-charts-in-power-bi-tutorial"></a>Wykresy punktowe i bąbelkowe w usłudze Power BI (samouczek)
Wykres punktowy zawsze ma dwie osie wartości: jeden zestaw danych liczbowych jest wyświetlany wzdłuż osi poziomej, a drugi wzdłuż osi pionowej. Na wykresie kreślone są punkty występujące na przecięciu wartości liczbowych x i y, co zapewnia połączenie tych par wartości w pojedynczych punktach danych. Te punkty danych mogą być rozproszone równomiernie lub nierównomiernie wzdłuż osi poziomej, w zależności od danych.

Na wykresie bąbelkowym zamiast punktów danych używane są bąbelki. *Rozmiar* bąbelka reprezentuje dodatkowy wymiar danych.

![](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

Liczbę punktów danych można ustawić  

## <a name="when-to-use-a-scatter-chart-or-bubble-chart"></a>Kiedy używać wykresu punktowego i wykresu bąbelkowego
### <a name="scatter-charts-are-a-great-choice"></a>Wykresy punktowe są doskonałym wyborem w następujących przypadkach:
* Pokazywanie zależności między dwiema (punkty) lub trzema (bąbelki) wartościami **liczbowymi**.
* Przedstawianie dwóch grup liczb jako jednej serii współrzędnych xy.
* Trzeba zmienić skalę osi poziomej (zamiast wykresu liniowego).    
* Trzeba zmienić oś poziomą na skalę logarytmiczną.
* Przedstawianie danych arkusza obejmujących pary lub pogrupowane zestawy wartości. Wykres punktowy pozwala niezależnie dopasowywać skale osi, aby uwidocznić dodatkowe informacje o pogrupowanych wartościach.
* Wyświetlanie wzorców w dużych zestawach danych, na przykład za pomocą trendów liniowych i nieliniowych, grup i wartości odstających.
* Porównywanie dużej liczby punktów danych bez względu na czas.  Im więcej danych uwzględnionych na wykresie punktowym, tym lepsze porównania możesz uzyskać.

### <a name="bubble-charts-are-a-great-choice"></a>Wykresy bąbelkowe są doskonałym wyborem w następujących przypadkach:
* Dane zawierają 3 serie danych, a każda z nich zawiera zestaw wartości.
* Przedstawianie danych finansowych.  Różne rozmiary bąbelków są przydatne do graficznego podkreślania określonych wartości.
* Są używane ćwiartki.

## <a name="create-a-scatter-chart"></a>Tworzenie wykresu punktowego
Obejrzyj ten film wideo, aby zobaczyć, jak Will tworzy wykres punktowy, a następnie wykonaj poniższe kroki w celu utworzenia własnego wykresu.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


W poniższych instrukcjach używane są przykładowe dane dotyczące analizy handlu detalicznego. Aby je wykonać, [pobierz przykład](sample-datasets.md) dla usługi Power BI (app.powerbi.com) lub dla programu Power BI Desktop.   

1. Rozpocznij od [pustej strony raportu](power-bi-report-add-page.md) i wybierz pola **Sales** \> **Sales Per Sq Ft** oraz **Sales** > **Total Sales Variance %**. Jeśli używasz usługi Power BI, upewnij się, że raport jest otwarty w [widoku do edycji](service-interact-with-a-report-in-editing-view.md).
 
2. W okienku Pola wybierz pozycję **District > District**.
   
    ![](media/power-bi-visualization-scatter/power-bi-bar-chart.png)
4. Przekonwertuj na wykres punktowy. W okienku wizualizacji wybierz ikonę wykresu punktowego.
   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_icon.png).
5. Przeciągnij pole **District** z obszaru **Szczegóły** do obszaru **Legenda**.
   
    ![](media/power-bi-visualization-scatter/power-bi-scatter.png)

W efekcie powstał wykres punktowy, który przedstawia wartości Total Sales Variance % wzdłuż osi Y i Sales Per Square Feet wzdłuż osi X.  Kolory punktów danych reprezentują poszczególne regiony.  Teraz dodamy trzeci wymiar.

## <a name="create-a-bubble-chart"></a>Tworzenie wykresu bąbelkowego
1. Z okienka Pola przeciągnij pozycję **Sales** > **This Year Sales** > **Value** do obszaru **Rozmiar**. 
   
   ![](media/power-bi-visualization-scatter/power-bi-bubble.png)
2. Umieść kursor nad bąbelkiem.  Rozmiar bąbelka odzwierciedla wielkość wartości **This Year Sales**.
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)
3. Opcjonalnie można [sformatować kolory, etykiety, tytuły, tło i inne elementy wizualizacji](service-getting-started-with-color-formatting-and-axis-properties.md).

   Możesz również zmienić kształt znacznika na romb, trójkąt lub kwadrat:

   ![Znacznik kwadratowy](media/power-bi-visualization-scatter/pbi_scatter_chart_hover_square.png)

4. Opcjonalnie, aby ustawić liczbę punktów danych do wyświetlenia na wykresie bąbelkowym, w sekcji **Format** okienka **Wizualizacje** rozwiń kartę **Ogólne** i dostosuj pozycję **Ilość danych**. Wartość domyślna to 3500. 
 
    ![Ilość danych](media/power-bi-visualization-scatter/pbi_scatter_data_volume.png) 

   > [!NOTE]
   > Ponieważ większa liczba punktów danych może oznaczać dłuższy czas ładowania, jeśli wybierzesz publikację raportów z ograniczeniami na wyższym końcu skali, pamiętaj o przetestowaniu raportów w Internecie oraz mobilnych w celu zapewnienia, że wydajność jest zgodna z oczekiwaniami użytkowników.

5.   Opcjonalnie, aby wybrać kształt znacznika, rozwiń kartę **Kształty**, a następnie wybierz kształt znacznika.

      ![Kształt znacznika](media/power-bi-visualization-scatter/pbi_scatter_marker.png)

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów
### <a name="your-scatter-chart-has-only-one-data-point"></a>**Wykres punktowy ma tylko jeden punkt danych**
Czy na wykresie punktowym wyświetlany jest tylko jeden punkt danych, w którym zagregowane są wszystkie wartości na osiach X i Y?  A może wszystkie wartości są zagregowane wzdłuż pojedynczej linii poziomej lub pionowej?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

Dodaj pole do obszaru **Szczegóły** w celu poinformowania usługi Power BI o tym, jak należy zgrupować wartości. To pole musi być unikatowe dla każdego punktu, który ma zostać wykreślony.  
Może to być zwykły numer wiersza lub pole identyfikatora:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

Jeśli dane nie zawierają takiego pola, utwórz pole, które łączy wartości X i Y w taki sposób, aby wykreślały unikatowy punkt:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

W celu utworzenia nowego pola [użyj Edytora zapytań programu Power BI Desktop, aby dodać kolumnę indeksu](desktop-add-custom-column.md) do zestawu danych.  Następnie dodaj tę kolumnę do obszaru **Szczegóły** danej wizualizacji.

## <a name="next-steps"></a>Następne kroki
 [Typy wizualizacji w usłudze Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Wypróbuj bezpłatnie!](https://powerbi.com/)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)
