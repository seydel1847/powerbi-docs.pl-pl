---
title: Łączenie się z usługą SendGrid za pomocą usługi Power BI
description: Usługa SendGrid dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: a0ae99e2dfad889840cc29ca4fa9f0f29397bf04
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37135380"
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

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

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

