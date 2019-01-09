---
title: Informacje o łączeniu się z przepływami danych w usłudze Power BI
description: Informacje na temat sposobu działania przepływów danych w usłudze Power BI
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 7e26074d0ee8e45740513e17b4c4346cae5dfcf5
ms.sourcegitcommit: 5206651c12f2b91a368f509470b46f3f4c5641e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/02/2019
ms.locfileid: "53984660"
---
# <a name="connect-to-data-sources-for-power-bi-dataflows-preview"></a>Łączenie się ze źródłami danych przepływów danych usługi Power BI (wersja zapoznawcza)

Za pomocą przepływów danych usługi Power BI możesz łączyć się z wieloma różnymi źródłami danych, aby tworzyć nowe przepływy danych lub dodawać nowe jednostki do istniejącego przepływu danych.

W tym artykule wymieniono wiele źródeł danych dostępnych na potrzeby tworzenia przepływów danych lub dodawania do nich elementów oraz opisano sposób tworzenia tych przepływów danych przy użyciu tych źródeł danych.

Omówienie tworzenia i używania przepływów danych zawiera artykuł [Tworzenie i używanie przepływów danych w usłudze Power BI (wersja zapoznawcza)](service-dataflows-create-use.md).

## <a name="create-a-dataflow-from-a-data-source"></a>Tworzenie przepływu danych na podstawie źródła danych

Aby połączyć się z danymi, z poziomu **usługi Power BI** wybierz element menu **+ Utwórz**, a następnie wybierz polecenie **przepływ danych** z wyświetlonego menu. Po dokonaniu wyboru na kanwie usługi Power BI zostanie wyświetlony poniższy obraz. 

![Dodawanie nowego przepływu danych lub jednostki](media/service-dataflows-data-sources/dataflows-data-sources_01.png)

Jeśli Twój przepływ danych już istnieje, możesz do niego dodać nowe jednostki, wybierając pozycję **Dodaj jednostki**, pokazaną poniżej, lub pozycję **Pobierz dane** w narzędziu do tworzenia przepływów danych.

![Dodawanie jednostek do istniejącego przepływu danych](media/service-dataflows-data-sources/dataflows-data-sources_02.png)

Na poniższym obrazie przedstawiono przycisk **Pobierz dane** w narzędziu do tworzenia przepływów danych. 

![Dodawanie jednostek za pomocą przycisku Pobierz dane](media/service-dataflows-data-sources/dataflows-data-sources_03.png)


## <a name="data-sources-for-dataflows"></a>Źródła danych na potrzeby przepływów danych

Dostępne źródła danych możesz wyświetlić, wybierając przycisk **Pobierz dane** w narzędziu do tworzenia przepływów danych. Spowoduje to wyświetlenie okna dialogowego umożliwiającego wybranie kategorii oraz poszczególnych źródeł danych, jak pokazano na poniższym obrazie.


![Kategorie pobierania danych dla przepływów danych](media/service-dataflows-data-sources/dataflows-data-sources_04.png)

Źródła danych na potrzeby przepływów danych są podzielone na następujące kategorie, które są wyświetlane w górnej części okna dialogowego **Pobieranie danych**:

* Wszystkie kategorie
* Plik
* Baza danych
* Power BI
* Azure
* Usługi online
* Inne

Kategoria **Wszystkie kategorie** zawiera wszystkie źródła danych z wszystkich kategorii. 

Kategoria **Plik** obejmuje następujące połączenia danych dostępne dla przepływów danych:

* Dostęp
* Excel
* JSON
* Plik tekstowy lub CSV
* XML

Kategoria **Baza danych** obejmuje następujące połączenia danych dostępne dla przepływów danych:

* Baza danych IBM DB2
* Baza danych MySQL
* Baza danych Oracle
* Baza danych PostgreSQL
* Baza danych programu SQL Server
* Baza danych Sybase
* Baza danych Teradata

Kategoria **Power BI** obejmuje następujące połączenia danych dostępne dla przepływów danych:

* Przepływy danych usługi Power BI

Kategoria **Azure** obejmuje następujące połączenia danych dostępne dla przepływów danych:

* Obiekty blob platformy Azure
* Azure Data Explorer
* Azure SQL Data Warehouse
* Azure SQL Database
* Tabele platformy Azure

Kategoria **Usługi online** obejmuje następujące połączenia danych dostępne dla przepływów danych:

* Common Data Service for Apps
* Microsoft Exchange Online
* Obiekty Salesforce
* Raporty usługi Salesforce
* Lista usługi SharePoint Online
* Smartsheet

Kategoria **Inne** obejmuje następujące połączenia danych dostępne dla przepływów danych:

* Active Directory
* OData
* Listy programu SharePoint
* Internetowy interfejs API
* Strona internetowa
* Pusta tabela
* Puste zapytanie


## <a name="connecting-to-a-data-source"></a>Nawiązywanie połączenia ze źródłem danych

Aby połączyć się ze źródłem danych, wybierz je. Pokażemy działanie procesu na jednym przykładzie, ale proces jest podobny w przypadku każdego połączenia danych dla przepływów danych. Różne łączniki mogą wymagać określonych poświadczeń lub innych informacji, jednak przepływ jest podobny. W ramach naszego przykładu na poniższym obrazie widać, że wybrano opcję **Common Data Service for Apps** z kategorii połączeń danych **Usługi online**.

![Wybieranie opcji Common Data Service for Apps](media/service-dataflows-data-sources/dataflows-data-sources_05.png)

