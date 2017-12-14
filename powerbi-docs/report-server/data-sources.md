---
title: "Źródła danych raportów usługi Power BI na Serwerze raportów usługi Power BI"
description: "Raporty usługi Power BI mogą łączyć się z różnymi źródłami danych. Zależnie od sposobu użycia danych są dostępne różne źródła danych."
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
ms.openlocfilehash: f800f79fd49854e0f26a19de1fc9475dad0e1045
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Źródła danych raportów usługi Power BI na Serwerze raportów usługi Power BI
Raporty usługi Power BI mogą łączyć się z różnymi źródłami danych. Zależnie od sposobu użycia danych są dostępne różne źródła danych. Dane można zaimportować lub wykonywać względem nich zapytania bezpośrednio przy użyciu zapytania bezpośredniego lub połączenia na żywo z usługami SQL Server Analysis Services.

Te źródła danych są specyficzne dla raportów Power BI używanych na Serwerze raportów Power BI. Aby uzyskać informacje o źródłach danych obsługiwanych w raportach z podziałem na strony, zobacz [Źródła danych obsługiwane przez usługi Reporting Services](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Wszystkie źródła danych w raporcie programu Power BI Desktop muszą być obsługiwane, aby można było skonfigurować zaplanowane odświeżanie.
> 
> 

## <a name="list-of-supported-data-sources"></a>Lista obsługiwanych źródeł danych
Inne źródła danych mogą działać, nawet jeśli nie znajdują się na liście obsługiwanych źródeł.

| **Źródło danych** | **Dane w pamięci podręcznej** | **Zaplanowane odświeżanie** | **Połączenie na żywo/zapytanie bezpośrednie** |
| --- | --- | --- | --- |
| Baza danych programu SQL Server |Tak |Tak |Tak |
| SQL Server Analysis Services |Tak |Tak |Tak |
| Azure SQL Database |Tak |Tak |Tak |
| Azure SQL Data Warehouse |Tak |Tak |Tak |
| Excel |Tak |Tak |Nie |
| Baza danych programu Access |Tak |Tak |Nie |
| Active Directory |Tak |Tak |Nie |
| Amazon Redshift |Tak |Nie |Nie |
| Azure Blob Storage |Tak |Tak |Nie |
| Azure Data Lake Store |Tak |Nie |Nie |
| Azure HDInsight (HDFS) |Tak |Tak |Nie |
| Azure HDInsight (Spark) |Tak |Tak |Nie |
| Azure Table Storage |Tak |Tak |Nie |
| Dynamics 365 (online) |Tak |Nie |Nie |
| Facebook |Tak |Nie |Nie |
| Folder |Tak |Tak |Nie |
| Google Analytics |Tak |Nie |Nie |
| Plik usługi Hadoop (HDFS) |Tak |Nie |Nie |
| Baza danych IBM DB2 |Tak |Tak |Nie |
| Impala |Tak |Nie |Nie |
| JSON |Tak |Tak |Nie |
| Microsoft Exchange |Tak |Nie |Nie |
| Microsoft Exchange Online |Tak |Nie |Nie |
| Baza danych MySQL |Tak |Tak |Nie |
| Źródło danych OData |Tak |Tak |Nie |
| ODBC |Tak |Tak |Nie |
| OLE DB |Tak |Tak |Nie |
| Baza danych Oracle |Tak |Tak |Tak |
| Baza danych PostgreSQL |Tak |Tak |Nie |
| Usługa Power BI |Nie |Nie |Nie |
| Skrypt języka R |Tak |Nie |Nie |
| Obiekty Salesforce |Tak |Nie |Nie |
| Raporty Salesforce |Tak |Nie |Nie |
| SAP Business Warehouse Server |Tak |Tak |Tak |
| Baza danych SAP HANA |Tak |Tak |Tak |
| Folder programu SharePoint (lokalny) |Tak |Tak |Nie |
| Lista programu SharePoint (lokalna) |Tak |Tak |Nie |
| Lista usługi SharePoint Online |Tak |Nie |Nie |
| Snowflake |Tak |Nie |Nie |
| Baza danych Sybase |Tak |Tak |Nie |
| Baza danych Teradata |Tak |Tak |Tak |
| Plik tekstowy/CSV |Tak |Tak |Nie |
| Internet |Tak |Tak |Nie |
| Plik XML |Tak |Tak |Nie |
| appFigures (beta) |Tak |Nie |Nie |
| Baza danych Azure Analysis Services (beta) |Tak |Nie |Nie |
| Azure Cosmos DB (beta) |Tak |Nie |Nie |
| Azure HDInsight Spark (beta) |Tak |Nie |Nie |
| Common Data Service (beta) |Tak |Nie |Nie |
| comScore Digital Analytix (beta) |Tak |Nie |Nie |
| Dynamics 365 for Customer Insights (beta) |Tak |Nie |Nie |
| Dynamics 365 for Financials (beta) |Tak |Nie |Nie |
| GitHub (beta) |Tak |Nie |Nie |
| Google BigQuery (beta) |Tak |Nie |Nie |
| Baza danych IBM Informix (beta) |Tak |Nie |Nie |
| IBM Netezza (beta) |Tak |Nie |Nie |
| Kusto (beta) |Tak |Nie |Nie |
| MailChimp (beta) |Tak |Nie |Nie |
| Microsoft Azure Consumption Insights (beta) |Tak |Nie |Nie |
| Mixpanel (beta) |Tak |Nie |Nie |
| Planview Enterprise (beta) |Tak |Nie |Nie |
| Projectplace (beta) |Tak |Nie |Nie |
| QuickBooks Online (beta) |Tak |Nie |Nie |
| Smartsheet |Tak |Nie |Nie |
| Spark (beta) |Tak |Nie |Nie |
| SparkPost (beta) |Tak |Nie |Nie |
| SQL Sentry (beta) |Tak |Nie |Nie |
| Stripe (beta) |Tak |Nie |Nie |
| SweetIQ (beta) |Tak |Nie |Nie |
| Troux (beta) |Tak |Nie |Nie |
| Twilio (beta) |Tak |Nie |Nie |
| tyGraph (beta) |Tak |Nie |Nie |
| Vertica (beta) |Tak |Nie |Nie |
| Visual Studio Team Services (beta) |Tak |Nie |Nie |
| Webtrends (beta) |Tak |Nie |Nie |
| Zendesk (beta) |Tak |Nie |Nie |

> [!IMPORTANT]
> Zabezpieczenia na poziomie wiersza skonfigurowane dla źródła danych powinny działać w przypadku niektórych źródeł danych obsługujących zapytania bezpośrednie (SQL Server, Azure SQL Database, Oracle i Teradata) oraz połączeń na żywo, przy założeniu, że protokół Kerberos jest prawidłowo skonfigurowany w danym środowisku.
> 
> 

## <a name="next-steps"></a>Następne kroki
Teraz, gdy wybrano źródło danych, [utwórz raport](quickstart-create-powerbi-report.md) przy użyciu danych z tego źródła danych.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

