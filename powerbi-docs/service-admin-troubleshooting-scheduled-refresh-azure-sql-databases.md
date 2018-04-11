---
title: Rozwiązywanie problemów z zaplanowanym odświeżaniem baz danych Azure SQL Database
description: Rozwiązywanie problemów z zaplanowanym odświeżaniem baz danych Azure SQL Database w usłudze Power BI
services: powerbi
documentationcenter: ''
author: mgblythe
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
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 6fc118a2f809f06f1bdd61984d100ebece516baa
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/08/2018
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Rozwiązywanie problemów z zaplanowanym odświeżaniem baz danych Azure SQL Database w usłudze Power BI
Aby uzyskać szczegółowe instrukcje dotyczące konfigurowania zaplanowanego odświeżania, zobacz [Odświeżanie danych w usłudze Power BI](refresh-data.md).

Jeśli konfigurujesz zaplanowane odświeżanie bazy danych Azure SQL Database i w trakcie tego procesu wystąpi błąd z kodem 400 podczas edytowania poświadczeń, spróbuj wykonać następujące czynności, aby skonfigurować odpowiednią regułę zapory:

1. Zaloguj się do portalu zarządzania platformy Azure
2. Przejdź do serwera Azure SQL, dla którego konfigurujesz odświeżanie
3. W sekcji usług dozwolonych włącz opcję „Usługi platformy Microsoft Azure”

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

