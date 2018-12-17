---
title: Duże zestawy danych, limity punktów danych i strategie danych
description: Limity danych dla wizualizacji i strategie redukcji danych
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 125787bab3892f2e9616866a9d5487837131d0ed
ms.sourcegitcommit: 4f46d71ff6026c1c158f007425aefdcb501f48ee
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2018
ms.locfileid: "52981496"
---
# <a name="data-point-limits-and-strategies-by-visual-type"></a>Limity punktów danych i strategie według typu wizualizacji

W przypadku renderowania wizualizacji w usłudze Power BI wizualizacja musi być szybka i dokładna. Wymaga to skonfigurowania podstawowych algorytmów dla każdego typu wizualizacji. Wizualizacje w usłudze Power BI muszą być wystarczająco elastyczne, aby obsługiwać różne rozmiary zestawów danych. Niektóre zestawy danych mają tylko kilka punktów danych, a inne zestawy danych mają petabajty punktów danych. W tym artykule opisano strategie używane przez usługę Power BI do renderowania wizualizacji.

## <a name="data-reduction-strategies"></a>Strategie redukcji danych
W każdej wizualizacji jest stosowana co najmniej jedna *strategia redukcji danych* w celu obsługi potencjalnie dużych woluminów analizowanych danych. Nawet prosta tabela stosuje strategię pozwalającą uniknąć ładowania całego zestawu danych do klienta.  Używana strategia redukcji różni się w zależności od typu wizualizacji. Każda wizualizacja wybiera strategię spośród dostępnych *strategii redukcji danych* jako część generowania żądania danych wysyłanego do serwera. 

Każda wizualizacja kontroluje parametry tych strategii, aby wpływać na ogólną ilość danych.   

## <a name="strategies"></a>Strategie
Każda strategia ma wartości domyślne oparte na kształcie i typie wizualizowanych danych. Jednak wartości domyślne można przesłonić w okienku formatowania programu Power BI, aby zaoferować użytkownikowi odpowiednie środowisko. 

* **Obsługa okien danych** (segmentacja): Pozwala użytkownikom na przewijanie danych w wizualizacji przez stopniowe ładowanie fragmentów ogólnego zestawu danych.
* **TopN**: Pokaż tylko pierwsze N elementów
* **Prosty przykład**: Pokaż pierwsze, ostatnie i N równomiernie rozłożonych elementów.
* **BottomN**: Pokaż tylko ostatnie N elementów.  Przydatne w przypadku monitorowania często aktualizowanych danych.
* **Próbkowanie o wysokiej gęstości** — ulepszony algorytm próbkowania, który w większym stopniu przestrzega elementów odstających i/lub kształtu krzywej.
    * **Próbkowanie liniowe z podziałem na przedziały** — przykładowe punkty danych oparte na wartościach odstających w przedziałach na osi
    * **Próbkowanie nakładających się punktów** — przykładowe punkty danych oparte na nakładających się wartościach w celu zachowania elementów odstających

## <a name="statistics"></a>Statystyczne
Niektóre modele mogą oferować statystyki dotyczące wartości niektórych kolumn. Jeśli takie informacje są dostępne, będziemy ich używać w celu zapewnienia skuteczniejszego równoważenia w obrębie wielu hierarchii, jeśli wizualizacja nie będzie jawnie przesłaniać liczby wartości dla strategii.

