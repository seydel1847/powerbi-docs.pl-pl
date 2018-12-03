---
title: Jak administratorzy mogą zarządzać formularzem logowania programu Power BI Desktop
description: Dowiedz się, jak można zarządzać początkowym formularzem logowania podczas otwierania programu Power BI Desktop.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
ms.openlocfilehash: 3c92063c82c370bd59ecd7bfa2798ae60a3b425d
ms.sourcegitcommit: 05303d3e0454f5627eccaa25721b2e0bad2cc781
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/28/2018
ms.locfileid: "52578249"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Jak administratorzy mogą zarządzać formularzem logowania programu Power BI Desktop
Podczas pierwszego uruchomienia programu Power BI Desktop zostaje wyświetlony formularz logowania. Można uzupełnić informacje lub zalogować się do usługi Power BI, aby kontynuować. Administratorzy zarządzają tym formularzem przy użyciu klucza rejestru. 

![Początkowy formularz logowania programu Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

Administratorzy używają następującego klucza rejestru w celu wyłączenia formularza logowania. Można go również wypchnąć do całej organizacji przy użyciu zasad globalnych.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

Wartość 0 spowoduje wyłączenie okna dialogowego.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

