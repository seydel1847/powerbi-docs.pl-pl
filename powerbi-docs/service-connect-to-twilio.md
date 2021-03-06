---
title: Łączenie się z usługą Twilio za pomocą usługi Power BI
description: Usługa Twilio dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 4537f2845d89361cf06bc93a6a9c435275d9464d
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008148"
---
# <a name="connect-to-twilio-with-power-bi"></a>Łączenie się z usługą Twilio za pomocą usługi Power BI
Pakiet zawartości Microsoft Twilio dla usługi Power BI pozwala na ściąganie danych do usługi Power BI i tworzy gotowy do użycia [pulpit nawigacyjny Twilio](https://powerbi.microsoft.com/integrations/twilio) oraz raport, który zawiera szczegółowe informacje na temat danych. Możesz również tworzyć niestandardowe raporty i pulpit nawigacyjny w zestawie danych tworzonym przez usługę Power BI. Dane będą odświeżane raz dziennie, więc zawsze będziesz widzieć najnowsze dane.

Połącz się z [pakietem zawartości Twilio](https://app.powerbi.com/getdata/services/twilio) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-twilio/pbi_getdata.png) 
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-twilio/pbi_getservices.png) 
3. Wybierz pozycję **Twilio** \> **Pobierz**.
   
   ![](media/service-connect-to-twilio/twilio.png)
4. Jako **metodę uwierzytelniania** wybierz opcję **oAuth2** \> Zaloguj. Po wyświetleniu monitu podaj swoje poświadczenia Twilio i zezwól aplikacji Power BI na dostęp do danych.
   
   ![](media/service-connect-to-twilio/pbi_twilio_login.png)
5. Spowoduje to rozpoczęcie importowania danych z konta Twilio. Pulpit nawigacyjny zostanie wypełniony informacjami o rozmowach i wiadomościach z ostatnich 30 dni. 
   
   ![](media/service-connect-to-twilio/pbi_twilio_db.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Szczegółowe informacje na temat wszystkich transakcji dotyczących rozmów i wiadomości z ostatnich 30 dni. Te dane można poddawać wszelkiego rodzaju analizom i agregacji.

Zestaw już zagregowanych statystyk, które możesz kontrolować. Ten zestaw zawiera:

        All Time Calls Count  
        All Time Calls Duration  
        All Time Calls Price  
        All Time Messages Price  
        All Time Messages Count  
        All Time Count of Phone Numbers  
        All Time Price of Phone Numbers  
        All Time Twilio Client Calls Price  
        All Time Twilio Client Calls Duration  
        All Time Twilio Client Calls Count  
        All Time Total Price  
        All Time Inbound Calls Price  
        All Time Inbound Calls Duration  
        All Time Inbound Calls Count  
        All Time Outbound Calls Price  
        All Time Outbound Calls Duration  
        All Time Outbound Calls Count  
        This Month Calls Price  
        This Month Calls Duration  
        This Month Calls Count  
        This Month Messages Count  
        This Month Messages Price  
        This Month Count of Phone Numbers  
        This Month Price of Phone Numbers  
        This Month Twilio Client Calls Price  
        This Month Twilio Client Calls Duration  
        This Month Twilio Client Calls Count  
        This Month Total Price  
        This Month Inbound Calls Price  
        This Month Inbound Calls Duration  
        This Month Inbound Calls Count  
        This Month Outbound Calls Price  
        This Month Outbound Calls Duration  
        This Month Outbound Calls Count  
        This Month Inbound Messages Price  
        This Month Inbound Messages Count  
        This Month Outbound Messages Price  
        This Month Outbound Messages Count

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Jeśli w ostatnich 30 dniach masz bardzo duże ilości danych (setki tysięcy transakcji), etap pobierania danych może zakończyć się niepowodzeniem. Zdajemy sobie sprawę z problemu i pracujemy nad jego rozwiązaniem. Jeśli napotkasz ten problem, użyj linku do pomocy technicznej, który znajduje się w górnej części strony usługi Power BI, aby poinformować nas o tym, a my skontaktujemy się Tobą, aby kontynuować badanie problemu.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)

