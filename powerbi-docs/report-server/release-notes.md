---
title: "Informacje o wersji serwera raportów usługi Power BI"
description: "W tym temacie opisano ograniczenia i problemy z serwerem raportów usługi Power BI."
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
ms.openlocfilehash: ffd0d1ce38a989121225a666ca4aa924df130216
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-report-server-release-notes"></a>Informacje o wersji serwera raportów usługi Power BI
W tym temacie opisano ograniczenia i problemy z serwerem raportów usługi Power BI.

Aby pobrać serwer raportów usługi Power BI i program Power BI Desktop zoptymalizowany pod kątem serwera raportów usługi Power BI, przejdź do [On-premises reporting with Power BI Report Server](https://powerbi.microsoft.com/report-server/) (Lokalne raportowanie za pomocą serwera raportów usługi Power BI).

## <a name="october-2017"></a>Październik 2017
* Obsługa zaimportowanych danych w raportach usługi Power BI
* Możliwość wyświetlania skoroszytów programu Excel w portalu internetowym. Można to zrobić, konfigurując program Office Online Server.
* Obsługa nowych wizualizacji tabel i macierzy w usłudze Power BI.
* Obsługa interfejsu API REST

## <a name="june-2017"></a>Czerwiec 2017
* Brak nowych elementów do czerwca 2017 r.

## <a name="may-2017"></a>Maj 2017 r.
* Raporty usługi Power BI muszą być tworzone przy użyciu programu Power BI Desktop zoptymalizowanego dla serwera usługi Power BI, aby mogły działać z serwerem raportów usługi Power BI. Program Power BI Desktop można pobrać przy użyciu linku pobierania u góry tej strony.
* Raporty usługi Power BI obsługują tylko połączenia na żywo z usługami Analysis Services (tabelarycznymi lub wielowymiarowymi).
* Brak obsługi elementów wizualnych języka R.

**Problem i wpływ na klienta:** Jeśli usługi SQL Server Reporting Services i serwer raportów usługi Power BI znajdują się na tym samym komputerze, a jeden z tych programów zostanie odinstalowany, nie będzie możliwe nawiązywanie połączenia z menedżerem konfiguracji serwera raportów przez serwer raportów.

**Obejście** Aby obejść ten problem, należy wykonać następujące operacje po odinstalowaniu jednego z serwerów.

1. Uruchom wiersz polecenia w trybie administratora.
2. Przejdź do katalogu, w którym jest zainstalowany pozostały serwer raportów.
   
    *Domyślna lokalizacja serwera raportów usługi Power BI: C:\Program Files\Microsoft Power BI Report Server*
   
    *Domyślna lokalizacja usług SQL Server Reporting Services: C:\Program Files\Microsoft SQL Server Reporting Services*
3. Następnie przejdź do następnego folderu. Będzie to folder *SSRS* lub *PBIRS* zależnie od pozostałego serwera.
4. Przejdź do folderu WMI.
5. Uruchom następujące polecenie:
   
    ```
    regsvr32 /i ReportingServicesWMIProvider.dll
    ```
   
    Następujący błąd można zignorować, jeśli zostanie wyświetlony.
   
    ```
    The module "ReportingServicesWMIProvider.dll" was loaded but the entry-point DLLInstall was not found. Make sure that "ReportingServicesWMIProvider.dll" is a valid DLL or OCX file and then try again.
    ```

## <a name="next-steps"></a>Następne kroki
[Co nowego w serwerze raportów usługi Power BI](whats-new.md)  
[Podręcznik użytkownika](user-handbook-overview.md)  
[Podręcznik administratora](admin-handbook-overview.md)  
[Szybki start: instalowanie serwera raportów usługi Power BI](quickstart-install-report-server.md)  
[Instalowanie programu Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

