---
title: Korzystanie z modeli złożonych w programie Power BI Desktop
description: Tworzenie modeli danych z wieloma połączeniami danych i relacjami wiele-do-wielu w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/12/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: b7a8323557f769fa2a05d504de2540bc505e7a54
ms.sourcegitcommit: 6a6f552810a596e1000a02c8d144731ede59c0c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/14/2018
ms.locfileid: "51619706"
---
# <a name="use-composite-models-in-power-bi-desktop"></a>Korzystanie z modeli złożonych w programie Power BI Desktop

Wcześniej, jeśli w programie Power BI Desktop użyto w raporcie trybu DirectQuery, użycie w nim innych połączeń danych&mdash;typu Direct Query lub importu&mdash;było niedozwolone. Dzięki modelom złożonym to ograniczenie zostało usunięte. W raporcie można bez problemów uwzględniać połączenia danych pochodzące z więcej niż jednego połączenia danych typu DirectQuery lub importu w dowolnej kombinacji.

![Modele złożone w programie Power BI Desktop](media/desktop-composite-models/composite-models_01.png)

Funkcja Modele złożone w programie Power BI Desktop składa się z trzech powiązanych funkcji:

* **Modele złożone**: ta funkcja umożliwia użycie w raporcie wielu połączeń danych, takich jak połączenia trybu DirectQuery lub połączenia importu, w dowolnej kombinacji. W tym artykule szczegółowo opisano modele złożone.

* **Relacje wiele-do-wielu**: za pomocą *modeli złożonych* można ustanowić *relacje wiele-do-wielu* między tabelami. Takie rozwiązanie powoduje usunięcie wymagań dotyczących unikatowych wartości w tabelach. Powoduje również usunięcie poprzednich obejść, np. wprowadzania nowych tabel tylko w celu ustanowienia relacji. Aby uzyskać więcej informacji, zobacz temat [Relacje wiele-do-wielu w programie Power BI Desktop (wersja zapoznawcza)](desktop-many-to-many-relationships.md).

* **Tryb przechowywania** — teraz możesz określić, które wizualizacje wymagają zapytania do wewnętrznych źródeł danych. Wizualizacje, które nie wymagają zapytania, są importowane, nawet jeśli są oparte na trybie DirectQuery. Ta funkcja pomaga zwiększyć wydajność i zmniejszyć obciążenie zaplecza. Wcześniej nawet proste wizualizacje, takie jak fragmentatory, inicjowały zapytania wysyłane do źródeł wewnętrznych. Aby uzyskać więcej informacji, zobacz [Tryb przechowywania w programie Power BI Desktop (wersja zapoznawcza)](desktop-storage-mode.md).


## <a name="use-composite-models"></a>Używanie modeli złożonych

Za pomocą modeli złożonych można połączyć się z różnymi źródłami danych podczas używania programu Power BI Desktop lub usługi Power BI. Te połączenia danych można ustanowić na kilka sposobów:

* Importując dane do usługi Power BI, co jest najczęściej używanym sposobem pobierania danych.
* Bezpośrednio łącząc się z danymi w ich oryginalnym repozytorium źródłowym przy użyciu trybu DirectQuery. Aby dowiedzieć się więcej na temat trybu DirectQuery, zobacz [Używanie trybu DirectQuery w usłudze Power BI](desktop-directquery-about.md).

W przypadku korzystania z trybu DirectQuery *modele złożone* pozwalają na utworzenie modelu usługi Power BI (takiego jak pojedynczy plik *PBIX* programu Power BI Desktop), który wykonuje jedną lub obydwie z następujące czynności:

* łączy dane z jednego lub kilku źródeł trybu DirectQuery
* łączy dane ze źródeł trybu DirectQuery i dane importu.

Za pomocą modeli złożonych można na przykład utworzyć model, który łączy następujące typy danych:

* Dane sprzedaży z magazynu danych przedsiębiorstwa.
* Dane sprzedaży docelowej z bazy danych programu SQL Server działu.
* Dane zaimportowane z arkusza kalkulacyjnego. 

Model, który łączy dane z więcej niż jednego źródła DirectQuery lub łączy dane DirectQuery i dane importu, jest nazywany *modelem złożonym*.

> [!NOTE]
> Od wydania programu Power BI Desktop w październiku 2018 r. *można* publikować modele złożone w usłudze Power BI. W przypadku odświeżania zaplanowanego oraz odświeżania kafelka pulpitu nawigacyjnego modele złożone w usłudze Power BI zachowują się w taki sam sposób jak modele importu. 

