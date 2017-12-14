---
title: "Łączenie się z pakietem zawartości VMob przy użyciu usługi Power BI"
description: "Pakiet zawartości VMob dla usługi Power BI"
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
ms.openlocfilehash: fc0c8bc1ea177e20c25a614ed1de274f70056578
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-vmob-with-power-bi"></a>Łączenie się z pakietem zawartości VMob przy użyciu usługi Power BI
Przy użyciu usługi Power BI i pakietu zawartości VMob można łatwo śledzić i eksplorować dane w usłudze VMob. Usługa Power BI pobiera następujące dane: statystyki użytkowników dla wszystkich okresów łącznie i za ostatnie 30 dni, wskaźnik KPI dotyczący sprzedaży detalicznej za ostatnie 30 dni oraz wydajność kampanii za okres ostatnich 30 dni.

Połącz się z [pakietem zawartości VMob](https://app.powerbi.com/getdata/services/vmob) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
    ![](media/service-connect-to-vmob/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-vmob/services.png)
3. Wybierz pozycję **VMob** \> **Pobierz**.
   
   ![](media/service-connect-to-vmob/vmob.png)
4. Po wyświetleniu monitu podaj adres URL usługi VMob, a następnie kliknij przycisk Dalej. Ten adres URL jest dostarczany przez usługę VMob oddzielnie.
   
    ![](media/service-connect-to-vmob/params.png)
5. Z listy rozwijanej metod uwierzytelniania wybierz opcję **Podstawowa**, wprowadź nazwę użytkownika oraz hasło usługi VMob i kliknij przycisk **Zaloguj**.
   
    ![](media/service-connect-to-vmob/creds.png)
6. Proces importowania rozpocznie się automatycznie, a usługa Power BI pobierze dane usługi VMob, aby utworzyć gotowy do użycia pulpit nawigacyjny i raport.
   
   ![](media/service-connect-to-vmob/dashboard2.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu Pytania i odpowiedzi](service-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)