Aby uzyskać więcej informacji, zobacz [What's new in Analysis Services](https://docs.microsoft.com/en-us/sql/analysis-services/what-s-new-in-analysis-services?view=sql-server-2017) (Co nowego w usługach Analysis Services)

## <a name="dynamic-limits"></a>Limity dynamiczne
Oprócz powyższych strategii wizualizacje z dwoma hierarchiami kolumn grupowania (oś i legenda lub kategoria i seria) używają jednej dodatkowej strategii o nazwie *Limity dynamiczne*.  Limity dynamiczne zostały opracowane w celu skuteczniejszego równoważenia punktów danych. 

Limity dynamiczne oferują lepszy wybór punktów danych rozrzedzonych niż limity statyczne. Na przykład wizualizację można skonfigurować do wybierania 100 kategorii i 10 serii z łączną liczbą 1000 punktów. Ale rzeczywiste dane mają 50 kategorii i 20 serii.  W czasie wykonywania zapytania limity dynamiczne wybierają wszystkie 20 serii, aby wypełnić 1000 żądanych punktów.

Limity dynamiczne są stosowane automatycznie, gdy serwer jest w stanie zgodnym z poniższym opisem:

* W programie Power BI Desktop z lokalnymi usługami SSAS w wersji 2016 lub nowszej, która [korzysta z możliwości serwera SuperDax](https://blogs.msdn.microsoft.com/analysisservices/2015/09/02/whats-new-in-microsoft-sql-server-analysis-services-tabular-models-in-sql-server-2016-ctp-2-3/)

* W programie Desktop i usłudze Power BI w przypadku korzystania z zaimportowanego modelu, trybu Direct Query, połączenia na żywo z usługą lub połączenia na żywo z usługą AS PaaS. 

* W usłudze Power BI w przypadku nawiązywania połączenia za pośrednictwem bramy lokalnej z lokalnymi usługami SSAS nie możemy używać limitów dynamicznych. Brama lokalna nie obsługuje w pełni strategii limitów dynamicznych, która zwraca strukturę zestawów wyników inną niż usługi SSAS w środowisku lokalnym.  

## <a name="strategies-and-data-point-limits-by-visual-type"></a>Strategie i limity punktów danych według typu wizualizacji

### <a name="area-chart"></a>Wykres warstwowy
Zobacz sekcję [Jak działa próbkowanie liniowe](../desktop-high-density-sampling.md#how-the-new-line-sampling-algorithm-works)

### <a name="barcolumn-chart"></a>Wykres słupkowy/kolumnowy
- W trybie podziału na kategorie
    - Kategorie: Wirtualizacja przez użycie okna z 500 wierszami jednocześnie
    - Seria: 60 pierwszych
    - W trybie skalarnym (może używać limitów dynamicznych)
        - Maksymalna liczba punktów: 10 000
        - Kategorie: Przykład 500 wartości
        - Seria: 20 pierwszych wartości

### <a name="card-multirow"></a>Karta (z wieloma wierszami) 
- Wartości: Wirtualizacja przez użycie okna z 200 wierszami jednocześnie

### <a name="combo-chart"></a>Wykres kombi
 Używa tej samej strategii co wykres kolumnowy. Zauważ, że wiersz na **wykresie kombi** nie używa algorytmu o wysokiej gęstości, który stosuje **wykres liniowy**.

### <a name="custom-visuals"></a>Wizualizacje niestandardowe
Może osiągnąć wartość 30 000, ale wskazanie strategii do użycia należy do autorów wizualizacji

### <a name="doughnut"></a>Pierścieniowy
- Maksymalna liczba punktów: 3500
- Grupa: 500 pierwszych
- Szczegóły: 20 pierwszych

### <a name="filled-map-choropleth"></a>Kartogram 
W obrębie kartogramu można używać statystyk lub limitów dynamicznych. Usługa Power BI podejmie próbę użycia funkcji redukcji w następującej kolejności: limity dynamiczne, statystyk i konfiguracja jako ostatnia. 
- Maksymalna liczba punktów: 10 000
- Kategorie: 500 pierwszych
- Seria (jeśli obecne są osie X i Y): 20 pierwszych

### <a name="funnel"></a>Lejek
- Maksymalna liczba punktów: 3500
- Kategorie: 3500 pierwszych

### <a name="kpi"></a>KPI
- Oś trendu
- 3500 ostatnich

### <a name="line-chart"></a>Wykres liniowy
Zobacz sekcję [Jak działa próbkowanie liniowe](../desktop-high-density-sampling.md#how-the-new-line-sampling-algorithm-works)

### <a name="line-chart-high-density"></a>Wykres liniowy, wysoka gęstość
Zobacz temat [Próbkowanie o wysokiej gęstości](../desktop-high-density-sampling.md)

### <a name="map"></a>Mapa 
- Maksymalna liczba punktów: 3500

W zależności od konfiguracji mapa może mieć następujące elementy:
- Lokalizacja: 3500 pierwszych
- Lokalizacja, rozmiar: 3500 pierwszych
- Operacje agregowania lokalizacji, długości geograficznej i szerokości geograficznej (+/- rozmiar): 3500 pierwszych
- Szerokość geograficzna, długość geograficzna: zobacz [Wykres punktowy o wysokiej gęstości](desktop-high-density-scatter-charts.md)
- Szerokość geograficzna, długość geograficzna, rozmiar: 3500 pierwszych
- Legenda, szerokość geograficzna, długość geograficzna: zobacz [Wykres punktowy o wysokiej gęstości](desktop-high-density-scatter-charts.md)
- Legenda, szerokość geograficzna, długość geograficzna, rozmiar: 233 pierwsze legendy, 15 pierwszych szerokości geograficznych i długości geograficznych (mogą być używane statystyki lub limity dynamiczne)
- Lokalizacja, legenda, długość geograficzna, szerokość geograficzna jako operacje agregacji (+/- rozmiar): 233 pierwsze lokalizacje, 15 pierwszych legend (mogą być używane statystyki lub limity dynamiczne)

### <a name="matrix"></a>Macierz
- Wiersze: Wirtualizacja przez użycie okna z 500 wierszami jednocześnie
- Kolumny: 100 pierwszych kolumn grupowania 
- Wartości: wiele wartości nie jest uwzględnianych w ramach redukcji danych

### <a name="radial-gauge"></a>Miernik promieniowy
Brak strategii redukcji

### <a name="slicer"></a>Fragmentator
- Wartości: Wirtualizacja przez użycie okna z 200 wierszami jednocześnie

### <a name="scatter-chart-high-density"></a>Wykres punktowy (wysoka gęstość)
Zobacz [Wykres punktowy o wysokiej gęstości](https://docs.microsoft.com/en-us/power-bi/visuals/desktop-high-density-scatter-charts)

### <a name="pie"></a>Kołowy
- Maksymalna liczba punktów: 3500
- Grupa: 500 pierwszych
- Szczegóły: 20 pierwszych

### <a name="r--python-visuals"></a>Wizualizacje w językach R i Python
Ograniczone do 150 000 wierszy. Jeśli wybrano więcej niż 150 000 wierszy, zostanie użytych tylko 150 000 pierwszych wierszy

### <a name="ribbon-chart"></a>Wykres wstążkowy
- W trybie podziału na kategorie
    - Kategorie: Wirtualizacja (obsługa okien danych) przez użycie okna z 500 wierszami jednocześnie
    - Seria: 60 pierwszych
    - W trybie skalarnym (może używać limitów dynamicznych)
        - Maksymalna liczba punktów: 10 000
        - Kategorie: Przykład 500 wartości
        - Seria: 20 pierwszych wartości

### <a name="shape-map"></a>Mapa kształtów
W obrębie kartogramu można używać statystyk lub limitów dynamicznych. 
- Maksymalna liczba punktów: 10 000
- Kategorie: 500 pierwszych
- Seria (jeśli obecne są osie X i Y): 20 pierwszych

### <a name="table"></a>Tabela
- Wartości: Wirtualizacja (obsługa okien danych) przez użycie okna z 500 wierszami jednocześnie

### <a name="tree-map-this-could-use-statistics-or-dynamic-limits"></a>Mapa drzewa (mogą być używane statystyki lub limity dynamiczne)
- Maksymalna liczba punktów: 3500
- Grupa: 500 pierwszych
- Szczegóły: 20 pierwszych

### <a name="waterfall-chart"></a>Wykres kaskadowy
- Jeśli istnieje tylko jeden zasobnik kategorii
    - Maksymalna liczba punktów: 3500
    - Tylko kategoria — 3500 pierwszych
- Jeśli istnieje kategoria i podział
    - Kategoria: Wirtualizacja (obsługa okien danych) przez użycie okna z 30 wierszami jednocześnie
    - Podział — 200 pierwszych wartości


## <a name="next-steps"></a>Następne kroki
[Typy wizualizacji](power-bi-report-visualizations.md)
