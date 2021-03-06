---
title: Zapytanie bezpośrednie na platformie SAP HANA w usłudze Power BI
description: Zagadnienia dotyczące korzystania z zapytania bezpośredniego na platformie SAP HANA
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1b587edb82f60ac8a9ff22716e42bcf941e0c794
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54276542"
---
# <a name="directquery-and-sap-hana"></a>Zapytanie bezpośrednie i platforma SAP HANA
**Zapytanie bezpośrednie** umożliwia bezpośrednie połączenie się ze źródłami danych platformy **SAP HANA**. Łącząc się z platformą SAP HANA, mamy do wyboru dwie opcje:

* **Traktuj platformę SAP HANA jako źródło wielowymiarowe (ustawienie domyślne):**  W tym przypadku zachowanie będzie podobne jak wówczas, gdy usługa Power BI łączy się z innymi źródłami wielowymiarowymi, takimi jak usługi SAP Business Warehouse czy Analysis Services. W przypadku łączenia się z platformą SAP HANA przy użyciu tego ustawienia zostaje wybrany pojedynczy widok analizy lub obliczeń i wszystkie miary, hierarchie oraz atrybuty tego widoku będą dostępne na liście pól. Podczas tworzenia wizualizacji zagregowane dane będą zawsze pobierane z platformy SAP HANA. Jest to metoda zalecana i domyślna dla nowych raportów zapytania bezpośredniego tworzonych za pośrednictwem platformy SAP HANA.

* **Traktuj platformę SAP HANA jako źródło relacyjne:** w tym przypadku usługa Power BI traktuje platformę SAP HANA jako źródło relacyjne. Zapewnia to większą elastyczność, ale należy zwrócić uwagę, by miary zostały zagregowane zgodnie z oczekiwaniami. Należy również zadbać o to, by uniknąć problemów z wydajnością.

Metoda używana do połączenia zależy od globalnej opcji narzędzia, która została ustawiona przez wybranie kolejno opcji **Plik > Opcje i ustawienia**, a następnie **Opcje > Zapytanie bezpośrednie** oraz **Traktuj platformę SAP HANA jako źródło relacyjne**, zgodnie z rysunkiem poniżej. 

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01a.png)

Opcja traktowania platformy SAP HANA jako źródła relacyjnego decyduje o metodzie używanej wobec wszystkich *nowych* raportów zapytania bezpośredniego tworzonych za pośrednictwem platformy SAP HANA. Nie ma ona wpływu na istniejące połączenia platformy SAP HANA w bieżącym raporcie ani na połączenia w żadnych innych otwartych raportach. Jeśli ta opcja nie jest aktualnie zaznaczona, nowe połączenie dodane do platformy SAP HANA w oknie **Pobieranie danych** będzie traktować platformę SAP HANA jako źródło wielowymiarowe. Jednak jeśli zostanie otwarty inny raport, który również łączy się z platformą SAP HANA, będzie on nadal działać zgodnie z opcją ustawioną *w czasie jego utworzenia*. Oznacza to, że wszystkie raporty łączące się z platformą SAP HANA utworzone przed lutym 2018 roku będą w dalszym ciągu traktować platformę SAP HANA jako źródło relacyjne. 

Obie metody charakteryzują się bardzo odmiennym zachowaniem i nie można przełączyć istniejącego raportu z jednej metody do drugiej. 

Przyjrzyjmy się dokładniej tym dwóm metodom.

## <a name="treat-sap-hana-as-a-multi-dimensional-source-default"></a>Traktuj platformę SAP HANA jako źródło wielowymiarowe (ustawienie domyślne)

Wszystkie nowe połączenia z platformą SAP HANA domyślnie używają tej metody łączenia i traktują platformę SAP HANA jako źródło wielowymiarowe. Aby traktować połączenie z platformą SAP HANA jak źródło relacyjne, należy wybrać kolejno opcje **Plik > Opcje i ustawienia > Opcje**, a następnie zaznaczyć pole wyboru w obszarze **Zapytanie bezpośrednie > Traktuj platformę SAP HANA jako źródło relacyjne**. Chociaż ta funkcja jest dostępna w **wersji zapoznawczej**, raportów utworzonych przy użyciu metody wielowymiarowej *nie można* publikować w usłudze Power BI. Takie działanie spowoduje błędy podczas otwarcia raportu w usłudze Power BI.  

W przypadku łączenia się z platformą SAP HANA jako źródłem wielowymiarowym:

