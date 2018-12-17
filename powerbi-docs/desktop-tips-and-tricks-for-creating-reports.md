---
title: Porady i wskazówki dotyczące tworzenia raportów w usłudze Power BI
description: Poznaj najlepsze rozwiązania dotyczące tworzenia raportów w usłudze Power BI i programie Power BI Desktop
author: davidi
manager: kfile
ms.reviewer: willthom
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
ms.openlocfilehash: c68c29449873e22c7e338279e80f049d522ba347
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2018
ms.locfileid: "53026365"
---
# <a name="tips-and-tricks-for-creating-reports-in-power-bi-desktop"></a>Porady i wskazówki dotyczące tworzenia raportów w programie Power BI Desktop
Aby maksymalnie wykorzystać dane, czasami przydaje się trochę pomocy. Przygotowaliśmy kilka porad i wskazówek, z których można korzystać podczas tworzenia raportów w programie Microsoft Power BI Desktop *oraz* programie Microsoft Excel 2016 albo w wersjach Excel 2013 Pro-Plus z włączonym dodatkiem Power Pivot oraz z zainstalowanym i włączonym dodatkiem Power Query. 

## <a name="learning-to-use-the-query-editor"></a>Nauka korzystania z Edytora zapytań
Edytor zapytań w programie Power BI Desktop zapewnia możliwości podobne do tych, które są dostępne w dodatku Power Query w programie Excel 2013. W sekcji pomocy technicznej dotyczącej usługi Power BI jest kilka pomocnych artykułów, ale w celu rozpoczęcia korzystania zachęcamy do zapoznania się z dokumentacją dodatku Power Query w witrynie support.office.com.