Relacje między tabelami można tworzyć w zwykły sposób, nawet gdy pochodzą z różnych źródeł, z następującym ograniczeniem: wszystkie relacje obejmujące wiele źródeł należy definiować jako relacje z kardynalnością *wiele-do-wielu*, niezależnie od ich rzeczywistej kardynalności. Te relacje zachowują się jak zwykłe relacje *wiele-do-wielu*, co opisano w artykule [Relacje wiele-do-wielu w programie Power BI Desktop (wersja zapoznawcza)](desktop-many-to-many-relationships.md). 

> [!NOTE]
> W kontekście modeli złożonych wszystkie zaimportowane tabele są faktycznie pojedynczym źródłem, niezależnie od rzeczywistego bazowego źródła danych, z poziomu którego będą importowane.   

## <a name="example-of-a-composite-model"></a>Przykład modelu złożonego

Jako przykład *modelu złożonego* rozważymy raport, który jest połączony z korporacyjnym magazynem danych w programie SQL Server przy użyciu trybu DirectQuery. W tym przypadku magazyn danych zawiera dane *Sales by Country* (Sprzedaż wg. kraju), *Quarter* (Kwartał) i *Bike (Product)* (Rower), jak pokazano na poniższej ilustracji:

![Widok relacji w przypadku modeli złożonych](media/desktop-composite-models/composite-models_04.png)

W tym momencie można tworzyć proste wizualizacje przy użyciu pól z tego źródła. Na przykład poniższy obraz przedstawia sprzedaż całkowitą według pozycji *ProductName* (Nazwa_produktu) dla wybranego kwartału. 

![Wizualizacja oparta na danych](media/desktop-composite-models/composite-models_05.png)

Jednak co zrobić w sytuacji, gdy w arkuszu kalkulacyjnym programu Office Excel znajdują się dane na temat menedżera produktu, który jest przypisany do każdego produktu, wraz z priorytetem marketingowym? Jeśli chcesz wyświetlić pozycję *Sales Amount* (Kwota sprzedaży) według pozycji *Product Manager* (Menedżer produktu), dodanie tych danych lokalnych do korporacyjnego magazynu danych może być niemożliwe. W najlepszym przypadku może to potrwać kilka miesięcy. 

Można by zaimportować te dane sprzedażowe z magazynu danych, zamiast używać trybu DirectQuery. A następnie te dane sprzedażowe można by było połączyć z danymi zaimportowanymi z arkusza kalkulacyjnego. Takie podejście jest jednak nierozsądne z przyczyn, które doprowadziły do używania trybu DirectQuery. Przyczyny te mogą być następujące:

* Pewne kombinacje reguł zabezpieczeń wymuszanych w źródle bazowym.
* Wymaganie możliwości wyświetlenia najnowszych danych.
* Ogromna skala danych. 

W takiej sytuacji warto skorzystać z modeli złożonych. Modele złożone pozwalają na łączenie się z magazynem danych przy użyciu trybu DirectQuery, a następnie użycie metody GetData w przypadku dodatkowych źródeł. W tym przykładzie najpierw należy ustanowić połączenie w trybie DirectQuery z korporacyjnym magazynem danych. Użyj metody GetData, wybierz program Excel, a następnie przejdź do arkusza kalkulacyjnego, który zawiera nasze dane lokalne. Na koniec zaimportuj arkusz kalkulacyjny, który zawiera *nazwy produktów*, przypisanych *menedżerów sprzedaży* oraz *priorytet*.  

![Okno Nawigator](media/desktop-composite-models/composite-models_06.png)

Na liście **Pola** zobaczysz dwie tabele: oryginalną tabelę *Bike* (Rower) z programu SQL Server i nową tabelę **ProductManagers** (Menedżerowie produktów). Nowa tabela zawiera dane zaimportowane z programu Excel. 

![widok Pola tabel](media/desktop-composite-models/composite-models_07.png)

Podobnie w widoku **Relacja** w programie Power BI Desktop zobaczymy teraz dodatkową tabelę o nazwie **ProductManagers** (Menedżerowie produktów). 

![Widok relacji tabel](media/desktop-composite-models/composite-models_08.png)

Teraz musimy powiązać te tabele z pozostałymi tabelami w modelu. Jak zawsze tworzymy relację między tabelą **Bike** (Rower) z programu SQL Server i zaimportowaną tabelą **ProductManagers** (Menedżerowie produktów). Oznacza to, że relacja jest między danymi *Bike[ProductName]* (Rower[Nazwa_produktu]) i *ProductManagers[ProductName]* (Menedżerowie produktów[Nazwa_produktu]). Jak wspomnieliśmy wcześniej, wszystkie relacje, które przechodzą przez źródło, muszą mieć kardynalność domyślną *wiele do wielu*. 

