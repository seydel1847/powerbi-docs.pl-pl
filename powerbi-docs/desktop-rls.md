---
title: Informacje na temat zabezpieczeń na poziomie wiersza w programie Power BI Desktop
description: Jak skonfigurować zabezpieczenia na poziomie wiersza dla zaimportowanych zestawów danych oraz zapytanie bezpośrednie w programie Power BI Desktop.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/03/2018
ms.author: maghan
LocalizationGroup: Create reports
ms.openlocfilehash: 022668737f6bcce987b2923ba7a4416f4a08460a
ms.sourcegitcommit: 001ea0ef95fdd4382602bfdae74c686de7dc3bd8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2018
ms.locfileid: "38875993"
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Zabezpieczenia na poziomie wiersza w programie Power BI Desktop
Zabezpieczenia na poziomie wiersza w programie Power BI Desktop ograniczają dostęp do danych do konkretnych użytkowników. Filtry ograniczają dane na poziomie wiersza. Filtry można zdefiniować w ramach ról.

Teraz można skonfigurować zabezpieczenia na poziomie wiersza dla modeli danych importowanych do usługi Power BI za pomocą programu Power BI Desktop. Można również skonfigurować zabezpieczenia na poziomie wiersza w zestawach danych, które korzystają z zapytań bezpośrednich, takich jak program SQL Server. Wcześniej można było implementować zabezpieczenia na poziomie wiersza tylko w ramach modeli usług Analysis Services poza usługą Power BI. Dla połączeń na żywo usług Analysis Services zabezpieczenia na poziomie wiersza są konfigurowane w modelu lokalnym. Opcja zabezpieczeń nie jest widoczna dla zestawów danych w połączeniach na żywo.

> [!IMPORTANT]
> Jeśli w usłudze Power BI zdefiniowano role i reguły, należy ponownie utworzyć te role w programie Power BI Desktop i opublikować raport w usłudze.
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