Dodatkowe informacje można uzyskać z [centrum zasobów dodatku Power Query](https://support.office.com/article/Microsoft-Power-Query-for-Excel-Help-2b433a85-ddfb-420b-9cda-fe0e60b82a94).

Można również zajrzeć do [skorowidza formuł](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

## <a name="data-types-in-query-editor"></a>Typy danych w Edytorze zapytań
Gdy Edytor zapytań w programie Power BI Desktop jest używany do ładowania danych, program próbuje odgadnąć typ danych.  Gdy używane są formuły, ustawienia typów danych w kolumnach czasami nie są zachowywane. Poprawność typów danych kolumn należy sprawdzać po wykonaniu następujących operacji:  po początkowym załadowaniu danych do karty zapytania, po wybraniu polecenia Pierwszy wiersz jako nagłówek, Dodaj kolumnę, Grupuj według, Scal, Dołącz, a także przed wybraniem polecenia ładowania danych po raz pierwszy.

Jedna kluczowa sprawa, o której należy pamiętać: kursywa w siatce danych nie oznacza, że typ danych jest poprawnie ustawiony — oznacza tylko, że dane nie są traktowane jak tekst.

## <a name="reference-queries-in-the-query-editor"></a>Odwołania do zapytań w Edytorze zapytań
W nawigatorze Edytora zapytań w programie Power BI Desktop kliknięcie prawym przyciskiem myszy jednego z zapytań powoduje udostępnienie opcji „Odwołanie”.  Jest to przydatne z następującej przyczyny:

* gdy pliki są używane jako źródło danych dla zapytania, ścieżka bezwzględna do pliku jest zapisywana w tym zapytaniu. Gdy w przypadku udostępniania lub przenoszenia pliku programu Power BI Desktop lub skoroszytu programu Excel konieczne jest aktualizowanie ścieżek, można zaoszczędzić sporo czasu, aktualizując je tylko raz w zapytaniu, zamiast aktualizować same ścieżki.

Domyślnie wszystkie zapytania są ładowane do arkusza lub do modelu danych programu Excel (albo do obu tych elementów). Niektóre zapytania stanowią tylko kroki pośrednie i nie są przeznaczone dla użytkowników końcowych.  Tak jest często, gdy zapytania są tworzone w sposób opisany powyżej.  Aby kontrolować zachowanie podczas ładowania zapytania, należy kliknąć prawym przyciskiem myszy zapytanie w nawigatorze i przełączać stan opcji „Włącz ładowanie”.  Gdy obok opcji „Włącz ładowanie” nie jest widoczny znacznik wyboru, oznacza to, że zapytanie jest nadal dostępne na karcie zapytań i można go używać z innymi zapytaniami.  Jest to bardzo użyteczne w połączeniu z przekształceniami Scal, Dołącz i Odwołanie.  Jednak wyniki zapytania nie są ładowane do modelu danych, dlatego zapytanie nie zaśmieca listy pól raportu ani modelu danych. 

## <a name="scatter-charts-need-a-point-identifier"></a>Na wykresach punktowych potrzebne są identyfikatory punktów
Posłużymy się przykładem prostej tabeli zawierającej Temperatury oraz Czasy wykonania odczytów. Jeśli takie dane zostaną naniesione bezpośrednio na wykres punktowy, usługa Power BI zagreguje wszystkie wartości w pojedynczy punkt. Aby pokazać poszczególne punkty danych, należy dodać pole do zasobnika Szczegóły w obszarze pól.   Najprościej można to zrobić na karcie zapytania w programie Power BI Desktop, korzystając z opcji „Dodaj kolumnę indeksu” na wstążce „Dodaj kolumnę”. 

## <a name="reference-lines-in-your-report"></a>Linie odwołań w raporcie
W celu zdefiniowania linii odwołania w programie Power BI Desktop można użyć kolumny obliczeniowej.  Wybierz tabelę i kolumnę, w których chcesz utworzyć linię odwołania.  Na wstążce wybierz polecenie „Nowa kolumna”, a na pasku formuły wpisz następującą formułę:

    Target Value = 100

Ta kolumna obliczeniowa zwróci wartość 100 bez względu na to, gdzie zostanie użyta.  Nowa kolumna pojawi się w obszarze Lista pól.  Dodaj do wykresu liniowego kolumnę obliczeniową „Wartość docelowa”, aby pokazać relację dowolnej serii do tej konkretnej linii odwołania.  

## <a name="sort-by-another-column"></a>Sortowanie według innej kolumny
Gdy w usłudze Power BI używasz wartości podzielonej na kategorie (ciąg) dla osi wykresu albo we fragmentatorze lub filtrze, kolejnością domyślną jest porządek alfabetyczny. Jeśli chcesz zmienić tę kolejność, na przykład w przypadku elementów, takich jak dni tygodnia lub miesiące, możesz w programie Power BI Desktop ustawić sortowanie według innej kolumny. Aby dowiedzieć się więcej, zobacz temat [Sortowanie według kolumny w programie Power BI Desktop](desktop-sort-by-column.md).

## <a name="building-maps-more-easily-with-hints-to-bing"></a>Łatwiejsze tworzenie map dzięki wskazówkom do usługi Bing
Usługa Power BI została zintegrowana z usługą Bing w celu zapewnienia domyślnych współrzędnych mapy (w procesie nazywanym geokodowaniem), co ułatwia tworzenie map.  Usługa Bing używa pewnych algorytmów i podpowiedzi, próbując znaleźć właściwą lokalizację, ale cały proces przypomina odgadywanie. Aby zwiększyć prawdopodobieństwo poprawnego geokodowania, skorzystaj z poniższych wskazówek:

Gdy tworzysz mapę, często zajmujesz się nanoszeniem na nią krajów, regionów i miast.  W programie Power BI Desktop, jeśli po utworzeniu oznaczeń geograficznych nadasz kolumnom nazwy, ułatwi to usłudze Bing odgadywanie lokalizacji, którą chcesz wyświetlić. Jeśli na przykład posługujesz się polem z nazwami stanów USA, takimi jak „Kalifornia” i „Waszyngton”, a w wyszukiwaniu zostanie użyte słowo Waszyngton, wówczas usługa Bing może zwrócić lokalizację Dystryktu Kolumbii zamiast stanu Waszyngton.  Nadanie tej kolumnie nazwy „Stan” poprawi geokodowanie.  To samo dotyczy kolumn o nazwach „Kraj” i „Miasto”.   

Niektóre oznaczenia są niejednoznaczne, gdy są rozpatrywane w kontekście wielu krajów/regionów.  W niektórych przypadkach to, co dla jednego kraju/regionu jest „stanem”, może być „województwem”, „powiatem” lub innym oznaczeniem.  W celu zwiększenia dokładności geokodowania możesz tworzyć kolumny, które będą dołączać wiele pól jednocześnie, a następnie wykorzystywać taką zawartość do wykreślania lokalizacji danych.  Przykład może być następujący: zamiast przekazywać tylko „Wiltshire”, możesz przekazywać „Wiltshire, Anglia”, aby uzyskać dokładniejszy wynik geokodowania. 

W usłudze Power BI lub programie Desktop zawsze możesz podawać konkretne długości i szerokości geograficzne.  W takim przypadku musisz również przekazywać pole Lokalizacja, ponieważ w razie jego braku dane będą domyślnie agregowane, dlatego lokalizacje wyznaczone przez długość i szerokość geograficzną mogą być niezgodne z oczekiwaniami.

## <a name="categorizing-geographic-fields-to-hint-bings-geocoding"></a>Kategoryzowanie pól geograficznych w charakterze podpowiedzi dla geokodowania w usłudze Bing
Innym sposobem upewnienia się, że pola są poprawnie geokodowane jest ustawienie dla pól danych kategorii danych.   W programie Power BI Desktop wybierz odpowiednią tabelę, przejdź do wstążki Zaawansowane, a następnie ustaw parametr Kategoria danych na wartość Adres, Miasto, Kontynent, Kraj/region, Powiat, Kod pocztowy, Stan lub Województwo.  Te kategorie danych umożliwiają usłudze Bing poprawne kodowanie danych. Aby dowiedzieć się więcej, zobacz [Kategoryzacja danych w programie Power BI Desktop](desktop-data-categorization.md).

## <a name="better-geocoding-with-more-specific-locations"></a>Lepsze geokodowanie dzięki dokładniejszym lokalizacjom
Czasami nawet ustawienie kategorii danych dla mapowania jest niewystarczające.  Utwórz bardziej szczegółowe lokalizacje, takie jak adres ulicy, używając Edytora zapytań w programie Power BI Desktop.  Użyj funkcji „Dodaj kolumnę”, aby utworzyć kolumnę niestandardową.  Następnie utwórz żądaną lokalizację w następujący sposób: 

    = [Field1] & " " & [Field2]

Następnie możesz używać tego pola wynikowego w wizualizacjach map. Jest to bardzo przydatne w przypadku tworzenia adresów ulicy z pola adresu wysyłkowego, które w zestawach danych są wspólne.  Należy tylko pamiętać, że taka konkatenacja działa tylko z polami tekstowymi.  W razie potrzeby przekształć numer domu na typ danych tekstowych, zanim użyjesz go w celu utworzenia adresu.

## <a name="histograms-in-the-query-stage"></a>Histogramy w etapie zapytania
Istnieje kilka sposobów tworzenia histogramów w programie Power BI Desktop. Zaczniemy od najprostszego, który będzie stanowił podstawę dla bardziej zaawansowanych sposobów:

Najprostsze histogramy — ustal, w którym zapytaniu znajduje się pole, na podstawie którego chcesz utworzyć histogram.  Utwórz nowe zapytanie za pomocą opcji „Odwołanie” i nazwij je „NazwaPola — histogram”. Wybierz opcję „Grupuj według” na wstążce „Przekształć” i wybierz agregację „Zlicz wiersze”.  Upewnij się, że typem danych jest liczba w wynikowej kolumnie agregującej. Następnie utwórz wizualizację tych danych na stronie raportów.  To szybka i łatwa metoda, ale nie sprawdza się w przypadku wielu punktów danych ani nie zapewnia wzajemnego sprzężenia między wizualizacjami.

Definiowanie zasobników umożliwiających utworzenie histogramu — ustal, w którym zapytaniu znajduje się pole, na podstawie którego chcesz utworzyć histogram.  Utwórz nowe zapytanie za pomocą opcji „Odwołanie” i nazwij je „NazwaPola”.  Zdefiniuj zasobniki korzystające z reguły.  Użyj opcji „Dodaj kolumnę niestandardową” na wstążce „Dodaj kolumnę” i utwórz regułę niestandardową.  Prosta reguła podziału na zasobniki może wyglądać tak:

    if([FieldName] \< 2) then "\<2 min" else
    if([FieldName] \< 5) then "\<5 min" else
    if([FieldName] \< 10) then "\<10 min" else
    if([FieldName] \< 30) then "\<30 min" else
    "longer")

Upewnij się, że typem danych jest liczba w wynikowej kolumnie agregującej. Aby uzyskać histogram, możesz użyć techniki grupowania opisanej w sekcji „Najprostsze histogramy”.  Ta opcja pozwala korzystać z większej liczby punktów danych, ale wciąż nie zapewnia sprzężenia.

Definiowanie histogramu, który obsługuje sprzężenie — sprzężenie polega na połączeniu wizualizacji. Gdy użytkownik wybierze punkt danych w bieżącej wizualizacji, następuje wyróżnienie lub odfiltrowanie punktów danych, które są powiązane z wybranym punktem, w pozostałych wizualizacjach na stronie raportu.  Ponieważ manipulowanie danymi odbywa się w czasie wykonywania zapytania, musimy utworzyć relację między tabelami oraz wiedzieć, który element odpowiada zasobnikowi na histogramie i na odwrót.

Rozpocznij od wybrania opcji „Odwołanie” względem zapytania, które zawiera pole, na podstawie którego chcesz utworzyć histogram.  Nowe zapytanie nazwij „Zasobniki”.  W tym przykładzie oryginalne zapytanie nazwiemy „Szczegóły”.  Następnie usuń wszystkie kolumny z wyjątkiem tej, która ma być zasobnikiem dla histogramu.  Wybierz funkcję „Usuń duplikaty” w zapytaniu — dostępnej w menu wywoływanym prawym przyciskiem myszy po wybraniu kolumny — aby pozostałe wartości w kolumnie były unikatowe.   Jeśli masz liczby dziesiętne, możesz najpierw skorzystać z porady dotyczącej definiowania zasobników w celu utworzenia histogramu. Pozwoli to uzyskać zestaw zasobników, którym można łatwo zarządzać.  Sprawdź dane wyświetlane w podglądzie zapytania.  Jeśli widać wartości puste lub wartości null, musisz się ich pozbyć przed utworzeniem relacji.  Zobacz „Tworzenie relacji w przypadku danych z wartościami pustymi lub wartościami null”.   Metoda ta może sprawiać problemy ze względu na konieczność sortowania.  Aby zapewnić poprawne sortowanie zasobników, zobacz „Kolejność sortowania: zapewnianie odpowiedniej kolejności wyświetlania kategorii”.  

>[!NOTE]
>Warto zastanowić się nad kolejnością sortowania przed utworzeniem wizualizacji.   

Następny krok polega na zdefiniowaniu relacji między zapytaniami „Zasobniki” i „Szczegóły” w kolumnie zasobników.  W programie Power BI Desktop kliknij pozycję **Zarządzaj relacjami** na wstążce.  Utwórz relację między zapytaniem „Zasobniki” znajdującym się w lewej tabeli a zapytaniem „Szczegóły” znajdującym się w prawej tabeli, a następnie wybierz pole, na podstawie którego chcesz utworzyć histogram. 

Ostatnim krokiem jest utworzenie histogramu.  Przeciągnij pole Zasobnik z tabeli „Zasobniki”.  Usuń domyślne pole z wynikowego wykresu kolumnowego.  Przeciągnij pole histogramu z tabeli „Szczegóły” do tej samej wizualizacji.  W obszarze pól zmień domyślną agregację na Zlicz.  W wyniku tych czynności otrzymamy histogram. Jeśli utworzysz inną wizualizację, taką jak mapa drzewa, na podstawie tabeli Szczegóły, wybierz punkt danych na mapie drzewa, aby wyróżnić histogram i wyświetlić histogram dla wybranego punktu danych względem trendu w całym zestawie danych.

## <a name="histograms"></a>Histogramy
W programie Power BI Desktop w celu zdefiniowania histogramu możesz użyć pola obliczeniowego.  Wybierz tabelę i kolumnę, na podstawie których chcesz utworzyć histogram.  W obszarze obliczeń wpisz następującą formułę:

> Frequency:=COUNTROWS(\<Nazwa kolumny\>)
> 
> 

Zapisz zmiany i wróć do raportu.  Dodaj nazwę kolumny (\<Nazwa kolumny\>) i nazwę Frequency do tabeli, a następnie przekształć ją na wykres słupkowy.  Upewnij się, że \<Nazwa kolumny\> znajduje się na osi x, a pole obliczeniowe Frequency na osi y.

## <a name="tips-and-tricks-for-creating-relationships-in-power-bi-desktop"></a>Porady i wskazówki dotyczące tworzenia relacji w programie Power BI Desktop
Często podczas ładowania szczegółowych zestawów danych z wielu źródeł pojawiają się problemy, takie jak wartości null, wartości puste i zduplikowane, które uniemożliwiają tworzenie relacji. 

Spójrzmy na przykład: 

Ładujemy zestawy danych z żądań obsługi aktywnego klienta i inny zestaw danych elementów roboczych, które mają następujące schematy:

> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, Status} WorkItems: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName } 
> 
> 

