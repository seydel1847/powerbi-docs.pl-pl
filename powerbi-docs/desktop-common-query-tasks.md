---
title: Typowe zadania dotyczące zapytań w programie Power BI Desktop
description: Typowe zadania dotyczące zapytań w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: fde23a47bb0f4034e213a652d60241ff625921d3
ms.sourcegitcommit: 001ea0ef95fdd4382602bfdae74c686de7dc3bd8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2018
ms.locfileid: "38877336"
---
# <a name="common-query-tasks-in-power-bi-desktop"></a>Typowe zadania dotyczące zapytań w programie Power BI Desktop
Podczas pracy w oknie **Edytora zapytań** programu Power BI Desktop dostępnych jest kilka przydatnych, typowych zadań. W tym dokumencie przedstawiono te zadania i podano linki umożliwiające uzyskanie dodatkowych informacji. 

Typowe zadania dotyczące zapytań są następujące:

* Łączenie się z danymi
* Kształtowanie i łączenie danych
* Grupowanie wierszy
* Przestawianie kolumn
* Tworzenie niestandardowych kolumn
* Formuły zapytań

W celu wykonania tych zadań użyjemy kilka połączeń z danymi. Jeśli chcesz samodzielnie wykonać poszczególne kroki tych zadań, możesz pobrać te dane lub połączyć się z nimi.

Docelowym elementem pierwszego połączenia z danymi jest skoroszyt programu Excel. W drugim przypadku połączenie jest nawiązywane z zasobem internetowym (używanym również w innych artykułach dotyczących pomocy programu Power BI Desktop), dostępnym tutaj:

[*http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx*](http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx)

Kroki nawiązywania połączenia z obydwoma źródłami danych można wykonać przy użyciu typowych zadań dotyczących zapytań.

## <a name="connect-to-data"></a>Łączenie się z danymi
Aby połączyć się z danymi w programie Power BI Desktop, wybierz przycisk **Pobierz dane** na karcie **Narzędzia główne** na wstążce. Program Power BI Desktop wyświetli menu z typowymi źródłami danych. Aby uzyskać pełną listę źródeł danych obsługiwanych przez program Power BI Desktop, wybierz przycisk **Więcej** znajdujący się u dołu menu. Aby uzyskać więcej informacji, zobacz [Źródła danych w programie Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-data-sources).

![](media/desktop-common-query-tasks/commonquerytasks_getdata.png)

Na początku wybierz pozycję **Excel** i przejdź do skoroszytu, a następnie wybierz go. Zapytanie sprawdzi skoroszyt i przedstawi znalezione dane w oknie **Nawigator**.

![](media/desktop-common-query-tasks/commonquerytasks_navigator.png)

Przed załadowaniem danych do programu Power BI Desktop możesz je *ukształtować* lub dostosować, wybierając pozycję **Edytuj**. Edytowanie zapytania jest szczególnie przydatne podczas pracy z dużymi zestawami danych, które wymagają okrojenia przed załadowaniem. Właśnie o to nam chodzi, dlatego wybierzemy pozycję **Edytuj**.

Nawiązywanie połączenia z różnymi typami danych również jest proste. Chcemy też połączyć się z zasobem internetowym. Wybierz pozycję **Pobierz dane \> Więcej**, a następnie wybierz pozycję **Inne \> Sieć Web**.

![](media/desktop-common-query-tasks/commonquerytasks_getdata_other.png)

Zostanie wyświetlone okno **Z sieci Web**, w którym można wpisać adres URL strony internetowej.

![](media/desktop-common-query-tasks/datasources_fromwebbox.png)

Wybierz przycisk **OK**. Tak jak poprzednio, program Power BI Desktop przeanalizuje skoroszyt i przedstawi znalezione dane w oknie **Nawigator**.

Inne połączenia z danymi działają podobnie. Jeśli do nawiązania połączenia z danymi wymagane jest uwierzytelnienie, program Power BI Desktop wyświetla monit o wprowadzenie poświadczeń.

Aby uzyskać szczegółowe instrukcje dotyczące łączenia się z danymi w programie Power BI Desktop, zobacz [Łączenie się z danymi w programie Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-connect-to-data).

