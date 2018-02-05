---
title: "Kartogramy w usłudze Power BI (samouczek)"
description: "Dokumentacja — samouczek dotyczący tworzenia kartogramów w usłudze Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/19/2018
ms.author: mihart
ms.openlocfilehash: 1f1db890a9fea9c53575f9b5a263400d6b883693
ms.sourcegitcommit: c3be4de522874fd73fe6854333b379b85619b907
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/24/2018
---
# <a name="filled-maps-choropleths-in-power-bi-tutorial"></a>Kartogramy w usłudze Power BI (samouczek)
Kartogram używa cieniowania lub barwienia, lub wzorców do wyświetlania, jak wartość różni się w części lokalizacji geograficznej lub regionu.  Szybko wyświetlaj te względne różnice za pomocą cieniowania tych zakresów od jasnych (rzadsze/mniejsze) do ciemnych (częstsze/większe).    

![](media/power-bi-visualization-filled-maps-choropleths/large_map.png)

## <a name="what-is-sent-to-bing"></a>Co jest wysyłane do usługi Bing
Usługa Power BI integruje się z usługą Bing w celu zapewnienia domyślnych współrzędnych mapy (w procesie zwanym kodowaniem geograficznym). Podczas tworzenia wizualizacji mapy w usłudze Power BI lub programie Power BI Desktop dane w zasobnikach **Lokalizacja**, **Szerokość geograficzna** i **Długość geograficzna** (które są używane do tworzenia tej wizualizacji) są wysyłane do usługi Bing.

Użytkownik lub administrator może być zmuszony do aktualizacji zapory, aby umożliwić dostęp do adresów URL używanych przez usługę Bing do geokodowania.  Te adresy URL to:
* https://dev.virtualearth.net/REST/V1/Locations
* https://platform.bing.com/geo/spatial/v1/public/Geodata
* https://www.bing.com/api/maps/mapcontrol

Aby uzyskać więcej informacji o danych wysyłanych do usługi Bing i wskazówkach dotyczących zwiększenia sukcesu kodowania geograficznego, zobacz [Porady i wskazówki dotyczące wizualizacji map](power-bi-map-tips-and-tricks.md).

## <a name="when-to-use-a-filled-map"></a>Kiedy należy używać kartogramu
Kartogramy są doskonałym wyborem:

* do wyświetlania informacji ilościowych na mapie.
* do pokazywania wzorców przestrzennych i relacji.
* gdy dane są standaryzowane.
* podczas pracy z danymi socjoekonomicznymi.
* gdy zdefiniowane regiony są ważne.
* w celu uzyskania przeglądu rozkładu w różnych lokalizacjach geograficznych.

### <a name="prerequisites"></a>Wymagania wstępne
- Usługa Power BI lub program Power BI Desktop
- Próbka sprzedaży i marketingu

Przykład w tym samouczku obejmuje usługę Power BI, a nie program Power BI Desktop.

## <a name="create-a-basic-filled-map"></a>Tworzenie kartogramu podstawowego
Na tym filmie Kim tworzy mapę podstawową i przekształca ją w kartogram.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>


1. Aby utworzyć własny kartogram, [pobierz przykład sprzedaży i marketingu](sample-datasets.md), logując się do usługi Power BI i wybierając pozycje **Pobierz dane \> Przykłady \> Sprzedaż i marketing \> Połącz**.
2. Gdy pojawi się komunikat o powodzeniu, wybierz pozycję **Wyświetl zestaw danych**.

   ![](media/power-bi-visualization-filled-maps-choropleths/power-bi-view-dataset.png)
3. Usługa Power BI otwiera pustą kanwę raportu w [widoku do edycji](service-interact-with-a-report-in-editing-view.md).

    ![](media/power-bi-visualization-filled-maps-choropleths/power-bi-blank-canvas.png)
4. W okienku Pola wybierz pole **Geograficzny** \> **Stan**.    

   ![](media/power-bi-visualization-filled-maps-choropleths/img002.png)
5. [Przekształć wykres](power-bi-report-change-visualization-type.md) w kartogram. Pamiętaj, że **Stan** obecnie znajduje się w źródle **Lokalizacja**. Mapy Bing używają pola w źródle **Lokalizacja** do tworzenia mapy.  Lokalizacja może obejmować różne prawidłowe lokalizacje: kraje, województwa, powiaty, miasta, kody pocztowe lub inne kody itd. Mapy Bing udostępniają kształty kartogramów dla lokalizacji na całym świecie. Bez prawidłowego wpisu w źródle lokalizacji usługa Power BI nie może utworzyć kartogramu.  

   ![](media/power-bi-visualization-filled-maps-choropleths/img003.png)
