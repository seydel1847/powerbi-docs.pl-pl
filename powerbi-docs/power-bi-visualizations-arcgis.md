---
title: "Interakcje z udostępnioną mapą ArcGIS"
description: "Używanie mapy ArcGis w widoku do czytania "
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: power bi, service, desktop, mobile
featuredvideoid: 
qualityfocus: monitoring
qualitydate: 06/23/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/23/2017
ms.author: mihart
ms.openlocfilehash: 511f01494410215451d9f77ff637c7cfce8e89b3
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="interacting-with-arcgis-maps-in-power-bi"></a>Interakcje z mapami ArcGIS w usłudze Power BI
Ten temat przedstawia perspektywę osoby *korzystającej* z mapy ArcGIS w usłudze Power BI, programie Desktop lub aplikacji mobilnej. Jeśli twórca mapy ArcGIS udostępni Ci ją, możesz z niej korzystać na wiele sposobów.  Aby dowiedzieć się więcej na temat tworzenia mapy ArcGIS, zobacz [ArcGIS maps by esri tutorial (Samouczek Mapy ArcGIS firmy Esri)](power-bi-visualization-arcgis.md).

Kombinacja map ArcGIS i usługi Power BI przenosi tworzenie map na zupełnie nowy poziom wykraczający poza prezentację punktów na mapie. Dostępne opcje obejmujące mapy podstawowe, typy lokalizacji, motywy, style symboli i warstwy referencyjne pozwalają tworzyć okazałe i bogate w informacje wizualizacje map. Połączenie autorytatywnych warstw danych (na przykład dotyczących spisu) na mapie z analizą przestrzenną umożliwia lepsze zrozumienie danych używanych w wizualizacji.

> [!TIP]
> GIS (ang. Geographic Information Science) to inaczej system informacji geograficznej.
> 
> 

W tym przykładzie używamy mapy ArcGIS utworzonej w [samouczku firmy Esri dotyczącym map ArcGIS](power-bi-visualization-arcgis.md). Przedstawia ona zeszłoroczną sprzedaż w poszczególnych miastach przy użyciu podstawowej mapy ulicznej, symboli bąbelków reprezentujących wielkość i warstwy referencyjnej prezentującej średni dochód na gospodarstwo domowe. Mapy zawiera trzy pinezki i jedno (purpurowe) koło przedstawiające czas dojazdu.

![](media/power-bi-visualizations-arcgis/power-bi-arcgis-esri-new.png)

> [!TIP]
> Odwiedź [stronę firmy Esri dotyczącą usługi Power BI](https://www.esri.com/powerbi), aby zobaczyć szereg przykładów i przeczytać opinie klientów. Następnie zobacz stronę firmy Esri [ArcGIS Maps for Power BI Getting Started page (Wprowadzenie do komponentu ArcGIS Maps for Power BI)](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm).
> 
> 

<br/>

## <a name="user-consent"></a>Zgoda użytkownika
Gdy współpracownik udostępni Ci mapę ArcGIS po raz pierwszy, usługa Power BI wyświetli monit. Komponent ArcGIS Maps for Power BI jest dostarczany przez firmę [Esri](https://www.esri.com) i korzystanie z niego podlega ogólnym warunkom oraz zasadom ochrony prywatności firmy Esri. Użytkownicy usługi Power BI, którzy chcą korzystać z wizualizacji komponentu ArcGIS Maps for Power BI, muszą zaakceptować okno dialogowe ze zgodą.

## <a name="selection-tools"></a>Narzędzia wyboru
Komponent ArcGIS Maps for Power BI udostępnia trzy tryby wybierania. Maksymalnie można zaznaczyć 250 punktów danych jednocześnie.

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-tools2.png)

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-single2.png) Umożliwia wybranie poszczególnych punktów danych.

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-marquee2.png) Rysuje prostokąt na mapie i wybiera zawarte w nim punkty danych. Użyj klawisza CTRL, aby wybrać więcej niż jeden prostokątny obszar.

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-reference-layer2.png) Umożliwia użycie granic lub wielokątów w ramach warstwy referencyjnej w celu wybrania zawartych w nich punktów danych.

<br/>

## <a name="interacting-with-an-arcgis-map"></a>Interakcja z mapą ArcGIS
Dostępne funkcje zależą od tego, czy jest się *twórcą* (osobą, która stworzyła mapę) czy *użytkownikiem* (któremu ktoś inny udostępnił mapę ArcGIS). Jeśli korzystasz z mapy ArcGIS jako użytkownik (w [widoku do czytania](service-interact-with-a-report-in-reading-view.md)), możesz wykonywać następujące akcje.

* Podobnie jak w przypadku innych typów wizualizacji, mapy można [przypinać do pulpitów nawigacyjnych](service-dashboard-pin-tile-from-report.md) oraz wyświetlać w [trybie koncentracji uwagi](service-focus-mode.md) i [na pełnym ekranie](service-fullscreen-mode.md). Można też [wyświetlać](service-reports-show-data.md) i/lub [eksportować ich dane źródłowe](power-bi-visualization-export-data.md).    
* Rozwiń okienko **Filtry**, aby eksplorować mapy przy użyciu filtrów. Po zamknięciu raportu zastosowane filtry nie są zapisywane.    
    ![](media/power-bi-visualizations-arcgis/power-bi-filter-newer.png)  
