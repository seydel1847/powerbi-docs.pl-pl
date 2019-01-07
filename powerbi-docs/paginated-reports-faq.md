---
title: 'Raporty podzielone na strony w usłudze Power BI: często zadawane pytania (wersja zapoznawcza)'
description: Ten artykuł zawiera odpowiedzi na często zadawane pytania dotyczące raportów podzielonych na strony. Te raporty oferują dane wyjściowe z zaawansowanym formatowaniem i idealnie rozmieszczoną treścią, zoptymalizowane pod kątem drukowania lub generowania plików PDF.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: report-builder
ms.topic: overview
ms.date: 11/05/2018
ms.author: maggies
ms.openlocfilehash: d3fdf9b568aa13ba5a8437c684835e0fce803d19
ms.sourcegitcommit: bb4cf3469b44e451153c469725a9069dcd548809
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2018
ms.locfileid: "53649450"
---
# <a name="paginated-reports-in-power-bi-faq-preview"></a>Raporty podzielone na strony w usłudze Power BI: często zadawane pytania (wersja zapoznawcza)

Ten artykuł zawiera odpowiedzi na często zadawane pytania dotyczące raportów podzielonych na strony. Te raporty oferują dane wyjściowe z zaawansowanym formatowaniem i idealnie rozmieszczoną treścią, zoptymalizowane pod kątem drukowania lub generowania plików PDF. Są one określane jako „podzielone na strony”, ponieważ dzięki swojemu formatowaniu mieszczą się doskonale na wielu stronach. Raporty podzielone na strony są oparte na technologii raportów RDL dostępnej w usługach SQL Server Reporting Services. 

Ten artykuł zawiera odpowiedzi na wiele typowych pytań dotyczących raportów podzielonych na strony w usłudze Power BI Premium oraz programu Report Builder, który stanowi autonomiczne narzędzie do tworzenia raportów podzielonych na strony. Do publikowania raportu w usłudze jest niezbędna licencja usługi Power BI Pro. Raporty podzielone na strony można publikować i udostępniać w obszarze Mój obszar roboczy lub innych obszarach roboczych w aplikacji, jeśli obszar roboczy znajduje się w pojemności Premium usługi Power BI. 

## <a name="administration"></a>Administracja

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>Jakiego rozmiaru pojemności Premium potrzebuję w przypadku raportów podzielonych na strony?

Obciążenie raportów podzielonych na strony jest dostępne w publicznej wersji zapoznawczej w jednostkach SKU P1–P3.  Można również używać go w scenariuszach testowania/tworzenia przy użyciu jednostek SKU A4–A6.

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>Jaki jest maksymalny próg rozmiaru pamięci, którą mogę umieścić w pojemności na potrzeby raportów podzielonych na strony?

Obecnie dla tego obciążenia można zarezerwować tylko 50% pamięci. 

### <a name="how-does-user-access-work-for-paginated-reports"></a>Jak działa dostęp użytkowników w przypadku raportów podzielonych na strony?

Dostęp użytkowników w przypadku raportów podzielonych na strony działa tak jak dostęp użytkowników do całej pozostałej zawartości w usłudze Power BI. 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>Jak mogę włączyć/wyłączyć swoje obciążenie dotyczące raportów podzielonych na strony?

Administrator pojemności może włączać lub wyłączać obciążenie dotyczące raportów podzielonych na strony na stronie portalu administracyjnego pojemności.  

### <a name="how-can-i-monitor-usage-of-paginated-reports-in-my-tenant"></a>Jak mogę monitorować użycie raportów podzielonych na strony w dzierżawie?

Dzienniki inspekcji usługi Office 365 przedstawiają szczegółowe użycie danego typu raportu w ramach następujących zdarzeń: 

- Wyświetlanie raportu usługi Power BI
- Usuwanie raportu usługi Power BI
- Tworzenie raportu usługi Power BI
- Pobranie raportu usługi Power BI

Pole ReportType ma wartość „PaginatedReport”, co powoduje identyfikowanie raportów podzielonych na strony jako przeciwieństwa raportów usługi Power BI.

Dzienniki inspekcji oferują ponadto następujące zdarzenia dotyczące raportów podzielonych na strony:

