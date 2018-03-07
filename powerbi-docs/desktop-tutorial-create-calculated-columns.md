---
title: 'Samouczek: tworzenie kolumn obliczeniowych w programie Power BI Desktop'
description: 'Samouczek: tworzenie kolumn obliczeniowych w programie Power BI Desktop'
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: acdaa95908cd03006170eb06ddfc780c836c64ac
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="tutorial-create-calculated-columns-in-power-bi-desktop"></a>Samouczek: tworzenie kolumn obliczeniowych w programie Power BI Desktop
Czasami analizowane dane nie zawierają określonego pola, które jest potrzebne do uzyskania szukanych wyników. W tym momencie wkraczają kolumny obliczeniowe. W kolumnach obliczeniowych do definiowania wartości w kolumnie służą formuły języka DAX (Data Analysis Expressions). Te wartości mogą być praktycznie wszystkim — zestawieniem wartości tekstowych z kilku różnych kolumn w modelu lub wynikiem obliczenia wartości liczbowej na podstawie innych wartości. Załóżmy, że w Twoich danych znajdują się kolumny Miasto i Województwo (jako pola na liście Pola), ale chcesz uzyskać jedno pole Lokalizacja zawierające obie te wartości razem, np. Warszawa, Mazowieckie. Dokładnie do tego służą kolumny obliczeniowe.

Kolumny obliczeniowe przypominają miary, ponieważ także są oparte formule języka DAX, ale różnią się sposobem użycia. Miary najczęściej są używane w obszarze Wartości w wizualizacji do obliczania wyników na podstawie innych pól w wierszu tabeli albo w obszarze Oś, Legenda lub Grupa w wizualizacji. Z drugiej strony kolumny obliczeniowe są używane, gdy potrzebujesz wyników z kolumny w tym wierszu tabeli lub w obszarze Oś, Legenda lub Grupa.

Ten samouczek przeprowadzi Cię przez informacje umożliwiające zrozumienie i utworzenie własnych kolumn obliczeniowych w programie Power BI Desktop. Jest on przeznaczony dla użytkowników usługi Power BI, którzy są już zaznajomieni z używaniem programu Power BI Desktop na potrzeby tworzenia bardziej zaawansowanych modeli. Należy zapoznać się z używaniem funkcji Zapytanie w celu importowania danych, pracą z wieloma powiązanymi tabelami oraz dodawaniem pól do kanwy raportów. Jeśli jesteś nowym użytkownikiem programu Power BI Desktop, zapoznaj się z tematem [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md).

Aby wykonać kroki opisane w tym samouczku, musisz pobrać plik [Contoso Sales Sample for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip). Jest to ten sam przykładowy plik, który był używany w samouczku [Tworzenie własnych miar w programie Power BI Desktop](desktop-tutorial-create-measures.md). Plik zawiera już dane dotyczące sprzedaży fikcyjnej firmy, Contoso, Inc. Ponieważ dane w pliku zostały zaimportowane z bazy danych, nie będzie można połączyć się ze źródłem danych ani wyświetlić źródła w Edytorze zapytań. Gdy pobierzesz plik na swój komputer, otwórz go w programie Power BI Desktop.

## <a name="lets-create-a-calculated-column"></a>Utwórzmy kolumnę obliczeniową
Załóżmy, że chcesz wyświetlić kategorie produktów razem z podkategoriami produktów w postaci pojedynczej wartości w wierszach, np. Telefony komórkowe — Akcesoria, Telefony komórkowe — Smartfony i urządzenia PDA itd. Jeśli w widoku raportu lub widoku danych (w tym miejscu używamy widoku raportu) przyjrzymy się naszym tabelom produktów na liście Pola, zobaczymy, że nie istnieje żadne pole zawierające potrzebne nam informacje. Jednak mamy pole ProductCategory i pole ProductSubcategory w oddzielnych tabelach.

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_nonewcol.png)

Utworzymy nową kolumnę obliczeniową, aby połączyć wartości z tych dwóch kolumn w nowe wartości dla naszej nowej kolumny. Ciekawe jest to, że musimy połączyć dane z dwóch różnych tabel w jedną kolumnę. Ponieważ nową kolumnę chcemy utworzyć przy użyciu języka DAX, możemy wykorzystać wszystkie możliwości, jakie daje nam nasz model, w tym relacje między różnymi, już istniejącymi tabelami.

### <a name="to-create-a-productfullcategory-column"></a>Aby utworzyć kolumnę ProductFullCategory
1.  Kliknij prawym przyciskiem myszy lub kliknij strzałkę w dół obok tabeli **ProductSubcategory** na liście Pola, a następnie kliknij pozycję **Nowa kolumna**. Dzięki temu nasza nowa kolumna zostanie dodana do tabeli ProductSubcategory.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumn.png)
    
    Wzdłuż górnej krawędzi kanwy raportu lub siatki danych zostanie wyświetlony pasek formuły. W tym miejscu możesz zmienić nazwę kolumny i wprowadzić formułę w języku DAX.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumnformula.png)
    
    Domyślnie nowa kolumna obliczeniowa nosi po prostu nazwę Kolumna. Jeśli nie zmienisz jej nazwy, podczas tworzenia kolejnych kolumn otrzymają one kolejno nazwy Kolumna 2, Kolumna 3 itd. Chcemy, aby nasze kolumny było łatwiej zidentyfikować, dlatego nadamy naszej nowej kolumnie nową nazwę.
    
