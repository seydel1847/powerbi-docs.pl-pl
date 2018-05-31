---
title: 'Samouczek: łączenie danych z programu Excel i źródła danych OData w programie Power BI Desktop'
description: 'Samouczek: łączenie danych z programu Excel i źródła danych OData'
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
ms.date: 05/02/2018
ms.author: v-thepet
LocalizationGroup: Learn more
ms.openlocfilehash: 00c4915df0e18504ec6f5d26540d9289c2f5ddb2
ms.sourcegitcommit: 773ba0d1cc1d1fcee8e666e1c20450f5e343c5c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2018
ms.locfileid: "33945991"
---
# <a name="tutorial-combine-sales-data-from-excel-and-an-odata-feed"></a>Samouczek: łączenie danych sprzedaży z programu Excel i źródła danych OData

Często zdarza się, że dane są rozdzielone na wiele źródeł danych, np. informacje o produktach w jednej bazie danych, a o sprzedaży w drugiej. Dzięki programowi **Power BI Desktop** można łączyć dane z różnych źródeł w celu tworzenia interesujących, atrakcyjnych analiz i wizualizacji danych. 

Z tego samouczka dowiesz się, jak połączyć dane z dwóch źródeł danych: skoroszytu programu Excel, który zawiera informacje o produktach, oraz źródła danych OData, które zawiera dane zamówień. Po zaimportowaniu poszczególnych zestawów danych i wykonaniu kroków przekształcania i agregacji użyj danych z obu źródeł, aby utworzyć raport analizy sprzedaży z wizualizacjami interaktywnymi. Te techniki można również stosować w przypadku zapytań programu SQL Server, plików CSV i innych źródeł danych w programie Power BI Desktop.

>[!NOTE]
>W programie Power BI Desktop istnieje zazwyczaj kilka sposobów wykonania zadania. Na przykład wiele opcji wstążki jest również dostępnych po kliknięciu prawym przyciskiem myszy lub kliknięciu pozycji **Więcej opcji** w menu kolumny lub komórki. W poniższych krokach opisano kilka metod alternatywnych. 

## <a name="import-the-product-data-from-excel"></a>Importowanie danych produktów z programu Excel

Najpierw zaimportuj dane produktów ze skoroszytu Products.xlsx programu Excel do programu Power BI Desktop.

1. [Pobierz skoroszyt Products.xlsx programu Excel](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx) i zapisz go jako plik **Products.xlsx**.
   