## <a name="shape-and-combine-data"></a>Kształtowanie i łączenie danych
Edytor zapytań pozwala łatwo kształtować i łączyć dane. W tej sekcji podano kilka przykładów dotyczących kształtowania danych. Bardziej wyczerpujący opis kształtowania i łączenia danych można znaleźć w temacie **[Kształtowanie i łączenie danych w programie Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-shape-and-combine-data)**.

W poprzedniej sekcji nawiązaliśmy połączenie z dwoma zestawami danych — skoroszytem programu Excel i zasobem internetowym. Po załadowaniu zestawów do Edytora zapytań i wybraniu zapytania ze strony internetowej (z listy dostępnych zapytań w okienku **Zapytania** po lewej stronie okna Edytora zapytań) widać następującą zawartość.

![](media/desktop-common-query-tasks/commonquerytasks_querypaneloaded.png)

Kształtowanie danych polega na przekształcaniu źródła danych do postaci i formatu, który spełnia określone wymagania. W tym przypadku nie potrzebujemy pierwszej kolumny, o nazwie *Header*, dlatego ją usuniemy.

W **Edytorze zapytań** wiele poleceń jest dostępnych na wstążce i w menu kontekstowym wywoływanym prawym przyciskiem myszy. Na przykład po kliknięciu prawym przyciskiem myszy kolumny *Nagłówek* pojawia się menu, które pozwala usunąć tę kolumnę. Można również zaznaczyć kolumnę, a następnie wybrać przycisk **Usuń kolumny** na wstążce.

![](media/desktop-common-query-tasks/commonquerytasks_removecolumns.png)

Istnieje wiele innych metod kształtowania danych w tym zapytaniu. Można usuwać dowolną liczbę górnych lub dolnych wierszy, dodawać i dzielić kolumny, zastępować wartości, a także wykonywać inne zadania umożliwiające odpowiednie kształtowanie danych za pomocą Edytora zapytań.

## <a name="group-rows"></a>Grupowanie wierszy
W Edytorze zapytań wartości z wielu wierszy można grupować w jedną wartość. Może to być przydatne w przypadku podawania liczby oferowanych produktów, całkowitej wartości sprzedaży lub liczby studentów.

W tym przykładzie pogrupujemy wiersze w zestawie danych dotyczących rekrutacji w szkołach. Dane pochodzą ze skoroszytu programu Excel. Zostały ukształtowane w Edytorze zapytań — pozostawiono tylko potrzebne kolumny, zmieniono nazwę tabeli i wykonano kilka innych transformacji.

Chcemy dowiedzieć się, ile placówek edukacyjnych (zarówno w okręgach szkolnych, jak i całych regionach) znajduje się w poszczególnych stanach USA. Wybieramy kolumnę *State Abbr*, a następnie przycisk **Grupuj według** na karcie **Przekształcanie** lub **Narzędzia główne** na wstążce (polecenie **Grupuj według** jest dostępne na obu kartach).

![](media/desktop-common-query-tasks/commonquerytasks_groupby.png)

Okno **Grupowanie według** zostanie wyświetlone. Grupowanie wierszy w Edytorze zapytań powoduje utworzenie nowej kolumny, w której są umieszczane wyniki polecenia **Grupuj według**. Operację **Grupuj według** można dostosować przy użyciu następujących opcji:

1. *Grupuj według* — kolumna, która ma zostać pogrupowana; w Edytorze zapytań została wybrana zaznaczona wcześniej kolumna, ale można ją zmienić w tym oknie na dowolną kolumnę w tabeli.
2. *Nazwa nowej kolumny* — Edytor zapytań sugeruje nazwę na podstawie operacji wykonywanej na grupowanej kolumnie, ale można podać dowolną nazwę nowej kolumny.
3. *Operacja* — w tym miejscu można wskazać operację wykonywaną przez Edytora zapytań.
4. *Dodaj grupowanie* i *Dodaj agregację* — te opcje są wyświetlane po wybraniu opcji **Zaawansowane**. Operacje agregujące (akcje **Grupuj według**) można wykonywać na wielu kolumnach. W jednej operacji w oknie **Grupowanie według** można przeprowadzać wiele agregacji. Edytor zapytań tworzy nową kolumnę (na podstawie opcji wybranych w tym oknie), która jest wynikiem operacji na wielu kolumnach. 

