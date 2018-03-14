---
title: "Samouczek: analizowanie danych sprzedaży z programu Excel i źródła danych OData w programie Power BI Desktop"
description: "Samouczek: analizowanie danych sprzedaży z programu Excel i źródła danych OData"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 4cab3ed114d03d42c6acf1bf62f70e7d920e16b2
ms.sourcegitcommit: d91b7bf18d5c504037134f375886633379f28ede
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/27/2018
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>Samouczek: analizowanie danych sprzedaży z programu Excel i źródła danych OData
Program **Power BI Desktop** pozwala nawiązywać połączenia z różnego rodzaju źródłami danych, a następnie łączyć i kształtować je w sposób zapewniający uzyskanie interesujących i atrakcyjnych analiz danych oraz wizualizacji. Z tego samouczka dowiesz się, jak łączyć dane z dwóch źródeł danych. 

Często zdarza się, że dane są rozdzielone na wiele źródeł danych, np. informacje o produktach w jednej bazie danych, a o sprzedaży w drugiej. Techniki, które omówimy w tym dokumencie, obejmują skoroszyt programu Excel oraz strumieniowe źródło danych OData, ale techniki te można zastosować także do innych źródeł danych, takich jak zapytania programu SQL Server, pliki CSV lub dowolne źródła danych w programie Power BI Desktop.

W tym samouczku zaimportujemy dane z programu Excel (zawierające informacje o produktach) i strumieniowego źródła danych OData (zawierające dane o zamówieniach). Wykonamy kroki przekształcania i agregacji, oraz połączymy dane z obu źródeł, aby utworzyć raport **Total Sales per Product and Year** (Łączna sprzedaż według produktów i roku) zawierający interaktywne wizualizacje. 

Oto jak będzie wyglądać raport końcowy:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

