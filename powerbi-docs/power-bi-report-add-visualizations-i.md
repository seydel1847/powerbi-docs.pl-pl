---
title: "Część 1, dodawanie wizualizacji do raportu usługi Power BI (samouczek)"
description: "Samouczek: część 1, dodawanie wizualizacji do raportu usługi Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: IkJda4O7oGs
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/08/2018
ms.author: mihart
ms.openlocfilehash: 82519877ac9a9603d87f20fc3f1155af34421078
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2018
---
# <a name="part-i-add-visualizations-to-a-power-bi-report-tutorial"></a>Część 1, dodawanie wizualizacji do raportu usługi Power BI (samouczek)
Ten artykuł zawiera szybkie wprowadzenie do tworzenia wizualizacji w raporcie.  Bardziej zaawansowaną zawartość umieszczono w [części 2](power-bi-report-add-visualizations-ii.md). Obejrzyj film, w którym Amanda prezentuje kilka różnych sposobów tworzenia, edytowania i formatowania wizualizacji na kanwie raportu. Wypróbuj je samodzielnie, tworząc własny raport przy użyciu [próbki danych dotyczących sprzedaży i marketingu](sample-datasets.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>


## <a name="open-a-report-and-add-a-new-page"></a>Otwieranie raportu i dodawanie nowej strony
1. Otwórz [raport w widoku do edycji](service-reading-view-and-editing-view.md). W tym samouczku jest używana [próbka danych dotyczących sprzedaży i marketingu](sample-datasets.md).
2. Jeśli okienko Pola nie jest widoczne, wybierz ikonę strzałki, aby je otworzyć. 
   
   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)
3. [Dodaj do raportu pustą stronę](power-bi-report-add-page.md).

## <a name="add-visualizations-to-the-report"></a>Dodawanie wizualizacji do raportu
1. Utwórz wizualizację, wybierając pole w okienku **Pola**.  
   
   **Zacznij od pola liczbowego**, takiego jak Sales (Sprzedaż) > Sales $ (Kwota sprzedaży): usługa Power BI utworzy wykres kolumnowy z jedną kolumną.
   
   ![](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)
   
   **Zacznij od pola kategorii**, takiego jak Name (Nazwa) lub Product (Produkt): usługa Power BI utworzy tabelę i doda to pole do obszaru **Wartości**.
   
   ![](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)
   
   **Zacznij od pola geograficznego**, takiego jak Geo (Geograficzne) > City (Miasto). Usługi Power BI i Mapy Bing utworzą wizualizację mapy.
   
   ![](media/power-bi-report-add-visualizations-i/power-bi-map.png)
2. Utwórz wizualizację, a następnie zmień jej typ. Wybierz pozycję **Product (Produkt) > Liczba elementów: Product** i pozycję **Product (Produkt) > Category (Kategoria)**, aby dodać je do obszaru **Wartości**.
   
   ![](media/power-bi-report-add-visualizations-i/part1table1.png)
3. Zmień wizualizację na wykres kolumnowy, wybierając ikonę wykresu kolumnowego.
   
   ![](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)
4. Po utworzeniu wizualizacji w raporcie można [przypiąć je do pulpitu nawigacyjnego](service-dashboard-pin-tile-from-report.md). Aby przypiąć wizualizację, wybierz ikonę pinezki ![](media/power-bi-report-add-visualizations-i/pinnooutline.png).
   
   ![](media/power-bi-report-add-visualizations-i/part1pin1.png)
5. Co możesz teraz zrobić:
   
   Kontynuuj: [Część 2, dodawanie wizualizacji do raportu usługi Power BI](power-bi-report-add-visualizations-ii.md)
   
   [Wypróbuj interakcje z wizualizacjami](service-reading-view-and-editing-view.md) w raporcie.
   
   [Wykorzystaj inne możliwości wizualizacji](power-bi-report-visualizations.md).
   
   [Zapisz raport](service-report-save.md).

## <a name="next-steps"></a>Następne kroki
Więcej informacji o [wizualizacjach w raportach usługi Power BI](power-bi-report-visualizations.md).

[Raporty w usłudze Power BI](service-reports.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)
