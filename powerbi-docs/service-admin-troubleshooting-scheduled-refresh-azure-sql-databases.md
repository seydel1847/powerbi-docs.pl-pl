---
title: Rozwiązywanie problemów z zaplanowanym odświeżaniem baz danych Azure SQL Database
description: Rozwiązywanie problemów z zaplanowanym odświeżaniem baz danych Azure SQL Database w usłudze Power BI
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 17ee932bf0331940c7b30b020ab8fc43cdc9fdf5
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54274684"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Rozwiązywanie problemów z zaplanowanym odświeżaniem baz danych Azure SQL Database w usłudze Power BI
Aby uzyskać szczegółowe instrukcje dotyczące konfigurowania zaplanowanego odświeżania, zobacz [Odświeżanie danych w usłudze Power BI](refresh-data.md).

Jeśli konfigurujesz zaplanowane odświeżanie bazy danych Azure SQL Database i w trakcie tego procesu wystąpi błąd z kodem 400 podczas edytowania poświadczeń, spróbuj wykonać następujące czynności, aby skonfigurować odpowiednią regułę zapory:

1. Zaloguj się do portalu zarządzania platformy Azure
2. Przejdź do serwera Azure SQL, dla którego konfigurujesz odświeżanie
3. W sekcji usług dozwolonych włącz opcję „Usługi platformy Microsoft Azure”

![Dozwolone usługi platformy Azure](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

