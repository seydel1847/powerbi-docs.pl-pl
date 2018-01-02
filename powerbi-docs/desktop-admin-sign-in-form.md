---
title: "Jak administratorzy mogą zarządzać formularzem logowania programu Power BI Desktop"
description: "Dowiedz się, jak można zarządzać początkowym formularzem logowania podczas otwierania programu Power BI Desktop."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/17/2017
ms.author: davidi
ms.openlocfilehash: eabb59b32234fce1ba5669b95abb41c4f7e04aa2
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Jak administratorzy mogą zarządzać formularzem logowania programu Power BI Desktop
Podczas pierwszego uruchomienia programu Power BI Desktop zostaje wyświetlony formularz logowania. Można uzupełnić informacje lub zalogować się do usługi Power BI, aby kontynuować. Administratorzy mogą zarządzać tym formularzem przy użyciu klucza rejestru. 

![Początkowy formularz logowania programu Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

Administratorzy mogą używać następującego klucza rejestru w celu wyłączenia formularza logowania. Rozwiązanie to może również zostać zastosowane względem całej organizacji przy użyciu zasad globalnych.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

Wartość 0 spowoduje wyłączenie okna dialogowego.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

