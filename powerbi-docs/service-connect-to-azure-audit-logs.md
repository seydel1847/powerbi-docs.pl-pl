---
title: "Łączenie się z dziennikami inspekcji platformy Azure za pomocą usługi Power BI"
description: "Dzienniki inspekcji platformy Azure dla usługi Power BI"
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
ms.openlocfilehash: cb52b8dc6aefc199ef09946bf8b58c98171c5aba
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-azure-audit-logs-with-power-bi"></a>Łączenie się z dziennikami inspekcji platformy Azure za pomocą usługi Power BI
Pakiet zawartości dzienników inspekcji platformy Azure pozwala analizować i wizualizować informacje przechowywane w dziennikach inspekcji. Usługa Power BI pobiera dane, tworzy gotowy do użycia pulpit nawigacyjny i raporty w oparciu o dane.

Połącz się z [pakietem zawartości dzienników inspekcji platformy Azure](https://app.powerbi.com/getdata/services/azure-audit-logs) lub przeczytaj więcej na temat [integracji dzienników inspekcji platformy Azure](https://powerbi.microsoft.com/integrations/azure-audit-logs) z usługą Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.  
   
    ![](media/service-connect-to-azure-audit-logs/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.  
   
    ![](media/service-connect-to-azure-audit-logs/services.png) 
3. Wybierz pozycję **Dzienniki inspekcji platformy Azure** > **Pobierz**.  
   
   ![](media/service-connect-to-azure-audit-logs/azureauditlogs.png)
4. Po wyświetleniu monitu wprowadź **identyfikator subskrypcji platformy Azure**. Poniżej znajdują się szczegółowe informacje dotyczące wyszukiwania [identyfikatora subskrypcji](#FindingParams).   
   
    ![](media/service-connect-to-azure-audit-logs/parameters.png)
5. W polu **Metoda uwierzytelniania** wybierz opcję **oAuth2** \> **Zaloguj**.
   
    ![](media/service-connect-to-azure-audit-logs/creds.png)
6. Wprowadź poświadczenia konta, aby dokończyć proces logowania.
   
    ![](media/service-connect-to-azure-audit-logs/login.png)
7. Usługa Power BI pobierze dane dziennika inspekcji platformy Azure i utworzy gotowy do użycia pulpit nawigacyjny i raport. 
   
    ![](media/service-connect-to-azure-audit-logs/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu Pytania i odpowiedzi](service-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="system-requirements"></a>Wymagania systemowe
Pakiet zawartości dzienników inspekcji platformy Azure wymaga dostępu do dzienników inspekcji w witrynie Azure Portal. Więcej szczegółów można znaleźć [tutaj](https://azure.microsoft.com/en-us/documentation/articles/insights-debugging-with-events/).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Istnieją dwa sposoby na proste odnalezienie identyfikatora subskrypcji.

1. Z witryny https://portal.azure.com —&gt; Przeglądaj —&gt; Subskrypcje —&gt; Identyfikator subskrypcji
2. Z witryny https://manage.windowsazure.com —&gt; Ustawienia —&gt; Identyfikator subskrypcji

Identyfikator subskrypcji będzie długim zestawem cyfr i znaków, podobnym do przykładu w kroku \#4 powyżej. 

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Jeśli występuje błąd poświadczeń lub błąd podczas próby odświeżania z powodu nieprawidłowych poświadczeń, spróbuj usunąć wszystkie wystąpienia pakietu zawartości dzienników inspekcji platformy Azure i połączyć się ponownie.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)  
[Power BI — podstawowe pojęcia](service-basic-concepts.md)  
