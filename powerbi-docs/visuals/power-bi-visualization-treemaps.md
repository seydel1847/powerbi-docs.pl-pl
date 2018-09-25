---
title: Mapy drzewa w usłudze Power BI
description: Mapy drzewa w usłudze Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 01/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 946746b1c868ca5310edd929434cc852400b5bc3
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2018
ms.locfileid: "46548079"
---
# <a name="treemaps-in-power-bi"></a>Mapy drzewa w usłudze Power BI
Mapy drzewa prezentują dane hierarchiczne w formie zestawu zagnieżdżonych prostokątów.  Każdy poziom hierarchii jest przedstawiany jako kolorowy prostokąt (często określany jako „gałąź”) zawierający inne prostokąty („liście”).  Obszar wewnątrz każdego prostokąta jest przydzielany na podstawie mierzonych wartości ilościowych, przy czym prostokąty ułożone są według ich rozmiaru, od lewego górnego rogu (największy) do prawego dolnego rogu (najmniejszy).

![](media/power-bi-visualization-treemaps/pbi-nancy_viz_treemap.png)

Jeśli na przykład analizujemy sprzedaż, za prostokąty najwyższego poziomu (gałęzie) możemy przyjąć kategorie odzieży: **Urban**, **Rural**, **Youth** i **Mix**.  Prostokąty kategorii mogą zawierać mniejsze prostokąty (liście) odpowiadające producentom odzieży w ramach danej kategorii, a rozmiar oraz cieniowanie tych prostokątów będzie zależeć od wielkości sprzedaży.  W ramach gałęzi **Urban** powyżej sprzedano najwięcej ubrań Maximus, nieco mniej Natura i Fama, a bardzo niewiele Leo.  Tak więc gałąź **Urban** na naszej mapie drzewa będzie zawierać największy prostokąt dla odzieży Maximus (w lewym górnym rogu), nieco mniejsze prostokąty dla odzieży Natura i Fama, szereg innych prostokątów odpowiadających pozostałej sprzedanej odzieży oraz niewielki prostokąt dla odzieży Leo.  Możemy porównać wielkość sprzedaży poszczególnych kategorii odzieży, porównując rozmiar i cieniowanie każdego węzła liścia; im większy prostokąt i ciemniejsze cieniowanie, tym wyższa wartość.

## <a name="when-to-use-a-treemap"></a>Kiedy używać mapy drzewa
Mapy drzewa są doskonałym wyborem:

* do wyświetlania dużych ilości danych hierarchicznych.
* gdy wykres słupkowy nie jest w stanie skutecznie zaprezentować dużej liczby wartości.
* do pokazania proporcji między poszczególnymi częściami i całością.
* do pokazania schematu rozkładu miary dla każdego poziomu kategorii w hierarchii.
* do pokazania atrybutów z użyciem kodowania kolorami i rozmiarami.
* do odnajdywania schematów, odstających wartości, najważniejszych elementów oraz wyjątków.

### <a name="prerequisites"></a>Wymagania wstępne
 - Usługa Power BI lub program Power BI Desktop
 - Przykład Retail Analysis

## <a name="create-a-basic-treemap"></a>Tworzenie podstawowej mapy drzewa
Czy chcesz najpierw obejrzeć, jak ktoś inny tworzy mapę drzewa?  Przewiń film wideo do 2:10, aby zobaczyć, jak Amanda tworzy mapę drzewa.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

Możesz również utworzyć własną mapę drzewa. W poniższych instrukcjach używane są przykładowe dane dotyczące analizy handlu detalicznego. Aby można było wykonać te instrukcje, zaloguj się w usłudze Power BI (nie w programie Desktop) i wybierz opcję **Pobierz dane \> Przykłady \> Próbka analizy handlu detalicznego \> Połącz \> Przejdź do pulpitu nawigacyjnego**. Tworzenie wizualizacji w raporcie wymaga uprawnień do edytowania zestawu danych i raportu. Na szczęście przykłady usługi Power BI można edytować. Jeśli jednak ktoś udostępni Ci raport, nie będziesz mieć możliwości dodawania nowych wizualizacji.

