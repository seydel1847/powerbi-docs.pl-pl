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
ms.custom: ''
ms.date: 12/17/2018
ms.openlocfilehash: c17f9b9841335420db67abb62c92603bf804f275
ms.sourcegitcommit: 13fdc8d62960f20c6d9ca1ab292f98992b47083b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/18/2018
ms.locfileid: "53553909"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Często zadawane pytania dotyczące wizualizacji niestandardowych usługi Power BI

## <a name="organizational-custom-visuals"></a>Wizualizacje niestandardowe organizacji

### <a name="how-can-the-admin-manage-the-organizational-custom-visuals"></a>Jak administrator może zarządzać wizualizacjami niestandardowymi organizacji?

W portalu administracyjnym na karcie „Wizualizacje niestandardowe organizacji” administrator może zapoznać się z i [zarządzać wszystkimi wizualizacjami niestandardowymi organizacji w przedsiębiorstwie](https://docs.microsoft.com/power-bi/service-admin-portal#organization-visuals): dodawać, wyłączać, włączać i usuwać te wizualizacje.
Nie trzeba już udostępniać tych wizualizacji w wiadomościach e-mail lub w folderze udostępnionym. Po wdrożeniu w repozytorium organizacji użytkownicy mogą łatwo znajdywać wizualizacje niestandardowe organizacji i importować je do swoich raportów bezpośrednio w usłudze lub programie Power BI Desktop. Wizualizacje niestandardowe organizacji można znaleźć we wbudowanym magazynie (w programie Desktop i usłudze) na karcie *MOJA ORGANIZACJA*. Gdy administrator przekazuje nową wersję wizualizacji niestandardowej organizacji, wszyscy użytkownicy w organizacji otrzymują tę samą zaktualizowaną wersję. Autorzy raportów nie muszą usuwać wizualizacji w raportach, aby uzyskać nową wersję tych wizualizacji, ponieważ wszystkie raporty używające tych wizualizacji są aktualizowane automatycznie. Mechanizm aktualizacji jest podobny do wizualizacji platformy handlowej.

### <a name="if-an-admin-uploads-a-custom-visual-from-the-public-marketplace-to-the-organization-store-is-it-automatically-updated-once-a-vendor-updates-the-visual-in-the-public-marketplace"></a>Czy jeśli administrator przekazuje wizualizację niestandardową z publicznej platformy handlowej do magazynu organizacji, jest ona automatycznie aktualizowana, gdy dostawca zaktualizuje tę wizualizację na publicznej platformie handlowej?

Nie, nie ma automatycznej aktualizacji z publicznej platformy handlowej.
Administrator ponosi odpowiedzialność za aktualizowanie wersji wizualizacji niestandardowych organizacji.

### <a name="is-there-a-way-to-disable-the-organizational-store"></a>Czy istnieje sposób wyłączenia magazynu organizacji?

Nie, użytkownicy zawsze widzą kartę „MOJA ORGANIZACJA” w usłudze i programie Power BI Desktop. Administrator może wyłączyć lub usunąć wszystkie wizualizacje niestandardowe organizacji z portalu administracyjnego i magazyn organizacji będzie pusty.
  
### <a name="if-the-administrator-disables-custom-visuals-from-the-admin-portal-tenant-settings-do-users-still-have-access-to-the-organizational-custom-visuals"></a>Czy jeśli administrator wyłączy wizualizacje niestandardowe z poziomu portalu administracyjnego (ustawień dzierżawy), użytkownicy będą nadal mieć dostęp do wizualizacji niestandardowych organizacji?

Tak, jeśli administrator wyłączy wizualizacje niestandardowe w portalu administracyjnym, nie wpłynie to na magazyn organizacji. Niektóre organizacje wyłączają wizualizacje niestandardowe i włączają tylko wybrane ręcznie wizualizacje, które zostały zaimportowane i przekazane przez administratora usługi Power BI do magazynu organizacji. Wyłączanie wizualizacji niestandardowych z portalu administracyjnego nie jest wymuszane w programie Power BI Desktop. Użytkownicy programu Desktop mogą nadal dodawać i wykorzystywać wizualizacje niestandardowe z publicznej platformy handlowej w swoich raportach. Renderowanie tych publicznych wizualizacji niestandardowych jest jednak zatrzymywane po opublikowaniu ich w usłudze Power BI. Jest również wyświetlany odpowiedni komunikat o błędzie. W przypadku korzystania z usługi Power BI nie można importować wizualizacji niestandardowych z publicznej platformy handlowej. Tylko wizualizacje z magazynu organizacji mogą być importowane, ponieważ ustawienie wizualizacji niestandardowych w portalu administracyjnym jest wymuszane w usłudze Power BI.

### <a name="why-does-the-organizational-store-and-organizational-custom-visuals-make-a-great-enterprise-solution"></a>Dlaczego magazyn organizacji i wizualizacje niestandardowe organizacji stanowią doskonałe rozwiązanie dla przedsiębiorstwa?

* Wszyscy użytkownicy otrzymują tę samą wersję wizualizacji, która jest kontrolowana przez administratora usługi Power BI. Gdy administrator aktualizuje wersję wizualizacji w portalu administracyjnym, wszyscy użytkownicy w organizacji automatycznie otrzymują zaktualizowaną wersję.

* Nie trzeba już udostępniać plików wizualizacji w wiadomościach e-mail ani folderach udostępnionych. Jedno miejsce widoczne dla wszystkich zalogowanych użytkowników.

* Bezpieczeństwo i możliwość obsługi — nowe wersje wizualizacji niestandardowych organizacji są automatycznie aktualizowane we wszystkich raportach, podobnie jak wizualizacje platformy handlowej.

* Użytkownicy w organizacji korzystający z wizualizacji niestandardowych organizacji muszą się zalogować, aby przeglądać wizualizacje niestandardowe organizacji i z nich korzystać. To rozwiązanie stanowi element zabezpieczeń w organizacji.

* Administratorzy mogą kontrolować, które wizualizacje niestandardowe mają być dostępne w organizacji.

* Administratorzy mogą włączać i wyłączać wizualizacje na potrzeby testowania w portalu administracyjnym. Zwiększa to bezpieczeństwo, ponieważ tylko członkowie organizacji będą mieli zezwolenie na korzystanie z tych wizualizacji.

## <a name="certified-custom-visuals"></a>Certyfikowane wizualizacje niestandardowe

### <a name="what-are-certified-custom-visuals"></a>Co to są certyfikowane wizualizacje niestandardowe?

Certyfikowane wizualizacje niestandardowe to wizualizacje na [platformie handlowej](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals), które spełniają pewne [określone](power-bi-custom-visuals-certified.md) wymagania dotyczące kodu i warunki testowania przez zespół usługi Power BI.  Wykonywane testy mają na celu sprawdzenie, czy wizualizacja nie korzysta z usług ani zasobów zewnętrznych. Jednak firma Microsoft nie jest autorem wizualizacji niestandardowych tworzonych przez inne firmy. Zalecamy użytkownikom bezpośredni kontakt z autorami w celu zweryfikowania funkcjonalności takich wizualizacji.

## <a name="visuals-with-additional-purchases"></a>Wizualizacje z dodatkowymi zakupami

### <a name="what-is-a-visual-with-additional-purchases"></a>Co to jest wizualizacja z dodatkowymi zakupami?

Wizualizacje z dodatkowymi zakupami są podobne do dodatków Zakupy w aplikacji (IAP) na platformie handlowej. Te dodatki mają tag ceny  **Może być konieczny dodatkowy zakup**.

Wizualizacje niestandardowe IAP to bezpłatne, możliwe do pobrania wizualizacje niestandardowe. Użytkownicy nie płacą za możliwość pobrania tych wizualizacji niestandardowych z platformy handlowej. Wizualizacje IAP oferują opcjonalne zakupy w aplikacji zaawansowanych funkcji.  

### <a name="whats-the-benefit-to-developers"></a>Jakie są korzyści dla deweloperów?

Wizualizacje niestandardowe IAP w usłudze AppSource będą mogły być wykrywane przez wiele odwiedzających osób, generując cenny ruch i zwiększając świadomość istnienia Twoich wizualizacji niestandardowych IAP oraz Ciebie jako dewelopera.

Jeśli do tej pory te wizualizacje były zarządzane za pośrednictwem witryny internetowej, teraz możesz przekazać je do usługi AppSource. Spowoduje to zwiększenie możliwości odnajdywania i poziomu widoczności wizualizacji IAP w społeczności usługi Power BI.

Jeśli wizualizacje są przechowywane w usłudze AppSource, klienci, którzy korzystają z wizualizacji niestandardowych IAP, mogą za pośrednictwem bezpośredniego kanału przesyłania opinii oceniać je za pomocą przeglądów i systemu klasyfikacji w sklepie.  

Wizualizacje IAP zatwierdzone przez zespół weryfikacyjny usługi AppSource można również przekazywać do certyfikacji. Jest to proces opcjonalny.  

Certyfikowane wizualizacje niestandardowe IAP mogą być eksportowane do programu PowerPoint i wyświetlane w otrzymywanych wiadomościach e-mail, jeśli użytkownik subskrybuje strony raportu. Więc już dziś wizualizacje niestandardowe IAP przesłane na platformę handlową mogą być również certyfikowane i mogą obsługiwać zestaw dodatkowych funkcji.  

### <a name="do-iap-visuals-need-to-be-certified"></a>Czy wizualizacje IAP muszą być certyfikowane?

Proces certyfikacji jest opcjonalny. To deweloper decyduje, czy jego wizualizacje niestandardowe IAP powinny być certyfikowane, podobnie jak wizualizacje bezpłatne.

### <a name="what-is-changing-in-the-submission-process"></a>Co ulega zmianie w procesie przesyłania?

Proces przesyłania wizualizacji niestandardowych IAP na platformę handlową jest taki sam jak w przypadku wizualizacji bezpłatnych. Odbywa się on za pośrednictwem pulpitu nawigacyjnego sprzedawcy.  Jedyna różnica w procesie przesyłania polega na tym, że deweloperzy muszą umieścić następującą informację w uwagach dla deweloperów na pulpicie nawigacyjnym sprzedawcy: „Visual with in-app purchase” (Wizualizacja z zakupami w aplikacji). Konieczne będzie również podanie klucza/tokenu licencji, jeśli zajdzie potrzeba sprawdzenia poprawności funkcji płatnych/zaawansowanych.  

Na pulpicie nawigacyjnym sprzedawcy nie pojawi się nowa opcja: *bezpłatne z zakupami w aplikacji*. Wizualizacje IAP będzie trzeba przesyłać jako *bezpłatne*.

Ponadto należy poinformować użytkowników, czego mogą oczekiwać, udostępniając w sklepie szczegółowe wyjaśnienie, które funkcje są bezpłatne, a które do działania wymagają dodatkowych zakupów.  

### <a name="what-should-i-do-beforesubmittingmy-iap-custom-visual"></a>Co należy zrobić przed przesłaniem wizualizacji niestandardowej IAP?

Jeśli pracujesz nad wizualizacją niestandardową IAP lub już ją masz, upewnij się, że jest ona zgodna z wytycznymi.  

Jeśli masz logo w wizualizacji niestandardowej, upewnij się, że jest ono zgodne z wytycznymi dotyczącymi logo (kolor, lokalizacja, rozmiar i wyzwalanie akcji).

W wytycznych można również znaleźć uwagi dotyczące najlepszych rozwiązań.  

### <a name="can-i-get-my-iap-custom-visual-certified"></a>Czy mogę certyfikować moją wizualizację niestandardową IAP?

Tak, podobnie jak wizualizacje bezpłatne.  Po zatwierdzeniu wizualizacji niestandardowej IAP przez zespół usługi AppSource możesz przesłać swoją wizualizację do certyfikacji.

Aby wizualizacja mogła być certyfikowana, powinna być zgodna z wymaganiami dotyczącymi certyfikacji. Wizualizacja nie może na przykład uzyskiwać dostępu do usług zewnętrznych w celu przeprowadzenie weryfikacji licencji.

Unieważnienie certyfikacji to proces opcjonalny. To Ty decydujesz, czy wizualizacja IAP ma być certyfikowana.

## <a name="additional-questions"></a>Dodatkowe pytania

### <a name="how-to-get-support"></a>Jak mogę uzyskać pomoc techniczną?

Jeśli masz jakieś pytania, uwagi lub problemy, możesz skontaktować się z zespołem pomocy technicznej wizualizacji niestandardowych: *pbicvsupport@microsoft.com* .  

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji, odwiedź stronę [Rozwiązywanie problemów z wizualizacjami niestandardowymi usługi Power BI](power-bi-custom-visuals-troubleshoot.md).
