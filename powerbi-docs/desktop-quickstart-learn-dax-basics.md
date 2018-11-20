---
title: Podstawy języka DAX w programie Power BI Desktop
description: Podstawy języka DAX w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/27/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: a171dd2aa375f8d12830b051dd8ce6437e4b3236
ms.sourcegitcommit: a739a99e1006834a0f56e387c0bd9d945fb8a76b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2018
ms.locfileid: "51679460"
---
# <a name="dax-basics-in-power-bi-desktop"></a>Podstawy języka DAX w programie Power BI Desktop
Niniejszy artykuł jest przeznaczony dla nowych użytkowników programu Power BI Desktop. Artykuł stanowi szybkie i łatwe wprowadzenie do korzystania z języka Data Analysis Expressions (DAX) w celu rozwiązywania szeregu podstawowych problemów z zakresu obliczeń i analizy danych. Zapoznamy się z informacjami koncepcyjnymi, przeanalizujemy szereg zadań, które możesz wykonać, a na koniec zajmiesz się testami, które sprawdzą Twoją wiedzę. Gdy zapoznasz się z tym artykułem, najważniejsze podstawowe pojęcia dotyczące języka DAX nie powinny mieć dla Ciebie żadnych tajemnic.

## <a name="what-is-dax"></a>Czym jest DAX?
DAX jest kolekcją funkcji, operatorów i stałych, które mogą być używane w formułach lub wyrażeniach w celu wykonywania obliczeń i zwracania co najmniej jednej wartości. Mówiąc prościej, DAX ułatwia tworzenie nowych informacji z danych znajdujących się w modelu.

## <a name="why-is-dax-so-important"></a>Dlaczego język DAX jest taki ważny?
Całkiem łatwo można utworzyć nowy plik programu Power BI Desktop i zaimportować do niego jakieś dane. Raporty pokazujące wartościowe szczegółowe informacje można tworzyć bez użycia żadnych formuł języka DAX. Ale w jaki sposób przeanalizować procent wzrostu w różnych kategoriach produktów i dla różnych zakresów dat? Albo obliczyć wzrost rok do roku i porównać go z trendami rynkowymi? Taką możliwość (oraz wiele innych nie miej ważnych możliwości) zapewniają formuły języka DAX. Nauka tworzenia skutecznych formuł języka DAX pomoże Ci maksymalnie wykorzystać posiadane dane. Gdy uzyskasz informacje, które są Ci potrzebne, zaczniesz rozwiązywać rzeczywiste problemy biznesowe, które wpływają na zyski z Twojej działalności. Właśnie na tym polega siła usługi Power BI, a dzięki językowi DAX szybciej poznasz pełnię zalet tej usługi.

## <a name="prerequisites"></a>Wymagania wstępne
Być może wiesz już, jak tworzyć formuły w programie Microsoft Excel. Ta wiedza ułatwi Ci zrozumienie języka DAX, ale jeśli nawet nie posiadasz doświadczenia z formułami programu Excel, to dzięki pojęciom opisanym w niniejszym artykule znacznie łatwiej będzie Ci rozpocząć tworzenie formuł DAX i rozwiązywanie rzeczywistych problemów z dziedziny analityki biznesowej.

Skupimy się na wyjaśnieniu formuł DAX używanych w obliczeniach, a w szczególności w miarach i kolumnach obliczeniowych. Wymagania wstępne są następujące: powinien być Ci znany program Power BI Desktop, musisz wiedzieć, jak importować dane i dodawać pola do raportu, a także znać podstawowe pojęcia [Miara](desktop-measures.md) oraz [Kolumna obliczeniowa](desktop-calculated-columns.md).

**Przykładowy skoroszyt**

Najlepszy sposób na naukę języka DAX polega na utworzeniu kilku podstawowych formuł, użyciu ich z rzeczywistymi danymi i samodzielnym zapoznaniu się z wynikami. Przedstawione tutaj przykłady i zadania są oparte na przykładowym pliku sprzedaży Contoso dla programu Power BI Desktop w wersji zapoznawczej. Jest to ten sam plik, który był wykorzystywany w artykule [Samouczek: tworzenie własnych miar w programie Power BI Desktop](desktop-tutorial-create-measures.md). Oto [przykładowy plik](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20for%20Power%20BI%20Designer.zip) do pobrania.