1. Wybierz kafelek „Total stores”, aby otworzyć przykładowy raport analizy handlu detalicznego.    
2. Otwórz [Widok do edycji](../service-interact-with-a-report-in-editing-view.md) i wybierz miarę **Sales** > **Last Years Sales**.   
   ![](media/power-bi-visualization-treemaps/treemapfirstvalue_new.png)   
3. Przekonwertuj wykres na mapę drzewa.  
   ![](media/power-bi-visualization-treemaps/treemapconvertto_new.png)   
4. Przeciągnij pozycję **Item** > **Category** do obszaru **Grupa**. Usługa Power BI tworzy mapę drzewa, na której rozmiar prostokątów odzwierciedla całkowitą sprzedaż, a kolor oznacza kategorię.  W ten sposób utworzyliśmy hierarchię, która prezentuje wizualnie względną wielkość całkowitej sprzedaży według kategorii.  Kategoria **Mens** ma najwyższą sprzedaż, zaś kategoria **Hosiery** najniższą.   
   ![](media/power-bi-visualization-treemaps/treemapcomplete_new.png)   
5. Przeciągnij pozycję **Store** > **Chain** do obszaru **Szczegóły**, aby dokończyć mapę drzewa. Teraz możesz porównać sprzedaż z ostatniego roku według kategorii i sieci.   
   ![](media/power-bi-visualization-treemaps/treemap_addgroup_new.png)
   
   > [!NOTE]
   > Pozycje Nasycenie koloru i Szczegóły nie mogą być używane jednocześnie.
   > 
   > 
5. Umieść kursor nad obszarem **Chain**, aby wyświetlić etykietkę narzędzia tej części dla wartości **Category**.  Na przykład umieszczenie kursora nad pozycją **Lindseys** w prostokącie **040-Juniors** wyświetli etykietkę narzędzia dla części Lindsey kategorii Juniors.  
   ![](media/power-bi-visualization-treemaps/treemaphoverdetail_new.png)
6. [Dodaj mapę drzewa jako kafelek pulpitu nawigacyjnego (przypnij wizualizację)](../consumer/end-user-tiles.md). 
7. [Zapisz raport](../service-report-save.md).

## <a name="highlighting-and-cross-filtering"></a>Wyróżnianie i filtrowanie krzyżowe
Aby uzyskać informacje o korzystaniu z okienka filtrów, zobacz [Dodawanie filtra do raportu](../power-bi-report-add-filter.md).

Wyróżnienie elementu Category lub Details na mapie drzewa spowoduje wyróżnienie krzyżowe i filtrowanie krzyżowe pozostałych wizualizacji na stronie raportu... i na odwrót. Aby to sprawdzić, dodaj wizualizacje na tej samej stronie lub skopiuj/wklej mapę drzewa na stronie raportu zawierającej już inne wizualizacje.

1. Na mapie drzewa zaznacz element Category lub Chain w ramach wartości Category.  Spowoduje to wyróżnienie krzyżowe innych wizualizacji na stronie. Wybierając na przykład pozycję **050-Shoes**, wyświetlimy informacje, że sprzedaż butów w zeszłym roku wyniosła 3 640 471 USD, z czego 2 174 185 USD w ramach sieci Fashions Direct.  
   ![](media/power-bi-visualization-treemaps/treemaphiliting.png)

2. Na wykresie kołowym **Last Year Sales by Chain** wybierz wycinek **Fashions Direct**.  
   ![](media/power-bi-visualization-treemaps/treemapnoowl.gif)    

3. Aby zarządzać sposobem, w jaki odbywa się wzajemne wyróżnianie krzyżowe i filtrowanie krzyżowe dla wykresów, zobacz [Interakcje wizualizacji w raporcie usługi Power BI](../consumer/end-user-interactions.md)

## <a name="next-steps"></a>Następne kroki
[Przypinanie wizualizacji do pulpitu nawigacyjnego](../service-dashboard-pin-tile-from-report.md)  
[Power BI — podstawowe pojęcia](../consumer/end-user-basic-concepts.md)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)  