Skorzystaj z przycisku **Dodaj grupowanie** lub **Dodaj agregację**, aby dodać więcej grupowań lub agregacji do operacji **Grupuj według**. Możesz usunąć kolumnę lub agregację, wybierając ikonę **...**, a następnie opcję **Usuń** — spróbuj to wykonać i zobacz, jaki będzie wynik takiego działania.
   
   ![](media/desktop-common-query-tasks/commonquerytasks_groupbynumbered.png)

Po wybraniu przycisku **OK** zapytanie wykonuje operację **Grupuj według** i zwraca wyniki. Jak widać, liczba placówek w każdym z czterech stanów — Ohio, Teksasie, Illinois i Kalifornii — przekracza tysiąc!

![](media/desktop-common-query-tasks/commonquerytasks_groupedresult.png)

Edytor zapytań pozwala usunąć ostatnią operację kształtowania — wystarczy wybrać symbol **X** wyświetlany obok niej. Możesz dowolnie eksperymentować, ponawiając operacje, aż uzyskasz dane ukształtowane w odpowiedni sposób.

## <a name="pivot-columns"></a>Przestawianie kolumn
Program Power BI Desktop umożliwia przestawianie kolumn i utworzenie tabeli, która zawiera zagregowane wartości dla każdej unikatowej wartości w kolumnie. Na przykład jeśli chcesz się dowiedzieć, ile różnych produktów znajduje się w poszczególnych kategoriach, możesz szybko utworzyć tabelę zawierającą potrzebne informacje.

Spójrzmy na przykład. Poniższą tabelę **Products** ukształtowano w celu wyświetlenia unikatowych nazw produktów oraz ich kategorii. Aby utworzyć nową tabelę, zawierającą liczbę produktów z każdej kategorii (na podstawie kolumny *CategoryName*), wybierz kolumnę, a następnie wybierz polecenie **Kolumna przestawna** na karcie **Przekształcanie** na wstążce.

![](media/desktop-common-query-tasks/pivotcolumns_pivotbutton.png)

Zostanie wyświetlone okno **Kolumna przestawna** z informacjami o tym, które wartości z kolumny zostaną użyte do utworzenia nowych kolumn (1). Po rozwinięciu obszaru **Opcje zaawansowane** (2) można wybrać funkcję, która zostanie zastosowana do wartości zagregowanych (3).

![](media/desktop-common-query-tasks/pivotcolumns_pivotdialog.png)

Po wybraniu przycisku **OK** zostanie wyświetlona tabela — wynik instrukcji przekształcania podanych w oknie **Kolumna przestawna**.

![](media/desktop-common-query-tasks/pivotcolumns_pivotcomplete.png)

## <a name="create-custom-columns"></a>Tworzenie niestandardowych kolumn
W Edytorze zapytań można tworzyć niestandardowe formuły, które działają na wielu kolumnach tabeli, a następnie umieszczać wyniki takich formuł w nowej (niestandardowej) kolumnie. Tworzenie niestandardowych kolumn w Edytorze zapytań jest proste.

W Edytorze zapytań na karcie **Dodawanie kolumny** na wstążce wybierz pozycję **Kolumna niestandardowa**.

![](media/desktop-common-query-tasks/commonquerytasks_customcolumn.png)

Zostanie wyświetlone następujące okno. W poniższym przykładzie utworzymy niestandardową kolumnę o nazwie *Percent ELL*, która umożliwia obliczenie, jaki odsetek uczniów uczestniczy w kursach języka angielskiego (ELL, English Language Learners).

![](media/desktop-common-query-tasks/customcolumn_addcustomcolumndialog.png)

Podobnie jak w przypadku wszystkich kroków w Edytorze zapytań, jeśli okaże się, że nowa kolumna niestandardowa nie zawiera oczekiwanych danych, można po prostu usunąć krok z sekcji **Zastosowane kroki** w okienku **Ustawienia zapytania**, wybierając symbol **X** obok kroku **Dodano kolumnę niestandardową**.

![](media/desktop-common-query-tasks/customcolumn_addedappliedstep.png)

