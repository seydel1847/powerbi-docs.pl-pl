---
title: Pakiet zawartości Inspekcja bazy danych SQL
description: Pakiet zawartości Inspekcja bazy danych SQL dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 11/09/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 0d212510fd2856fd509077f35e0f10bb7c5dd4c5
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008756"
---
# <a name="sql-database-auditing-content-pack-for-power-bi"></a>Pakiet zawartości Inspekcja bazy danych SQL dla usługi Power BI

> [!IMPORTANT]
> Pakiet zawartości Inspekcja bazy danych SQL jest przestarzały i jest już niedostępny.
 
Pakiet zawartości usługi Power BI dla platformy Azure [Inspekcja bazy danych SQL](/azure/sql-database/sql-database-auditing/) umożliwia zrozumienie aktywności bazy danych oraz uzyskanie informacji dotyczących rozbieżności i anomalii, które mogą wskazywać na problemy biznesowe lub potencjalne naruszenia zabezpieczeń. 

Nawiąż połączenie z [pakietem zawartości Inspekcja bazy danych SQL](https://app.powerbi.com/getdata/services/sql-db-auditing) dla usługi Power BI.

>[!NOTE]
>Pakiet zawartości importuje dane ze wszystkich tabel, które zawierają frazę „AuditLogs” w swojej nazwie, a następnie dołącza je do jednej tabeli modelu danych o nazwie „AuditLogs”. Ostatnie 250 000 zdarzeń zostanie dołączonych, a dane będą odświeżane codziennie.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getdata.png) 
2. W polu Usługi wybierz polecenie Pobierz.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getservices.png) 
3. Wybierz pozycję **Inspekcja bazy danych SQL** \> **Pobierz**.
   
   ![](media/service-connect-to-azure-sql-database-auditing/sqldbaudit.png)
4. W oknie nawiązywania połączenia z inspekcją bazy danych SQL:
   
   - Wprowadź nazwę konta usługi Azure Table Storage lub adres URL do miejsca, w którym przechowywane są dzienniki.
   
   - Wprowadź nazwę odpowiedniego serwera SQL. Wprowadź „\*”, aby załadować dzienniki inspekcji dla wszystkich serwerów.
   
   - Wprowadź nazwę odpowiedniej bazy danych SQL. Wprowadź „\*”, aby załadować dzienniki inspekcji dla wszystkich baz danych.
   
   - Wprowadź nazwę tabeli platformy Azure, która zawiera odpowiednie dzienniki. Wprowadź „\*”, aby załadować dzienniki inspekcji ze wszystkich tabel zawierających frazę „AuditLogs” w nazwie.
   
   >[!IMPORTANT]
   >Ze względu na wydajność zaleca się, aby zawsze określać jawną nazwę tabeli, nawet jeśli wszystkie dzienniki inspekcji są przechowywane w jednej tabeli.
   
   - Wprowadź datę rozpoczęcia dla odpowiednich dzienników inspekcji. Wprowadź „\*”, aby załadować dzienniki inspekcji bez dolnego limitu czasu lub „1d”, aby załadować dzienniki inspekcji z ostatniego dnia.
   
   - Wprowadź datę zakończenia dla odpowiednich dzienników inspekcji. Wprowadź „\*”, aby załadować dzienniki inspekcji bez górnego limitu czasu.
   
   ![](media/service-connect-to-azure-sql-database-auditing/dbauditing_param.png)
5. Jako metodę uwierzytelniania wybierz **Klucz**, wprowadź swój **Klucz konta** \> **Zaloguj się**.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqlauditing3.png)
6. Po zaimportowaniu danych przez usługę Power BI zobaczysz nowy pulpit nawigacyjny, raport i zestaw danych w okienku nawigacji po lewej stronie. Nowe elementy są oznaczone żółtą gwiazdką \*.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqldbauditingnewdash.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="next-steps"></a>Następne kroki
[Pobieranie danych dla usługi Power BI](service-get-data.md)
[Co to jest usługa Power BI?](power-bi-overview.md)
