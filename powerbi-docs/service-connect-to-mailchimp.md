---
title: Łączenie się z pakietem zawartości MailChimp przy użyciu usługi Power BI
description: Pakiet zawartości MailChimp dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e6e09ceb6aa40f26e145b5ace7a3c9e94bfcb44d
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2018
ms.locfileid: "46547757"
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

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="next-steps"></a>Następne kroki
[Co to jest usługa Power BI?](power-bi-overview.md)

[Power BI — podstawowe pojęcia](consumer/end-user-basic-concepts.md)

