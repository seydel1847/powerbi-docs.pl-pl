---
title: "Łączenie się z bazą danych Oracle"
description: "Kroki i pliki do pobrania wymagane do połączenia bazy danych Oracle z programem Power BI Desktop"
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
ms.openlocfilehash: 462f4eb939ce34368afe9f4a247166a55b554e24
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2017
---
# <a name="connect-to-an-oracle-database"></a>Łączenie się z bazą danych Oracle
Aby można było nawiązać połączenie z bazą danych Oracle przy użyciu programu **Power BI Desktop**, na komputerze z działającym programem Power BI Desktop musi być zainstalowane poprawne oprogramowanie klienckie Oracle. Oprogramowanie klienckie Oracle, którego używasz, zależy od zainstalowanej wersji programu Power BI Desktop — wersji **32-bitowej** lub **64-bitowej**.

**Obsługiwane wersje**: program Oracle 9 lub nowszy, oprogramowanie klienckie Oracle 8.1.7 lub nowsze.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Określanie, jaka wersja programu Power BI Desktop jest zainstalowana
Aby określić, która wersja programu Power BI Desktop jest zainstalowana, wybierz kolejno pozycje **Plik > Informacje**, a następnie sprawdź wiersz **Wersja:**. Na poniższym obrazie widać, że jest zainstalowana wersja 64-bitowa programu Power BI Desktop:

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Instalowanie klienta Oracle
W przypadku **32-bitowych** wersji programu Power BI Desktop użyj następującego linku, aby pobrać i zainstalować **32-bitową** wersję klienta Oracle:

* [32-bitowa wersja programu Oracle Data Access Components (ODAC) z programem Oracle Developer Tools dla programu Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

W przypadku **64-bitowych** wersji programu Power BI Desktop użyj następującego linku, aby pobrać i zainstalować **64-bitową** wersję klienta Oracle:

* [64-bitowa wersja programu ODAC 12c w wersji 4 (12.1.0.2.4) dla systemu Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Łączenie się z bazą danych Oracle
Po zainstalowaniu odpowiedniego sterownika klienta Oracle możesz połączyć się z bazą danych Oracle. Wykonaj następujące kroki, aby nawiązać połączenie.

1. W oknie Pobieranie danych wybierz pozycję **Baza danych > Baza danych programu Oracle**
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. W wyświetlonym oknie dialogowym **Baza danych Oracle** podaj nazwę serwera, a następnie wybierz pozycję **Połącz**. Jeśli wymagany jest identyfikator SID, możesz go określić przy użyciu formatu: *NazwaSerwera/SID*.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. Jeśli chcesz zaimportować dane przy użyciu natywnego zapytania bazy danych, możesz umieścić zapytanie w polu **Instrukcja SQL** dostępnym po rozwinięciu sekcji **Opcje zaawansowane** okna dialogowego **Baza danych Oracle**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Po wprowadzeniu informacji o bazie danych programu Oracle do okna dialogowego Baza danych Oracle (w tym opcjonalnych informacji takich jak identyfikator SID lub natywne zapytanie bazy danych) wybierz pozycję **OK**, aby się połączyć.
5. Jeśli baza danych programu Oracle wymaga poświadczeń użytkownika bazy danych, wprowadź te poświadczenia w oknie dialogowym po wyświetleniu monitu.