![Okno „Tworzenie relacji”](media/desktop-composite-models/composite-models_09.png)

Teraz, gdy ustanowiliśmy już tę relację, będzie ona wyświetlana w widoku **Relacja** w programie Power BI Desktop, czego można się było spodziewać.

![Nowy widok relacji](media/desktop-composite-models/composite-models_10.png)

Teraz można tworzyć wizualizacje, korzystając z dowolnych pól na liście **Pola**. To podejście bezproblemowo łączy dane z wielu źródeł. Na przykład całkowita suma sprzedaży *SalesAmount* dla każdego menedżera produktu *Product Manager* jest wyświetlana na poniższej ilustracji: 

![Okienko Pola](media/desktop-composite-models/composite-models_11.png)

Poniższy przykład przedstawia typowy przypadek tabeli *wymiarów*&mdash;takiej jak *Product* (Produkt) lub *Customer* (Klient)&mdash;która jest rozszerzona o pewne dodatkowe dane zaimportowane z innego miejsca. Trybu DirectQuery mogą także używać tabele w celu łączenia się z różnymi źródłami. Aby kontynuować nasz przykład, załóżmy, że wartości *SalesTargets* (Cele sprzedaży) dla poszczególnych elementów *Country* (Kraj) i *Period* (Okres) są przechowywane w oddzielnej bazie danych działu. Jak zwykle możesz użyć metody *GetData*, aby połączyć się z tymi danymi, jak pokazano na poniższej ilustracji: 

![Okno Nawigatora](media/desktop-composite-models/composite-models_12.png)

Podobnie jak zrobiliśmy to wcześniej, możemy utworzyć relacje między nową tabelą i innymi tabelami w modelu, a następnie utworzyć wizualizacje łączące odpowiednie dane tabeli. Przyjrzyjmy się ponownie widokowi **Relacje**, w którym ustanowiliśmy nowe relacje:

![Widok relacji zawierający wiele tabel](media/desktop-composite-models/composite-models_13.png)

Następny obraz został utworzony na podstawie nowych danych i utworzonej przez nas relacji. Wizualizacja na dole po lewej stronie pokazuje całkowitą kwotę sprzedaży *Sales Amount* w porównaniu z docelową wartością *Target*, a obliczenie odchylenia pokazuje różnicę. Dane *Sales Amount* (Kwota sprzedaży) i *Target* (Wartość docelowa) pochodzą z dwóch różnych baz danych programu SQL Server. 

![Obraz przedstawiający większą ilość danych](media/desktop-composite-models/composite-models_14.png)

## <a name="set-the-storage-mode"></a>Ustawianie trybu przechowywania

Każda tabela w modelu złożonym ma tryb przechowywania wskazujący, czy tabela jest oparta na trybie DirectQuery, czy na trybie importu. Tryb przechowywania można wyświetlać i modyfikować w okienku **Właściwości**. Aby wyświetlić tryb przechowywania, kliknij prawym przyciskiem myszy tabelę na liście **Pola**, a następnie wybierz pozycję **Właściwości**. Poniższa ilustracja przedstawia tryb przechowywania dla tabeli **SalesTargets** (Cele sprzedaży).

![Ustawienie Tryb przechowywania](media/desktop-composite-models/composite-models_15.png)

Tryb przechowywania można również wyświetlać na etykietce narzędzia dla każdej tabeli.

![Etykietka narzędzia z wyświetlonym trybem przechowywania](media/desktop-composite-models/composite-models_16.png)

Dla każdego pliku programu Power BI Desktop (pliku *pbix*), zawierającego kilka tabel DirectQuery i kilka tabel importu, na pasku stanu jest wyświetlany tryb przechowywania o nazwie **Mieszany**. Można kliknąć ten termin na pasku stanu i łatwo przełączyć wszystkie tabele w tryb importu.

Aby uzyskać więcej informacji o trybie przechowywania, zobacz [Tryb przechowywania w programie Power BI Desktop (wersja zapoznawcza)](desktop-storage-mode.md).  

## <a name="calculated-tables"></a>Tabele obliczeniowe

Tabele obliczeniowe można dodać do modelu, który używa trybu DirectQuery. Język DAX (Data Analysis Expressions), który definiuje tabelę obliczeniową, może odwoływać się do tabel DirectQuery lub do tabel importu, albo do kombinacji tych dwóch typów tabel. 