- Powiązano zestaw danych usługi Power BI z bramą
- Odnajdywanie źródła danych usługi Power BI
- TakeOverDatasource

### <a name="can-i-monitor-this-workload-through-the-premium-capacity-monitoring-app"></a>Czy mogę monitorować to obciążenie za pośrednictwem aplikacji do monitorowania pojemności Premium?

Tak, monitorowanie jest dostępne jako nowa karta zawierająca te same szczegóły, które obsługujesz w przypadku zestawów danych usługi Power BI.

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>Czy potrzebuję licencji Pro do tworzenia i publikowania raportów podzielonych na strony?

Tak. Nie można przekazywać raportów do obszaru roboczego bez licencji Pro. Możesz pobrać i wypróbować program Report Builder bez licencji Pro, ale nie możesz publikować tworzonych raportów podzielonych na strony. 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>Co zrobić, jeśli mam raport podzielony na strony w obszarze roboczym, a obciążenie dotyczące raportów podzielonych na strony zostało wyłączone?

Zostanie wyświetlony raport o błędzie i nie będzie można wyświetlić raportu, dopóki obciążenie nie zostanie ponownie włączone. Raport będzie można nadal usunąć z obszaru roboczego.

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-supported-for-paginated-reports"></a>Jaka jest pamięć domyślna dla poszczególnych jednostek SKU w wersji Premium obsługiwanych w raportach podzielonych na strony?

Pamięć domyślna w każdej jednostce SKU w wersji Premium w przypadku raportów podzielonych na strony:

- **P1/A4**: Domyślna 20%; minimalna 10%
- **P2/A5**: Domyślna 20%; minimalna 5%
- **P3/A6**: Domyślna 20%; minimalna 2,5%

## <a name="general"></a>Ogólne

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>Kiedy należy używać raportu podzielonego na strony, a kiedy raportu usługi Power BI?

Raporty podzielone na strony to najlepsze rozwiązanie w przypadku scenariuszy, które wymagają danych wyjściowych z zaawansowanym formatowaniem i idealnie rozmieszczoną treścią, zoptymalizowanych pod kątem drukowania lub generowania plików PDF.  Dobrym przykładem typu raportu, który prawdopodobnie zechcesz utworzyć w postaci raportu podzielonego na strony, jest rachunek zysków i strat.  

Raporty usługi Power BI są zoptymalizowane pod kątem eksploracji i interakcyjności.  Do obsługi raportu sprzedaży, w którym różni sprzedawcy chcą używać fragmentów danych dla określonego regionu/branży/klienta i sprawdzać, jak zmieniają się liczby, najlepiej będzie nadawać się raport usługi Power BI.

### <a name="the-documentation-says-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>Zgodnie z dokumentacją program Report Builder jest preferowanym narzędziem do tworzenia. Czy mogę tworzyć raporty podzielone na strony przy użyciu narzędzi SQL Server Data Tools dla usługi Power BI?

Tak, ale usługa Power BI pozwala tylko na przekazywanie jednego elementu w danym momencie, dlatego wiele scenariuszy, w których autorzy używają narzędzi SQL Server Data Tools (SSDT), nie jest jeszcze obsługiwanych. Zobacz pełną [listę nieobsługiwanych funkcji](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi) w dalszej części tego artykułu zawierającego często zadawane pytania.  

### <a name="what-versions-of-report-builder-do-you-support"></a>Które wersje programu Report Builder są obsługiwane?