Zostanie wyświetlone okno połączenia dla wybranego połączenia danych. Jeśli wymagane są poświadczenia, zostanie wyświetlony monit o ich podanie. Na poniższym obrazie pokazano wprowadzanie adresu URL serwera w celu nawiązania połączenia z serwerem Common Data Service for Apps.

![Poświadczenia lub adresy URL dla połączeń danych](media/service-dataflows-data-sources/dataflows-data-sources_06.png)

Po podaniu adresu URL serwera lub informacji o połączeniu z zasobem wybierz pozycję **Zaloguj się**, aby wprowadzić poświadczenia na potrzeby dostępu do danych, a następnie wybierz przycisk **Dalej**.

Usługa **Power Query Online** inicjuje i nawiązuje połączenie ze źródłem danych, a następnie wyświetla tabele dostępne w tym źródle danych w oknie **Nawigator** pokazanym na poniższym obrazie.

![Okno Nawigator przedstawia tabele w źródle danych](media/service-dataflows-data-sources/dataflows-data-sources_07.png)

Tabele i dane do załadowania możesz wybrać, zaznaczając odpowiednie pola wyboru w okienku po lewej stronie. Aby załadować dane, wybierz przycisk **OK** w dolnej części okienka **Nawigator**. Zostanie wyświetlone okno dialogowe usługi Power Query Online, w którym możesz edytować zapytania i wykonywać inne niezbędne przekształcenia wybranych danych.

![Edytowanie zapytań i przekształcenia w edytorze Power Query](media/service-dataflows-data-sources/dataflows-data-sources_08.png)

To już wszystko. Inne źródła danych mają podobne przepływy i korzystają z usługi Power Query Online w celu edytowania i przekształcania danych wprowadzanych do przepływu danych.

## <a name="connecting-to-additional-data-sources"></a>Nawiązywanie połączenia z dodatkowymi źródłami danych

Istnieją także inne łączniki danych, które nie są wyświetlane w interfejsie użytkownika przepływów danych usługi Power BI, ale są obsługiwane po wykonaniu kilku dodatkowych kroków. 

Aby utworzyć połączenie z łącznikiem, który nie jest wyświetlany w interfejsie użytkownika, możesz wykonać następujące kroki:

1. Otwórz program **Power BI Desktop** i wybierz pozycję **Pobierz dane**.
2. Otwórz **Edytor Power Query** w programie Power BI Desktop, a następnie kliknij prawym przyciskiem myszy odpowiednie zapytanie i otwórz **Edytor zaawansowany**, jak pokazano na poniższym obrazie. Następnie skopiuj skrypt M wyświetlany w Edytorze zaawansowanym.

    ![Kopiowanie skryptu M z Edytora zaawansowanego w programie Power BI Desktop](media/service-dataflows-data-sources/dataflows-data-sources_09.png) 

3. Otwórz przepływ danych usługi Power BI i wybierz pozycję **Pobierz dane** dla pustego zapytania, jak pokazano na poniższym obrazie.

    ![Tworzenie pustego zapytania dla przepływu danych](media/service-dataflows-data-sources/dataflows-data-sources_10.png) 

4. Wklej skopiowane zapytanie do pustego zapytania dla przepływu danych.

    ![Kopiowanie skryptu M do okna edytora](media/service-dataflows-data-sources/dataflows-data-sources_11.png) 

Następnie skrypt połączy się z określonym źródłem danych. 

Na poniższej liście pokazano łączniki, których obecnie można używać, kopiując zapytanie M i wklejając je do pustego zapytania:

* Amazon Redshift
* SAP Business Warehouse 
* SAP HANA
* Analysis Services
* Azure Analysis Services
* Google Analytics
* Adobe Analytics
* ODBC
* OLE DB
* Folder
* Folder usługi SharePoint Online
* Folder programu SharePoint
* Hadoop (HDFS)
* Azure HDInsight (HDFS)
* Plik usługi Hadoop (HDFS)
* Informix (beta)
* Vertica

To wystarczy, aby nawiązać połączenie ze źródłami danych w przepływach danych usługi Power BI.


## <a name="next-steps"></a>Następne kroki

W tym artykule pokazano źródła danych, z którymi można nawiązywać połączenia na potrzeby przepływów danych. Poniższe artykuły zawierają bardziej szczegółowe informacje na temat typowych scenariuszy użycia przepływów danych. 

* [Przygotowywanie danych samoobsługi w usłudze Power BI (wersja zapoznawcza)](service-dataflows-overview.md)
* [Tworzenie i używanie przepływów danych w usłudze Power BI](service-dataflows-create-use.md)
* [Używanie obliczonych jednostek w usłudze Power BI Premium (wersja zapoznawcza)](service-dataflows-computed-entities-premium.md)
* [Używanie przepływów danych z lokalnymi źródłami danych (wersja zapoznawcza)](service-dataflows-on-premises-gateways.md)
* [Zasoby dla deweloperów dotyczące przepływów danych usługi Power BI (wersja zapoznawcza)](service-dataflows-developer-resources.md)
* [Integracja przepływów danych z usługą Azure Data Lake (wersja zapoznawcza)](service-dataflows-azure-data-lake-integration.md)

Aby uzyskać więcej informacji na temat dodatku Power Query oraz zaplanowanego odświeżania, możesz przeczytać następujące artykuły:
* [Omówienie zapytań w programie Power BI Desktop](desktop-query-overview.md)
* [Konfigurowanie zaplanowanego odświeżania](refresh-scheduled-refresh.md)

Aby uzyskać więcej informacji na temat modelu Common Data Model, można przeczytać artykuł zawierający jego omówienie:
* [Omówienie usługi Common Data Model](https://docs.microsoft.com/powerapps/common-data-model/overview)

