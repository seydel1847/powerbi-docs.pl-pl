---
title: Łączenie się z bazą danych Oracle
description: Kroki i pliki do pobrania wymagane do połączenia bazy danych Oracle z programem Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 4/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a56097c02c9f3af63151d0a38e14fdc580e4ee9e
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="connect-to-an-oracle-database"></a>Łączenie się z bazą danych Oracle
Aby można było nawiązać połączenie z bazą danych Oracle przy użyciu programu **Power BI Desktop**, na komputerze z działającym programem Power BI Desktop musi być zainstalowane poprawne oprogramowanie klienckie Oracle. Oprogramowanie klienckie Oracle, którego używasz, zależy od zainstalowanej wersji programu Power BI Desktop — wersji **32-bitowej** lub **64-bitowej**.

**Obsługiwane wersje**: program Oracle 9 lub nowszy, oprogramowanie klienckie Oracle 8.1.7 lub nowsze.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Określanie, jaka wersja programu Power BI Desktop jest zainstalowana
Aby określić, która wersja programu Power BI Desktop jest zainstalowana, wybierz kolejno pozycje **Plik > Pomoc > Informacje**, a następnie sprawdź wiersz **Wersja:**. Na poniższym obrazie widać, że jest zainstalowana wersja 64-bitowa programu Power BI Desktop:

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Instalowanie klienta Oracle
W przypadku **32-bitowych** wersji programu Power BI Desktop użyj następującego linku, aby pobrać i zainstalować **32-bitową** wersję klienta Oracle:

* [32-bitowa wersja programu Oracle Data Access Components (ODAC) z programem Oracle Developer Tools dla programu Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

W przypadku **64-bitowych** wersji programu Power BI Desktop użyj następującego linku, aby pobrać i zainstalować **64-bitową** wersję klienta Oracle:

* [64-bitowa wersja programu ODAC 12c w wersji 4 (12.1.0.2.4) dla systemu Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Łączenie się z bazą danych Oracle
Po zainstalowaniu odpowiedniego sterownika klienta Oracle możesz połączyć się z bazą danych Oracle. Aby nawiązać połączenie, wykonaj następujące kroki:

1. W oknie Pobieranie danych wybierz pozycję **Baza danych > Baza danych programu Oracle**
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. W wyświetlonym oknie dialogowym **Baza danych Oracle** podaj nazwę serwera, a następnie wybierz pozycję **Połącz**. Jeśli wymagany jest identyfikator SID, możesz go określić przy użyciu formatu: *nazwa_serwera/SID*, gdzie SID to unikatowa nazwa bazy danych. Jeśli format *nazwa_serwera/SID* nie działa, spróbuj użyć formatu *nazwa_serwera/nazwa_usługi*, gdzie nazwa_usługi to alias użyty podczas nawiązywania połączenia.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. Jeśli chcesz zaimportować dane przy użyciu natywnego zapytania bazy danych, możesz umieścić zapytanie w polu **Instrukcja SQL** dostępnym po rozwinięciu sekcji **Opcje zaawansowane** okna dialogowego **Baza danych Oracle**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Po wprowadzeniu informacji o bazie danych programu Oracle do okna dialogowego Baza danych Oracle (w tym opcjonalnych informacji takich jak identyfikator SID lub natywne zapytanie bazy danych) wybierz pozycję **OK**, aby się połączyć.
5. Jeśli baza danych programu Oracle wymaga poświadczeń użytkownika bazy danych, wprowadź te poświadczenia w oknie dialogowym po wyświetleniu monitu.