* W oknie **Get Data Navigator** (Nawigator pobierania danych) można wybrać pojedynczy widok platformy SAP HANA. Wybranie pojedynczych miar i atrybutów nie jest możliwe. Zapytanie nie jest definiowane podczas nawiązywania połączenia, inaczej niż w przypadku importowania danych lub korzystania z zapytania bezpośredniego w czasie traktowania platformy SAP HANA jako źródła relacyjnego. Oznacza to, że w przypadku wybrania tej metody połączenia nie można bezpośrednio korzystać z zapytania SQL platformy SAP HANA.

* Wszystkie miary, hierarchie i atrybuty wybranego widoku zostaną wyświetlone na liście pól. 

* W przypadku użycia miary w wizualizacji do platformy SAP HANA przesyłane jest zapytanie, które ma na celu pobranie wartości miary na poziomie agregacji wymaganym przez wizualizację. Dlatego w przypadku miar (liczników, wskaźników itd.) niepoddających się agregacji wszelkie operacje agregacji są wykonywane przez platformę SAP HANA. Usługa Power BI nie wykonuje żadnych dalszych agregacji. 

* Aby zagwarantować, że z platformy SAP HANA będzie można zawsze uzyskać prawidłowe wartości agregacji, należy wprowadzić pewne ograniczenia. Na przykład nie można dodawać kolumn obliczeniowych ani łączyć danych z wielu widoków platformy SAP HANA w jednym raporcie. 

Traktowanie platformy SAP HANA jako źródła wielowymiarowego nie zapewnia większej elastyczności niż alternatywna metoda *relacyjna*, ale jest prostsze i gwarantuje prawidłowe wartości agregacji podczas pracy z bardziej złożonymi miarami platformy SAP HANA, generalnie zapewniając większą wydajność. 

Lista **Pole** zawiera wszystkie miary, atrybuty i hierarchie z widoku platformy SAP HANA. Należy zwrócić uwagę na następujące zachowania, które mają miejsce w przypadku korzystania z tej metody połączenia:

* Każdy atrybut uwzględniony w co najmniej jednej hierarchii jest domyślnie ukryty. W razie potrzeby można go jednak wyświetlić, wybierając opcję **Wyświetl ukryte** z menu kontekstowego na liście pól. Za pomocą tego samego menu kontekstowego można również włączyć wyświetlanie atrybutów jako widocznych, jeśli jest to wymagane.

* Na platformie SAP HANA można zdefiniować atrybut w taki sposób, aby używał innego atrybutu jako etykiety. Na przykład atrybut **Product** (o wartościach 1,2,3 itd.) może używać atrybutu **ProductName** (o wartościach Rower, Koszulka, Rękawiczki itd.) jako swojej etykiety. W takim przypadku na liście pól jest widoczne jedno pole **Product**, którego wartościami będą etykiety Rower, Koszulka, Rękawiczki itd., ale które będzie sortowane i którego unikatowość będzie ustalana według kluczowych wartości 1, 2, 3. Utworzona zostaje również ukryta kolumna **Product.Key**, która w razie potrzeby umożliwia dostęp do podstawowych wartości kluczy. 

Wszelkie zmienne zdefiniowane w bazowym widoku platformy SAP HANA będą wyświetlane w czasie nawiązywania połączenia. Można wówczas wprowadzić niezbędne wartości. Wartości te można następnie zmienić, wybierając ze wstążki opcję **Edytuj zapytania**, a następnie z wyświetlonego menu podręcznego opcję **Zarządzaj parametrami**. 

Dozwolone operacje modelowania są bardziej restrykcyjne niż ogólne użycie zapytania bezpośredniego, co wynika z potrzeby zapewnienia możliwości uzyskania poprawnych zagregowanych danych z platformy SAP HANA w każdej sytuacji. W dalszym ciągu można jednak wprowadzić liczne zmiany i dodatki, m.in. zdefiniować miary, zmienić nazwy pól i je ukryć oraz zdefiniować formaty wyświetlania. Wszelkie takie zmiany zostaną zachowane po odświeżeniu, a wszystkie zmiany niepowodujące konfliktu zostaną zastosowane do widoku platformy SAP HANA. 

### <a name="additional-modeling-restrictions"></a>Dodatkowe ograniczenia modelowania

Najważniejsze dodatkowe ograniczenia dotyczące modelowania w przypadku nawiązywania połączenia z platformą SAP HANA (traktowaną jako źródło wielowymiarowe) przy użyciu zapytania bezpośredniego są następujące: 

