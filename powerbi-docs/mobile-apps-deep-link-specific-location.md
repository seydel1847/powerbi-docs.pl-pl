---
title: Tworzenie linku do określonej lokalizacji w aplikacjach mobilnych usługi Power BI
description: Dowiedz się, jak utworzyć link bezpośredni do określonego pulpitu nawigacyjnego, kafelka lub raportu w aplikacji mobilnej usługi Power BI z identyfikatorem (URI).
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 3be6882219e23a2d22ee03e6805ce3a1e8e08b8f
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Tworzenie linku do określonej lokalizacji w aplikacjach mobilnych usługi Power BI
Możesz tworzyć identyfikator URI i używać go do łączenia z określoną lokalizacją (*link bezpośredni*) w aplikacjach mobilnych usługi Power BI na wszystkich platformach przenośnych: iOS, urządzeniach z systemem Android i Windows 10.

Linki identyfikatora URI mogą wskazywać bezpośrednio na pulpity nawigacyjne, kafelki i raporty.

Miejsce docelowe linku bezpośredniego określa format identyfikatora URI. Wykonaj następujące kroki, aby utworzyć linki bezpośrednie do różnych lokalizacji. 

## <a name="open-the-power-bi-mobile-app"></a>Otwieranie aplikacji mobilnej usługi Power BI
Użyj tego identyfikatora URI, aby otworzyć aplikację mobilną usługi Power BI na dowolnym urządzeniu:

    mspbi://app/


## <a name="open-to-a-specific-dashboard"></a>Otwieranie określonego pulpitu nawigacyjnego
Ten identyfikator URI otwiera aplikację mobilną usługi Power BI do określonego pulpitu nawigacyjnego:

    mspbi://app/OpenDashboard?DashboardObjectId=<36-character-dashboard-id>

Aby znaleźć 36-znakowy identyfikator obiektu pulpitu nawigacyjnego, przejdź do określonego pulpitu nawigacyjnego w usłudze Power BI (https://powerbi.com). Na przykład zobacz wyróżnioną sekcję tego adresu URL:

https://powerbi.com/groups/me/dashboards/**61b7e871-cb98-48ed-bddc-6572c921e270**

Jeśli pulpit nawigacyjny jest w grupie innej niż Mój obszar roboczy, dodaj `&GroupObjectId=<36-character-group-id>` przed lub po identyfikatorze pulpitu nawigacyjnego. Na przykład: 

mspbi://app/OpenDashboard?DashboardObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60 **&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

Należy zwrócić uwagę na znak ampersand (&) między nimi.

## <a name="open-to-a-specific-tile-in-focus"></a>Otwieranie na określonym kafelku w trybie koncentracji uwagi
Ten identyfikator URI otwiera określony kafelek w trybie koncentracji uwagi w aplikacji mobilnej usługi Power BI:

    mspbi://app/OpenTile?DashboardObjectId=<36-character-dashboard-id>&TileObjectId=<36-character-tile-id>

Aby znaleźć 36-znakowe identyfikatory obiektu pulpitu nawigacyjnego i kafelka, przejdź do określonego pulpitu nawigacyjnego w usłudze Power BI (https://powerbi.com) i otwórz kafelek w trybie koncentracji uwagi. Na przykład zobacz wyróżnione sekcje tego adresu URL:

https://powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus

Dla tego kafelka identyfikatorem URI będzie:

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

Należy zwrócić uwagę na znak ampersand (&) między nimi.

Jeśli pulpit nawigacyjny jest w grupie innej niż Mój obszar roboczy, dodaj `&GroupObjectId=<36-character-group-id>`

## <a name="open-to-a-specific-report"></a>Otwieranie określonego raportu
Ten identyfikator URI otwiera określony raport w aplikacji mobilnej usługi Power BI:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>

Aby znaleźć 36-znakowy identyfikator obiektu raportu, przejdź do określonego raportu w usłudze Power BI (https://powerbi.com). Na przykład zobacz wyróżnioną sekcję tego adresu URL:

https://powerbi.com/groups/me/reports/**df9f0e94-31df-450b-b97f-4461a7e4d300**

## <a name="open-to-a-specific-report-page"></a>Otwieranie strony określonego raportu
Ten identyfikator URI otwiera określoną stronę raportu w aplikacji mobilnej usługi Power BI:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>&reportPage=ReportSection<number>

Strona raportu jest nazywana „Sekcją raportu”, po której następuje numer. Ponownie otwórz raport w usłudze Power BI (https://powerbi.com) i przejdź do określonej strony raportu. 

Na przykład zobacz wyróżnioną sekcję tego adresu URL:

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**ReportSection11**

## <a name="open-in-full-screen-mode"></a>Otwieranie w trybie pełnoekranowym
Dodaj pogrubiony parametr, aby otworzyć określony raport w trybie pełnoekranowym:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>**&openFullScreen=true**

Na przykład: 

mspbi://app/OpenReport?ReportObjectId=500217de-50f0-4af1-b345-b81027224033&openFullScreen=true

## <a name="add-context-optional"></a>Dodawanie kontekstu (opcjonalnie)
Można również dodać kontekst w ciągu. Następnie, jeśli zachodzi potrzeba kontaktu z nami, możemy użyć tego kontekstu do filtrowania naszych danych do Twojej aplikacji. Dodawanie `&context=<app-name>` do linku

Na przykład zobacz wyróżnioną sekcję tego adresu URL: 

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**&context=SlackDeepLink**

## <a name="next-steps"></a>Następne kroki
Twoja opinia pomoże nam zdecydować, co należy zaimplementować w przyszłości. Nie zapomnij więc zagłosować na inne funkcje, które chcesz zobaczyć w aplikacjach mobilnych usługi Power BI. 

* [Aplikacje Power BI dla urządzeń przenośnych](mobile-apps-for-mobile-devices.md)
* Obserwuj @MSPowerBI na Twitterze
* Dołącz do konwersacji w [społeczności usługi Power BI](http://community.powerbi.com/)
* [Wprowadzenie do usługi Power BI](service-get-started.md)