2.  Ponieważ nazwa **Kolumna** jest już wyróżniona na pasku formuły, wystarczy wpisać **ProductFullCategory**.
    
    Teraz możemy rozpocząć wprowadzanie formuły. Chcemy, aby wartości w naszej nowej kolumnie zaczynały się od nazwy ProductCategory z tabeli ProductCategory. Ponieważ ta kolumna znajduje się w innej, ale powiązanej tabeli, użyjemy funkcji [RELATED](https://msdn.microsoft.com/library/ee634202.aspx), która pomoże nam uzyskać zamierzony efekt.
    
3.  Po znaku równości wpisz **R**. Zobaczysz listę rozwijaną z sugestiami zawierającą wszystkie funkcje DAX zaczynające się od litery R. Im więcej liter wpiszesz, tym dokładniej lista sugestii będzie filtrowana pod kątem funkcji, której potrzebujesz. Obok funkcji będzie wyświetlany opis funkcji. Wybierz funkcję **RELATED**, przewijając w dół, a następnie naciskając klawisz Enter.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_1.png)
    
    Zostanie wyświetlony nawias otwierający z kolejną listą sugestii zawierającą wszystkie dostępne kolumny, które możemy przekazać do funkcji RELATED. Będzie widoczny także opis oraz szczegółowe informacje na temat oczekiwanych parametrów.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_2.png)
    
    Wyrażenie zawsze pojawia się między nawiasem otwierającym i zamykającym. W tym przypadku nasze wyrażenie będzie zawierać pojedynczy argument przekazany do funkcji RELATED: powiązaną kolumnę, z której będą zwracane wartości. Lista wyświetlanych kolumn zostanie automatycznie zawężona tylko do powiązanych kolumn. W tym przypadku potrzebujemy kolumny ProductCategory z tabeli ProductCategory.
    
    Wybierz pozycję **ProductCategory[ProductCategory]**, a następnie wpisz nawias zamykający.
    
    > [!TIP]
    > Błędy składniowe są najczęściej powodowane przez brakujące lub błędnie umieszczone nawiasy zamykające. Jednak często program Power BI Desktop dodaje nawiasy, gdy o nich zapomnisz.
    > 
    > 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_3.png)
    
4. Chcemy dodać symbol łącznika, aby oddzielić poszczególne wartości, dlatego po nawiasie zamykającym pierwsze wyrażenie wpisujemy spację, ampersand (&), cudzysłów, spację, myślnik (-), kolejną spację, cudzysłów zamykający, a następnie kolejny ampersand. Twoja formuła powinna teraz wyglądać następująco:
    
    **ProductFullCategory = RELATED(ProductCategory[ProductCategory]) & " - " &**
    
    > [!TIP]
    > Kliknij strzałkę w dół po prawej stronie paska formuły, aby rozwinąć edytor formuł. Naciśnij klawisze Alt & Enter, aby przejść do kolejnego wiersza, i klawisz Tab, aby przesunąć wpisany tekst.
    > 
    > 
    
5.  Na koniec wprowadź kolejny nawias otwierający, a następnie wybierz kolumnę **[ProductSubcategory]**, aby zakończyć formułę. Twoja formuła powinna wyglądać następująco:
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_5.png)
    
    Zwróć uwagę, że w drugim wyrażeniu wywołującym kolumnę ProductSubcategory nie użyliśmy kolejnej funkcji RELATED. Stało się tak dlatego, że ta kolumna znajduje się już w tabeli, w której tworzymy naszą nową kolumnę. Kolumnę [ProductCategory] możemy wprowadzić z nazwą tabeli (w pełni kwalifikowana) lub bez nazwy (niekwalifikowana).
    
6.  Zakończ formułę, naciskając klawisz Enter lub klikając znacznik wyboru na pasku formuły. Formuła zostanie zatwierdzona i dodana do listy pól w tabeli **ProductSubcategory**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_6.png)
    
    Zauważ, że kolumny obliczeniowe otrzymują specjalną ikonę na liście pól. Oznacza to, że zawierają one formuły. W ten sposób są one wyświetlane tylko w programie Power BI Desktop. W usłudze Power BI (witrynie usługi Power BI) nie ma możliwości zmiany formuły, dlatego pole kolumny obliczeniowej nie zawiera ikony.
    
## <a name="lets-add-our-new-column-to-a-report"></a>Dodajmy nową kolumnę do raportu
Teraz możemy dodać naszą nową kolumnę ProductFullCategory do kanwy raportów. Spójrzmy na wartości SalesAmount według kolumny ProductFullCategory.

Przeciągnij kolumnę **ProductFullCategory** z tabeli **ProductSubcategory** na kanwę raportów, a następnie przeciągnij pole **SalesAmount** z tabeli **Sales** na wykres.

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_report_1.png)