Do wykonania kroków opisanych w tym samouczku jest potrzebny skoroszyt z danymi produktów, który można pobrać: **[kliknij tutaj, aby pobrać plik Products.xlsx](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**

W oknie dialogowym **Zapisywanie jako** nadaj plikowi nazwę **Products.xlsx**.

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>Zadanie 1. Pobranie danych o produktach ze skoroszytu programu Excel
W ramach tego zadania zaimportujemy produkty z pliku Products.xlsx do programu Power BI Desktop.

### <a name="step-1-connect-to-an-excel-workbook"></a>Krok 1. Nawiązywanie połączenia ze skoroszytem programu Excel
1. Uruchom program Power BI Desktop.
2. Na wstążce Narzędzia główne wybierz pozycję **Pobierz dane**. Program Excel jest jednym z **najbardziej typowych** połączeń danych, można więc wybrać je bezpośrednio z menu **Pobierz dane**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. W przypadku wybrania przycisku Pobierz dane bezpośrednio można też wybrać pozycję **Plik \> Excel** i polecenie **Połącz.**
4. W oknie dialogowym **Otwieranie pliku** wybierz plik **Products.xlsx**.
5. W okienku **Nawigator** wybierz tabelę **Products** (produkty), a następnie wybierz przycisk **Edytuj**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>Krok 2. Usuwanie innych kolumn w celu wyświetlenia tylko interesujących kolumn
W tym kroku usuniemy wszystkie kolumny z wyjątkiem **ProductID**, **ProductName**, **UnitsInStock** i **QuantityPerUnit**. W programie Power BI Desktop istnieje zazwyczaj kilka sposób, aby wykonać to samo zadanie. Na przykład wiele przycisków na wstążce można również uruchomić, wywołując menu kontekstowe kolumny lub komórki.

Program Power BI Desktop posiada Edytor zapytań, gdzie można tworzyć i przekształcać połączenia danych. Edytor zapytań jest otwierany automatycznie po wybraniu polecenia **Edytuj** w okienku **Nawigator**. Edytor zapytań można również otworzyć, wybierając pozycję **Edytuj zapytania** na wstążce **Narzędzia główne** programu Power BI Desktop. Wykonaj następujące kroki w edytorze zapytań.

1. W edytorze zapytań wybierz kolumny **ProductID**, **ProductName**, **QuantityPerUnit** i **UnitsInStock** (naciśnij klawisz **Ctrl** i kliknij, aby wybrać więcej niż jedną kolumnę, lub klawisz **Shift** i kliknij, aby wybrać kolumny, które są obok siebie).
2. Wybierz pozycję **Usuń kolumny** \> **Usuń inne kolumny** na wstążce lub kliknij prawym przyciskiem myszy nagłówek kolumny i kliknij pozycję **Usuń inne kolumny**.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>Krok 3. Zmiana typu danych kolumny UnitsInStock
Nawiązując połączenie z danymi, edytor zapytań sprawdza każde pole, aby określić najlepszy typ danych. W przypadku skoroszytu programu Excel produkty w magazynie będą zawsze liczbą całkowitą, w tym kroku musisz zatem potwierdzić, że typ danych dla kolumny **UnitsInStock** to Liczba całkowita.

1. Wybierz kolumnę **UnitsInStock**.
2. Wybierz przycisk listy rozwijanej **Typ danych** na wstążce **Narzędzia główne**.
3. Jeśli typ danych jest inny niż Liczba całkowita, wybierz pozycję **Liczba całkowita** z listy rozwijanej (przycisk **Typ danych:** również zawiera typ danych dla bieżącego zaznaczenia).
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>Utworzone kroki programu Power BI Desktop
W miarę wykonywania działań dotyczących zapytania w edytorze zapytań tworzone są kroki zapytania i wyświetlane w formie listy **Zastosowane kroki** w okienku **Ustawienia zapytania**. Każdy krok zapytania ma odpowiadającą mu formułę określaną także jako język „M”. Aby uzyskać więcej informacji na temat języka „M” formuł, zobacz [Więcej informacji na temat formuł usługi Power BI](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

| Zadanie | Krok zapytania | Formuła |
| --- | --- | --- |
| Połączenie się ze skoroszytem programu Excel |Source |Source{[Name="Products"]}[Data] |
| Podniesienie poziomu pierwszego wiersza do poziomu nagłówków kolumn tabeli |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> (Products) |
| Usunięcie innych kolumn w celu wyświetlenia tylko interesujących kolumn |RemovedOtherColumns |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| Zmiana typu danych |Changed Type |Table.TransformColumnTypes(\#"Removed Other Columns",{{"UnitsInStock", Int64.Type}}) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>Zadanie 2. Importowanie danych dotyczących zamówień ze strumieniowego źródła danych OData
W ramach tego zadania dodamy dane dotyczące zamówień. Ten krok reprezentuje proces łączenia się z systemem sprzedaży. Zaimportujemy dane do programu Power BI Desktop, korzystając z przykładowych danych Northwind strumieniowego źródła OData dostępnego pod następującym adresem URL, który można skopiować i następnie wkleić w ramach kroków opisanych poniżej: <http://services.odata.org/V3/Northwind/Northwind.svc/> 

### <a name="step-1-connect-to-an-odata-feed"></a>Krok 1. Łączenie się ze strumieniowym źródłem danych OData
1. Na karcie **Narzędzia główne** wstążki w edytorze zapytań wybierz pozycję **Pobierz dane.**
2. Przejdź do źródła danych **OData Feed**.
3. W oknie dialogowym **OData Feed** wklej **adres URL** strumieniowego źródła danych Northwind OData.
4. Wybierz przycisk **OK**.
5. W okienku **Nawigator** wybierz tabelę **Orders** (zamówienia), a następnie wybierz przycisk **Edytuj**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>Możesz kliknąć nazwę tabeli bez zaznaczania pola wyboru, aby wyświetlić podgląd.

### <a name="step-2-expand-the-orderdetails-table"></a>Krok 2. Rozwijanie tabeli Order\_Details (szczegóły zamówienia)
Tabela **Orders** (Zamówienia) zawiera odwołanie do tabeli **Details** (Szczegóły), która zawiera poszczególne produkty w ramach każdego zamówienia. Łącząc się ze źródłami danych zawierającymi wiele tabel (na przykład z relacyjną bazą danych), można użyć tych odwołań do utworzenia zapytania. 

W tym kroku rozwiniemy tabelę **Order\_Details** powiązaną z tabelą **Orders**, aby połączyć kolumny **ProductID**, **UnitPrice** i **Quantity** tabeli **Order\_Details** z tabelą **Orders**. To jest reprezentacja danych w tych tabelach:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

Operacja **Rozwiń** łączy kolumny z tabeli powiązanej z przedmiotową tabelą. Po uruchomieniu zapytania wiersze z tabeli powiązanej (**Order\_Details**) są łączone z wierszami z tabeli przedmiotowej (**Orders**).

Po rozwinięciu tabeli **Order\_Details** trzy nowe kolumny i dodatkowe wiersze są dodawane do tabeli **Orders**, po jednym dla każdego wiersza w tabeli zagnieżdżonej lub powiązanej.

1. W **widoku zapytania** przewiń do kolumny **Order\_Details**.
2. W kolumnie **Order\_Details** wybierz ikonę rozwijania (![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)).
3. Na liście rozwijanej **Rozwiń**:
   1. Wybierz pozycję **(Zaznacz wszystkie kolumny)**, aby wyczyścić wszystkie kolumny.
   2. Zaznacz pozycje **ProductID** (Identyfikator produktu), **UnitPrice** (Cena jednostkowa) i **Quantity** (Ilość).
   3. Kliknij przycisk **OK**.
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>Krok 3. Usuwanie innych kolumn w celu wyświetlenia tylko interesujących kolumn
W tym kroku usuniemy wszystkie kolumny z wyjątkiem kolumn **OrderDate, ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** oraz **Order\_Details.Quantity**. W poprzednim zadaniu użyliśmy pozycji **Usuń inne kolumny**. W ramach tego zadania usuniemy zaznaczone kolumny.

1. W **widoku zapytania** zaznacz wszystkie kolumny, postępując zgodnie z punktami a. oraz b.:
   1. Kliknij pierwszą kolumnę (**OrderID**).
   2. Naciśnij klawisz Shift i kliknij ostatnią kolumnę (**Shipper**).
   3. Gdy wszystkie kolumny są już zaznaczone, kliknij następujące kolumny z wciśniętym klawiszem Ctrl, aby usunąć ich zaznaczenie: **OrderDate**, **ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** oraz **Order\_Details.Quantity**.
2. Teraz, gdy zaznaczone są tylko te kolumny, które chcemy usunąć, kliknij prawym przyciskiem myszy nagłówek dowolnej zaznaczonej kolumny i kliknij polecenie **Usuń kolumny**.

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>Krok 4. Obliczanie sumy wiersza dla każdego wiersza tabeli Order\_Details
Program Power BI Desktop umożliwia tworzenie obliczeń w oparciu o importowane kolumny, co pozwala wzbogacić dane, z którymi się łączysz. W tym kroku utworzymy **kolumnę niestandardową**, aby obliczyć sumę wiersza dla każdego wiersza tabeli **Order\_Details**.

Oblicz sumę wiersza dla każdego wiersza tabeli **Order\_Details**:

1. Na karcie **Dodawanie kolumny** wstążki kliknij pozycję **Dodaj** **Kolumna niestandardowa**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. W oknie dialogowym **Dodawanie kolumny niestandardowej** w polu tekstowym **Formuła kolumny niestandardowej** wprowadź formułę **[Order\_Details.UnitPrice] \* [Order\_Details.Quantity]**.
3. W polu tekstowym **Nazwa nowej kolumny** wprowadź nazwę **LineTotal**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. Kliknij przycisk **OK**.

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>Krok 5. Ustawianie typu danych pola LineTotal
1. Kliknij prawym przyciskiem myszy kolumnę **LineTotal**.
2. Wybierz pozycję **Zmień typ** i wybierz opcję **Liczba dziesiętna**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>Krok 6. Zmienianie nazw i kolejności kolumn w zapytaniu
W tym kroku dokończymy upraszczanie pracy z modelem podczas tworzenia raportów, zmieniając ostateczne nazwy kolumn oraz ich kolejność.

1. W **edytorze zapytań** przeciągnij kolumnę **LineTotal** w lewo, ustawiając ją za kolumną **ShipCountry**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. Usuń prefiks *Order\_Details.* z nazw kolumn **Order\_Details.ProductID**, **Order\_Details.UnitPrice** i **Order\_Details.Quantity**, klikając dwukrotnie nagłówek każdej kolumny, a następnie usuwając ten tekst z nazwy kolumny.

### <a name="power-bi-desktop-steps-created"></a>Utworzone kroki programu Power BI Desktop
W miarę wykonywania działań dotyczących zapytania w edytorze zapytań tworzone są kroki zapytania i wyświetlane w formie listy **Zastosowane kroki** w okienku **Ustawienia zapytania**. Każdy krok zapytania ma odpowiadającą mu formułę Power Query określaną także jako formuła języka „M”. Aby uzyskać więcej informacji na temat tego języka formuł, zobacz [Więcej informacji na temat formuł usługi Power BI](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "Więcej informacji na temat formuł Power Query").

| Zadanie | Krok zapytania | Formuła |
| --- | --- | --- |
| Połączenie się ze strumieniowym źródłem danych OData |Source |Source{[Name="Orders"]}[Data] |
| Rozwinięcie tabeli Order\_Details |Expand Order\_Details |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| Usunięcie innych kolumn w celu wyświetlenia tylko interesujących kolumn |RemovedColumns |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Expand Order\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| Obliczenie sumy wiersza dla każdego wiersza tabeli Order\_Details |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>Zadanie 3. Łączenie zapytań Products (Produkty) i Total Sales (Łączna sprzedaż)
Program Power BI Desktop nie wymaga łączenia zapytań w celu tworzenia raportów obejmujących te zapytania. Zamiast tego można utworzyć **relacje** między zestawami danych. Te relacje można utworzyć dla dowolnej kolumny, która jest wspólna dla zestawów danych. Aby uzyskać więcej informacji, zobacz [Tworzenie relacji i zarządzanie nimi](desktop-create-and-manage-relationships.md).

W tym samouczku mamy dane dotyczące zamówień i produktów, które mają wspólne pole „ProductID”, dlatego musimy upewnić się, że w modelu, którego używamy w programie Power BI Desktop, istnieje relacja między nimi. W tym celu wystarczy po prostu określić w programie Power BI Desktop, że te kolumny w tabelach są powiązane (tzn. te kolumny posiadają takie same wartości). Program Power BI Desktop ustali kierunek i liczebność relacji. W niektórych przypadkach wykryje nawet relacje automatycznie.

W tym zadaniu potwierdzimy fakt istnienia relacji w programie Power BI Desktop między zapytaniami **Products** (Produkty) i **Total Sales** (Łączna sprzedaż).

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>Krok 1. Potwierdzenie relacji między zapytaniami Products i Total Sales
1. Najpierw musimy załadować model utworzony w edytorze zapytań do programu Power BI Desktop. Na karcie **Narzędzia główne** wstążki edytora zapytań wybierz pozycję **Zamknij i załaduj**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Program Power BI Desktop załaduje dane z obu zapytań.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. Po załadowaniu danych wybierz przycisk **Zarządzaj relacjami** na karcie **Narzędzia główne** wstążki.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. Wybierz przycisk **Nowa...** button
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. Podczas próby utworzenia relacji zostanie wyświetlona informacja, że relacja ta już istnieje! Jak widać w oknie dialogowym **Tworzenie relacji** (po zacieniowaniu kolumn), pola **ProductsID** obu zapytań mają już ustaloną relację.
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. Naciśnij przycisk **Anuluj**, a następnie wybierz widok **relacji** w programie Power BI Desktop.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. Zostanie wyświetlona następująca wizualizacja relacji między zapytaniami.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. Po dwukrotnym kliknięciu symbolu strzałki na linii łączącej zapytania zostanie wyświetlone okno dialogowe **Edytowanie relacji**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. Nie trzeba dokonywać zmian, wybierzemy zatem przycisk **Anuluj**, aby zamknąć okno dialogowe **Edytowanie relacji**.

## <a name="task-4-build-visuals-using-your-data"></a>Zadanie 4. Tworzenie wizualizacji przy użyciu danych
Program Power BI Desktop pozwala tworzyć różne wizualizacje w celu uzyskania szczegółowych informacji na podstawie danych. Można tworzyć raporty z wieloma stronami, a każda z tych stron może zawierać wiele wizualizacji. Wizualizacje umożliwiają interakcję w celu ułatwienia analizy danych i ich zrozumienia. Aby uzyskać więcej informacji na temat edytowania raportów, zobacz [Edytowanie raportu](service-interact-with-a-report-in-editing-view.md).

W tym zadaniu utworzymy raport na podstawie wcześniej załadowanych danych. W okienku Pola można wybrać kolumny, które posłużą do utworzenia wizualizacji.

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>Krok 1. Tworzenie wykresów pokazujących liczbę jednostek w magazynie według produktu oraz łączną sprzedaż według roku
Przeciągnij pozycję **UnitsInStock** (Jednostki w magazynie) z okienka Pola (okienko Pola znajduje się z prawej strony ekranu) do pustego obszaru na kanwie. Zostanie utworzona wizualizacja tabeli. Następnie przeciągnij pole ProductName (Nazwa produktu) do pola Oś znajdującego się w dolnej części okienka wizualizacji. Korzystając z kropek w prawym górnym rogu wizualizacji, wybierz pozycję **Sortuj według \> UnitsInStock**.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

Przeciągnij pole **OrderDate** na kanwę pod pierwszym wykresem, przeciągnij pole LineTotal (ponownie z okienka Pola) na wizualizację i wybierz wykres liniowy. Zostanie utworzona następująca wizualizacja.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 Następnie przeciągnij pole **ShipCountry** do obszaru na kanwie w prawym górnym rogu. Ponieważ wybrane pole było polem geograficznym, automatycznie została utworzona mapa. Teraz przeciągnij pole **LineTotal** do pola **Values**. Rozmiar okręgów na mapie dla każdego kraju odpowiada względnie wartościom **LineTotal** zamówień wysłanych do tego kraju.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>Krok 2. Wchodzenie w interakcje z wizualizacjami raportu w celu dalszej analizy
Program Power BI Desktop umożliwia interakcję z wizualizacjami, które wzajemnie krzyżowo wyróżniają i filtrują dane, ujawniając dalsze trendy. Aby uzyskać więcej informacji, zobacz [Filtrowanie i wyróżnianie w raportach](power-bi-reports-filters-and-highlighting.md)

1. Kliknij jasnoniebieski okrąg widoczny w **Kanadzie.** Zwróć uwagę, jak inne wizualizacje są filtrowane, aby wyświetlać towar (**ShipCountry**) i całkowitą liczbę zamówień (**LineTotal**) tylko dla Kanady.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>Gotowy raport analizy sprzedaży
Po wykonaniu wszystkich kroków otrzymasz raport sprzedaży, który łączy dane z pliku Products.xlsx i strumieniowego źródła danych Northwind OData. Raport wyświetla wizualizacje, które ułatwiają analizę informacji o sprzedaży z różnych krajów. Gotowy plik programu Power BI Desktop do tego samouczka można pobrać [tutaj](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix).

## <a name="next-steps"></a>Następne kroki
* [Zapoznaj się z innymi samouczkami dotyczącymi programu Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Obejrzyj filmy wideo dotyczące programu Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Odwiedź forum usługi Power BI](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Przeczytaj blog poświęcony usłudze Power BI](http://go.microsoft.com/fwlink/?LinkID=519327)


