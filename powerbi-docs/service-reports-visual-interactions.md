---
title: Zmienianie sposobu interakcji elementów wizualnych w raporcie
description: Dokumentacja ustawiania interakcji wizualizacji w raporcie usługi Microsoft Power BI i w raporcie programu Power BI Desktop.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: N_xYsCbyHPw
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: da525715a5d813c076be1f1ca1bf43ea1270ceae
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284960"
---
# <a name="change-how-visuals-interact-in-a-power-bi-report"></a>Zmienianie sposobu interakcji elementów wizualnych w raporcie usługi Power BI
Jeśli masz uprawnień do edytowania raportu, możesz użyć pozycji **Interakcje wizualne**, aby zmienić sposób wpływania wizualizacji na siebie nawzajem na stronie raportu. 

Domyślnie wizualizacje na stronie raportu mogą służyć do krzyżowego filtrowania i wyróżniania innych wizualizacji na stronie.
Na przykład wybranie stanu na wizualizacji mapy powoduje wyróżnienie wykresu kolumnowego i filtruje wykres liniowy, aby wyświetlić tylko te dane, które dotyczą tego jednego stanu.
Zobacz [Informacje o filtrowaniu i wyróżnianiu](power-bi-reports-filters-and-highlighting.md). A jeśli masz wizualizacje, które obsługują [przechodzenie do szczegółów](consumer/end-user-drill.md), domyślnie przechodzenie do szczegółów jednej wizualizacji nie ma wpływu na inne wizualizacje na stronie raportu. Oba te zachowania domyślne można przesłonić, a interakcje skonfigurować dla poszczególnych wizualizacji.

W tym artykule przedstawiono sposób użycia **Interakcji wizualnych** w [Widoku do edycji](service-interact-with-a-report-in-editing-view.md) usługi Power BI i w programie Power BI Desktop. Jeśli raport został Ci udostępniony, nie będzie można zmienić ustawień interakcji wizualnych.

> [!NOTE]
> Terminy *filtr krzyżowy* i *wyróżnienie krzyżowe* służą do odróżnienia opisanego tutaj zachowania od tego, co się dzieje, gdy używasz okienka **Filtry** do filtrowania i wyróżniania wizualizacji.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Wybierz wizualizację, aby ją uaktywnić.  
2. Wyświetl opcje **Interakcji wizualnych**.
    - W usłudze Power BI wybierz listę rozwijaną z paska menu raportu.

       ![Lista rozwijana Interakcje wizualne](media/service-reports-visual-interactions/power-bi-visual-interaction.png)

    - W programie Desktop wybierz pozycje **Format > Interakcje**.

        ![wybieranie pozycji Format, a następnie pozycji Interakcje](media/service-reports-visual-interactions/pbi-visual-interaction-desktop.png)

3. Aby włączyć kontrolki interakcji wizualizacji, wybierz pozycję **Edytuj interakcje**. Usługa Power BI dodaje ikony filtru i wyróżnienia krzyżowego do wszystkich innych wizualizacji na stronie raportu.
   
    ![raport z włączonymi interakcjami wizualnymi](media/service-reports-visual-interactions/power-bi-icons-on.png)
3. Ustal, jaki wpływ wybrana wizualizacja powinna mieć na inne.  Opcjonalnie powtórz to dla wszystkich innych wizualizacji na stronie raportu.
   
   * Jeśli powinna filtrować krzyżowo wizualizacje, wybierz ikonę **filtru** ![ikona filtru](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png).
   * Jeśli powinna wyróżniać krzyżowo tę wizualizację, wybierz ikonę **wyróżnienia** ![ikona wyróżnienia](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png).
   * Jeśli nie powinna mieć żadnego wpływu, wybierz ikonę **brak wpływu** ![ikona braku wpływu](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png).

4. Aby włączyć kontrolki przechodzenia do szczegółów, wybierz pozycję **Przechodzenie do szczegółów filtruje inne elementy wizualne**.  Teraz po przejściu do szczegółów (i uogólnieniu) wizualizacji inne wizualizacje na stronie raportu zmienią się, aby odzwierciedlić bieżący wybór przechodzenia do szczegółów. 

   ![wideo dotyczące włączania kontrolek przechodzenia do szczegółów](media/service-reports-visual-interactions/drill2.gif)

