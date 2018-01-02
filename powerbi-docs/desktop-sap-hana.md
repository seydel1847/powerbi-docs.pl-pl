---
title: "Używanie platformy SAP HANA w programie Power BI Desktop"
description: "Używanie platformy SAP HANA w programie Power BI Desktop"
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 9cbeb0b2504612a9eb32fdad1d95fd90b57e07d9
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2017
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>Używanie platformy SAP HANA w programie Power BI Desktop
Teraz program Power BI Desktop umożliwia uzyskiwanie dostępu do baz danych platformy **SAP HANA**. Aby używać platformy **SAP HANA**, na lokalnym komputerze klienckim musi być zainstalowany sterownik ODBC platformy SAP HANA w celu zapewnienia prawidłowego działania połączenia danych platformy **SAP HANA** z programem Power BI Desktop. Sterownik ODBC platformy SAP HANA możesz pobrać z witryny [SAP Software Download Center (Centrum pobierania oprogramowania SAP)](https://support.sap.com/swdc). W tej witrynie wyszukaj klienta SAP HANA dla komputerów z systemem Windows. Ponieważ struktura witryny **SAP Software Download Center** (Centrum pobierania oprogramowania SAP) jest często zmieniana, dokładniejsze wskazówki dotyczące nawigowania w tej witrynie są niedostępne.

Aby nawiązać połączenie z bazą danych **SAP HANA**, wybierz pozycję **Pobierz dane > Baza danych > Baza danych SAP HANA**, jak pokazano na poniższym obrazie.

![](media/desktop-sap-hana/sap-hana-1.png)

Podczas nawiązywania połączenia z bazą danych SAP HANA podaj nazwę serwera i numer portu w formacie *serwer:port* — na poniższej ilustracji przedstawiono przykład z serwerem o nazwie *ServerXYZ* i numerem portu *30015*.

![](media/desktop-sap-hana/sap-hana-2.png)

W tej wersji platforma **SAP HANA** w trybie [zapytania bezpośredniego](desktop-use-directquery.md) jest obsługiwana w programie Power BI Desktop i usłudze Power BI. Możesz publikować i przekazywać raporty, które używają platformy **SAP HANA**, w trybie zapytania bezpośredniego do usługi Power BI. Możesz również publikować i przesyłać raporty do usługi Power BI, gdy nie korzystasz z platformy **SAP HANA** w trybie zapytania bezpośredniego.

### <a name="supported-features-for-sap-hana"></a>Obsługiwane funkcje platformy SAP HANA
Ta wersja zawiera wiele funkcji do obsługi platformy **SAP HANA** wymienionych na poniższej liście:

* Łącznik usługi Power BI dla platformy **SAP HANA** używa sterownika SAP ODBC w celu zapewniania najlepszego środowiska użytkownika
* Platforma **SAP HANA** obsługuje zarówno opcje zapytania bezpośredniego, jak i importowania
* Usługa Power BI obsługuje modele informacji platformy HANA (takie jak widoki analityczne i obliczeniowe) i ma zoptymalizowaną nawigację
* Wraz z platformą **SAP HANA** można także używać funkcji bezpośredniego kodu SQL do nawiązywania połączenia z tabelami wierszy i kolumn
* Obejmuje zoptymalizowaną nawigację dla modeli HANA
* Usługa Power BI obsługuje zmienne i parametry wejściowe platformy **SAP HANA**

### <a name="installing-the-sap-hana-odbc-driver"></a>Instalowanie sterownika ODBC platformy SAP HANA
### <a name="limitations-of-sap-hana"></a>Ograniczenia dotyczące platformy SAP HANA
Istnieje również kilka ograniczeń dotyczących używania platformy **SAP HANA** wymienionych poniżej:

* Ciągi NVARCHAR są obcinane do maksymalnej długości wynoszącej 4000 znaków Unicode
* Typ danych SMALLDECIMAL nie jest obsługiwany
* Typ danych VARBINARY nie jest obsługiwany
* Prawidłowe daty są z zakresu od 1899-12-30 do 9999-12-31

