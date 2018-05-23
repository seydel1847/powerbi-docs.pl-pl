---
title: Rozwiązywanie problemów ze źródłem danych, którego odświeżanie nie jest obsługiwane
description: Rozwiązywanie problemów ze źródłem danych, którego odświeżanie nie jest obsługiwane
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 9ea17fd80c928ee0193ca94aac88fa00f362a523
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>Rozwiązywanie problemów ze źródłem danych, którego odświeżanie nie jest obsługiwane
Podczas próby konfigurowania zaplanowanego odświeżania zestawu danych może zostać wyświetlony błąd.

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

Dzieje się tak, jeśli odświeżanie źródła danych używanego w programie Power BI Desktop nie jest obsługiwane. Musisz ustalić, czy używane źródło danych znajduje się na liście obsługiwanych źródeł danych zawartej w artykule [Odświeżanie danych w usłudze Power BI](refresh-data.md). 

## <a name="find-the-data-source"></a>Znajdowanie źródła danych
Jeśli nie masz pewności, jakie źródło danych jest używane, możesz to sprawdzić za pomocą poniższych kroków w programie Power BI Desktop.  

1. W programie Power BI Desktop przejdź do okienka **Raport**.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. Wybierz pozycję **Edytuj zapytania** na wstążce.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. Wybierz pozycję **Edytor zaawansowany**.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. Zanotuj nazwę dostawcy źródła.  W tym przykładzie dostawca to ActiveDirectory.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. Sprawdź, czy dostawca znajduje się na liście obsługiwanych źródeł danych w artykule [Odświeżanie danych w usłudze Power BI](refresh-data.md).  Zobaczysz, że odświeżanie źródła danych Active Directory nie jest obsługiwane.  

## <a name="next-steps"></a>Następne kroki
[Odświeżanie danych](refresh-data.md)  
[Power BI Gateway — Personal](personal-gateway.md)  
[Lokalna brama danych](service-gateway-onprem.md)  
[Rozwiązywanie problemów z lokalną bramą danych](service-gateway-onprem-tshoot.md)  
[Rozwiązywanie problemów z bramą Power BI Gateway — Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

