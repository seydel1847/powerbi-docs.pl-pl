---
title: Łączenie się z dziennikami inspekcji platformy Azure za pomocą usługi Power BI
description: Dzienniki inspekcji platformy Azure dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/06/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 4faaa63a3845125b4df1ec634d22b084b5ae25f2
ms.sourcegitcommit: 60fb46b61ac73806987847d9c606993c0e14fb30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2018
ms.locfileid: "50101214"
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

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="system-requirements"></a>Wymagania systemowe
Pakiet zawartości dzienników inspekcji platformy Azure wymaga dostępu do dzienników inspekcji w witrynie Azure Portal. Więcej szczegółów można znaleźć [tutaj](/azure/azure-resource-manager/resource-group-audit/).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Istnieją dwa sposoby na proste odnalezienie identyfikatora subskrypcji.

1. Z witryny https://portal.azure.com -&gt; Przeglądaj -&gt; Subskrypcje -&gt; Identyfikator subskrypcji
2. Z witryny https://manage.windowsazure.com -&gt; Ustawienia -&gt; Identyfikator subskrypcji

Identyfikator subskrypcji będzie długim zestawem cyfr i znaków, podobnym do przykładu w kroku \#4 powyżej. 

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Jeśli występuje błąd poświadczeń lub błąd podczas próby odświeżania z powodu nieprawidłowych poświadczeń, spróbuj usunąć wszystkie wystąpienia pakietu zawartości dzienników inspekcji platformy Azure i połączyć się ponownie.

## <a name="next-steps"></a>Następne kroki
[Co to jest usługa Power BI?](power-bi-overview.md)  
[Power BI — podstawowe pojęcia](consumer/end-user-basic-concepts.md)  