## <a name="lets-begin"></a>Zacznijmy!
Zrozumienie języka DAX zawęzimy do trzech kluczowych pojęć: *Składnia*, *Funkcje* i *Kontekst*. Oczywiście w języku DAX są inne ważne pojęcia, ale zrozumienie tych trzech zapewni najlepszy fundament, na którym będziemy budować umiejętności korzystania z języka DAX.

### <a name="syntax"></a>Składnia
Zanim zaczniesz tworzyć własne formuły, przyjrzyj się składni formuł języka DAX. Składnia zawiera różne elementy wchodzące w skład formuły — albo po prostu określające sposób pisania formuł. Przyjrzyjmy się prostej formule przykładowej języka DAX dla miary.

![](media/desktop-quickstart-learn-dax-basics/qsdax_1_syntax.png)

Ta formuła zawiera następujące elementy składni:

**A.** Nazwa miary: **Total Sales**.

**B.** Operator znaku równości (**=**) wskazuje początek formuły. Po obliczeniu zwróci on wynik.

**C.** Funkcja języka DAX **SUM** dodaje wszystkie liczby z kolumny **Sales[SalesAmount]**. Więcej informacji na temat funkcji uzyskasz później.

**D.** Nawiasy **()** otaczają wyrażenie zawierające co najmniej jeden argument. Wszystkie funkcje wymagają co najmniej jednego argumentu. Argument przekazuje wartość do funkcji.

**E.** Tabela **Sales**, do której istnieje odwołanie.

**F.** Kolumna **[SalesAmount]**, do której istnieje odwołanie w tabeli Sales. Dzięki temu argumentowi funkcja SUM wie, z której kolumny zostanie obliczona agregacja SUM.

Przy próbie zrozumienia formuły języka DAX często pomocne jest rozbicie poszczególnych elementów na język, w którym codziennie myślimy i mówimy. Tę formułę można na przykład przeczytać w następujący sposób:

> *Dla miary o nazwie Total Sales oblicz (=) sumę SUM wartości w kolumnie [SalesAmount ] tabeli Sales.*
> 
> 

Gdy ta miara zostanie dodana do raportu, obliczy i zwróci wartości poprzez sumowanie kwot sprzedaży dla każdego z innych pól, które dołączymy — na przykład pól Telefony komórkowe w USA.

Być może zadajesz sobie teraz pytanie: „Czy ta miara pełni taką samą rolę jak dodanie pola SalesAmount do raportu?” Tak. Ale istnieje ważny powód, dla którego warto jest utworzyć własną miarę, która będzie sumować wartości z pola SalesAmount: możemy jej użyć jako argumentu w innych formułach. Na tym etapie może się to wydawać zagmatwane, ale w miarę jak Twoje umiejętności dotyczące formuł języka DAX będą rosnąć, wiedza o tym sprawi, że Twoje formuły i modele będą bardziej skuteczne. Prawda jest taka, że miarę Total Sales zobaczysz w roli argumentu również w innych formułach później.

