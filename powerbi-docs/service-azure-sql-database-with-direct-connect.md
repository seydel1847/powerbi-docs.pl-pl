---
title: "Usługa Azure SQL Database i zapytanie bezpośrednie"
description: "Usługa Azure SQL Database i zapytanie bezpośrednie"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.author: asaxton
ms.openlocfilehash: 83613f0ed915a03b65b90d4bf61e37568b922182
ms.sourcegitcommit: c2deaff54434da67698a14cc00172a2119ed1a56
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2017
---
# <a name="azure-sql-database-with-directquery"></a>Usługa Azure SQL Database i zapytanie bezpośrednie
Dowiedz się, jak łączyć się bezpośrednio z usługą Azure SQL Database i tworzyć raporty wykorzystujące dane w czasie rzeczywistym. Dane mogą być przechowywane w lokalizacji źródłowej, a nie w usłudze Power BI.

Dzięki zapytaniu bezpośredniemu zapytania są wysyłane do usługi Azure SQL Database w czasie, gdy eksplorujesz dane w widoku raportu. To środowisko jest zalecane użytkownikom zaznajomionym z bazami danych i jednostkami, z którymi one się łączą.

**Uwagi:**

* Określ w pełni kwalifikowaną nazwę serwera podczas łączenia (szczegóły poniżej)
* Upewnij się, że reguły zapory dla bazy danych mają ustawioną opcję „[Zezwalaj na dostęp do usług platformy Azure](https://msdn.microsoft.com/library/azure/ee621782.aspx)”.
* Wszystkie akcje, takie jak wybór kolumny lub dodawanie filtru, spowodują wysłanie zapytania zwrotnego do bazy danych
* Kafelki są odświeżane co około 15 minut (nie trzeba określać harmonogramu odświeżania). Można dostosować tę opcję w Ustawieniach zaawansowanych podczas łączenia.
* Funkcja Pytania i odpowiedzi nie jest dostępna dla zestawów danych zapytania bezpośredniego
* Zmiany schematu nie są pobierane automatycznie

Te ograniczenia i uwagi mogą ulegać zmianom, gdy będziemy kontynuować proces ulepszania środowisk. Etapy nawiązywania połączenia są szczegółowo opisane poniżej. 

## <a name="power-bi-desktop-and-directquery"></a>Program Power BI Desktop i zapytania bezpośrednie
W celu nawiązania połączenia z usługą Azure SQL Database za pomocą zapytania bezpośredniego należy użyć programu Power BI Desktop. Metoda ta zapewnia dodatkową elastyczność i możliwości. Raporty utworzone za pomocą programu Power BI Desktop mogą być następnie publikowane w usłudze Power BI. Dowiedz się więcej na temat nawiązywania połączenia z [usługą Azure SQL Database za pomocą zapytania bezpośredniego](desktop-use-directquery.md) w programie Power BI Desktop. 

## <a name="connecting-through-power-bi"></a>Łączenie się za pośrednictwem usługi Power BI
Nawiązywanie połączenia z usługą Azure SQL Database bezpośrednio z usługi Power BI nie jest już możliwe. Po wybraniu [łącznika usługi Azure SQL Database](https://app.powerbi.com/getdata/bigdata/azure-sql-database-with-live-connect) zostanie wyświetlona prośba o nawiązanie połączenia w programie Power BI Desktop. Pozwoli to na publikowanie raportów programu Power BI Desktop w usłudze Power BI. 

![](media/service-azure-sql-database-with-direct-connect/azure-sql-database-in-power-bi.png)

### <a name="finding-parameter-values"></a>Znajdowanie wartości parametrów
W pełni kwalifikowaną nazwę serwera i nazwę bazy danych można znaleźć w witrynie Azure Portal.

![](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>Następne kroki
[Używanie zapytania bezpośredniego w programie Power BI Desktop](desktop-use-directquery.md)  
[Wprowadzenie do usługi Power BI](service-get-started.md)  
[Pobieranie danych dla usługi Power BI](service-get-data.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

