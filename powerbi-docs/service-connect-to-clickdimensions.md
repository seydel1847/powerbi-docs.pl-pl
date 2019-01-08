---
title: Łączenie się z pakietem zawartości ClickDimensions za pomocą usługi Power BI
description: Pakiet zawartości ClickDimensions dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e7db66dfb79cd0348967369d92e7b13c698d8f71
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007857"
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

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

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

