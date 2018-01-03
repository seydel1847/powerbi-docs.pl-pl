---
title: "Pakiet zawartości Inspekcja bazy danych SQL"
description: "Pakiet zawartości Inspekcja bazy danych SQL dla usługi Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
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
ms.date: 08/10/2017
ms.author: yshoukry
ms.openlocfilehash: 096b48f69529ae17bdc37be5484e90f47a769264
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="sql-database-auditing-content-pack-for-power-bi"></a>Pakiet zawartości Inspekcja bazy danych SQL dla usługi Power BI
Pakiet zawartości usługi Power BI dla platformy Azure [Inspekcja bazy danych SQL](http://azure.microsoft.com/documentation/articles/sql-database-auditing-get-started/) umożliwia zrozumienie aktywności bazy danych oraz uzyskanie informacji dotyczących rozbieżności i anomalii, które mogą wskazywać na problemy biznesowe lub potencjalne naruszenia zabezpieczeń. 

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
5. Jako metodę uwierzytelniania wybierz **Klucz**, wprowadź swój ** Klucz konta** i \> **Zaloguj się**.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqlauditing3.png)
6. Po zaimportowaniu danych przez usługę Power BI zobaczysz nowy pulpit nawigacyjny, raport i zestaw danych w okienku nawigacji po lewej stronie. Nowe elementy są oznaczone żółtą gwiazdką \*.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqldbauditingnewdash.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu Pytania i odpowiedzi](service-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="next-steps"></a>Następne kroki
[Pobieranie danych dla usługi Power BI](service-get-data.md)
[Wprowadzenie do usługi Power BI](service-get-started.md)