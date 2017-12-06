Istnieją dwa podstawowe obliczenia, które możesz utworzyć za pomocą języka DAX:

* **kolumny obliczeniowe**
* **miary obliczeniowe**

Przed zagłębieniem się w tworzenie dowolnego z tych elementów warto dobrze poznać składnię języka DAX dla tabel i kolumn, których będziesz używać podczas tworzenia **kolumn obliczeniowych** albo **miar obliczeniowych**.

## <a name="dax-table-and-column-name-syntax"></a>Składnia nazw tabel i kolumn języka DAX
Niezależnie od tego, czy tworzysz nową kolumnę, czy też miarę, ważne jest, aby znać ogólny format nazw tabel w języku DAX:

    'Table Name'[ColumnName]

Jeśli nazwa tabeli zawiera spacje (jak pokazano powyżej), apostrofy wokół tej nazwy są obowiązkowe. Jeśli nazwa tabeli nie zawiera spacji, apostrofy można pominąć, więc składnia wygląda następująco:

    TableName[ColumnName]

Na poniższej ilustracji przedstawiono formułę języka DAX utworzoną w usłudze Power BI:

![](media/7-2-dax-calculation-types/dax-calc-types_1.png)

Możesz również całkowicie pominąć nazwę tabeli i użyć tylko nazwy kolumny, ale nie jest to dobre rozwiązanie, aby uzyskać przejrzyste funkcje (i, w związku z tym, przejrzysty kod języka DAX). Nazwy kolumn muszą zawsze zawierać nawiasy kwadratowe.

Najlepszym rozwiązaniem jest stosowanie *zawsze* następujących zasad:

* Brak spacji w nazwach tabel
* Uwzględnianie nazw tabel w formułach (nie pomijaj ich, chociaż język DAX to umożliwia)

## <a name="creating-calculated-columns"></a>Tworzenie kolumn obliczeniowych
**Kolumny obliczeniowe** są przydatne, jeśli chcesz wyciąć lub odfiltrować wartość, lub jeśli chcesz wykonać obliczenia dla każdego wiersza w tabeli.

Kolumny obliczeniowe możesz tworzyć w programie Power BI Desktop, wybierając pozycję **Nowa kolumna** na karcie **Modelowanie**. Najlepiej korzystać z widoku **Dane** (a nie widoku **Raport** lub **Relacje**), ponieważ widać nowo utworzoną kolumnę, a **pasek formuły** jest wypełniony i gotowy na formułę języka DAX.

![](media/7-2-dax-calculation-types/dax-calc-types_2a.png)

Po naciśnięciu przycisku **Nowa kolumna** **pasek formuły** jest zapełniany nazwą podstawowej kolumny (którą oczywiście zmienisz, aby dopasować do formuły) i operatorem **=**, a nowa kolumna pojawi się w siatce danych, jak pokazano na poniższej ilustracji.

![](media/7-2-dax-calculation-types/dax-calc-types_3.png)

Wymagane elementy kolumny obliczeniowej to:

* Nazwa nowej kolumny
* Co najmniej jedna funkcja lub wyrażenie

Jeśli odwołujesz się do tabeli lub kolumny w swojej formule kolumny obliczeniowej, nie musisz określać wiersza w tabeli — usługa Power BI obliczy kolumnę dla bieżącego wiersza dla każdego obliczenia.

## <a name="creating-calculated-measures"></a>Tworzenie miar obliczeniowych
**Miary obliczeniowe** są przydatne podczas obliczania wartości procentowych lub stosunku albo gdy potrzebujesz złożonych agregacji. Aby utworzyć miarę przy użyciu formuły języka DAX, naciśnij przycisk **Nowa miara** na karcie **Modelowanie**. W tym przypadku również najlepiej korzystać z widoku **Dane** programu Power BI Desktop, ponieważ pokazuje on **pasek formuły** i ułatwia pisanie formuły języka DAX.

![](media/7-2-dax-calculation-types/dax-calc-types_4.png)

W przypadku **miar** w okienku **Pola** zostanie wyświetlona nowa ikona miary z nazwą miary. **Pasek formuły** także zostanie wypełniony nazwą formuły języka DAX (tym razem z Twoją miarą).

![](media/7-2-dax-calculation-types/dax-calc-types_5.png)

Elementy wymagane dla miary obliczeniowej są takie same, jak dla kolumny obliczeniowej:

* Nazwa nowej miary
* Co najmniej jedna funkcja lub wyrażenie

> Zawartość wideo dzięki uprzejmości [Alberta Ferrariego, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

