---
title: Zarządzanie obsługą wielu podmiotów za pomocą analizy osadzonej w usłudze Power BI
description: Projektowanie aplikacji z wieloma dzierżawami przy użyciu analizy osadzonej.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: nishalit
ms.service: powerbi
ms.subservice: powerbi - developer
ms.topic: conceptual
ms.date: 01/11/2019
ms.openlocfilehash: d09312ecf462e557ef33851d9d2b1f91ec936dae
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54289215"
---
# <a name="manage-multi-tenancy-with-power-bi-embedded-analytics"></a>Zarządzanie obsługą wielu podmiotów za pomocą analizy osadzonej w usłudze Power BI

W przypadku projektowania aplikacji SaaS z wieloma dzierżawami należy starannie wybrać model dzierżawy, który najlepiej spełnia potrzeby aplikacji SaaS. Ten proces działa również w usłudze Power BI jako część analizy osadzonej aplikacji SaaS. Model dzierżawy określa, jak dane każdej dzierżawy są mapowane i zarządzane w usłudze Power BI i na koncie magazynu. Model dzierżawy wpływa na projekt aplikacji i zarządzanie nią. Przełączanie do innego modelu w terminie późniejszym może spowodować wzrost kosztów i zakłócenia działania.

W usłudze Power BI Embedded są stosowane dwa podstawowe podejścia do zarządzania oddzielaniem dzierżaw.

   1. **Izolacja oparta na obszarze roboczym** — tworzenie oddzielnego obszaru roboczego usługi Power BI na dzierżawę.
   2. **Izolacja oparta na zabezpieczeniach na poziomie wiersza** — dane podstawowe są używane do kontrolowania dostępu poszczególnych użytkowników lub grup do danych oraz do zarządzania tym dostępem.

W tym artykule opisano różne podejścia i przeanalizowano je przy użyciu kilku kryteriów oceny.

## <a name="concepts-and-terminology"></a>Pojęcia i terminologia

**[AAD](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)** — Azure Active Directory.

**Aplikacja usługi AAD**  — tożsamość aplikacji w usłudze AAD. Aplikacja usługi AAD jest wymagana do uwierzytelniania.

**Aplikacja SaaS (oprogramowanie jako usługa)** — zaimplementowany przez przedsiębiorstwo lub niezależnego dostawcę oprogramowania system, który jest przeważnie usługą online. Mogą być to również powiązane systemy oprogramowania służące do obsługi wielu dzierżaw klientów (organizacji). W tym artykule **aplikacja SaaS używa usługi Power BI Embedded do przekazywania danych analitycznych do różnych dzierżaw**. Usługa Power BI Embedded może również współdziałać ze wszystkimi typami aplikacji, jeśli mają połączenie w trybie online.

**Dzierżawa** — pojedynczy klient (organizacja) korzystający z aplikacji SaaS i innych zasobów lub danych, które klient umieszcza w aplikacji SaaS.

**[Power BI](../power-bi-overview.md)** — usługa Power BI w chmurze, która służy jako platforma usługi Power BI Embedded.

**Dzierżawa usługi Power BI** — zbór zasobów usługi Power BI skojarzony z pojedynczą dzierżawą usługi AAD.

**[Obszar roboczy usługi Power BI](../service-create-workspaces.md)** — kontener zawartości w usłudze Power BI.

**Artefakty usługi Power BI** — w obszarach roboczych usługi Power BI istnieją różne rodzaje artefaktów usługi Power BI, takie jak pulpity nawigacyjne, raporty, zestawy danych i przepływy danych.

**[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md)** — zestaw publicznych interfejsów API, które umożliwiają deweloperom kompilowanie aplikacji zarządzających zawartością usługi Power BI i osadzających elementy usługi Power BI.

**[Zabezpieczenia na poziomie wiersza (RLS)](embedded-row-level-security.md)** — umożliwiają kontrolowanie dostępu użytkowników do danych dla poszczególnych wierszy w tabeli. Zabezpieczenia na poziomie wiersza można zaimplementować na poziomie źródła danych lub w modelu semantycznym usługi Power BI.

**Użytkownik główny** — tożsamość, która reprezentuje aplikację SaaS w usłudze Power BI i której aplikacja SaaS używa podczas wywoływania interfejsów API usługi Power BI. Musi być to użytkownik usługi AAD z licencją usługi Power BI Pro.

**Użytkownik aplikacji usługi AAD (jednostka usługi)** — tożsamość, która reprezentuje aplikację SaaS w usłudze Power BI i której aplikacja SaaS używa podczas wywoływania interfejsów API usługi Power BI. Musi być to aplikacja internetowa usługi AAD. Może ona zastąpić użycie użytkownika *głównego* do uwierzytelniania za pomocą usługi Power BI.

