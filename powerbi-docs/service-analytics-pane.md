---
title: Okienko Analiza w usłudze Power BI
description: Tworzenie dynamicznych linii odwołania dla wizualizacji w usłudze Power BI
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2017
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 37f4663a176e81f2c235111092fcfa5576bfe08a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34244523"
---
# <a name="analytics-pane-in-power-bi-service"></a>Okienko Analiza w usłudze Power BI
Za pomocą okienka **Analiza** w **usłudze Power BI** możesz dodać do wizualizacji dynamiczne *linie odwołania* i skoncentrować się na ważnych trendach lub szczegółowych informacjach.

![](media/service-analytics-pane/power-bi-analytics-pane.png)

> [!NOTE]
> Okienko **Analiza** jest wyświetlane tylko po wybraniu wizualizacji na kanwie raportów.
> 
> 

## <a name="using-the-analytics-pane"></a>Używanie okienka Analiza
Za pomocą okienka **Analiza** można utworzyć następujące typy dynamicznych linii odwołania (w przypadku poszczególnych typów wizualizacji są dostępne określone linie):

* Linia stałej (oś X)
* Linia stałej (oś Y)
* Linia minimum
* Linia maksimum
* Linia średniej
* Linia mediany
* Linia percentylu


Aby wyświetlić dynamiczne linie odwołania dostępne dla danej wizualizacji, wykonaj następujące kroki:

1. Wybierz lub utwórz wizualizację, a następnie wybierz ikonę **Analiza** ![](media/service-analytics-pane/power-bi-analytics-icon.png) znajdującą się w okienku **Wizualizacje**.

2. Wybierz strzałkę w dół dla tworzonego typu linii, aby rozwinąć dostępne opcje. W tym przypadku wybierzemy pozycję **Linia średniej**.
   
   ![dodawanie linii średniej](media/service-analytics-pane/power-bi-add.png)

3. Aby utworzyć nową linię, wybierz pozycję **+ Dodaj** i wybierz miarę do użycia podczas tworzenia wiersza.  Lista rozwijana **Miara** jest automatycznie wypełniana przy użyciu dostępnych danych z wybranej wizualizacji. Użyjmy wartości **Open store count**.

5. Masz do wyboru wiele różnych opcji linii, takich jak kolor, przezroczystość, styl i pozycja (względem elementów danych wizualizacji). Jeśli chcesz oznaczyć linię etykietą, nadaj jej tytuł, a następnie przenieś suwak **Etykieta danych** do pozycji **Wł.**  W tym przypadku oznaczymy linię etykietą *Avg # Open Stores*. Dostosujemy także kilka innych opcji, co przedstawiono poniżej.
   
   ![dostosowywanie analizy Linia średniej](media/service-analytics-pane/power-bi-average-line2.png)

1. Zwróć uwagę na liczbę obok elementu **Linia średniej** w okienku **Analiza**. Informuje on, ile dynamicznych linii poszczególnych typów znajduje się obecnie w wizualizacji. Jeśli dodamy element **Linia stałej** w celu wyznaczenia docelowej liczby sklepów równiej 9, w okienku **Analiza** pojawi się informacja, że wizualizacja została wzbogacona o linię odwołania **Linia stałej**.
   
   ![](media/service-analytics-pane/power-bi-reference-lines.png)
   

Istnieją różne rodzaje interesujących danych szczegółowych, które można wyróżnić, tworząc dynamiczne linie odwołania w okienku **Analiza**.

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów

Jeśli do wybranej wizualizacji nie można zastosować dynamicznych linii odwołania (w tym przypadku wizualizacji **Mapa**), po wybraniu okienka **Analiza** zobaczysz poniższy komunikat.
   
![analiza niedostępna](media/service-analytics-pane/power-bi-no-lines.png)

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
* Tabela

## <a name="next-steps"></a>Następne kroki
[Okienko analizy w programie Power BI Desktop](desktop-analytics-pane.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

