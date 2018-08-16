---
title: Adresy URL usługi Power BI
description: Punkty końcowe powinny być dostępne dla klientów korzystających z usługi Power BI
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/13/2018
ms.openlocfilehash: 8e29fa0c9471bb865619102247f38776208c3d87
ms.sourcegitcommit: 8990028a348b642ba5c96f001fe3a4280f0166ee
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/14/2018
ms.locfileid: "40101144"
---
# <a name="power-bi-urls"></a>Adresy URL usługi Power BI

**Usługa online Power BI**, nazywana też aplikacją Power BI SaaS (oprogramowanie jako usługa), wymaga połączenia z Internetem. Poniższe punkty końcowe powinny być dostępne dla klientów korzystających z usługi online Power BI.

Aby móc korzystać z usługi online Power BI, musisz mieć połączenie z punktami końcowymi oznaczonymi jako **wymagane** w poniższych tabelach i punktami końcowymi oznaczonymi jako **wymagane** w połączonych witrynach. Jeśli link do witryny zewnętrznej odwołuje się do określonej sekcji, wystarczy przejrzeć punkty końcowe w tej sekcji.

Punkty końcowe oznaczone jako **opcjonalne** można również **dodać do listy dozwolonych**, aby umożliwić działanie określonych funkcji.

Usługa online Power BI wymaga tylko otwartego portu TCP 443 dla podanych punktów końcowych.

Symbole wieloznaczne (*) reprezentują wszystkie poziomy w domenie głównej — gdy informacje są niedostępne, jest używany ciąg „Nie dotyczy”. Kolumna **Miejsca docelowe** zawiera listę nazw FQDN/domen i linków do witryn zewnętrznych, które zawierają więcej informacji o punkcie końcowym.

>[!Important]
>Informacje przedstawione w poniższych tabelach nie dotyczą **chmury dla instytucji rządowych USA**, **chmury w Niemczech** i **chmury w Chinach**.

## <a name="authentication"></a>Uwierzytelnianie

Usługa Power BI zależy od wymaganych punktów końcowych w sekcjach tożsamości i uwierzytelniania usługi Office 365. Aby móc korzystać z usługi Power BI, musisz mieć możliwość łączenia się z punktami końcowymi w poniższej połączonej witrynie.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Wymagane:** uwierzytelnianie i tożsamość | Zobacz [sekcję dotyczącą uwierzytelniania i tożsamości w usłudze Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_identity) w witrynie z listą dozwolonych w usłudze Office 365 | Nie dotyczy |

## <a name="general-site-usage"></a>Ogólne użycie witryny

Aby móc używać usługi Power BI do celów ogólnych, musisz mieć możliwość nawiązania połączenia z punktami końcowymi w poniższych połączonych witrynach i tabeli.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Wymagane:** interfejsy API zaplecza | *.analysis.windows.net | TCP 443 |
| 2 | **Wymagane:** integracja usługi Office 365 | Zobacz [sekcję dotyczącą portalu usługi Office 365 i udostępniania](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity) w witrynie z listą dozwolonych w usłudze Office 365 | Nie dotyczy |
| 3 | **Wymagane:** portal | app.powerbi.com | TCP 443 |
| 4 | **Wymagane:** telemetria usługi | dc.services.visualstudio.com | TCP 443 |
| 5 | **Opcjonalne:** komunikaty informacyjne | dynmsg.modpim.com | TCP 443 |
| 6 | **Opcjonalne:** ankiety serwera NPS | nps.onyx.azure.net | TCP 443 |

## <a name="administration"></a>Administracja

Do wykonywania zadań administracyjnych w usłudze Power BI jest konieczna możliwość nawiązania połączenia z punktami końcowymi w poniższych połączonych witrynach.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Wymagane:** do zarządzania użytkownikami i wyświetlania dzienników inspekcji | Zobacz [sekcję dotyczącą portalu usługi Office 365 i udostępniania](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity) w witrynie z listą dozwolonych w usłudze Office 365 | Nie dotyczy |

## <a name="get-data"></a>Pobierz dane

Aby móc pobierać dane z konkretnych źródeł danych, takich jak usługa OneDrive, musisz mieć możliwość nawiązania połączenia z punktami końcowymi w poniższej tabeli.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Wymagane:** AppSource (aplikacje wewnętrzne lub zewnętrzne w usłudze Power BI) | appsource.microsoft.com | TCP 443 |
| 2 | **Opcjonalne:** importowanie plików z usługi OneDrive w wersji dla osób prywatnych | Zobacz [witrynę wymaganych adresów URL i portów dla witryny usługi OneDrive](https://support.office.com/en-ie/article/required-urls-and-ports-for-onedrive-ce15d2cc-52ef-42cd-b738-d9c6f9b03f3a) | Nie dotyczy |
| 3 | **Opcjonalne:** 60-sekundowy samouczek wideo dotyczący usługi Power BI | *.doubleclick.net </br> *.ggpht.com </br> *.google.com </br> *.googlevideo.com </br> *.youtube.com </br> *.ytimg.com </br> fonts.gstatic.com | TCP 443 |
| 4 | **Opcjonalne:** źródła danych przesyłania strumieniowego PubNub | Zobacz [dokumentację usługi PubNub](https://support.pubnub.com/support/solutions/articles/14000043522) | Nie dotyczy |

## <a name="dashboard-and-report-integration"></a>Integracja pulpitów nawigacyjnych i raportów 

Możliwość zapewnienia obsługi pulpitów nawigacyjnych i raportów w usłudze Power BI zależy od pewnych punktów końcowych. Musisz mieć możliwość nawiązania połączenia z punktami końcowymi w poniższych połączonych witrynach i tabeli.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Wymagane:** integracja z programem Excel | Zobacz [sekcję dotyczącą aplikacji Office Online](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline) w witrynie z listą dozwolonych w usłudze Office 365 | Nie dotyczy |

## <a name="custom-visuals"></a>Wizualizacje niestandardowe

Możliwość wyświetlania niestandardowych wizualizacji i uzyskiwania do nich dostępu w usłudze Power BI zależy od pewnych punktów końcowych. Musisz mieć możliwość nawiązania połączenia z punktami końcowymi w poniższych połączonych witrynach i tabeli.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Wymagane:** importowanie niestandardowej wizualizacji z interfejsu witryny Marketplace i pliku | *.microsoft.com </br> *.bing.com </br> *.msecnd.net </br> *.osi.office.net </br> *.azureedge.net </br> ajax.aspnetcdn.com </br> nexus.ensighten.com </br> store.office.com | TCP 443 |
| 2 | **Opcjonalne:** Mapy Bing | bing.com </br> platform.bing.com </br> *.dynamic.tiles.virtualearth.net </br> *.virtualearth.net | TCP 443 |
| 3 | **Opcjonalne:** PowerApps | Zobacz [sekcję dotyczącą wymaganych usług](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) w witrynie wymagań systemowych usługi PowerApps | Nie dotyczy |
| 4 | **Opcjonalne:** Visio | Zobacz [sekcję dotyczącą aplikacji Office Online](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline) w witrynie z listą dozwolonych w usłudze Office 365 | Nie dotyczy |