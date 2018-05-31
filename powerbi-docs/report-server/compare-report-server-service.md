---
title: Porównanie serwera raportów usługi Power BI i usługi Power BI
description: W tym artykule znajduje się porównanie funkcji serwera raportów usługi Power BI i usługi Power BI.
services: powerbi
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.component: powerbi-report-server
ms.date: 05/07/2018
ms.topic: overview
ms.service: powerbi
manager: kfile
ms.custom: mvc
ms.openlocfilehash: d0a3e2870edc8b18cb982c33582c7578aa67f2c3
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
ms.locfileid: "33813903"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Porównanie serwera raportów usługi Power BI i usługi Power BI

Serwer raportów usługi Power BI i usługa Power BI mają wiele podobieństw i niektóre podstawowe różnice. Poniższa tabela zawiera ich szczegółowe objaśnienia.

| Funkcje | Serwer raportów usługi Power BI | Usługa Power BI | Uwagi
|---------|---------|---------|---------|
| Wdrożenie | Środowisko lokalne lub chmura hostowana | Chmura | Serwer raportów usługi Power BI można wdrożyć na maszynach wirtualnych platformy Azure (chmura hostowana), jeśli jest licencjonowany za pośrednictwem usługi Power BI Premium
| Dane źródłowe | Chmura i/lub środowisko lokalne | Chmura i/lub środowisko lokalne |  
| Licencja | Usługa Power BI Premium lub program SQL Server EE z pakietem SA | Usługa Power BI Pro i/lub Power BI Premium |  
| Cykl życia | Nowoczesne zasady cyklu życia | Usługa w pełni zarządzana |  
| Cykl wydania | Co 4 miesiące | Raz na miesiąc | Najnowsze funkcje i poprawki są najpierw dodawane do usługi Power BI. Większość podstawowych funkcji jest dodawana do serwera raportów usługi Power BI w kilku kolejnych wydaniach; niektóre funkcje są przeznaczone tylko dla usługi Power BI.
| Tworzenie raportów usługi Power BI w programie Power BI Desktop | Tak | Tak |  
| Tworzenie raportów usługi Power BI w przeglądarce | Nie | Tak |  
| Wymagana brama | Nie | Tak w przypadku lokalnych źródeł danych |  
| Przesyłanie strumieniowe w czasie rzeczywistym | Nie | Tak | [Przesyłanie strumieniowe w czasie rzeczywistym w usłudze Power BI](../service-real-time-streaming.md)
| Pulpity nawigacyjne | Nie | Tak | [Pulpity nawigacyjne w usłudze Power BI](../service-dashboards.md) 
| Dystrybuowanie grupy raportów za pomocą aplikacji | Nie | Tak | [Tworzenie i publikowanie aplikacji z pulpitami nawigacyjnymi i raportami](../service-create-distribute-apps.md) 
| Pakiety zawartości | Nie | Tak | [Organizacyjne pakiety zawartości: wprowadzenie](../service-organizational-content-pack-introduction.md) 
| Łączenie z usługami, takimi jak Salesforce | Nie | Tak | [Łączenie z usługami używanymi](../service-connect-to-services.md) z usługą Power BI
| Pytania i odpowiedzi | Nie | Tak | [Funkcja pytań i odpowiedzi w usłudze Power BI i programie Power BI Desktop](../power-bi-q-and-a.md) 
| Szybki wgląd w szczegółowe dane | Nie | Tak | [Automatyczne generowanie wglądu w szczegółowe dane przy użyciu usługi Power BI](../service-insights.md) 
| Analizuj w programie Excel | Nie | Tak | [Analizowanie w programie Excel](../service-analyze-in-excel.md) 
| Raporty z podziałem na strony | Tak | Nie | Raporty podzielone na strony są niedostępne w usłudze Power BI, ale można [przypinać elementy raportu podzielonego na strony do pulpitów nawigacyjnych usługi Power BI](https://docs.microsoft.com/sql/reporting-services/pin-reporting-services-items-to-power-bi-dashboards)
| Aplikacje mobilne Power BI | Tak | Tak | [Omówienie aplikacji mobilnych usługi Power BI](../mobile-apps-for-mobile-devices.md) 
| Mapy ARC GIS | Nie | Tak | [Mapy ArcGIS firmy Esri w usłudze Power BI i programie Power BI Desktop](../power-bi-visualization-arcgis.md)
| Subskrypcje poczty e-mail dla raportów usługi Power BI | Nie | Tak | [Subskrybowanie raportu i pulpitu nawigacyjnego](../service-report-subscribe.md) w usłudze Power BI 
| Subskrypcje poczty e-mail dla raportów podzielonych na strony | Tak | Nie | [Dostarczanie wiadomości e-mail w usługach Reporting Services](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  
| Alerty dotyczące danych | Nie | Tak | [Alerty dotyczące danych](../service-set-data-alerts.md) w usłudze Power BI
| Zabezpieczenia na poziomie wiersza | Tylko za pośrednictwem źródła danych w trybie DirectQuery | Dostępne w trybie DirectQuery (źródło danych) i trybie importu | [Zabezpieczenia na poziomie wiersza](../service-admin-rls.md) w usłudze Power BI 
| Tryb pełnoekranowy | Nie | Tak | [Tryb pełnoekranowy](../service-fullscreen-mode.md) w usłudze Power BI 
| Zaawansowana współpraca z usługą Office 365 | Nie | Tak | [Współpraca w obszarze roboczym aplikacji](../service-collaborate-power-bi-workspace.md) z usługą Office 365 
| Wizualizacje języka R | Nie | Tak | [Tworzenie wizualizacji języka R](../service-r-visuals.md) w usłudze Power BI  
| Funkcje w wersji zapoznawczej | Nie | Tak | [Włączanie funkcji usługi Power BI w wersji zapoznawczej](../service-preview-features.md) 
| Wizualizacje niestandardowe | Tak | Tak | [Tworzenie wizualizacji niestandardowych w usłudze Power BI](../power-bi-custom-visuals.md) 
| Power BI Desktop | Wersja zoptymalizowana pod kątem serwera raportów dostępna do pobrania z serwerem raportów | Wersja zoptymalizowana pod kątem usługi Power BI dostępna w Sklepie Windows | [Program Power BI Desktop dla serwera raportów](https://powerbi.microsoft.com/report-server/) <br><br> [Program Power BI Desktop dla usługi Power BI](http://aka.ms/pbidesktopstore)

## <a name="next-steps"></a>Następne kroki
[Instalacja serwera raportów usługi Power BI](install-report-server.md)  