* **Brak obsługi kolumn obliczeniowych:** możliwość tworzenia kolumn obliczeniowych została wyłączona. Oznacza to również, że funkcje grupowania i klastrowania, które tworzą kolumny obliczeniowe, nie są dostępne.
* **Dodatkowe ograniczenia dotyczące miar:** istnieją dodatkowe ograniczenia dotyczące wyrażeń języka DAX, które mogą zostać użyte w miarach, odzwierciedlające poziom obsługi oferowany przez system SAP HANA.
* **Brak obsługi definiowania relacji:** tylko dla jednego widoku w raporcie można wykonywać zapytania, w związku z czym definiowanie relacji nie jest obsługiwane.
* **Brak widoku danych:** w **widoku danych** zwykle są wyświetlane szczegółowe dane tabel. Ze względu na charakter źródeł OLAP, takich jak SAP HANA, ten widok nie jest dostępny w przypadku połączenia z platformą SAP HANA.
* **Stałe szczegóły kolumn i miar:** lista kolumn i miar na liście pól jest ustalana przez bazowe źródło danych i nie można jej zmienić. Nie można na przykład usunąć kolumny ani zmienić typu danych (można jednak zmienić jej nazwę).
* **Dodatkowe ograniczenia dotyczące języka DAX:** istnieją dodatkowe ograniczenia dotyczące wyrażeń języka DAX, które mogą zostać użyte w definicjach miar, odzwierciedlające ograniczenia w źródle. Nie można na przykład zastosować funkcji agregującej do tabeli.

### <a name="additional-visualization-restrictions"></a>Dodatkowe ograniczenia wizualizacji

W przypadku nawiązywania połączenia z platformą SAP HANA (traktowanej jako źródła wielowymiarowego) przy użyciu zapytania bezpośredniego obowiązują ograniczenia wizualizacji: 
* **Brak agregacji kolumn:** nie można zmienić sposobu agregacji kolumny w wizualizacji — zawsze jest to opcja *Nie sumuj*.

## <a name="treat-sap-hana-as-a-relational-source"></a>Traktuj platformę SAP HANA jako źródło relacyjne 

Wybór opcji połączenia z platformą SAP HANA jako źródłem relacyjnym zapewnia zwiększoną elastyczność. Na przykład można tworzyć kolumny obliczeniowe, uwzględniać dane z wielu widoków platformy SAP HANA i tworzyć relacje między tabelami wynikowymi. Jednak w przypadku takiego użycia platformy SAP HANA ważne jest, by zrozumieć pewne aspekty związane ze sposobem traktowania połączeń. Pozwoli to zagwarantować, że: 

* Wyniki są zgodnie z oczekiwaniami, gdy widok SAP HANA zawiera miary niepoddające się agregacji (na przykład różne liczniki lub średnie zamiast zwykłych sum).
* Zapytania wynikowe są wydajne.

Na początek zaleca się wyjaśnienie zachowania źródła relacyjnego, takiego jak program SQL Server, gdy zapytanie zdefiniowane w oknie **Pobieranie danych** lub **Edytorze zapytań** wykonuje agregację. W poniższym przykładzie zapytanie zdefiniowane w **Edytorze zapytań** zwraca średnią cenę według kolumny *ProductID*.  

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

Jeśli dane zostaną zaimportowane do usługi Power BI (w przeciwieństwie do użycia zapytania bezpośredniego), spowoduje to następujące konsekwencje:

* Dane zostaną zaimportowane na poziomie agregacji zdefiniowanym przez zapytanie utworzone w **Edytorze zapytań**. Na przykład średnia cena według produktu. W konsekwencji zostanie utworzona tabela z dwiema kolumnami: *ProductID* i *AveragePrice*, które mogą zostać użyte w wizualizacjach.
* W wizualizacji każda kolejna agregacja (na przykład *Sum*, *Average*, *Min* i inne) jest wykonywana na zaimportowanych danych. Na przykład dołączenie kolumny *AveragePrice* do wizualizacji spowoduje domyślne użycie agregacji *Sum* i zwróci sumę z kolumny *AveragePrice* dla każdego produktu o identyfikatorze  *ProductID*, czyli w tym przykładzie wartość 13,67. Dotyczy to każdej alternatywnej funkcji agregującej (takiej jak *Min*, *Average* itd.) używanej w wizualizacji. Na przykład funkcja *Average* zwróci dla kolumny *AveragePrice* średnią wartości 6,66, 4 i 3, co da liczbę 4,56, a nie średnią 6 rekordów z kolumny *Price* tabeli bazowej, czyli liczbę 5,17.
  
Jeśli zamiast importowania zostanie wykonane **zapytanie bezpośrednie** (za pośrednictwem tego samego źródła relacyjnego), zastosowanie będzie mieć ta sama semantyka i wyniki będą dokładnie takie same:  

