---
title: "Omówienie podręcznika administratora — serwer raportów usługi Power BI"
description: "Witamy w podręczniku administratora serwera raportów usługi Power BI, który jest lokalizacją lokalną służącą do przechowywania podzielonych na strony raportów dla urządzeń przenośnych i usługi Power BI, jak również zarządzania nimi."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/01/2017
ms.author: asaxton
ms.openlocfilehash: 6307e6cc3beb119ffaba40344736ff29e293fc95
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="administrator-handbook-overview-power-bi-report-server"></a>Omówienie podręcznika administratora — serwer raportów usługi Power BI
Witamy w podręczniku administratora serwera raportów usługi Power BI, który jest lokalizacją lokalną służącą do przechowywania podzielonych na strony raportów dla urządzeń przenośnych i usługi Power BI, jak również zarządzania nimi.

![](media/admin-handbook-overview/admin-handbook.png)

Podręcznik ten pomoże zrozumieć koncepcje planowania, wdrażania i zarządzania serwerem raportów usługi Power BI.

## <a name="installing-and-migration"></a>Instalowanie i migracja
Musisz zainstalować serwer raportów usługi Power BI, aby rozpocząć korzystanie z niego. Mamy informacje, które umożliwiają realizację tego zadania.

Przed rozpoczęciem instalacji przeprowadź uaktualnienie i migrację do serwera raportów usługi Power BI. Przyjrzyjmy się [wymaganiom systemowym](system-requirements.md) dla serwera raportów.

### <a name="installing"></a>Instalowanie
Jeżeli wdrażasz nowy serwer raportów usługi Power BI, używasz następujących dokumentów jako pomocy. Szybki Start jest dostępny od ręki. Lub możesz zapoznać się z pełnymi szczegółami w dokumencie instalacji.

* [Szybki start: instalowanie serwera raportów usługi Power BI](quickstart-install-report-server.md)
* [Instalacja serwera raportów usługi Power BI](install-report-server.md)

### <a name="migration"></a>Migracja
Nie ma dostępnego od razu uaktualnienia dla usług SQL Server Reporting Services. Jeśli masz istniejące wystąpienie usług SQL Server Reporting Services, które ma zostać serwerem raportów usługi Power BI, musisz przeprowadzić migrację. Istnieją inne przyczyny, które również powodują, że zechcesz przeprowadzić migrację. Zapoznaj się z dokumentem migracji, aby uzyskać więcej informacji.

[Migrowanie instalacji serwera raportów](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>Konfigurowanie serwera raportów
Podczas konfigurowania serwera raportów dostępnych jest wiele opcji. Czy będziesz używać protokołu SSL? Czy chcesz skonfigurować serwer poczty e-mail? Czy chcesz zintegrować z usługą Power BI w celu przypinania wizualizacji?

Większość konfiguracji zostanie przeprowadzona w Menedżerze konfiguracji serwera raportów. Zapoznaj się z dokumentacją [menedżera konfiguracji](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode), aby uzyskać więcej szczegółowych informacji.

## <a name="security"></a>Zabezpieczenia
Zabezpieczenia i ochrona są ważne dla każdej organizacji. Informacje na temat uwierzytelniania, autoryzacji, ról i uprawnień możesz znaleźć w dokumentacji [zabezpieczeń](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection).

## <a name="next-steps"></a>Następne kroki
[Szybki start: instalowanie serwera raportów usługi Power BI](quickstart-install-report-server.md)  
[Jak znaleźć klucz produktu serwera raportów](find-product-key.md)  
[Instalowanie programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI](install-powerbi-desktop.md)  
[Instalowanie programu Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

