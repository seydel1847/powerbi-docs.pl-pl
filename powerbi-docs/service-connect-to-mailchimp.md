---
title: "Łączenie się z pakietem zawartości MailChimp przy użyciu usługi Power BI"
description: "Pakiet zawartości MailChimp dla usługi Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
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
ms.author: yshoukry
ms.openlocfilehash: 5a0935d9401841ee2db71fdf821621ababdd01cb
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-mailchimp-with-power-bi"></a>Łączenie się z pakietem zawartości MailChimp przy użyciu usługi Power BI
Pakiet zawartości usługi Power BI pobiera dane z konta usługi MailChimp oraz generuje pulpit nawigacyjny, zestaw raportów i zestaw danych, aby umożliwić eksplorowanie danych. Pobieraj analizy, aby tworzyć [pulpity nawigacyjne usługi MailChimp](https://powerbi.microsoft.com/integrations/mailchimp) i w szybki sposób identyfikować trendy w ramach kampanii, raportów oraz dla poszczególnych subskrybentów. Dane będą odświeżane codziennie, zapewniając aktualność monitorowanych danych.

Połącz się z [pakietem zawartości MailChimp](https://app.powerbi.com/getdata/services/mailchimp) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
    ![](media/service-connect-to-mailchimp/pbi_getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-mailchimp/pbi_getservices.png)
3. Wybierz pozycję **MailChimp** \> **Pobierz**.
   
   ![](media/service-connect-to-mailchimp/mailchimp.png)
4. Jako metodę uwierzytelniania wybierz opcję **oAuth2** \> **Zaloguj**.
   
    Po wyświetleniu monitu wprowadź swoje poświadczenia usługi MailChimp i postępuj zgodnie z procesem uwierzytelniania.
   
    Przy pierwszym połączeniu usługa Power BI wyświetli monit o zgodę na dostęp do konta w trybie tylko do odczytu. Wybierz przycisk **Zezwalaj**, aby rozpocząć proces importowania, który może zająć kilka minut w zależności od ilości danych na koncie.
   
    ![](media/service-connect-to-mailchimp/allow.png)
5. Po zaimportowaniu danych przez usługę Power BI zobaczysz nowy pulpit nawigacyjny, raport i zestaw danych w okienku nawigacji po lewej stronie. Jest to domyślny pulpit nawigacyjny utworzony przez usługę Power BI do wyświetlania Twoich danych. Możesz modyfikować pulpit nawigacyjny, aby wyświetlać dane w dowolny sposób.
   
   ![](media/service-connect-to-mailchimp/pbi_mailchimpnewdash.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