**Pojemność** — zestaw zasobów przeznaczonych do obsługi usługi Power BI. [Pojemności usługi Power BI Premium](../service-premium.md) są przeznaczone dla przedsiębiorstw używających usługi Power BI wewnętrznie, natomiast [pojemności usługi Power BI Embedded](azure-pbie-create-capacity.md) są przeznaczone dla deweloperów aplikacji i służą do tworzenia aplikacji SaaS dla innych firm.

**[Licencja usługi Power BI Pro](../service-admin-purchasing-power-bi-pro.md)** — oparta na użytkowniku licencja, która przyznaje prawa do publikowania zawartości w obszarach roboczych aplikacji, używania aplikacji bez pojemności Premium, udostępniania pulpitów nawigacyjnych oraz subskrybowania pulpitów nawigacyjnych i raportów.

**[Tryby łączności danych](../desktop-directquery-about.md)** — łączenie źródeł danych z usługą Power BI, które może odbywać się w różnych trybach:

   * Import — najczęściej używany sposób pobierania danych.
   * DirectQuery — łączenie bezpośrednio z danymi w repozytorium źródłowym.
   * Połączenie na żywo — kolejny tryb, który powoduje bezpośrednie połączenie z danymi usług Analysis Services (na platformie Azure i w środowisku lokalnym).

## <a name="evaluation-criteria"></a>Kryteria oceny

Optymalny wybór właściwego modelu dzierżawy dla aplikacji SaaS zależy od specyficznych wymagań biznesowych i technicznych, architektury danych i innych czynników. Dokładne zrozumienie tych wymagań oraz dostępnych opcji i kompromisów związanych z modelami dzierżawy może pomóc w zdefiniowaniu niezawodnej, wydajnej, taniej i skalowalnej architektury aplikacji SaaS.

Poniżej przedstawiono zestaw obszarów, które należy wziąć pod uwagę, dokonując wyboru między różnymi modelami dzierżawy.

### <a name="data-architecture"></a>Architektura danych

Przeważnie deweloperzy tworzący aplikacje za pomocą usługi Power BI Embedded już mają bazę danych z jedną lub wieloma dzierżawami. Łatwiej jest korzystać z modelu dzierżawy dla usługi Power BI Embedded, który jest podobny do modelu dzierżawy bazy danych. Jeśli model dzierżawy bazy danych nie został jeszcze zdefiniowany, warto wziąć pod uwagę inne aspekty przed podjęciem decyzji dotyczącej architektury danych.

### <a name="data-isolation"></a>Izolacja danych

Jak poufne są przechowywane dane? Jaki poziom izolacji jest potrzebny przy oddzielaniu różnych dzierżaw klientów? Odpowiedzi mogą różnić się w zależności od branży lub klientów, którzy mają określone wymagania.

### <a name="scalability"></a>Skalowalność

Aby uzyskać najlepsze rozwiązanie, należy zdefiniować skalę, która ma zostać osiągnięta w najbliższej przyszłości. Należy pamiętać o tym, że rozwiązanie stosowane w tej chwili może nie być wystarczające, gdy użycie i dane będą skalowane w górę. Podczas analizowania skalowalności należy wziąć pod uwagę poniższą listę:

   * Liczba dzierżaw (klientów).
   * Liczba raportów, pulpitów nawigacyjnych i zestawów danych dla każdej dzierżawy.
   * Rozmiar danych w poszczególnych zestawach danych i częstotliwość odświeżania.
   * Liczba użytkowników.
   * Liczba współbieżnych użytkowników w godzinach szczytu.

Niektóre aplikacje SaaS mogą mieć małą liczbę klientów i niskie użycie, ale duże ilości danych. Inne mogą mieć wielu klientów i wysokie użycie, ale niewielką ilość danych i małą liczbę raportów dla każdego klienta. Duże liczby w takich sytuacjach mogą wpływać na przyszłe koszty i złożoność operacyjną.

### <a name="automation--operational-complexity"></a>Automatyzacja i złożoność operacyjna

Należy zidentyfikować cykliczne procesy, które wymagają automatyzacji.

   * Jaka jest częstotliwość dołączania nowych dzierżaw? Jakie akcje należy wykonać w celu pełnego dołączenia każdej z nich?
   * Jakie jest tempo wydawania nowej lub zaktualizowanej zawartości usługi Power BI, którą należy wdrożyć?
   * Ile ról zabezpieczeń na poziomie wiersza zdefiniowano dla każdej dzierżawy?  

Zidentyfikowanie tych procesów oraz sposobu ich obsługi może ułatwić zrozumienie złożoności operacyjnej związanej z zarządzaniem poszczególnymi modelami.