Tabele obliczeniowe są zawsze importowane, a ich dane są odświeżane podczas odświeżania tabel. Jeśli tabela obliczeniowa odwołuje się do tabeli DirectQuery, to wizualizacje odwołujące się do tej tabeli DirectQuery zawsze pokazują najnowsze wartości w źródle bazowym. Alternatywnie, wizualizacje, które odwołują się do tabeli obliczeniowej, pokazują wartości dla czasu ostatniego odświeżenia tabeli obliczeniowej.

## <a name="security-implications"></a>Implikacje dotyczące bezpieczeństwa 

Modele złożone powodują pewne implikacje dotyczące bezpieczeństwa. Zapytanie wysłane do jednego źródła danych może uwzględniać wartości danych, które zostały pobrane z innego źródła. We wcześniejszym przykładzie wizualizacja, która pokazuje sprzedaż *Sales Amount* według menedżera *Product Manager* wysyła zapytanie SQL do relacyjnej bazy danych sprzedażowych **Sales**. To zapytanie SQL może zawierać imiona i nazwiska *menedżerów produktów* i ich skojarzonych *produktów*. 

![Skrypt przedstawiający implikacje dotyczące bezpieczeństwa](media/desktop-composite-models/composite-models_17.png)

Z tego względu informacje przechowywane w arkuszu kalkulacyjnym są teraz uwzględniane w zapytaniu wysłanym do relacyjnej bazy danych. Jeśli te informacje są poufne, należy rozważyć implikacje dotyczące bezpieczeństwa. W szczególności należy wziąć pod uwagę następujące kwestie:

* Każdy administrator bazy danych, który może wyświetlać ślady lub dzienniki inspekcji, może wyświetlać te informacje, nawet bez uprawnień do danych w jej oryginalnym źródle. W tym przykładzie administrator potrzebowałby uprawnień do pliku programu Excel.

* Należy rozważyć ustawienia szyfrowania dla każdego źródła. Należy unikać pobierania informacji z jednego źródła za pośrednictwem połączenia szyfrowanego, a następnie nieumyślnego umieszczania ich w zapytaniu, które jest wysyłane do innego źródła za pośrednictwem połączenia nieszyfrowanego. 

Aby zezwolić na potwierdzenie, że wszelkie implikacje dotyczące bezpieczeństwa zostały wzięte pod uwagę, program Power BI Desktop wyświetla komunikat ostrzegawczy podczas tworzenia modelu złożonego.  

Z podobnych względów należy zachować ostrożność podczas otwierania pliku programu Power BI Desktop wysłanego z niezaufanego źródła. Jeśli plik zawiera modele złożone, informacje, które ktoś pobiera z jednego źródła przy użyciu poświadczeń użytkownika, który otwiera plik, byłyby wysyłane do innego źródła danych jako część zapytania. Informacje te mogłyby być wyświetlane przez autora złośliwego pliku programu Power BI Desktop. Z tego powodu po początkowym otwarciu pliku programu Power BI Desktop, który zawiera wiele źródeł, program Power BI Desktop wyświetla ostrzeżenie. To ostrzeżenie jest podobne do ostrzeżenia wyświetlanego podczas otwierania pliku zawierającego natywne zapytania SQL.  

## <a name="performance-implications"></a>Implikacje dotyczące wydajności  

W przypadku używania trybu DirectQuery zawsze należy brać pod uwagę wydajność, głównie po to, aby zapewnić, że źródło zaplecza ma wystarczające zasoby, aby zaoferować użytkownikom dobre środowisko pracy. Dobre środowisko oznacza, że wizualizacje są odświeżania w ciągu co najwyżej pięciu sekund. Należy również stosować się do porad dotyczących wydajności z artykułu [Używanie trybu DirectQuery w usłudze Power BI](desktop-directquery-about.md). 

Używanie modeli złożonych powoduje dodanie kolejnych kwestii związanych z wydajnością. Jedna wizualizacja może powodować wysyłanie zapytań do wielu źródeł, co często przekazuje wyniki jednego zapytania do drugiego źródła. Taka sytuacja może spowodować następujące formy wykonywania:

* **Zapytanie SQL, która zawiera dużą liczbę wartości literalnych**: na przykład wizualizacja, która żąda całkowitej *kwoty sprzedaży* dla wybranych *menedżerów produktów*, musiałaby najpierw ustalić, które *produkty* były zarządzane przez tych menedżerów produktów. Ta sekwencja musi się zdarzyć, zanim wizualizacja wyśle zapytanie SQL, które zawiera wszystkie identyfikatory produktów w klauzuli *WHERE*.

