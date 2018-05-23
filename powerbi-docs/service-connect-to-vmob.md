---
title: Łączenie się z pakietem zawartości VMob przy użyciu usługi Power BI
description: Pakiet zawartości VMob dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b1f2970ad73783acf3736856463915161056b801
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="connect-to-vmob-with-power-bi"></a>Łączenie się z pakietem zawartości VMob przy użyciu usługi Power BI
Przy użyciu usługi Power BI i pakietu zawartości VMob można łatwo śledzić i eksplorować dane w usłudze VMob. Usługa Power BI pobiera następujące dane: statystyki użytkowników dla wszystkich okresów łącznie i za ostatnie 30 dni, wskaźnik KPI dotyczący sprzedaży detalicznej za ostatnie 30 dni oraz wydajność kampanii za okres ostatnich 30 dni.

Połącz się z [pakietem zawartości VMob](https://app.powerbi.com/getdata/services/vmob) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
    ![](media/service-connect-to-vmob/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-vmob/services.png)
3. Wybierz pozycję **VMob** \> **Pobierz**.
   
   ![](media/service-connect-to-vmob/vmob.png)
4. Po wyświetleniu monitu podaj adres URL usługi VMob, a następnie kliknij przycisk Dalej. Ten adres URL jest dostarczany przez usługę VMob oddzielnie.
   
    ![](media/service-connect-to-vmob/params.png)
5. Z listy rozwijanej metod uwierzytelniania wybierz opcję **Podstawowa**, wprowadź nazwę użytkownika oraz hasło usługi VMob i kliknij przycisk **Zaloguj**.
   
    ![](media/service-connect-to-vmob/creds.png)
6. Proces importowania rozpocznie się automatycznie, a usługa Power BI pobierze dane usługi VMob, aby utworzyć gotowy do użycia pulpit nawigacyjny i raport.
   
   ![](media/service-connect-to-vmob/dashboard2.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)

