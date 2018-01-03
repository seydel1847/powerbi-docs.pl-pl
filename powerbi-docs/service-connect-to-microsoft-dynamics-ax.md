---
title: "Nawiązywanie połączenia z pakietem zawartości Microsoft Dynamics AX przy użyciu usługi Power BI"
description: "Pakiet zawartości Microsoft Dynamics AX dla usługi Power BI"
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
ms.openlocfilehash: f942c0551a473140903e2fce19feba641a62e5a2
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-microsoft-dynamics-ax-content-pack-with-power-bi"></a>Nawiązywanie połączenia z pakietem zawartości Microsoft Dynamics AX przy użyciu usługi Power BI
System Microsoft Dynamics AX ma trzy pakiety zawartości Power BI przeznaczone dla różnych użytkowników biznesowych. Pakiet zawartości Financial Performance, zaprojektowany specjalnie z myślą o dyrektorach finansowych, zapewnia dostęp do szczegółowych informacji dotyczących wydajności finansowej organizacji. Pakiet zawartości Retail Channel Performance jest przeznaczony dla menedżerów kanału i koncentruje się na wydajności sprzedaży, aby umożliwiać przewidywanie trendów i odkrywanie informacji opartych bezpośrednio na danych dotyczących sprzedaży detalicznej i działań komercyjnych. Pakiet Cost Management jest przeznaczony dla dyrektorów zarządzających oraz dyrektorów finansowych i zapewnia szczegółowe informacje dotyczące wydajności operacyjnej.

Nawiąż połączenie z pakietem zawartości Microsoft Dynamics AX [Retail Channel Performance](https://app.powerbi.com/getdata/services/dynamics-ax-retail-channel-performance), [Financial Performance](https://app.powerbi.com/getdata/services/dynamics-ax-financial-performance) lub [Cost Management](https://app.powerbi.com/getdata/services/dynamics-ax-cost-management) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/services.png)
3. Wybierz jeden z pakietów zawartości Dynamics AX i wybierz opcję **Pobierz**.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/mdax.png)
4. Określ adres URL środowiska Dynamics AX 7. Poniżej znajdują się szczegółowe informacje dotyczące [wyszukiwania tych parametrów](#FindingParams).
   
   ![](media/service-connect-to-microsoft-dynamics-ax/params.png)
5. Jako **metodę uwierzytelniania** wybierz opcję **oAuth2** \> **Zaloguj**. Po wyświetleniu monitu wprowadź poświadczenia Dynamics AX.
   
    ![](media/service-connect-to-microsoft-dynamics-ax/creds.png)
   
    ![](media/service-connect-to-microsoft-dynamics-ax/creds2.png)
6. Po zatwierdzeniu proces importowania rozpocznie się automatycznie. Po zakończeniu tego procesu w okienku nawigacji zostaną wyświetlone nowy pulpit nawigacyjny, raport i model. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
     ![](media/service-connect-to-microsoft-dynamics-ax/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu Pytania i odpowiedzi](service-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Pakiet zawartości używa źródła Dynamics AX 7 OData do importowania danych powiązanych z wydajnością kanału sprzedaży (Retail Channel), finansową (Financial) oraz zarządzania kosztami (Cost Management).

## <a name="system-requirements"></a>Wymagania systemowe
Ten pakiet zawartości wymaga adresu URL środowiska Dynamics AX 7, a użytkownik powinien mieć dostęp do źródła danych OData.

## <a name="finding-parameters"></a>Znajdowanie parametrów
<a name="FindingParams"></a>

Adres URL środowiska Dynamics AX 7 można znaleźć w przeglądarce po zalogowaniu użytkownika. Wystarczy skopiować adres URL głównego środowiska Dynamics AX do okna dialogowego usługi Power BI.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Ładowanie danych może zająć trochę czasu w zależności od wystąpienia. Jeśli widzisz puste raporty w usłudze Power BI, upewnij się, że masz dostęp do tabel OData wymaganych do utworzenia raportów.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)
