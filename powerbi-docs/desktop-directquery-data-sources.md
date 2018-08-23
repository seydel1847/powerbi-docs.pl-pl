---
title: Źródła danych obsługiwane przez zapytanie bezpośrednie w usłudze Power BI
description: Zobacz listę źródeł danych, które mogą korzystać z zapytania bezpośredniego.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/10/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: d37ed22c0abba4e843d37fd6df465f9a755fbdc6
ms.sourcegitcommit: 126e5eca8bfab6273581dabd7603df88be755240
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2018
ms.locfileid: "40257091"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Źródła danych obsługiwane przez zapytanie bezpośrednie w usłudze Power BI
Program **Power BI Desktop** i **usługa Power BI** mają wiele źródeł danych, z którymi można się łączyć, aby uzyskać dostęp do danych. W tym artykule opisano, jakie źródła danych usługi Power BI obsługują metodę połączenia nazywaną **zapytaniem bezpośrednim**. Aby uzyskać więcej informacji na temat zapytania bezpośredniego, zobacz [**Zapytanie bezpośrednie w usłudze Power BI**](desktop-directquery-about.md).

Następujące źródła danych obsługują zapytanie bezpośrednie w usłudze Power BI:

* Amazon Redshift
* Azure Databricks
* Azure HDInsight Spark (wersja beta)
* Azure SQL Database
* Azure SQL Data Warehouse
* Google BigQuery (wersja beta)
* IBM Netezza (wersja beta)
* Impala (wersja 2.x)
* Oracle Database (wersja 12 i nowsze)
* SAP Business Warehouse Application Server
* SAP Business Warehouse Message Server (wersja beta)
* SAP HANA
* Snowflake
* Spark (wersja beta) (wersja 0.9 i nowsze)
* SQL Server
* Teradata Database
* Vertica (wersja beta)

Źródła danych, których nazwy zawierają ciąg **(wersja beta)** lub **(wersja zapoznawcza)**, mogą ulec zmianie i nie powinny być używane w środowiskach produkcyjnych. Mogą one również nie być obsługiwane po opublikowaniu raportu w **usłudze Power BI**, co oznacza, że otwarcie opublikowanego raportu lub eksploracja zestawu danych mogą spowodować wystąpienie błędu.

Jedyna różnica między źródłami danych typu **(wersja beta)** i **(wersja zapoznawcza)** polega na tym, że źródła **(wersja zapoznawcza)** należy włączyć jako funkcję w wersji zapoznawczej, zanim będą dostępne do użycia. Aby włączyć łącznik danych **(Wersja zapoznawcza)**, w programie **Power BI Desktop** wybierz pozycję **Plik > Opcje i ustawienia > Opcje**, a następnie wybierz pozycję **Funkcje w wersji zapoznawczej**.

> [!NOTE]
> Zapytania DirectQuery względem programu SQL Server wymagają uwierzytelniania przy użyciu bieżących poświadczeń uwierzytelniania systemu Windows lub poświadczeń bazy danych w celu ustanowienia dostępu. Alternatywne poświadczenia nie są obsługiwane.
>

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
| Snowflake |Tak |
| Spark (wersja beta), wersja 0.9 i nowsze |Jeszcze nie jest obsługiwana w **usłudze Power BI** |
| Azure HDInsight Spark (wersja beta) |Nie |
| IBM Netezza |Tak |
| SAP Buisness Warehouse Application Server |Tak |
| SAP Buisness Warehouse Message Server |Jeszcze nie jest obsługiwana w **usłudze Power BI** |
| Google BigQuery |Nie |


## <a name="next-steps"></a>Następne kroki
Aby uzyskać więcej informacji na temat zapytania bezpośredniego, zapoznaj się z następującymi zasobami:

* [Zapytanie bezpośrednie w usłudze Power BI](desktop-directquery-about.md)
* [Zapytanie bezpośrednie i platforma SAP HANA](desktop-directquery-sap-hana.md)
* [Zapytanie bezpośrednie i system SAP BW](desktop-directquery-sap-bw.md)
* [Lokalna brama danych](service-gateway-onprem.md)

