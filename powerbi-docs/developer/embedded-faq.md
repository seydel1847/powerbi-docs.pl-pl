---
title: Często zadawane pytania dotyczące usługi Power BI Embedded
description: Przeglądaj listę często zadawanych pytań i odpowiedzi dotyczących usługi Power BI Embedded.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/17/2018
ms.openlocfilehash: cd32b644205629ce62579f5a720d486f93073dea
ms.sourcegitcommit: ccbe76a0a43c5c5e87354a33e617bf3cb291608e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/18/2019
ms.locfileid: "54394736"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Często zadawane pytania dotyczące usługi Power BI Embedded

* Jeśli masz inne pytania, [zadaj je społeczności usługi Power BI](http://community.powerbi.com/).
* Nadal masz problem? Odwiedź [stronę pomocy technicznej usługi Power BI](https://powerbi.microsoft.com/support/).

## <a name="general"></a>Ogólne

### <a name="what-is-power-bi-embedded"></a>Co to jest usługa Power BI Embedded?

Usługa Microsoft Power BI Embedded (PBIE) umożliwia osadzanie niesamowitych, w pełni interaktywnych raportów w aplikacjach bez potrzeby poświęcania czasu i pieniędzy na tworzenie wizualizacji danych i kontrolek od podstaw.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Kto jest docelowym odbiorcą usługi Power BI Embedded?

Deweloperzy i firmy programistyczne tworzące własne aplikacje nazywani niezależnymi dostawcami oprogramowania (ISV).

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Czym różnią się usługi Power BI Embedded i Power BI?

Usługa Power BI Embedded jest przeznaczona dla niezależnych dostawców oprogramowania lub deweloperów, którzy tworzą aplikacje i chcą w nich osadzać wizualizacje, aby pomóc klientom w podejmowaniu decyzji bez konieczności tworzenia rozwiązania do analizy od podstaw. Osadzona analiza zapewnia użytkownikom biznesowym dostęp do danych biznesowych i możliwość wykonywania zapytań w celu generowania wniosków za pomocą tych danych w ramach aplikacji.

Usługa Power BI to rozwiązanie analityczne w postaci oprogramowania jako usługi, które zapewnia organizacjom pojedynczy widok danych biznesowych o kluczowym znaczeniu.

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Czym różnią się usługi Power BI Premium i Power BI Embedded?

Power BI Premium to pojemność skierowana do przedsiębiorstw, które chcą korzystać z kompleksowego rozwiązania analizy biznesowej zapewniającego pojedynczy widok organizacji, partnerów, klientów i dostawców. Usługa Power BI Premium pomaga organizacji w podejmowaniu decyzji. Power BI Premium jest produktem SaaS, który pozwala użytkownikom na korzystanie z zawartości za pośrednictwem portalu usługi Power BI, aplikacji mobilnej oraz opracowanych wewnętrznie aplikacji.

Usługa Power BI Embedded jest przeznaczona dla niezależnych dostawców oprogramowania lub deweloperów, którzy tworzą aplikacje i chcą w nich osadzać wizualizacje. Power BI Embedded pomaga klientom w podjęciu decyzji, ponieważ jest usługą skierowaną do deweloperów aplikacji. Klienci takiej aplikacji, w tym dowolne osoby w organizacji lub spoza niej, mogą korzystać z zawartości przechowywanej w ramach pojemności usługi Power BI Embedded. Zawartość dotycząca pojemności usługi Power BI Embedded nie może być udostępniana jednym kliknięciem pozycji Publikuj w Internecie ani jednym kliknięciem pozycji Publikuj w programie SharePoint i nie obsługuje raportów usług SSRS.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Kiedy firma Microsoft zaleca klientom zakup usługi Power BI Premium a kiedy usługi Power BI Embedded?

Firma Microsoft zaleca przedsiębiorstwom zakup usługi Power BI Premium, czyli samoobsługowego rozwiązania analizy biznesowej w chmurze klasy korporacyjnej, natomiast niezależnym dostawcom oprogramowania poleca zakup usługi Power BI Embedded, czyli składników osadzonej analizy opartych na chmurze. Nie ma jednak żadnych ograniczeń dotyczących produktu, który klient może kupić.

W niektórych przypadkach niezależny dostawca oprogramowania (działający zazwyczaj na dużą skalę) zechce użyć jednostki SKU P, aby skorzystać z dodatkowych korzyści wstępnie spakowanej usługi Power BI w swojej organizacji oraz mieć możliwość osadzania aplikacji. Niektóre przedsiębiorstwa mogą być zainteresowane wyłącznie tworzeniem aplikacji biznesowych i osadzaniem w nich analizy, ale bez korzystania ze wstępnie dołączonej usługi Power BI — w takim przypadku mogą zdecydować się na użycie jednostek SKU A na platformie Azure.

### <a name="how-many-embed-tokens-can-i-create"></a>Ile mogę utworzyć tokenów osadzania?

Tokeny osadzania z licencją PRO są przeznaczone do celów projektowania i testowania programowania, więc liczba tokenów osadzania, które może wygenerować konto główne usługi Power BI, jest ograniczona. Aby umożliwić osadzanie w środowisku produkcyjnym, musisz [kupić pojemność](#technical). Nie ma ograniczenia liczby generowanych tokenów osadzania, gdy zostanie kupiona pojemność. Przejdź do sekcji [Available Features](https://docs.microsoft.com/rest/api/power-bi/availablefeatures) (Dostępne funkcje), aby sprawdzić wartość użycia, która wskazuje bieżące użycie osadzania w procentach.

## <a name="technical"></a>Szczegóły techniczne

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Jaka jest różnica między jednostkami SKU A na platformie Azure i jednostkami SKU EM w usłudze Office 365?

PowerBI.com to rozwiązanie dla przedsiębiorstw oferowane w modelu SaaS, które obejmuje wiele funkcji, takich jak współpraca w społeczności czy subskrypcja wiadomości e-mail.

Usługa Power BI Embedded to zestaw interfejsów API udostępnionych deweloperom, aby umożliwić im tworzenie osadzonego rozwiązania do analizy w ramach modelu PaaS. W przypadku scenariusza osadzonej analizy witryna PowerBI.com ułatwia niezależnym dostawcom oprogramowania i deweloperom zarządzanie zawartością osadzonego rozwiązania do analizy oraz ustawieniami poziomu dzierżawy.

Poniżej przedstawiono skróconą listę różnych funkcji, których można używać z poszczególnymi jednostkami SKU.

| Promowanie | Power BI Embedded | Pojemność usługi Power BI Premium | Pojemność usługi Power BI Premium |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (jednostki SKU A) | (jednostki SKU EM) | (Jednostki SKU P) |
| Osadzanie artefaktów z obszaru roboczego aplikacji Power BI | Pojemność platformy Azure | Pojemność usługi Office 365 | Pojemność usługi Office 365 |
| Korzystanie z raportów usługi Power BI w aplikacji osadzonej | Tak | Tak | Tak |
| Korzystanie z raportów usługi Power BI w programie SharePoint | Nie | Tak | Tak |
| Korzystanie z raportów usługi Power BI w usłudze Dynamics | Nie | Tak | Tak |
| Korzystanie z raportów usługi Power BI w usłudze Teams (z wyłączeniem aplikacji mobilnych) | Nie | Tak | Tak |
| Dostęp do zawartości z bezpłatną licencją usługi Power BI w witrynie Powerbi.com i na platformie Power BI dla urządzeń przenośnych | Nie | Nie | Tak |
| Dostęp do zawartości osadzonej w aplikacjach pakietu MS Office z bezpłatną licencją usługi Power BI | Nie | Tak | Tak |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Usługa Power BI oferuje teraz trzy rodzaje jednostek SKU na potrzeby osadzania: jednostki SKU A, EM i P. Którą z nich kupić dla mojego scenariusza?

|  |Jednostka SKU A (usługa Power BI Embedded)  |Jednostka SKU EM (usługa Power BI Premium)  |Jednostka SKU P (usługa Power BI Premium)  |
|---------|---------|---------|---------|
|Zakup  |Witryna Azure Portal |Pakiet Office |Pakiet Office |
|Przypadki użycia | Osadzanie zawartości we własnej aplikacji | <li> Osadzanie zawartości we własnej aplikacji <br><br></br> <li> Osadzanie zawartości w aplikacjach pakietu MS Office: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (z wyłączeniem aplikacji mobilnych)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> Osadzanie zawartości we własnej aplikacji <br><br></br> <li> Osadzanie zawartości w aplikacjach pakietu MS Office: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (z wyłączeniem aplikacji mobilnych)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br></br> <li> Udostępnianie zawartości użytkownikom usługi Power BI za pośrednictwem [usługi Power BI](https://powerbi.microsoft.com/en-us/)  |
|Rozliczenia |Godzinowe |Miesięczne |Miesięczne |
|Zobowiązanie  |Brak zobowiązania |Roczne  |Miesięczne lub roczne |
|Rozróżnienie produktów |Pełna elastyczność, która umożliwia skalowanie w górę i w dół oraz wstrzymywanie i wznawianie zasobów w witrynie Azure Portal lub za pośrednictwem interfejsu API  |Może służyć do osadzania zawartości w usługach SharePoint Online i Microsoft Teams (z wyłączeniem aplikacji mobilnych) |Pozwala przeprowadzać osadzanie w aplikacjach, używając jednocześnie usługi Power BI w ramach tej samej pojemności |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Jakie są wymagania wstępne dotyczące tworzenia pojemności PBIE na platformie Azure?

* Musisz zalogować się do swojego katalogu organizacyjnego (konta MSA nie są obsługiwane).
* Musisz mieć dzierżawę usługi Power BI, czyli co najmniej jeden użytkownik w Twoim katalogu musi utworzyć konto usługi Power BI. 
* Musisz mieć subskrypcję platformy Azure w katalogu organizacyjnym.

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Jak można monitorować użycie pojemności usługi Power BI Embedded?

* Używając [portalu administracyjnego usługi Power BI](../service-admin-portal.md#power-bi-embedded).

* Pobierając [aplikację metryki](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) w usłudze Power BI.

* Używając [rejestrowania diagnostycznego na platformie Azure](azure-pbie-diag-logs.md).

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>Czy pojemność będzie automatycznie skalować w celu dostosowania się do poziomu użycia aplikacji?

Chociaż obecnie funkcja automatycznego skalowania nie jest dostępna, wszystkie interfejsy API mogą rozpocząć skalowanie w dowolnym momencie.

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>Dlaczego tworzenie/skalowanie/wznawianie pojemności powoduje umieszczenie pojemności w stanie wstrzymania?

Aprowizowanie pojemności (skalowanie/wznawianie/tworzenie) może zakończyć się niepowodzeniem. Obiekt wywołujący wywołania aprowizowania musi sprawdzić stan ProvisioningState pojemności przy użyciu interfejsu API pobierania szczegółów: [Pojemności — Pobierz szczegóły](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails).

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>Czy mogę tworzyć pojemności usługi Power BI Embedded tylko w określonym regionie?

Dzięki funkcji [Multi-Geo (wersja zapoznawcza)](embedded-multi-geo.md) możesz kupić [pojemność usługi Power BI Embedded](azure-pbie-create-capacity.md) w regionie innym niż lokalizacja Twojej głównej dzierżawy usługi Power BI

### <a name="how-can-i-find-what-is-my-pbi-tenant-region"></a>Jak mogę znaleźć swój region dzierżawy usługi PBI?

Możesz użyć portalu usługi PBI, aby zrozumieć, co to jest region dzierżawy usługi PBI.

[https://app.powerbi.com/](https://app.powerbi.com/) > ? > Power BI — informacje

![Power BI — informacje](media/embedded-faq/about-01.png)
![Region dzierżawy](media/embedded-faq/tenant-location-01.png)

### <a name="what-is-supported-with-the-cloud-solution-provider-csp-channel"></a>Jakie operacje są obsługiwane w przypadku kanału dostawcy rozwiązań w chmurze (CSP, Cloud Solution Provider)?

* Możesz utworzyć PBIE dla dzierżawy przy użyciu subskrypcji typu CSP
* Konto partnera może logować się do dzierżawy klienta i kupować usługę PBIE dla dzierżawy klienta. Określ użytkownika dzierżawy klienta jako administratora pojemności usługi Power BI

### <a name="why-do-i-get-an-unsupported-account-message"></a>Dlaczego otrzymuję komunikat o nieobsługiwanym koncie?

Usługa Power BI wymaga zarejestrowania się za pomocą konta organizacyjnego. Próby rejestracji w usłudze Power BI przy użyciu konta Microsoft nie są obsługiwane.

### <a name="can-i-use-apis-to-create--manage-azure-capacities"></a>Czy mogę używać interfejsów API do tworzenia możliwości platformy Azure i zarządzania nimi?

Tak, istnieją polecenia cmdlet programu PowerShell i interfejsy API usługi Azure Resource Manager, których można używać do tworzenia zasobów usługi PBIE i zarządzania nimi.

* Interfejsy API REST — https://docs.microsoft.com/rest/api/power-bi-embedded/
* Polecenia cmdlet programu PowerShell — https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>Co to jest dedykowana pojemność PBI Embedded w rozwiązaniu PBI Embedded?

W celu [podniesienia poziomu rozwiązania do środowiska produkcyjnego](https://docs.microsoft.com/power-bi/developer/embedding-content#step-3-promote-your-solution-to-production) musisz przypisać zawartość usługi Power BI (obszaru roboczego aplikacji, którego używasz w swojej aplikacji) do pojemności usługi Power BI Embedded (SKU A).

### <a name="what-are-the-azure-regions-pbi-embedded-is-available"></a>Które regiony świadczenia usługi Azure PBI Embedded są dostępne?

[PAM](https://ecosystemmanager.azurewebsites.net/home) (EcoManager) — zobacz Menedżer dostępności produktu

Dostępne regiony (16 — te same regiony, co w usłudze Power BI)

* USA (6) — Wschodnie stany USA, Wschodnie stany USA 2, Północno-środkowe stany USA, Południowo-środkowe stany USA, Zachodnie stany USA, Zachodnie stany USA 2
* Europa (2) — Europa Północna, Europa Zachodnia
* Azja i Pacyfik (2) — Azja Południowo-Wschodnia, Azja Wschodnia
* Brazylia (1) — Brazylia Południowa
* Japonia (1) — Japonia Wschodnia
* Australia (1) — Australia Południowo-Wschodnia
* Indie (1) — Indie Zachodnie
* Kanada (1) — Kanada Środkowa
* Zjednoczone Królestwo (1) — Południowe Zjednoczone Królestwo

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>Z jakiego modelu uwierzytelnienia korzysta usługa Power BI Embedded?

Usługa Power BI Embedded nadal używa usługi Azure AD do uwierzytelniania użytkownika głównego (wyznaczonego licencjonowanego użytkownika usługi Power BI Pro), tym samym uwierzytelniając aplikację w usłudze Power BI.

Mechanizmy uwierzytelniania i autoryzacji użytkowników aplikacji są implementowane przez niezależnego dostawcę oprogramowania — może on zaimplementować w swoich aplikacjach własny mechanizm uwierzytelniania.

Jeśli masz już dzierżawę usługi Azure AD, możesz użyć istniejącego katalogu lub utworzyć nową dzierżawę usługi Azure AD w celu zabezpieczenia zawartości aplikacji osadzonej.

Aby uzyskać token usługi AAD, możesz użyć jednej z bibliotek uwierzytelniania usługi Azure Active Directory — https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries. Dostępne są biblioteki klienckie dla wielu platform.

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-an-user-owns-data-scenario"></a>Moja aplikacja już używa usługi AAD do uwierzytelniania użytkowników. Jak możemy użyć tej tożsamości podczas uwierzytelniania w usłudze Power BI w ramach scenariusza „User Owns Data”?

Jest to standardowy przepływ protokołu OAuth typu „w imieniu użytkownika” (https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#web-application-to-web-api): aplikacja musi zostać skonfigurowana do wymagania uprawnień związanych z usługą Power BI (z wymaganymi zakresami). Po utworzeniu tokenu użytkownika do aplikacji wystarczy wywołać metodę AcquireTokenAsync interfejsu API biblioteki ADAL przy użyciu tokenu dostępu użytkownika i określić adres URL zasobu usługi Power BI jako identyfikator zasobu. Poniższy fragment kodu przedstawia sposób wykonania tej czynności:

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

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

### <a name="what-is-the-difference-between-using-rls-vs-javascript-filters"></a>Jaka jest różnica między używaniem zabezpieczeń na poziomie wiersza i filtrów języka JavaScript?

Często występują niejasności związane z określeniem, kiedy należy używać zabezpieczeń na poziomie wiersza, a kiedy filtrów języka JavaScript, ponieważ jedna z metod dotyczy kontrolowania elementów widocznych dla określonego użytkownika, a druga — optymalizacji widoku użytkownika.

W przypadku zabezpieczeń na poziomie wiersza deweloper ISV kontroluje filtrowanie danych w ramach procesu tworzenia modelu i generowania tokenów osadzania. Użytkownik końcowy widzi tylko to, na co zezwoli mu dostawca ISV. W tym przypadku użytkownik może wybrać opcję wyświetlania mniejszej ilości danych niż odfiltrowana, ale nie będzie mógł pominąć konfiguracji zabezpieczeń na poziomie wiersza i wyświetlić więcej zawartości niż dozwolona.

W przypadku filtrowania po stronie klienta (JavaScript) niezależny dostawca oprogramowania może zdecydować, co użytkownik końcowy będzie widzieć w widoku początkowym, ale dostawca ten nie może kontrolować zmian, które użytkownicy mogą samodzielnie zastosować w widoku. Mimo że filtrowanie danych może być przeprowadzane w obrębie zaplecza, jest ono wywoływane przez kod klienta języka JavaScript i dlatego użytkownik końcowy może je zmienić. Filtrowanie takie nie będzie uważane za bezpieczne.

Zapoznaj się z częścią dotyczącą [porównania zabezpieczeń na poziomie wiersza i filtrów języka JavaScript](embedded-row-level-security.md#using-rls-vs-javascript-filters), aby uzyskać więcej informacji.

### <a name="what-are-the-best-practices-to-improve-performance"></a>Jakie są najlepsze rozwiązania w celu zwiększenia wydajności?

[Wydajność usługi Power BI Embedded](embedded-performance-best-practices.md)

## <a name="licensing"></a>Licencjonowanie

### <a name="how-do-i-purchase-power-bi-embedded"></a>Jak kupić usługę Power BI Embedded?

Dostęp do usługi Power BI Embedded można uzyskać za pośrednictwem platformy Azure.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>Co się stanie, jeśli po zakupie usługi Power BI Premium zechcę skorzystać z niektórych zalet usługi Power BI Embedded na platformie Azure?

Klienci będą wnosić opłaty za wszelkie dotychczasowe zakupy dokonane w ramach usługi Power BI Premium do końca obowiązywania bieżącej umowy. Po jej wygaśnięciu będą mogli w razie potrzeby przejść do innej usługi niż Power BI Premium.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Czy muszę kupić usługę Power BI Premium, aby uzyskać dostęp do usługi Power BI Embedded?

Nie, usługa Power BI Embedded zawiera pojemność opartą na platformie Azure, którą należy wdrożyć, a następnie dystrybuować do swoich klientów.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Jakie jest zobowiązanie dotyczące zakupu usługi Power BI Embedded?

Klienci mogą zmieniać poziom użycia co godzinę. Usługa Power BI Embedded nie oferuje zobowiązania miesięcznego ani rocznego.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Jak użycie usługi Power BI Embedded jest rozliczane na rachunku?

W przypadku usługi Power BI Embedded stosowana jest stała, przewidywalna stawka godzinowa zależna od typu wdrażanych węzłów. Tak długo, jak zasób jest aktywny, opłaty są naliczane nawet wtedy, gdy nie jest on używany. Aby zatrzymać naliczanie opłat, musisz aktywnie wstrzymać zasób.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Kto potrzebuje licencji usługi Power BI Pro dla usługi Power BI Embedded i dlaczego?

Każdy analityk, który chce dodawać raporty do obszaru roboczego usługi Power BI, musi mieć licencję usługi Power BI. Każdy deweloper, który chce używać interfejsów API REST, musi mieć licencję usługi Power BI Pro. Każdy administrator dzierżawy, który chce zarządzać dzierżawą i pojemnością usługi Power BI, musi mieć licencję usługi Power BI Pro.

Ponieważ usługa Power BI Embedded umożliwia korzystanie z portalu usługi Power BI do zarządzania i sprawdzania osadzonej zawartości, posiadanie licencji usługi Power BI Pro jest wymagane do uwierzytelnienia aplikacji w ramach witryny PowerBI.com, a tym samym uzyskania dostępu do raportów we właściwych repozytoriach.

Jednak w przypadku [tworzenia/edytowania raportów osadzonych](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View) wewnątrz własnej aplikacji użytkownik końcowy nie potrzebuje licencji Pro, ponieważ w ogóle nie musi być użytkownikiem usługi Power BI.

### <a name="can-i-get-started-for-free"></a>Czy mogę zacząć korzystać z usługi bezpłatnie?

Tak, możesz użyć [środków na korzystanie z platformy Azure](https://azure.microsoft.com/free/) w celu rozpoczęcia pracy z usługą Power BI Embedded.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Czy mogę korzystać z wersji próbnej usługi Power BI Embedded na platformie Azure?

Ponieważ usługa Power BI Embedded jest częścią platformy Azure, możesz korzystać z niej na podstawie [środków w wysokości 200 USD otrzymanych podczas rejestracji na platformie Azure](https://azure.microsoft.com/free/).

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

    > [!Note]
    > Możesz nadal używać **kolekcji obszarów roboczych usługi Power BI** podczas kompilowania równolegle z rozwiązaniem **Power BI Embedded**. Gdy wszystko będzie gotowe, można przenieść klienta do nowego rozwiązania usługi **Power BI Embedded** i wycofać rozwiązanie **Kolekcja obszarów roboczych usługi Power BI**.

Aby uzyskać więcej informacji, zapoznaj się z tematem [Jak migrować zawartość kolekcji obszarów roboczych usługi Power BI do usługi Power BI Embedded](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded)

### <a name="is-power-bi-workspace-collection-on-a-path-to-be-deprecated"></a>Czy jest planowane wycofanie z użycia kolekcji obszarów roboczych usługi Power BI?

Tak, ale klienci, którzy już używają rozwiązania **Kolekcja obszarów roboczych usługi Power BI**, mogą nadal z niego korzystać, dopóki nie zostanie uznane za przestarzałe. Klienci mogą również tworzyć nowe kolekcje obszarów roboczych i wszystkie aplikacje usługi **Power BI Embedded**, które będą nadal używać rozwiązania **Kolekcja obszarów roboczych usługi Power BI**.

Oznacza to jednak również, że nowe funkcje nie są dodawane do żadnych rozwiązań typu **Kolekcja obszarów roboczych usługi Power BI**, a klienci są zachęcani do przeprowadzania migracji do nowego rozwiązania **Power BI Embedded**.

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>Kiedy kończy się świadczenie pomocy technicznej dla rozwiązania Kolekcja obszarów roboczych usługi Power BI?

Klienci, którzy już używają rozwiązania **Kolekcja obszarów roboczych usługi Power BI**, mogą z niego korzystać do końca czerwca 2018 r. lub do zakończenia okresu obowiązywania umowy dotyczącej pomocy technicznej.

### <a name="in-what-regions-can-pbi-workspace-collection-be-created"></a>W jakich regionach można tworzyć kolekcję obszarów roboczych usługi PBI?

Dostępne regiony to: Australia Południowo-Wschodnia, Brazylia Południowa, Kanada Środkowa, Wschodnie stany USA 2, Japonia Wschodnia, Środkowo-północne stany USA, Europa Północna, Południowo-środkowe stany USA, Azja Południowo-wschodnia, Południowe Zjednoczone Królestwo, Europa Zachodnia, Indie Zachodnie i Zachodnie stany USA.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>Dlaczego warto migrować kolekcję obszarów roboczych usługi Power BI do usługi Power BI Embedded?

Istnieją nowe funkcje i możliwości wprowadzone w rozwiązaniu **Power BI Embedded**, z których nie można korzystać w przypadku **kolekcji obszarów roboczych usługi Power BI**.

Oto przykłady tych funkcji:

* Wszystkie źródła danych usługi PBI są obsługiwane, w odróżnieniu od dwóch źródeł danych rozwiązania **Kolekcja obszarów roboczych usługi Power BI**. 
* Nowe funkcje, takie jak pytania i odpowiedzi, odświeżanie, zakładki, osadzanie pulpitów nawigacyjnych i kafelków oraz menu niestandardowe, są obsługiwane tylko w rozwiązaniu **Power BI Embedded**.
* Model rozliczania pojemności.

## <a name="embedding-setup-tool"></a>Narzędzie do konfigurowania osadzania

### <a name="what-is-the-embedding-setup-tool"></a>Co to jest narzędzie do konfigurowania osadzania?

[Narzędzie do konfigurowania osadzania](https://aka.ms/embedsetup) umożliwia szybkie rozpoczęcie pracy i pobranie przykładowej aplikacji w celu rozpoczęcia osadzania przy użyciu usługi Power BI.

### <a name="which-solution-should-i-choose"></a>Które rozwiązanie wybrać?

* [Osadzanie dla swoich klientów](embedding.md#embedding-for-your-customers) zapewnia możliwość osadzenia pulpitów nawigacyjnych i raportów u użytkowników, którzy nie mają konta w usłudze Power BI. Uruchom rozwiązanie [osadzania dla klientów](https://aka.ms/embedsetup/AppOwnsData).
* [Osadzanie dla swojej organizacji](embedding.md#embedding-for-your-organization) umożliwia rozszerzanie usługi Power BI. Uruchom rozwiązanie [osadzania dla organizacji](https://aka.ms/embedsetup/UserOwnsData).

### <a name="ive-downloaded-the-sample-app-which-solution-do-i-choose"></a>Mam przykładową aplikację. Które rozwiązanie wybrać?

Jeśli korzystasz ze środowiska **osadzania dla klientów**, zapisz i rozpakuj plik *PowerBI-Developer-Samples.zip*. Następnie otwórz folder *PowerBI-Developer-Samples-master\App Owns Data* i uruchom plik *PowerBIEmbedded_AppOwnsData.sln*.

Jeśli korzystasz ze środowiska **osadzania dla organizacji**, zapisz i rozpakuj plik *PowerBI-Developer-Samples.zip*. Następnie otwórz folder *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* i uruchom plik *pbi-saas-embed-report.sln*.

### <a name="how-can-i-edit-my-registered-application"></a>Jak mogę edytować zarejestrowaną aplikację?

Informacje dotyczące edytowania aplikacji zarejestrowanych w usłudze AAD można znaleźć [tutaj](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#updating-an-application).

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>Jak mogę edytować dane lub profil użytkownika usługi Power BI?

Informacje dotyczące edytowania danych usługi Power BI można znaleźć [tutaj](https://docs.microsoft.com/power-bi/service-basic-concepts).

Aby uzyskać więcej informacji, zobacz [Rozwiązywanie problemów z aplikacją osadzoną](embedded-troubleshoot.md).

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)