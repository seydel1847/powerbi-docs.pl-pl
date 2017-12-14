---
title: "Power BI — podstawowe pojęcia"
description: "Power BI — podstawowe pojęcia"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: B2vd4MQrz4M
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/31/2017
ms.author: mihart
ms.openlocfilehash: f20ea18fb46928bf7533caacf55a0cdb3d761571
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi---basic-concepts-for-power-bi-service"></a>Power BI — podstawowe pojęcia dotyczące usługi Power BI
<!-- Shared newnav Include -->
[!INCLUDE [newnavbydefault](./includes/newnavbydefault.md)]

W tym artykule przyjęto, że użytkownik [zarejestrował się już w usłudze Power BI](service-self-service-signup-for-power-bi.md) i [dodał pewne dane](service-get-data.md).

Po otwarciu usługi Power BI zobaczysz wyświetlony ***pulpit nawigacyjny***. Pulpity nawigacyjne są elementem różniącym się w przypadku usługi Power BI i aplikacji Power BI Desktop.

![](media/service-basic-concepts/completenewer.png)

Najważniejsze funkcje interfejsu użytkownika usługi Power IB:

1. Pasek nawigacyjny
2. Pulpit nawigacyjny z kafelkami
3. Pole pytań funkcji pytań i odpowiedzi
4. Przyciski pomocy i opinii
5. Kafelek pulpitu nawigacyjnego
6. Uruchamianie aplikacji usługi Office 365
7. Przyciski narzędzi głównych usługi Power BI
8. Dodatkowe akcje pulpitu nawigacyjnego

Później przyjrzymy się im dokładniej, a najpierw sprawdzimy niektóre pojęcia dotyczące usługi Power BI.

Możesz też obejrzeć ten film, zanim przeczytasz dalszą część artykułu.  W filmie Will omówi podstawowe pojęcia i przedstawi przewodnik po usłudze Power BI.

<iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>


## <a name="power-bi-concepts"></a>Pojęcia dotyczące usługi Power BI
Trzy główne bloki konstrukcyjne usługi Power BI to: ***pulpity nawigacyjne***, ***raporty*** i ***zestawy danych***. Nie możesz mieć pulpitów nawigacyjnych lub raportów bez danych (właściwie możesz mieć puste pulpity nawigacyjne i puste raporty, ale nie będą zbyt użyteczne przed dostarczeniem danych), więc rozpocznijmy od **zestawów danych**.

## <a name="datasets"></a>Zestawy danych
*Zestaw danych* jest kolekcją danych, które są *importowane* lub z którymi *nawiązuje się połączenie*. Usługa Power BI umożliwia nawiązywanie połączeń z wszystkimi rodzajami zestawów danych i importowanie ich, a także łączy wszystkie te możliwości w jednym miejscu.  

Na pasku nawigacyjnym zestawy danych, z którymi użytkownik nawiązał połączenie lub które zaimportował, znajdują się na liście o nagłówku **Zestawy danych**. Każdy z zestawów danych na liście reprezentuje jedno źródło danych, np. skoroszyt programu Excel w usłudze OneDrive, lokalny tabelaryczny zestaw danych SSAS lub zestaw danych programu Salesforce. Istnieje wiele różnych, obsługiwanych zestawów danych. Ponadto nieustannie dodajemy nowe zestawy danych. [Zobacz listę typów zestawów danych, których można używać w usłudze Power BI](service-get-data.md).

**JEDNEGO** zestawu danych...

* Można używać wiele razy.
* Można używać w wielu różnych raportach.
* Wizualizacje z tego jednego zestawu danych można wyświetlać w wielu różnych pulpitach nawigacyjnych.
  
  ![](media/service-basic-concepts/drawing2.png)

