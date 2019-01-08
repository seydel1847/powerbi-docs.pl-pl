---
title: Łączenie się z usługą SendGrid za pomocą usługi Power BI
description: Usługa SendGrid dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 2e9da4bc46a741af42a214d4e70fd46bfaa4a541
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007783"
---
# <a name="connect-to-sendgrid-with-power-bi"></a>Łączenie się z usługą SendGrid za pomocą usługi Power BI
Pakiet zawartości Power BI dla usługi SendGrid pozwala na wyodrębnianie szczegółowych danych i statystyk z Twojego konta SendGrid. Przy użyciu pakietu zawartości SendGrid możesz zwizualizować statystyki SendGrid na pulpicie nawigacyjnym.

Połącz się z [pakietem zawartości SendGrid](https://app.powerbi.com/getdata/services/sendgrid) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-sendgrid/pbi_getdata.png) 
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-sendgrid/pbi_getservices.png) 
3. Wybierz pakiet zawartości **SendGrid**, a następnie kliknij przycisk **Pobierz**.
   
   ![](media/service-connect-to-sendgrid/sendgrid.png) 
4. Po wyświetleniu monitu podaj nazwę użytkownika i hasło do konta SendGrid. Wybierz pozycję **Zaloguj**.
   
   ![](media/service-connect-to-sendgrid/pbi_sendgridsignin.png)
5. Po zaimportowaniu danych przez usługę Power BI w lewym okienku nawigacji zobaczysz nowy pulpit nawigacyjny, raport i zestaw danych wypełniony statystykami dotyczącymi poczty e-mail z ostatnich 90 dni. Nowe elementy są oznaczone żółtą gwiazdką \*.
   
   ![](media/service-connect-to-sendgrid/pbi_sendgriddash.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Na pulpicie nawigacyjnym SendGrid dostępne są następujące metryki:

* Ogólne statystyki dotyczące wiadomości e-mail: żądania, dostarczone, zwrócone, zablokowane wiadomości-śmieci, raport na temat wiadomości-śmieci itp.
* Statystyka dotycząca wiadomości e-mail według kategorii
* Statystyka dotycząca wiadomości e-mail według lokalizacji geograficznej
* Statystyka dotycząca wiadomości e-mail według usługodawcy internetowego
* Statystyka dotycząca wiadomości e-mail według urządzenia, klienta, przeglądarki

## <a name="next-steps"></a>Następne kroki
[Co to jest usługa Power BI?](power-bi-overview.md)

[Pobieranie danych](service-get-data.md)

