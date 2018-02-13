---
title: "Nawiązywanie połączenia z usługą Azure Security Center przy użyciu usługi Power BI"
description: "Azure Security Center dla usługi Power BI"
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
ms.openlocfilehash: e26a26d7cba2ae3d68586a2e0dcdf87481009bd6
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-azure-security-center-with-power-bi"></a>Nawiązywanie połączenia z usługą Azure Security Center przy użyciu usługi Power BI
Uzyskaj informacje o zabezpieczeniach obciążenia platformy Azure, łącząc dane zabezpieczeń platformy Azure z usługą Power BI. Usługa Power BI automatycznie tworzy pulpit nawigacyjny i raport na podstawie danych usługi Azure Security Center, umożliwiając analizowanie i eksplorowanie danych.

Nawiąż połączenie z [pakietem zawartości Azure Security Center](https://app.powerbi.com/getdata/services/azure-security-center) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-azure-security-center/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-azure-security-center/services.png)
3. Wybierz pozycję **Azure Security Center** \>  **Pobierz**.
   
   ![](media/service-connect-to-azure-security-center/asc.png)
4. Określ swój identyfikator subskrypcji. Poniżej znajdują się szczegółowe informacje dotyczące [wyszukiwania tych parametrów](#FindingParams).
   
   ![](media/service-connect-to-azure-security-center/params.png)
5. Jako **metodę uwierzytelniania** wybierz opcję **oAuth2** \> **Zaloguj**. Po wyświetleniu monitu wprowadź poświadczenia platformy Azure.
   
    ![](media/service-connect-to-azure-security-center/creds.png)
6. Po zatwierdzeniu proces importowania rozpocznie się automatycznie. Po zakończeniu nowy pulpit nawigacyjny, raport i model zostaną wyświetlone w okienku nawigacji. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
     ![](media/service-connect-to-azure-security-center/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Pakiet zawartości obejmuje informacje dotyczące stanu zabezpieczeń zasobu, analizy alertów oraz analizy zapobiegania.

## <a name="system-requirements"></a>Wymagania systemowe
Ten pakiet zawartości wymaga włączonego dostępu do identyfikatora subskrypcji w usłudze Azure Security Center. Zobacz więcej szczegółów w sekcji [Azure Security Center](https://portal.azure.com/#blade/Microsoft_Azure_Security/SecurityDashboardStartBladeV2) w witrynie Azure Portal.

Ponadto pakiet zawartości wymaga, aby użytkownik nawiązał połączenie przy użyciu konta firmowego (nie konta osobistego).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Istnieją dwa sposoby na proste odnalezienie identyfikatora subskrypcji.

1. Z witryny https://portal.azure.com —&gt; Przeglądaj —&gt; Subskrypcje —&gt; Identyfikator subskrypcji
2. Z witryny https://manage.windowsazure.com —&gt; Ustawienia —&gt; Identyfikator subskrypcji

Identyfikator subskrypcji będzie długim zestawem cyfr i znaków, podobnym do przykładu w kroku \#4 powyżej. 

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Ładowanie danych może zająć trochę czasu w zależności od konta. Jeśli podczas logowania napotkasz błąd, sprawdź parametry i upewnij się, że konto ma włączoną usługę Azure Security Center.

Jeśli pakiet zawartości został załadowany, ale nie wyświetla żadnych danych, upewnij się, że łączysz się przy użyciu konta firmowego. Konta osobiste są obsługiwane przez usługę Azure Security Center, niemniej interfejs API (a zatem pakiet zawartości) nie zwraca oczekiwanych wartości, jeśli użytkownik połączy się przy użyciu konta innego niż firmowe. Zapewnij dostęp do konta firmowego i spróbuj połączyć się ponownie.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)