Najnowsza wersja programu SQL Server 2016 Report Builder umożliwia tworzenie i publikowanie raportów w usłudze Power BI. Zainstaluj program [Report Builder z Centrum pobierania Microsoft](https://www.microsoft.com/download/details.aspx?id=53613).

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>Jak mogę przenieść istniejące raporty zapisane w usługach SQL Server Reporting Services do usługi Power BI?

Musisz pobrać raport z serwera, a następnie przekazać go do usługi Power BI za pośrednictwem portalu.  Obecnie nie jest dostępne żadne narzędzie migracji, ale planujemy utworzyć je po zamknięciu etapu publicznej wersji zapoznawczej i uzyskaniu odpowiedniego poziomu równoważności funkcji między produktami.

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>Czy mogę otwierać raporty i publikować je bezpośrednio w usłudze?

W tej chwili nie. W przyszłości dodamy możliwość otwierania raportów i publikowania ich bezpośrednio w usłudze z poziomu programu Report Builder — tak jak w przypadku programu Power BI Desktop.

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>Które funkcje raportów podzielonych na strony w usługach SSRS nie są jeszcze obsługiwane w usłudze Power BI?

Obecnie raporty podzielone na strony nie obsługują następujących elementów:

- Udostępnione źródła danych
- Udostępnione zestawy danych
- Podraporty
- Akcje obsługiwane za pomocą kliknięć i akcje przechodzenia do szczegółów
- Połączone raporty
- Zakładki
- Warstwy mapy Bing
- Czcionki niestandardowe

Próba przekazania pliku, który ma nieobsługiwaną funkcję w usłudze Power BI inną niż przełączanie/sortowanie, spowoduje wyświetlenie komunikatu o błędzie.

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>Które źródła danych są obecnie obsługiwane w przypadku raportów podzielonych na strony?

Obsługujemy usługę Azure SQL Database, program SQL Server oraz modele tabelaryczne (DAX) i wielowymiarowe (MDX) usług SQL Server Analysis Services (SSAS) przy użyciu bramy lokalnej.

W przypadku uzyskiwania dostępu do usług SSAS za pośrednictwem bramy użytkownik, którego poświadczenia są przechowywane, musi mieć uprawnienia z podniesionym poziomem w usługach SSAS, aby pracować za pośrednictwem bramy.

### <a name="what-authentication-methods-do-you-support"></a>Które metody uwierzytelniania są obsługiwane?

Aktualnie musisz przechowywać nazwę użytkownika i hasło ze źródłem danych w portalu lub bramie.  Dodatkowe metody uwierzytelniania do obsługi elementów, takich jak zabezpieczenia na poziomie wiersza, będą dostępne później w wersji zapoznawczej.

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>Czy mogę używać zestawu danych usługi Power BI jako źródła danych w raporcie podzielonym na strony?

Jeszcze nie, ale planujemy wkrótce wdrożyć taką obsługę.

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>Czy mogę używać procedur składowanych za pośrednictwem bramy?

Możesz używać procedury składowanej za pośrednictwem bramy, ale w niektórych scenariuszach mogą występować problemy, jeśli procedura składowana ma parametry.

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Które formaty eksportu są dostępne dla raportu w usłudze Power BI?

Można eksportować do programów Microsoft Excel, Microsoft Word i Microsoft PowerPoint oraz formatów PDF, CSV, XML i MHTML.

### <a name="can-i-print-paginated-reports"></a>Czy mogę drukować raporty podzielone na strony?

Tak, drukowanie jest możliwe dla raportów podzielonych na strony. Dostępne jest także nowe i ulepszone środowisko podglądu wydruku. 

### <a name="are-e-mail-subscriptions-available-yet-for-paginated-reports"></a>Czy subskrypcje e-mail są już dostępne w przypadku raportów podzielonych na strony?

Nie, ale zostaną wkrótce udostępnione.

### <a name="what-features-from-ssrs-will-you-be-supporting-in-the-power-bi-service"></a>Które funkcje usług SSRS będą obsługiwane w usłudze Power BI?

Mamy zamiar wprowadzić równoważność funkcji w większości scenariuszy, ale w przypadku niektórych funkcji usług SSRS i Power BI próba ich dopasowania do istniejących wzorców usług SSRS może nie mieć sensu.  Nie można na przykład zamapować różnych modeli uprawnień usługi Power BI na usługi SSRS.  Podczas podejmowania tego rodzaju decyzji będziemy kierować się opiniami naszych klientów i partnerów.

### <a name="can-i-run-custom-code-in-my-report"></a>Czy mogę uruchamiać kod niestandardowy w raporcie?

Tak, obsługujemy możliwość uruchamiania kodu w raportach tak jak w usługach SSRS.

### <a name="does-this-mean-ssrs-is-going-away"></a>Czy oznacza to, że usługi SSRS zostaną wycofane z użycia?

Absolutnie nie.  Ta nowa oferta udostępnia klientom opartą na chmurze opcję pracy z raportami podzielonymi na strony.  

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Czy mogę używać usługi Power BI Embedded do osadzania raportów podzielonych na strony w hostowanej przez siebie aplikacji?

Planujemy obsługę tego scenariusza przy użyciu istniejących interfejsów API usługi Power BI, ale nie określiliśmy jeszcze przedziału czasu, w którym ten scenariusz będzie dostępny.

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Czy mogę drążyć wskroś z raportu usługi Power BI do raportu podzielonego na strony?

Jeszcze nie, ale mamy w planach obsługę tego scenariusza.

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Czy mogę udostępniać zawartość raportu podzielonego na strony za pośrednictwem aplikacji usługi Power BI?

Obecnie można udostępniać poszczególne raporty podzielone na strony innym użytkownikom za pośrednictwem akcji udostępniania w portalu lub za pomocą paska narzędzi. Nie obsługujemy jeszcze udostępniania w aplikacji, ale ta funkcja jest oczekiwana wkrótce. 

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-to-report-tiles-to-dashboards-work-with-paginated-reports"></a>Czy inne funkcje specyficzne dla raportów w usłudze Power BI, takie jak przypinanie kafelków raportów do pulpitów nawigacyjnych, działają w przypadku raportów podzielonych na strony?

Planujemy, aby raporty w jak największym stopniu obsługiwały te same główne scenariusze w usłudze.  W idealnej sytuacji, chociaż narzędzie do tworzenia raportów jest inne, z perspektywy klienta wybrany raport będzie po prostu kolejnym raportem na liście w portalu. Klienta nie interesuje sposób utworzenia raportu — ważne jest, że może on osiągnąć wybrany cel.  Dobrym przykładem takiej równoważności funkcji jest planowana obsługa komentarzy. Chociaż sama funkcja może działać nieco inaczej dla każdego typu raportu, komentarzy będzie można używać w przypadku obydwu typów.

### <a name="are-you-planning-to-create-a-new-authoring-tool-for-paginated-reports-in-the-power-bi-service--we-cant-do-everything-we-need-to-with-report-builder-today"></a>Czy planujecie opracowanie nowego narzędzia do tworzenia raportów podzielonych na strony w usłudze Power BI?  Obecnie nie możemy wykonywać wszystkich wybranych czynności za pomocą programu Report Builder.

Aktualnie wypróbowujemy różne opcje i szukamy najlepszego narzędzia do obsługi raportów podzielonych na strony w usłudze Power BI. 

### <a name="is-a-migration-tool-planned-so-ssrs-customers-can-move-their-existing-reports-and-assets-to-power-bi"></a>Czy jest planowane narzędzie do migracji, dzięki któremu klienci usług SSRS będą mogli przenosić istniejące raporty i elementy zawartości do usługi Power BI?

Wypróbowujemy różne opcje umożliwiające przenoszenie zawartości do usługi Power BI w zautomatyzowany sposób, ale ta funkcja nie będzie jeszcze dostępna w momencie opublikowania wersji ogólnodostępnej.

### <a name="will-i-ever-be-able-to-create-both-paginated-reports-and-power-bi-reports-in-a-single-authoring-tool"></a>Czy kiedykolwiek będzie możliwe tworzenie raportów podzielonych na strony i raportów usługi Power BI przy użyciu jednego narzędzia do tworzenia?

Prawdopodobnie tak.  Obecnie zapoznajemy się ze sposobami realizacji takiego scenariusza oraz rozważamy możliwość dystrybucji narzędzi do tworzenia jako pojedynczego pakietu do analizy biznesowej w porównaniu z opcją pojedynczych operacji pobierania/znakowania.

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Czy w usłudze Power BI istnieje kontrolka przeglądarki raportów na potrzeby raportów podzielonych na strony?

Nie, kontrolka przeglądarki raportów nie jest obecnie dostępna.

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Czy mogę wyszukiwać raporty podzielone na strony w nowym środowisku strony głównej w usłudze Power BI?

Nie, obecnie nie można wyszukiwać raportów podzielonych na strony z poziomu strony głównej.  Są one jednak widoczne w innych częściach nowego środowiska strony głównej.

## <a name="next-steps"></a>Następne kroki

- [Install Report Builder from the Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613) (Instalowanie programu Report Builder z Centrum pobierania Microsoft)
- [Samouczek: Tworzenie raportu podzielonego na strony](paginated-reports-quickstart-aw.md)
