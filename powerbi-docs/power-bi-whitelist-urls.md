---
title: Adresy URL usługi Power BI do umieszczania na liście dozwolonych
description: W tym artykule opisano punkty końcowe, które powinny być dostępne dla użytkowników korzystających z usługi Power BI.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/22/2018
ms.custom: seodec18
ms.openlocfilehash: 39a62950260789b50be034c2f55808e6991764db
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54294098"
---
# <a name="power-bi-urls-for-whitelisting"></a>Adresy URL usługi Power BI do umieszczania na liście dozwolonych

**Usługa online Power BI**, nazywana też aplikacją Power BI SaaS (oprogramowanie jako usługa), wymaga połączenia z Internetem. Poniższe punkty końcowe powinny być dostępne dla klientów korzystających z usługi online Power BI.

Aby móc korzystać z usługi online Power BI, musisz mieć połączenie z punktami końcowymi oznaczonymi jako **wymagane** w poniższych tabelach i punktami końcowymi oznaczonymi jako **wymagane** w połączonych witrynach. Jeśli link do witryny zewnętrznej odwołuje się do określonej sekcji, wystarczy przejrzeć punkty końcowe w tej sekcji.

Punkty końcowe oznaczone jako **opcjonalne** można również **dodać do listy dozwolonych**, aby umożliwić działanie określonych funkcji.

Usługa online Power BI wymaga tylko otwartego portu TCP 443 dla podanych punktów końcowych.

Symbole wieloznaczne (*) reprezentują wszystkie poziomy w domenie głównej — gdy informacje są niedostępne, jest używany ciąg „Nie dotyczy”. Kolumna **Miejsca docelowe** zawiera listę nazw FQDN/domen i linków do witryn zewnętrznych, które zawierają więcej informacji o punkcie końcowym.

>[!Important]
>Informacje przedstawione w poniższych tabelach nie dotyczą **chmury dla instytucji rządowych USA**, **chmury w Niemczech** ani **chmury w Chinach**.

## <a name="authentication"></a>Uwierzytelnianie

Usługa Power BI zależy od wymaganych punktów końcowych w sekcjach tożsamości i uwierzytelniania usługi Office 365. Aby móc korzystać z usługi Power BI, musisz mieć możliwość łączenia się z punktami końcowymi w poniższej połączonej witrynie.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
| --- | --- | --- | --- |
| 1 | **Wymagane:** Uwierzytelnianie i tożsamość | Zobacz dokumentację usługi Office 365 dla [aplikacji Office Online i typowych adresów URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online)  | Nie dotyczy |

## <a name="general-site-usage"></a>Ogólne użycie witryny

