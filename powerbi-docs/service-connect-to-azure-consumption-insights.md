---
title: Łączenie się z usługą Microsoft Azure Consumption Insights przy użyciu usługi Power BI
description: Pakiet zawartości Microsoft Azure Consumption Insights dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 31f1d4161801b45307e92ad3f654d30843897dc8
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34244162"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Łączenie się z usługą Microsoft Azure Consumption Insights przy użyciu usługi Power BI
Eksploruj i monitoruj dane dotyczące użycia platformy Microsoft Azure w usłudze Power BI przy użyciu pakietu zawartości Power BI. Dane będą odświeżane automatycznie raz dziennie.

Połącz się z [pakietem zawartości Microsoft Azure Consumption Insights](https://app.powerbi.com/getdata/services/azureconsumption) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. Wybierz pozycję **Microsoft Azure Consumption Insights** \> **Pobierz**. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Podaj liczbę miesięcy, dla których chcesz zaimportować dane, oraz numer rejestracji w usłudze Azure Enterprise. Poniżej znajdują się szczegółowe informacje dotyczące [wyszukiwania tych parametrów](#FindingParams).
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Podaj klucz dostępu w celu nawiązania połączenia. Klucz rejestracji można znaleźć w witrynie Azure EA Portal. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Proces importowania rozpocznie się automatycznie. Po zakończeniu nowy pulpit nawigacyjny, raport i model zostaną wyświetlone w okienku nawigacji. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Pakiet zawartości Microsoft Azure Consumption Insights obejmuje miesięczne dane raportowania z zakresu miesięcy podanego podczas przepływu połączenia. Zakres to okno ruchome, więc uwzględnione daty będą aktualizowane podczas odświeżania zestawu danych.

## <a name="system-requirements"></a>Wymagania systemowe
Pakiet zawartości wymaga dostępu do funkcji Enterprise w witrynie Azure Portal. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Raportowanie w usłudze Power BI jest dostępne dla klientów pośrednich, partnerów i klientów bezpośrednich EA, którzy mają możliwość wyświetlania informacji dotyczących rozliczeń. Przeczytaj poniższe informacje dotyczące znajdowania wszystkich wartości wymaganych przez przepływ połączenia.

**Liczba miesięcy**

* Musi to być wartość z zakresu od 1 do 36 reprezentująca liczbę miesięcy danych (od bieżącego dnia), które chcesz zaimportować.

**Numer rejestracji**

* Jest to numer rejestracji w usłudze Azure Enterprise, który można znaleźć na ekranie głównym witryny [Azure Enterprise Portal](https://ea.azure.com/) w obszarze „Szczegóły rejestracji”.
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**Klucz dostępu**

* Klucz można znaleźć w witrynie Azure Enterprise Portal, w obszarze „Pobierz dane użycia” > „Klucz dostępu interfejsu API”
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**Dodatkowa pomoc**

* Aby uzyskać dodatkową pomoc w konfigurowaniu pakietu Power BI w usłudze Azure Enterprise, zaloguj się w witrynie Azure Enterprise Portal w celu wyświetlenia pliku pomocy interfejsu API w obszarze „Pomoc” oraz dodatkowych instrukcji w obszarze Raporty > Pobierz dane użycia > Klucz dostępu interfejsu API. 

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)

