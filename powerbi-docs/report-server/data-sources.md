---
title: Źródła danych raportów usługi Power BI na Serwerze raportów usługi Power BI
description: Raporty usługi Power BI mogą łączyć się z kilkoma źródłami danych. Zależnie od sposobu użycia danych są dostępne różne źródła danych.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: maghan
ms.openlocfilehash: de16c10a03654802e4c65bfa92e60259e2f9510d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54291768"
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Źródła danych raportów usługi Power BI na Serwerze raportów usługi Power BI
Raporty usługi Power BI mogą łączyć się z kilkoma źródłami danych. Zależnie od sposobu użycia danych są dostępne różne źródła danych. Dane można zaimportować lub wykonywać względem nich zapytania bezpośrednio przy użyciu zapytania bezpośredniego lub połączenia na żywo z usługami SQL Server Analysis Services.

Te źródła danych są specyficzne dla raportów Power BI używanych na Serwerze raportów Power BI. Aby uzyskać informacje o źródłach danych obsługiwanych w raportach podzielonych na strony (RDL), zobacz [Źródła danych obsługiwane przez usługi Reporting Services](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Wszystkie źródła danych w raporcie programu Power BI Desktop muszą obsługiwać skonfigurowanie zaplanowanego odświeżania.
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
| Azure HDInsight (HDFS) |Tak |Nie |Nie |
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
| Baza danych usług Azure Analysis Services |Tak |Nie |Tak |
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

## <a name="list-of-supported-authentication-methods-for-model-refresh"></a>Lista obsługiwanych metod uwierzytelniania na potrzeby odświeżania modelu

Serwer raportów usługi Power BI nie obsługuje uwierzytelniania OAuth na potrzeby odświeżania modelu. Niektóre źródła danych, takie jak program Excel lub bazy danych programu Access, korzystają z oddzielnego etapu (pliku lub witryny internetowej) do łączenia się z danymi.

| **Źródło danych** | **Uwierzytelnianie anonimowe** | **Uwierzytelnianie za pomocą klucza** | **Nazwa użytkownika i hasło** | **Uwierzytelnianie systemu Windows** |
| --- | --- | --- | --- | --- |
| Baza danych programu SQL Server |Nie |Nie |Tak |Tak |
| SQL Server Analysis Services |Nie |Nie |Tak |Tak |
| Internet |Tak |Nie |Tak |Tak |
| Azure SQL Database |Nie |Nie |Tak |Nie |
| Azure SQL Data Warehouse |Nie |Nie |Tak |Nie |
| Active Directory |Nie |Nie |Tak |Tak |
| Amazon Redshift |Nie |Nie |Nie |Nie |
| Azure Blob Storage |Tak |Tak |Nie |Nie |
| Azure Data Lake Store |Nie |Nie |Nie |Nie |
| Azure HDInsight (HDFS) |Nie |Nie |Nie |Nie |
| Azure HDInsight (Spark) |Tak |Tak |Nie |Nie |
| Azure Table Storage |Nie |Tak |Nie |Nie |
| Dynamics 365 (online) |Nie |Nie |Nie |Nie |
| Facebook |Nie |Nie |Nie |Nie |
| Folder |Nie |Nie |Nie |Tak |
| Google Analytics |Nie |Nie |Nie |Nie |
| Plik usługi Hadoop (HDFS) |Nie |Nie |Nie |Nie |
| Baza danych IBM DB2 |Nie |Nie |Tak |Tak |
| Impala |Nie |Nie |Nie |Nie |
| Microsoft Exchange |Nie |Nie |Nie |Nie |
| Microsoft Exchange Online |Nie |Nie |Nie |Nie |
| Baza danych MySQL |Nie |Nie |Tak |Tak |
| Źródło danych OData |Tak |Tak |Tak |Tak |
| ODBC |Tak |Nie |Tak |Tak |
| OLE DB |Tak |Nie |Tak |Tak |
| Baza danych Oracle |Nie |Nie |Tak |Tak |
| Baza danych PostgreSQL |Nie |Nie |Tak |Nie |
| Usługa Power BI |Nie |Nie |Nie |Nie |
| Skrypt języka R |Nie |Nie |Nie |Nie |
| Obiekty Salesforce |Nie |Nie |Nie |Nie |
| Raporty usługi Salesforce |Nie |Nie |Nie |Nie |
| SAP Business Warehouse Server |Nie |Nie |Tak |Nie |
| Baza danych SAP HANA |Nie |Nie |Tak |Tak |
| Folder programu SharePoint (lokalny) |Tak |Nie |Nie |Tak |
| Lista programu SharePoint (lokalna) |Tak |Nie |Nie |Tak |
| Lista usługi SharePoint Online |Nie |Nie |Nie |Nie |
| Snowflake |Nie |Nie |Nie |Nie |
| Baza danych Sybase |Nie |Nie |Tak |Tak |
| Baza danych Teradata |Nie |Nie |Tak |Tak |
| appFigures (beta) |Nie |Nie |Nie |Nie |
| Baza danych Azure Analysis Services (beta) |Nie |Nie |Nie |Nie |
| Azure Cosmos DB (beta) |Nie |Nie |Nie |Nie |
| Azure HDInsight Spark (wersja beta) |Nie |Nie |Nie |Nie |
| Common Data Service (beta) |Nie |Nie |Nie |Nie |
| comScore Digital Analytix (beta) |Nie |Nie |Nie |Nie |
| Dynamics 365 for Customer Insights (beta) |Nie |Nie |Nie |Nie |
| Dynamics 365 for Financials (beta) |Nie |Nie |Nie |Nie |
| GitHub (beta) |Nie |Nie |Nie |Nie |
| Google BigQuery (wersja beta) |Nie |Nie |Nie |Nie |
| Baza danych IBM Informix (beta) |Nie |Nie |Nie |Nie |
| IBM Netezza (wersja beta) |Nie |Nie |Nie |Nie |
| Kusto (beta) |Nie |Nie |Nie |Nie |
| MailChimp (beta) |Nie |Nie |Nie |Nie |
| Microsoft Azure Consumption Insights (wersja beta) |Nie |Nie |Nie |Nie |
| Mixpanel (beta) |Nie |Nie |Nie |Nie |
| Planview Enterprise (beta) |Nie |Nie |Nie |Nie |
| Projectplace (beta) |Nie |Nie |Nie |Nie |
| QuickBooks Online (beta) |Nie |Nie |Nie |Nie |
| Smartsheet |Nie |Nie |Nie |Nie |
| Spark (beta) |Nie |Nie |Nie |Nie |
| SparkPost (beta) |Nie |Nie |Nie |Nie |
| SQL Sentry (beta) |Nie |Nie |Nie |Nie |
| Stripe (beta) |Nie |Nie |Nie |Nie |
| SweetIQ (beta) |Nie |Nie |Nie |Nie |
| Troux (beta) |Nie |Nie |Nie |Nie |
| Twilio (beta) |Nie |Nie |Nie |Nie |
| tyGraph (beta) |Nie |Nie |Nie |Nie |
| Vertica (wersja beta) |Nie |Nie |Nie |Nie |
| Visual Studio Team Services (beta) |Nie |Nie |Nie |Nie |
| Webtrends (beta) |Nie |Nie |Nie |Nie |
| Zendesk (beta) |Nie |Nie |Nie |Nie |

## <a name="list-of-supported-authentication-methods-for-directquery"></a>Lista obsługiwanych metod uwierzytelniania dla zapytania bezpośredniego

Serwer raportów usługi Power BI nie obsługuje uwierzytelniania OAuth na potrzeby zapytań bezpośrednich.

| **Źródło danych** | **Uwierzytelnianie anonimowe** | **Uwierzytelnianie za pomocą klucza** | **Nazwa użytkownika i hasło** | **Uwierzytelnianie systemu Windows** | **Zintegrowane uwierzytelnianie systemu Windows** |
| --- | --- | --- | --- | --- | --- |
| Baza danych programu SQL Server |Nie |Nie |Tak |Tak |Tak |
| SQL Server Analysis Services |Nie |Nie |Tak |Tak |Tak |
| Azure SQL Database |Nie |Nie |Tak |Nie |Nie |
| Azure SQL Data Warehouse |Nie |Nie |Tak |Nie |Nie |
| Baza danych Oracle |Nie |Nie |Tak |Tak |Tak |
| SAP Business Warehouse Server |Nie |Nie |Tak |Nie |Tak |
| Baza danych SAP HANA |Nie |Nie |Tak |Tak |Nie |
| Baza danych Teradata |Nie |Nie |Tak |Tak |Tak |


## <a name="next-steps"></a>Następne kroki
Teraz po połączeniu ze źródłem danych [utwórz raport usługi Power BI](quickstart-create-powerbi-report.md) przy użyciu danych z tego źródła danych.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

