---
title: "Nawiązywanie połączenia z Centrum deweloperów systemu Windows przy użyciu usługi Power BI"
description: "Centrum deweloperów systemu Windows dla usługi Power BI"
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
ms.openlocfilehash: 95673e25b373f6878ba87098fa8e37625f6c4996
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-windows-dev-center-with-power-bi"></a>Nawiązywanie połączenia z Centrum deweloperów systemu Windows przy użyciu usługi Power BI
Eksploruj i monitoruj dane analiz aplikacji Centrum deweloperów systemu Windows w usłudze Power BI przy użyciu pakietu zawartości Power BI. Dane będą odświeżane automatycznie raz dziennie.

Nawiąż połączenie z [pakietem zawartości Centrum deweloperów systemu Windows](https://app.powerbi.com/getdata/services/devcenter) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-windows-dev-center/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-windows-dev-center/services.png)
3. Wybierz pozycję **Centrum deweloperów systemu Windows** \>  **Pobierz**.
   
   ![](media/service-connect-to-windows-dev-center/windowsdev.png)
4. Wprowadź identyfikator posiadanej aplikacji i kliknij przycisk Dalej. Poniżej znajdują się szczegółowe informacje dotyczące [wyszukiwania tych parametrów](#FindingParams).
   
   ![](media/service-connect-to-windows-dev-center/params.png)
5. Jako **metodę uwierzytelniania** wybierz opcję **oAuth2** \> **Zaloguj**. Po wyświetleniu monitu wprowadź poświadczenia usługi Azure Active Directory skojarzone z kontem Centrum deweloperów systemu Windows (więcej informacji znajduje się w sekcji [Wymagania systemowe](#Requirements)).
   
    ![](media/service-connect-to-windows-dev-center/creds.png)
   
    ![](media/service-connect-to-windows-dev-center/creds2.png)
6. Po zatwierdzeniu proces importowania rozpocznie się automatycznie. Po zakończeniu tego procesu w okienku nawigacji zostaną wyświetlone nowy pulpit nawigacyjny, raport i model. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane, a następnie wybierz kafelek, aby przejść do raportów źródłowych.
   
    ![](media/service-connect-to-windows-dev-center/dashboard.png)
   
    ![](media/service-connect-to-windows-dev-center/report.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Pakiet zawartości Centrum deweloperów dla usługi Power BI zawiera dane analityczne dotyczące aplikacji oraz nabyć IAP, klasyfikacji, recenzji i kondycji aplikacji. Dane są ograniczone do ostatnich 3 miesięcy. oraz jest to okno ruchome, więc uwzględnione daty będą aktualizowane podczas odświeżania zestawu danych.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Wymagania systemowe
Ten pakiet zawartości wymaga co najmniej jednej aplikacji opublikowanej w Sklepie Windows oraz konta Centrum deweloperów systemu Windows (więcej informacji znajduje się [tutaj](https://msdn.microsoft.com/windows/uwp/publish/manage-account-users)).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Identyfikator aplikacji można znaleźć na stronie tożsamości aplikacji w sekcji Zarządzanie aplikacjami.

Identyfikator aplikacji znajduje się na końcu adresu URL w Sklepie Windows 10, https://www.microsoft.com/store/apps/ **{applicationId}**

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)