Aby móc używać usługi Power BI do celów ogólnych, musisz mieć możliwość nawiązania połączenia z punktami końcowymi w poniższych połączonych witrynach i tabeli.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
| --- | --- | --- | --- |
| 1 | **Wymagane:** Interfejsy API zaplecza | *.analysis.windows.net | TCP 443 |
| 2 | **Wymagane:** Integracja usługi Office 365 | Zobacz dokumentację usługi Office 365 dla [aplikacji Office Online i typowych adresów URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | Nie dotyczy |
| 3 | **Wymagane:** Portal | app.powerbi.com | TCP 443 |
| 4 | **Wymagane:** Telemetria usługi | dc.services.visualstudio.com | TCP 443 |
| 5 | **Opcjonalne:** Komunikaty informacyjne | dynmsg.modpim.com | TCP 443 |
| 6 | **Opcjonalne:** Ankiety serwera NPS | nps.onyx.azure.net | TCP 443 |
| | | |

## <a name="administration"></a>Administracja

Do wykonywania zadań administracyjnych w usłudze Power BI jest konieczna możliwość nawiązania połączenia z punktami końcowymi w poniższych połączonych witrynach.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
| --- | --- | --- | --- |
| 1 | **Wymagane:** Do zarządzania użytkownikami i wyświetlania dzienników inspekcji | Zobacz dokumentację usługi Office 365 dla [aplikacji Office Online i typowych adresów URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | Nie dotyczy |
| | | |

## <a name="getting-data"></a>Pobieranie danych

Aby móc pobierać dane z konkretnych źródeł danych, takich jak usługa OneDrive, musisz mieć możliwość nawiązania połączenia z punktami końcowymi w poniższej tabeli. W przypadku specyficznych źródeł danych używanych w Twojej organizacji może być wymagany dostęp do dodatkowych domen internetowych i adresów URL.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
| --- | --- | --- | --- |
| 1 | **Wymagane:** AppSource (aplikacje wewnętrzne lub zewnętrzne w usłudze Power BI) | appsource.microsoft.com </br> *.s-microsoft.com  | TCP 443 |
| 2 | **Opcjonalne:** Logowanie i pobieranie danych dla pakietów zawartości | Zależne od używanych pakietów zawartości | Zależne od używanych pakietów zawartości |
| 3 | **Opcjonalne:** Importowanie plików z usługi OneDrive w wersji dla osób prywatnych | Zobacz [witrynę wymaganych adresów URL i portów dla witryny usługi OneDrive](https://docs.microsoft.com/onedrive/required-urls-and-ports) | Nie dotyczy |
| 4 | **Opcjonalne:** 60-sekundowy samouczek wideo dotyczący usługi Power BI | *.doubleclick.net </br> *.ggpht.com </br> *.google.com </br> *.googlevideo.com </br> *.youtube.com </br> *.ytimg.com </br> fonts.gstatic.com | TCP 443 |
| 5 | **Opcjonalne:** Źródła danych przesyłania strumieniowego PubNub | Zobacz [dokumentację usługi PubNub](https://support.pubnub.com/support/solutions/articles/14000043522) | Nie dotyczy |
| | | |

## <a name="dashboard-and-report-integration"></a>Integracja pulpitów nawigacyjnych i raportów

Możliwość zapewnienia obsługi pulpitów nawigacyjnych i raportów w usłudze Power BI zależy od pewnych punktów końcowych. Musisz mieć możliwość nawiązania połączenia z punktami końcowymi w poniższych połączonych witrynach i tabeli.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
| --- | --- | --- | --- |
| 1 | **Wymagane:** Integracja z programem Excel | Zobacz dokumentację usługi Office 365 dla [aplikacji Office Online i typowych adresów URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | Nie dotyczy |
| | | |

## <a name="custom-visuals"></a>Wizualizacje niestandardowe

Możliwość wyświetlania niestandardowych wizualizacji i uzyskiwania do nich dostępu w usłudze Power BI zależy od pewnych punktów końcowych. Musisz mieć możliwość nawiązania połączenia z punktami końcowymi w poniższych połączonych witrynach i tabeli.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
| --- | --- | --- | --- |
| 1 | **Wymagane:** Importowanie niestandardowej wizualizacji z interfejsu witryny Marketplace lub z pliku | *.azureedge.net </br> *.blob.core.windows.net </br> store.office.com | TCP 443 |
| 2 | **Opcjonalne:** Mapy usługi Bing | bing.com </br> platform.bing.com </br> *.virtualearth.net | TCP 443 |
| 3 | **Opcjonalne:** PowerApps | Zobacz [sekcję dotyczącą wymaganych usług](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) w witrynie wymagań systemowych usługi PowerApps | Nie dotyczy |
| 4 | **Opcjonalne:** Visio | Zobacz dokumentację usługi Office 365 dla [aplikacji Office Online i typowych adresów URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online), a także dla usług [SharePoint Online i OneDrive dla Firm](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business) | Nie dotyczy |
| | | |

## <a name="related-external-sites"></a>Pokrewne witryny zewnętrzne

Usługa Power BI zawiera linki do innych powiązanych witryn. Są to witryny z dokumentacją oraz z informacjami dotyczącymi pomocy technicznej, próśb o dodanie nowych funkcji i nie tylko. Te witryny nie będą miały wpływu na funkcjonalność usługi Power BI, więc w razie potrzeby można opcjonalnie umieścić je na liście dozwolonych.

| Wiersz | Przeznaczenie | Miejsca docelowe | Porty |
| --- | --- | --- | --- |
| 1 | **Opcjonalne:** Witryna społeczności | community.powerbi.com </br> oxcrx34285.i.lithium.com | TCP 443 |
| 2 | **Opcjonalne:** Witryna dokumentacji | docs.microsoft.com </br> img-prod-cms-rt-microsoft-com.akamaized.net </br> statics-uhf-eas.akamaized.net </br> cdnssl.clicktale.net </br> ing-district.clicktale.net | TCP 443 |
| 3 | **Opcjonalne:** Witryna pobierania (dla programu Power BI Desktop itd.) | download.microsoft.com | TCP 443 |
| 4 | **Opcjonalne:** Zewnętrzne przekierowania | aka.ms </br> go.microsoft.com | TCP 443 |
| 5 | **Opcjonalne:** Witryna z opiniami o pomysłach| ideas.powerbi.com </br> powerbi.uservoice.com | TCP 443 |
| 6 | **Opcjonalne:** Witryna usługi Power BI — strona docelowa, linki „Dowiedz się więcej”, witryna pomocy technicznej, linki do plików do pobrania, pokaz partnera itp. | powerbi.microsoft.com | TCP 443 |
| 7 | **Opcjonalne:** Centrum deweloperów usługi Power BI | dev.powerbi.com | TCP 443 |
| 8 | **Opcjonalne:** Witryna pomocy technicznej | support.powerbi.com </br> s3.amazonaws.com </br> *.olark.com </br> logx.optimizely.com </br> mscom.demdex.net </br> tags.tiqcdn.com | TCP 443 |
| | | |