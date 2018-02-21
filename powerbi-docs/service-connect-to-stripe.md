---
title: "Łączenie się z pakietem zawartości Stripe przy użyciu usługi Power BI"
description: "Pakiet zawartości Stripe dla usługi Power BI"
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
ms.openlocfilehash: 02ff2a878f8ae016d824d9039c79279519428136
ms.sourcegitcommit: c24e5d7bd1806e0d637e974b5143ab5125298fc6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2018
---
# <a name="connect-to-stripe-with-power-bi"></a>Łączenie się z pakietem zawartości Stripe przy użyciu usługi Power BI
Za pomocą pakietu zawartości dla usługi Power BI możesz wizualizować i eksplorować dane usługi Stripe. Pakiet zawartości Stripe dla usługi Power BI pobiera dane o klientach, opłatach, zdarzeniach i fakturach. Dane obejmują najnowsze dziesięć tysięcy zdarzeń i pięć tysięcy opłat z ostatnich 30 dni. Zawartość będzie odświeżana automatycznie raz dziennie zgodnie z ustalonym przez Ciebie harmonogramem. 

Połącz się z [pakietem zawartości Stripe dla usługi Power BI](https://app.powerbi.com/getdata/services/stripe).

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję Pobierz dane w dolnej części okienka nawigacji po lewej stronie.  
   
    ![](media/service-connect-to-stripe/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.  
   
    ![](media/service-connect-to-stripe/services.png)  
3. Wybierz pozycje **Stripe** &gt; **Pobierz**.  
   
    ![](media/service-connect-to-stripe/stripe.png)  
4. Podaj [klucz interfejsu API](https://dashboard.stripe.com/account/apikeys) usługi Stripe, aby się połączyć.  
   
    ![](media/service-connect-to-stripe/creds.png)
5. Proces importowania rozpocznie się automatycznie. Po zakończeniu tego procesu w okienku nawigacji zostaną wyświetlone nowy pulpit nawigacyjny, raport i model, oznaczone gwiazdką. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
    ![](media/service-connect-to-stripe/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych dla usługi Power BI](service-get-data.md)

