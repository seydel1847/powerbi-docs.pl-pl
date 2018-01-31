---
title: "Źródła danych obsługiwane przez zapytanie bezpośrednie w usłudze Power BI"
description: "Zobacz listę źródeł danych, które mogą korzystać z zapytania bezpośredniego."
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 6e93a6d216603ee247979c586481115ba3f67d77
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Źródła danych obsługiwane przez zapytanie bezpośrednie w usłudze Power BI
Program **Power BI Desktop** i **usługa Power BI** mają wiele źródeł danych, z którymi można się łączyć, aby uzyskać dostęp do danych. W tym artykule opisano, jakie źródła danych usługi Power BI obsługują metodę połączenia nazywaną **zapytaniem bezpośrednim**. Aby uzyskać więcej informacji na temat zapytania bezpośredniego, zobacz [**Zapytanie bezpośrednie w usłudze Power BI**](desktop-directquery-about.md).

Następujące źródła danych obsługują zapytanie bezpośrednie w usłudze Power BI:

* Amazon Redshift
* Azure HDInsight Spark (wersja beta)
* Azure SQL Database
* Azure SQL Data Warehouse
* Google BigQuery (wersja beta)
* IBM Netezza (wersja beta)
* Impala (wersja 2.x)
* Oracle Database (wersja 12 i nowsze)
* SAP Business Warehouse (wersja beta)
* SAP HANA
* Snowflake
* Spark (wersja beta) (wersja 0.9 i nowsze)
* SQL Server
* Teradata Database
* Vertica (wersja beta)

Źródła danych, których nazwy zawierają ciąg **(wersja beta)** lub **(wersja zapoznawcza)**, mogą ulec zmianie i nie powinny być używane w środowiskach produkcyjnych. Mogą one również nie być obsługiwane po opublikowaniu raportu w **usłudze Power BI**, co oznacza, że otwarcie opublikowanego raportu lub eksploracja zestawu danych mogą spowodować wystąpienie błędu.

Jedyna różnica między źródłami danych typu **(wersja beta)** i **(wersja zapoznawcza)** polega na tym, że źródła **(wersja zapoznawcza)** należy włączyć jako funkcję w wersji zapoznawczej, zanim będą dostępne do użycia. Aby włączyć łącznik danych **(wersja zapoznawcza)**, w programie **Power BI Desktop** wybierz pozycję **Plik > Opcje i ustawienia**, a następnie **Ustawienia > Opcje > Funkcje w wersji zapoznawczej**.

## <a name="on-premises-gateway-requirements"></a>Wymagania bramy lokalnej
W poniższej tabeli określono, czy **lokalna brama danych** jest wymagana do łączenia się z określonym źródłem danych po opublikowaniu raportu w **usłudze Power BI**.

| Źródło | Czy brama jest wymagana? |
| --- | --- |
| SQL Server |Tak |
| Azure SQL Database |Nie |
| Azure SQL Data Warehouse |Nie |
| SAP HANA |Tak |
| Oracle Database |Tak |
| Teradata Database |Tak |
| Amazon Redshift |Nie |
| Impala (wersja 2.x) |Tak |
| Snowflake (wersja zapoznawcza) |Jeszcze nie jest obsługiwana w **usłudze Power BI** |
| Spark (wersja beta), wersja 0.9 i nowsze |Jeszcze nie jest obsługiwana w **usłudze Power BI** |
| Azure HDInsight Spark (wersja beta) |Jeszcze nie jest obsługiwana w **usłudze Power BI** |
| IBM Netezza (wersja beta) |Jeszcze nie jest obsługiwana w **usłudze Power BI** |
| SAP Buisness Warehouse (wersja beta) |Jeszcze nie jest obsługiwana w **usłudze Power BI** |

## <a name="next-steps"></a>Następne kroki
Aby uzyskać więcej informacji na temat zapytania bezpośredniego, zapoznaj się z następującymi zasobami:

* [Zapytanie bezpośrednie w usłudze Power BI](desktop-directquery-about.md)
* [Zapytanie bezpośrednie i platforma SAP HANA](desktop-directquery-sap-hana.md)
* [Zapytanie bezpośrednie i system SAP BW](desktop-directquery-sap-bw.md)
* [Lokalna brama danych](service-gateway-onprem.md)

