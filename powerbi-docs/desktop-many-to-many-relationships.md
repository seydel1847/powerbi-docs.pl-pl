---
title: Relacje wiele-do-wielu w programie Power BI Desktop (wersja zapoznawcza)
description: Używanie relacji wiele-do-wielu w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/31/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 40799bb2716b2f6e85405e76c2a301acef3509aa
ms.sourcegitcommit: 06f59902105c93700e71e913dff8453e221e4f82
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2018
ms.locfileid: "39388760"
---
# <a name="many-to-many-relationships-in-power-bi-desktop-preview"></a>Relacje wiele-do-wielu w programie Power BI Desktop (wersja zapoznawcza)

Za pomocą funkcji **Relacje wiele-do-wielu** w programie **Power BI Desktop** można łączyć tabele, używając kardynalności **Wiele do wielu**, oraz łatwiej i bardziej intuicyjnie tworzyć modele danych zawierające wiele źródeł danych. Funkcja **relacji wiele-do-wielu** jest częścią większych możliwości **modeli złożonych** w programie **Power BI Desktop**.

![relacja wiele-do-wielu w oknie dialogowym Edytowanie relacji](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Możliwość obsługi **relacji wiele-do-wielu** w programie **Power BI Desktop** jest częścią kolekcji trzech pokrewnych funkcji:

* **Modele złożone** — ta funkcja umożliwia użycie w raporcie wielu połączeń danych, takich jak połączenia trybu DirectQuery lub importowanie, w dowolnej kombinacji.
* **Relacje wiele-do-wielu** — dzięki **modelom złożonym** można ustanawiać **relacje wiele-do-wielu** między tabelami, usuwać wymagania dotyczące unikatowe wartości w tabelach, a także usuwać wcześniejsze obejścia, takie jak wprowadzanie nowych tabel tylko w celu ustanowienia relacji. 
* **Tryb przechowywania** — można teraz określić, które wizualizacje wymagają wykonania zapytania dotyczącego źródła danych zaplecza. Wizualizacje niewymagające tej czynności są importowane, nawet jeśli są oparte na trybie DirectQuery, co zwiększa wydajność i redukuje obciążenie zaplecza. Wcześniej nawet proste wizualizacje, takie jak fragmentatory, inicjowały wysyłanie zapytań do źródeł zaplecza. 

Ta kolekcja trzech powiązanych funkcji **modeli złożonych** została opisana w osobnych artykułach:

* **Modele złożone** zostały szczegółowo opisane w artykule [Modele złożone w programie Power BI Desktop (wersja zapoznawcza)](desktop-composite-models.md).
* **Relacje wiele do wielu** zostały opisane w tym artykule.
* **Tryb przechowywania** został opisany w oddzielnym artykule: [Tryb przechowywania w programie Power BI Desktop (wersja zapoznawcza)](desktop-storage-mode.md).

## <a name="enabling-the-many-to-many-relationships-preview-feature"></a>Włączanie funkcji relacji wiele do wielu w wersji zapoznawczej

Funkcja **relacji wiele-do-wielu** jest częścią możliwości **modeli złożonych** i jest dostępna w wersji zapoznawczej. Należy ją włączyć w programie **Power BI Desktop**. Aby włączyć **modele złożone**, wybierz pozycję **Plik > Opcje i ustawienia > Opcje > Funkcje w wersji zapoznawczej**, a następnie zaznacz pole wyboru **Modele złożone**.

![włączanie funkcji w wersji zapoznawczej](media/desktop-composite-models/composite-models_02.png)

Aby funkcja została włączona, należy ponownie uruchomić program **Power BI Desktop**.

![ponowne uruchomienie wymagane do uwzględnienia zmian](media/desktop-composite-models/composite-models_03.png)


## <a name="what-many-to-many-relationships-solves"></a>Jakie problemy rozwiązuje funkcji relacji wiele do wielu

Zanim **relacje wiele do wielu** zostały udostępnione, podczas definiowania relacji między dwiema tabelami w usłudze Power BI co najmniej jedna z kolumn uwzględnionych w relacji musiała zawierać unikatowe wartości. W wielu przypadkach żadna kolumna w tabeli nie zawierała unikatowych wartości. 

Na przykład dwie tabele mogą mieć kolumnę zawierającą wartość *Country* (Kraj), ale wartości *Country* nie były unikatowe w żadnej tabeli. Aby połączyć takie tabele, trzeba było utworzyć obejście, takie jak wprowadzenie do modelu dodatkowych tabel zawierających niezbędne unikatowe wartości. Funkcja **relacji wiele-do-wielu** oferuje alternatywne podejście, pozwalając na bezpośrednie łączenie takich tabel przy użyciu relacji o kardynalności **wiele-do-wielu**.  

## <a name="using-many-to-many-relationships"></a>Używanie relacji wiele do wielu

Podczas definiowania relacji między dwoma tabelami w usłudze Power BI należy zdefiniować kardynalność relacji. Na przykład relacja między tabelami *ProductSales* (Sprzedaż produktu) i *Product* (Produkt) (przy użyciu kolumn *ProductSales[ProductCode]* i *Product[ProductCode]*) zostaną zdefiniowane jako **wiele-1**, ponieważ istnieje wiele operacji sprzedaży każdego produktu, a kolumna *Product* (Produkt) *(ProductCode)* jest unikatowa. W przypadku definiowania kardynalności relacji jako **wiele-1**, **1-wiele** lub **1-1** usługa Power BI przeprowadza walidację, aby zapewnić zgodność wybranej kardynalności z rzeczywistymi danymi.

Spójrzmy na przykład na prosty model na poniższej ilustracji.

![widok relacji](media/desktop-many-to-many-relationships/many-to-many-relationships_02.png)

Następnie wyobraźmy sobie, że tabela *Product* (Produkt) zawiera tylko dwa wiersze.

![wizualizacja tabeli](media/desktop-many-to-many-relationships/many-to-many-relationships_03.png)

Wyobraźmy sobie również, że tabela *Sales* (Sprzedaż) zawiera tylko cztery wiersze, w tym wartość *Sales* (Sprzedaż) dla produktu **C**, która nie istnieje w tabeli *Product* (z powodu błędu integralności referencyjnej).

![wizualizacja tabeli](media/desktop-many-to-many-relationships/many-to-many-relationships_04.png)

Wizualizacja, w której zostały wyświetlone elementy *ProductName* (Nazwa produktu) i *Price* (Cena) (z tabeli *Product* (Produkt)) oraz łączna ilość (*Qty*) dla każdego produktu (z tabeli *ProductSales* (Sprzedaż produktu)), będzie wyglądać jak na poniższej ilustracji: 

![wizualizacja tabeli](media/desktop-many-to-many-relationships/many-to-many-relationships_05.png)

Jak widać na poprzedniej ilustracji, w wizualizacji znajduje się wiersz z pustą wartością *ProductName* skojarzony ze sprzedażą produktu *C*. Ten pusty wiersz odpowiada:

* Dowolnemu wierszowi w tabeli *ProductSales* (Sprzedaż produktu), który nie ma odpowiadającego wiersza w tabeli *Product* (Product) — wystąpił problem z integralnością referencyjną, co widzimy w przypadku produktu *C* w tym przykładzie.

* Dowolnemu wierszowi w tabeli *ProductSales* (Sprzedaż produktu), dla którego kolumna klucza obcego ma wartość Null. 

Z tych powodów w obydwu przypadkach pusty wiersz odpowiada operacji sprzedaży, w której wartości *ProductName* (Nazwa produktu) i *Price* (Cena) są nieznane.

Czasami jednak tabele są łączone za pomocą dwóch kolumn, mimo że żadna z nich nie jest unikatowa. Na przykład rozważmy następujące dwie tabele:

* Tabela *Sales* (Sprzedaż) zawiera dane sprzedaży według wartości *State* (Stan), a każdy wiersz zawiera kwotę sprzedaży dla typu sprzedaży w danym stanie (w tym stany CA (Kalifornia), WA (Waszyngton) i TX (Teksas)) 

    ![wizualizacja tabeli](media/desktop-many-to-many-relationships/many-to-many-relationships_06.png)

* Tabela *CityData* (Dane miast) zawiera dane dotyczące miast, w tym populacji i stanu (w tym stany CA (Kalifornia), WA (Waszyngton) i Nowy Jork)

    ![wizualizacja tabeli](media/desktop-many-to-many-relationships/many-to-many-relationships_07.png)

Mimo że w obydwu tabelach istnieje kolumna *State* (Stan) i jest uzasadnione raportowanie łącznej wartości *Sales* (Sprzedaż) według *State* (Stan) wraz z całkowitą populacją poszczególnych stanów, istnieje problem: kolumna *State* (Stan) nie jest unikatowa w żadnej tabeli. 

## <a name="the-prior-workaround"></a>Wcześniejsze obejście

W wersjach programu **Power BI Desktop** poprzedzających wydanie z lipca 2018 r. nie można było utworzyć relacji między tymi tabelami. Typowym obejściem tego problemu było wykonanie następujących czynności:

* Utworzenie trzeciej tabeli zawierającej tylko unikatowe identyfikatory stanów (*State*). Mogłaby to być tabela obliczeniowa (zdefiniowana przy użyciu języka DAX) lub tabela zdefiniowana przy użyciu zapytania zdefiniowanego w **edytorze zapytań**, która mogłaby zawierać unikatowe identyfikatory z jednej z tabel lub z pełnego połączonego zestawu.

* Powiązanie dwóch oryginalnych tabel z nową tabelą za pomocą typowych relacji **wiele-1*.

Ta tabela stosowana w obejściu może być widoczna lub zostać ukryta, aby nie była wyświetlana na liście pól. W drugim przypadku relacje **wiele-1** byłyby często ustawiane z opcją filtrowania w obydwu kierunkach, tak aby można było używać pola *State* (Stan) z dowolnej tabeli, a następnie przeprowadzać propagowanie filtrowania krzyżowego w drugiej tabeli. Takie podejście do obejścia pokazano w poniższym **widoku relacji**.

![widok relacji](media/desktop-many-to-many-relationships/many-to-many-relationships_08.png)

Wizualizacja z wartością *State* (Stan) (z tabeli *CityData* (Dane miast)) wraz z łącznymi wartościami *Population* (Populacja) i *Sales* (Sprzedaż) wyglądałaby tak, jak przedstawiono poniżej.

![wizualizacja tabeli](media/desktop-many-to-many-relationships/many-to-many-relationships_09.png)

Należy pamiętać, że jeśli w tym obejściu jest używany stan z tabeli *CityData* (Dane miast), są wymieniane tylko wartości *State* (Stan) z tej tabeli (i w związku z tym stan TX jest wykluczany). Ponadto w odróżnieniu od relacji **wiele-1** wiersz sumy obejmuje wszystkie operacje typu *Sales* (Sprzedaż) (z uwzględnieniem stanu TX),ale szczegóły nie uwzględniają pustego wiersza obejmującego takie niedopasowane wiersze. Podobnie nie byłoby pustych wierszy obejmujących dowolną wartość *Sales* (Sprzedaż), dla której element *State* (Stan) miał wartość null.

Jeśli do tej wizualizacji dodano również element *City* (Miasto), a populacja danego elementu *City* jest znana, wartość *Sales* (Sprzedaż) wyświetlana dla elementu *City* będzie po prostu powtórzeniem wartości *Sales* dla odpowiedniego elementu *State* (Stan) (taka sytuacja występuje zwykle w przypadku grupowania według kolumny, której nie powiązano z miarą zagregowaną), jak pokazano na poniższej ilustracji.

![wizualizacja tabeli](media/desktop-many-to-many-relationships/many-to-many-relationships_10.png)

Jeśli nowa tabela *Sales* (Sprzedaż) została zdefiniowana jako związek między wszystkimi elementami *State* (Stan) w tym obejściu i jest widoczna na liście pól, ta sama wizualizacja przedstawiająca element *State* (w nowej tabeli) wraz z łączną wartością *Population* (Population) i całkowitą wartością *Sales* (Sprzedaż) będzie wyglądać tak, jak pokazano poniżej.

![wizualizacja tabeli](media/desktop-many-to-many-relationships/many-to-many-relationships_11.png)

W tym przypadku, jak pokazano w wizualizacji, zostałyby uwzględnione stany *TX* (z wartością *Sales* (Sprzedaż), ale nieznaną populacją) i *Nowy Jork* (ze znaną populacją, ale bez wartości *Sales* (Sprzedaż)). 

Jak widać, to obejście nie było optymalne i powodowało wiele problemów. Utworzenie **relacji wiele do wielu** umożliwiło rozwiązanie tych problemów, tak jak opisano to w poniższej sekcji.

## <a name="using-many-to-many-relationships-instead-of-the-workaround"></a>Używanie relacji wiele-do-wielu zamiast obejścia

W wersjach programu **Power BI Desktop** od lipca 2018 r. można bezpośrednio powiązać tabele opisane w poprzedniej sekcji bez konieczności stosowania takich obejść. Obecnie można ustawić kardynalność relacji na **wiele-do-wielu**, aby wskazać, że żadna tabela nie zawiera unikatowych wartości. W przypadku takich relacji można nadal kontrolować, która tabela filtruje drugą tabelę, lub stosować filtrowanie dwukierunkowe, w przypadku którego obie tabele filtrują siebie nawzajem.  

> [!NOTE]
> Możliwość tworzenia relacji **wiele-do-wielu** jest dostępna w wersji zapoznawczej. W tym okresie nie można publikować modeli przy użyciu relacji **wiele-do-wielu** do usługi Power BI. 

W programie **Power BI Desktop** kardynalność jest domyślnie ustawiana na **Wiele do wielu**, jeśli zostanie zidentyfikowana sytuacja, w której żadna z tabel nie zawiera unikatowych wartość kolumn w relacji. W takich przypadkach jest wyświetlane ostrzeżenie mające na celu potwierdzenie, że takie ustawienie relacji jest zamierzone i nie jest nieplanowanym efektem problemów z danymi. 

Na przykład podczas tworzenia relacji bezpośrednio między tabelami *CityData* (Dane miasta) i *Sales* (Sprzedaż), w której filtry powinny przepływać z tabeli *CityData* do tabeli *Sales*, jest wyświetlane okno dialogowe relacji, takie jak na poniższej ilustracji.

![Okno dialogowe Edytowanie relacji](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Wynikowy **widok relacji** zawierałby bezpośrednią relację **Wiele do wielu** między dwiema tabelami. Wygląd na liście **Pola** oraz wynikowe zachowanie podczas tworzenia wizualizacji będą takie same po zastosowaniu obejścia problemu opisanego w poprzedniej sekcji, w którym dodatkowa tabela (z różnymi wartościami *State* (Stan)) nie jest widoczna. Na przykład, tak jak w poprzedniej sekcji, opisującej obejście, wizualizacja pokazująca wartości *State* (Stan) z całkowitą populacją i sprzedażą wyglądałaby jak na poniższej ilustracji.

![wizualizacja tabeli](media/desktop-many-to-many-relationships/many-to-many-relationships_12.png)

Dlatego główna różnica między relacjami **Wiele do wielu** i bardziej typowymi relacjami **Wiele-1** byłaby następująca.

* Pokazane wartości nie uwzględniają pustego wiersza odpowiadającego dowolnym niezgodnym wierszom w drugiej tabeli ani wierszy, w których kolumna używana w relacji w drugiej tabeli ma wartość null.
* Nie można używać funkcji *RELATED()* (ponieważ więcej niż jeden wiersz może być powiązany)
* Użycie funkcji *ALL()* w tabeli nie spowoduje usunięcia filtrów stosowanych w innych tabelach powiązanych z nią za pomocą relacji **Wiele do wielu**. Na przykład miara zdefiniowana tak jak w poprzednim przykładzie nie będzie usuwać filtrów w kolumnach powiązanej tabeli *CityData* (Dane miast):

    ![przykład skryptu](media/desktop-many-to-many-relationships/many-to-many-relationships_13.png)

    W takiej sytuacji wizualizacja przedstawiająca wartości *State* (Stan), *Sales* (Sprzedaż) i *Sales Total* (Całkowita sprzedaż) byłaby następująca:

    ![wizualizacja tabeli](media/desktop-many-to-many-relationships/many-to-many-relationships_14.png)

W związku z tym należy upewnić się, że obliczenia korzystające z funkcji *ALL(\<Table>)*, takie jak *% sumy końcowej*, zwracają zamierzone wyniki. 


## <a name="limitations-and-considerations"></a>Ograniczenia i istotne zagadnienia

Istnieje kilka ograniczeń tej wersji **relacji wiele-do-wielu** i **modeli złożonych**.

Następujących źródeł wielowymiarowych nie można używać z **modelami złożonymi**:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Zestawy danych usługi Power BI

W przypadku łączenia ze źródłami wielowymiarowymi w trybie DirectQuery nie można również połączyć się z innym źródłem DirectQuery ani utworzyć kombinacji z danymi importowanymi.

Istniejące ograniczenia użycia trybu DirectQuery nadal obowiązują w przypadku korzystania z **relacji wiele do wielu**. Wiele z tych ograniczeń jest teraz określanych na tabelę, w zależności od **tryb przechowywania** tabeli. Na przykład kolumna obliczeniowa w zaimportowanej tabeli może odwoływać się do innych tabel, ale kolumna obliczeniowa w tabeli DirectQuery jest nadal ograniczona tak, aby odwoływać się tylko do kolumn w tej samej tabeli. Inne ograniczenia mają zastosowanie do modelu jako całości, jeśli dowolne tabele w modelu działają w trybie DirectQuery. Na przykład funkcje **QuickInsights** oraz **Pytania i odpowiedzi** nie są dostępne w modelu, jeśli dowolne uwzględnione w nim tabele mają **tryb przechowywania** ustawiony na DirectQuery. 

## <a name="next-steps"></a>Następne kroki

W poniższych artykułach bardziej szczegółowo opisano modele złożone oraz przedstawiono szczegóły trybu DirectQuery.

* [Modele złożone w programie Power BI Desktop (wersja zapoznawcza)](desktop-composite-models.md)
* [Tryb przechowywania w programie Power BI Desktop (wersja zapoznawcza)](desktop-storage-mode.md)

Artykuły dotyczące trybu DirectQuery:

* [Używanie trybu DirectQuery w usłudze Power BI](desktop-directquery-about.md)
* [Źródła danych obsługiwane przez tryb DirectQuery w usłudze Power BI](desktop-directquery-data-sources.md)

