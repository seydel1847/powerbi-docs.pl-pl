---
title: Łączenie się z usługą ServiceNow za pomocą usługi Power BI
description: Pakiet zawartości ServiceNow dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 285c22347f049e6b99cb97fa19efc6363d9b57cb
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008654"
---
# <a name="connect-to-servicenow-with-power-bi-for-incident-reporting"></a>Łączenie się z usługą ServiceNow za pomocą usługi Power BI w celu raportowania zdarzeń
Firma ServiceNow oferuje wiele produktów i rozwiązań, w tym dotyczących zarządzania działalnością biznesową, bieżącymi operacjami i zarządzania IT, które pozwalają usprawnić firmę. Ten pakiet zawartości obejmuje szereg raportów oraz szczegółowych informacji dotyczących otwartych, ostatnio rozwiązanych i ostatnio zakończonych zdarzeń.  

Połącz się z pakietem zawartości usługi Power BI dla usługi [ServiceNow Incidents](https://app.powerbi.com/getdata/services/servicenow).

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-servicenow/pbi_getdata.png) 
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-servicenow/pbi_getservices.png) 
3. Wybierz pozycję **ServiceNow Incidents** \> **Pobierz**.
   
   ![](media/service-connect-to-servicenow/connect.png)
4. Podaj adres URL wystąpienia usługi ServiceNow i zakres dni/rekordów do pobrania. Po osiągnięciu limitu import zostanie zatrzymany.
   
   ![](media/service-connect-to-servicenow/params.png)
5. Po wyświetleniu monitu wprowadź poświadczenia usługi ServiceNow dla **podstawowej** metody uwierzytelniania. Logowanie jednokrotne nie jest obecnie obsługiwane. Więcej szczegółowych informacji o wymaganiach systemowych można znaleźć poniżej.
   
   ![](media/service-connect-to-servicenow/creds.png)
6. Po zakończeniu przepływu logowania rozpocznie się proces importowania. Po zakończeniu nowy pulpit nawigacyjny, raport i model zostaną wyświetlone w okienku nawigacji. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
    ![](media/service-connect-to-servicenow/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="system-requirements"></a>Wymagania systemowe
Aby nawiązać połączenie, potrzebne są następujące elementy:  

* Konto, które może uzyskać dostęp do witryny organizacja.service-now.com za pomocą uwierzytelniania podstawowego (logowanie jednokrotne nie jest obsługiwane w tej wersji)  
* Konto musi mieć rolę rest_service i dostęp w trybie do odczytu do tabeli zdarzeń  

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Jeśli podczas ładowania występuje błąd poświadczeń, sprawdź powyższe wymagania dostępu. Jeśli masz odpowiednie uprawnienia, a problem nadal występuje, skontaktuj się z administratorem usługi ServiceNow, aby upewnić się, że masz dodatkowe uprawnienia, które mogą być wymagane w przypadku Twojego wystąpienia niestandardowego.

Jeśli ładowanie trwa długo, sprawdź liczbę zdarzeń oraz liczbę dni określonych podczas nawiązywania połączenia i rozważ zmniejszenie tych wartości.

## <a name="next-steps"></a>Następne kroki
[Co to jest usługa Power BI?](power-bi-overview.md)

[Power BI — podstawowe pojęcia](consumer/end-user-basic-concepts.md)

