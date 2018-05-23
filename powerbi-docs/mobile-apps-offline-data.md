---
title: Wyświetlanie danych w trybie offline w aplikacjach mobilnych Power BI
description: 'Przeczytaj o korzyściach wyświetlania usługi Power BI w aplikacji mobilnej zamiast w przeglądarce mobilnej: możesz zobaczyć swoje dane nawet wtedy, gdy nie masz połączenia z siecią.'
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 01/16/2018
ms.author: maggies
ms.openlocfilehash: 5dd171ccd7d8859286abeac2f87771b454421448
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="view-your-data-offline-in-the-power-bi-mobile-apps"></a>Wyświetlanie danych w trybie offline w aplikacjach mobilnych Power BI
Dotyczy:

| ![Telefon iPhone](media/mobile-apps-offline-data/iphone-logo-50-px.png) | ![Tablet iPad](media/mobile-apps-offline-data/ipad-logo-50-px.png) | ![Telefon z systemem Android](media/mobile-apps-offline-data/android-phone-logo-50-px.png) | ![Tablet z systemem Android](media/mobile-apps-offline-data/android-tablet-logo-50-px.png) | ![Windows 10](media/mobile-apps-offline-data/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| Telefony iPhone |Urządzenia iPad |Telefony z systemem Android |Tablety z systemem Android |Urządzenia z systemem Windows 10 |

Jedną z korzyści wyświetlania usługi Power BI w aplikacji mobilnej zamiast w przeglądarce mobilnej jest możliwość wyświetlenia danych nawet wtedy, gdy nie masz połączenia z siecią. 

![Komunikat o braku sieci](media/mobile-apps-offline-data/power-bi-iphone-no-network.png)

Domyślnie usługa Power BI odświeża dane często, więc otrzymujesz aktualne odpowiedzi na pytania biznesowe w dowolnym momencie, nawet podczas podróży lub pracy zdalnej.

## <a name="data-access-while-youre-offline"></a>Dostęp do danych w trybie offline
Podczas pracy w trybie offline możesz uzyskać dostęp do pulpitów nawigacyjnych, do których uzyskano wcześniej dostęp z aplikacji mobilnej, i wejść z nimi w interakcje.

Masz też dostęp tylko do odczytu do raportów usługi Power BI, do których uzyskano wcześniej dostęp z aplikacji mobilnej. Możesz wyświetlić pełny raport, ale nie możesz go filtrować, filtrować krzyżowo, sortować lub stosować na nim fragmentatorów.

## <a name="background-data-refresh"></a>Odświeżanie danych w tle
Odświeżane w tle aktualizuje ulubione pulpity nawigacyjne oraz pulpity nawigacyjne i raporty, które zostały wyświetlone w ciągu ostatnich dwóch tygodni, przy użyciu danych w usłudze Power BI (nie w źródle danych). Jeśli masz połączenie Wi-Fi, odświeżanie w tle aktualizuje dane co 2 godziny. W przeciwnym wypadku, jeśli korzystasz z sieci 3G, usługa Power BI będzie aktualizować zawartość co 24 godziny.

Możesz wyłączyć odświeżanie w tle, np. aby unikać użycia sieci. Sprawdź ustawienia na urządzeniu.

> [!NOTE]
> Jeśli korzystasz z aplikacji mobilnej Power BI na urządzeniu z systemem iOS, a Twoja organizacja skonfigurowała funkcję zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune, odświeżanie danych w tle jest wyłączone. Przy następnym otwarciu aplikacji usługa Power BI odświeży dane na podstawie usługi Power BI w Internecie.
> 
> Dowiedz się więcej na temat [konfigurowania aplikacji mobilnych Power BI przy użyciu usługi Microsoft Intune](service-admin-mobile-intune.md). 
> 
> 

## <a name="offline-indicators"></a>Wskaźniki trybu offline
Usługa Power BI zapewnia wyraźne wskaźniki informujące o przechodzeniu do trybu offline i wychodzeniu z niego, a także wskaźniki informujące o brakujących pulpitach nawigacyjnych, raportach i kafelkach, które nie są dostępne w trybie offline.

## <a name="limitations"></a>Ograniczenia
Jeśli pracujesz w trybie offline z usługą Power BI na urządzeniu przenośnym, możesz napotkać następujące ograniczenia:

* Usługa Power BI może buforować do 250 MB danych w trybie offline.
* Niektóre typy kafelków wymagają aktywnego połączenia z serwerem, więc nie są dostępne w trybie offline, np. kafelki map Bing i niektóre kafelki niestandardowe.
* Całe skoroszyty programu Excel w usłudze Power BI nie są dostępne w trybie offline.
* Możesz wyświetlić raporty dla urządzeń przenośnych usług Reporting Services oraz kluczowe wskaźniki wydajności w trybie offline, jeśli wyświetlano je podczas połączenia. Nie są one odświeżane w tle. Są odświeżane przy każdym otworzeniu. 

## <a name="next-steps"></a>Następne kroki
Twoja opinia pomoże nam zdecydować, co należy zaimplementować w przyszłości. Nie zapomnij więc zagłosować na inne funkcje, które chcesz zobaczyć w aplikacjach mobilnych usługi Power BI. 

* [Aplikacje Power BI dla urządzeń przenośnych](mobile-apps-for-mobile-devices.md)
* Obserwuj @MSPowerBI na Twitterze
* Dołącz do konwersacji w [społeczności usługi Power BI](http://community.powerbi.com/)
* [Wprowadzenie do usługi Power BI](service-get-started.md)

