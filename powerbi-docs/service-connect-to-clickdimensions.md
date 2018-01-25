---
title: "Łączenie się z pakietem zawartości ClickDimensions za pomocą usługi Power BI"
description: "Pakiet zawartości ClickDimensions dla usługi Power BI"
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
ms.openlocfilehash: 007d4f6f5181722e23e280e1a57d305d7f069155
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-clickdimensions-with-power-bi"></a>Łączenie się z pakietem zawartości ClickDimensions za pomocą usługi Power BI
Pakiet zawartości ClickDimensions dla usługi Power BI pozwala użytkownikom wykorzystywać dane marketingowe usługi ClickDimensions w usłudze Power BI, oferując zespołom zarządzającym możliwość lepszej oceny efektów podejmowanych wysiłków sprzedażowych i marketingowych. Wizualizuj i analizuj interakcje w ramach wiadomości e-mail, odwiedziny na stronach internetowych oraz odsyłane formularze w raportach i pulpitach nawigacyjnych usługi Power BI.

Połącz się z [pakietem zawartości ClickDimensions](https://app.powerbi.com/getdata/services/click-dimensions) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-clickdimensions/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-clickdimensions/services.png)
3. Wybierz pozycję **ClickDimensions** \>  **Pobierz**.
   
   ![](media/service-connect-to-clickdimensions/clickdimensions.png)
4. Podaj lokalizację centrum danych (USA, Europa lub Australia) i wybierz przycisk **Dalej**.
   
   ![](media/service-connect-to-clickdimensions/params.png)
5. W polu **Metoda uwierzytelniania** wybierz opcję **Podstawowa** \> **Zaloguj**. Po wyświetleniu monitu wprowadź poświadczenia usługi ClickDimensions. Poniżej znajdują się szczegółowe informacje dotyczące [wyszukiwania tych parametrów](#FindingParams)
   
    ![](media/service-connect-to-clickdimensions/creds.png)
6. Po zatwierdzeniu proces importowania rozpocznie się automatycznie. Po zakończeniu nowy pulpit nawigacyjny, raport i model zostaną wyświetlone w okienku nawigacji. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
     ![](media/service-connect-to-clickdimensions/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="system-requirements"></a>Wymagania systemowe
Aby nawiązać połączenie z pakietem zawartości usługi Power BI, należy podać informacje dotyczące odpowiadającego kontu centrum danych oraz zalogować się przy użyciu konta usługi ClickDimensions. Jeśli nie wiesz, jakie centrum danych masz podać, skonsultuj to z administratorem.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Klucz konta można znaleźć w pozycji Ustawienia CRM \> Ustawienia usługi ClickDimensions. Skopiuj klucz konta z pozycji Ustawienia usługi ClickDimensions i wklej go w polu Nazwa użytkownika.  

![](media/service-connect-to-clickdimensions/crm.png)  

Skopiuj token usługi Power BI z pozycji Ustawienia usługi ClickDimensions i wklej go w polu Hasło. Token usługi Power BI można znaleźć w pozycji Ustawienia CRM \> Ustawienia usługi ClickDimensions.  

![](media/service-connect-to-clickdimensions/crm2.png)  

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)

