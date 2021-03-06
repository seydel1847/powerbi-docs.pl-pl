---
title: Typy wglądu w szczegółowe dane obsługiwane przez usługę Power BI
description: Szybki wgląd w szczegółowe dane i wyświetlanie szczegółowych danych przy użyciu usługi Power BI.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 11ae59caf72f2ff96b4674f60d4520484009d877
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54278175"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Typy wglądu w szczegółowe dane obsługiwane przez usługę Power BI
## <a name="how-does-insights-work"></a>Jak działa wgląd w szczegółowe dane?
Usługa Power BI szybko wyszukuje różne podzbiory zestawu danych, stosując zestaw zaawansowanych algorytmów w celu odnajdywania potencjalnie interesujących szczegółowych informacji. Usługa Power BI skanuje zestaw danych jak najszerzej w wyznaczonym czasie.

Wgląd w szczegółowe dane można uruchomić dla kafelka pulpitu nawigacyjnego lub zestawu danych.   

## <a name="what-types-of-insights-can-we-find"></a>Jakie rodzaje wglądu w szczegółowe dane możemy znaleźć?
Oto niektóre z używanych przez nas algorytmów:

## <a name="category-outliers-topbottom"></a>Elementy spoza kategorii (odstające w górę/w dół)
Wyróżnia przypadki, w których dla miary w modelu jeden lub dwa elementy członkowskie wymiaru mają znacznie większe wartości niż pozostałe elementy członkowskie wymiaru.  

![Przykład elementów spoza kategorii](./media/end-user-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Punkty zmian w szeregach czasowych
Wyróżnia punkty znaczących zmian trendów w szeregach czasowych danych.

![Przykład punktów zmian w szeregach czasowych](./media/end-user-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Korelacja
Wykrywa przypadki, w których wiele miar pokazuje korelację między sobą po wykreśleniu względem wymiaru w zestawie danych.

![Przykład korelacji](./media/end-user-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Mała wariancja
Wykrywa przypadki, w których punkty danych nie są dalekie od wartości średniej.

![Przykład małej wariancji](./media/end-user-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Większość (główne współczynniki)
Umożliwia znalezienie przypadków, w którym większość całkowitej wartości można przypisać do pojedynczego współczynnika przy rozbiciu według innego wymiaru.  

![Przykład głównych współczynników](./media/end-user-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Ogólne trendy w szeregach czasowych
Wykrywa trendy rosnące i malejące w danych szeregów czasowych.

![Przykład ogólnych trendów w szeregach czasowych](./media/end-user-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Sezonowość w szeregach czasowych
Znajduje okresowe wzorce w danych szeregu czasowego, takie jak tygodniowa, miesięczna lub roczna sezonowość.

![Przykład sezonowości](./media/end-user-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Stały udział
Wyróżnia przypadki, gdy istnieje korelacja między udziałem wartości podrzędnej w stosunku do całkowitej wartości elementu nadrzędnego w zmiennej ciągłej.

![Przykład stałego udziału](./media/end-user-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Elementy spoza szeregu czasowego
Dla danych w szeregu czasowym wykrywa określone daty lub godziny z wartościami znacząco różnymi od innych wartości dat/godzin.

![Przykład elementów spoza szeregu czasowego](./media/end-user-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Następne kroki
[Wgląd w szczegółowe dane w usłudze Power BI](end-user-insights.md)

Jeśli jesteś właścicielem zestawu danych, [zoptymalizuj go pod kątem wglądu w szczegółowe dane](../service-insights-optimize.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