6. Przefiltruj mapę, aby wyświetlić tylko kontynentalne Stany Zjednoczone.

   a.  W dolnej części okienka wizualizacji wyszukaj obszar **Filtry**.

   b.  Umieść kursor nad pozycją **Stan** i kliknij cudzysłów ostrokątny rozwijania  
   ![](media/power-bi-visualization-filled-maps-choropleths/img004.png)

   c.  Umieść znacznik wyboru obok pozycji **Wszystkie** i usuń znacznik wyboru obok pozycji **AK**.

   ![](media/power-bi-visualization-filled-maps-choropleths/img005.png)
7. Wybierz pozycję **SalesFact** \> **Wskaźniki nastrojów klientów**, aby je dodać do źródła **Nasycenie koloru**. Pole w źródle **Nasycenie koloru** steruje cieniowaniem mapy.  
   ![](media/power-bi-visualization-filled-maps-choropleths/power-bi-color-saturation.png)
8. Kartogram zostanie zacieniowany na zielono, gdzie jasnozielony reprezentuje niższe wartości wskaźnika nastrojów klientów a ciemnozielony reprezentuje wyższe, bardziej dodatnie wskaźniki nastrojów klientów.  W tym miejscu został wyróżniony stan Wyoming (WY), gdzie wskaźniki nastrojów klientów są bardzo dobre i wynoszą 74.  
   ![](media/power-bi-visualization-filled-maps-choropleths/img007.png)
9. [Zapisz raport](service-report-save.md).

## <a name="highlighting-and-cross-filtering"></a>Wyróżnianie i filtrowanie krzyżowe
Aby uzyskać informacje o korzystaniu z okienka filtrów, zobacz [Dodawanie filtra do raportu](power-bi-report-add-filter.md).

Wyróżnianie lokalizacji na kartogramie powoduje krzyżowe filtrowanie innych wizualizacji na stronie raportu... i na odwrót.

Aby kontynuować, skopiuj i wklej swój kartogram na stronę **Wskaźniki nastrojów klientów** raportu *Sprzedaż i marketing*.

1. Na kartogramie wybierz stan.  Spowoduje to wyróżnienie innych wizualizacji na stronie. Na przykład wybranie **Teksasu** pokazuje, że wskaźnik nastrojów klientów wynosi 74, że Teksas znajduje się w regionie centralnym \#23 i że większość woluminu sprzedaży pochodzi z segmentów łagodzenia i wygody.   
   ![](media/power-bi-visualization-filled-maps-choropleths/img008.png)
2. Na wykresie liniowym, przełącz się między **Nie** i **Tak**. To filtruje kartogram, aby pokazać wskaźniki nastrojów klientów dla firmy VanArsdel i konkurentów firmy VanArsdel.  
   ![](media/power-bi-visualization-filled-maps-choropleths/img009.gif)

## <a name="considerations-and-troubleshooting"></a>Zagadnienia i rozwiązywanie problemów
Dane mapy mogą być niejednoznaczne.  Na przykład istnieje Paryż we Francji, ale jest również Paryż w Teksasie. Twoje dane geograficzne prawdopodobnie znajdują się w oddzielnych kolumnach — kolumnie na nazwy miast, kolumnie na nazwy województw lub powiatów itd. — więc usługa Bing nie może ustalić, który Paryż jest który. Jeśli zestaw danych zawiera już dane współrzędnych geograficznych, usługa Power BI ma specjalne pola, aby sprawić, że dane mapy będą jednoznaczne. Przeciągnij pole zawierające dane szerokości geograficznej do obszaru wizualizacji \> Szerokość geograficzna.  Wykonaj te same czynności dla danych długości geograficznej.  
![](media/power-bi-visualization-filled-maps-choropleths/pbi_latitude.png)

Jeśli masz uprawnienia do edycji zestawu danych w programie Power BI Desktop, obejrzyj ten film, aby uzyskać pomoc na temat niejednoznaczności mapy.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Co2z9b-s_yM" frameborder="0" allowfullscreen></iframe>

Jeśli nie masz dostępu do danych współrzędnych geograficznych, [wykonaj te instrukcje, aby zaktualizować zestaw danych](https://support.office.com/article/Maps-in-Power-View-8A9B2AF3-A055-4131-A327-85CC835271F7).

Aby uzyskać pomoc na temat wizualizacji map, zobacz [Porady i wskazówki dotyczące wizualizacji map](power-bi-map-tips-and-tricks.md).

## <a name="next-steps"></a>Następne kroki
[Dodawanie kartogramu jako kafelka pulpitu nawigacyjnego (przypinanie elementu wizualnego)](service-dashboard-tiles.md)    
 [Dodawanie wizualizacji do raportu](power-bi-report-add-visualizations-i.md)  
 [Typy wizualizacji w usłudze Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)    
 [Zmienianie typu używanej wizualizacji](power-bi-report-change-visualization-type.md)      
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)