* Dla tego samego zapytania w warstwie raportowania zostaną przedstawione logicznie dokładnie te same dane — nawet jeśli dane nie zostaną w rzeczywistości zaimportowane.

* W wizualizacji każda kolejna agregacja (*Sum*, *Average*, *Min* i inne) jest znowu wykonywana na tabeli logicznej z zapytania. I ponownie wizualizacja zawierająca funkcję *Average* z kolumny *AveragePrice* zwróci tę samą wartość — 4,56.
  
Przyjrzyjmy się teraz platformie SAP HANA, gdy połącznie jest traktowane jako źródło relacyjne. Usługa Power BI może pracować na platformie SAP HANA zarówno w *widokach analitycznych*, jak i *widokach obliczeniowych*, które mogą zawierać miary. Aktualnie w przypadku platformy SAP HANA mają zastosowanie te same zasady, które opisano wcześniej w tej sekcji. Zapytanie zdefiniowane w oknie **Pobieranie danych** lub **Edytor zapytań** determinuje dostępne dane. Każda kolejna agregacja w wizualizacji jest wykonywana z użyciem tych danych, co dotyczy zarówno importowania, jak i wykonywania zapytania bezpośredniego.  
Jednak ze względu na charakter platformy SAP HANA zapytanie zdefiniowane w początkowym oknie dialogowym **Pobieranie danych** lub **Edytor zapytań** jest zawsze zapytaniem agregującym i zwykle obejmuje miary, a rzeczywista agregacja, która zostanie użyta, jest definiowana w widoku platformy SAP HANA.

W przykładzie odpowiadającym znajdującemu się wyżej przykładowi z programu SQL Server przedstawiono widok platformy SAP HANA zawierający kolumny *ID*, *ProductID*, *DepotID* i miary, w tym miarę *AveragePrice* zdefiniowaną w widoku jako *Średnia cena*.  
    
Jeśli w oknie **Pobieranie danych** wybrano dane dla miar **ProductID** i **AveragePrice**, definiują one zapytanie w widoku, które zawiera żądanie danych zagregowanych (we wcześniejszym przykładzie dla uproszczenia użyto pseudojęzyka SQL, który nie odpowiada dokładnie składni języka SAP HANA SQL). W przypadku takiego zapytania wszelkie dalsze agregacje zdefiniowane w wizualizacji prowadzą do większej agregacji wyników. Tak samo jak w powyższym przykładzie dotyczącym programu SQL Server, dotyczy to zarówno importowania, jak i wykonywania zapytania bezpośredniego. Należy zauważyć, że w przypadku użycia zapytania bezpośredniego zapytanie pochodzące z okna **Pobieranie danych** lub **Edytor zapytań** zostanie użyte w podwyborach dokonanych w obrębie pojedynczego zapytania wysłanego do platformy SAP HANA i dlatego w takim przypadku w rzeczywistości wszystkie dane nie zostaną wczytane przed dalszym ich agregowaniem.  

Wszystkie te zagadnienia i zachowania powodują, że w przypadku korzystania z zapytania bezpośredniego na platformie SAP HANA należy wziąć pod uwagę następujące ważne kwestie:  

* Należy zwrócić uwagę na kolejne agregacje wykonywane w wizualizacjach, gdy miara na platformie SAP HANA nie jest addytywna (na przykład nie jest to prosta funkcja *Sum*, *Min* czy *Max*).

* W oknie **Pobieranie danych** lub **Edytor zapytań** należy korzystać tylko z wymaganych kolumn w celu zwrócenia niezbędnych danych ze względu na fakt, że wynik będzie zapytaniem, które musi być zapytaniem uzasadnionym możliwym do przesłania na platformę SAP HANA. Na przykład jeśli wybrano dziesiątki kolumn z przekonaniem, że mogą one być wymagane w kolejnych wizualizacjach, to nawet w przypadku zapytania bezpośredniego prosta wizualizacja będzie oznaczać, że zapytanie agregujące używane w podwyborze będzie zawierać te dziesiątki kolumn, co zwykle doprowadza do znacznego zmniejszenia wydajności.
  