## <a name="query-formulas"></a>Formuły zapytań
Można edytować kroki wygenerowane w Edytorze zapytań oraz tworzyć niestandardowe formuły, aby mieć ścisłą kontrolę nad kształtowaniem danych i łączeniem się z nimi. Gdy Edytor zapytań wykonuje jakąś akcję na danych, formuła skojarzona z tą akcją jest wyświetlana na **pasku formuły**. Aby wyświetlić **pasek formuły**, zaznacz pole wyboru obok pozycji **Pasek formuły** na karcie **Widok** na wstążce.

![](media/desktop-common-query-tasks/queryformulas_formulabar.png)

Edytor zapytań przechowuje wszystkie zastosowane kroki poszczególnych zapytań jako tekst, który można wyświetlić lub zmodyfikować. Tekst dowolnego zapytania można wyświetlać lub modyfikować za pomocą **edytora zaawansowanego**, wyświetlanego po wybraniu pozycji **Edytor zaawansowany** na karcie **Widok** na wstążce.

![](media/desktop-common-query-tasks/queryformulas_advancededitorbutton.png)

Poniżej przedstawiono **edytor zaawansowany** z wyświetlonymi krokami zapytania **USA\_StudentEnrollment**. Kroki te utworzono przy użyciu języka formuł dodatku Power Query, często określanego jako język **M**. Aby uzyskać więcej informacji, zobacz [Informacje o formułach dodatku Power Query](https://support.office.com/article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f?ui=en-US&rs=en-US&ad=US). Aby zapoznać się ze specyfikacją języka, zobacz artykuł [Specyfikacja języka formuł dodatku Microsoft Power Query dla programu Excel](http://go.microsoft.com/fwlink/?linkid=320633).

![](media/desktop-common-query-tasks/queryformulas_advancededitor.png)

Program Power BI Desktop udostępnia rozbudowany zestaw kategorii formuł. Więcej informacji oraz pełną dokumentację wszystkich formuł Edytora zapytań można znaleźć na stronie [Kategorie formuł w dodatku Power Query](https://support.office.com/en-in/article/Power-Query-formula-categories-125024ec-873c-47b9-bdfd-b437f8716819).

Poniżej przedstawiono kategorie formuł w Edytorze zapytań:

* Liczba
  * Stałe
  * Informacje
  * Konwersja i formatowanie
  * Format
  * Zaokrąglanie
  * Operacje
  * Losowe
  * Trygonometryczne
  * Bajty
* Tekst
  * Informacje
  * Porównywanie tekstu
  * Wyodrębnianie
  * Modyfikowanie
  * Członkostwo
  * Przekształcenia
* Wartości logiczne
* Data
* Godzina
* Data/godzina
* Data/godzina/strefa czasowa
* Czas trwania
* Rekord
  * Informacje
  * Przekształcenia
  * Wybieranie
  * Serializacja
* Lista
  * Informacje
  * Wybieranie
  * Przekształcenia
  * Członkostwo
  * Operacje na zestawach
  * Porządkowanie
  * Wartości średnie
  * Dodawanie
  * Wartości numeryczne
  * Generatory
* Tabela
  * Konstrukcja tabeli
  * Konwersje
  * Informacje
  * Operacje na wierszach
  * Operacje na kolumnach
  * Członkostwo
* Wartości
* Operacje arytmetyczne
* Typy parametrów
* Metadane
* Dostęp do danych
* Identyfikator URI
* Formaty binarne
  * Odczytywanie liczb
* Binarne
* Linie
* Wyrażenie
* Funkcja
* Błąd
* Funkcja porównująca
* Rozdzielacz
* Funkcja łącząca
* Funkcja zamieniająca
* Typ

## <a name="next-steps"></a>Następne kroki
Przy użyciu programu Power BI Desktop można wykonywać różnorodne zadania. Aby uzyskać więcej informacji na temat jego możliwości, skorzystaj z następujących zasobów:

* [Co to jest Power BI Desktop?](desktop-what-is-desktop.md)
* [Omówienie zapytań w programie Power BI Desktop](desktop-query-overview.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Łączenie się z danymi w programie Power BI Desktop](desktop-connect-to-data.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)

