---
title: "Źródła danych w programie Power BI Desktop"
description: "Źródła danych w programie Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 04/29/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: ff28f5d43b065ae798e2e9f275c8e8b59e9ee1ce
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2018
---
# <a name="data-sources-in-power-bi-desktop"></a>Źródła danych w programie Power BI Desktop
Korzystając z programu Power BI Desktop, możesz nawiązywać połączenie z danymi z wielu różnych źródeł. Pełna lista dostępnych źródeł danych znajduje się w dolnej części tej strony.

Aby nawiązać połączenie z danymi, wybierz pozycję **Pobierz dane** z karty **Narzędzia główne** wstążki. Jeśli wybierzesz strzałkę w dół obok przycisku lub znajdujący się na nim tekst **Pobierz dane**, zostanie wyświetlone menu przedstawiające **Najpopularniejsze** typy danych. Widać je na poniższej ilustracji.

![](media/desktop-data-sources/data-sources_1.png)

Po wybraniu pozycji **Więcej...** z menu **Najpopularniejsze** zostanie wyświetlone okno **Pobieranie danych**. Okno **Pobieranie danych** można również wywołać (z pominięciem menu **Najpopularniejsze**), bezpośrednio wybierając **przycisk ikony** **Pobierz dane**.

![](media/desktop-data-sources/data-sources_2.png)

> [!NOTE]
> Zespół usługi Power BI nieustannie rozszerza źródła danych dostępne w programie **Power BI Desktop** i **usłudze Power BI**. Z tego powodu często będzie można zauważyć wczesne wersje eksperymentalnych źródeł danych oznaczone jako *beta* lub *wersja zapoznawcza*. Wszystkie źródła danych oznaczone jako *beta* lub *wersja zapoznawcza* mają ograniczone wsparcie i funkcjonalność, dlatego nie powinny być używane w środowiskach produkcyjnych.
> 
> 

## <a name="data-sources"></a>Źródła danych
Typy danych sklasyfikowano w następujące kategorie:

* Wszystkie
* Plik
* Baza danych
* Azure
* Usługi online
* Inne

Kategoria **Wszystkie** obejmuje wszystkie typy połączeń danych ze wszystkich kategorii.

Kategoria **Plik** udostępnia następujące połączenia danych:

* Excel
* Plik tekstowy lub CSV
* XML
* JSON
* Folder
* Folder programu SharePoint

Na poniższej ilustracji przedstawiono okno **Pobieranie danych** dla kategorii **Plik**.

![](media/desktop-data-sources/data-sources_3.png)

> [!NOTE]
> W poprzednich wersjach programu Power BI Desktop kategorie **CSV** i **Tekst** były oddzielnymi typami połączeń. Te łączniki danych zostały połączone w kategorię **Plik tekstowy lub CSV**.
> 
> 

Kategoria **Baza danych** udostępnia następujące połączenia danych:

* Baza danych programu SQL Server
* Baza danych programu Access
* Baza danych usług SQL Server Analysis Services
* Oracle Database
* Baza danych IBM DB2
* Baza danych IBM Informix (beta)
* IBM Netezza
* Baza danych MySQL
* Baza danych PostgreSQL
* Baza danych Sybase
* Teradata Database
* Baza danych SAP HANA
* SAP Business Warehouse Application Server
* SAP Business Warehouse Message Server (wersja beta)
* Amazon Redshift
* Impala
* Google BigQuery (wersja beta)
* Snowflake

> [!NOTE]
> Niektóre łączniki baz danych wymagają włączenia przez wybranie pozycji **Plik > Opcje i ustawienia > Opcje**, a następnie wybranie opcji **Funkcje wersji zapoznawczej** i włączenie łącznika. Jeśli chcesz użyć niektórych łączników wymienionych powyżej, ale ich nie widzisz, sprawdź ustawienie **Funkcje wersji zapoznawczej**. Pamiętaj jednak, że wszystkie źródła danych oznaczone jako *beta* lub *wersja zapoznawcza* mają ograniczone wsparcie i funkcjonalność, dlatego nie powinny być używane w środowiskach produkcyjnych.
> 
> 

Na poniższej ilustracji przedstawiono okno **Pobieranie danych** dla kategorii **Baza danych**.

![](media/desktop-data-sources/data-sources_4.png)

Kategoria **Azure** udostępnia następujące połączenia danych:

* Azure SQL Database
* Azure SQL Data Warehouse
* Baza danych usług Azure Analysis Services
* Azure Blob Storage
* Azure Table Storage
* Azure Cosmos DB (beta)
* Azure Data Lake Store
* Azure HDInsight (HDFS)
* Azure HDInsight Spark (wersja beta)
* Interaktywne zapytanie usługi HDInsight (beta)

