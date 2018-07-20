---
title: Rozwiązywanie problemów z zaplanowanym odświeżaniem baz danych Azure SQL Database
description: Rozwiązywanie problemów z zaplanowanym odświeżaniem baz danych Azure SQL Database w usłudze Power BI
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 9439ac6bd0b4df568b964f548372fb94d2fd0b26
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34238531"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Rozwiązywanie problemów z zaplanowanym odświeżaniem baz danych Azure SQL Database w usłudze Power BI
Aby uzyskać szczegółowe instrukcje dotyczące konfigurowania zaplanowanego odświeżania, zobacz [Odświeżanie danych w usłudze Power BI](refresh-data.md).

Jeśli konfigurujesz zaplanowane odświeżanie bazy danych Azure SQL Database i w trakcie tego procesu wystąpi błąd z kodem 400 podczas edytowania poświadczeń, spróbuj wykonać następujące czynności, aby skonfigurować odpowiednią regułę zapory:

1. Zaloguj się do portalu zarządzania platformy Azure
2. Przejdź do serwera Azure SQL, dla którego konfigurujesz odświeżanie
3. W sekcji usług dozwolonych włącz opcję „Usługi platformy Microsoft Azure”

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