Jeśli chcemy śledzić wszystkie incydenty i elementy robocze powiązane z konkretnym elementem CustomerName, wówczas nie możemy po prostu utworzyć relacji między tymi dwoma zestawami danych.  Niektóre elementy zestawu WorkItems mogą być niepowiązane z elementem CustomerName, dlatego takie pole byłoby puste lub zawierało wartość NULL.  Dla dowolnego elementu CustomerName może istnieć wiele rekordów w zestawach WorkItems i CustomerIncidents.  

### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-null-or-blank-values"></a>Tworzenie relacji w programie Power BI Desktop w przypadku danych z wartościami pustymi lub wartościami null
Często zestawy danych zawierają kolumny z wartościami pustymi lub wartościami null.  Może to spowodować problemy podczas próby użycia relacji.  Zasadniczo możesz rozwiązać te problemy na dwa sposoby.  Można usunąć wiersze, które zawierają wartości null lub puste.  W tym celu można użyć funkcji filtrowania na karcie zapytania lub — jeśli scalasz zapytania — wybrać opcję, która spowoduje zachowanie tylko pasujących wierszy. Alternatywnie możesz zastąpić wartości null lub wartości puste wartościami, które działają w relacjach — zwykle są to ciągi, takie jak „NULL” i „(Blank)”.   W tym przypadku nie ma właściwej metody postępowania — odfiltrowanie wierszy na etapie zapytania usuwa wiersze i może mieć wpływ na statystyki zbiorcze i obliczenia.  Drugie podejście zachowuje te wiersze danych, ale może powodować, że niepowiązane wiersze będą pojawiać się w modelu, prowadząc do błędów obliczeń.  Jeśli zastosujesz drugie rozwiązanie, użyj filtrów odpowiednio w widoku lub wykresie, aby uzyskać dokładne wyniki.  Najważniejsze jest to, aby ocenić, które wiersze powinny zostać zachowane/usunięte i rozważyć wpływ usunięcia lub pozostawienia ich na analizę.  

### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-duplicate-values"></a>Tworzenie relacji w programie Power BI Desktop w przypadku danych z wartościami zduplikowanymi
Często podczas ładowania szczegółowych zestawów danych z wielu źródeł zduplikowane wartości uniemożliwiają tworzenie relacji.  Można tego uniknąć, tworząc tabelę wymiarów zawierającą niepowtarzalne wartości z obu zestawów danych. 

Spójrzmy na przykład: 

Ładujemy zestawy danych z żądań obsługi aktywnego klienta i inny zestaw danych elementów roboczych, które mają następujące schematy:

> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, Status} WorkItems: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName } 
> 
> 

Jeśli chcemy śledzić wszystkie incydenty i elementy robocze powiązane z konkretnym elementem CustomerName, wówczas nie możemy po prostu utworzyć relacji między tymi dwoma zestawami danych.  Niektóre elementy zestawu WorkItems mogą być niepowiązane z elementem CustomerName, dlatego takie pole byłoby puste lub zawierało wartość NULL.  Jeśli w tabeli CustomerNames znajdują się jakiekolwiek wartości puste lub wartość null, utworzenie relacji nadal może być niemożliwe — zobacz temat „Tworzenie relacji w przypadku danych z wartościami pustymi lub wartościami null”.  Dla pojedynczego elementu CustomerName może istnieć wiele zestawów danych WorkItems i CustomerIncidents.  

