---
title: Lokalna brama danych
description: "Ten temat zawiera omówienie lokalnej bramy danych dla usługi Power BI. Brama ta umożliwia korzystanie ze źródeł danych obsługujących zapytania bezpośrednie. Można jej również używać do odświeżania zestawów danych w chmurze za pomocą danych lokalnych."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 11/02/2017
ms.author: davidi
ms.openlocfilehash: e905fa099537f49a9a8e69a9d3121f955b74864f
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2017
---
# <a name="on-premises-data-gateway"></a>Lokalna brama danych
Lokalna brama danych działa jak most, zapewniając szybki i bezpieczny transfer danych między lokalnymi danymi (danymi, które nie są w chmurze) a usługami Power BI, Microsoft Flow, Logic Apps i PowerApps.

Brama może być używana z różnymi usługami. Jeśli korzystasz zarówno z usługi Power BI, jak i PowerApps, możesz używać jednej bramy. Zależy to od konta, na które się logujesz.

> [!NOTE]
> We wszystkich trybach pracy lokalnej bramy danych zaimplementowano kompresję danych i szyfrowanie transportu.
> 
> 

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-requirements-include.md)]

### <a name="limitations-of-analysis-services-live-connections"></a>Ograniczenia połączeń na żywo usług Analysis Services
W przypadku wystąpień tabelarycznych lub wielowymiarowych można używać połączenia na żywo.

| **Wersja serwera** | **Wymagana jednostka SKU** |
| --- | --- |
| 2012 SP1 CU4 lub nowszy |Jednostka SKU w wersji Business Intelligence i Enterprise |
| 2014 |Jednostka SKU w wersji Business Intelligence i Enterprise |
| 2016 |Jednostka SKU w wersji Standard lub nowsza |

* Formatowanie na poziomie komórki i funkcje tłumaczenia nie są obsługiwane.
* Akcje i nazwane zestawy nie są widoczne w usłudze Power BI, ale można łączyć się z wielowymiarowymi modułami zawierającymi akcje lub nazwane zestawy i tworzyć wizualizacje oraz raporty.

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="download-and-install-the-on-premises-data-gateway"></a>Pobieranie i instalowanie lokalnej bramy danych
Aby pobrać bramę, wybierz pozycję **Brama danych** w menu Pliki do pobrania. Pobierz [lokalną bramę danych](http://go.microsoft.com/fwlink/?LinkID=820925).

![](media/service-gateway-onprem/powerbi-download-data-gateway.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-install-include](./includes/gateway-onprem-install-include.md)]

## <a name="install-the-gateway-in-personal-mode"></a>Instalowanie bramy w trybie osobistym
> [!NOTE]
> Tryb osobisty działa tylko z usługą Power BI.
> 
> 

Po zainstalowaniu bramy osobistej musisz uruchomić **Kreatora konfiguracji bramy Power BI Gateway – Personal**.

![](media/service-gateway-onprem/personal-gateway-launch-configuration.png)

Następnie zaloguj się do usługi Power BI, aby zarejestrować bramę w usłudze w chmurze.

![](media/service-gateway-onprem/personal-gateway-signin.png)

Musisz również podać nazwę użytkownika i hasło do systemu Windows na potrzeby uruchamiania usługi systemu Windows. Nie musisz wskazywać własnego konta systemu Windows. Usługa bramy zostanie uruchomiona przy użyciu tego konta.

![](media/service-gateway-onprem/personal-gateway-windows-service.png)

Po zakończeniu instalacji przejdź do zestawów danych w usłudze Power BI i upewnij się, że wprowadzono poświadczenia dla lokalnych źródeł danych.

<a name="credentials"></a>

## <a name="storing-encrypted-credentials-in-the-cloud"></a>Przechowywanie zaszyfrowanych poświadczeń w chmurze
Po dodaniu źródła danych do bramy musisz podać poświadczenia dla tego źródła danych. Wszystkie zapytania w tym źródle danych będą wykonywane z użyciem tych poświadczeń. Przed zapisaniem poświadczeń w chmurze są one bezpiecznie szyfrowane za pomocą asymetrycznych algorytmów, uniemożliwiających odszyfrowanie poświadczeń w chmurze. W przypadku próby dostępu do źródeł danych poświadczenia są wysyłane do maszyny z uruchomioną bramą i odszyfrowywane lokalnie.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

<!-- How the gateway works -->
[!INCLUDE [gateway-onprem-how-it-works-include](./includes/gateway-onprem-how-it-works-include.md)]

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Jeśli masz problemy z instalacją i konfiguracją bramy, zobacz [Rozwiązywanie problemów z lokalną bramą danych](service-gateway-onprem-tshoot.md). Jeśli uważasz, że występuje problem z zaporą, zobacz sekcję dotyczącą [zapory lub serwera proxy](service-gateway-onprem-tshoot.md#firewall-or-proxy) w artykule na temat rozwiązywania problemów.

Jeśli sądzisz, że problemy z bramą dotyczą serwera proxy, zobacz [Konfigurowanie ustawień serwera proxy dla bram Power BI Gateway](service-gateway-proxy.md).

## <a name="next-steps"></a>Następne kroki
[Zarządzanie źródłami danych — Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Zarządzanie źródłami danych — SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Zarządzanie źródłami danych — SQL Server](service-gateway-enterprise-manage-sql.md)  
[Zarządzanie źródłami danych — Oracle](service-gateway-onprem-manage-oracle.md)  
[Zarządzanie źródłami danych — importowanie/zaplanowane odświeżanie](service-gateway-enterprise-manage-scheduled-refresh.md)  
[Lokalna brama danych — szczegóły](service-gateway-onprem-indepth.md)  
[Lokalna brama danych (tryb osobisty) — nowa wersja bramy osobistej](service-gateway-personal-mode.md)
[Konfigurowanie ustawień serwera proxy dla lokalnej bramy danych](service-gateway-proxy.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