* Jeśli mapa ma warstwę referencyjną, wybierz lokalizacje, aby wyświetlić szczegóły w etykietce narzędzia. Poniżej wybraliśmy hrabstwo Adams, aby wyświetlić dane dotyczące średniego dochodu na gospodarstwo domowe zawarte w warstwie referencyjnej, którą dodał twórca mapy.
  
    ![](media/power-bi-visualizations-arcgis/power-bi-reference-layer.png)  
  
    W tym przypadku mamy również wykres. Wybierz słupek na wykresie, aby wyświetlić szczegółowe dane. Widać, że 79 gospodarstw domowych w hrabstwie Adams uzyskuje dochód na poziomie co najmniej 200 000 USD.
  
    ![](media/power-bi-visualizations-arcgis/power-bi-tooltip-chart.png)
  
    Wybierz strzałkę, aby wyświetlić dodatkowe wykresy.
* Aby wyświetlić szczegółowe informacje w etykietce narzędzia, umieść kursor nad symbolem lokalizacji na mapie podstawowej.     
  ![](media/power-bi-visualizations-arcgis/power-bi-arcgis-hover.png)
  
  > [!TIP]
  > Wybranie konkretnej lokalizacji może wymagać powiększenia wyświetlanego obszaru.  Jeśli lokalizacje nakładają się na siebie, usługa Power BI może wyświetlać więcej niż jedną etykietkę narzędzia naraz. Aby przechodzić między etykietkami narzędzi, wybieraj strzałki.
  > 
  > ![](media/power-bi-visualizations-arcgis/power-bi-3-screens.png)
  > 
  > 
* Jeśli twórca dodał do mapy ArcGIS warstwę infografiki, w prawym górnym rogu mapy zostaną wyświetlone dodatkowe dane.  W tym przykładzie twórca mapy dodał informacje o dzieciach poniżej 14 lat.
  
    ![](media/power-bi-visualizations-arcgis/power-bi-demographics.png)

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia
Komponent ArcGIS Maps for Power BI jest dostępny w ramach następujących usług i aplikacji:

<table>
<tr><th>Usługa/aplikacja</th><th>Dostępność</th></tr>
<tr>
<td>Power BI Desktop</td>
<td>Tak</td>
</tr>
<tr>
<td>Usługa Power BI (PowerBI.com)</td>
<td>Tak</td>
</tr>
<tr>
<td>Aplikacje mobilne Power BI</td>
<td>Tak</td>
</tr>
<tr>
<td>Usługa Power BI — publikowanie w Internecie</td>
<td>Nie</td>
</tr>
<tr>
<td>Power BI Embedded</td>
<td>Nie</td>
</tr>
<tr>
<td>Osadzanie usługi Power BI (PowerBI.com)</td>
<td>Nie</td>
</tr>
</table>

**Mapa ArcGIS nie jest wyświetlana**    
W usługach lub aplikacjach, w których komponent ArcGIS Maps for Power BI nie jest dostępny, będzie wyświetlana pusta wizualizacja z logo usługi Power BI.

**Na mapie nie widać wszystkich moich adresów**    
Geokodowanych jest tylko 1500 pierwszych adresów. Limit 1500 adresów nie dotyczy geokodowania nazw miejsc ani krajów.

**Czy korzystanie z komponentu ArcGIS Maps for Power BI wiąże się z opłatami?**

Komponent ArcGIS Maps for Power BI jest dostępny dla wszystkich użytkowników usługi Power BI bez konieczności ponoszenia dodatkowych kosztów. Jak wspomniano wcześniej w tym artykule, jest to komponent dostarczany przez firmę **Esri**, dlatego jego używanie podlega ogólnym warunkom oraz zasadom ochrony prywatności określonym przez firmę **Esri**.

**Wyświetlany jest błąd informujący o przepełnieniu pamięci podręcznej**

Jest to błąd, którego naprawianie jest w toku.  Tymczasowym rozwiązaniem jest wybranie linku wyświetlanego w komunikacie o błędzie w celu uzyskania instrukcji dotyczących czyszczenia pamięci podręcznej usługi Power BI.

**Czy można wyświetlać mapy ArcGIS w trybie offline?**

Nie, usługa Power BI wymaga połączenia z siecią, aby wyświetlać mapy.

## <a name="next-steps"></a>Następne kroki
Uzyskiwanie pomocy: firma **Esri** udostępnia [kompleksową dokumentację](https://go.microsoft.com/fwlink/?LinkID=828772) dotyczącą zestawu funkcji komponentu **ArcGIS Maps for Power BI**.

W ramach [wątku społeczności usługi Power BI związanego z komponentem **ArcGIS Maps for Power BI**](https://go.microsoft.com/fwlink/?LinkID=828771) można zadawać pytania, znajdować najnowsze informacje, zgłaszać problemy i szukać odpowiedzi.

Jeśli masz sugestię dotyczącą tego, co można poprawić, prześlij ją na [listę pomysłów usługi Power BI](https://ideas.powerbi.com).

[ArcGIS Maps for Power BI — strona produktu](https://www.esri.com/powerbi)
