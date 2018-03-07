---
title: "Łączenie się z usługą Azure Search za pomocą usługi Power BI"
description: "Usługa Azure Search dla usługi Power BI"
services: powerbi
documentationcenter: 
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: d868c50a69381c1ef95a8b3a69590223eb066e90
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-azure-search-with-power-bi"></a>Łączenie się z usługą Azure Search za pomocą usługi Power BI
Usługa Azure Search Traffic Analytics pozwala na monitorowanie i zrozumienie ruchu w usłudze Azure Search. Pakiet zawartości Azure Search dla usługi Power BI dostarcza szczegółowe informacje na temat danych wyszukiwania, w tym wyszukiwania, indeksowania, statystyk usługi i opóźnienia w ciągu ostatnich 30 dni. Więcej szczegółów można znaleźć we [wpisie na blogu dotyczącym platformy Azure](https://azure.microsoft.com/en-us/blog/analyzing-your-azure-search-traffic/).

Połącz się z [pakietem zawartości Azure Search](https://app.powerbi.com/getdata/services/azure-search) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-azure-search/pbi_getdata.png) 
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-azure-search/pbi_getservices.png) 
3. Wybierz pozycję **Azure Search** \> **Pobierz**.
   
   ![](media/service-connect-to-azure-search/azuresearch.png)
4. Podaj nazwę konta magazynu tabeli, na którym jest przechowywana analiza usługi Azure Search.
   
   ![](media/service-connect-to-azure-search/params.png)
5. Jako mechanizm uwierzytelniania wybierz **Klucz** i podaj swój klucz konta magazynu. Kliknij przycisk **Zaloguj** i rozpocznij proces ładowania.
   
   ![](media/service-connect-to-azure-search/creds.png)
6. Po zakończeniu ładowania nowy pulpit nawigacyjny, raport i model zostanie wyświetlony w okienku nawigacji. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
    ![](media/service-connect-to-azure-search/dashboard2.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="system-requirements"></a>Wymagania systemowe
Pakiet zawartości Azure Search wymaga, aby usługa Azure Search Traffic Analytics była włączona na koncie.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Upewnij się, że nazwa konta magazynu została poprawnie wprowadzona razem z kluczem pełnego dostępu. Nazwa konta magazynu powinna zgadzać się z kontem skonfigurowanym w usłudze Azure Search Traffic Analytics.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