Aby utworzyć relację w takim przypadku, potrzebujemy zestawu danych logicznych zawierającego wszystkie elementy CustomerName z tych dwóch zestawów danych.  Na karcie zapytania możesz wykonać poniższą procedurę, aby utworzyć logiczny zestaw danych:

1. Zduplikuj oba zapytania, nadając pierwszemu nazwę **Temp**, a drugiemu nazwę **CustomerNames**.
2. W każdym zapytaniu usuń wszystkie kolumny *oprócz* kolumny CustomerName.
3. W każdym zapytaniu użyj polecenia **Usuń duplikaty**.
4. W zapytaniu **CustomerNames** wybierz opcję **Dołącz** na wstążce, a następnie wybierz zapytanie **Temp**.
5. W zapytaniu **CustomerNames** wybierz polecenie **Usuń duplikaty**.

W ten sposób powstała tabela wymiarów, której możesz użyć, aby powiązać zestawy danych CustomerIndicents i WorkItems, a która zawiera wszystkie wartości każdego z nich.  

## <a name="patterns-to-jump-start-your-use-of-the-query-editor"></a>Wzorce pozwalające na szybkie rozpoczęcie korzystania z Edytora zapytań
Edytor zapytań jest bardzo zaawansowany z uwagi na możliwości, jakie oferuje w zakresie kształtowania i czyszczenia danych podczas przygotowywania ich do wizualizacji lub modelowania. Istnieje kilka wzorców, na które należy zwrócić uwagę.

