---
title: "Łączenie się z usługą Project Online przy użyciu usługi Power BI"
description: "Pakiet zawartości Project Online dla usługi Power BI"
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
ms.openlocfilehash: 509b75d91611de827b236e45dc25ef893aff8177
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-project-online-with-power-bi"></a>Łączenie się z usługą Project Online przy użyciu usługi Power BI
Microsoft Project Online to elastyczne rozwiązanie online do zarządzania portfelem projektów (PPM) i codziennej pracy. Usługa Project Online pozwala organizacjom rozpocząć pracę, ustalić priorytety inwestycji projektowych i dostarczyć zamierzoną wartość biznesową. Pakiet zawartości Project Online dla usługi Power BI umożliwia eksplorowanie danych projektu za pomocą gotowych metryk, takich jak status portfela i zgodność projektu.

Połącz się z [pakietem zawartości Project Online](https://app.powerbi.com/getdata/services/project-online) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
    ![](media/service-connect-to-project-online/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-project-online/services.png)
3. Wybierz pozycję **Microsoft Project Online** \> **Pobierz**.
   
   ![](media/service-connect-to-project-online/mproject.png)
4. W polu tekstowym **Adres URL aplikacji Project Web App** wprowadź adres URL programu Project Web Add (PWA), z którym chcesz nawiązać połączenie i naciśnij przycisk **Dalej**. Należy pamiętać, że adres może być inny niż w podanym przykładzie, jeśli masz domenę niestandardową.
   
    ![](media/service-connect-to-project-online/params.png)
5. Jako metodę uwierzytelniania wybierz opcję **oAuth2** \> **Zaloguj**. Po wyświetleniu monitu wprowadź swoje poświadczenia usługi Project Online i postępuj zgodnie z procesem uwierzytelniania.
   
    ![](media/service-connect-to-project-online/creds.png)
6. Zostanie wyświetlone powiadomienie informujące, że trwa ładowanie danych. Proces ten może zająć trochę czasu w zależności od konta. Po zaimportowaniu danych przez usługę Power BI zobaczysz nowy pulpit nawigacyjny, raport i zestaw danych w okienku nawigacji po lewej stronie. Jest to domyślny pulpit nawigacyjny utworzony przez usługę Power BI do wyświetlania Twoich danych. Możesz modyfikować pulpit nawigacyjny, aby wyświetlać dane w dowolny sposób.
   
   ![](media/service-connect-to-project-online/dashboard2.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu Pytania i odpowiedzi](service-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)
