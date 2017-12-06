Jedną istotną różnicą między językiem **DAX** i językiem formuł programu Excel jest to, że język DAX umożliwia przekazywanie *całych tabel* między wyrażeniami zamiast ograniczać się do pojedynczej wartości. Jednym bardzo przydatnym skutkiem takiego działania jest to, że język DAX umożliwia filtrowanie tabel w swoich wyrażeniach, a następnie pracę z odfiltrowanym zestawem wartości.

![](media/7-6-dax-tables-and-filtering/dax-tables-filtering_1.png)

Za pomocą języka DAX możesz tworzyć całkowicie nowe tabele obliczeniowe, a następnie traktować je jak każdą inną tabelę — w tym tworzyć relacje między nimi i innymi tabelami w swoim modelu danych.

## <a name="dax-table-functions"></a>Funkcje tabel języka DAX
Język DAX zawiera bogaty zestaw funkcji **tabel**, takich jak:

* FILTER
* ALL
* VALUES
* DISTINCT
* RELATEDTABLE

Te funkcje zwracają pełną tabelę, a nie wartość. Zazwyczaj wynik funkcji **tabeli** jest używany do dalszej analizy jako część większego wyrażenia, a nie jako końcowa wartość. Pamiętaj, że jeśli używasz funkcji tabeli, wyniki dziedziczą relacje kolumn.

Dopóki każda funkcja używa tabeli i zwraca tabelę, możesz mieszać funkcje tabeli w swoim wyrażeniu. Na przykład rozważmy następujące wyrażenie w języku DAX:

    FILTER (ALL (Table), Condition)

To wyrażenie zastosuje filtr względem całej tabeli *Table*, ignorując zawartość bieżącego filtru.

Funkcja DISTINCT zwraca odrębne wartości kolumny, które są też widoczne w bieżącym kontekście. W przypadku powyższego przykładu wyrażenia języka DAX użycie funkcji **ALL** w tym wyrażeniu powoduje zignorowanie filtrów, a zastąpienie funkcji **ALL** funkcją **DISTINCT** spowodowałoby ich uwzględnienie.

## <a name="counting-values-with-dax"></a>Zliczanie wartości za pomocą języka DAX
Typowym pytaniem konstruktorów raportów usługi Power BI, na które oczekują odpowiedzi, jest:

* Ile wartości mam dla tej kolumny?

Odpowiedź na to pytanie może być prosta, gdy masz przed sobą wyświetlaną tabelę, ale język DAX ma inne podejście, szczególnie w przypadku, gdy istnieje relacja między tabelami.

Na przykład usługa Power BI i język DAX zawierają wartości, które nie są prawidłowo indeksowane krzyżowo. Jeśli przychodząca relacja jest uszkodzona, język DAX dodaje do powiązanej tabeli nowy wiersz, który ma puste wartości w każdym polu, i łączy ten nowy wiersz z nieindeksowanym wierszem, aby zagwarantować integralność referencyjną. Jeśli funkcja zawiera puste wiersze, tak jak często ma to miejsce podczas używania funkcji **ALL**, te puste wiersze następnie zostaną uwzględnione w liczbie wartości zwracanych dla tej kolumny.

Można również tworzyć całe tabele obliczeniowe, korzystając z funkcji języka DAX. Tabele obliczeniowe utworzone przy użyciu języka DAX wymagają funkcji **NAME** i **TABLE**. Tabele obliczeniowe mogą być używane, jak każda inna tabela, łącznie z ustanawianiem relacji.

> Zawartość wideo dzięki uprzejmości [Alberta Ferrariego, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