Aby [nawiązać połączenie z zestawem danych lub zaimportować go](service-get-data.md), wybierz opcję **Pobierz dane** (u dołu paska nawigacyjnego) lub wybierz ikonę plusa obok nagłówka **Zestawy danych**. Postępuj zgodnie z instrukcjami, aby nawiązać połączenie z konkretnym źródłem lub zaimportować je i dodać zestaw danych do obszaru roboczego. Nowe zestawy danych są wyświetlane na liście na pasku nawigacyjnym po lewej stronie i są oznaczone żółtą gwiazdką. Praca wykonywana w usłudze Power BI nie zmienia źródłowego zestawu danych.

Jeśli jesteś [częścią ***obszaru roboczego aplikacji***](service-collaborate-power-bi-workspace.md), zestawy danych dodane przez jednego członka obszaru roboczego będą dostępne dla innych członków obszaru roboczego.

Można odświeżać zestawy danych, zmieniać ich nazwy, eksplorować i usuwać je oraz używać ich do tworzenia raportów. Aby eksplorować zestaw danych, wybierz go. Tak właściwie otworzysz zestaw danych w edytorze raportu, w którym będziesz w stanie rozpocząć szczegółowe badanie danych i tworzenie wizualizacji. Przejdźmy do kolejnego tematu — raportów.

### <a name="dig-deeper"></a>Szczegółowe informacje:
* [Power BI Premium — co to jest?](service-premium.md)
* [Pobieranie danych dla usługi Power BI](service-get-data.md)
* [Przykładowe zestawy danych i pakiety zawartości dla usługi Power BI](sample-datasets.md)

## <a name="reports"></a>Raporty
Raport usługi Power BI to co najmniej jedna strona wizualizacji (wykresów i diagramów, np. wykresów liniowych, wykresów kołowych, map w formie drzewa i wielu innych). Wizualizacje są również zwane ***elementami wizualnymi***. Wszystkie wizualizacje w raporcie pochodzą z jednego zestawu danych. Raporty można tworzyć od podstaw w usłudze Power BI, importować je wraz z pulpitami nawigacyjnymi udostępnianymi przez współpracowników lub tworzyć je podczas nawiązywania połączenia z zestawami danych z programu Excel, Power BI Desktop, bazami danych, aplikacjami SaaS i [pakietami zawartości](service-organizational-content-pack-introduction.md).  Na przykład po połączeniu ze skoroszytem programu Excel zawierającym arkusze Power View usługa Power BI utworzy raport w oparciu o te arkusze. Ponadto po nawiązaniu połączenia z aplikacją SaaS usługa Power BI zaimportuje wstępnie utworzony raport.

Istnieją 2 tryby umożliwiające wyświetlanie i wchodzenie w interakcję z raportami: [Widok odczytu](service-report-open-in-reading-view.md) i [Widok edycji](service-interact-with-a-report-in-editing-view.md).  Tylko osoba, która utworzyła raport, współwłaściciele oraz osoby, którym udzielono uprawnień, mają dostęp do wszystkich możliwości związanych z eksplorowaniem, projektowaniem, tworzeniem i udostępnianiem w ***Widoku edycji*** dla tego raportu. Ponadto osoby, którym raport zostanie udostępniony, mogą eksplorować raport i wchodzić z nim w interakcje przy użyciu ***Widoku odczytu***.   

W okienku nawigacji raporty znajdują się na liście o nagłówku **Raporty**. Każdy raport na liście reprezentuje jedną lub więcej stron wizualizacji opartych na jednym lub większej liczbie źródłowych zestawów danych. Aby otworzyć raport, wybierz go. Domyślnie raport zostanie najpierw otworzony w Widoku odczytu.  Po prostu wybierz opcję **Edytuj raport**, aby otworzyć go w Widoku edycji (jeśli masz odpowiednie uprawnienia).  Jeśli udostępniony pulpit nawigacyjny ma raporty, NIE zobaczysz raportu na liście na pasku nawigacyjnym. Zamiast tego otwórz udostępnione raporty bezpośrednio z udostępnionego pulpitu nawigacyjnego, wybierając kafelek pulpitu nawigacyjnego (więcej informacji na ten temat podamy później).

