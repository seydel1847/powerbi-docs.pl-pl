---
title: Łączenie się z pakietem zawartości Stripe przy użyciu usługi Power BI
description: Pakiet zawartości Stripe dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6a194a4d56f4a940ad892ccd2f9097dd782f49d3
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008539"
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

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="next-steps"></a>Następne kroki
[Co to jest usługa Power BI?](power-bi-overview.md)

[Pobieranie danych dla usługi Power BI](service-get-data.md)