Zajmijmy się kilkoma innymi zagadnieniami dotyczącymi tej formuły. Najważniejsze jest to, że wprowadziliśmy funkcję [SUM](https://msdn.microsoft.com/library/ee634387.aspx). Funkcje są wstępnie napisanymi formułami, które ułatwiają wykonywanie złożonych obliczeń i manipulacji dotyczących liczb, dat, wartości czasu, ciągów tekstowych i innych elementów. Więcej informacji na temat funkcji uzyskasz później.

Widoczne jest również, że kolumna [SalesAmount] była poprzedzona tabelą Sales, do której ta kolumna należy. Jest to nazywane w pełni kwalifikowaną nazwą kolumny, która zawiera nazwę kolumny poprzedzoną nazwą tabeli. W przypadku kolumn, do których istnieją odniesienia w tej samej tabeli, nazwa tabeli nie musi być uwzględniona w formule. Dzięki temu długie formuły zawierające odniesienia do wielu kolumn mogą być krótsze i bardziej czytelne. Jednak warto jest umieszczać nazwy tabel w formułach miar, nawet jeśli dotyczą tej samej tabeli.

> [!NOTE]
> Jeśli nazwa tabeli zawiera spacje, słowa zastrzeżone lub niedozwolone znaki, wówczas konieczne będzie umieszczenie tej nazwy w pojedynczych cudzysłowach. Nazwy tabel należy umieszczać w cudzysłowach także wtedy, gdy nazwa zawiera jakiekolwiek znaki spoza zakresu znaków alfanumerycznych ANSI — bez względu na to, czy obowiązujące ustawienia regionalne obsługują konkretny znak, czy nie.
> 
> 

Ważne jest, aby formuły miały poprawną składnię. Gdy składnia jest niepoprawna, w większości przypadków zostanie zwrócony błąd składniowy. W pozostałych przypadkach składnia może być poprawna, ale zwracane wartości mogą być niezgodne z oczekiwaniami. Edytor języka DAX w programie Power BI Desktop zawiera sugestie; jest to funkcja służąca do tworzenia poprawnych składniowo formuł, która ułatwia wybieranie właściwych elementów.

Teraz zajmiemy się tworzeniem prostej formuły. To zadanie ułatwi Ci dalsze zrozumienie składni formuł. Dzięki niemu dowiesz się również, w jaki sposób może Ci pomóc funkcja sugestii na pasku formuł.

### <a name="task-create-a-measure-formula"></a>Zadanie: tworzenie formuły miary
W celu wykonania tego zadania musisz otworzyć przykładowy plik sprzedaży Contoso dla programu Power BI Desktop.
    
1. W widoku Raport, na liście pól, kliknij prawym przyciskiem myszy w tabeli **Sales**, a następnie kliknij polecenie **Nowa miara**.
    
2. Na pasku formuły zastąp słowo **Miara**, wpisując nazwę nowej miary **Previous Quarter Sales**.
    
3. Po znaku równości wpisz kilka pierwszych liter **CAL**, a następnie dwukrotnie kliknij funkcję, której chcesz użyć. W tej formule chcesz użyć funkcji **CALCULATE**.

   Użyjemy funkcji CALCULATE, aby odfiltrować kwoty, które chcemy zsumować, według argumentu, który przekażemy do funkcji CALCULATE. Taki zapis nazywa się zagnieżdżaniem funkcji. Funkcja CALCULATE ma co najmniej dwa argumenty. Pierwszy jest wyrażeniem, które zostanie ocenione, a drugi jest filtrem.
   
4. Po nawiasie otwierającym **(** funkcji **CALCULATE** wpisz ciąg **SUM**, a następnie inny nawias otwierający **(**. Teraz musimy przekazać argument do funkcji SUM.

5. Rozpocznij wpisywanie ciągu **Sal**, a następnie wybierz pozycję **Sales[SalesAmount]**, po czym wpisz nawias zamykający **)**. Jest to pierwszy argument wyrażenia dla funkcji CALCULATE.
    
6. Wpisz przecinek (**,**), a następnie spację, aby określić pierwszy filtr, po czym wpisz **PREVIOUSQUARTER**. To będzie nasz filtr.
    
   Funkcja analizy czasu PREVIOUSQUARTER posłuży do filtrowania wyników funkcji SUM według poprzedniego kwartału.
    
7. Po nawiasie otwierającym **(** dla funkcji PREVIOUSQUARTER wpisz **Calendar[DateKey]**.
    
   Funkcja PREVIOUSQUARTER ma jeden argument, którym jest kolumna zawierająca ciągły zakres dat. W naszym przypadku jest to kolumna DateKey w tabeli Kalendarz.
    
8. Upewnij się, że oba argumenty przekazywane do funkcji PREVIOUSQUARTER i funkcji CALCULATE są zamknięte po wpisaniu dwóch nawiasów zamykających **))**.
    
   Twoja formuła powinna teraz wyglądać następująco:
    
   **Previous Quarter Sales = CALCULATE(SUM(Sales[SalesAmount]), PREVIOUSQUARTER(Calendar[DateKey]))**
    
9. Kliknij znacznik wyboru ![](media/desktop-quickstart-learn-dax-basics/qsdax_syntax_taskcheckmark.png) na pasku formuły lub naciśnij klawisz Enter, aby zweryfikować formułę i dodać ją do modelu.

Udało Ci się! Utworzona została miara w języku DAX i to wcale nie było łatwe. Ta formuła obliczy łączną sprzedaż w poprzednim kwartale w zależności od filtrów zastosowanych w raporcie. Jeśli na przykład umieścimy kolumnę SalesAmount i naszą nową miarę Previous Quarter Sales na wykresie, a następnie dodamy Year i QuarterOfYear jako fragmentatory, otrzymamy wynik podobny do poniższego:

![](media/desktop-quickstart-learn-dax-basics/qsdax_3_chart.png)

Właśnie poznaliśmy kilka istotnych aspektów formuł języka DAX. Po pierwsze: formuła zawierała dwie funkcje. Zwróć uwagę na to, że funkcja analizy czasu [PREVIOUSQUARTER](https://msdn.microsoft.com/library/ee634385.aspx) jest zagnieżdżona jako argument przekazywany do funkcji filtru [CALCULATE](https://msdn.microsoft.com/library/ee634825.aspx). Formuły języka DAX mogą zawierać maksymalnie 64 zagnieżdżone funkcje. Jest mało prawdopodobne, że jakakolwiek formuła będzie zawierać tak dużo zagnieżdżonych funkcji. W rzeczywistości tworzenie i debugowanie takiej formuły byłoby bardzo trudne, a jej szybkość również nie byłaby największa.

W tej formule użyliśmy również filtrów. Filtry zawężają zakres obliczeń. W tym przypadku wybraliśmy jeden filtr jako argument, który w rzeczywistości jest wynikiem innej funkcji. Więcej na temat filtrów dowiesz się później.

Na koniec użyliśmy funkcji CALCULATE. Jest to jedna z najbardziej zaawansowanych funkcji języka DAX. Tworząc modele i bardziej złożone formuły, prawdopodobnie użyjesz tej funkcji wiele razy. Omawianie funkcji CALCULATE jest poza zakresem niniejszego artykułu, ale zachęcamy do zwrócenia szczególnej uwagi na tę funkcję podczas tworzenia bardziej zaawansowanych formuł w języku DAX.

### <a name="syntax-quickquiz"></a>Szybki test dotyczący składni
1. Do czego służy ten przycisk na pasku formuły?
   
   > ![](media/desktop-quickstart-learn-dax-basics/qsdax_2_syntaxquiz.png)
   > 
   > 
2. Co zawsze otacza nazwę kolumny w formule języka DAX?

Odpowiedzi są podane na końcu tego artykułu.

### <a name="functions"></a>Funkcje
Funkcje to wstępnie zdefiniowane formuły, które wykonują obliczenia, używając konkretnych wartości nazywanych argumentami — w określonej kolejności lub strukturze. Argumenty mogą być innymi funkcjami, innymi formułami, wyrażeniami, odwołaniami do kolumn, liczbami, ciągami tekstowymi, wartościami logicznymi, takimi jak TRUE (Prawda) lub FALSE (Fałsz), albo stałymi.

Język DAX zawiera następujące kategorie funkcji: [Daty i godziny](https://msdn.microsoft.com/library/ee634786.aspx), [Analizy czasowej](https://msdn.microsoft.com/library/ee634763.aspx), [Informacyjne](https://msdn.microsoft.com/library/ee634552.aspx), [Logiczne](https://msdn.microsoft.com/library/ee634365.aspx), [Matematyczne](https://msdn.microsoft.com/library/ee634241.aspx), [Statystyczne](https://msdn.microsoft.com/library/ee634822.aspx), [Tekstowe](https://msdn.microsoft.com/library/ee634938.aspx), [Nadrzędne/podrzędne](https://msdn.microsoft.com/library/mt150102.aspx) oraz [Inne](https://msdn.microsoft.com/library/mt150101.aspx). Jeśli znasz funkcje w formułach programu Excel, wiele funkcji języka DAX będzie wyglądać dla Ciebie znajomo; jednak funkcje języka DAX są wyjątkowe pod następującymi względami:

* Funkcja języka DAX zawsze odwołuje się do kompletnej kolumny lub tabeli. Jeśli chcesz użyć konkretnych wartości z tabeli lub kolumny, możesz dodać do formuły filtry.
* Jeśli musisz dostosowywać obliczenia wiersz po wierszu, wówczas język DAX udostępnia funkcje, dzięki którym możesz użyć wartości bieżącego wiersza albo powiązanej wartości jako rodzaju argumentu, aby wykonać obliczenia zmieniające się w zależności od kontekstu. Więcej na temat kontekstu dowiesz się później.
* Język DAX zawiera wiele funkcji, które zwracają tabelę, a nie wartość. Ta tabela nie jest wyświetlana, ale jest używana w celu zapewnienia danych wejściowych dla innych funkcji. Możesz na przykład pobrać tabelę, a następnie zliczyć w niej odrębne wartości lub obliczyć dynamiczne sumy z wielu filtrowanych tabel lub kolumn.
* Język DAX zawiera różne funkcje analizy czasu. Te funkcje pozwalają definiować lub wybierać zakresy czasu, a także wykonywać dynamiczne obliczenia w oparciu o nie. Możesz na przykład porównywać sumy z równoległych okresów.
* Program Excel zawiera bardzo popularną funkcję o nazwie WYSZUKAJ.PIONOWO. Funkcje DAX nie traktują komórki ani zakresu komórek jak referencji, tak jak funkcja WYSZUKAJ.PIONOWO w programie Excel. Funkcje języka DAX traktują kolumnę lub tabelę jako referencję. Należy pamiętać o tym, że w programie Power BI Desktop pracujemy z użyciem relacyjnego modelu danych. Wyszukiwanie wartości w innej tabeli jest naprawdę dosyć łatwe i w większości przypadków nie trzeba wcale tworzyć formuł.
  
  Jak widać, funkcje języka DAX mogą pomóc w tworzeniu bardzo zaawansowanych formuł. Dotychczas zaledwie wspomnieliśmy o funkcjach. Gdy Twoje umiejętności w zakresie języka DAX wzrosną, będziesz tworzyć formuły z użyciem wielu różnych funkcji. Jednym z najlepszych miejsc na naukę szczegółów dotyczących poszczególnych funkcji języka DAX jest [skorowidz funkcji DAX](https://msdn.microsoft.com/query-bi/dax/data-analysis-expressions-dax-reference).

### <a name="functions-quickquiz"></a>Szybki test dotyczący funkcji
1. Do czego zawsze odwołuje się funkcja?
2. Czy formuła może zawierać więcej niż jedną funkcję?
3. Jakiej kategorii funkcji użyjesz, aby złączyć dwa ciągi tekstowe w jeden?

Odpowiedzi są podane na końcu tego artykułu.

### <a name="context"></a>Kontekst
Kontekst jest jednym z najważniejszych pojęć języka DAX. Istnieją dwa typy kontekstu w języku DAX; kontekst wiersza i kontekstu filtru. Najpierw przyjrzymy się kontekstowi wiersza.

**Kontekst wiersza**

Kontekst wiersza najłatwiej jest traktować jako bieżący wiersz. Ma zastosowanie zawsze, gdy formuła zawiera funkcję, która stosuje filtr w celu identyfikacji pojedynczego wiersza w tabeli. Ta funkcja będzie z założenia stosować kontekst wiersza względem każdego wiersza tabeli, według którego przeprowadza filtrowanie. Ten typ kontekstu wiersza najczęściej ma zastosowanie do miar.

**Kontekst filtru**

Kontekst filtru jest nieco trudniejszy do zrozumienia niż kontekst wiersza. O kontekście filtru najłatwiej jest myśleć jako o co najmniej jednym filtrze stosowanym w obliczeniu, które określa wynik lub wartość.

Kontekst filtru nie istnieje zamiast kontekstu wiersza; ma on zastosowanie obok kontekstu wiersza. Na przykład w celu dalszego zawężenia wartości do uwzględnienia w obliczeniu możemy zastosować kontekst filtru, który nie tylko określi kontekst wiersza, ale również określi tylko konkretną wartość (filtr) w tym kontekście wiersza.

Kontekst filtru można łatwo zauważyć w raportach. Jeśli na przykład dodamy TotalCost (Łączny koszt) do wizualizacji, a następnie dodamy Year (Rok) i Region, wówczas zdefiniujemy kontekst filtru, który wybierze podzbiór danych na podstawie podanego roku i regionu.

Dlaczego kontekst filtru jest tak ważny w języku DAX? Ponieważ kontekst filtru najłatwiej można zastosować, dodając pola do wizualizacji, kontekst filtru można również zastosować w formule języka DAX przez zdefiniowanie filtru używającego funkcji, takich jak ALL, RELATED, FILTER, CALCULATE oraz przez zastosowanie relacji, innych miar i kolumn. Na przykład przyjrzyjmy się następującej formule w mierze o nazwie Store Sales:

![](media/desktop-quickstart-learn-dax-basics/qsdax_4_context.png)

Aby lepiej zrozumieć tę formułę, możemy ją rozbić, podobnie jak inne formuły.

Ta formuła zawiera następujące elementy składni:

**A.** Nazwa miary: **Store Sales**.

**B.** Operator znaku równości (**=**) wskazuje początek formuły.

**C.** Funkcja **CALCULATE** ocenia wyrażenie jako argument w kontekście, który jest modyfikowany przez określone filtry.

**D.** Nawiasy **()** otaczają wyrażenie zawierające co najmniej jeden argument.

**E.** Miara **[Total Sales]** w tej samej tabeli jako wyrażenie. Miara Total Sales ma formułę: =SUM(Sales[SalesAmount]).

**F.** Przecinek (**,**) oddziela pierwszy argument wyrażenia od argumentu filtru.

**G.** W pełni kwalifikowana nazwa kolumny, do której istnieje odwołanie — **Channel[ChannelName]**. Jest to nasz kontekst wiersza. Każdy wiersz w tej kolumnie określa kanał: Store, Online, itp.

**H.** Konkretna wartość **Store** jako filtr. Oto nasz kontekst filtru.

Ta formuła zapewnia, że tylko wartości sprzedaży zdefiniowane przez miarę Total Sales są obliczane tylko dla wierszy kolumny Channel[ChannelName], które zawierają wartość „Store” jako filtr.

Jak możesz sobie wyobrazić, możliwość definiowania kontekstu w formule to przepustka do wykorzystania ogromnego potencjału języka DAX. Jednym z przykładów wykorzystania tej możliwości jest utworzenie odwołania do konkretnej wartości w powiązanej tabeli. Nie martw się, jeśli nie do końca rozumiesz jeszcze kontekst. Gdy będziesz tworzyć własne formuły, lepiej zrozumiesz kontekst i to, dlaczego jest on tak ważny w języku DAX.

### <a name="context-quickquiz"></a>Szybki test dotyczący kontekstu
1. Jakie są dwa typy kontekstu?
2. Czym jest kontekst filtru?
3. Czym jest kontekst wiersza?

Odpowiedzi są podane na końcu tego artykułu.

## <a name="summary"></a>Podsumowanie
Teraz, gdy masz podstawową wiedzę na temat najważniejszych pojęć języka DAX, możesz samodzielnie przystąpić do tworzenia formuł języka DAX dla miar. Nauka języka DAX może rzeczywiście być trudna, ale jest wiele zasobów, z których możesz korzystać. Jeśli przeczytasz niniejszy artykuł i poeksperymentujesz z własnymi formułami, lepiej poznasz inne pojęcia i formuły języka DAX, co ułatwi Ci rozwiązywanie rzeczywistych problemów biznesowych. Istnieje wiele zasobów dotyczących języka DAX; najważniejszym jest [Data Analysis Expressions (DAX) — kompendium](https://msdn.microsoft.com/library/gg413422.aspx).

Język DAX jest w użyciu już od kilku lat w innych narzędziach BI firmy Microsoft, takich jak dodatek Power Pivot i modele tabelaryczne usług Analysis Services, dlatego masz do wyboru naprawdę wiele świetnych źródeł informacji. Więcej informacji można znaleźć w książkach, oficjalnych dokumentach i blogach tworzonych zarówno przez firmę Microsoft, jak i wiodących specjalistów z dziedziny BI. Świetnym miejscem na rozpoczęcie przygody z językiem DAX jest [wiki centrum zasobów języka DAX w witrynie TechNet](http://social.technet.microsoft.com/wiki/contents/articles/dax-resource-center.aspx).

### <a name="quickquiz-answers"></a>Odpowiedzi do pytań z szybkich testów
Składnia:

1. Weryfikuje i wprowadza miarę do modelu.
2. Nawiasy kwadratowe [].

Funkcje:

1. Tabela i kolumna.
2. Tak. Formuła może zawierać maksymalnie 64 zagnieżdżone funkcje.
3. [Funkcje tekstowe](https://msdn.microsoft.com/library/ee634938.aspx).

Kontekst:

1. Kontekst wiersza i kontekst filtru.
2. Co najmniej jeden filtr w obliczeniu, który określa pojedynczą wartość.
3. Bieżący wiersz.