**JEDEN** raport...

* Może być skojarzony z wieloma pulpitami nawigacyjnymi (kafelki przypięte z tego raportu mogą pojawiać się na wielu pulpitach nawigacyjnych).
* Może być utworzony przy użyciu danych z jednego zestawu danych. (Nieznacznym wyjątkiem od tej reguły jest aplikacja Power BI Desktop, w której można połączyć więcej niż jeden zestaw danych w pojedynczy raport, a następnie zaimportować ten raport do usługi Power BI).
  
  ![](media/service-basic-concepts/drawing3new.png)

## <a name="dashboards"></a>Pulpity nawigacyjne
*Pulpit nawigacyjny* jest elementem tworzonym przez użytkownika lub tworzonym i udostępnianym przez współpracownika. Jest to jedna kanwa zawierająca zero lub więcej kafelków i widgetów. Każdy kafelek wyświetla jedną [wizualizację](power-bi-report-visualizations.md), która została utworzona na podstawie zestawu danych i przypięta do pulpitu nawigacyjnego. Istnieje wiele sposobów na dodanie kafelków do pulpitu nawigacyjnego; zbyt wiele, aby uwzględnić je w tym temacie. Aby dowiedzieć się więcej, zobacz [Kafelki pulpitu nawigacyjnego w usłudze Power BI](service-dashboard-tiles.md). 

Ma pasku nawigacyjnym „Twoje” pulpity nawigacyjne są wyświetlane na liście o nagłówku **Pulpity nawigacyjne**. „Twoje” oznacza, że masz do nich dostęp. Niekoniecznie są to pulpity utworzone przez Ciebie. Każdy pulpit nawigacyjny reprezentuje dostosowany widok przedstawiający podzbiór źródłowych zestawów danych.  Jeśli jesteś właścicielem pulpitu nawigacyjnego, będziesz również mieć dostęp do źródłowych zestawów danych, które zostaną wyświetlone na pasku nawigacyjnym w sekcji **Zestawy danych**.  Jeśli pulpit nawigacyjny został Ci udostępniony, obok niego będzie wyświetlana ikona udostępnienia ![](media/service-basic-concepts/sharing-icon.png) oraz, w zależności od sposobu udostępnienia, możesz zobaczyć źródłowe zestawy danych na liście na pasku nawigacyjnym.

> [!NOTE]
> Przypinanie i kafelki zostały omówione bardziej szczegółowo poniżej w sekcji „Pulpit nawigacyjny z kafelkami”.
> 
> 

**JEDEN** pulpit nawigacyjny...

* Może wyświetlać wizualizacje z wielu różnych zestawów danych.
* Może wyświetlać wizualizacje z wielu różnych raportów.
* Może wyświetlać wizualizacje przypięte z innych narzędzi (np. programu Excel).
  
  ![](media/service-basic-concepts/drawing1.png)

### <a name="dig-deeper"></a>Szczegółowe informacje:
**Pulpit nawigacyjny można [utworzyć od podstaw](service-dashboard-create.md)** — poprzez utworzenie nowego, pustego pulpitu nawigacyjnego i pobranie danych. 

**Użytkownik lub współpracownik może utworzyć pulpit nawigacyjny i [udostępnić go](service-share-dashboards.md)** — po zaakceptowaniu zaproszenia udostępniony pulpit nawigacyjny (oraz skojarzony raport i zestaw danych) zostanie dodany do paska nawigacyjnego. Usługa Power BI Pro jest wymagana w przypadku udostępniania pulpitu nawigacyjnego oraz wyświetlania udostępnionego pulpitu nawigacyjnego.

**Czasami pulpity nawigacyjne są importowane wraz z zestawem danych lub są tworzone podczas nawiązywania połączenia z zestawem danych**. Na przykład kreator **Pobieranie danych** dla programu Salesforce zapyta, czy chcesz utworzyć pulpit nawigacyjny i/lub raport na podstawie zestawu danych. 

