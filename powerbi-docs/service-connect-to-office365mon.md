---
title: Łączenie się z pakietem zawartości Office365Mon za pomocą usługi Power BI
description: Pakiet zawartości Office365Mon dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 18093772232d119a24e76437d3f62a145a0a7153
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34247693"
---
# <a name="connect-to-office365mon-with-power-bi"></a>Łączenie się z pakietem zawartości Office365Mon za pomocą usługi Power BI
Analizowanie danych wydajności dotyczących kondycji i awarii usługi Office 365 jest bardzo proste dzięki usłudze Power BI i pakietowi zawartości Office365Mon. Usługa Power BI pobiera dane, w tym dane sond kondycji i awarii, a następnie tworzy gotowy pulpit nawigacyjny i gotowe raporty na podstawie tych danych.

Połącz się z [pakietem zawartości Office365Mon](https://app.powerbi.com/groups/me/getdata/services/office365mon) dla usługi Power BI.

>[!NOTE]
>Aby nawiązać połączenie i załadować pakiet zawartości usługi Power BI, wymagane jest konto administratora Office365Mon.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-office365mon/pbi_getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-office365mon/pbi_getservices.png) 
3. Wybierz pozycję **Office365Mon** \> **Pobierz**.
   
   ![](media/service-connect-to-office365mon/o365mon.png)
4. Jako metodę uwierzytelniania wybierz opcję **oAuth2** \> **Zaloguj**.
   
   Po wyświetleniu monitu wprowadź swoje poświadczenia administratora Office365Mon i postępuj zgodnie z procesem uwierzytelniania.
   
   ![](media/service-connect-to-office365mon/creds.png)
   
   ![](media/service-connect-to-office365mon/creds2.png)
5. Po zaimportowaniu danych przez usługę Power BI zobaczysz nowy pulpit nawigacyjny, raport i zestaw danych w okienku nawigacji po lewej stronie. Nowe elementy są oznaczone żółtą gwiazdką \*, wybierz pozycję Office365Mon.
   
   ![](media/service-connect-to-office365mon/dashboard4.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Jeśli po zalogowaniu się przy użyciu poświadczeń subskrypcji pakietu Office365Mon otrzymasz komunikat o błędzie **„Logowanie nie powiodło się”**, oznacza to, że konto, którego używasz, nie ma uprawnień do pobierania danych pakietu Office365Mon z Twojego konta. Sprawdź, czy jest to konto administratora, i spróbuj ponownie.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych dla usługi Power BI](service-get-data.md)

