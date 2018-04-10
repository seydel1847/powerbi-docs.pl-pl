---
title: Kształtowanie i łączenie danych w programie Power BI Desktop
description: Kształtowanie i łączenie danych w programie Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 01/30/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 0bb2f8a8d9299d525085a8ba7d2ecabdcd9e6c78
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/04/2018
---
# <a name="shape-and-combine-data-in-power-bi-desktop"></a>Kształtowanie i łączenie danych w programie Power BI Desktop
Program **Power BI Desktop** umożliwia nawiązywanie połączeń z wieloma typami źródeł danych, a następnie kształtowanie tych danych w celu spełnienia konkretnych potrzeb. *Kształtowanie* danych oznacza przekształcanie danych, np. zmienianie nazw kolumn lub tabel, zmienianie tekstu na liczby, usuwanie wierszy, ustawianie pierwszego wiersza jako nagłówków i tak dalej. *Łączenie* danych oznacza nawiązywanie połączenia z co najmniej dwoma źródłami danych, kształtowanie danych zgodnie z potrzebami, a następnie konsolidowanie ich do postaci jednego użytecznego zapytania.

W tym artykule omówiono sposób kształtowania zapytania za pomocą programu Power BI Desktop i wyróżniono niektóre najczęściej wykonywane czynności. Zapytanie użyte tutaj zostało opisane bardziej szczegółowo, z uwzględnieniem sposobu tworzenia zapytania od początku, w artykule [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md).

Warto pamiętać, że w **Edytorze zapytań** programu Power BI Desktop bardzo często używane są menu dostępne po kliknięciu prawym przyciskiem myszy oraz wstążka. Większość opcji, które można wybrać we wstążce **Przekształć**, jest również dostępna po kliknięciu prawym przyciskiem myszy elementu (takiego jak kolumna) i wybraniu z menu, które zostanie wyświetlone.

## <a name="shape-data"></a>Kształtowanie danych
Kształtując dane w Edytorze zapytań, udostępniasz instrukcje krok po kroku (wykonywane przez Edytor zapytań), aby dostosować dane, które Edytor zapytań ładuje i prezentuje. Nie wpływa to na oryginalne źródło danych. Dostosowywanie, czyli *kształtowanie*, dotyczy tylko tego konkretnego widoku danych.

Określone kroki (takie jak zmiana nazwy tabeli, przekształcenie typu danych lub usunięcie kolumn) są rejestrowane przez Edytor zapytań, a następnie wykonywane za każdym razem, gdy to zapytanie połączy się ze źródłem danych. Dzięki temu dane są zawsze kształtowane zgodnie z Twoimi instrukcjami. Ten proces odbywa się za każdym, gdy użyjesz funkcji Edytora zapytań programu Power BI Desktop lub gdy dowolny użytkownik użyje Twojego udostępnionego zapytania, na przykład w usłudze **Power BI**. Kroki są przechwytywane sekwencyjnie w okienku **Ustawienia zapytania** w obszarze **Zastosowane kroki**.

Poniższy obraz przedstawia okienko **Ustawienia zapytania** dla zapytania, które zostało ukształtowane — w kilku następnych akapitach przyjrzymy się każdemu z tych kroków.

![](media/desktop-shape-and-combine-data/shapecombine_querysettingsfinished2.png)

Użyjemy danych dotyczących przechodzenia na emeryturę z artykułu [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md), które uzyskaliśmy przez nawiązanie połączenia z internetowym źródłem danych, i ukształtujemy je zgodnie z naszymi potrzebami.

Na początek dodajmy kolumnę niestandardową, aby wyliczyć rangi w oparciu o wszystkie dane traktowane jako równoważne czynniki i porównać ich wartości z istniejącą kolumną _Ranga_.  W tym miejscu znajduje się wstążka **Dodaj kolumnę** ze strzałką wskazującą na przycisk **Kolumna niestandardowa**, który pozwala dodać kolumnę niestandardową.