Spójrzmy na przykład. W poniższym przykładzie wybranie pięciu kolumn (**CalendarQuarter**, **Color**, **LastName**, **ProductLine**, **SalesOrderNumber**) w oknie dialogowym **Pobieranie danych** wraz z miarą *OrderQuantity* oznacza, że późniejsze utworzenie prostej wizualizacji zawierającej funkcję Min OrderQuantity spowoduje wysłanie następującego zapytania SQL do platformy SAP HANA. Zacieniony fragment to podwybór zawierający zapytanie z okna dialogowego **Pobieranie danych** / **Edytor zapytań**. Jeśli ten podwybór daje wynik o bardzo dużej kardynalności, to najprawdopodobniej wynikowa wydajność platformy SAP HANA będzie niska.  

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

   
W związku z tym zachowaniem zaleca się, aby elementy wybierane w oknie **Pobieranie danych** lub **Edytor zapytań** były ograniczone do tych, które są niezbędne. Zapewni to uzyskanie odpowiednich wyników zapytania z platformy SAP HANA.  

## <a name="best-practices"></a>Najlepsze rozwiązania 

W przypadku obu metod łączenia się z platformą SAP HANA zalecenia dotyczące zapytania bezpośredniego mają również zastosowanie do platformy SAP HANA, zwłaszcza te związane z zapewnianiem wysokiej wydajności. Zalecenia te zostały szczegółowo opisane w artykule [Używanie zapytania bezpośredniego w usłudze Power BI](desktop-directquery-about.md).
   
## <a name="limitations"></a>Ograniczenia

Poniższa lista zawiera wszystkie funkcje platformy SAP HANA, które nie są w pełni obsługiwane lub działają inaczej niż w przypadku korzystania z usługi Power BI. 

* **Hierarchie nadrzędny-podrzędny** — hierarchie nadrzędny-podrzędny nie będą widoczne w usłudze Power BI.
Wynika to z faktu, że usługa Power BI uzyskuje dostęp do platformy SAP HANA przy użyciu interfejsu SQL, a hierarchie nadrzędny-podrzędny nie są w pełni dostępne za pośrednictwem programu SQL.
* **Inne metadane hierarchii** — podstawowa struktura hierarchii jest wyświetlana w usłudze Power BI, jednak niektóre metadane hierarchii (np. kontrola zachowania hierarchii niewyrównanych) nie będą miały zastosowania.
Ponownie jest to spowodowane ograniczeniami narzuconymi przez interfejs SQL.
* **Połączenie przy użyciu protokołu SSL** — nie można nawiązać połączenia z wystąpieniami platformy SAP HANA skonfigurowanymi do używania protokołu SSL.
* **Obsługa widoków atrybutów** — usługa Power BI może nawiązać połączenie z widokami analitycznymi i obliczeniowymi, ale nie może łączyć się bezpośrednio z widokami atrybutów.
* **Obsługa obiektów wykazu** — usługa Power BI nie może łączyć się obiektami wykazu.
* **Modyfikowanie zmiennych po publikacji** — po opublikowaniu raportu nie można zmienić wartości żadnych zmiennych platformy SAP HANA bezpośrednio w usłudze Power BI. 
 
## <a name="known-issues"></a>Znane problemy 
Poniższa lista zawiera wszystkie znane problemy występujące podczas nawiązywania połączenia z platformą SAP HANA (zapytanie bezpośrednie) przy użyciu usługi Power BI. 

* **Problem z platformą SAP HANA w przypadku wykonywania zapytania dla miary Counters i innych miar** — w przypadku łączenia się z widokiem analitycznym, gdy miara Counter i niektóre inne miary wskaźnika znajdują się w tej samej wizualizacji, platforma SAP HANA zwraca nieprawidłowe dane. Informacje na ten temat znajdują się w uwadze dotyczącej rozwiązania SAP 2128928 (Wyniki niezgodne z oczekiwaniami w przypadku wykonywania zapytań dotyczących kolumny obliczeniowej i miary Counter). Miara wskaźnika będzie w tym przypadku nieprawidłowa. 

* **Wiele kolumn usługi Power BI z jednej kolumny platformy SAP HANA** — w przypadku niektórych widoków obliczeniowych, gdy kolumna platformy SAP HANA jest używana w więcej niż jednej hierarchii, platforma SAP HANA wyświetla dwa oddzielne atrybuty. Powoduje to utworzenie dwóch kolumn w usłudze Power BI.  Te kolumny są jednak domyślnie ukryte i wszystkie zapytania bezpośrednio obejmujące hierarchie lub kolumny działają prawidłowo. 
 
## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat zapytania bezpośredniego, zapoznaj się z następującymi zasobami:

* [Zapytanie bezpośrednie w usłudze Power BI](desktop-directquery-about.md)
* [Źródła danych obsługiwane przez zapytanie bezpośrednie](desktop-directquery-data-sources.md)
* [Zapytanie bezpośrednie i system SAP BW](desktop-directquery-sap-bw.md)
* [Lokalna brama danych](service-gateway-onprem.md)

