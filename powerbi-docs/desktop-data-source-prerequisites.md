---
title: Wymagania wstępne dotyczące źródeł danych usługi Power BI
description: Wymagania wstępne dotyczące źródeł danych usługi Power BI
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 282526e18777e623725859adc84475525dcf25ba
ms.sourcegitcommit: ae4d771b883b654358a6a94dd784ea9bdf3d3aa3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/28/2018
---
# <a name="power-bi-data-source-prerequisites"></a>Wymagania wstępne dotyczące źródeł danych usługi Power BI
W przypadku każdego dostawcy danych usługa Power BI obsługuje określoną wersję dostawcy na obiektach. Aby uzyskać więcej informacji o źródłach danych dostępnych dla usługi Power BI, zobacz [Źródła danych](desktop-data-sources.md). Poniższa tabela opisuje te wymagania.

| Źródło danych | Dostawca | Minimalna wersja dostawcy | Minimalna wersja źródła danych | Obsługiwane obiekty źródła danych | Link pobierania |
| --- | --- | --- | --- | --- | --- |
| SQL Server |ADO.NET (wbudowany w programie .NET Framework) |.Net Framework 3.5 (tylko) |SQL Server 2005 lob nowszy |Tabele/widoki, funkcje skalarne, funkcje tabelaryczne |Zawarte w programie .NET Framework 3.5 lub nowszym |
| Access |Aparat bazy danych programu Microsoft Access (ACE) |ACE 2010 z dodatkiem SP1 |Bez ograniczeń |Tabele/widoki |[Link pobierania](http://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Excel (tylko pliki xls) (patrz uwaga 1) |Aparat bazy danych programu Microsoft Access (ACE) |ACE 2010 z dodatkiem SP1 |Bez ograniczeń |Tabele, arkusze |[Link pobierania](http://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Oracle (patrz uwaga 2) |ODP.NET |ODAC 11.2 w wersji 5 (11.2.0.3.20) |9.x lub nowszy |Tabele/widoki |[Link pobierania](http://go.microsoft.com/fwlink/?linkid=272376&clcid=0x409) |
| | Klient System.Data.Oracle (wbudowany w programie .NET Framework) |.NET Framework 3.5 |9.x lub nowszy |Tabele/widoki |Zawarte w programie .NET Framework 3.5 lub nowszym |
| IBM DB2 |Klient ADO.Net od firmy IBM (część pakietu sterowników serwera danych IBM) |10.1 |9.1+ |Tabele/widoki |[Link pobierania](http://go.microsoft.com/fwlink/?linkid=274911&clcid=0x409) |
| MySQL |Connector/Net |6.6.5 |5.1 |Tabele/widoki, funkcje skalarne |[Link pobierania](http://go.microsoft.com/fwlink/?linkid=278885&clcid=0x409) |
| PostgreSQL |Dostawca NPGSQL ADO.NET |2.0.12 |7.4 |Tabele/widoki |[Link pobierania](http://go.microsoft.com/fwlink/?linkid=282716&clcid=0x409) |
| Teradata |Dostawca danych programu .NET dla programu Teradata |14+ |12+ |Tabele/widoki |[Link pobierania](http://go.microsoft.com/fwlink/?linkid=278886&clcid=0x409) |
| SAP Sybase SQL Anywhere |iAnywhere.Data.SQLAnywhere dla .NET 3.5 |16+ |16+ |Tabele/widoki |[Link pobierania](http://go.microsoft.com/fwlink/?linkid=324846) |

>[!NOTE]
>Pliki programu Excel z rozszerzeniem xlsx nie wymagają oddzielnej instalacji dostawcy.

>[!NOTE]
>Dostawcy Oracle wymagają również oprogramowania klienta Oracle (wersja 8.1.7 lub nowsza).
> 
> 

