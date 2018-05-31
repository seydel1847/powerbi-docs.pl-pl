---
title: Omówienie administracji, serwer raportów usługi Power BI
description: W tym artykule przedstawiono omówienie administracji serwera raportów usługi Power BI, który jest lokalizacją lokalną służącą do przechowywania raportów podzielonych na strony, raportów dla urządzeń przenośnych i raportów usługi Power BI, jak również zarządzania nimi.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/07/2018
ms.author: maghan
ms.openlocfilehash: 52b2c9cac7fd07564480fdbf3a6a91e04e72db11
ms.sourcegitcommit: c29525cbac2e747edb4dd3a1841084bb0ce42582
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883094"
---
# <a name="admin-overview-power-bi-report-server"></a>Omówienie administracji, serwer raportów usługi Power BI
W tym artykule przedstawiono omówienie administracji serwera raportów usługi Power BI, który jest lokalizacją lokalną służącą do przechowywania raportów podzielonych na strony, raportów dla urządzeń przenośnych i raportów usługi Power BI, jak również zarządzania nimi. W tym artykule przedstawiono koncepcje planowania i wdrażania serwera raportów usługi Power BI oraz zarządzania nim, a także linki do dodatkowych informacji.

![](media/admin-handbook-overview/admin-handbook.png)



## <a name="installing-and-migration"></a>Instalowanie i migracja
Musisz zainstalować serwer raportów usługi Power BI, aby rozpocząć korzystanie z niego. Mamy informacje, które umożliwiają realizację tego zadania.

Przed rozpoczęciem instalacji przeprowadź uaktualnienie i migrację do serwera raportów usługi Power BI. Przyjrzyjmy się [wymaganiom systemowym](system-requirements.md) dla serwera raportów.

### <a name="installing"></a>Instalowanie
Jeżeli wdrażasz nowy serwer raportów usługi Power BI, użyj poniższego dokumentu jako pomocy. 

[Instalacja serwera raportów usługi Power BI](install-report-server.md)

### <a name="migration"></a>Migracja
Nie ma dostępnego od razu uaktualnienia dla usług SQL Server Reporting Services. Jeśli masz istniejące wystąpienie usług SQL Server Reporting Services, które ma zostać serwerem raportów usługi Power BI, musisz przeprowadzić migrację. Istnieją inne przyczyny, które również powodują, że zechcesz przeprowadzić migrację. Zapoznaj się z dokumentem migracji, aby uzyskać więcej informacji.

[Migrowanie instalacji serwera raportów](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>Konfigurowanie serwera raportów
Podczas konfigurowania serwera raportów dostępnych jest wiele opcji. Czy będziesz używać protokołu SSL? Czy chcesz skonfigurować serwer poczty e-mail? Czy chcesz zintegrować z usługą Power BI w celu przypinania wizualizacji?

Większość konfiguracji zostanie przeprowadzona w Menedżerze konfiguracji serwera raportów. Zapoznaj się z dokumentacją [menedżera konfiguracji](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode), aby uzyskać więcej szczegółowych informacji.

## <a name="security"></a>Zabezpieczenia
Zabezpieczenia i ochrona są ważne dla każdej organizacji. Informacje na temat uwierzytelniania, autoryzacji, ról i uprawnień możesz znaleźć w dokumentacji [zabezpieczeń](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection).

## <a name="next-steps"></a>Następne kroki
[Instalacja serwera raportów usługi Power BI](install-report-server.md)  
[Znajdowanie klucza produktu serwera raportów](find-product-key.md)  
[Instalowanie programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI](install-powerbi-desktop.md)  
[Instalowanie programu Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