### <a name="temporary-columns-can-be-deleted-after-computing-a-result"></a>Kolumny tymczasowe mogą być usuwane po obliczeniu wyniku
Często potrzebne jest utworzenie w programie Power BI Desktop obliczenia, które przekształci dane z wielu kolumn w pojedynczą nową kolumnę.  Może to być dosyć żmudne.  Jeden łatwy sposób polega na rozbiciu całej operacji na kroki.  Zacznij od zduplikowania kolumn początkowych. Następnie wykonaj kroki tworzenia kolumn tymczasowych. Następnie utwórz kolumnę na wynik końcowy.  Po wykonaniu tych kroków możesz usunąć kolumny tymczasowe, dzięki czemu końcowy zestaw danych nie będzie zaśmiecony. Jest to możliwe, ponieważ karta zapytania wykonuje kroki w kolejności. 

### <a name="duplicate-or-reference-queries-followed-by-merge-to-original-query"></a>Zapytania Duplikuj lub Odwołanie, po których następuje scalenie do zapytania pierwotnego
Czasami przydatne jest obliczenie statystyk podsumowujących dla zestawu danych.  Prosty sposób polega na zduplikowaniu zapytania lub utworzeniu odwołania do zapytania na karcie zapytania. Następnie należy użyć polecenia **Grupuj według**, aby obliczyć statystyki podsumowujące.  Statystyki podsumowujące pomagają normalizować dane w danych oryginalnych, dzięki czemu łatwiej jest je porównywać.  Jest to szczególnie przydatne w przypadku porównywania poszczególnych wartości z całością.  Aby to zrobić, przejdź do oryginalnego zapytania i wybierz opcję scalania.  Następnie scal dane z zapytania statystki podsumowującej, dopasowując elementy do odpowiednich identyfikatorów.  Teraz możesz przystąpić do normalizacji danych zgodnie z potrzebami analizy.

## <a name="using-dax-for-the-first-time"></a>Korzystanie z języka DAX po raz pierwszy
DAX to język formuł obliczeń w programie Power BI Desktop.  Jest zoptymalizowany pod kątem analiz BI.  Różni się nieco od języków, do których przyzwyczajeni są użytkownicy języków zapytań podobnych do SQL. W sieci oraz w literaturze dostępne są bardzo dobre zasoby do nauki języka DAX. 

[Podstawy języka DAX w programie Power BI Desktop](desktop-quickstart-learn-dax-basics.md)

[Data Analysis Expressions (DAX) — kompendium](https://msdn.microsoft.com/library/gg413422.aspx)

[Centrum zasobów języka DAX](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx)
