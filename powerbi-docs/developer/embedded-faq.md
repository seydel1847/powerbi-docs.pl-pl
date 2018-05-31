---
title: Często zadawane pytania dotyczące usługi Power BI Embedded
description: Przeglądaj listę często zadawanych pytań i odpowiedzi dotyczących usługi Power BI Embedded.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/23/2018
ms.author: maghan
ms.openlocfilehash: f2d457c04f9db2bdd57f363ccb0c09e2496aefd6
ms.sourcegitcommit: 1c7780e0dfe0b6b8322e6fafdd0693177db455d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/14/2018
ms.locfileid: "34163327"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Często zadawane pytania dotyczące usługi Power BI Embedded

* Jeśli masz inne pytania, [zadaj je społeczności usługi Power BI](http://community.powerbi.com/).
* Nadal masz problem? Odwiedź [stronę pomocy technicznej usługi Power BI](https://powerbi.microsoft.com/support/).

## <a name="general"></a>Ogólne

### <a name="what-is-power-bi-embedded"></a>Co to jest usługa Power BI Embedded?

Usługa Microsoft Power BI Embedded umożliwia osadzanie niesamowitych, w pełni interaktywnych raportów, pulpitów nawigacyjnych i kafelków w aplikacjach bez potrzeby poświęcania czasu i pieniędzy na tworzenie wizualizacji danych i kontrolek od podstaw.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Kto jest docelowym odbiorcą usługi Power BI Embedded?

Deweloperzy i firmy programistyczne tworzące własne aplikacje nazywani niezależnymi dostawcami oprogramowania (ISV).

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Czym różnią się usługi Power BI Embedded i Power BI?

Usługa Power BI Embedded jest przeznaczona dla niezależnych dostawców oprogramowania lub deweloperów, którzy tworzą aplikacje i chcą w nich osadzać wizualizacje, aby pomóc klientom w podejmowaniu decyzji bez konieczności tworzenia rozwiązania do analizy od podstaw. Osadzona analiza zapewnia użytkownikom biznesowym dostęp do danych biznesowych i możliwość wykonywania zapytań w celu generowania wniosków za pomocą tych danych w ramach aplikacji.

Z kolei usługa Power BI to rozwiązanie analityczne w postaci oprogramowania jako usługi, które zapewnia organizacjom pojedynczy widok danych biznesowych o kluczowym znaczeniu.

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Czym różnią się usługi Power BI Premium i Power BI Embedded?

Power BI Premium to pojemność skierowana do przedsiębiorstw, które chcą korzystać z kompleksowego rozwiązania analizy biznesowej zapewniającego pojedynczy widok organizacji, partnerów, klientów i dostawców. Usługa Power BI Premium pomaga organizacji w podejmowaniu decyzji. Power BI Premium jest produktem SaaS, który pozwala użytkownikom na korzystanie z zawartości za pośrednictwem portalu usługi Power BI, aplikacji mobilnej oraz opracowanych wewnętrznie aplikacji.

Usługa Power BI Embedded jest przeznaczona dla niezależnych dostawców oprogramowania lub deweloperów, którzy tworzą aplikacje i chcą w nich osadzać wizualizacje. Power BI Embedded pomaga klientom w podjęciu decyzji, ponieważ jest usługą skierowaną do deweloperów aplikacji. Klienci takiej aplikacji, w tym dowolne osoby w organizacji lub spoza niej, mogą korzystać z zawartości przechowywanej w ramach pojemności usługi Power BI Embedded. Zawartość dotycząca pojemności usługi Power BI Embedded nie może być udostępniana jednym kliknięciem pozycji Publikuj w sieci web lub jednym kliknięciem pozycji Publikuj w programie SharePoint i nie obsługuje raportów usług SSRS.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Kiedy firma Microsoft zaleca klientom zakup usługi Power BI Premium a kiedy usługi Power BI Embedded?

Firma Microsoft zaleca przedsiębiorstwom zakup usługi Power BI Premium, czyli samoobsługowego rozwiązania analizy biznesowej w chmurze klasy korporacyjnej, natomiast niezależnym dostawcom oprogramowania poleca zakup usługi Power BI Embedded, czyli składników osadzonej analizy opartych na chmurze. Nie ma jednak żadnych ograniczeń dotyczących produktu, który klient może kupić.

W niektórych przypadkach niezależny dostawca oprogramowania (działający zazwyczaj na dużą skalę) zechce użyć jednostki SKU P, aby skorzystać z dodatkowych korzyści wstępnie spakowanej usługi Power BI w swojej organizacji oraz mieć możliwość osadzania aplikacji. Z kolei inne przedsiębiorstwa mogą być zainteresowane wyłącznie tworzeniem aplikacji biznesowych i osadzaniem w nich analizy, ale bez korzystania ze wstępnie spakowanej usługi Power BI, w takim przypadku mogą zdecydować się na użycie jednostek SKU A na platformie Azure.

### <a name="how-many-embed-tokens-can-i-create"></a>Ile mogę utworzyć tokenów osadzania?

Tokeny osadzania z licencją PRO są przeznaczone do celów projektowania i testowania programowania, więc liczba tokenów osadzania, które może wygenerować konto główne usługi Power BI, jest ograniczona. Aby umożliwić osadzanie w środowisku produkcyjnym, musisz [kupić pojemność](#technical). Nie ma żadnego ograniczenia liczby generowanych tokenów osadzania, gdy zostanie kupiona pojemność. Przejdź do tematu [Get Available Features](https://msdn.microsoft.com/library/mt846473.aspx) (Pobieranie dostępnych funkcji), aby sprawdzić wartość użycia, która wskazuje bieżące użycie osadzania w procentach.

## <a name="technical"></a>Szczegóły techniczne

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Jaka jest różnica między jednostkami SKU A na platformie Azure i jednostkami SKU EM w usłudze Office 365?

PowerBI.com to rozwiązanie dla przedsiębiorstw oferowane w modelu SaaS, które obejmuje wiele funkcji, takich jak współpraca w społeczności czy subskrypcja wiadomości e-mail.

Usługa Power BI Embedded to zestaw interfejsów API udostępnionych deweloperom, aby umożliwić im tworzenie osadzonego rozwiązania do analizy w ramach modelu PaaS. W przypadku scenariusza osadzonej analizy witryna PowerBI.com powinna być używana w celu ułatwienia niezależnym dostawcom oprogramowania i deweloperom zarządzania zawartością osadzonego rozwiązania do analizy oraz ustawieniami poziomu dzierżawy.

Poniżej przedstawiono skróconą listę różnych funkcji, których można używać z poszczególnymi jednostkami SKU.

|Promowanie  |Power BI Embedded<br>(jednostki SKU A) |Pojemność usługi Power BI Premium<br>(jednostki SKU EM)  | 
|---------|---------|---------|
|Osadzanie artefaktów z obszarów roboczych aplikacji Power BI     |Pojemność platformy Azure |Pojemność usługi Office 365 |
|Korzystanie z raportów wymaga licencji usługi Power BI |Nie  |Tak |
|Korzystanie z raportów usługi Power BI w aplikacji osadzonej |Tak  |Tak |
|Korzystanie z raportów usługi Power BI w programie SharePoint |Nie |Tak |
|Korzystanie z raportów usługi Power BI w usłudze Teams |Nie |Tak |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Usługa Power BI oferuje trzy rodzaje jednostek SKU na potrzeby osadzania: SKU A, SKU EM i SKU P. Którą z nich kupić dla mojego scenariusza?

|  |Jednostka SKU A (usługa Power BI Embedded)  |Jednostka SKU EM (usługa Power BI Premium)  |Jednostka SKU P (usługa Power BI Premium)  |
|---------|---------|---------|---------|
|Zakup     |Witryna Azure Portal |Pakiet Office |Pakiet Office |
|Przypadki użycia |* Osadzanie zawartości we własnej aplikacji |* Osadzanie zawartości we własnej aplikacji<br>* Udostępnianie zawartości użytkownikom spoza witryny PowerBI.com korzystającym z bezpłatnej wersji usługi Power BI i przeprowadzanie osadzania w innych aplikacjach SaaS, takich jak SharePoint i Teams |* Osadzanie zawartości we własnej aplikacji<br>* Udostępnianie zawartości użytkownikom spoza witryny PowerBI.com korzystającym z bezpłatnej wersji usługi Power BI i przeprowadzanie osadzania w innych aplikacjach SaaS, takich jak SharePoint i Teams<br>* Udostępnianie zawartości użytkownikom korzystającym z bezpłatnej wersji usługi Power BI za pośrednictwem witryny PowerBI.com  |
|Rozliczanie |Godzinowe |Miesięczne |Miesięczne |
|Zobowiązanie  |Brak zobowiązania |Roczne  |Miesięczne lub roczne |
|Rozróżnienie produktów |Pełna elastyczność, która umożliwia skalowanie w górę i w dół oraz wstrzymywanie i wznawianie zasobów w witrynie Azure Portal lub za pośrednictwem interfejsu API  |Może służyć do osadzania zawartości w usługach SharePoint Online i Microsoft Teams |Pozwala przeprowadzać osadzanie w aplikacjach, używając jednocześnie usługi Power BI w ramach tej samej pojemności |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Jakie są wymagania wstępne dotyczące tworzenia pojemności PBIE na platformie Azure?

- Musisz zalogować się do swojego katalogu organizacyjnego (konta MSA nie są obsługiwane).
- Musisz mieć dzierżawę usługi Power BI, tj. co najmniej jeden użytkownik w Twoim katalogu musi być zarejestrowany w usłudze Power BI. 
- Musisz mieć subskrypcję platformy Azure w katalogu organizacyjnym.

### <a name="how-can-i-monitor-capacity-consumption"></a>Jak można monitorować poziom zużycia pojemności?

Monitorowanie za pomocą platformy Azure zostało uwzględnione w najbliższych planach rozwoju. Zasób platformy Azure, jakim jest usługa Power BI Embedded, będzie umożliwiał monitorowanie wskaźników KPI, których zadaniem jest prezentowanie informacji na temat kondycji i użycia.

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>Czy pojemność będzie automatycznie skalować w celu dostosowania się do poziomu użycia aplikacji?

Chociaż obecnie funkcja automatycznego skalowania nie jest dostępna, wszystkie interfejsy API mogą rozpocząć skalowanie w dowolnym momencie.

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>Z jakiego modelu uwierzytelnienia korzysta usługa Power BI Embedded?

Usługa Power BI Embedded będzie nadal używała usługi Azure AD do uwierzytelniania użytkownika głównego (wyznaczonego licencjonowanego użytkownika usługi Power BI Pro), tym samym uwierzytelniając aplikację w usłudze Power BI.

Mechanizmy uwierzytelniania i autoryzacji użytkowników aplikacji zostaną zaimplementowane przez niezależnego dostawcę oprogramowania — może on też zaimplementować w swoich aplikacjach własny mechanizm uwierzytelniania.

Jeśli masz już dzierżawę usługi Azure AD, możesz użyć istniejącego katalogu lub utworzyć nową dzierżawę usługi Azure AD w celu zabezpieczenia zawartości aplikacji osadzonej.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Czym różnią się usługa Power BI Embedded od innych usług platformy Azure?

Przed zakupieniem usługi Power BI Embedded na platformie Azure niezależny dostawca oprogramowania lub deweloper musi utworzyć konto usługi Power BI. Region wdrożenia usługi Power BI Embedded jest ustalany na podstawie konta usługi Power BI. Zarządzanie zasobem Power BI Embedded na platformie Azure umożliwia:

* skalowanie w górę i w dół
* dodawanie administratorów pojemności
* wstrzymywanie i wznawianie usługi

W celu przypisania lub cofnięcia przypisania obszarów roboczych do pojemności usługi Power BI Embedded należy skorzystać z witryny PowerBI.com.

### <a name="what-deploy-regions-are-supported"></a>Które regiony wdrożenia są obsługiwane?

Australia Południowo-Wschodnia, Brazylia Południowa, Kanada Środkowa, Wschodnie stany USA 2, Indie Zachodnie, Japonia Wschodnia, Środkowo-północne stany USA, Europa Północna, Południowo-środkowe stany USA, Azja Południowo-wschodnia, Południowe Zjednoczone Królestwo, Europa Zachodnia, Zachodnie stany USA i Zachodnie stany USA 2.

### <a name="what-type-of-content-pack-data-can-be-embedded"></a>Jakiego typu dane pakietu zawartości mogą być osadzone?

**Pulpitów nawigacyjnych** i **kafelków** zbudowanych na podstawie zestawów danych pakietu zawartości *nie* można osadzić, jednak **raporty** zbudowane na podstawie zestawu danych pakietu zawartości*można* osadzić.

## <a name="licensing"></a>Licencjonowanie

### <a name="how-do-i-purchase-power-bi-embedded"></a>Jak kupić usługę Power BI Embedded?

Dostęp do usługi Power BI Embedded można uzyskać za pośrednictwem platformy Azure.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>Co się stanie, jeśli po zakupie usługi Power BI Premium zechcę skorzystać z niektórych zalet usługi Power BI Embedded na platformie Azure?

Klienci będą wnosić opłaty za wszelkie dotychczasowe zakupy dokonane w ramach usługi Power BI Premium do końca obowiązywania bieżącej umowy. Po jej wygaśnięciu będą mogli w razie potrzeby przejść do innej usługi niż Power BI Premium.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Czy muszę kupić usługę Power BI Premium, aby uzyskać dostęp do usługi Power BI Embedded?

Nie, usługa Power BI Embedded zawiera pojemność opartą na platformie Azure, którą należy wdrożyć, a następnie dystrybuować swoim klientom.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Jakie jest zobowiązanie dotyczące zakupu usługi Power BI Embedded? 

Klienci mogą zmieniać poziom użycia co godzinę. Usługa Power BI Embedded nie oferuje zobowiązania miesięcznego ani rocznego.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Jak użycie usługi Power BI Embedded jest rozliczane na rachunku?

W przypadku usługi Power BI Embedded stosowana jest stała, przewidywalna stawka godzinowa zależna od typu wdrażanych węzłów. Należy pamiętać, że tak długo, jak zasób jest aktywny, opłaty będą naliczane nawet wtedy, gdy nie będzie on używany. Aby zatrzymać naliczanie opłat, musisz aktywnie wstrzymać zasób.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Kto potrzebuje licencji usługi Power BI Pro dla usługi Power BI Embedded i dlaczego?

Licencję usługi Power BI Pro musi posiadać każdy analityk dodający raporty do obszaru roboczego usługi Power BI, każdy deweloper korzystający z interfejsów API REST oraz każdy administrator dzierżawy zarządzający dzierżawą i pojemnością usługi Power BI.

Ponieważ usługa Power BI Embedded umożliwia korzystanie z portalu usługi Power BI do zarządzania i sprawdzania osadzonej zawartości, posiadanie licencji usługi Power BI Pro jest wymagane do uwierzytelnienia aplikacji w ramach witryny PowerBI.com, a tym samym uzyskania dostępu do raportów we właściwych repozytoriach.

### <a name="can-i-get-started-for-free"></a>Czy mogę zacząć korzystać z usługi bezpłatnie?

Tak, możesz użyć [środków na korzystanie z platformy Azure](https://azure.microsoft.com/free/) w celu rozpoczęcia pracy z usługą Power BI Embedded.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Czy mogę korzystać z wersji próbnej usługi Power BI Embedded na platformie Azure?

Ponieważ usługa Power BI Embedded jest częścią platformy Azure, możesz korzystać z niej na podstawie [kredytu w wysokości 200 USD uzyskanego podczas rejestracji na platformie Azure](https://azure.microsoft.com/free/).

### <a name="is-power-bi-embedded-available-for-sovereign-clouds-us-government-germany-china"></a>Czy usługa Power BI Embedded jest dostępna w przypadku chmur suwerennych (instytucje rządowe Stanów Zjednoczonych, Niemcy, Chiny)?

Usługa Power BI Embedded jest dostępna dla niektórych [chmur suwerennych](embed-sample-for-customers-sovereign-clouds.md). Nadal **NIE** jest ona dostępna w przypadku chmury w wersji dla Chin.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Czy usługa Power BI Embedded jest dostępna dla instytucji edukacyjnych i organizacji niedochodowych?

Instytucje edukacyjne i organizacje niedochodowe mogą zakupić platformę Azure. Nie ma żadnych specjalnych cen dla tego typu klientów platformy Azure.

## <a name="power-bi-workspace-collection"></a>Kolekcja obszarów roboczych usługi Power BI

### <a name="what-is-power-bi-workspace-collection"></a>Co to jest kolekcja obszarów roboczych usługi Power BI?

**Kolekcja obszarów roboczych usługi Power BI** (**Power BI Embedded** w wersji 1) to rozwiązanie oparte na następującym zasobie **Kolekcja obszarów roboczych usługi Power BI** platformy Azure. To rozwiązanie umożliwia tworzenie aplikacji usługi **Power BI Embedded** dla klientów dzięki użyciu zawartości usługi Power BI w rozwiązaniu **Kolekcja obszarów roboczych usługi Power BI**, dedykowanych interfejsów API i kluczy kolekcji obszarów roboczych do uwierzytelniania aplikacji w usłudze Power BI.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Czy mogę migrować zawartość kolekcji obszarów roboczych usługi Power BI do usługi Power BI Embedded?

1. Do klonowania zawartości **kolekcji obszarów roboczych usługi Power BI** do usługi Power BI można użyć narzędzia migracji — https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration.

2. Uruchom weryfikację koncepcji aplikacji usługi **Power BI Embedded**, w której jest używana zawartość usługi Power BI.

3. Gdy wszystko będzie gotowe do produkcji, kup dedykowaną pojemność usługi **Power BI Embedded** i przypisz zawartość usługi Power BI (obszar roboczy) do tej wydajności.

>[!Note]
Możesz nadal używać **kolekcji obszarów roboczych usługi Power BI** podczas kompilowania równolegle z rozwiązaniem **Power BI Embedded**. Gdy wszystko będzie gotowe, można przenieść klienta do nowego rozwiązania usługi **Power BI Embedded** i wycofać rozwiązanie **Kolekcja obszarów roboczych usługi Power BI**.

Aby uzyskać więcej informacji, zapoznaj się z tematem [Jak migrować zawartość kolekcji obszarów roboczych usługi Power BI do usługi Power BI Embedded](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded)

### <a name="is-power-bi-workspace-collection-on-a-path-to-be-deprecated"></a>Czy jest planowane wycofanie z użycia kolekcji obszarów roboczych usługi Power BI?

Tak, ale klienci, którzy już używają rozwiązania **Kolekcja obszarów roboczych usługi Power BI**, mogą nadal z niego korzystać, dopóki nie zostanie uznane za przestarzałe. Klienci mogą również tworzyć nowe kolekcje obszarów roboczych i wszystkie aplikacje usługi **Power BI Embedded**, które będą nadal używać rozwiązania **Kolekcja obszarów roboczych usługi Power BI**.

Oznacza to jednak również, że nowe funkcje nie są dodawane do żadnych rozwiązań typu **Kolekcja obszarów roboczych usługi Power BI**, a klienci są zachęcani do przeprowadzania migracji do nowego rozwiązania **Power BI Embedded**.
### <a name="when-will-power-bi-workspace-collection-support-be-discontinued"></a>Kiedy zakończy się świadczenie pomocy technicznej dla rozwiązania Kolekcja obszarów roboczych usługi Power BI?

Klienci, którzy już używają rozwiązania **Kolekcja obszarów roboczych usługi Power BI**, mogą z niego korzystać do końca czerwca 2018 r. lub do zakończenia okresu obowiązywania umowy dotyczącej pomocy technicznej.

### <a name="in-what-regions-can-pbi-workspace-collection-be-created"></a>W jakich regionach można tworzyć kolekcję obszarów roboczych usługi PBI?

Dostępne regiony to: Australia Południowo-Wschodnia, Brazylia Południowa, Kanada Środkowa, Wschodnie stany USA 2, Japonia Wschodnia, Środkowo-północne stany USA, Europa Północna, Południowo-środkowe stany USA, Azja Południowo-wschodnia, Południowe Zjednoczone Królestwo, Europa Zachodnia, Indie Zachodnie i Zachodnie stany USA.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>Dlaczego warto migrować kolekcję obszarów roboczych usługi Power BI do usługi Power BI Embedded?

Istnieją nowe funkcje i możliwości wprowadzone w rozwiązaniu **Power BI Embedded**, z których nie można korzystać w przypadku **kolekcji obszarów roboczych usługi Power BI**.

Oto przykłady tych funkcji:
* Wszystkie źródła danych usługi PBI są obsługiwane, w odróżnieniu od 2 źródeł danych rozwiązania **Kolekcja obszarów roboczych usługi Power BI**. 
* Nowe funkcje, takie jak pytania i odpowiedzi, odświeżanie, zakładki, osadzanie pulpitów nawigacyjnych i kafelków, menu niestandardowe itd., są obsługiwane tylko w rozwiązaniu **Power BI Embedded**.
* Model rozliczania pojemności.

Aby uzyskać więcej informacji, zobacz [Rozwiązywanie problemów z aplikacją osadzoną](embedded-troubleshoot.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)