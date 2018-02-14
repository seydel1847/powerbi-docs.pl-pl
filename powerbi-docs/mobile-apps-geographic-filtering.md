---
title: "Filtrowanie raportu według lokalizacji geograficznej w aplikacji mobilnej Power BI"
description: "Dowiedz się, jak możesz filtrować raport według lokalizacji geograficznej w aplikacjach mobilnych usługi Microsoft Power BI, jeśli właściciel raportu ustawił tagi geograficzne."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/09/2018
ms.author: maggies
ms.openlocfilehash: 90d6e6f80be49e8d1c2a9605558a57834e24e285
ms.sourcegitcommit: ad9bd4e52471b1179f46f847960d5ed79c0c0761
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/11/2018
---
# <a name="filter-a-report-by-geographic-location-in-the-power-bi-mobile-apps"></a>Filtrowanie raportu według lokalizacji geograficznej w aplikacjach mobilnych Power BI
Dotyczy:

| ![Telefon iPhone](media/mobile-apps-geographic-filtering/iphone-logo-50-px.png) | ![Tablet iPad](media/mobile-apps-geographic-filtering/ipad-logo-50-px.png) | ![Telefon z systemem Android](media/mobile-apps-geographic-filtering/android-phone-logo-50-px.png) | ![Tablet z systemem Android](media/mobile-apps-geographic-filtering/android-tablet-logo-50-px.png) | ![Tablet z systemem Android](media/mobile-apps-geographic-filtering/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| Telefony iPhone |Urządzenia iPad |Telefony z systemem Android |Tablety z systemem Android |Telefony z systemem Windows 10 |

Czy kiedy wyświetlasz raport usługi Power BI na urządzeniu przenośnym, widzisz małą ikonę pinezki w prawym górnym rogu? Jeśli tak, możesz filtrować ten raport na podstawie swojej lokalizacji geograficznej.

> [!NOTE]
> Filtrować według lokalizacji można tylko wtedy, jeśli nazwy geograficzne w raporcie są w języku angielskim — na przykład „New York City” lub „Germany”. Tablety i komputery z systemem Windows 10 nie obsługują filtrowania geograficznego, ale telefony z systemem Windows 10 obsługują je.
> 
> 

## <a name="filter-your-report-by-your-geographic-location"></a>Filtrowanie raportu według lokalizacji geograficznej
1. Otwórz raport w aplikacji mobilnej Power BI na urządzeniu przenośnym.
2. Jeśli raport zawiera dane geograficzne, zobaczysz komunikat z prośbą o umożliwienie usłudze Power BI uzyskania dostępu do Twojej lokalizacji. Kliknij pozycję **Zezwalaj**, następnie ponownie naciśnij pozycję **Zezwalaj**.
3. Naciśnij ikonę pinezki ![Ikona pinezki](media/mobile-apps-geographic-filtering/power-bi-mobile-geo-icon.png). Możesz filtrować według miasta, województwa lub kraju/regionu w zależności od danych w raporcie. W filtrze są wymienione tylko opcje zgodne z bieżącą lokalizacją.
   
    ![Filtr pinezki](media/mobile-apps-geographic-filtering/power-bi-mobile-geo-map-set-filter.png)

## <a name="why-dont-i-see-location-tags-on-a-report"></a>Dlaczego nie widać tagów lokalizacji w raporcie?
Aby tagi lokalizacji były widoczne, muszą być spełnione wszystkie trzy poniższe warunki. 

* Osoba, która utworzyła raport w programie Power BI Desktop, [skategoryzowała dane geograficzne](desktop-mobile-geofiltering.md) dla co najmniej jednej kolumny, takiej jak Miejscowość, Województwo lub Kraj/Region.
* Jesteś w jednej z lokalizacji, które zawierają dane w tej kolumnie.
* Używasz jednego z tych urządzeń przenośnych:
  * z systemem iOS (iPad, iPhone i iPod);
  * telefon lub tablet z systemem Android;
  * telefon z systemem Windows 10 (inne urządzenia z systemem Windows 10, takie jak komputery i tablety, nie obsługują filtrowania geograficznego).

Przeczytaj więcej na temat [konfigurowania filtrowania geograficznego](desktop-mobile-geofiltering.md) w programie Power BI Desktop.

### <a name="next-steps"></a>Następne kroki
* [Nawiązywanie połączenia z danymi usługi Power BI ze środowisk rzeczywistych](mobile-apps-data-in-real-world-context.md) za pomocą aplikacji mobilnych
* [Kategoryzacja danych w programie Power BI Desktop](desktop-data-categorization.md) 
* Masz pytania? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