2. Wybierz strzałkę listy rozwijanej obok pozycji **Pobierz dane** na karcie **Narzędzia główne** wstążki programu Power BI Desktop, a następnie wybierz pozycję **Excel** z listy rozwijanej **Najbardziej typowe**. 
   
   ![Pobieranie danych](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
   
   >[!NOTE]
   >Można również wybrać samą pozycję **Pobierz dane** lub wybrać pozycję **Pobierz dane** w oknie dialogowym **Wprowadzenie** usługi Power BI, wybrać pozycję **Excel** lub **Plik** > **Excel** w oknie dialogowym **Pobieranie danych**, a następnie wybrać pozycję **Połącz**.
   
3. W oknie dialogowym **Otwieranie** przejdź do pliku **Products.xlsx** i wybierz go, a następnie wybierz pozycję **Otwórz**.
   
4. W okienku **Nawigator** wybierz tabelę **Products** (produkty), a następnie wybierz przycisk **Edytuj**.
   
   ![Okienko nawigatora programu Excel](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)
   
Otwiera podgląd tabeli w **Edytorze Power Query**, w którym można zastosować przekształcenia w celu wyczyszczenia danych. 
   
![Edytor Power Query](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_3.png)
   
>[!NOTE]
>**Edytor Power Query** można również otworzyć, wybierając pozycję **Edytuj zapytania** > **Edytuj zapytania** na wstążce **Narzędzia główne** programu Power BI Desktop lub klikając prawym przyciskiem myszy albo wybierając pozycję **Więcej opcji** obok dowolnego zapytania w **Widoku raportu** i wybierając pozycję **Edytuj zapytanie**.

## <a name="clean-up-the-products-columns"></a>Czyszczenie kolumn produktów

W połączonym raporcie będą używane tylko kolumny **ProductID** (Identyfikator produktu), **ProductName** (Nazwa produktu), **QuantityPerUnit** (Ilość na jednostkę) **UnitsInStock** (Jednostki w magazynie) skoroszytu programu Excel, dlatego można usunąć inne kolumny. 

1. W **Edytorze Power Query** wybierz kolumny **ProductID**, **ProductName**, **QuantityPerUnit** i **UnitsInStock** (naciśnij klawisz **Ctrl** + **kliknij**, aby wybrać więcej niż jedną kolumnę, lub klawisz**Shift** + **kliknij**, aby wybrać kolumny znajdujące się obok siebie).
   
2. Kliknij prawym przyciskiem myszy wybrane nagłówki i wybierz z listy rozwijanej pozycję **Usuń inne kolumny**, aby usunąć z tabeli wszystkie kolumny, z wyjątkiem zaznaczonych. 
   Możesz również wybrać pozycję **Usuń kolumny** > **Usuń inne kolumny** w grupie **Zarządzanie kolumnami** na karcie wstążki **Narzędzia główne**. 
   
   ![Usuwanie innych kolumn](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_removeothercolumns.png)

## <a name="import-the-order-data-from-an-odata-feed"></a>Importowanie danych dotyczących zamówień ze źródła danych OData

Następnie zaimportuj dane zamówień ze źródła danych OData przykładowego systemu sprzedaży firmy Northwind. 

1. W **Edytorze Power Query** wybierz pozycję **Nowe źródło**, a następnie wybierz pozycję **Źródło danych OData** z listy rozwijanej **Najbardziej typowe**. 
   
   ![Pobieranie danych OData](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata.png)
   
2. W oknie dialogowym **Źródło danych OData** wklej adres URL źródła danych Northwind OData, `http://services.odata.org/V3/Northwind/Northwind.svc/`, i wybierz przycisk **OK**.
   
   ![Okno dialogowe źródła danych OData](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata2.png)
   
3. W okienku **Nawigator** wybierz tabelę **Orders** (Zamówienia), a następnie wybierz przycisk **OK**, aby załadować dane do **Edytora Power Query**.
   
   ![Okienko nawigatora dla danych OData](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_odatafeed.png)
   
   >[!NOTE]
   >W okienku **nawigatora** możesz wybrać dowolną nazwę tabeli bez zaznaczania pola wyboru, aby wyświetlić podgląd.

## <a name="expand-the-order-data"></a>Rozwijanie danych zamówień

Po połączeniu ze źródłami danych obejmującymi wiele tabel, takimi jak relacyjne bazy danych lub źródło danych Northwind OData, można używać odwołań między tabelami w celu kompilowania zapytań. Tabela **Orders** (Zamówienia) zawiera odwołania do kilku powiązanych tabel. Możesz dodać kolumny **ProductID**, **UnitPrice** i **Quantity** z powiązanej tabeli **Order_Details** (Szczegóły_zamówienia) do tabeli głównej (**Orders** (Zamówienia)), używając operacji **Rozwiń**. 

1. Przewijaj tabelę **Orders** w prawo do momentu pojawienia się kolumny **Order_Details**. Pamiętaj, że zawiera ona odwołania do innej tabeli, a nie dane.
   
   ![Kolumna Order_Details](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)
   
2. Wybierz ikonę **Rozwiń** (![ikona Rozwiń](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)) w nagłówku kolumny **Order_Details**. 
   
3. Na liście rozwijanej **Rozwiń**:
   
   1. Wybierz pozycję **(Zaznacz wszystkie kolumny)**, aby wyczyścić wszystkie kolumny.
      
   2. Zaznacz pozycje **ProductID** (Identyfikator produktu), **UnitPrice** (Cena jednostkowa) i **Quantity** (Ilość), a następnie wybierz przycisk **OK**.
      
      ![Okno dialogowe rozwijania](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)

Po rozwinięciu tabeli **Order_Details** (Szczegóły zamówienia) kolumna **Order_Details** (Szczegóły zamówienia) jest zastępowana przez trzy nowe kolumny z tabeli zagnieżdżonej. Tabela będzie zawierać nowe wiersze dla danych dodanych z każdego zamówienia. 

![Rozwinięte kolumny](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

## <a name="create-a-custom-calculated-column"></a>Tworzenie niestandardowej kolumny obliczeniowej

Edytor Power Query umożliwia tworzenie obliczeń i pól niestandardowych w celu wzbogacenia danych. Utworzysz kolumnę niestandardową, w której całkowity koszt każdego elementu pozycji w zamówieniu będzie obliczany przez pomnożenie ceny jednostkowej przez liczbę sztuk danego elementu.

1. Na karcie **Dodawanie kolumny** na wstążce Edytora Power Query wybierz pozycję **Kolumna niestandardowa**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
   
2. W oknie dialogowym **Kolumna niestandardowa** wpisz ciąg **LineTotal** w polu **Nazwa nowej kolumny**.

3. W polu **Formuła kolumny niestandardowej** po znaku **=** wprowadź **[Order_Details.UnitPrice]** \* **[Order_Details.Quantity]**. (Możesz również wybrać nazwy pól przy użyciu suwaka przewijania **Dostępne kolumny** i wybrać pozycję **<< Wstaw**, zamiast wpisywać te ciągi). 
3. Wybierz przycisk **OK**.
   
   ![Okno dialogowe Kolumna niestandardowa](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)

Nowe pole **LineTotal** (Suma wiersza) zostanie wyświetlone jako ostatnia kolumna w tabeli **Orders** (Zamówienia).

## <a name="set-the-data-type-for-the-new-field"></a>Ustawianie typu danych dla nowego pola

Gdy Edytor Power Query łączy się z danymi, określa najlepszy typ danych dla każdego pola i wyświetla odpowiednie dane. Aby wyświetlić typy danych przypisane do pól, można użyć ikon w nagłówkach lub w obszarze **Typ danych** w grupie **Przekształcenie** na karcie **Narzędzia główne** na wstążce. 

Nowa kolumna **LineTotal** (Suma wiersza) zawiera dane typu **Dowolny**, ale jej wartości są przedstawiane jako waluta. Aby przypisać typ danych, kliknij prawym przyciskiem myszy nagłówek kolumny **LineTotal**, wybierz polecenie **Zmień typ danych** z listy rozwijanej, a następnie wybierz pozycję **Stałoprzecinkowa liczba dziesiętna**. 

![Zmiana typu danych](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)

>[!NOTE]
>Możesz również wybrać kolumnę **LineTotal**, a następnie wybrać strzałkę listy rozwijanej obok pola **Typ danych** w obszarze **Przekształcenie** karty **Narzędzia główne** na wstążce, a następnie wybrać pozycję **Stałoprzecinkowa liczba dziesiętna**.

## <a name="clean-up-the-orders-columns"></a>Czyszczenie kolumn zamówienia

Aby ułatwić współpracę modelu z raportami, można usuwać niektóre kolumny oraz zmieniać ich nazwy lub kolejność.

W raporcie będą używane tylko kolumny **OrderDate** (Data zamówienia), **ShipCity** (Kraj wysyłki), **ShipCountry** (Kraj wysyłki), **Order_Details.ProductID** (Szczegóły zamówienia, identyfikator produktu), **Order_Details.UnitPrice** (Szczegóły zamówienia, cena jednostkowa) i **Order_Details.Quantity** (Szczegóły zamówienia, ilość). Można wybrać te kolumny i użyć pozycji **Usuń inne kolumny**, tak jak w przypadku danych programu Excel. Można też wybrać wszystkie kolumny z wyjątkiem wymienionych, kliknąć prawym przyciskiem myszy jedną z wybranych kolumn i wybrać **Usuń kolumny**, aby usunąć wszystkie. 

Aby ułatwić identyfikowanie kolumn **Order_Details.ProductID**, **Order_Details.UnitPrice** i **Order_Details.Quantity**, można usunąć prefiksy *Order_Details.* z nazw kolumn. Aby odpowiednio zmienić nazwy kolumn na **ProductID** (Identyfikator produktu), **UnitPrice** (Cena jednostkowa) i **Quantity** (Ilość):

1. Kliknij dwukrotnie lub naciśnij i przytrzymaj każdy nagłówek kolumny albo kliknij prawym przyciskiem myszy nagłówek kolumny i wybierz polecenie **Zmień nazwę** z listy rozwijanej. 
2. Usuń prefiks *Order_Details.* z każdej nazwy, a następnie naciśnij klawisz **Enter**.

Na koniec, aby ułatwić dostęp do kolumny **LineTotal**, przeciągnij ją w lewo i upuść po prawej stronie kolumny **ShipCountry**.

![Wyczyszczona tabela](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

## <a name="review-the-query-steps"></a>Przeglądanie kroków zapytania

Ponieważ dane zostały przekształcone w Edytorze Power Query, każdy krok został zarejestrowany w obszarze **Zastosowane kroki** okienka **Ustawienia zapytania** po prawej stronie okna Edytora Power Query. Można przejrzeć wstecz Zastosowane kroki, aby zobaczyć, jakie zmiany wprowadzono, a następnie w razie potrzeby je edytować, usunąć lub zmienić (chociaż może to być ryzykowne, ponieważ zmiana wcześniejszych kroków może zaszkodzić efektom późniejszych). 

Wybierz poszczególne zapytania na liście **Zapytania** z lewej strony Edytora Power Query i przejrzyj obszar **Zastosowane kroki** w okienku **Ustawienia zapytania**. Po zastosowaniu poprzednich operacji przekształcania danych zastosowane kroki dla dwóch zapytań powinny wyglądać następująco:

![Zapytanie o produkty — zastosowane kroki](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png) &nbsp;&nbsp; ![Zapytanie o zamówienia — zastosowane kroki](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

>[!TIP]
>Zastosowane kroki są formułami zapisanymi w **języku Power Query**, znanym również jako język **M**. Aby wyświetlić i edytować formuły, wybierz opcję **Edytor zaawansowany** w grupie **Zapytanie** na karcie Narzędzia główne na wstążce. 

## <a name="import-the-transformed-queries"></a>Importowanie przekształconych zapytań

Jeśli przekształcone dane Ci odpowiadają, wybierz pozycję **Zamknij i zastosuj** > **Zamknij i zastosuj** w grupie **Zamykanie**na karcie **Narzędzia główne** na wstążce, aby zaimportować dane do widoku raportu programu Power BI Desktop. 

![Zamknij i zastosuj](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)

Po załadowaniu danych zapytania są wyświetlane na liście **Pola** w widoku raportu programu Power BI Desktop.

![Zapytania na liście Pola](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="manage-the-relationship-between-the-datasets"></a>Zarządzanie relacjami między zestawami danych

Program Power BI Desktop nie wymaga łączenia zapytań w celu tworzenia raportów obejmujących te zapytania. Można jednak używać relacji między zestawami danych opartych na ich wspólnych polach w celu rozszerzania i wzbogacania raportów. Program Power BI Desktop może automatycznie wykrywać relacje albo można je tworzyć w oknie dialogowym **Zarządzanie relacjami** programu Power BI Desktop. Aby uzyskać więcej informacji na temat relacji w programie Power BI Desktop, zobacz [Tworzenie relacji i zarządzanie nimi](desktop-create-and-manage-relationships.md).

Zestawy danych Orders (Zamówienia) i Products (Produkty) w tym samouczku korzystają ze wspólnego pola *ProductID* (Identyfikator produktu), więc istnieje między nimi relacja oparta na tej kolumnie. 

1. W widoku raportu programu Power BI Desktop wybierz pozycję **Zarządzaj relacjami** w obszarze **Relacje** na karcie wstążki **Narzędzia główne**.
   
   ![Wstążka zarządzania relacjami](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
   
2. W oknie dialogowym **Zarządzanie relacjami** zauważ, że program Power BI Desktop wykrył i wymienił już aktywną relację między tabelami Products i Orders. Aby wyświetlić relację, wybierz pozycję **Edytuj**. 
   
   ![Okno dialogowe Zarządzanie relacjami](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
   
   Zostanie otwarte okno dialogowe **Edytowanie relacji** zawierające szczegółowe informacje na temat relacji.  
   
   ![Okno dialogowe Edytowanie relacji](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
   
3. Program Power BI Desktop automatycznie wykrył relację w prawidłowy sposób, więc możesz wybrać pozycję **Anuluj**, a następnie **Zamknij**, aby zamknąć okna dialogowe relacji.

Można również wyświetlać relacje między zapytania i zarządzać nimi, wybierając widok **Relacje** po lewej stronie programu okna Power BI Desktop. Kliknij dwukrotnie strzałkę na linii łączącej dwa zapytania, aby otworzyć okno dialogowe **Edytowanie relacji** i wyświetlić lub zmienić relację. 

![Widok relacji](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)

Aby wrócić do widoku raportu z widoku relacji, wybierz ikonę **Widok raportu**. 

![Ikona widoku raportu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)

## <a name="create-visualizations-using-your-data"></a>Tworzenie wizualizacji przy użyciu danych

W widoku raportu programu Power BI Desktop można tworzyć różne wizualizacje w celu uzyskania szczegółowych informacji na podstawie danych. Można tworzyć raporty z wieloma stronami, a każda z tych stron może zawierać wiele wizualizacji. Wizualizacje umożliwiają Tobie i innym użytkownikom interakcję w celu ułatwienia analizy danych i ich zrozumienia. Aby uzyskać więcej informacji na temat wyświetlania i edytowania raportów w usłudze Power BI (Twojej witrynie), zobacz [Edytowanie raportu](service-interact-with-a-report-in-editing-view.md).

Można używać obydwu zestawów danych oraz relacji między nimi, aby ułatwić wizualizowanie i analizowanie danych sprzedaży. 

Najpierw utwórz skumulowany wykres kolumnowy używający pól z obydwu zapytań, aby pokazać zamówione ilości poszczególnych produktów. 

1. Wybierz pole **Quantity** (Ilość) w obszarze **Orders** (Zamówienia) w okienku **Pola** po prawej stronie lub przeciągnij je na puste miejsce na kanwie. Spowoduje to utworzenie skumulowanego wykresu kolumnowego przedstawiającego całkowitą ilość wszystkich produktów zamówionych. 
   
2. Wybierz kolumnę **ProductName** z obszaru **Products** w okienku **Pola** lub przeciągnij ją do wykresu, aby wyświetlić ilość każdego zamówionego produktu. 
   
3. Aby posortować produkty według zamówionej ilości od największej do najmniejszej, wybierz wielokropek **Więcej opcji** (**...**) w prawym górnym prawym rogu wizualizacji, a następnie wybierz pozycję **Sortuj według ilości**.
   
4. Użyj uchwytów w narożnikach wykresu, aby go powiększyć i wyświetlić więcej nazw produktów. 
   
   ![Wykres słupkowy Quantity by ProductName (Ilość według nazwy produktu)](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/19.png)

Następnie utwórz wykres przedstawiający zmianę wartości zamówień w dolarach (**LineTotal**) w czasie (**OrderDate**). 

1. Nie wybierając niczego na kanwie, wybierz pozycję **LineTotal** w obszarze **Orders** w okienku **Pola** lub przeciągnij ją do pustego miejsca na kanwie. Na skumulowanym wykresie kolumnowym zostanie przedstawiona łączna kwota wszystkich zamówień w dolarach. 
   
2. Po wybraniu wykresu wybierz pozycję **OrderDate** w obszarze **Orders** lub przeciągnij ją na wykresie. Wykres przedstawia teraz sumy wierszy dla każdej daty zamówienia. 
   
3. Zmień rozmiar wizualizacji, przeciągając narożniki, aby wyświetlić więcej danych. 
   
   ![Wykres liniowy LineTotals by OrderDate (Sumy wierszy według daty zamówienia)](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/20.png)
   
   >[!TIP]
   >Jeśli na wykresie widać tylko lata (tylko trzy punkty danych), kliknij strzałkę listy rozwijanej obok pozycji **OrderDate** w polu **Oś** okienka **Wizualizacje**, a następnie wybierz pozycję **OrderDate** zamiast pozycji **Hierarchia danych**. 

Na koniec utwórz wizualizację mapy przedstawiającą kwoty zamówień z poszczególnych krajów. 

1. Nie wybierając niczego na kanwie, wybierz pozycję **ShipCountry** w obszarze **Orders** w okienku **Pola** lub przeciągnij ją do pustego miejsca na kanwie. Program Power BI Desktop wykrywa, że dane to nazwy krajów, i automatycznie tworzy wizualizację mapy z punktem danych dla każdego kraju, w którym złożono zamówienia. 
   
2. Aby rozmiary punktów danych odzwierciedlały wartości kwoty zamówień dla poszczególnych krajów, przeciągnij pole **LineTotal** na mapę (lub przeciągnij je do obszaru **Przeciągnij pola danych tutaj** w obszarze **Rozmiar** w dolnej połowie okienka **Wizualizacje**). Rozmiary okręgów na mapie odzwierciedlają teraz kwoty zamówień (w dolarach) dla poszczególnych krajów. 
   
   ![Wizualizacja mapy LineTotals by ShipCountry (Sumy wierszy według kraju wysyłki)](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/21.png)

## <a name="interact-with-your-report-visuals-to-analyze-further"></a>Wchodzenie w interakcje z wizualizacjami raportu w celu dalszej analizy

Program Power BI Desktop umożliwia ujawnianie dalszych trendów, wchodząc w interakcję z wizualizacjami, które wzajemnie krzyżowo wyróżniają i filtrują dane. Aby uzyskać więcej informacji, zobacz [Filtrowanie i wyróżnianie w raportach](power-bi-reports-filters-and-highlighting.md). 

Z powodu relacji między zapytaniami interakcje z jedną wizualizacją będą wpływać na wszystkie inne wizualizacje na stronie. 

W wizualizacji mapy wybierz okręg wyśrodkowany na terenie **Kanady**. Pamiętaj, że dwie inne wizualizacje są filtrowane w celu wyróżnienia sum wierszy i ilości zamówień tylko dla Kanady.

![Odfiltrowane dane sprzedaży dla Kanady](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/22.png)

Po wybraniu jednego z produktów na wykresie **Quantity by ProductName** (Ilość według nazwy produktu) mapa i wykres dat będą filtrowane w celu odzwierciedlenia danych danego produktu, a po wybraniu jednej z dat na wykresie **LineTotal by OrderDate** (Suma wiersza według daty zamówienia) mapa i wykres produktów są filtrowane w celu przedstawienia danych dla wybranej daty. 
>[!TIP]
>Aby cofnąć wybór pozycji, wybierz pozycję ponownie lub wybierz jedną z innych wizualizacji. 

## <a name="complete-the-sales-analysis-report"></a>Kończenie raportu analizy sprzedaży

Ukończony raport łączy dane z pliku Products.xlsx programu Excel i źródła danych Northwind OData w wizualizacjach, które ułatwiają analizowanie informacji o zamówieniach dla różnych krajów, przedziałów czasowych i produktów. Gdy raport jest gotowy, można [przekazać go do usługi Power BI](desktop-upload-desktop-files.md), aby udostępniać go innym użytkownikom usługi Power BI.

## <a name="next-steps"></a>Następne kroki
* [Zapoznaj się z innymi samouczkami dotyczącymi programu Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Obejrzyj filmy wideo dotyczące programu Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Odwiedź forum usługi Power BI](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Przeczytaj blog poświęcony usłudze Power BI](http://go.microsoft.com/fwlink/?LinkID=519327)