---
title: "Używanie szczegółowych informacji w programie Power BI Desktop (wersja zapoznawcza)"
description: "Łatwe uzyskiwanie wglądu w szczegółowe informacje dotyczące wzrostów i spadków w programie Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/25/2017
ms.author: davidi
ms.openlocfilehash: e32cf08625d6d36013175ad9533eac8791e76814
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2017
---
# <a name="use-insights-in-power-bi-desktop-preview"></a>Używanie szczegółowych informacji w programie Power BI Desktop (wersja zapoznawcza)
Program **Power BI Desktop** może wyjaśnić wzrosty i spadki na wykresach oraz dostarczyć szybką, automatyczną, szczegółową analizę danych. Po prostu kliknij prawym przyciskiem myszy punkt danych i wybierz pozycję **Analizuj > Wyjaśnij spadek** (lub wzrost, jeśli poprzedni słupek był niższy), a szczegółowe informacje zostaną wyświetlone w łatwym do obsługi oknie.

![](media/desktop-insights/insights_01.png)

Funkcja szczegółowych informacji jest kontekstowa i jest oparta na bezpośrednio poprzednim punkcie danych, takim jak poprzedni słupek lub kolumna.

> [!NOTE]
> Ta funkcja jest w wersji zapoznawczej i zostanie zmodyfikowana. Funkcja szczegółowych informacji jest domyślnie włączona (nie trzeba otwierać okna wersji zapoznawczej, aby ją włączyć), począwszy od wersji programu **Power BI Desktop** z września 2017 r.
> 
> 

## <a name="using-insights"></a>Korzystanie z funkcji szczegółowych informacji
Aby użyć funkcji szczegółowych informacji, po prostu kliknij prawym przyciskiem myszy dowolny punkt danych na wizualizacji słupkowej lub liniowej i wybierz pozycję **Analizuj > Wyjaśnij wzrost** (lub *Wyjaśnij spadek*, ponieważ wszystkie szczegółowe informacje są oparte na zmianie w stosunku do poprzedniego punktu danych).

![](media/desktop-insights/insights_02.png)

Program **Power BI Desktop** uruchomi algorytmy uczenia maszynowego na odpowiednich danych i wypełni okno wizualizacją i opisem na temat kategorii, które miały największy wpływ na dany spadek lub wzrost. Szczegółowe informacje są domyślnie przekazywane jako wizualizacja *kaskadowa*, jak pokazano na poniższej ilustracji.

![](media/desktop-insights/insights_03.png)

Korzystając z małych ikon w dolnej części tej wizualizacji kaskadowej, można wybrać, aby szczegółowe informacje zostały wyświetlone na wykresie punktowym, skumulowanym kolumnowym lub na wykresie wstążki.

![](media/desktop-insights/insights_04.png)

Za pomocą ikon *kciuk w górę* i *kciuk w dół* znajdujących się w górnej części strony można wyrazić opinię na temat wizualizacji i funkcji.

Przycisk **+** w górnej części wizualizacji umożliwia dodanie wybranej wizualizacji do raportu, tak jak w przypadku wizualizacji utworzonych ręcznie. Następnie wizualizację można formatować lub dopasowywać ją w inny sposób, tak jak każdą inną wizualizację w raporcie. Wybraną wizualizację szczegółowych informacji można dodać tylko podczas edytowania raportu w programie **Power BI Desktop**.

Szczegółowych informacji można używać w trybie do odczytu i w trybie edytowania raportu, dzięki czemu są one uniwersalne zarówno pod kątem analizowania danych, jak i tworzenia wizualizacji, które można łatwo dodawać do raportów.

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia
Ponieważ szczegółowe informacje są oparte na zmianie w stosunku do poprzedniego punktu danych, nie są one dostępne po wybraniu pierwszego punktu danych w wizualizacji. 

Poniżej znajduje się lista scenariuszy, które obecnie nie są obsługiwane przez funkcję **szczegółowych informacji**:

* Filtry TopN
* Filtry uwzględniające/wykluczające
* Filtry miary
* Miary i agregacje nie-addytywne
* Funkcja Pokaż wartość jako
* Miary filtrowane (to nowa funkcja, której używamy dla wykresów punktowych w szczegółowych informacjach)
* Podzielone na kategorie kolumny na osi x, chyba że definiowane jest sortowanie według kolumny, która jest skalarna. W przypadku używania hierarchii każda kolumna w aktywnej hierarchii musi spełniać ten warunek
* Miary nieliczbowe

Ponadto następujące typy modeli i źródła danych nie są obecnie obsługiwane dla szczegółowych informacji:

* Zapytanie bezpośrednie
* Połączenie na żywo
* Lokalne usługi Reporting Services
* Osadzanie

## <a name="next-steps"></a>Następne kroki
Aby uzyskać więcej informacji na temat programu **Power BI Desktop** oraz dowiedzieć się, jak rozpocząć pracę w tym programie, zapoznaj się z następującymi artykułami.

* [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md)
* [Omówienie zapytań w programie Power BI Desktop](desktop-query-overview.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Łączenie się z danymi w programie Power BI Desktop](desktop-connect-to-data.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)
* [Typowe zadania dotyczące zapytań w programie Power BI Desktop](desktop-common-query-tasks.md)   