## <a name="lets-create-another"></a>Utwórzmy kolejną
Teraz już wiesz, jak utworzyć kolumnę obliczeniową. Utwórz kolejną.

Model Contoso Sales Sample for Power BI Desktop zawiera dane sprzedaży zarówno dla sklepów aktywnych, jak i nieaktywnych. Chcemy wyraźnie podkreślić, że dane wyświetlane dla sklepów nieaktywnych są określone jako takie. W efekcie potrzebujemy pola o nazwie Active StoreName. W tym celu utworzymy kolejną kolumnę. W tym przypadku, gdy sklep jest nieaktywny, chcemy, aby nazwa sklepu w naszej nowej kolumnie Active StoreName (jako pole) była wyświetlana jako „Nieaktywny”. Natomiast gdy sklep jest aktywny, powinna być wyświetlana jego prawdziwa nazwa.

Na szczęście w naszej tabeli Stores znajduje się kolumna o nazwie Status zawierająca wartość On w przypadku sklepów aktywnych i Off w przypadku nieaktywnych. Możemy sprawdzić wartości dla każdego wiersza w kolumnie Status, aby utworzyć nowe wartości w naszej nowej kolumnie.

### <a name="to-create-an-active-storename-column"></a>Aby utworzyć kolumnę Active StoreName
1.  Utwórz nową kolumnę obliczeniową o nazwie **Active StoreName** w tabeli **Stores**.
    
    W tej kolumnie nasza formuła języka DAX sprawdzi stan każdego sklepu. Jeśli stan sklepu ma wartość On, nasza formuła zwróci nazwę sklepu. W przypadku wartości Off sklep będzie miał nazwę „Nieaktywny”. W tym celu użyjemy funkcji logicznej [IF](https://msdn.microsoft.com/library/ee634824.aspx), aby sprawdzić stan sklepów i zwrócić określoną wartość, gdy wynikiem jest „prawda” lub „fałsz”.
    
2.  Rozpocznij wpisywanie **IF**. Lista sugestii będzie wyświetlać elementy, które możemy dodać. Wybierz pozycję **IF**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_1.png)
    
    Pierwszym argumentem funkcji IF jest test logiczny. Chcemy sprawdzić, czy sklep ma stan „On”.
    
3.  Wpisz otwierający nawias kwadratowy **[**, co pozwoli nam wybrać kolumny z tabeli Stores. Wybierz pozycję **[Status]**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_2.png)
    
4.  Tuż za argumentem **[Status]** wpisz **= "On"**, a następnie wpisz przecinek (**,**), aby wprowadzić drugi argument. Etykietka narzędzia sugeruje, że musimy dodać wartość dla sytuacji, gdy wynik jest prawdą.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_3.png)
    
5.  Jeśli sklep ma stan On, chcemy wyświetlić jego nazwę. Wpisz otwierający nawias kwadratowy **[** i wybierz kolumnę **[StoreName]**, a następnie wpisz kolejny przecinek, abyśmy mogli wprowadzić nasz trzeci argument.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step5.png)
    
6.  Musimy dodać wartość dla sytuacji, gdy wynik jest fałszem. W tym przypadku chcemy uzyskać wartość **"Nieaktywny"**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step6.png)
    
7.  Zakończ formułę, naciskając klawisz Enter lub klikając znacznik wyboru na pasku formuły. Formuła zostanie zatwierdzona i dodana do listy pól w tabeli Stores.
    
    Naszej nowej kolumny Active StoreName możemy używać w wizualizacji, podobnie jak każdego innego pola. Na poniższym wykresie sklepy o stanie On są wyświetlane indywidualnie według nazwy, natomiast sklepy o stanie Off są zgrupowane razem i wyświetlane jako Nieaktywny. 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_viz.png)
    
## <a name="what-weve-learned"></a>Poznane informacje
Kolumny obliczeniowe mogą wzbogacić nasze dane, ułatwiając dostarczanie szczegółowych informacji. Nauczyliśmy się, jak tworzyć kolumny obliczeniowe przy użyciu paska formuły, jak używać listy sugestii i jak nadawać najlepsze nazwy naszym nowym kolumnom.

## <a name="next-steps"></a>Następne kroki
Jeśli chcesz poznać więcej szczegółowych informacji na temat formuł języka DAX i tworzyć kolumny obliczeniowe za pomocą bardziej zaawansowanych formuł języka DAX, zobacz [Podstawy języka DAX w programie Power BI Desktop](desktop-quickstart-learn-dax-basics.md). Ten artykuł skupia się na podstawowych pojęciach dotyczących języka DAX, np. składni, funkcjach i dokładniejszym rozumieniu kontekstu.

Pamiętaj, aby dodać [dokumentację języka Data Analysis Expressions (DAX)](https://msdn.microsoft.com/library/gg413422.aspx) do ulubionych. W tym miejscu znajdziesz szczegółowe informacje dotyczące składni, operatorów i ponad 200 funkcji języka DAX.

