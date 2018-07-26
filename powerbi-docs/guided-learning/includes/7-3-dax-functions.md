W języku DAX dostępnych jest wiele funkcji pozwalających kształtować, formować lub w inny sposób analizować Twoje dane. Te funkcje można zgrupować w kilku kategoriach:

* Funkcje **agregacji**
* Funkcje **zliczania**
* Funkcje **logiczne**
* Funkcje **informacyjne**
* Funkcje **tekstowe**
* Funkcje **daty**

Podobnie jak w programie Excel, po rozpoczęciu wpisywania formuły w programie Power BI Desktop na **pasku formuły** wyświetla się lista dostępnych funkcji, aby ułatwić ustalenie, która z dostępnych funkcji ma zostać wybrana. Wówczas za pomocą klawiszy strzałek **w górę** i **w dół** na klawiaturze możesz zaznaczyć dowolną dostępną funkcję, co spowoduje wyświetlenie krótkiego opisu.

Usługa Power BI wyświetla funkcje, które odpowiadają literom wpisanym do danego momentu, dlatego, w przypadku wpisania litery *S*, na liście pojawią się tylko funkcje, które zaczynają się od litery *S*. Jeśli wpiszesz *Su*, tylko funkcje, które *zawierają* sekwencję liter *Su* w nazwie, pojawią się na liście (nie muszą one rozpoczynać się od liter *Su*, wystarczy tylko, że zawierają tę sekwencję liter).

![](media/7-3-dax-functions/dax-functions_1.png)

W ten sposób można łatwo eksperymentować z językiem DAX oraz znaleźć każdą z różnych funkcji języka DAX, które są dostępne w usłudze Power BI. Wystarczy rozpocząć pisanie, a usługa Power BI zapewni pomoc.

Teraz, gdy wiemy, jak rozpocząć formułę języka DAX, przyjrzyjmy się po kolei każdej z tych kategorii funkcji.

## <a name="aggregation-functions"></a>Funkcje agregacji
Język DAX ma wiele funkcji **agregacji**, takich jak często używane funkcje:

* SUM
* AVERAGE
* MIN
* MAX
* SUMX (i inne funkcje typu *X*)

Te funkcje działają tylko na kolumnach liczbowych i zazwyczaj mogą zagregować tylko jedną kolumnę naraz.

Jednak specjalne funkcje agregacji, które kończą się znakiem **X**, takie jak **SUMX**, mogą pracować na wielu kolumnach. Te funkcje iteracyjnie sprawdzają tablę i oceniają wyrażenie dla każdego wiersza.

## <a name="counting-functions"></a>Funkcje zliczania
Często używane funkcje **zliczania** języka DAX są następujące:

* COUNT
* COUNTA
* COUNTBLANK
* COUNTROWS
* DISTINCTCOUNT

Te funkcje zliczają różne elementy, takie jak różne wartości, wartości niepuste i wiersze tabeli.

## <a name="logical-functions"></a>Funkcje logiczne
Kolekcja funkcji **logicznych** w języku DAX obejmuje:

* AND
* LUB
* NOT
* IF
* IFERROR

Te funkcje specjalne można również wyrazić za pomocą *operatorów*. Na przykład funkcję **AND** można wpisać jako znaki **&&** (zastąpić tymi znakami) w formule języka DAX.

Możesz używać operatorów (takich jak **&&**), gdy potrzebujesz więcej niż dwóch warunków w swojej formule, ale w przeciwnym razie najlepszą praktyką jest użycie samej nazwy funkcji (takiej jak **AND**) dla czytelności kodu DAX.

## <a name="information-functions"></a>Funkcje informacyjne
Funkcje **informacyjne** w języku DAX obejmują:

* ISBLANK
* ISNUMBER
* ISTEXT
* ISNONTEXT
* ISERROR

Chociaż te funkcje mogą być użyteczne w niektórych sytuacjach, wartościowa jest wcześniejsza wiedza o typie danych kolumny, a nie poleganie na tych funkcjach, aby zapewnić typ danych.

Język DAX używa funkcji **MAX** i **MIN** zarówno do *agregacji* wartości, jak i *porównania* wartości.

## <a name="text-functions"></a>Funkcje tekstowe
Funkcje **tekstowe** języka DAX są następujące:

* CONCATENTATE
* REPLACE
* SEARCH
* UPPER
* FIXED

Te funkcje **tekstowe** działają bardzo podobnie do funkcji programu Excel, które mają taką samą nazwę, więc jeśli wiesz, jak program Excel obsługuje funkcje tekstowe, jesteś o krok do przodu. Jeśli nie, zawsze możesz eksperymentować z tymi funkcjami w usłudze Power BI i dowiedzieć się więcej o ich działaniu.

## <a name="date-functions"></a>Funkcje daty
Język DAX zawiera następujące funkcje **daty**:

* DATE
* HOUR
* NOW
* EOMONTH
* WEEKDAY

Chociaż te funkcje są przydatne do obliczania i wyodrębniania informacji z wartości *daty*, nie mają zastosowania do analizy czasu, która używa tabeli dat.

> Zawartość wideo dzięki uprzejmości [Alberta Ferrariego, SQLBI](http://www.sqlbi.com/learning-dax)
> 
> 

