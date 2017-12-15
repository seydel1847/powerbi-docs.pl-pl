---
title: "Zabezpieczenia na poziomie wiersza w usłudze Power BI"
description: "Jak skonfigurować zabezpieczenia na poziomie wiersza dla zaimportowanych zestawów danych oraz zapytanie bezpośrednie w usłudze Power BI."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/29/2017
ms.author: asaxton
ms.openlocfilehash: 338921df57b77b1e79f9b71e814203734ab5971c
ms.sourcegitcommit: 7742f952c20695dfb475f74965c0065b02c01521
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/29/2017
---
# <a name="row-level-security-rls-with-power-bi"></a>Zabezpieczenia na poziomie wiersza w usłudze Power BI
<iframe width="560" height="315" src="https://www.youtube.com/embed/67fK0GoVQ80?showinfo=0" frameborder="0" allowfullscreen></iframe>

Zabezpieczenia na poziomie wiersza w usłudze Power BI mogą służyć do ograniczania dostępu do danych do konkretnych użytkowników. Filtry ograniczają dane na poziomie wiersza. Filtry można zdefiniować w ramach ról.

Można skonfigurować zabezpieczenia na poziomie wiersza dla modeli danych importowanych do usługi Power BI za pomocą programu Power BI Desktop. Można również skonfigurować zabezpieczenia na poziomie wiersza w zestawach danych, które korzystają z zapytań bezpośrednich, takich jak program SQL Server. Wcześniej można było implementować zabezpieczenia na poziomie wiersza tylko w ramach modeli usług Analysis Services poza usługą Power BI. Dla połączeń na żywo usług Analysis Services zabezpieczenia na poziomie wiersza są konfigurowane w modelu lokalnym. Opcja zabezpieczeń nie będzie widoczna dla zestawów danych w połączeniach na żywo.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

## <a name="manage-security-on-your-model"></a>Zarządzanie zabezpieczeniami modelu
Aby zarządzać zabezpieczeniami modelu danych, należy wykonać następujące czynności.

1. Wybierz **wielokropek (…)** dla zestawu danych.
2. Wybierz pozycję **Zabezpieczenia**.
   
   ![](media/service-admin-rls/rls-security.png)

Spowoduje to przejście do strony zabezpieczeń na poziomie wiersza, która umożliwia dodawanie członków do roli utworzonej w programie Power BI Desktop. Opcja Zabezpieczenia jest widoczna tylko dla właścicieli zestawu danych. Jeśli zestaw danych należy do grupy, opcja Zabezpieczenia będzie widoczna tylko dla administratorów tej grupy. 

Tworzenie i modyfikowanie ról jest możliwe tylko w programie Power BI Desktop.

## <a name="working-with-members"></a>Praca z członkami
### <a name="add-members"></a>Dodawanie członków
Można dodać członka do roli, wpisując adres e-mail lub nazwę użytkownika, grupy zabezpieczeń lub listy dystrybucyjnej, która ma zostać dodana. Ten członek musi należeć do organizacji. Nie można dodawać grup utworzonych w usłudze Power BI.

![](media/service-admin-rls/rls-add-member.png)

Liczba w nawiasach obok nazwy roli lub obok obszaru Członkowie informuje to tym, ilu członków jest przypisanych do roli.

![](media/service-admin-rls/rls-member-count.png)

### <a name="remove-members"></a>Usuwanie członków
Członków można usuwać, wybierając znak X obok ich nazwy. 

![](media/service-admin-rls/rls-remove-member.png)

## <a name="validating-the-role-within-the-power-bi-service"></a>Sprawdzanie poprawności roli w usłudze Power BI
Można zweryfikować, czy zdefiniowana rola działa prawidłowo, testując tę rolę. 

1. Wybierz **wielokropek (...)** obok roli.
2. Wybierz pozycję **Testuj dane jako rola**.

![](media/service-admin-rls/rls-test-role.png)

Zostaną wyświetlone raporty dostępne dla tej roli. Pulpity nawigacyjne nie są wyświetlane w tym widoku. Na niebieskim pasku powyżej będą widoczne zastosowane role.

![](media/service-admin-rls/rls-test-role2.png)

Można testować inne role lub kombinację ról, wybierając pozycję **Wyświetlane jako**.

![](media/service-admin-rls/rls-test-role3.png)

Można wybrać, aby wyświetlić dane jako określona osoba, lub wybrać kombinację dostępnych ról, aby sprawdzić poprawność ich działania. 

Aby powrócić do normalnego widoku, wybierz pozycję **Wróć do zabezpieczeń na poziomie wiersza**.

[!INCLUDE [include-short-name](./includes/rls-usernames.md)]

## <a name="using-rls-with-app-workspaces-in-power-bi"></a>Używanie zabezpieczeń na poziomie wiersza z obszarami roboczymi aplikacji w usłudze Power BI
Jeśli opublikujesz raport programu Power BI Desktop w obszarze roboczym aplikacji w usłudze Power BI, role będą stosowane do członków tylko do odczytu. W ustawieniach obszaru roboczego aplikacji należy wskazać, że członkowie mogą tylko wyświetlać zawartość usługi Power BI.

> [!WARNING]
> Jeśli skonfigurowano obszar roboczy aplikacji tak, aby członkowie mieli uprawnienia do edycji, role zabezpieczeń na poziomie wiersza nie będą do nich stosowane. Użytkownicy będą mogli wyświetlać wszystkie dane.
> 
> 

![](media/service-admin-rls/rls-group-settings.png)

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Następne kroki
[Zabezpieczenia na poziomie wiersza w programie Power BI Desktop](desktop-rls.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