**Dlaczego ludzie tworzą pulpity nawigacyjne?**  Poniżej przedstawiono niektóre z powodów:

* Aby zobaczyć, na pierwszy rzut oka, wszystkie informacje wymagane do podejmowania decyzji.
* Aby monitorować najważniejsze informacje dotyczące ich firmy.
* Aby upewnić się, że wszyscy współpracownicy są na tej samej stronie i używają tych samych informacji.
* Aby monitorować kondycję firmy, produktu, jednostki biznesowej lub kampanii marketingowej itd.
* Aby tworzyć spersonalizowany widok większego pulpitu nawigacyjnego — zawierający wszystkie ważne metryki.

## <a name="my-workspace"></a>Mój obszar roboczy
Dotarliśmy z powrotem do pulpitu nawigacyjnego i obszaru roboczego usługi Power BI. Przyjrzyjmy się bliżej elementom, które składają się na stronę docelową usługi Power BI.

![](media/service-basic-concepts/completenewer.png)

### <a name="1-navigation-bar-navbar"></a>1. **Pasek nawigacyjny**
Użyj paska nawigacyjnego, aby przechodzić pomiędzy blokami konstrukcyjnymi usługi Power BI: pulpitami nawigacyjnymi, raportami i zestawami danych.  

  ![](media/service-basic-concepts/navpane-new.png)

* Wybierz opcję **Pobierz dane**, aby [dodać zestawy danych, raporty i pulpity nawigacyjne do usługi Power BI](service-get-data.md).
* Rozwiń lub zwiń pasek nawigacyjny, korzystając z tej ikony ![](media/service-basic-concepts/expand-icon.png).
* Użyj opcji **Wyszukiwanie**, aby znaleźć konkretne elementy na pasku nawigacyjnym.
* Wybierz ikonę plusa ![](media/service-basic-concepts/pbi_nancy_plus.png), aby utworzyć nowy pulpit nawigacyjny lub pobrać nowy zestaw danych.
* Wymienione na liście **pulpity nawigacyjne, raporty** oraz **zestawy danych** są dostępne do użycia.  Udostępnione pulpity nawigacyjne są tylko do odczytu i wyświetlają ikonę udostępnienia ![](media/service-basic-concepts/sharing-icon.png).
* Nazwy pulpitu nawigacyjnego, raportu i zestawu danych zazwyczaj pasują do nazwy źródłowego pliku z zestawem danych — ale możesz [je zmienić](service-rename.md).
* Kliknij prawym przyciskiem myszy pulpit nawigacyjny, raport lub zestaw danych, aby wyświetlić menu kontekstowe. 
  
  ![](media/service-basic-concepts/menu.png)

Kliknij jeden raz:

* Nagłówek, aby go zwinąć lub rozwinąć.
* Pulpit nawigacyjny, aby go wyświetlić.
* Raport, aby otworzyć go w widoku odczytu.
* Zestaw danych, aby go eksplorować.

### <a name="2-dashboard-with-tiles"></a>2. **Pulpit nawigacyjny z kafelkami**
Pulpity nawigacyjne składają się z [kafelków](service-dashboard-tiles.md).  Kafelki są tworzone w widoku edycji raportu, funkcji pytań i odpowiedzi, innych pulpitach nawigacyjnych oraz mogą być przypinane z programu Excel, SSRS i innych. Specjalnym typem kafelka jest [widget](service-dashboard-add-widget.md), który jest dodawany bezpośrednio do pulpitu nawigacyjnego. Kafelki, które są wyświetlane na pulpicie nawigacyjnym, zostały tam specjalnie umieszczone przez twórcę/właściciela raportu.  Dodawanie kafelka do pulpitu nawigacyjnego jest nazywane *przypinaniem*.

![](media/service-basic-concepts/canvas.png)

Aby uzyskać więcej informacji, zobacz sekcję **Pulpity nawigacyjne** (powyżej).

