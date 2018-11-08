---
title: Często zadawane pytania dotyczące wizualizacji niestandardowych usługi Power BI
description: Zapoznaj się z listą często zadawanych pytań i odpowiedzi dotyczących wizualizacji niestandardowych usługi Power BI
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 10/29/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: 064d32944f52f6e391d4a7ec4df41ecbf09b7e3f
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223081"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Często zadawane pytania dotyczące wizualizacji niestandardowych usługi Power BI

## <a name="organizational-custom-visuals"></a>Wizualizacje niestandardowe organizacji

**Jak administrator może zarządzać wizualizacjami niestandardowymi organizacji?**

W portalu administracyjnym na karcie „Wizualizacje niestandardowe organizacji” administrator może zapoznać się z i [zarządzać wszystkimi wizualizacjami niestandardowymi organizacji w przedsiębiorstwie](https://docs.microsoft.com/power-bi/service-admin-portal#organization-visuals): dodawać, wyłączać, włączać i usuwać te wizualizacje.
Nie trzeba już udostępniać tych wizualizacji w wiadomościach e-mail lub w folderze udostępnionym. Po wdrożeniu w repozytorium organizacji użytkownicy mogą łatwo odnajdywać i importować wizualizacje niestandardowe organizacji do swoich raportów bezpośrednio w usłudze lub programie Power BI Desktop. Wizualizacje niestandardowe organizacji można znaleźć we wbudowanym magazynie (w programie Desktop i usłudze) na karcie „MOJA ORGANIZACJA”. Gdy administrator przekazuje nową wersję wizualizacji niestandardowej organizacji, wszyscy użytkownicy w organizacji otrzymują tę samą zaktualizowaną wersję. Autorzy raportów nie muszą usuwać wizualizacji w raportach, aby uzyskać nową wersję tych wizualizacji, ponieważ wszystkie raporty używające tych wizualizacji są aktualizowane automatycznie. Mechanizm aktualizacji jest podobny do wizualizacji platformy handlowej.

**Czy jeśli administrator przekazuje wizualizację niestandardową z publicznej platformy handlowej do magazynu organizacji, jest ona automatycznie aktualizowana, gdy dostawca zaktualizuje tę wizualizację na publicznej platformie handlowej?**

Nie, nie ma automatycznej aktualizacji z publicznej platformy handlowej.
Administrator ponosi odpowiedzialność za aktualizowanie wersji wizualizacji niestandardowych organizacji, jeśli jest to konieczne.

**Czy istnieje sposób wyłączenia magazynu organizacji?**

Nie, użytkownicy zawsze widzą kartę „MOJA ORGANIZACJA” w usłudze i programie Power BI Desktop. Administrator może wyłączyć lub usunąć wszystkie wizualizacje niestandardowe organizacji z portalu administracyjnego i magazyn organizacji będzie pusty.
  
**Czy jeśli administrator wyłączy wizualizacje niestandardowe z poziomu portalu administracyjnego (ustawień dzierżawy), użytkownicy będą nadal mieć dostęp do wizualizacji niestandardowych organizacji?**

Tak, jeśli administrator wyłączy wizualizacje niestandardowe w portalu administracyjnym, nie wpłynie to na magazyn organizacji. Niektóre organizacje wyłączają wizualizacje niestandardowe i włączają tylko wybrane ręcznie wizualizacje, które zostały zaimportowane i przekazane przez administratora usługi Power BI do magazynu organizacji. Wyłączanie wizualizacji niestandardowych z portalu administracyjnego nie jest wymuszane w programie Power BI Desktop. Użytkownicy programu Desktop mogą nadal dodawać i wykorzystywać wizualizacje niestandardowe z publicznej platformy handlowej w swoich raportach. Renderowanie tych publicznych wizualizacji niestandardowych jest jednak zatrzymywane po opublikowaniu ich w usłudze Power BI. Jest również wyświetlany odpowiedni komunikat o błędzie. W przypadku korzystania z usługi Power BI nie można importować wizualizacji niestandardowych z publicznej platformy handlowej. Tylko wizualizacje z magazynu organizacji mogą być importowane, ponieważ ustawienie wizualizacji niestandardowych w portalu administracyjnym jest wymuszane w usłudze Power BI.

**Dlaczego magazyn organizacji i wizualizacje niestandardowe organizacji stanowią doskonałe rozwiązanie dla przedsiębiorstwa?**

* Wszyscy użytkownicy otrzymują tę samą wersję wizualizacji, która jest kontrolowana przez administratora usługi Power BI. Gdy administrator aktualizuje wersję wizualizacji w portalu administracyjnym, wszyscy użytkownicy w organizacji automatycznie otrzymują zaktualizowaną wersję.

* Nie trzeba już udostępniać plików wizualizacji w wiadomościach e-mail ani folderach udostępnionych. Jedno miejsce widoczne dla wszystkich zalogowanych użytkowników.

* Bezpieczeństwo i możliwość obsługi — nowe wersje wizualizacji niestandardowych organizacji są automatycznie aktualizowane we wszystkich raportach, podobnie jak wizualizacje platformy handlowej.

* Użytkownicy w organizacji korzystający z wizualizacji niestandardowych organizacji muszą się zalogować, aby przeglądać wizualizacje niestandardowe organizacji i z nich korzystać. To rozwiązanie stanowi element zabezpieczeń w organizacji.

* Administratorzy mogą kontrolować, które wizualizacje niestandardowe mają być dostępne w organizacji.

* Administratorzy mogą włączać i wyłączać wizualizacje na potrzeby testowania w portalu administracyjnym. Zwiększa to bezpieczeństwo, ponieważ tylko członkowie organizacji będą mieli zezwolenie na korzystanie z tych wizualizacji.

## <a name="certified-custom-visuals"></a>Certyfikowane wizualizacje niestandardowe

**Co to są certyfikowane wizualizacje niestandardowe?**

Certyfikowane wizualizacje niestandardowe to wizualizacje na [platformie handlowej](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals), które spełniają pewne [określone](power-bi-custom-visuals-certified.md) wymagania dotyczące kodu i warunki testowania przez zespół usługi Power BI.  Wykonywane testy mają na celu sprawdzenie, czy wizualizacja nie ma dostępu do zewnętrznych usług lub zasobów. Firma Microsoft nie jest autorem zewnętrznych wizualizacji niestandardowych, dlatego zalecamy klientom bezpośrednie skontaktowanie się z autorem w celu sprawdzenia funkcjonalności takiej wizualizacji.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać informacje dotyczące rozwiązywania problemów, odwiedź stronę [Rozwiązywanie problemów z wizualizacjami niestandardowymi usługi Power BI](power-bi-custom-visuals-troubleshoot.md).
