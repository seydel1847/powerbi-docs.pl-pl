---
title: Użycie okienka analizy w programie Power BI Desktop
description: Tworzenie dynamicznych linii odwołania dla wizualizacji w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 817e01f83904a8481fa1d0915f671c6761247795
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="using-the-analytics-pane-in-power-bi-desktop"></a>Użycie okienka analizy w programie Power BI Desktop
Za pomocą okienka **Analiza** w programie **Power BI Desktop** możesz dodać do wizualizacji dynamiczne *linie odwołania* i skoncentrować się na ważnych trendach lub szczegółowych informacjach. Okienko **Analiza** znajduje się w obszarze **Wizualizacje** programu Power BI Desktop.

![](media/desktop-analytics-pane/analytics-pane_1.png)

> [!NOTE]
> Okienko **Analiza** jest wyświetlane tylko po wybraniu wizualizacji na kanwie programu Power BI Desktop.

## <a name="search-within-the-analytics-pane"></a>Wyszukiwanie w okienku Analiza
W wersji programu **Power BI Desktop** z lutego 2018 r. (wersji 2.55.5010.201 lub nowszej) można przeprowadzać wyszukiwanie w okienku **Analiza**, które stanowi podsekcję okienka **Wizualizacje**. Jak pokazano na ilustracji poniżej, pole wyszukiwania jest wyświetlane po wybraniu okienka **Analiza**.

![](media/desktop-analytics-pane/analytics-pane_1b.png)

## <a name="using-the-analytics-pane"></a>Używanie okienka Analiza
Za pomocą okienka **Analiza** można utworzyć następujące typy dynamicznych linii odwołania (w przypadku poszczególnych typów wizualizacji są dostępne określone linie):

* Linia stałej (oś X)
* Linia stałej (oś Y)
* Linia minimum
* Linia maksimum
* Linia średniej
* Linia mediany
* Linia percentylu

W poniższych sekcjach przedstawiono, jak można wykorzystać okienko **Analiza** i dynamiczne linie odwołania w swoich wizualizacjach.

Aby wyświetlić dynamiczne linie odwołania dostępne dla danej wizualizacji, wykonaj następujące kroki:

1. Wybierz lub utwórz wizualizację, a następnie wybierz ikonę **Analiza** znajdującą się w sekcji **Wizualizacje**.
   
   ![](media/desktop-analytics-pane/analytics-pane_2.png)
2. Wybierz strzałkę w dół dla tworzonego typu linii, aby rozwinąć dostępne opcje. W tym przypadku wybierzemy pozycję **Linia średniej**.
   
   ![](media/desktop-analytics-pane/analytics-pane_3.png)
3. Aby utworzyć nową linię, wybierz pozycję **+ Dodaj**. Następnie można określić nazwę linii, dwukrotnie klikając pole tekstowe, a następnie wpisując nazwę.
   
   Masz do wyboru wiele różnych opcji dotyczących linii, takich jak *kolor*, *przezroczystość*, *styl* i *pozycja* (względem wizualizacji danych). Możesz też zdecydować, czy linia ma mieć etykietę. Możesz też wybrać opcję **Miara** dla wizualizacji, na której ma bazować linia. W tym celu skorzystaj z listy rozwijanej **Miara**, która jest automatycznie wypełniona przy użyciu elementów danych wizualizacji. W tym przypadku miarą będzie pozycja *Weather*, którą oznaczymy etykietą *Average Weather*. Dostosujemy także kilka innych opcji, co przedstawiono poniżej.
   
   ![](media/desktop-analytics-pane/analytics-pane_4.png)
4. Jeśli chcesz, aby etykieta danych była wyświetlana, przesuń suwak **Etykieta danych**, aby ta opcja była włączona. Jeśli tak zrobisz, uzyskasz dostęp do wielu dodatkowych opcji dotyczących etykiety danych, jak pokazano na poniższej ilustracji.
   
   ![](media/desktop-analytics-pane/analytics-pane_5.png)
