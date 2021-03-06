---
title: Część 1, dodawanie wizualizacji do raportu usługi Power BI
description: Część 1, dodawanie wizualizacji do raportu usługi Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 52c0211aea0462e0bf79d7a48808f1f826c09fb6
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296092"
---
# <a name="part-i-add-visualizations-to-a-power-bi-report"></a>Część 1, dodawanie wizualizacji do raportu usługi Power BI
Ten artykuł zawiera szybkie wprowadzenie do tworzenia wizualizacji w raporcie przy użyciu usługi Power BI lub programu Power BI Desktop.  Bardziej zaawansowaną zawartość umieszczono w [części 2](power-bi-report-add-visualizations-ii.md). Obejrzyj film, w którym Amanda prezentuje kilka różnych sposobów tworzenia, edytowania i formatowania wizualizacji na kanwie raportu. Wypróbuj je samodzielnie, tworząc własny raport przy użyciu [próbki danych dotyczących sprzedaży i marketingu](../sample-datasets.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>


## <a name="open-a-report-and-add-a-new-page"></a>Otwieranie raportu i dodawanie nowej strony
1. Otwórz [raport w widoku do edycji](../consumer/end-user-reading-view.md). W tym samouczku jest używana [próbka danych dotyczących sprzedaży i marketingu](../sample-datasets.md).
2. Jeśli okienko Pola nie jest widoczne, wybierz ikonę strzałki, aby je otworzyć. 
   
   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)
3. Dodaj do raportu pustą stronę.

## <a name="add-visualizations-to-the-report"></a>Dodawanie wizualizacji do raportu
1. Utwórz wizualizację, wybierając pole w okienku **Pola**.  
   
   **Zacznij od pola liczbowego**, takiego jak SalesFact (Informacje o sprzedaży) > Sales $ (Sprzedaż w USD). Usługa Power BI tworzy wykres kolumnowy dla jednej kolumny.
   
   ![](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)
   
   **Albo zacznij od pola kategorii**, takiego jak Name (Nazwa) lub Product (Produkt): usługa Power BI utworzy tabelę i doda to pole do zasobnika **Values** (Wartości).
   
   ![](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)
   
   **Albo zacznij od pola geograficznego**, takiego jak Geo (Geograficzne) > City (Miasto). Usługi Power BI i Mapy Bing utworzą wizualizację mapy.
   
   ![](media/power-bi-report-add-visualizations-i/power-bi-map.png)
2. Utwórz wizualizację, a następnie zmień jej typ. Wybierz pozycję **Product (Produkt) > Category (Kategoria)**, a następnie pozycję **Product (Produkt) > Liczba elementów: Product**, aby dodać je do obszaru **Wartości**.
   
   ![](media/power-bi-report-add-visualizations-i/part1table1.png)
3. Zmień wizualizację na wykres kolumnowy, wybierając ikonę wykresu kolumnowego.
   
   ![](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)
4. Po utworzeniu wizualizacji w raporcie można [przypiąć je do pulpitu nawigacyjnego](../service-dashboard-pin-tile-from-report.md). Aby przypiąć wizualizację, wybierz ikonę pinezki ![](media/power-bi-report-add-visualizations-i/pinnooutline.png).
   
   ![](media/power-bi-report-add-visualizations-i/part1pin1.png)
  

## <a name="next-steps"></a>Następne kroki
 Przejdź do tematu [Część 2: dodawanie wizualizacji do raportu usługi Power BI](power-bi-report-add-visualizations-ii.md)
   
   [Wypróbuj interakcje z wizualizacjami](../consumer/end-user-reading-view.md) w raporcie.
   
   [Wykorzystaj inne możliwości wizualizacji](power-bi-report-visualizations.md).
   
   [Zapisz raport](../service-report-save.md).