![](media/desktop-shape-and-combine-data/shapecombine_customcolumn.png)

W oknie dialogowym **Kolumna niestandardowa** w polu **Nazwa nowej kolumny** wprowadź wartość _Nowa ranga_, a w polu **Formuła kolumny niestandardowej** wprowadź następującą wartość:

    ([Cost of living] + [Weather] + [Health care quality] + [Crime] + [Tax] + [Culture] + [Senior] + [#"Well-being"]) / 8

Upewnij się, że komunikat o stanie ma treść: _„Nie wykryto błędów składniowych.”_ i kliknij przycisk **OK**.

![](media/desktop-shape-and-combine-data/shapecombine_customcolumndialog.png)

Aby dane pozostały spójne, dokonajmy przekształcania wartości w nowej kolumnie na liczby całkowite. W celu ich zmiany wystarczy kliknąć nagłówek kolumny prawym przyciskiem myszy i wybrać pozycję **Zmień typ \> Liczba całkowita**. 

Jeśli chcesz zaznaczyć więcej niż jedną kolumnę, najpierw zaznacz jedną z nich, naciśnij i przytrzymaj klawisz **SHIFT**, wybierz dodatkowe przyległe kolumny, a następnie kliknij prawym przyciskiem myszy nagłówek kolumny w celu dokonania zmiany wszystkich zaznaczonych kolumn. Możesz także użyć klawisza **CTRL**, aby wybrać kolumny niesąsiadujące.

![](media/desktop-shape-and-combine-data/shapecombine_changetype2.png)

Możesz również *przekształcić* typy danych w kolumnach z poziomu wstążki **Przekształć**. Oto wstążka **Przekształć** i strzałka wskazująca przycisk **Typ danych**, który umożliwia przekształcenie bieżącego typu danych na inny.

![](media/desktop-shape-and-combine-data/queryoverview_transformribbonarrow.png)

Zwróć uwagę na to, że w obszarze **Ustawienia zapytania** pole **Zastosowane kroki** odzwierciedla wszelkie kroki kształtowania wykonane względem danych. Aby usunąć dowolny krok z procesu kształtowania, po prostu wybierz symbol **X** po lewej stronie kroku. Na poniższej ilustracji pole **Zastosowane kroki** odzwierciedla dotychczasowe kroki: nawiązanie połączenia z witryną internetową (**Źródło**), wybranie tabeli (**Nawigacja**) oraz automatyczną zmianę tekstowych kolumn z liczbami z typu *Tekst* na *Liczba całkowita* (**Zmieniono typ**) wykonaną przez Edytor zapytań podczas ładowania tabeli. Ostatnie dwa kroki pokazują nasze poprzednie działania z operacjami **Dodano kolumnę niestandardową** i **Zmieniono typ1**. 

![](media/desktop-shape-and-combine-data/shapecombine_appliedstepsearly2.png)

Zanim zaczniemy pracę z tym zapytaniem, musimy wprowadzić kilka zmian, aby dostosować jego dane do naszych potrzeb:

* *Dostosujemy klasyfikację przez usunięcie kolumny* — postanowiliśmy, że kolumna **Koszty utrzymania** nie będzie współczynnikiem naszych wyników. Po usunięciu tej kolumny natrafiamy na problem: dane pozostają niezmienione. Problem ten jednak łatwo rozwiązać przy użyciu programu Power BI Desktop, co przy okazji demonstruje działanie świetnej funkcji **Zastosowane kroki** w zapytaniu.
* *Usuniemy kilka błędów* — ponieważ usunęliśmy kolumnę, musimy ponownie dopasować nasze obliczenia w kolumnie **Nowa ranga**. Obejmuje to zmianę formuły.
* *Posortujemy dane* — na podstawie kolumn **Nowa ranga** i **Ranga**. 
* *Zastąpimy dane* — wskażemy sposób zastąpienia określonej wartości oraz potrzebę wstawienia **zastosowanego kroku**.
* *Zmienimy nazwę tabeli* — nazwa **Tabela 0** nie stanowi przydatnego opisu, ale można ją łatwo zmienić.

Aby usunąć kolumnę **Koszty utrzymania**, po prostu zaznacz kolumnę i wybierz kartę **Narzędzia główne** na wstążce, a następnie wybierz opcję **Usuń kolumny**, jak pokazano na poniższej ilustracji.

![](media/desktop-shape-and-combine-data/shapecombine_removecolumnscostofliving.png)

Zwróć uwagę, że wartości w kolumnie _Nowa ranga_ nie zostały zmienione; jest to spowodowane kolejnością kroków. Edytor zapytań rejestruje kroki sekwencyjnie, ale każdy z nich jest niezależny od pozostałych, dlatego każdy **zastosowany krok** można przenieść w górę lub w dół sekwencji. Po prostu kliknij prawym przyciskiem myszy dowolny krok, a Edytor zapytań udostępni menu, w którym można wybrać następujące polecenia: **Zmień nazwę**, **Usuń**, **Usuwaj** **do końca** (usuwa bieżący krok i wszystkie kroki następujące po nim), **Przenieś w górę** oraz **Przenieś w dół**. Przejdź dalej i przenieś w górę ostatni krok _Usunięto kolumny_ bezpośrednio powyżej kroku _Dodano kolumnę niestandardową_.

![](media/desktop-shape-and-combine-data/shapecombine_movestep.png)

Następnie wybierz krok _Dodano kolumnę niestandardową_. Zwróć uwagę, że w danych widoczny jest teraz _Błąd_, którym musimy się zająć. 

![](media/desktop-shape-and-combine-data/shapecombine_error2.png)

Istnieje kilka sposobów na uzyskanie dodatkowych informacji o każdym błędzie. Możesz kliknąć komórkę (nie klikając słowa **Błąd**) albo kliknąć bezpośrednio słowo **Błąd**. Gdy wybierzesz komórkę *bez* klikania słowa **Błąd**, Edytor zapytań wyświetli informacje o błędzie u dołu okna.

![](media/desktop-shape-and-combine-data/shapecombine_errorinfo2.png)

Jeśli klikniesz słowo *Błąd* bezpośrednio, zapytanie utworzy **zastosowany krok** w okienku **Ustawienia zapytania** i wyświetli informacje o błędzie. Nie chcemy iść tą ścieżką, dlatego wybierz opcję **Anuluj**.

Aby naprawić błędy, wybierz kolumnę _Nowa ranga_, a następnie wyświetl formułę danych z kolumny, otwierając wstążkę **Widok** i wybierając pole wyboru **Pasek formuły**. 

![](media/desktop-shape-and-combine-data/shapecombine_formulabar.png)

Teraz możesz usunąć parametr _Koszty utrzymania_ i zmniejszyć o 1 wartość dzielnika, zmieniając formułę na następującą: 

    Table.AddColumn(#"Removed Columns", "New Rank", each ([Weather] + [Health care quality] + [Crime] + [Tax] + [Culture] + [Senior] + [#"Well-being"]) / 7)

Zaznacz zielony znacznik wyboru po lewej stronie pola formuły lub naciśnij klawisz **Enter**. Dane powinny zostać zastąpione przez poprawione wartości, a krok **Dodaj kolumnę niestandardową** powinien teraz zostać wykonany *bez błędów*.

> [!NOTE]
> Alternatywnie możesz użyć opcji **Usuń błędy** (ze wstążki lub menu wywoływanego prawym przyciskiem myszy), co spowoduje usunięcie wszystkich wierszy z błędami. W tym przypadku to polecenie spowodowałoby usunięcie wszystkich wierszy z naszych danych, ale my tego nie chcemy — chcemy je zachować w tabeli.

Teraz musimy posortować dane na podstawie kolumny **Nowa ranga**. Najpierw wybierz ostatni zastosowany krok, **Zmieniono typ1**, aby uzyskać dostęp do najnowszych danych. Następnie wybierz listę rozwijaną znajdującą się obok nagłówka kolumny **Nowa ranga** i wskaż pozycję **Sortuj rosnąco**.

![](media/desktop-shape-and-combine-data/shapecombine_sort.png)

Zauważ, że dane są teraz posortowane według wartości pola **Nowa ranga**.  Jednak jeśli spojrzysz na kolumnę **Ranga**, zauważysz, że dane nie są prawidłowo posortowane w przypadkach, gdy wartości w polu **Nowa ranga** są równe. Aby rozwiązać ten problem, zaznacz kolumnę **Nowa ranga** i zmień formułę w **Pasku formuły** na następującą:

    = Table.Sort(#"Changed Type1",{{"New Rank", Order.Ascending},{"Rank", Order.Ascending}})

Zaznacz zielony znacznik wyboru po lewej stronie pola formuły lub naciśnij klawisz **Enter**. Wiersze powinny zostać ułożone w kolejności zgodnej z wartościami pól _Nowa ranga_ i _Ranga_.

Dodatkowo możesz wybrać **zastosowany krok** w dowolnym miejscu na liście i kontynuować kształtowanie danych od tego miejsca w sekwencji. Edytor zapytań automatycznie wstawi nowy krok bezpośrednio po aktualnie wybranym **zastosowanym kroku**. Spróbujmy.

Najpierw wybierz **zastosowany krok** przed dodaniem kolumny niestandardowej; będzie to krok _Usunięto kolumnę_. W tym miejscu zastąpimy wartość rankingu _Pogoda_ w Arizonie. Kliknij prawym przyciskiem myszy komórkę, która zawiera wartość rankingu _Pogoda_ dla Arizony i wybierz polecenie *Zamień wartości...* z wyświetlonego menu. Zwróć uwagę na to, który **zastosowany krok** jest aktualnie wybrany (krok poprzedzający krok _Dodano kolumnę niestandardową_).

![](media/desktop-shape-and-combine-data/shapecombine_replacevalues2.png)

Ponieważ wstawiamy krok, Edytor zapytań ostrzega nas o niebezpieczeństwach takiego działania — kolejne kroki mogą spowodować uszkodzenie zapytania. Musimy zachować ostrożność! Ponieważ jest to samouczek i demonstrujemy ciekawą funkcję Edytora zapytań, która umożliwia tworzenie, usuwanie i wstawianie kroków, a także zmianę ich kolejności, wybieramy polecenie **Wstaw**.

![](media/desktop-shape-and-combine-data/shapecombine_insertstep.png)

Zmień wartość na _51_, zastępując poprzednią daną dla Arizony. Gdy tworzysz nowy zastosowany krok, Edytor zapytań nadaje mu nazwę na podstawie akcji — w tym przypadku **Zamieniono wartość**. Gdy w zapytaniu istnieje więcej niż jeden krok o takiej samej nazwie, Edytor zapytań dodaje numer (kolejny) do każdego następnego **zastosowanego kroku**, aby je w ten sposób odróżnić.

Teraz wybierz ostatni **zastosowany krok**, _Posortowano wiersze_, i zwróć uwagę, że dane zostały zmienione: uwzględniają teraz nowy ranking dla Arizony.  Stało się tak, ponieważ umieściliśmy krok _Zastąpiono wartość_ w odpowiednim miejscu przed krokiem _Dodano kolumnę niestandardową_.

To było dosyć wymagające, ale to dobry przykład wszechstronności Edytora zapytań.

Na koniec zmienimy nazwę tabeli na opisową. Gdy będziemy zajmować się tworzeniem raportów, opisowe nazwy tabel będą bardzo przydatne — szczególnie wtedy, gdy połączenia będą nawiązywane z wieloma źródłami danych i wszystkie będą widoczne w okienku **Pola** widoku **Raport**.

Zmiana nazwy tabeli jest łatwa: w okienku **Ustawienia zapytania**, w obszarze **Właściwości**, po prostu wpisz nową nazwę tabeli w sposób pokazany na poniższej ilustracji, a następnie naciśnij klawisz **Enter**. Nadajmy tej tabeli nazwę *RetirementStats*.

![](media/desktop-shape-and-combine-data/shapecombine_renametable2.png)

Ukształtowaliśmy te dane w takim zakresie, w jakim było to potrzebne. Następnie nawiążemy połączenie z innym źródłem danych i połączymy dane.

## <a name="combine-data"></a>Łączenie danych
Dane dotyczące różnych stanów są interesujące i będą użyteczne podczas tworzenia dodatkowych zapytań i analizowania. Jest jednak jeden problem: w większości istniejących danych używane są dwuliterowe skróty kodów stanów, a nie pełne nazwy. Potrzebujemy sposobu na skojarzenie nazw stanów z ich skrótami.

Mamy szczęście: istnieje inne publiczne źródło danych, które właśnie to robi, ale zanim połączymy je z naszą tabelą dotyczącą emerytur, konieczna będzie znaczna ilość operacji w celu ukształtowania danych. Oto zasób internetowy zawierający skróty nazw stanów:

<http://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations>

Ze wstążki **Narzędzia główne** w Edytorze zapytań wybieramy polecenie **Nowe źródło \> Internet** i wpisujemy adres. Następnie wybieramy przycisk **Połącz**, a Nawigator wyświetli to, co znalazł na podanej stronie internetowej.

 ![](media/desktop-shape-and-combine-data/designer_gsg_usstateabbreviationsnavigator2.png)

Wybieramy tabelę **Kody i skróty...**, ponieważ zawiera ona dane, których potrzebujemy, ale dostosowanie danych z tej tabeli do naszych potrzeb będzie wymagało pewnej liczby operacji kształtowania.

> [!TIP]
> Czy istnieje szybszy lub łatwiejszy sposób na wykonanie poniższych kroków? Tak, można utworzyć *relację* między dwiema tabelami i ukształtować dane na podstawie tej relacji. Poniższe kroki w dalszym ciągu idealnie sprawdzają się jako pomoc do nauki pracy z tabelami, ale pamiętaj, że relacje mogą ułatwiać szybkie wykorzystanie danych z wielu tabel.
> 
> 

Aby ukształtować te dane, wykonamy następujące kroki:

* Usuniemy pierwszy wiersz — wynika on ze sposobu utworzenia tabeli na stronie internetowej i nie jest nam potrzebny. Ze wstążki **Narzędzia główne** wybierz polecenie **Zmniejsz wiersze \> Usuń wiersze \> Usuń pierwsze wiersze**.

![](media/desktop-shape-and-combine-data/shapecombine_removetoprows.png)

Zostanie wyświetlone okno **Usuwanie pierwszych wierszy**, w którym można określić liczbę wierszy do usunięcia.

>[!NOTE]
>Jeśli usługa Power BI zaimportuje przypadkowo nagłówki tabeli jako wiersz w tabeli danych, w celu naprawy tabeli możesz wybrać opcję **Użyj pierwszego wiersza jako nagłówków** z karty **Narzędzia główne** lub z karty **Przekształć** na wstążce.

* Usuniemy 26 ostatnich wierszy — wszystkie one dotyczą terytoriów i nie musimy ich uwzględniać. Ze wstążki **Narzędzia główne** wybierz polecenie **Zmniejsz wiersze \> Usuń wiersze \> Usuń końcowe wiersze**.

![](media/desktop-shape-and-combine-data/shapecombine_removebottomrows.png)

* Ponieważ tabela RetirementStats nie zawiera danych dotyczących Dystryktu Kolumbii, musimy go odfiltrować z naszej listy. Wybierz strzałkę listy rozwijanej obok kolumny Region Status, a następnie usuń zaznaczenie pola wyboru obok wartości **Federal district**.

![](media/desktop-shape-and-combine-data/shapecombine_filterdc.png)

* Usuniemy kilka niepotrzebnych kolumn — potrzebujemy tylko odwzorowania stanu na jej oficjalny dwuliterowy skrót, dlatego możemy usunąć następujące kolumny: **Kolumna1**, **Kolumna3**, **Kolumna4** oraz wszystkie kolumny od **Kolumna6** do **Kolumna11**. Najpierw wybierz kolumnę **Kolumna1**, a następnie przytrzymaj naciśnięty klawisz **CTRL** i wybierz pozostałe kolumny do usunięcia (w ten sposób można wybrać wiele kolumn, które ze sobą nie sąsiadują). Na karcie Narzędzia główne na wstążce wybierz polecenie **Usuń kolumny \> Usuń kolumny**.

![](media/desktop-shape-and-combine-data/shapecombine_removecolumns.png)

>[!NOTE]
>To dobry moment na to, aby wspomnieć, że *kolejność* zastosowanych kroków w Edytorze zapytań jest istotna i może wpłynąć na kształt danych. Należy również pamiętać o tym, że jeden krok może wpłynąć na kolejne kroki. Jeśli usuniesz krok z obszaru Zastosowane kroki, kolejne kroki mogą zachowywać się inaczej niż oczekiwano z powodu wpływu sekwencji kroków w zapytaniu.

>[!NOTE]
>Gdy zmieniasz rozmiar okna Edytora zapytań, aby zmniejszyć jego szerokość, niektóre elementy wstążki są zagęszczane w celu najlepszego wykorzystania widocznej przestrzeni. Gdy zwiększasz szerokość okna Edytora zapytań, elementy wstążki rozszerzają się, wykorzystując do maksimum zwiększoną ilość miejsca na wstążce.

* Zmienimy nazwy kolumn i nazwę samej tabeli — jak zwykle, istnieje kilka sposobów na zmianę nazwy kolumny. Najpierw wybierz kolumnę, a następnie polecenie **Zmień nazwę** z karty **Przekształć** na wstążce lub kliknij prawym przyciskiem myszy i wybierz polecenie **Zmień nazwę…** z wyświetlonego menu. Na poniższej ilustracji widoczne są strzałki wskazujące obie opcje. Wystarczy wybrać jedną z nich.

![](media/desktop-shape-and-combine-data/shapecombine_rename.png)

Zmieńmy ich nazwy na *State Name* i *State Code*. Aby zmienić nazwę tabeli, po prostu wpisz nazwę w polu **Nazwa** w okienku **Ustawienia zapytania**. Nadajmy tej tabeli nazwę *StateCodes*.

Ukształtowaliśmy tabelę StateCodes zgodnie z naszymi potrzebami, a teraz możemy połączyć te dwie tabele (zapytania) w jedną. Obecne tabele są wynikiem zapytań zastosowanych względem danych, dlatego często są nazywane *zapytaniami*.

Istnieją dwa podstawowe sposoby łączenia zapytań — *scalanie* i *dołączanie*.

Jeśli masz co najmniej jedną kolumnę, którą chcesz dodać do innego zapytania, **scalasz** zapytania. Jeśli masz dodatkowe wiersze danych, które chcesz dodać do istniejącego zapytania, wówczas **dołączasz** zapytanie.

W tym przypadku chcemy scalić zapytania. Aby rozpocząć, w lewym okienku Edytora zapytań wybieramy zapytanie *docelowe* scalania (zapytanie, do którego mają zostać dodane dane z innego zapytania). W tym przypadku jest to zapytanie *RetirementStats*. Następnie wybieramy polecenie **Połącz \> Scal zapytania** z karty **Narzędzia główne** na wstążce.

![](media/desktop-shape-and-combine-data/shapecombine_mergequeries.png)

Może pojawić się monit dotyczący ustawiania poziomów prywatności w celu zapewnienia, że dane zostaną połączone bez dołączania i przenoszenia danych, których nie chcesz przenosić.

Następnie zostanie wyświetlone okno **Scalanie** z prośbą o wybranie tabeli, która ma zostać scalona z wybraną tabelą, oraz pasujących kolumn na potrzeby scalania. Wybierz kolumnę State z tabeli (zapytania) *RetirementStats*, a następnie zapytanie *StateCodes* (w tym przypadku jest łatwo, ponieważ istnieje tylko jedno inne zapytanie — w przypadku nawiązania połączenia z wieloma źródłami danych istnieje wiele zapytań do wyboru). Gdy wybierzemy poprawne pasujące kolumny — **State** z zapytania *RetirementStats* i **State Name** z zapytania *StateCodes* — wówczas okno **Scalanie** będzie wyglądać podobnie, jak poniższe, a przycisk **OK** będzie włączony.

![](media/desktop-shape-and-combine-data/shapecombine_merge2.png)

Na końcu zapytania zostanie utworzona kolumna **Nowa kolumna**, w której znajduje się zawartość tabeli (zapytania) scalonej z istniejącym zapytaniem. Wszystkie kolumny ze scalonego zapytania są zmniejszone do kolumny **Nowa kolumna**, ale można wybrać opcję **Rozwiń**, aby rozwinąć tabelę i dołączyć dowolne kolumny.

![](media/desktop-shape-and-combine-data/shapecombine_mergenewcolumn.png)

Aby rozwinąć scaloną tabelę i wybrać kolumny do dołączenia, wybierz ikonę Rozwiń (![Rozwiń](media/desktop-shape-and-combine-data/icon.png)). Zostanie wyświetlone okno **Rozwijanie**.

![](media/desktop-shape-and-combine-data/shapecombine_mergeexpand.png)

W tym przypadku potrzebujemy tylko kolumny **State Code**, dlatego wybieramy tylko ją, a następnie przycisk **OK**. Usuwamy zaznaczenie pola wyboru „Użyj oryginalnej nazwy kolumny jako prefiksu”, ponieważ nie potrzebujemy tej opcji. Jeśli to pole pozostanie zaznaczone, scalona kolumna będzie miała nazwę **Nowa kolumna.State Code** (oryginalna nazwa kolumny, czyli **Nowa kolumna**, kropka, a następnie nazwa kolumny wprowadzanej do zapytania).

>[!NOTE]
>Chcesz wypróbować wprowadzanie tej tabeli **Nowa kolumna**? Możesz trochę poeksperymentować, a jeśli nie spodobają Ci się wyniki, po prostu usuń ten krok z listy **Zastosowane kroki** w okienku **Ustawienia zapytania**. Zapytanie wróci do stanu sprzed zastosowania kroku **Rozwiń**. Możesz powtarzać te czynności dowolną liczbę razy, aż dostosujesz proces rozwijania do swoich potrzeb.

Teraz mamy pojedyncze zapytanie (tabelę), które łączy w sobie dwa źródła danych, a każde z nich zostało ukształtowane zgodnie z naszymi potrzebami. To zapytanie może służyć jako podstawa dla wielu dodatkowych, interesujących połączeń danych, takich jak statystyki wydatków na mieszkania, dane demograficzne lub oferty pracy w dowolnym stanie.

Aby zastosować zmiany i zamknąć Edytor zapytań, wybierz pozycję **Zamknij i zastosuj** z karty **Narzędzia główne** na wstążce. Przekształcony zestaw danych zostanie wyświetlony w programie Power BI Desktop i będzie gotowy do użycia na potrzeby tworzenia raportów.

![](media/desktop-shape-and-combine-data/shapecombine_closeandapply.png)

## <a name="next-steps"></a>Następne kroki
Przy użyciu programu Power BI Desktop można wykonywać różnorodne zadania. Aby uzyskać więcej informacji na temat jego możliwości, skorzystaj z następujących zasobów:

* [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md)
* [Omówienie zapytań w programie Power BI Desktop](desktop-query-overview.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Łączenie się z danymi w programie Power BI Desktop](desktop-connect-to-data.md)
* [Typowe zadania dotyczące zapytań w programie Power BI Desktop](desktop-common-query-tasks.md)   

