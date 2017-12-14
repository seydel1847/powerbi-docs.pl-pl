---
title: "Zmienianie sposobu interakcji elementów wizualnych w raporcie"
description: "Dokumentacja ustawiania interakcji elementów wizualnych w raporcie usługi Microsoft Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: N_xYsCbyHPw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 126bd40e98a88138a2732155f9792d65666e52c7
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Interakcje wizualizacji w raporcie usługi Power BI
Domyślnie wizualizacje na stronie raportu mogą służyć do krzyżowego filtrowania i wyróżniania innych wizualizacji na stronie.
Na przykład wybranie stanu na wizualizacji mapy powoduje wyróżnienie wykresu kolumnowego i filtruje wykres liniowy, aby wyświetlić tylko te dane, które dotyczą tego jednego stanu.
Zobacz [Informacje o filtrowaniu i wyróżnianiu](power-bi-reports-filters-and-highlighting.md).

Aby zmienić to zachowanie domyślne, użyj kontrolki **Interakcja wizualna**. Interakcje wizualne są dostępne tylko w [Widoku do edycji](service-interact-with-a-report-in-editing-view.md). Jeśli raport został Ci udostępniony, nie będziesz mieć dostępu do interakcji wizualnych.

> [!NOTE]
> Terminy *filtr krzyżowy* i *wyróżnienie krzyżowe* służą do odróżnienia opisanego tutaj zachowania od tego, co się dzieje, gdy używasz okienka **Filtry** do filtrowania i wyróżniania wizualizacji.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Wybierz wizualizację, aby ją uaktywnić.  
2. Włącz kontrolkę **Interakcje wizualne**, wybierając ją na pasku menu u góry. Zwróć uwagę na ikony filtra i wyróżnienia, które pojawią się, gdy ustawisz kursor nad innymi wizualizacjami na stronie raportu.
   
    ![](media/service-reports-visual-interactions/pbi-visual-interaction-icon.png)
3. Ustal, jaki wpływ wybrana wizualizacja powinna mieć na inne.  
   
   * Jeśli powinna filtrować krzyżowo inne wizualizacje, wybierz ikonę **filtru** ![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png).
   * Jeśli powinna wyróżniać krzyżowo tę wizualizację, wybierz ikonę **wyróżnienia** ![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png).
   * Jeśli nie powinna mieć żadnego wpływu, wybierz ikonę **brak wpływu** ![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png).
4. Opcjonalnie powtórz to dla wszystkich innych wizualizacji na stronie raportu.

### <a name="next-steps"></a>Następne kroki
[Jak używać filtrów raportu](power-bi-how-to-report-filter.md)

[Filtry i wyróżnianie w raportach](power-bi-reports-filters-and-highlighting.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