5. Zwróć uwagę na liczbę obok elementu **Linia średniej** w okienku **Analiza**. Informuje on, ile dynamicznych linii poszczególnych typów znajduje się obecnie w wizualizacji. Jeśli dodamy element **Linia maksimum** dla pozycji *Cost of Living*, w okienku **Analiza** pojawi się informacja, że wizualizacja została wzbogacona o linię odwołania dynamicznej **Linii maksimum**.
   
   ![](media/desktop-analytics-pane/analytics-pane_6.png)

Jeśli do wybranej wizualizacji nie można zastosować dynamicznych linii odwołania (w tym przypadku wizualizacji **Mapa**), po wybraniu okienka **Analiza** zobaczysz poniższy komunikat.

![](media/desktop-analytics-pane/analytics-pane_7.png)

Istnieją różne rodzaje interesujących danych szczegółowych, które można wyróżnić, tworząc dynamiczne linie odwołania w okienku **Analiza**.

Planujemy wprowadzenie kolejnych funkcji i możliwości. Mamy między innymi zamiar poszerzyć liczbę wizualizacji obsługujących dynamiczne linie odwołania. Warto zatem często sprawdzać, co mamy nowego.

## <a name="apply-forecasting"></a>Stosowanie prognozowania
Możesz użyć funkcji **Prognoza**, wybierając wizualizację, a następnie rozszerzając sekcję **Prognoza** okienka **Analiza**. Możesz określić wiele danych wejściowych, aby zmodyfikować prognozę, np. *Długość prognozy*, *Interwał ufności* i wiele innych. Na poniższej ilustracji przedstawiono podstawową wizualizację liniową z zastosowanym prognozowaniem, ale możesz użyć swojej wyobraźni (i pobawić się funkcją *prognozowania*), aby zobaczyć, jak można zastosować tę funkcję do Twoich modeli.

![](media/desktop-analytics-pane/analytics-pane_8.png)

## <a name="limitations"></a>Ograniczenia
Możliwość używania dynamicznych linii odwołania zależy od typu wizualizacji. Poniższej przedstawiono listę linii dynamicznych dostępnych obecnie dla poszczególnych wizualizacji:

Pełne wykorzystanie linii dynamicznych jest możliwe w przypadku następujących wizualizacji:

* Wykres warstwowy
* Wykres liniowy
* Wykres punktowy
* Wykres kolumnowy grupowany
* Wykres słupkowy grupowany

Poniższe wizualizacje mogą używać jedynie *linii stałej* z okienka **Analiza**:

* Skumulowany warstwowy
* Skumulowany słupkowy
* Skumulowany kolumnowy
* 100% skumulowany słupkowy
* 100% skumulowany kolumnowy

W przypadku poniższych wizualizacji obecnie jest dostępna jedynie opcja *linia trendu*:

* Nieskumulowany liniowy
* Wykres kolumnowy grupowany

Wizualizacje niekartezjańskie nie obsługują obecnie linii dynamicznych z okienka **Analiza**. Są to elementy, takie jak:

* Macierz
* Wykres kołowy
* Pierścień
* tabela

Wiersz percentylu jest dostępny tylko w przypadku używania zaimportowanych danych w programie **Power BI Desktop** lub łączenia na żywo z modelem na serwerze z usługami **Analysis Services 2016** lub nowszymi, usługami **Azure Analysis Services** lub zestawem danych w usłudze Power BI. 

## <a name="next-steps"></a>Następne kroki
Przy użyciu programu Power BI Desktop można wykonywać różnorodne zadania. Aby uzyskać więcej informacji na temat jego możliwości, skorzystaj z następujących zasobów:

* [Co nowego w programie Power BI Desktop](desktop-latest-update.md)
* [Pobieranie programu Power BI Desktop](desktop-get-the-desktop.md)
* [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md)
* [Omówienie zapytań w programie Power BI Desktop](desktop-query-overview.md)
* [Typy danych w programie Power BI Desktop](desktop-data-types.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)
* [Typowe zadania dotyczące zapytań w programie Power BI Desktop](desktop-common-query-tasks.md)    

