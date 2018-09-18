---
title: Ustawianie filtrów geograficznych w programie Power BI Desktop dla aplikacji mobilnych
description: Podczas ustawiania filtrowania geograficznego w modelu w programie Power BI Desktop możesz automatycznie filtrować dane według lokalizacji w aplikacjach mobilnych usługi Power BI.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 01/16/2018
ms.author: maggies
LocalizationGroup: Model your data
ms.openlocfilehash: 80d2039b2cfcac2f2c3db9c6f656561b670aa341
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44727495"
---
# <a name="set-geographic-filters-in-power-bi-desktop-for-the-mobile-apps"></a>Ustawianie filtrów geograficznych w programie Power BI Desktop dla aplikacji mobilnych
W programie Power BI Desktop możesz [skategoryzować dane geograficzne](desktop-data-categorization.md) dla kolumny, aby poinformować program Power BI Desktop, jak ma traktować wartości w wizualizacjach w raporcie. Dodatkowo gdy Ty lub Twoi współpracownicy wyświetlą ten raport w aplikacjach mobilnych usługi Power BI, usługa Power BI automatycznie udostępni filtry geograficzne, które pasują do miejsca, gdzie się znajdujesz. 

Załóżmy przykładowo, że jesteś menedżerem sprzedaży podróżującym na spotkanie z klientami i chcesz szybko przefiltrować łączną wartość sprzedaży i przychodu dla określonego klienta, z którym planujesz się spotkać. Możesz rozbić dane dla bieżącej lokalizacji według regionu, miasta lub rzeczywistego adresu. Jeśli zostanie czas, być może zechcesz odwiedzić innych klientów znajdujących się w pobliżu. Możesz [przefiltrować raport według swojej lokalizacji, by znaleźć tych klientów](consumer/mobile/mobile-apps-geographic-filtering.md).

> [!NOTE]
> W aplikacji mobilnej filtrować według lokalizacji można tylko wtedy, jeśli nazwy geograficzne w raporcie są w języku angielskim — na przykład „New York City” lub „Germany”.
> 
> 

## <a name="identify-geographic-data-in-your-report"></a>Identyfikowanie danych geograficznych w raporcie
1. W programie Power BI Desktop przejdź do widoku danych ![Ikona widoku danych](media/desktop-mobile-geofiltering/pbi_desktop_data_icon.png).
2. Wybierz kolumnę z danymi geograficznymi — na przykład kolumnę City (Miasto).
   
    ![Kolumna City (Miasto)](media/desktop-mobile-geofiltering/power-bi-desktop-geo-column.png)
3. Na karcie **Modelowanie** wybierz pozycję **Kategoria danych**, a następnie prawidłową kategorię — w tym przykładzie **Miasto**.
   
    ![Pole kategorii danych](media/desktop-mobile-geofiltering/power-bi-desktop-geo-category.png)
4. Kontynuuj ustawianie kategorii danych geograficznych dla innych pól w modelu. 
   
   > [!NOTE]
   > Możesz ustawić wiele kolumn dla każdej kategorii danych w modelu, ale jeśli to zrobisz, model nie będzie filtrował lokalizacji geograficznych w aplikacji mobilnej Power BI. Aby korzystać z filtrowania lokalizacji geograficznej w aplikacjach mobilnych, ustaw tylko jedną kolumnę dla każdej kategorii danych — na przykład tylko jedną kolumnę **Miasto**, jedną kolumnę **Województwo** i jedną kolumnę **Kraj**. 
   > 
   > 

## <a name="create-visuals-with-your-geographic-data"></a>Tworzenie wizualizacji za pomocą danych geograficznych
1. Przełącz się do widoku raportu ![Ikona widoku raportu](media/desktop-mobile-geofiltering/power-bi-desktop-report-icon.png)i utwórz wizualizacje używające pól geograficznych w Twoich danych. 
   
    ![Raport z mapą](media/desktop-mobile-geofiltering/power-bi-desktop-geo-report.png)
   
    W tym przykładzie model zawiera kolumnę obliczeniową, która powoduje połączenie miasta i stanu w jedną kolumnę. Przeczytaj o [tworzeniu kolumn obliczeniowych w programie Power BI Desktop](desktop-calculated-columns.md).
   
    ![Miasto + stan](media/desktop-mobile-geofiltering/power-bi-desktop-city-state-column.png)
2. Opublikuj raport w usłudze Power BI.

## <a name="view-the-report-in-power-bi-mobile-app"></a>Wyświetlanie raportu w aplikacji mobilnej usługi Power BI
1. Otwórz raport w dowolnej [aplikacji mobilnej usługi Power BI](consumer/mobile/mobile-apps-for-mobile-devices.md).
2. Jeśli znajdujesz się w lokalizacji geograficznej, dla której masz dane w raporcie, możesz go automatycznie przefiltrować pod kątem swojej lokalizacji.
   
    ![Filtr geograficzny w aplikacji mobilnej](media/desktop-mobile-geofiltering/power-bi-mobile-geo-map-set-filter.png)

Przeczytaj więcej o [filtrowaniu raportu według lokalizacji w aplikacjach mobilnych Power BI](consumer/mobile/mobile-apps-geographic-filtering.md).

## <a name="next-steps"></a>Następne kroki
* [Kategoryzacja danych w programie Power BI Desktop](desktop-data-categorization.md)  
* Masz pytania? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

