---
title: "Informacje na temat zabezpieczeń na poziomie wiersza w programie Power BI Desktop"
description: "Jak skonfigurować zabezpieczenia na poziomie wiersza dla zaimportowanych zestawów danych oraz zapytanie bezpośrednie w programie Power BI Desktop."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: maghan
ms.openlocfilehash: fccb2094158ed2dffaa0a80cc5609dfbf382be30
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2018
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Zabezpieczenia na poziomie wiersza w programie Power BI Desktop
Zabezpieczenia na poziomie wiersza w programie Power BI Desktop mogą służyć do ograniczania dostępu do danych do konkretnych użytkowników. Filtry ograniczają dane na poziomie wiersza. Filtry można zdefiniować w ramach ról.

Teraz można skonfigurować zabezpieczenia na poziomie wiersza dla modeli danych importowanych do usługi Power BI za pomocą programu Power BI Desktop. Można również skonfigurować zabezpieczenia na poziomie wiersza w zestawach danych, które korzystają z zapytań bezpośrednich, takich jak program SQL Server. Wcześniej można było implementować zabezpieczenia na poziomie wiersza tylko w ramach modeli usług Analysis Services poza usługą Power BI. Dla połączeń na żywo usług Analysis Services zabezpieczenia na poziomie wiersza są konfigurowane w modelu lokalnym. Opcja zabezpieczeń nie będzie widoczna dla zestawów danych połączenia na żywo.

> [!IMPORTANT]
> Jeśli w usłudze Power BI zdefiniowano role/reguły, należy ponownie utworzyć te role w programie Power BI Desktop i opublikować raport w usłudze.
> 
> 

Dowiedz się więcej o opcjach [zabezpieczeń na poziomie wiersza w usłudze Power BI](service-admin-rls.md).

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Następne kroki
[Row-level security (RLS) with the Power BI service (Zabezpieczenia na poziomie wiersza w usłudze Power BI)](service-admin-rls.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

