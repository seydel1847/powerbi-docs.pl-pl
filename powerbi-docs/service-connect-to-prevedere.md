---
title: "Łączenie się z pakietem zawartości Prevedere przy użyciu usługi Power BI"
description: "Pakiet zawartości Prevedere dla usługi Power BI"
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
ms.openlocfilehash: fd9426a8fce0ed1d707184b421a93f989852a33d
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-prevedere-with-power-bi"></a>Łączenie się z pakietem zawartości Prevedere przy użyciu usługi Power BI
Uzyskaj dostęp do wyłącznych i kluczowych informacji finansowych, które pozwolą pewnie oraz aktywnie rozwijać Twoją firmę.

Połącz się z [pakietem zawartości Prevedere](https://app.powerbi.com/getdata/services/prevedere) dla usługi Power BI.

>[!NOTE]
>Jeśli nie jesteś jeszcze użytkownikiem usługi Prevedere, skorzystaj z [klucza przykładowego](https://prevederepowerbiconnector.azurewebsites.net/static/learnmore.html), aby ją wypróbować.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-prevedere/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-prevedere/services.png)
3. Wybierz pozycję **Prevedere**, a następnie pozycję **Pobierz**.
   
   ![](media/service-connect-to-prevedere/connect.png)
4. W polu **Metoda uwierzytelniania** wybierz opcję **Klucz** i wprowadź klucz interfejsu API usługi Prevedere.
   
    ![](media/service-connect-to-prevedere/creds.png)
5. Kliknij przycisk **Zaloguj**, aby rozpocząć proces importowania. Po zakończeniu tego procesu w okienku nawigacji zostaną wyświetlone nowy pulpit nawigacyjny, raport i model. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
     ![](media/service-connect-to-prevedere/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Pakiet zawartości pozwala uzyskać dostęp do analiz dotyczących prognoz sprzedaży detalicznej, modeli prognoz, wskaźników wyprzedzających i innych.

## <a name="system-requirements"></a>Wymagania systemowe
Ten pakiet zawartości wymaga dostępu do klucza interfejsu API usługi Prevedere lub klucza przykładowego (zobacz poniżej).

## <a name="finding-parameters"></a>Znajdowanie parametrów
<a name="FindingParams"></a>

Istniejący klienci mogą uzyskać dostęp do danych przy użyciu klucza interfejsu API. Jeśli nie jesteś jeszcze naszym klientem, możesz wyświetlić przykładowe dane i analizy przy użyciu [klucza przykładowego](https://prevederepowerbiconnector.azurewebsites.net/static/learnmore.html).

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Ładowanie danych może zająć trochę czasu w zależności od wystąpienia.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)