* **Zapytanie SQL, które działa na niższym poziomie szczegółowości przy użyciu danych agregowanych lokalnie**: gdy liczba *produktów* spełniających kryteria filtru dla *menedżera produktu* rośnie, dołączanie wszystkich produktów do klauzuli *WHERE* może stać się niewydajne lub niewykonalne. Zamiast tego można wykonać zapytanie dotyczące źródła relacyjnego na niższym poziomie elementu *Product* (Produkt), a następnie zagregować wyniki lokalnie. Jeśli kardynalność elementów *Product* (Product) przekracza limit wynoszący 1 milion, zapytanie zakończy się niepowodzeniem.

* **Wiele zapytań SQL, jedno na grupę według wartości**: jeśli agregacja używa elementu **DistinctCount** pogrupowanego według kolumny z innego źródła, a źródło zewnętrzne nie obsługuje efektywnego przekazywania wielu wartości literałów definiujących grupowanie, konieczne jest wysłanie jednego zapytania SQL na grupę według wartości. 

   Na przykład wizualizacja żądająca liczności unikatowych wartości *CustomerAccountNumber* (numer konta klienta) (z tabeli programu SQL Server) według elementu *Product Manager* (Menedżer produktu) (zaimportowanego z arkusza kalkulacyjnego) musiałaby przekazać szczegóły z tabeli *Product Managers* (Menedżerowie produktów) w zapytaniu wysłanym do programu SQL Server. W przypadku innych źródeł (takich jak Redshift) jest to niemożliwe. W zamian byłoby wysyłane jedno zapytanie SQL na element *Sales Manager* (Menedżer sprzedaży)&mdash;do poziomu wskazanego przez praktyczny limit, po przekroczeniu którego zapytanie zakończy się niepowodzeniem. 

Każdy z tych przypadków ma własny wpływ na wydajność, a szczegóły różnią się w zależności od źródła danych. Mimo że kardynalność kolumn używanych w relacji łączącej dwa źródła pozostaje niska (kilka tysięcy), nie powinna mieć wpływu na wydajność. Wraz ze wzrostem kardynalności należy zwrócić uwagę na wpływ na wynikową wydajność. Stosuj te wskazówki jako reguły praktyczne. 

Ponadto użycie relacji *wiele do wielu* oznacza, że do bazowego źródła trzeba wysyłać oddzielne zapytania na każdym poziomie sumy lub sumy podrzędnej, zamiast agregować szczegółowe wartości lokalnie. Prosta wizualizacja tabeli zawierająca sumy wyśle dwa zapytania SQL, zamiast jednego. 

## <a name="limitations-and-considerations"></a>Ograniczenia i istotne zagadnienia

Ta wersja modeli złożonych zawiera kilka ograniczeń.

Następujących źródeł wielowymiarowych programu Live Connect nie można używać z modelami złożonymi:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Zestawy danych usługi Power BI
* Azure Analysis Services

W przypadku łączenia ze źródłami wielowymiarowymi w trybie DirectQuery nie można połączyć się z innym źródłem DirectQuery ani połączyć go z danymi importowanymi.

Istniejące ograniczenia trybu DirectQuery obowiązują także w przypadku korzystania z modeli złożonych. Wiele z tych ograniczeń dotyczy teraz poszczególnych tabel, w zależności od trybu przechowywania tabeli. Na przykład kolumna obliczeniowa w tabeli importu może odwoływać się do innych tabel, ale kolumna obliczeniowa w tabeli DirectQuery nadal może odwoływać się tylko do kolumn w tej samej tabeli. Inne ograniczenia mają zastosowanie do modelu jako całości, jeśli dowolne tabele w modelu działają w trybie DirectQuery. Na przykład funkcje QuickInsights oraz Pytania i odpowiedzi nie są dostępne w modelu, jeśli dowolne uwzględnione w nim tabele mają tryb przechowywania ustawiony na DirectQuery. 

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat modeli złożonych i trybu DirectQuery, zobacz następujące artykuły:
* [Relacje wiele-do-wielu w programie Power BI Desktop (wersja zapoznawcza)](desktop-many-to-many-relationships.md)
* [Tryb przechowywania w programie Power BI Desktop (wersja zapoznawcza)](desktop-storage-mode.md)
* [Używanie zapytania bezpośredniego w usłudze Power BI](desktop-directquery-about.md)
* [Źródła danych obsługiwane przez tryb DirectQuery w usłudze Power BI](desktop-directquery-data-sources.md)