### <a name="data-residency-requirements-and-the-need-to-support-multiple-geographies"></a>Wymagania dotyczące rezydencji danych i konieczność obsługi wielu obszarów geograficznych

Usługa Power BI Embedded obsługuje wdrażanie w wielu obszarach geograficznych (funkcja w wersji zapoznawczej). Funkcja [Multi-Geo](embedded-multi-geo.md) umożliwia wdrażanie zasobów usługi Power BI Embedded w różnych regionach z określoną zawartością przypisaną do określonych regionów. Tej funkcji można również używać we wszystkich modelach, ale może mieć to wpływ na ilość zawartości do zarządzania oraz na koszt. Obecnie wiele obszarów geograficznych zaprojektowano tak, aby spełniały wymagania dotyczące rezydencji danych. Przenoszenie danych bliżej użytkowników nie poprawia wydajności.

### <a name="cost"></a>Cost

Usługa [Power BI Embedded](https://azure.microsoft.com/en-us/services/power-bi-embedded/) korzysta z modelu zakupów opartych na zasobach, takiego jak usługa **Power BI Premium**. Można zakupić co najmniej jedną pojemność o stałej mocy obliczeniowej i pamięci. Ta pojemność stanowi główny element kosztów w przypadku pracy z usługą **Power BI Embedded**. Liczba użytkowników używających pojemności nie jest ograniczona. Jedynym ograniczeniem jest wydajność pojemności. [Licencja usługi Power BI Pro](../service-admin-licensing-organization.md) jest wymagana dla każdego użytkownika *głównego* lub określonych użytkowników, którzy muszą uzyskiwać dostęp do portalu usługi Power BI.

Zalecamy przetestowanie i zmierzenie oczekiwanego obciążenia pojemności przez symulowanie na żywo środowiska i użycia oraz uruchamianie testów obciążenia w obrębie pojemności. Obciążenie i wydajność można mierzyć za pomocą różnych metryk dostępnych w obrębie pojemności na platformie Azure lub w [aplikacji metryki pojemności Premium](../service-admin-premium-monitor-capacity.md).

### <a name="content-customization-and-authoring"></a>Dostosowywanie i tworzenie zawartości

Istnieją dwa podejścia do aplikacji SaaS, które oferują użytkownikom możliwość edytowania i tworzenia raportów lub przekazywania danych do usługi w ramach przepływu:

   * [Tryb edytowania/tworzenia w osadzonym elemencie iFrame](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View) — użytkownik otrzymuje widok raportu lub nową, pustą kanwę w aplikacji SaaS. Dzięki temu może za pomocą paska narzędzi usługi Power BI tworzyć zawartość w oparciu o zestaw danych w obszarze roboczym. Zalecamy użycie tej opcji, ponieważ działa ona w kontekście użytkownika w znajomym środowisku. Rozpoczęcie pracy i edycji jest prostsze, a użytkownik tworzy raport dołączony do istniejącego zestawu danych.

   * Program Power BI Desktop umożliwia tworzenie zawartości i przekazywanie jej za pośrednictwem interfejsu użytkownika aplikacji SaaS do obszaru roboczego. W przypadku tego podejścia użytkownicy mają więcej narzędzi, z którymi mogą pracować w programie Power BI Desktop. Nie zalecamy jednak korzystania z tego podejścia, ponieważ użytkownicy muszą znać dodatkowe narzędzie poza kontekstem aplikacji SaaS. Przekazywanie pliku PBIX oznacza, że użytkownik dodaje kolejny zestaw danych, który może być duplikatem zestawów danych już znajdujących się w obszarze roboczym.

## <a name="power-bi-workspace-based-isolation"></a>Izolacja oparta na obszarze roboczym usługi Power BI

W przypadku izolacji opartej na obszarze roboczym usługi Power BI aplikacja SaaS obsługuje wiele dzierżaw z poziomu pojedynczej dzierżawy usługi Power BI. Izolacja oparta na obszarze roboczym obejmuje całą zawartość usługi Power BI używaną przez różne dzierżawy. Oddzielanie dzierżaw odbywa się na poziomie obszaru roboczego usługi Power BI przez utworzenie wielu obszarów roboczych. Każdy obszar roboczy zawiera odpowiednie zestawy danych, raporty i pulpity nawigacyjne dla konkretnej dzierżawy. Ponadto każdy obszar roboczy jest połączony tylko z danymi tej dzierżawy. Jeśli potrzebujesz dodatkowej izolacji, możesz utworzyć użytkownika *głównego* lub jednostkę usługi dla każdego obszaru roboczego i jego zawartości.

![Obszar roboczy](media/multi-tenant-saas/multi-tenant-saas-workspace.png)

### <a name="data-architecture"></a>Architektura danych

Istnieją dwa główne podejścia do zarządzania danymi dzierżawy.

* Oddzielna baza danych na dzierżawę
* Jedna baza danych z wieloma dzierżawami

Jeśli w magazynie aplikacji SaaS jest przechowywana oddzielna baza danych na dzierżawę, naturalnym wyborem jest używanie zestawów danych z jedną dzierżawą w usłudze Power BI z parametrami połączenia dla każdego zestawu danych wskazującego na pasującą bazę danych.

Jeśli magazyn aplikacji SaaS korzysta z bazy danych z wieloma dzierżawami dla wszystkich dzierżaw, można łatwo rozdzielić dzierżawy według obszaru roboczego. Można skonfigurować połączenie bazy danych dla zestawu danych usługi Power BI przy użyciu zapytania sparametryzowanego, które pobiera tylko dane odpowiedniej dzierżawy. Połączenie można zaktualizować przy użyciu programu [Power BI Desktop](../desktop-query-overview.md) lub korzystając z interfejsu [API](https://docs.microsoft.com/rest/api/power-bi/datasets/updatedatasourcesingroup) z [parametrami](https://docs.microsoft.com/en-us/rest/api/power-bi/datasets/updateparametersingroup) w zapytaniu.

### <a name="data-isolation"></a>Izolacja danych

Dane w tym modelu dzierżawcy są oddzielone na poziomie obszaru roboczego. Proste mapowanie między obszarem roboczym i dzierżawą uniemożliwia użytkownikom z jednej dzierżawy wyświetlanie zawartości innej dzierżawy. Użycie pojedynczego użytkownika *głównego* wymaga dostępu do wszystkich obszarów roboczych. Konfiguracja danych, które mają być widoczne dla użytkownika końcowego, jest definiowana podczas [generowania tokenu osadzania](https://docs.microsoft.com/en-us/rest/api/power-bi/embedtoken), czyli procesu odbywającego się tylko w obrębie zaplecza, którego użytkownicy końcowi nie widzą ani nie mogą zmienić.

Aby dodać dodatkową izolację, deweloper aplikacji może zdefiniować użytkownika *głównego* lub aplikację na obszar roboczy, zamiast pojedynczego użytkownika *głównego* lub aplikacji z dostępem do wielu obszarów roboczych. W ten sposób można zagwarantować, że żaden błąd ludzki ani wyciek poświadczeń nie spowoduje ujawnienia danych wielu klientów.

### <a name="scalability"></a>Skalowalność

Jedną z zalet tego modelu jest to, że rozdzielenie danych między wieloma zestawami danych dla każdej dzierżawy pozwala na rozwiązanie problemów z [limitami rozmiaru pojedynczego zestawu danych](https://docs.microsoft.com/en-us/power-bi/service-premium-large-datasets) (obecnie 10 GB w pojemności). W przypadku przeciążenia pojemności [może nastąpić wykluczenie nieużywanych zestawów danych](../service-premium-understand-how-it-works.md) do bezpłatnej pamięci na potrzeby aktywnych zestawów danych. Tego zadania nie można wykonać w przypadku pojedynczego dużego zestawu danych. W przypadku używania wielu zestawów danych można również w razie potrzeby rozdzielić dzierżawy między wiele pojemności usługi Power BI. [Dowiedz się więcej na temat sposobu działania pojemności](../service-admin-premium-manage.md).

Mimo tych korzyści należy wziąć pod uwagę skalę, którą aplikacja SaaS może osiągnąć w przyszłości. Na przykład mogą zostać osiągnięte ograniczenia dotyczące liczby artefaktów, którymi można zarządzać. Aby uzyskać więcej informacji, zobacz [ograniczenia](#summary-comparison-of-the-different-approaches) dotyczące wdrożenia w dalszej części tego artykułu. Używana jednostka SKU wprowadza limit rozmiaru pamięci, w którym muszą mieścić się zestawy danych, [liczbę operacji odświeżania, które można uruchomić w tym samym czasie](../service-premium-understand-how-it-works.md), oraz maksymalną częstotliwość operacji odświeżania danych. W przypadku zarządzania setkami lub tysiącami zestawów danych zaleca się testowanie działania tej funkcji. Zaleca się również, aby wziąć pod uwagę średnią i szczytową wielkość użycia, a także określone dzierżawy z dużymi zestawami danych lub różne wzorce użycia, które są zarządzane w sposób inny niż pozostałe dzierżawy.

### <a name="automation--operational-complexity"></a>Automatyzacja i złożoność operacyjna

W przypadku izolacji opartej na obszarze roboczym usługi Power BI od dewelopera aplikacji może być wymagane zarządzanie setkami lub tysiącami artefaktów. Istotne jest określenie procesów, które często są przeprowadzane w trakcie zarządzania cyklem życia aplikacji, oraz upewnienie się, że istnieje właściwy zestaw narzędzi do wykonywania tych operacji na odpowiednią skalę w danym modelu dzierżawy. Niektóre przykładowe operacje to:

   * Dodawanie nowej dzierżawy (klienta)
   * Aktualizowanie raportu lub pulpitu nawigacyjnego dla niektórych lub wszystkich dzierżaw
   * Aktualizowanie schematu zestawu danych dla niektórych lub wszystkich dzierżaw
   * Nieplanowane dostosowania określonych dzierżaw
   * Częstotliwość odświeżania zestawów danych

Na przykład tworzenie obszaru roboczego dla nowej dzierżawy to typowe zadanie, które wymaga automatyzacji. Dzięki [interfejsowi API REST usługi Power BI](https://docs.microsoft.com/rest/api/power-bi/) można osiągnąć [pełną automatyzację podczas tworzenia obszarów roboczych](https://powerbi.microsoft.com/blog/duplicate-workspaces-using-the-power-bi-rest-apis-a-step-by-step-tutorial/).

### <a name="multi-geo-needs"></a>Potrzeby funkcji Multi-Geo

Funkcja Multi-Geo obejmuje zakup pojemności w żądanych regionach oraz przypisywanie obszaru roboczego do tej pojemności. Jeśli chcesz obsługiwać różne dzierżawy w różnych regionach, musisz przypisać obszar roboczy dzierżawy do pojemności w żądanym regionie. To zadanie jest prostą operacją, której koszt jest nie większy niż w sytuacji, w której wszystkie obszary robocze znajdują się w tej samej pojemności. Jednak jeśli Twoje dzierżawy wymagają danych znajdujących się w wielu regionach, wszystkie artefakty w obszarze roboczym muszą być powielone w każdej pojemności regionalnej, co zwiększa koszt i złożoność zarządzania.

### <a name="cost"></a>Cost

Deweloperzy aplikacji korzystający z usługi Power BI Embedded muszą [kupić pojemność usługi Power BI Embedded, aby przejść do środowiska produkcyjnego](embed-sample-for-customers.md#move-to-production).  Ważne jest, aby zrozumieć wpływ modelu izolacji opartej na obszarze roboczym oraz efekty jej zastosowania w poszczególnych pojemnościach.

Model izolacji opartej na obszarze roboczym dobrze współpracuje z pojemnościami z następujących powodów:

   * Najmniejszy obiekt, który można niezależnie przypisać do pojemności, to obszar roboczy (czyli nie można na przykład przypisać raportu), dlatego rozdzielając dzierżawy według obszarów roboczych, uzyskujesz pełną elastyczność zarządzania poszczególnymi dzierżawami i ich potrzebami związanymi z wydajnością oraz optymalizowania wykorzystania wydajności przez skalowanie w górę/w dół. Na przykład dużymi i niezbędnymi dzierżawami o dużych wolumenach i zmienności można zarządzać w oddzielnej pojemności, co zapewni spójny poziom usługi, grupując równocześnie mniejsze dzierżawy w celu zoptymalizowania kosztów.

   * Oddzielanie obszarów roboczych oznacza również rozdzielanie zestawów danych między dzierżawami, tak aby modele danych miały postać mniejszych fragmentów, zamiast pojedynczego, dużego zestawu danych. To zadanie pozwala pojemności lepiej zarządzać użyciem pamięci dzięki wykluczaniu małych i nieużywanych zestawów danych, gdy nie będą potrzebne, utrzymując równocześnie poziom zadowolenia użytkowników z wydajności.

Deweloperzy aplikacji muszą brać pod uwagę limit liczby równoległych odświeżeń, ponieważ procesy odświeżania mogą potrzebować dodatkowej pojemności, jeśli istnieje wiele zestawów danych.

### <a name="content-customization-and-authoring"></a>Dostosowywanie i tworzenie zawartości

W przypadku podstawowych zastosowań procesu tworzenia zawartości deweloper aplikacji musi dokładnie zastanowić się, które dzierżawy mogą mieć możliwości edytowania oraz ilu użytkowników w każdej dzierżawie będzie mogło edytować dane. Zezwolenie wielu użytkownikom w każdej dzierżawie na edytowanie może spowodować generowanie wielu elementów zawartości, a w konsekwencji osiąganie limitów dotyczących zestawu danych, takich jak liczba raportów na zestaw danych lub liczba zestawów danych w obszarze roboczym. Jeśli przyznasz użytkownikom tę możliwość, zalecamy dokładne monitorowanie zawartości i skalowanie w górę odpowiednio do potrzeb. Z tych samych powodów nie zalecamy używania tej możliwości w procesie personalizowania zawartości, podczas którego każdy użytkownik może wprowadzać drobne zmiany w raporcie i zapisywać je do własnego użytku. Jeśli aplikacja SaaS zezwala na personalizację zawartości, należy rozważyć wprowadzanie i komunikowanie zasad przechowywania zawartości specyficznej dla użytkownika w obszarze roboczym. Usprawni to przepływ usuwania zawartości, gdy użytkownicy końcowi zmienią stanowisko, opuszczą firmę lub nie będą już korzystać z platformy.

## <a name="row-level-security-based-isolation"></a>Izolacja oparta na zabezpieczeniach na poziomie wiersza

W przypadku izolacji opartej na zabezpieczeniach na poziomie wiersza aplikacja SaaS używa jednego obszaru roboczego do hostowania wielu dzierżaw. Oznacza to, że każdy zestaw danych, pulpit nawigacyjny i raport artefaktu usługi Power BI jest tworzony po użyciu przez wszystkie dzierżawy. Rozdzielenie danych między dzierżawami można osiągnąć przy użyciu [zabezpieczeń na poziomie wiersza](embedded-row-level-security.md) w zestawie danych z wieloma dzierżawami. Gdy użytkownicy końcowi logują się do aplikacji SaaS i otwierają zawartość, jest generowany token osadzania dla sesji danego użytkownika z rolami i filtrami, które zapewnią, że użytkownik będzie widzieć tylko dane, do których ma uprawnienia. Jeśli użytkownicy z tej samej dzierżawy nie mogą wyświetlać tych samych danych, deweloper aplikacji musi zaimplementować role hierarchiczne między dzierżawami i w tej samej dzierżawie.

![Zabezpieczenia na poziomie wiersza](media/multi-tenant-saas/multi-tenant-saas-rls.png)

### <a name="data-architecture"></a>Architektura danych

Implementowanie izolacji opartej na zabezpieczeniach na poziomie wiersza jest najłatwiejsze, gdy dane wszystkich dzierżaw są przechowywane w jednym magazynie danych. W takiej sytuacji deweloper aplikacji może przekazać tylko odpowiednie dane z magazynu danych do zestawu danych usługi Power BI za pośrednictwem zapytania bezpośredniego lub importu danych. Jeśli dane w bazie danych są oddzielone według dzierżaw, należy je połączyć w jeden zestaw danych, co spowoduje niższy stopień oddzielenia między dzierżawami, które istniały w bazie danych.

### <a name="data-isolation"></a>Izolacja danych

W przypadku izolacji opartej na zabezpieczeniach na poziomie wiersza oddzielanie danych odbywa się przy użyciu [definicji zabezpieczeń na poziomie wiersza](embedded-row-level-security.md) w zestawie danych, co oznacza, że wszystkie dane współistnieją. Ta forma oddzielania danych jest bardziej narażona na wyciek danych spowodowany błędem dewelopera. Mimo że zabezpieczenia na poziomie wiersza są wdrażane w obrębie zaplecza i chronione przed użytkownikiem końcowym, jeśli dane są wysoce poufne lub klienci proszą o oddzielenie danych, lepszym rozwiązaniem może być użycie izolacji opartej na obszarze roboczym.

### <a name="scalability"></a>Skalowalność

W przypadku izolacji opartej na zabezpieczeniach na poziomie wiersza dane muszą mieścić się w limicie rozmiaru zestawu danych, który obecnie wynosi 10 GB. Wraz z wprowadzeniem [odświeżania przyrostowego](../service-premium-incremental-refresh.md) i nadchodzącej wersji punktu końcowego XMLA w przypadku zestawów danych usługi Power BI oczekuje się znacznego wzrostu limitu rozmiaru zestawu danych. Dane muszą jednak nadal mieścić się w pamięci pojemności, a pozostała ilość pamięci musi być wystarczająca do uruchamiania odświeżeń. Wdrożenia na dużą skalę potrzebują dużej pojemności, aby uniknąć sytuacji, w których użytkownicy będą mieli problemy, gdy pamięć przekroczy limity bieżącej pojemności. Alternatywne sposoby obsługi skalowania obejmują użycie **[agregacji](../desktop-aggregations.md)** lub nawiązanie połączenia ze źródłem danych bezpośrednio za pomocą trybu DirectQuery lub połączenia na żywo, zamiast buforowania wszystkich danych w pojemności usługi Power BI.

### <a name="automation--operational-complexity"></a>Automatyzacja i złożoność operacyjna

Zarządzanie artefaktami jest znacznie wygodniejsze przy użyciu izolacji opartej na zabezpieczeniach na poziomie wiersza niż przy użyciu izolacji opartej na obszarze roboczym, ponieważ istnieje tylko jedna wersja artefaktu dla każdego środowiska (tworzenie/testowanie/produkcja), zamiast wersji na dzierżawę. Na dużą skalę zarządzanie artefaktami oznacza zarządzanie dziesiątkami, a nie tysiącami lub dziesiątkami tysięcy, artefaktów oraz ich aktualizowanie.

Usługa Power BI nie ma jeszcze interfejsu API umożliwiającego modyfikowanie lub tworzenie reguł i ról zabezpieczeń na poziomie wiersza. Role można dodawać lub zmieniać wyłącznie ręcznie w programie Power BI Desktop. Jeśli trzeba zastosować hierarchię zabezpieczeń na poziomie wiersza i ta operacja nie zostanie dokładnie zaplanowana, będzie bardziej skomplikowana i mniej odporna na błędy.

Jeśli deweloper aplikacji musi zarządzać wieloma rolami i definicjami ról, które trzeba często tworzyć lub aktualizować, izolacja oparta na zabezpieczeniach na poziomie wiersza nie jest skalowalna z punktu widzenia możliwości zarządzania.

Inna złożoność operacyjna to konieczność ścisłego monitorowania wykorzystania pamięci i zbudowania niezawodnego mechanizmu alertów i skalowania w celu zagwarantowania użytkownikom bezproblemowego środowiska pracy.  

### <a name="multi-geo-needs"></a>Potrzeby funkcji Multi-Geo

Ponieważ wszystkie dane są przechowywane w jednym zestawie danych, spełnienie wymagań dotyczących rezydencji danych, które wymagają powiązania pewnych danych z określonymi lokalizacjami, może być trudne. Może to również znacznie zwiększyć koszt używania wielu regionów, ponieważ wszystkie dane są replikowane i przechowywane w poszczególnych regionach. Jeśli tylko ograniczona liczba dzierżaw musi mieć różne lokalizacje geograficzne, możesz przechowywać dane tylko tych dzierżaw w innym regionie, korzystając z opisanego powyżej modelu izolacji opartej na obszarze roboczym.

### <a name="cost"></a>Cost

Głównym czynnikiem wpływającym na koszt w przypadku izolacji opartej na zabezpieczeniach na poziomie wiersza jest zużycie pamięci zestawu danych. Potrzebna jest wystarczająca pojemność do przechowywania zestawu danych oraz dodatkowy bufor pamięci na wypadek wzrostów zapotrzebowania na pamięć. Jednym ze sposobów uniknięcia tej sytuacji jest przechowywanie danych w bazie danych programu SQL Server lub module usług Analysis Services w programie SQL Server oraz używanie trybu zapytań bezpośrednich lub połączenia na żywo do pobierania danych ze źródła danych w czasie rzeczywistym. To podejście zwiększa koszt źródeł danych, ale zmniejsza zapotrzebowanie na dużą pojemność z powody wymagań dotyczących pamięci, a w konsekwencji obniża koszt pojemności usługi Power BI.

### <a name="content-customization-and-authoring"></a>Dostosowywanie i tworzenie zawartości

Gdy użytkownicy końcowi edytują lub tworzą raporty, mogą używać produkcyjnego zestawu danych z wieloma dzierżawami. Z tego powodu zalecamy używanie tylko opcji osadzonego elementu iFrame do edytowania lub [tworzenia raportów](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View), ponieważ opiera się on na tym samym zestawie danych z zastosowanymi zabezpieczeniami na poziomie wiersza. Opcja przekazywania przez użytkowników plików PBIX z dodatkowymi zestawami może być kosztowna i trudna do zarządzania w przypadku izolacji opartej na zabezpieczeniach poziomu wierszy. Ponadto gdy użytkownicy generują nową zawartość, która znajduje się w tym samym obszarze roboczym, musisz upewnić się, że produkcyjny obszar roboczy nie osiąga limitów, oraz zbudować niezawodny mechanizm rozróżniania zawartości połączonej z poszczególnymi dzierżawami.

## <a name="summary-comparison-of-the-different-approaches"></a>Podsumowanie porównania różnych podejść

> [!Important]
> Poniższa analiza opiera się na bieżącym stanie produktu. Ponieważ co miesiąc udostępniamy nowe funkcje, masz stały dostęp do nowych możliwości i funkcji stanowiących odpowiedź na istniejące ograniczenia i słabe punkty. Pamiętaj, aby co miesiąc sprawdzać wpisy w naszym blogu w celu zapoznania się z nowościami oraz regularnie wracać do tego artykułu w celu sprawdzenia, jak nowe funkcje wpływają na rekomendacje dotyczące modelu dzierżawy.

| Kryteria oceny | Oparte na obszarze roboczym   | Oparte na zabezpieczeniach na poziomie wiersza  |  |  |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|---|---|
| Architektura danych  | Najłatwiejsze, gdy istnieje oddzielna baza danych na dzierżawę  | Najłatwiejsze, gdy wszystkie dane dla wszystkich dzierżaw znajdują się w pojedynczym magazynie danych   |  |  |
| Izolacja danych  | Dobra. Każda dzierżawa ma dedykowany zestaw danych.  | Średnia. Wszystkie dane znajdują się w tym samym udostępnionym zestawie danych, ale są zarządzane przy użyciu kontroli dostępu.  |  |  |
| Skalowalność  | Średnia. Podzielenie danych na wiele zestawów danych umożliwia optymalizację.  | Najniższa. Ograniczona przez limity zestawu danych.  |  |  |
| Potrzeby funkcji Multi-Geo  | Dobre rozwiązanie, gdy większość dzierżaw znajduje się tylko w jednym regionie.  | Niezalecane. Należy zachować cały zestaw danych przechowywany w wielu regionach.  |  |  |
| Automatyzacja i złożoność operacyjna  | Dobre rozwiązanie w przypadku automatyzacji pojedynczej dzierżawy.   Złożone zarządzanie wieloma artefaktami w odpowiedniej skali.  | Łatwe zarządzanie artefaktami usługi Power BI, ale trudne zarządzanie zabezpieczeniami na poziomie wiersza w odpowiedniej skali.  |  |  |
| Cost  | Niski/średni. Można optymalizować wykorzystanie w celu zmniejszenia kosztów na dzierżawę.  Może wzrosnąć, jeśli są wymagane częste operacje odświeżania.  | Średni/wysoki w przypadku używania trybu importu.  Niski/średni w przypadku używania trybu zapytań bezpośrednich.  |  |  |
| Dostosowywanie i tworzenie zawartości  | Dobre rozwiązanie. Może napotkać ograniczenia w przypadku dużej skalę.  | Generowanie zawartości tylko w osadzonym elemencie iFrame  |  |  |

## <a name="deployment-considerations-and-limitations"></a>Zagadnienia i ograniczenia związane z wdrażaniem

**Limity artefaktów usługi Power BI:**

* Liczba obszarów roboczych w wersji 1 (grupy), w których pojedynczy użytkownik/aplikacja może być członkiem/administratorem, wynosi 250.
* Liczba obszarów roboczych w wersji 2 (foldery), w których pojedynczy użytkownik/aplikacja może być członkiem/administratorem, wynosi 1000.
* Liczba zestawów danych w pojedynczym obszarze roboczym wynosi 1000.
* Liczba raportów/pulpitów nawigacyjnych połączonych z pojedynczym zestawem danych wynosi 1000.
* Limit rozmiaru pamięci zestawu danych w przypadku przekazywania pliku *pbix* wynosi 10 GB.

**Zagadnienia i ograniczenia dotyczące pojemności usługi Power BI:**

* Każda pojemność może używać tylko przydzielonej pamięci i rdzeni wirtualnych zgodnie z [zakupionymi jednostkami SKU](../service-premium.md).
* Aby uzyskać informacje na temat zalecanego rozmiaru zestawu danych dla poszczególnych jednostek SKU, zapoznaj się z artykułem dotyczącym [dużych zestawów danych w wersji Premium](../service-premium-large-datasets.md).
* Maksymalny rozmiar zestawu danych w pojemności dedykowanej wynosi 10 GB.
* Liczba zaplanowanych odświeżeń zestawu danych w *trybie importu* w ciągu dnia wynosi 48.
* Czas między zaplanowanymi odświeżeniami zestawu danych w *trybie importu* wynosi 30 minut.
* Aby uzyskać informacje na temat liczby odświeżeń, które można współbieżnie uruchamiać w ramach pojemności, zapoznaj się z artykułem dotyczącym [zarządzania zasobami i ich optymalizacji](../service-premium-understand-how-it-works.md).
* Średni czas skalowania pojemności wynosi od 1 do 2 minut. W tym czasie pojemność jest niedostępna. W celu [uniknięcia przestojów](https://powerbi.microsoft.com/blog/power-bi-developer-community-november-update-2018/#scale-script) zalecamy stosowanie podejścia obejmującego zwiększanie skali w poziomie.

## <a name="next-steps"></a>Następne kroki

* [Analiza osadzona w usłudze Power BI](embedding.md)
* [Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md)
* [Power BI Premium](../service-premium.md)
* [Zabezpieczenia na poziomie wiersza](embedded-row-level-security.md)