Na poniższej ilustracji przedstawiono okno **Pobieranie danych** dla kategorii **Azure**.

![](media/desktop-data-sources/data-sources_5.png)

Kategoria **Usługi online** udostępnia następujące połączenia danych:

* Usługa Power BI
* Lista usługi SharePoint Online
* Microsoft Exchange Online
* Dynamics 365 (online)
* Dynamics NAV (beta)
* Dynamics 365 for Financials (beta)
* Common Data Service (beta)
* Microsoft Azure Consumption Insights (beta)
* Visual Studio Team Services (beta)
* Obiekty Salesforce
* Raporty Salesforce
* Google Analytics
* Adobe Analytics
* appFigures (beta)
* comScore Digital Analytix (beta)
* Dynamics 365 for Customer Insights (beta)
* Data.World — pobierz zestaw danych (beta)
* Facebook
* GitHub (beta)
* MailChimp (beta)
* Marketo (beta)
* Mixpanel (beta)
* Planview Enterprise One — PRM (beta)
* Planview Projectplace (beta)
* QuickBooks Online (beta)
* Smartsheet
* SparkPost (beta)
* Stripe (beta)
* SweetIQ (beta)
* Planview Enterprise One — CMT (beta)
* Twilio (beta)
* tyGraph (beta)
* Webtrends (beta)
* Zendesk (beta)

Na poniższej ilustracji przedstawiono okno **Pobieranie danych** dla kategorii **Usługi online**.

![](media/desktop-data-sources/data-sources_6b.png)

Kategoria **Inne** udostępnia następujące połączenia danych:

* Vertica (wersja beta)
* Kusto (beta)
* Internet
* Listy programu SharePoint
* Źródło danych OData
* Active Directory
* Microsoft Exchange
* Plik usługi Hadoop (HDFS)
* Spark (beta)
* Skrypt języka R
* ODBC
* OLE DB
* Puste zapytanie

Na poniższej ilustracji przedstawiono okno **Pobieranie danych** dla kategorii **Inne**.

![](media/desktop-data-sources/data-sources_7a.png)

> [!NOTE]
> Aktualnie nie jest możliwe nawiązanie połączenia z niestandardowymi źródłami danych zabezpieczonymi przy użyciu usługi Azure Active Directory.
> 
> 

## <a name="connecting-to-a-data-source"></a>Nawiązywanie połączenia ze źródłem danych
Aby nawiązać połączenie ze źródłem danych, wybierz źródło danych w oknie **Pobieranie danych** i wybierz przycisk **Połącz**. Na poniższej ilustracji zaznaczono pozycję **Internet** z kategorii **Inne** połączeń danych.

![](media/desktop-data-sources/data-sources_7b.png)

Zostanie wyświetlone okno połączenia specyficzne dla typu połączenia danych. Jeśli wymagane są poświadczenia, zostanie wyświetlony monit o ich podanie. Na poniższej ilustracji przedstawiono adres URL wprowadzany w celu nawiązania połączenia ze źródłem danych Internet.

![](media/desktop-data-sources/datasources_fromwebbox.png)

Po wprowadzeniu adresu URL lub informacji o połączeniu z zasobem wybierz przycisk **OK**. Program Power BI Desktop nawiązuje połączenie ze źródłem danych i prezentuje dostępne źródła danych w okienku **Nawigator**.

![](media/desktop-data-sources/datasources_fromnavigatordialog.png)

Możesz załadować dane, wybierając przycisk **Załaduj** w dolnej części okienka **Nawigator**, lub zmodyfikować zapytanie przed załadowaniem danych, wybierając przycisk **Edytuj**.

To wystarczy, aby nawiązać połączenie ze źródłami danych w programie Power BI Desktop. Spróbuj nawiązać połączenie z danymi, korzystając z naszej ciągle uzupełnianej listy źródeł danych. Sprawdzaj często tę listę, ponieważ stale dodajemy do niej nowe pozycje.

## <a name="next-steps"></a>Następne kroki
Przy użyciu programu Power BI Desktop można wykonywać różnorodne zadania. Aby uzyskać więcej informacji na temat jego możliwości, skorzystaj z następujących zasobów:

* [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md)
* [Omówienie zapytań w programie Power BI Desktop](desktop-query-overview.md)
* [Typy danych w programie Power BI Desktop](desktop-data-types.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)
* [Typowe zadania dotyczące zapytań w programie Power BI Desktop](desktop-common-query-tasks.md)    
