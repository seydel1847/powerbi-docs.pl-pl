---
title: Jak wizualizacje stosują filtrowanie krzyżowe wobec siebie w raporcie (dla użytkowników raportu)
description: Dokumentacja dla użytkowników końcowych usługi Power BI, w której wyjaśniono sposób interakcji z wizualizacjami na stronie raportu.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 838b881622dd19eb881aa53ac895f223cf9bc460
ms.sourcegitcommit: f25464d5cae46691130eb7b02c33f42404011357
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2018
ms.locfileid: "53180512"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Jak wizualizacje stosują filtrowanie krzyżowe wobec siebie w raporcie usługi Power BI
Jedną z przydatnych funkcji usługi Power BI jest sposób, w jaki są ze sobą połączone wszystkie wizualizacje na stronie raportu. Jeśli wybierzesz punkt danych na jednej z wizualizacji, wszystkie pozostałe wizualizacje na stronie zawierające te dane zostaną zmienione w oparciu o ten wybór. 

![wideo: interakcja z wizualizacjami](media/end-user-interactions/interactions.gif)

Domyślnie wizualizacje na stronie raportu mogą służyć do filtrowania i wyróżniania krzyżowego oraz przechodzenia do szczegółów innych wizualizacji na stronie. Na przykład wybranie stanu na wizualizacji mapy powoduje wyróżnienie wykresu kolumnowego i filtruje wykres liniowy, aby wyświetlić tylko dane dotyczące tego jednego stanu.

Zobacz [Informacje o filtrowaniu i wyróżnianiu](../power-bi-reports-filters-and-highlighting.md). A jeśli masz wizualizacje, które obsługują [przechodzenie do szczegółów](../power-bi-visualization-drill-down.md), domyślnie przechodzenie do szczegółów jednej wizualizacji nie ma wpływu na inne wizualizacje na stronie raportu. 

Sposób interakcji z wizualizacjami na stronie jest ustawiany przez *projektanta* raportu. Projektanci mają możliwość włączania i wyłączania interakcji wizualizacji oraz zmiany domyślnego zachowania filtrowania i wyróżniania krzyżowego oraz przechodzenia do szczegółów.
  
> [!NOTE]
> Terminy *filtr krzyżowy* i *wyróżnienie krzyżowe* służą do odróżnienia opisanego tutaj zachowania od tego, co się dzieje, gdy używasz okienka **Filtry** do filtrowania i wyróżniania wizualizacji.  

### <a name="next-steps"></a>Następne kroki
[Jak używać filtrów raportu](../power-bi-how-to-report-filter.md)
