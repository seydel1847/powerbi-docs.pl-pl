---
title: Co to jest serwer raportów usługi Power BI?
description: Omówienie serwera raportów usługi Power BI wyjaśniające, jak współpracuje on z usługami SQL Server Reporting Services (SSRS) i pozostałymi elementami usługi Power BI.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 11/20/2018
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: 4db2f7ca5a84563e86b3a3033daae6d83bffcf5e
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54291990"
---
# <a name="what-is-power-bi-report-server"></a>Co to jest serwer raportów usługi Power BI?

Serwer raportów usługi Power BI to lokalny serwer raportów powiązany z portalem internetowym, w którym można wyświetlać raporty oraz wskaźniki KPI i zarządzać nimi. Dostępne w nim są również narzędzia do tworzenia raportów usługi Power BI, raportów podzielonych na strony, raportów dla urządzeń przenośnych i wskaźników KPI. Użytkownicy mają dostęp do tych raportów na różne sposoby: mogą wyświetlić je w przeglądarce internetowej, na urządzeniu przenośnym lub jako wiadomości e-mail w skrzynce odbiorczej.

![Portal internetowy Serwera raportów usługi Power BI](media/get-started/power-bi-report-server-overview.png)

## <a name="comparing-power-bi-report-server"></a>Porównanie serwera raportów usługi Power BI 
Serwer raportów usługi Power BI jest podobny do usługi SQL Server Reporting Services i usługi Power BI w trybie online, ale na różne sposoby. Tak jak usługa Power BI, serwer raportów usługi Power BI hostuje raporty usługi Power BI (PBIX) i pliki programu Excel. Podobnie jak usługi Reporting Services, serwer raportów usługi Power BI działa lokalnie i hostuje raporty podzielone na strony (RDL). Serwer raportów usługi Power BI jest nadzbiorem usług Reporting Services: wszystko, co można zrobić w usługach Reporting Services, można zrobić za pomocą serwera raportów usługi Power BI — a ponadto oferuje on obsługę raportów usługi Power BI. Szczegółowe informacje można znaleźć w temacie [Porównanie serwera raportów usługi Power BI i usługi Power BI](compare-report-server-service.md).

## <a name="licensing-power-bi-report-server"></a>Licencjonowanie serwera raportów usługi Power BI
Serwer raportów usługi Power BI jest dostępny za pośrednictwem dwóch różnych licencji: [Power BI Premium](../service-premium.md) i [SQL Server Enterprise Edition](https://www.microsoft.com/sql-server/sql-server-2017-editions) z pakietem Software Assurance. Licencja usługi Power BI Premium umożliwia tworzenie hybrydowego wdrożenia łączącego chmurę i środowisko lokalne.  

> [!NOTE]
> W przypadku usługi Power BI Premium, serwer raportów usługi Power BI jest dołączony tylko do jednostek SKU typu P. Nie jest on dołączony do jednostek SKU typu EM.

## <a name="web-portal"></a>Portal internetowy
Punkt wejścia serwera raportów usługi Power BI to bezpieczny portal internetowy, który można wyświetlić w dowolnej nowoczesnej przeglądarce. W tym miejscu można uzyskać dostęp do wszystkich swoich raportów i wskaźników KPI. Zawartość portalu internetowego jest zorganizowana przy użyciu tradycyjnej hierarchii folderów. Zawartość w folderach jest pogrupowana według typu: raporty usługi Power BI, raporty dla urządzeń przenośnych, raporty podzielone na strony, wskaźniki KPI oraz skoroszyty programu Excel. Udostępnione zestawy danych oraz udostępnione źródła danych, których można użyć jako bloków konstrukcyjnych dla własnych raportów, również znajdują się w oddzielnych folderach. Można otagować ulubione elementy, aby wyświetlać je w jednym folderze. W portalu internetowym można również tworzyć wskaźniki KPI. 

![Portal internetowy Serwera raportów usługi Power BI](media/get-started/web-portal.png)

W zależności od uprawnień można zarządzać zawartością w portalu internetowym. Można planować przetwarzanie raportów, uzyskiwać dostęp do raportów na żądanie i subskrybować opublikowane raporty. Można także zastosować własne, niestandardowe [znakowanie](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal) w portalu internetowym. 

Więcej informacji o [portalu internetowym serwera raportów usługi Power BI](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).

## <a name="power-bi-reports"></a>Raporty usługi Power BI
Można tworzyć raporty usługi Power BI (PBIX) przy użyciu wersji programu Power BI Desktop zoptymalizowanej pod kątem serwera raportów. Następnie można je opublikować i wyświetlić w portalu internetowym we własnym środowisku.

![Raporty usługi Power BI na serwerze raportów programu Power BI](media/get-started/powerbi-reports.png)

Raport usługi Power BI to widok modelu danych z wielu perspektyw z wizualizacjami przedstawiającymi różne wyniki i szczegółowe informacje wynikające z tego modelu danych.  Raport może zawierać jedną wizualizację lub kilka stron wypełnionych wizualizacjami. W zależności od roli użytkownika można odczytywać i poznawać raporty lub utworzyć je dla innych użytkowników.

Instalowanie [programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI](quickstart-create-powerbi-report.md).

## <a name="paginated-reports"></a>Raporty z podziałem na strony
Raporty podzielone na strony (RDL) to raporty przypominające dokumenty z wizualizacjami, w których tabele rozwijają się w poziomie i w pionie w celu wyświetlenia wszystkich danych. Raporty te są kontynuowane na kolejnych stronach zgodnie z potrzebami. To doskonałe rozwiązanie do tworzenia dokumentów o stałym układzie z idealnie rozmieszczoną treścią, zoptymalizowanych pod kątem wydruku, takich jak pliki PDF i pliki programu Word. 

![Raporty z podziałem na strony na serwerze raportów usługi Power BI](media/get-started/paginated-reports.png)

Raporty o nowoczesnym wyglądzie można tworzyć przy użyciu programów [Report Builder](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016) i Report Designer w narzędziach [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt). 

## <a name="reporting-services-mobile-reports"></a>Raporty usług Reporting Services dla urządzeń przenośnych
Raporty dla urządzeń przenośnych łączą się z danymi lokalnymi i mają dynamiczny układ, który dostosowuje się do różnych urządzeń i sposobów ich trzymania. Można je utworzyć za pomocą programu Microsoft SQL Server Mobile Report Publisher.

Więcej informacji o [raportach usług Reporting Services dla urządzeń przenośnych](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher). 

## <a name="report-server-programming-features"></a>Funkcje programowania serwera raportów
Korzystaj z funkcji programowania serwera raportów usługi Power BI, aby rozszerzać i dostosowywać raporty dzięki interfejsom API do integracji i rozszerzania możliwości przetwarzania danych i raportów w aplikacjach niestandardowych.

Więcej [dokumentacji dla deweloperów serwera raportów](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation).

## <a name="next-steps"></a>Następne kroki
[Instalacja serwera raportów usługi Power BI](install-report-server.md)  
[Pobieranie programu Report Builder](https://www.microsoft.com/download/details.aspx?id=53613)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)


