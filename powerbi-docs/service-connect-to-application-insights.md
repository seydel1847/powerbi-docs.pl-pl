---
title: "Łączenie się z usługą Application Insights Łączenie się z usługą Power BI"
description: "Usługa Application Insights dla usługi Power BI"
services: powerbi
documentationcenter: 
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 04cc92bd33f342097b9952a744d8dfffced22bb3
ms.sourcegitcommit: d91b7bf18d5c504037134f375886633379f28ede
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/27/2018
---
# <a name="connect-to-application-insights-with-power-bi"></a>Łączenie się z usługą Application Insights za pomocą usługi Power BI
Usługa Power BI umożliwia tworzenie zaawansowanych niestandardowych pulpitów nawigacyjnych z telemetrii usługi [Application Insights](https://azure.microsoft.com/documentation/articles/app-insights-overview/). Dostępne są nowe sposoby wykorzystania telemetrii aplikacji. Możesz łączyć metryki z wielu aplikacji lub usług składowych na jednym pulpicie nawigacyjnym. Ta pierwsza wersja pakietu zawartości usługi Power BI dla usługi Application Insights zawiera widgety dla typowych metryk związanych z użyciem, takich jak aktywni użytkownicy, widok strony, sesje, przeglądarka i wersja systemu operacyjnego oraz rozkład geograficzny użytkowników na mapie.

Połącz się z [pakietem zawartości Application Insights dla usługi Power BI](https://app.powerbi.com/getdata/services/application-insights).

>[!NOTE]
>W celu nawiązania połączenia wymagany jest dostęp do bloku przeglądu usługi Application Insights dla aplikacji w Portalu Azure w wersji zapoznawczej. Więcej szczegółowych informacji na temat wymagań znajduje się poniżej.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
    ![Przycisk Pobierz dane](media/service-connect-to-application-insights/pbi_getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
    ![Przycisk Pobierz usługi](media/service-connect-to-application-insights/pbi_getservices.png)
3. Wybierz pozycję **Application Insights** > **Pobierz**.
   
    ![Pakiet zawartości Application Insights](media/service-connect-to-application-insights/appinsights.png)
4. Podaj szczegółowe informacje dotyczące aplikacji, z którą chcesz nawiązać połączenie, w tym dane, takie jak **Nazwa zasobu usługi Application Insights**, **Grupa zasobów** i **Identyfikator subskrypcji**. Zobacz [Znajdowanie parametrów usługi Application Insights](#FindingAppInsightsParams) poniżej, aby uzyskać więcej informacji.
   
    ![Okno dialogowe połączenia z usługą Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitconnectndialog.png)    
5. Wybierz pozycję **Zaloguj** i postępuj zgodnie z instrukcjami na ekranie, aby nawiązać połączenie.
   
    ![Logowanie przy połączeniu z usługą Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitconnectn2.png)
6. Proces importowania rozpocznie się automatycznie. Po zakończeniu zostanie wyświetlone powiadomienie, a w okienku nawigacji oznaczonym gwiazdką pojawi się nowy pulpit nawigacyjny, raport i zestaw danych.  Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
    ![Pulpit nawigacyjny usługi Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitdash.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Pakiet zawartości Application Insights obejmuje następujące tabele i metryki:  

    ´´´
    - ApplicationDetails  
    - UniqueUsersLast7Days   
    - UniqueUsersLast30Days   
    - UniqueUsersDailyLast30Days  
    - UniqueUsersByCountryLast7Days  
    - UniqueUsersByCountryLast30Days   
    - PageViewsDailyLast30Days   
    - SessionsLast7Days   
    - SessionsLast30Days  
    - PageViewsByBrowserVersionDailyLast30Days   
    - UniqueUsersByOperatingSystemLast7Days   
    - UniqueUsersByOperatingSystemLast30Days    
    - SessionsDailyLast30Days   
    - SessionsByCountryLast7Days   
    - SessionsByCountryLast30Days   
    - PageViewsByCountryDailyLast30Days  
    ´´´ 

<a name="FindingAppInsightsParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Parametry, takie jak Nazwa zasobu, Grupa zasobów i Identyfikator subskrypcji, można znaleźć w witrynie Azure Portal. Po wybraniu pozycji Nazwa zostanie otwarty widok szczegółowy. Wszystkie potrzebne elementy będzie można znaleźć na liście rozwijanej Podstawowe elementy.

![Parametry usługi Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitparams.png)

Skopiuj i wklej te dane do pól w usłudze Power BI:

![Parametry usługi Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitparam2.png)

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)

