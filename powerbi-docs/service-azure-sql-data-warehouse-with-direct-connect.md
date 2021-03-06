---
title: Usługa Azure SQL Data Warehouse z zapytaniem bezpośrednim
description: Usługa Azure SQL Data Warehouse z zapytaniem bezpośrednim
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/20/2018
ms.author: maghan
LocalizationGroup: Data from databases
ms.openlocfilehash: a09b9bed97f34b317fadc6b60216019a6c562d0f
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54295688"
---
# <a name="azure-sql-data-warehouse-with-directquery"></a>Usługa Azure SQL Data Warehouse z zapytaniem bezpośrednim
Usługa Azure SQL Data Warehouse z zapytaniem bezpośrednim umożliwia tworzenie dynamicznych raportów na podstawie danych i metryk, które już znajdują się w usłudze Azure SQL Data Warehouse. Dzięki zapytaniu bezpośredniemu zapytania są wysyłane do usługi Azure SQL Data Warehouse w czasie rzeczywistym, gdy eksplorujesz dane. Zapytania w czasie rzeczywistym połączone ze skalą usługi SQL Data Warehouse umożliwiają użytkownikom tworzenie dynamicznych raportów względem terabajtów danych w ciągu kilku minut. Ponadto wprowadzenie przycisku **Otwórz w usłudze Power BI** umożliwia użytkownikom bezpośrednie łączenie usługi Power BI z usługą SQL Data Warehouse bez konieczności ręcznego określania informacji.

W przypadku używania łącznika usługi SQL Data Warehouse:

* Określ w pełni kwalifikowaną nazwę serwera podczas łączenia (szczegóły poniżej)
* Upewnij się, że reguły zapory dla serwera są ustawione na opcję „Zezwalaj na dostęp do usług platformy Azure”
* Wszystkie akcje, takie jak wybór kolumny lub dodawanie filtru, spowodują bezpośrednie wysłanie zapytania do magazynu danych
* Kafelki są ustawione na odświeżanie co około 15 minut. Nie trzeba planować odświeżania.  Odświeżanie można dostosować w obszarze Ustawienia zaawansowane podczas łączenia.
* Funkcja Pytania i odpowiedzi nie jest dostępna dla zestawów danych trybu DirectQuery.
* Zmiany schematu nie są pobierane automatycznie.

Te ograniczenia i uwagi mogą ulegać zmianom w miarę kontynuowania procesu ulepszania środowisk. Etapy nawiązywania połączenia są szczegółowo opisane poniżej.

## <a name="using-the-open-in-power-bi-button"></a>Użycie przycisku „Otwórz w usłudze Power BI”

> [!Important]
> Pracowaliśmy nad ulepszeniem łączności z usługą Azure SQL Data Warehouse.  Aby uzyskać najlepsze wyniki podczas łączenia ze źródłem danych usługi Azure SQL Data Warehouse, użyj programu Power BI Desktop.  Po skompilowaniu modelu i raportów możesz opublikować go w usłudze Power BI.  Bezpośredni łącznik z usługą Azure SQL Data Warehouse w usłudze Power BI jest już przestarzały.
>

Najprostszym sposobem na przemieszczanie się między usługą SQL Data Warehouse i usługą Power BI jest użycie przycisku **Otwórz w usłudze Power BI** znajdującego się w witrynie Azure Portal. Ten przycisk pozwala na łatwe rozpoczęcie tworzenia nowych pulpitów nawigacyjnych w usłudze Power BI.

1. Aby rozpocząć, przejdź do swojego wystąpienia usługi SQL Data Warehouse w witrynie Azure Portal. Pamiętaj, że usługa SQL Data Warehouse jest w tej chwili obecna w witrynie Azure Portal tylko w wersji zapoznawczej.
2. Kliknij przycisk **Otwórz w usłudze Power BI**.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/openinpowerbi.png)
3. Jeśli nie możesz zalogować się bezpośrednio lub nie masz konta w usłudze Power BI, musisz się zalogować.
4. Nastąpi przekierowanie do strony logowania do usługi SQL Data Warehouse ze wstępnie wypełnionymi informacjami z usługi SQL Data Warehouse. Wprowadź swoje poświadczenia i kliknij przycisk Połącz, aby utworzyć połączenie.

## <a name="connecting-through-power-bi"></a>Łączenie się za pośrednictwem usługi Power BI
Usługa SQL Data Warehouse jest również wymieniona na stronie Pobierz dane w usłudze Power BI. 

1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.  
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/getdatabutton.png)
2. W obszarze **Bazy danych** wybierz pozycję **Pobierz**.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/databases.png)
3. Wybierz pozycję **SQL Data Warehouse** \> **Połącz**.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/azuresqldatawarehouseconnect.png)
4. Wprowadź informacje wymagane do połączenia. W poniższej sekcji **Znajdowanie parametrów** przedstawiono, gdzie te dane mogą się znajdować w witrynie Azure Portal.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/servername.png)
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/servernamewithadvanced.png)
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/username.png)
   
   > [!NOTE]
   > Nazwa użytkownika będzie oznaczała użytkownika, który jest zdefiniowany w wystąpieniu usługi Azure SQL Data Warehouse.
   > 
   > 
5. Przejdź do szczegółów zestawu danych, wybierając nowy kafelek lub nowo utworzony zestaw danych wskazany przez gwiazdkę. Ten zestaw danych będzie mieć taką samą nazwę jak baza danych.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/dataset2.png)
6. Można eksplorować wszystkie tabele i kolumny. Wybór kolumny spowoduje odesłanie zapytania do źródła, dynamicznie tworząc element wizualny. Filtry również zostaną przetłumaczone na zapytania z powrotem do magazynu danych. Te elementy wizualne mogą być zapisywane w nowym raporcie i ponownie przypięte do pulpitu nawigacyjnego.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/explore3.png)

## <a name="finding-parameter-values"></a>Znajdowanie wartości parametrów
W pełni kwalifikowaną nazwę serwera i nazwę bazy danych można znaleźć w witrynie Azure Portal. Pamiętaj, że usługa SQL Data Warehouse jest w tej chwili obecna w witrynie Azure Portal tylko w wersji zapoznawczej.

![](media/service-azure-sql-data-warehouse-with-direct-connect/azureportal.png)

> [!NOTE]
> Jeśli Twoja dzierżawa usługi Power BI będzie znajdować się w tym samym regionie co usługa Azure SQL Data Warehouse, nie będą naliczane opłaty za ruch wychodzący. Lokalizację dzierżawy usługi Power BI można znaleźć za pomocą [tych instrukcji](https://docs.microsoft.com/power-bi/service-admin-where-is-my-tenant-located).
>

## <a name="next-steps"></a>Następne kroki
[Co to jest usługa Power BI?](power-bi-overview.md)  
[Pobieranie danych dla usługi Power BI](service-get-data.md)  
[Azure SQL Data Warehouse](/azure/sql-data-warehouse/sql-data-warehouse-overview-what-is/)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)