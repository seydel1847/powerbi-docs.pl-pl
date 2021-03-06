---
title: Podstawowe pojęcia dla projektantów w usłudze Power BI
description: Obszary robocze, pulpity nawigacyjne, raporty, zestawy danych i skoroszyty usługi Power BI.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/18/2018
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 487a67f48913ee774904377956eee85ccbae49fc
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296690"
---
# <a name="basic-concepts-for-designers-in-the-power-bi-service"></a>Podstawowe pojęcia dla projektantów w usłudze Power BI

W tym artykule przyjęto, że jesteś [zarejestrowanym użytkownikiem w usłudze Power BI](service-self-service-signup-for-power-bi.md), który [dodał pewne dane](service-get-data.md). Jeśli nie masz jeszcze żadnych danych, spróbuj zainstalować [przykładowy pakiet zawartości usługi Power BI](sample-datasets.md#the-power-bi-samples-as-content-packs).

![Ekran główny usługi Power BI w przeglądarce](media/service-basic-concepts/power-bi-home-screen.png)

Oto elementy widoczne po otworzeniu usługi Power BI w przeglądarce:

1. Okienko nawigacji (lewy obszar nawigacji)
2. Uruchamianie aplikacji usługi Office 365
3. Przycisk strony głównej usługi Power BI
4. Przyciski ikon, w tym ustawienia, pomoc i opinia
5. Pole wyszukiwania
6. Kafelki z ulubionego pulpitu nawigacyjnego
7. Ulubione oraz często używane pulpity nawigacyjne i raporty

Później przyjrzymy się tym funkcjom dokładniej, a najpierw sprawdzimy niektóre pojęcia dotyczące usługi Power BI.

Możesz też obejrzeć ten film, zanim przeczytasz dalszą część artykułu.  W filmie Will omówi podstawowe pojęcia i przedstawi przewodnik po usłudze Power BI.

<iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>


## <a name="power-bi-concepts"></a>Pojęcia dotyczące usługi Power BI
4 główne bloki konstrukcyjne usługi Power BI to: **_pulpity nawigacyjne_**, **_raporty_**, **_skoroszyty_** i **_zestawy danych_**. Są one podzielone na **_obszary robocze_**. Przed rozpoczęciem omawiania bloków konstrukcyjnych należy zapoznać się z czterema obszarami roboczymi, więc od tego zaczniemy.

## <a name="workspaces"></a>Obszary robocze
Obszary robocze to kontenery pulpitów nawigacyjnych, raportów, skoroszytów i zestawów danych w usłudze Power BI. Istnieją dwa typy obszarów roboczych: *Mój obszar roboczy* i *obszary robocze aplikacji*. Co to jest *aplikacja*? *Aplikacja* usługi Power BI to kolekcja pulpitów nawigacyjnych i raportów utworzona w celu udostępnienia najważniejszych metryk dla organizacji. Aplikacje są interakcyjne, ale nie można ich edytować.

- Obszar *Mój obszar roboczy* to osobisty obszar roboczy dla każdego klienta usługi Power BI do pracy z własną zawartością. Tylko Ty masz dostęp do swojego obszaru Mój obszar roboczy. Z poziomu obszaru Mój obszar roboczy możesz udostępniać pulpity nawigacyjne i raporty. Jeśli chcesz współpracować nad pulpitami nawigacyjnymi i raportami lub utworzyć aplikację, warto pracować w obszarze roboczym aplikacji.      
-  *Obszary robocze aplikacji* służą do wspólnej pracy nad zawartością ze współpracownikami i udostępniania im tej zawartości. Można też w nich tworzyć i publikować aplikacje dla organizacji oraz zarządzać nimi. Pełnią one funkcję tymczasowych obszarów i kontenerów zawartości aplikacji usługi Power BI. Możesz dodawać współpracowników do obszarów roboczych aplikacji oraz współpracować nad pulpitami nawigacyjnymi, raportami, skoroszytami i zestawami danych. Wszyscy członkowie obszaru roboczego aplikacji muszą mieć licencje usługi Power BI Pro, ale użytkownicy aplikacji (współpracownicy mający dostęp do aplikacji) nie muszą mieć licencji Pro.  

Aby dowiedzieć się więcej, zobacz sekcję **Udostępnianie wyników pracy** w spisie treści, począwszy od tekstu [Jak współpracować nad pulpitami nawigacyjnymi i raportami oraz udostępniać je](service-how-to-collaborate-distribute-dashboards-reports.md)


Teraz można przejść do bloków konstrukcyjnych usługi Power BI. Nie możesz mieć pulpitów nawigacyjnych lub raportów bez danych (właściwie możesz mieć puste pulpity nawigacyjne i puste raporty, ale nie będą użyteczne przed dostarczeniem danych), więc rozpocznijmy od **zestawów danych**.

## <a name="datasets"></a>Zestawy danych
*Zestaw danych* jest kolekcją danych, które są *importowane* lub z którymi *nawiązuje się połączenie*. Usługa Power BI umożliwia nawiązywanie połączeń z wszystkimi rodzajami zestawów danych i importowanie ich, a także łączy wszystkie te możliwości w jednym miejscu.  

Zestawy danych są skojarzone z *obszarami roboczymi* — jeden zestaw danych może należeć do wielu obszarów roboczych. Gdy otworzysz obszar roboczy, skojarzone zestawy danych będą wyświetlane na karcie **Zestawy danych**. Każdy z zestawów danych na liście reprezentuje jedno źródło danych, np. skoroszyt programu Excel w usłudze OneDrive, lokalny tabelaryczny zestaw danych SSAS lub zestaw danych programu Salesforce. Istnieje wiele różnych, obsługiwanych zestawów danych. Ponadto nieustannie dodajemy nowe zestawy danych. [Zobacz listę typów zestawów danych, których można używać w usłudze Power BI](service-get-data.md).

W poniższym przykładzie wybrano obszar roboczy aplikacji „Sales and marketing” i kliknięto kartę **Zestawy danych**.

![Wybrano zestawy danych](media/service-basic-concepts/power-bi-datasets.png)

**JEDNEGO** zestawu danych...

* Można używać wielokrotnie w co najmniej jednym obszarze roboczym.
* Można używać w wielu różnych raportach.
* Wizualizacje z tego jednego zestawu danych można wyświetlać w wielu różnych pulpitach nawigacyjnych.

  ![Diagram zestawu danych](media/service-basic-concepts/drawing2.png)

Aby [nawiązać połączenie z zestawem danych lub zaimportować go](service-get-data.md), wybierz pozycję **Pobierz dane** (u dołu lewego paska nawigacyjnego) lub wybierz pozycje **+ Utwórz > Zestaw danych** (w prawym górnym rogu). Postępuj zgodnie z instrukcjami, aby nawiązać połączenie z konkretnym źródłem lub zaimportować je i dodać zestaw danych do aktywnego obszaru roboczego. Nowe zestawy danych są oznaczone żółtą gwiazdką. Praca wykonywana w usłudze Power BI nie zmienia źródłowego zestawu danych.

Jeśli [należysz do **_obszaru roboczego aplikacji_**](service-collaborate-power-bi-workspace.md), zestawy danych dodane przez jednego członka obszaru roboczego będą dostępne dla innych członków obszaru roboczego.

Możesz odświeżać, eksplorować i usuwać zestawy danych oraz zmieniać ich nazwy. Użyj zestawu danych, aby utworzyć raport od podstaw lub przez uruchomienie [szybkiego wglądu w szczegółowe dane](service-insights.md).  Aby sprawdzić, które raporty i pulpity nawigacyjne już używają zestawu danych, wybierz pozycję **Wyświetl powiązane**. Aby eksplorować zestaw danych, wybierz go. Tak właściwie otworzysz zestaw danych w edytorze raportu, w którym będziesz w stanie rozpocząć szczegółowe badanie danych i tworzenie wizualizacji. Przejdźmy do kolejnego tematu — raportów.

### <a name="dig-deeper"></a>Szczegółowe informacje
* [Power BI Premium — co to jest?](service-premium.md)
* [Pobieranie danych dla usługi Power BI](service-get-data.md)
* [Przykładowe zestawy danych dla usługi Power BI](sample-datasets.md)

## <a name="reports"></a>Raporty
Raport usługi Power BI to co najmniej jedna strona wizualizacji, takich jak wykresy liniowe, mapy i mapy drzewa. Wizualizacje są również zwane **_elementami wizualnymi_**. Wszystkie wizualizacje w raporcie pochodzą z jednego zestawu danych. Raporty można tworzyć od podstaw w usłudze Power BI, importować je wraz z pulpitami nawigacyjnymi udostępnianymi przez współpracowników lub tworzyć je podczas nawiązywania połączenia z zestawami danych z programu Excel, Power BI Desktop, bazami danych, aplikacjami SaaS i [aplikacjami](service-get-data.md).  Na przykład po połączeniu ze skoroszytem programu Excel zawierającym arkusze Power View usługa Power BI utworzy raport w oparciu o te arkusze. Ponadto po nawiązaniu połączenia z aplikacją SaaS usługa Power BI zaimportuje wstępnie utworzony raport.

Istnieją dwa tryby umożliwiające wyświetlanie i wchodzenie w interakcję z raportami: [Widok do czytania i Widok do edycji](service-reading-view-and-editing-view.md).  Tylko osoba, która utworzyła raport, współwłaściciele oraz osoby, którym udzielono uprawnień, mają dostęp do wszystkich możliwości związanych z eksplorowaniem, projektowaniem, tworzeniem i udostępnianiem w **_Widoku do edycji_** dla tego raportu. Osoby, którym raport zostanie udostępniony, mogą eksplorować raport i wchodzić z nim w interakcje w **_Widoku do czytania_**.   

Gdy otworzysz obszar roboczy, skojarzone raporty będą wyświetlane na karcie **Raporty**. Każdy raport na liście reprezentuje co najmniej jedną stronę wizualizacji opartą na tylko jednym źródłowym zestawie danych. Aby otworzyć raport, wybierz go.

Gdy otworzysz aplikację, zostanie wyświetlony pulpit nawigacyjny.  Aby uzyskać dostęp do raportu źródłowego, wybierz kafelek pulpitu nawigacyjnego (później zostaną one omówione dokładniej) przypięty z raportu. Nie wszystkie kafelki są przypinane z raportów, więc może być konieczne kliknięcie kilku kafelków w celu znalezienia raportu.

Domyślnie raport jest otwierany w widoku do czytania.  Po prostu wybierz pozycję **Edytuj raport**, aby otworzyć go w widoku do edycji (jeśli masz odpowiednie uprawnienia).

W poniższym przykładzie wybrano obszar roboczy aplikacji „Sales and marketing” i kliknięto kartę **Raporty**.

![Wybrane raporty](media/service-basic-concepts/power-bi-reports.png)

**JEDEN** raport...

* Znajduje się w jednym obszarze roboczym.
* Może być skojarzony z wieloma pulpitami nawigacyjnymi w tym obszarze roboczym (kafelki przypięte z tego raportu mogą pojawiać się na wielu pulpitach nawigacyjnych).
* Może być utworzony przy użyciu danych z jednego zestawu danych. (Nieznacznym wyjątkiem od tej reguły jest aplikacja Power BI Desktop, w której można połączyć więcej niż jeden zestaw danych w pojedynczy raport, a następnie zaimportować ten raport do usługi Power BI).

  ![Diagram raportów](media/service-basic-concepts/drawing3new.png)

### <a name="dig-deeper"></a>Szczegółowe informacje
* [Raporty w usłudze Power BI i programie Power BI Desktop](service-reports.md)
* [Raporty w aplikacjach mobilnych Power BI](mobile-reports-in-the-mobile-apps.md)

## <a name="dashboards"></a>Pulpity nawigacyjne
*Pulpit nawigacyjny* jest elementem tworzonym przez Ciebie **w usłudze Power BI** lub tworzonym i udostępnianym przez współpracownika **w usłudze Power BI**. Jest to jedna kanwa zawierająca zero lub więcej kafelków i widgetów. Każdy kafelek przypięty z raportu lub [sesji pytań i odpowiedzi](power-bi-q-and-a.md) wyświetla jedną [wizualizację](power-bi-report-visualizations.md), która została utworzona na podstawie zestawu danych i przypięta do pulpitu nawigacyjnego. Do pulpitu nawigacyjnego można też przypinać całe strony raportów jako pojedyncze kafelki. Istnieje wiele sposobów na dodanie kafelków do pulpitu nawigacyjnego; zbyt wiele, aby uwzględnić je w tym temacie. Aby dowiedzieć się więcej, zobacz [Kafelki pulpitu nawigacyjnego w usłudze Power BI](service-dashboard-tiles.md).

Dlaczego ludzie tworzą pulpity nawigacyjne?  Poniżej przedstawiono niektóre z powodów:

* Aby zobaczyć, na pierwszy rzut oka, wszystkie informacje wymagane do podejmowania decyzji.
* Aby monitorować najważniejsze informacje dotyczące firmy.
* Aby upewnić się, że wszyscy współpracownicy dysponują tymi samymi informacjami oraz korzystają z tych samych informacji.
* Aby monitorować kondycję firmy, produktu, jednostki biznesowej lub kampanii marketingowej itd.
* Aby utworzyć spersonalizowany widok większego pulpitu nawigacyjnego — zawierający wszystkie ważne metryki.

Gdy otworzysz obszar roboczy, skojarzone pulpity nawigacyjne będą wyświetlane na karcie **Pulpity nawigacyjne**. Aby otworzyć pulpit nawigacyjny, wybierz go. Gdy otworzysz aplikację, zostanie wyświetlony pulpit nawigacyjny.  Każdy pulpit nawigacyjny reprezentuje dostosowany widok przedstawiający podzbiór źródłowych zestawów danych.  Jeśli jesteś właścicielem pulpitu nawigacyjnego, będziesz również mieć uprawnienia do edytowania źródłowych zestawów danych i raportów.  Jeśli pulpit nawigacyjny został Ci udostępniony, będziesz mieć możliwość interakcji z nim i raportami źródłowymi, ale nie będziesz móc zapisywać żadnych zmian.

Istnieje wiele sposobów umożliwiających Tobie lub Twoim współpracownikom [udostępnianie pulpitu nawigacyjnego](service-share-dashboards.md). Usługa Power BI Pro jest wymagana w przypadku udostępniania pulpitu nawigacyjnego oraz może być wymagana w przypadku wyświetlania udostępnionego pulpitu nawigacyjnego.

**JEDEN** pulpit nawigacyjny...

* Jest skojarzony z jednym obszarem roboczym.
* Może wyświetlać wizualizacje z wielu różnych zestawów danych.
* Może wyświetlać wizualizacje z wielu różnych raportów.
* Może wyświetlać wizualizacje przypięte z innych narzędzi (np. programu Excel).

  ![Wybrany pulpit nawigacyjny](media/service-basic-concepts/drawing1.png)

### <a name="dig-deeper"></a>Szczegółowe informacje
* [Tworzenie nowego pustego pulpitu nawigacyjnego i pobieranie danych](service-dashboard-create.md)
* [Duplikowanie pulpitu nawigacyjnego](service-dashboard-copy.md)
* [Tworzenie widoku pulpitu nawigacyjnego dla telefonu](service-create-dashboard-mobile-phone-view.md)


## <a name="workbooks"></a>Skoroszyty
Skoroszyty są specjalnym typem zestawów danych. Niemal wszystkie potrzebne informacje o skoroszytach przedstawiono w powyższej sekcji **Zestawy danych**. Jednak możesz się zastanawiać, dlaczego czasami usługa Power BI klasyfikuje skoroszyt programu Excel jako **zestaw danych**, a czasami jako **skoroszyt**.

Jeśli używasz polecenia **Pobierz dane** w plikach programu Excel, możesz *zaimportować* plik lub *nawiązać z nim połączenie*. Po wybraniu pozycji Połącz skoroszyt pojawi się w usłudze Power BI, podobnie jak w aplikacji Excel Online. Jednak, w przeciwieństwie do programu Excel Online, będziesz mieć dostęp do pewnych doskonałych funkcji ułatwiających przypinanie elementów z arkuszy bezpośrednio do pulpitów nawigacyjnych.

W usłudze Power BI nie możesz edytować swojego skoroszytu. Niemniej jeśli musisz wprowadzić zmiany, możesz kliknąć pozycję Edytuj, a następnie wprowadzić zmiany do swojego skoroszytu w aplikacji Excel Online lub otworzyć go w programie Excel na komputerze. Wszelkie wprowadzone zmiany są zapisywane w skoroszycie w usłudze OneDrive.

### <a name="dig-deeper"></a>Szczegółowe informacje
* [Pobieranie danych z plików skoroszytów programu Excel](service-excel-workbook-files.md)
* [Publikowanie w usłudze Power BI z programu Excel](service-publish-from-excel.md)


## <a name="a-dashboard-in-my-workspace"></a>Pulpit nawigacyjny w lokalizacji Mój obszar roboczy
Omówiliśmy obszary robocze i bloki konstrukcyjne. Teraz połączmy te informacje i przejrzyjmy elementy tworzące środowisko pulpitu nawigacyjnego w usłudze Power BI.

![Usługa Power BI w przeglądarce](media/service-basic-concepts/completenewest.png)

### <a name="1-navigation-pane-left-nav"></a>1. **Lewe okienko nawigacji**
Okienko nawigacji umożliwia znajdowanie obszarów roboczych i bloków konstrukcyjnych usługi Power BI (pulpitów nawigacyjnych, raportów, skoroszytów i zestawów danych) oraz poruszanie się między nimi.  

  ![Okienko nawigacji](media/service-basic-concepts/power-bi-navigation.png)

* Wybierz opcję **Pobierz dane**, aby [dodać zestawy danych, raporty i pulpity nawigacyjne do usługi Power BI](service-get-data.md).
* Rozwiń lub zwiń okienko nawigacji, korzystając z ikony ![ikona okienka nawigacji](media/service-basic-concepts/expand-icon.png).
* Otwórz ulubioną zawartość lub zarządzaj nią przez wybranie pozycji **Ulubione**.
* Wyświetl i otwórz ostatnio odwiedzaną zawartość przez wybranie pozycji **Ostatnio używane**.
* Wyświetl, otwórz lub usuń aplikację przez wybranie pozycji **Aplikacje**.
* Czy współpracownik udostępnił Ci zawartość? Wybierz pozycję **Udostępnione dla mnie**, aby wyszukiwać i sortować tę zawartość w celu znalezienia potrzebnych informacji.
* Wyświetlaj i otwieraj obszary robocze przez wybranie pozycji **Obszary robocze**.

Kliknij następujące elementy:

* Ikonę lub nagłówek, aby otworzyć widok zawartości.
* Strzałkę w prawo (>), aby otworzyć menu wysuwane Ulubione, Ostatnio używane i Obszary robocze.
* Ikonę pagonu, aby wyświetlić przewijaną listę pulpitów nawigacyjnych, raportów, skoroszytów i zestawów danych **Mój obszar roboczy**.

### <a name="2-canvas"></a>2. **Kanwa**
Otwarto pulpit nawigacyjny, dlatego w obszarze kanwy są wyświetlane kafelki wizualizacji. Gdyby na przykład otwarto edytor raportu, w obszarze kanwy byłaby wyświetlana strona raportu.

Pulpity nawigacyjne składają się z [kafelków](service-dashboard-tiles.md).  Kafelki są tworzone w widoku edycji raportu, funkcji pytań i odpowiedzi oraz innych pulpitach nawigacyjnych i mogą być przypinane z programu Excel, SSRS i nie tylko. Specjalnym typem kafelka jest [widget](service-dashboard-add-widget.md), który jest dodawany bezpośrednio do pulpitu nawigacyjnego. Kafelki, które są wyświetlane na pulpicie nawigacyjnym, zostały tam specjalnie umieszczone przez twórcę/właściciela raportu.  Dodawanie kafelka do pulpitu nawigacyjnego jest nazywane *przypinaniem*.

![Kanwa pulpitu nawigacyjnego usługi Power BI](media/service-basic-concepts/canvas.png)

Aby uzyskać więcej informacji, zobacz sekcję [Pulpity nawigacyjne](#dashboards) (powyżej).

### <a name="3-qa-question-box"></a>3. **Pole pytań funkcji pytań i odpowiedzi**
Jednym ze sposobów na eksplorowanie danych jest zadanie pytania i umożliwienie znalezienia odpowiedzi w formie wizualizacji przez funkcję pytań i odpowiedzi usługi Power BI. Funkcja pytań i odpowiedzi umożliwia dodawanie zawartości do pulpitu nawigacyjnego lub raportu.

Funkcja pytań i odpowiedzi wyszukuje odpowiedź w zestawach danych połączonych z pulpitem nawigacyjnym.  Połączony zestaw danych to taki, który ma co najmniej jeden kafelek przypięty do tego pulpitu nawigacyjnego.

![Pole pytań funkcji pytań i odpowiedzi](media/service-basic-concepts/power-bi-qna.png)

Kiedy tylko zaczniesz wpisywać pytanie, funkcja pytań i odpowiedzi przeniesie Cię na stronę funkcji pytań i odpowiedzi. Podczas wpisywania funkcja pytań i odpowiedzi pomaga zadać odpowiednie pytanie i znaleźć najlepszą odpowiedź przy użyciu parafrazowania, automatycznego uzupełniania, sugestii i innych funkcji. Jeśli otrzymasz żądaną wizualizację (odpowiedź), przypnij ją do pulpitu nawigacyjnego. Aby uzyskać więcej informacji, zobacz [Funkcja pytań i odpowiedzi w usłudze Power BI](power-bi-q-and-a.md).

### <a name="4-icon-buttons"></a>4. **Przyciski ikon**
Ikony w prawym górnym rogu stanowią zasoby umożliwiające korzystanie z ustawień, powiadomień, pobierania, pomocy i funkcji przekazywania opinii do zespołu usługi Power BI. Wybierz podwójną strzałkę, aby otworzyć pulpit nawigacyjny w trybie **pełnoekranowym**.  

![przyciski ikon](media/service-basic-concepts/power-bi-icons.png)

### <a name="5-dashboard-title-navigation-path-aka-breadcrumbs"></a>5. **Tytuł pulpitu nawigacyjnego** (ścieżka nawigacji, czyli linki do stron nadrzędnych)
Czasami ustalenie, który obszar roboczy i pulpit nawigacyjny jest aktywny, jest trudne, dlatego usługa Power BI tworzy automatycznie ścieżkę nawigacji.  W tym przykładzie przedstawiono obszar roboczy (Mój obszar roboczy) i tytuł pulpitu nawigacyjnego (Retail Analysis Sample).  W przypadku otwarcia raportu nazwa raportu zostanie dołączona na końcu ścieżki nawigacji.  Każda sekcja ścieżki jest aktywnym hiperlinkiem.  

W tytule pulpitu nawigacyjnego jest wyświetlana ikona „C”. Ten pulpit nawigacyjny zawiera [tag klasyfikacji danych](service-data-classification.md) dla informacji poufnych. Tag identyfikuje poziom poufności i zabezpieczeń danych. Jeśli administrator wyłączył klasyfikację danych, każdy pulpit nawigacyjny będzie mieć ustawiony tag domyślny. Właściciele pulpitu nawigacyjnego powinni zmienić tag zgodnie z poziomem zabezpieczeń ich pulpitu nawigacyjnego.

![Ikona klasyfikacji danych](media/service-basic-concepts/power-bi-title.png)

### <a name="6-office-365-app-launcher"></a>6. **Uruchamianie aplikacji usługi Office 365**
Funkcja uruchamiania aplikacji umożliwia łatwe uzyskiwanie dostępu do wszystkich aplikacji usługi Office 365 jednym kliknięciem. W tym miejscu można szybko uruchomić pocztę e-mail, dokumenty, kalendarz i nie tylko.

![Uruchamianie aplikacji pakietu Office](media/service-basic-concepts/power-bi-waffle.png)

### <a name="7-power-bi-home"></a>7. **Strona główna usługi Power BI**
Wybranie pozycji **Power BI** powoduje powrót do strony głównej usługi Power BI.

   ![„Power BI” w usłudze](media/service-basic-concepts/version-new.png)

### <a name="8-labeled-icon-buttons"></a>8. **Przyciski ikon z etykietami**
Ten obszar ekranu zawiera dodatkowe opcje interakcji z zawartością (w tym przypadku z pulpitem nawigacyjnym).  Oprócz widocznych ikon z etykietami można wybrać wielokropek, co spowoduje wyświetlenie opcji umożliwiających duplikowanie, drukowanie i odświeżanie pulpitu nawigacyjnego oraz innych opcji.

   ![Przyciski ikon z etykietami](media/service-basic-concepts/power-bi-labeled-icons.png)

## <a name="next-steps"></a>Następne kroki
- [Co to jest usługa Power BI?](power-bi-overview.md)  
- [Nawigacja: Poruszanie się po usłudze Power BI](service-the-new-power-bi-experience.md)
- [Power BI — wideo](videos.md)  
- [Edytor raportu — krótki przewodnik](service-the-report-editor-take-a-tour.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)
