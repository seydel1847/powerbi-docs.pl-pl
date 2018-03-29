---
title: Rozwiązywanie problemów ze źródłem danych, którego odświeżanie nie jest obsługiwane
description: Rozwiązywanie problemów ze źródłem danych, którego odświeżanie nie jest obsługiwane
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: d09d75350cbffbab78c1a44252f18d2216c2505f
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
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

