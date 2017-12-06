Usługa Power BI umożliwia tworzenie relacji między wieloma tabelami, w tym tabelami pochodzącymi z całkowicie różnych źródeł danych. Możesz zobaczyć te relacje dla dowolnego modelu danych w widoku **Relacje** programu Power BI Desktop.

![](media/7-5-table-relationships-and-dax/dax-relationships_1.png)

## <a name="dax-relational-functions"></a>Funkcje relacyjne języka DAX
Język DAX ma **funkcje relacyjne**, które umożliwiają interakcje z tabelami mającymi ustalone relacje.

Za pomocą funkcji języka DAX możesz zwracać wartość kolumny lub wszystkie wiersze w relacji.

Na przykład funkcja **TABLE** śledzi relacje i zwraca wartość kolumny, zaś funkcja **RELATEDTABLE** śledzi relacje i zwraca całą tabelę, która jest filtrowana w celu uwzględnienia tylko powiązanych wierszy.

![](media/7-5-table-relationships-and-dax/dax-relationships_2.png)

Funkcja **RELATED** działa na relacjach *wiele do jednego*, zaś funkcja **RELATEDTABLE** jest przeznaczona dla relacji *jeden do wielu*.

Funkcji relacyjnych możesz używać do kompilacji wyrażeń, które zawierają wartości dla wielu tabel. Język DAX zwróci wyniki tych funkcji niezależnie od długości łańcucha relacji.

> Zawartość wideo dzięki uprzejmości [Alberta Ferrariego, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