### <a name="3-qa-question-box"></a>3. **Pole pytań funkcji pytań i odpowiedzi**
Jednym ze sposobów na eksplorowanie danych jest zadanie pytania i umożliwienie znalezienia odpowiedzi w formie wizualizacji przez funkcję pytań i odpowiedzi usługi Power BI. Funkcji pytań i odpowiedzi nie można używać do dodawania zawartości do raportu — tylko do dodawania zawartości, w formie kafelków, do pulpitów nawigacyjnych.

Funkcja pytań i odpowiedzi wyszukuje odpowiedź w zestawach danych połączonych z pulpitem nawigacyjnym.  Połączony zestaw danych to taki, który ma co najmniej jeden kafelek przypięty do tego pulpitu nawigacyjnego.

![](media/service-basic-concepts/qna.png)

Kiedy tylko zaczniesz wpisywać pytanie, funkcja pytań i odpowiedzi przeniesie Cię na stronę funkcji pytań i odpowiedzi. Podczas wpisywania funkcja pytań i odpowiedzi pomaga zadać odpowiednie pytanie i znaleźć najlepszą odpowiedź przy użyciu parafrazowania, automatycznego uzupełniania, sugestii i innych funkcji. Jeśli otrzymasz żądaną wizualizację (odpowiedź), przypnij ją do pulpitu nawigacyjnego. Aby uzyskać więcej informacji, zobacz [Funkcja pytań i odpowiedzi w usłudze Power BI](service-q-and-a.md).

### <a name="4-full-screen-notifications-settings-downloads-help-and-feedback"></a>4. **Pełny ekran, Powiadomienia, Ustawienia, Pobieranie, Pomoc i Opinie**
Ikony w prawym górnym rogu stanowią zasoby umożliwiające korzystanie z ustawień, powiadomień, pobierania, pomocy i funkcji przekazywania opinii do zespołu usługi Power BI. Wybierz podwójną strzałkę, aby otworzyć pulpit nawigacyjny w trybie **pełnoekranowym**.  

![](media/service-basic-concepts/help-new.png)

### <a name="5-dashboard-title-aka-what-dashboard-is-active"></a>5. **Tytuł pulpitu nawigacyjnego** (Który pulpit nawigacyjny jest aktywny?)
Ustalenie tego, który pulpit nawigacyjny jest aktywny, nie zawsze jest proste.  Tytuł pulpitu nawigacyjnego jest wyświetlany na stronie widoku pulpitu nawigacyjnego, na stronie funkcji pytań i odpowiedzi, w widoku edycji raportu oraz widoku odczytu raportu, a także podczas otwierania zestawu danych.   

![](media/service-basic-concepts/dash-title-new.png)

### <a name="6-office-365-app-launcher"></a>6. **Uruchamianie aplikacji usługi Office 365**
Uruchamianie aplikacji zostało zaprojektowane z myślą o przechodzeniu do aplikacji usługi Office 365.

![](media/service-basic-concepts/basicconcepts2-newer.png)

### <a name="7-power-bi-home"></a>7. **Strona główna usługi Power BI**
Wybranie tej opcji spowoduje powrót do ostatnio wyświetlanego pulpitu nawigacyjnego.

   ![](media/service-basic-concepts/version-new.png)

### <a name="8-options"></a>8. **Opcje**
Ta sekcja obszaru roboczego zawiera ikony umożliwiające wchodzenie w interakcje z pulpitem nawigacyjnym.  Oprócz opcji **Dodaj kafelek**, **Ulubione** i **Udostępnij** można wybrać wielokropek, co spowoduje wyświetlenie opcji umożliwiających duplikowanie, drukowanie i odświeżanie pulpitu nawigacyjnego oraz innych opcji.

   ![](media/service-basic-concepts/options.png)

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)  
[Power BI — wideo](videos.md)  
[Power BI Premium — co to jest?](service-premium.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

