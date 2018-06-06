---
title: Jak administratorzy mogą zarządzać formularzem logowania programu Power BI Desktop
description: Dowiedz się, jak można zarządzać początkowym formularzem logowania podczas otwierania programu Power BI Desktop.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/02/2018
ms.author: davidi
ms.openlocfilehash: f35553acd65aeea2c1bf02b04fcbd665af4b99ea
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721092"
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

