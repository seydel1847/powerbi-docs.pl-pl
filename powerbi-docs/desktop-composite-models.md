---
title: Używanie modeli złożonych w programie Power BI Desktop (wersja zapoznawcza)
description: Tworzenie modeli danych z wieloma połączeniami danych i relacjami wiele-do-wielu w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/23/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 4f882865271411d04a99c9213a68df24d000677d
ms.sourcegitcommit: 6faeb642721ee5abb41c04a8b729880c01c4d40e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2018
ms.locfileid: "39211352"
---
# <a name="composite-models-in-power-bi-desktop-preview"></a>Modele złożone w programie Power BI Desktop (wersja zapoznawcza)

Wcześniej, jeśli w programie **Power BI Desktop** użyto w raporcie trybu DirectQuery, użycie w nim innych połączeń danych — typu Direct Query lub Importowanie — było niedozwolone. Dzięki **modelom złożonym** to ograniczenie zostało usunięte, a w raporcie można bez problemów uwzględniać połączenia danych pochodzące z więcej niż jednego połączenia danych typu DirectQuery lub Importowanie w dowolnej kombinacji.

![modele złożone w programie Power BI Desktop](media/desktop-composite-models/composite-models_01.png)

Możliwość **Modele złożone** w programie **Power BI Desktop** składa się z trzech powiązanych funkcji:

* **Modele złożone** — umożliwia użycie w raporcie wielu połączeń danych, takich jak połączenia trybu DirectQuery lub importowanie, w dowolnej kombinacji.
* **Relacje wiele-do-wielu** — dzięki **modelom złożonym** można ustanawiać **relacje wiele-do-wielu** między tabelami, usuwać wymagania dotyczące unikatowe wartości w tabelach, a także usuwać wcześniejsze obejścia, takie jak wprowadzanie nowych tabel tylko w celu ustanowienia relacji. 
* **Tryb przechowywania** — można teraz określić, które wizualizacje wymagają wykonania zapytania dotyczącego źródła danych zaplecza. Wizualizacje niewymagające tej czynności są importowane, nawet jeśli są oparte na trybie DirectQuery, co zwiększa wydajność i redukuje obciążenie zaplecza. Wcześniej nawet proste wizualizacje, takie jak fragmentatory, inicjowały wysyłanie zapytań do źródeł zaplecza. 

Ta kolekcja trzech powiązanych funkcji **modeli złożonych** została opisana w osobnych artykułach:

* **Modele złożone** zostały szczegółowo opisane w tym artykule.
* **Relacje wiele-do-wielu** zostały opisane we własnym artykule: [Relacje wiele-do-wielu w programie Power BI Desktop (wersja zapoznawcza)](desktop-many-to-many-relationships.md).
* **Tryb przechowywania** został opisany we własnym artykule: [Tryb przechowywania w programie Power BI Desktop (wersja zapoznawcza)](desktop-storage-mode.md).

## <a name="enabling-the-composite-models-preview-feature"></a>Włączanie funkcji modeli złożonych w wersji zapoznawczej

Funkcja **Modele złożone** jest dostępna w wersji zapoznawczej i należy ją włączyć w programie **Power BI Desktop**. Aby włączyć **modele złożone**, wybierz pozycję **Plik > Opcje i ustawienia > Opcje > Funkcje w wersji zapoznawczej**, a następnie zaznacz pole wyboru **Modele złożone**. 

![włączanie funkcji w wersji zapoznawczej](media/desktop-composite-models/composite-models_02.png)

Aby funkcja została włączona, należy ponownie uruchomić program **Power BI Desktop**.

![ponowne uruchomienie wymagane do uwzględnienia zmian](media/desktop-composite-models/composite-models_03.png)


## <a name="using-composite-models"></a>Używanie modeli złożonych

Dzięki **modelom złożonym** można połączyć się z szeroką gamą różnych źródeł danych, korzystając z programu **Power BI Desktop** lub **usługi Power BI**. Te połączenia z danymi można wykonywać na różne sposoby. Można zaimportować dane do usługi Power BI, co jest najczęściej używanym sposobem pobierania danych, lub można połączyć się bezpośrednio z danymi w ich oryginalnym repozytorium źródłowym przy użyciu trybu DirectQuery. Szczegółowe informacje na temat trybu DirectQuery przedstawiono w artykule [Używanie zapytania bezpośredniego w usłudze Power BI](desktop-directquery-about.md).

W przypadku korzystania z trybu DirectQuery **modele złożone** pozwalają na utworzenie modelu usługi Power BI (takiego jak pojedynczy plik PBIX programu Power BI Desktop), który wykonuje następujące czynności:

* łączy dane z jednego lub kilku źródeł trybu DirectQuery i/lub
* łączy dane z jednego lub kilku źródeł trybu DirectQuery i dane importu

Na przykład za pomocą funkcji **modeli złożonych** można utworzyć model, który łączy dane sprzedaży z magazynu danych przedsiębiorstwa z danymi dotyczącymi celów sprzedaży z bazy danych SQL Server działu oraz z niektórymi danymi zaimportowanymi z arkusza kalkulacyjnego. Model, który łączy dane z więcej niż jednego źródła trybu DirectQuery lub łączy tryb DirectQuery z zaimportowanymi danymi, jest określany jako *model złożony*.

> [!NOTE]
> Mimo że modele złożone są dostępne w wersji zapoznawczej, nie można publikować ich w usłudze Power BI. 

Relacje między tabelami można tworzyć w zwykły sposób, nawet gdy pochodzą z różnych źródeł, z następującym ograniczeniem: wszystkie relacje obejmujące wiele źródeł należy definiować jako relacje z kardynalnością **Wiele-do-wielu**, niezależnie od ich rzeczywistej kardynalności. Te relacje zachowują się jak zwykłe relacje **wiele-do-wielu**, co opisano w artykule [Relacje wiele-do-wielu w programie Power BI Desktop (wersja zapoznawcza)](desktop-many-to-many-relationships.md). Należy zauważyć, że w kontekście modeli złożonych wszystkie zaimportowane tabele są faktycznie pojedynczym źródłem, niezależnie od rzeczywistego bazowego źródła danych, z poziomu którego będą w rzeczywistości importowane.   

## <a name="example-of-using-composite-models"></a>Przykład użycia modeli złożonych

Jako przykład **modelu złożonego** weź pod uwagę raport połączony z magazynem danych firmowych (w programie SQL Server) przy użyciu trybu DirectQuery, w którym magazyn zawiera dane typu *Sales by Country* (Sprzedaż według kraju),  *Quarter* (Kwartał) i *Bike (Product)* (Rower (Produkt)), jak pokazano na poniższej ilustracji.

![widok relacji w przypadku modeli złożonych](media/desktop-composite-models/composite-models_04.png)

W tym momencie można tworzyć proste wizualizacje przy użyciu pól z tego źródła. Na przykład poniższa wizualizacja przedstawia całkowitą sprzedaż według elementu *ProductName* dla wybranego kwartału. 

![wizualizacja oparta na danych](media/desktop-composite-models/composite-models_05.png)

Ale co zrobić, jeśli masz niektóre informacje na temat menedżera produktu, który został przypisany do każdego produktu, oraz priorytet marketingowy? Gdzie te dane są przechowywane w arkuszu kalkulacyjnym programu Excel? Możesz wyświetlić wartość *Sales Amount* (Kwota sprzedaży) według elementu *Product Manager* (Menedżer produktu), jednak dodanie tych lokalnych danych do magazynu danych firmowych będzie prawdopodobnie niemożliwe lub potrwa minimalnie kilka miesięcy. Mimo że te dane sprzedaży można zaimportować z magazynu danych (zamiast korzystać z trybu DirectQuery) — w tym momencie zostałyby one połączone z danymi zaimportowanymi z arkusza kalkulacyjnego — takie podejście jest nieuzasadnione, jeśli weźmiemy pod uwagę przyczyny, które mogą przede wszystkim prowadzić do korzystania z trybu DirectQuery — takie jak niektóre kombinacje reguł zabezpieczeń wymuszane w źródle bazowym, potrzeba wyświetlenia najnowszych danych oraz dane na ogromną skalę. 

W tym momencie warto skorzystać z **modeli złożonych**. Modele złożone oferują opcję łączenia z magazynem danych przy użyciu trybu DirectQuery, a następnie również przy użyciu metody GetData w przypadku dodatkowych źródeł. W tym przypadku ustanawiamy połączenie DirectQuery z magazynem danych firmowych, a następnie używamy metody GetData i wybieramy program Excel, przechodzimy do arkusza kalkulacyjnego zawierającego nasze dane lokalne i możemy zaimportować arkusz zawierający element *ProductNames* (Nazwy produktów), przypisanego menedżera sprzedaży *SalesManager* oraz element *Priority* (Priorytet).  

![Okno Nawigator](media/desktop-composite-models/composite-models_06.png)

Teraz na liście **Pola** widzimy oryginalną tabelę *Bike* (Rower) (z programu SQL Server) i nową tabelę *Product Managers* (Menedżerowie produktów) (z danymi zaimportowanymi z programu Excel). 

![widok Pola tabel](media/desktop-composite-models/composite-models_07.png)

Podobnie analizując **widok relacji** w programie **Power BI Desktop**, zobaczymy teraz dodatkową tabelę o nazwie *Product Managers* (Menedżerowie produktów). 

![widok relacji tabel](media/desktop-composite-models/composite-models_08.png)

Musimy teraz w zwykły sposób powiązać je z innymi tabelami w modelu, tworząc relację między tabelą *Bike* (Rower) (w programie SQL Server) i tabelą *Product Managers* (Menedżerowie produktów) (importowaną), taką jak relacja między elementami *Bike[ProductName]* i *ProductManagers[ProductName]*. Zgodnie z opisem we wcześniejszej części tego artykułu wszystkie relacje obejmujące źródło muszą mieć kardynalność **wiele-do-wielu** i jest to kardynalność wybierana domyślnie. 

![okno dialogowe tworzenia relacji](media/desktop-composite-models/composite-models_09.png)

Jeśli utworzono tę relację, zostanie ona zgodnie z oczekiwaniami wyświetlona w **widoku relacji** w programie **Power BI Desktop**.

![widok nowej relacji](media/desktop-composite-models/composite-models_10.png)

Po ustanowieniu tych relacji między tabelami możemy teraz tworzyć wizualizacje przy użyciu dowolnych pól z listy **Pola**, bezproblemowo łącząc dane z wielu źródeł. Na przykład poniższa wizualizacja przedstawia łączną kwotę sprzedaży *Sales Amount* dla każdego menedżera produktu *Product Manager*. 

![wizualizacja z wyświetlonym okienkiem Pola](media/desktop-composite-models/composite-models_11.png)

W tym przykładzie przedstawiono typowy przypadek tabeli *wymiarów* (takiej jak *Product* (Produkt) lub *Customer* (Klient)) rozszerzanej przy użyciu dodatkowych danych importowanych z innej lokalizacji. Można również ustawić tabele tak, aby używały trybu DirectQuery do łączenia się z innymi źródłami. Dlatego w celu rozszerzenia naszego przykładu załóżmy, że wartości *SalesTargets* (Cele sprzedaży) dla poszczególnych elementów *Country* (Kraj) i *Period* (Okres) są przechowywane w oddzielnej bazie danych działu. Możesz użyć metody **GetData**, aby połączyć się z tymi danymi w zwykły sposób, jak pokazano na poniższej ilustracji. 

![Okno dialogowe Nawigator](media/desktop-composite-models/composite-models_12.png)

Następnie, podobnie jak zrobiliśmy to wcześniej w tym przykładzie, możemy tworzyć relacje między nową tabelą i innymi tabelami w modelu oraz tworzyć wizualizacje łączące odpowiednie dane. Przyjrzyjmy się ponownie **widokowi relacji**, w którym ustanowiliśmy nowe relacje w naszym rozszerzonym przykładowym scenariuszu.

![widok relacji zawierający wiele tabel](media/desktop-composite-models/composite-models_13.png)

Jak pokazano na poniższej ilustracji opartej na nowych danych i właśnie utworzonej relacji, wizualizacja w lewym dolnym rogu pokazuje całkowitą wartość *Sales Amount* (Kwota sprzedaży) w porównaniu do wartości *Target* (Cel) z obliczeniem odchylenia przedstawiającym różnicę, gdzie wartości *Sales Amount* (Kwota sprzedaży) i *Target* (Cel) pochodzą z dwóch różnych baz danych programu SQL Server. 

![wizualizacja przedstawiająca większą ilość danych](media/desktop-composite-models/composite-models_14.png)

## <a name="setting-storage-mode"></a>Ustawianie trybu przechowywania

Każda tabela w **modelu złożonym** ma **tryb przechowywania** wskazujący, czy tabela jest oparta na trybie DirectQuery, czy też na imporcie. **Tryb przechowywania** można wyświetlać i modyfikować w okienku **Właściwości**. Aby do niego przejść, wybierz pozycję **Właściwości** z listy **Pola** i kliknij menu kontekstowe prawym przyciskiem myszy. Na poniższej ilustracji przedstawiono **tryb przechowywania** (skrócony do **Tryb...** ze względu na szerokość okienka).

![Ustawienie Tryb przechowywania](media/desktop-composite-models/composite-models_15.png)

**Tryb przechowywania** jest również widoczny na etykietce narzędzia dla każdej tabeli.

![etykietka narzędzia z trybem przechowywania](media/desktop-composite-models/composite-models_16.png)

Dla każdego pliku programu **Power BI Desktop** (pliku pbix) zawierającego kilka spośród tabel trybu DirectQuery i importu na pasku stanu jest wyświetlany **tryb przechowywania** o wartości **Mieszany**. Można kliknąć ten termin na pasku stanu i łatwo przełączyć wszystkie tabele na tryb importu.

Szczegółowe informacje dotyczące **trybu przechowywania** zostały w całości przedstawione w artykule [Tryb przechowywania w programie Power BI Desktop (wersja zapoznawcza)](desktop-storage-mode.md).  

## <a name="calculated-tables"></a>Tabele obliczeniowe

Tabele obliczeniowe można dodawać do modelu, który używa trybu DirectQuery. Kod języka DAX definiujący tabelę obliczeniową może odwoływać się do tabel importu lub DirectQuery albo kombinacji obydwu tych rodzajów. 

Tabele obliczeniowe są zawsze importowane, a dane w tych tabelach są odświeżane podczas odświeżania tabeli. W efekcie, jeśli tabela obliczeniowa odwołuje się do tabeli trybu DirectQuery, wizualizacje odwołujące się do tabeli DirectQuery zawsze przedstawiają najnowsze wartości w źródle bazowym, ale wizualizacje odwołujące się do tabeli obliczeniowej przedstawiają wartości w momencie ostatniego odświeżenia tabeli obliczeniowej.

## <a name="security-implications"></a>Implikacje dotyczące bezpieczeństwa 

Modele złożone powodują pewne implikacje dotyczące bezpieczeństwa. Zapytanie wysłane do jednego źródła danych może uwzględniać wartości danych, które zostały pobrane z innego źródła. W przykładzie opisanym wcześniej w tym artykule wizualizacja, która przedstawia wartość *Sales Amount* (Kwota sprzedaży) według elementu *Product Manager* (Menedżer produktu), spowoduje wysłanie zapytania SQL do relacyjnej bazy danych **Sales** (Sprzedaż), gdzie to zapytanie SQL może zawierać nazwy elementów *Product Manager* i ich skojarzone elementy *Product* (Produkt). 

![skrypt przedstawiający implikacje dotyczące bezpieczeństwa](media/desktop-composite-models/composite-models_17.png)

Z tego względu informacje przechowywane w arkuszu kalkulacyjnym są teraz uwzględniane w zapytaniu wysłanym do relacyjnej bazy danych. Jeśli te informacje są poufne, należy rozważyć odpowiednie implikacje dotyczące bezpieczeństwa. W szczególności należy wziąć pod uwagę następujące konsekwencje:

* Każdy administrator bazy danych, który może wyświetlić ślady lub dzienniki inspekcji, będzie mógł zobaczyć te informacje, nawet jeśli nie miał uprawnień dostępu do danych w ich oryginalnym źródle (w tym przypadku uprawnień do pliku programu Excel).

* Należy wziąć pod uwagę ustawienia szyfrowania poszczególnych źródeł, aby uniknąć pobrania informacji z jednego źródła przy użyciu połączenia zaszyfrowanego, a następnie ich przypadkowego uwzględnienia w zapytaniu wysłanym do innego źródła przy użyciu połączenia niezaszyfrowanego. 

Program **Power BI Desktop** wyświetla komunikat ostrzegawczy, gdy zostanie podjęta akcja w celu utworzenia modelu złożonego, aby zezwolić na potwierdzenie, że wszelkie implikacje dotyczące bezpieczeństwa zostały wzięte pod uwagę.  

Z podobnych względów należy zachować ostrożność podczas otwierania pliku programu **Power BI Desktop** wysłanego z niezaufanego źródła. Jeśli ten plik zawiera modele złożone, oznacza to, że informacje pobrane z jednego źródła (przy użyciu poświadczeń użytkownika otwierającego plik) zostałyby wysłane do innego źródła danych jako część zapytania (gdzie mogłyby być prawdopodobnie widoczne dla złośliwego autora pliku programu Power BI Desktop). Z tego względu jeśli otwierany po raz pierwszy plik programu Power BI Desktop zawiera wiele źródeł, zostanie wyświetlone ostrzeżenie. To ostrzeżenie jest podobne do ostrzeżenia wyświetlanego podczas otwierania pliku zawierającego natywne zapytania SQL.  

## <a name="performance-implications"></a>Implikacje dotyczące wydajności  

W przypadku używania trybu DirectQuery należy zawsze brać pod uwagę wydajność, głównie po to, aby zapewnić, że źródło zaplecza ma wystarczające zasoby i może zaoferować użytkownikom skuteczne środowisko pracy. Skutecznie działające środowisko to takie, w którym wizualizacje są odświeżane co 5 sekund lub częściej. Należy również stosować się do porad dotyczących wydajności z artykułu [Używanie trybu DirectQuery w usłudze Power BI](desktop-directquery-about.md). Użycie modeli złożonych dodaje kolejne zagadnienia do rozważenia dotyczące wydajności, ponieważ jedna wizualizacja może spowodować wysyłanie zapytań do wielu źródeł, a także często przekazywanie wyników z jednego zapytania do drugiego źródła. Taka sytuacja może spowodować następujące formy wykonywania:

* **Zapytanie SQL, która zawiera dużą liczbę wartości literałów** — na przykład wizualizacja żądająca łącznej wartości *Sales Amount* (Kwota sprzedaży) (z bazy danych SQL) dla zestawu wybranych elementów *Product Manager* (Menedżer produktu) (z powiązanej tabeli, która została zaimportowana z arkusza kalkulacyjnego) musiałaby najpierw ustalić, które elementy *Product* (Produkt) były zarządzane przez danych menedżerów produktu przed wysłaniem zapytania SQL uwzględniającego wszystkie identyfikatory produktów w klauzuli *WHERE*.

* **Zapytanie SQL wykonywane na niższym poziomie szczegółowości z danymi następnie agregowanymi lokalnie** — jest używany ten sam przykład, co dla poprzedniego elementu na tej liście wypunktowanej. W miarę, jak liczba elementów *Product* (Produkt) spełniających warunki filtru elementu *Product Manager* (Menedżer produktu) staje się bardzo duża, w pewnym momencie uwzględnienie wszystkich elementów w klauzuli *WHERE* staje się nieefektywne lub niemożliwe. W zamian należy wykonać zapytanie dotyczące źródła relacyjnego na niższym poziomie elementu *Product* (Produkt), a następnie lokalnie zagregować wyniki. Jeśli kardynalność elementów *Product* (Product) przekracza limit wynoszący 1 milion, wykonywanie zapytania zakończy się niepowodzeniem.

* **Wiele zapytań SQL, jedno na grupę według wartości** — jeśli agregacja używa elementu **DistinctCount** pogrupowanego według kolumny z innego źródła, a źródło zewnętrzne nie obsługuje efektywnego przekazywania wielu wartości literałów definiujących grupowanie, konieczne jest wysłanie jednego zapytania SQL na grupę według wartości. Na przykład wizualizacja żądająca liczności unikatowych wartości *CustomerAccountNumber* (numer konta klienta) (z tabeli programu SQL Server) według elementu *Product Manager* (Menedżer produktu) (z powiązanej tabeli zaimportowanej z arkusza kalkulacyjnego) musiałaby przekazać szczegóły z tabeli *Product Managers* (Menedżerowie produktów) w zapytaniu wysłanym do programu SQL Server. W przypadku innych źródeł, takich jak Redshift, jest to niemożliwe. W zamian będzie istnieć tylko wysłane jedno zapytanie SQL na element *Sales Manager* (Menedżer sprzedaży) (do poziomu wskazanego przez praktyczny limit, po przekroczeniu którego zapytanie zakończy się niepowodzeniem). 

Każdy z tych przypadków ma własny wpływ na wydajność, a szczegóły różnią się w zależności od źródła danych. Skuteczną praktyczną regułą jest to, że jeśli kardynalność kolumn używanych w relacji łączącej dwa źródła pozostaje niska (kilka tysięcy), nie powinna mieć znaczącego wpływu na wydajność. W miarę wzrostu kardynalności pojawia się więcej zagadnień do wzięcia pod uwagę, które mogą wpływać na wynikową wydajność. 

Ponadto użycie relacji **wiele do wielu** oznacza, że do bazowego źródła trzeba wysyłać oddzielne zapytania na każdym poziomie sumy/sumy podrzędnej, zamiast agregować szczegółowe wartości lokalnie. W efekcie prosta wizualizacja tabeli zawierająca sumy wyśle dwa zapytania SQL zamiast jednego. 

## <a name="limitations-and-considerations"></a>Ograniczenia i istotne zagadnienia

Istnieje kilka ograniczeń tej wersji **modeli złożonych**.

Następujących źródeł wielowymiarowych nie można używać z **modelami złożonymi**:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Zestawy danych usługi Power BI

W przypadku łączenia ze źródłami wielowymiarowymi w trybie DirectQuery nie można również połączyć się z innym źródłem DirectQuery ani utworzyć kombinacji z danymi importowanymi.

Istniejące ograniczenia użycia trybu DirectQuery nadal obowiązują w przypadku korzystania z **modeli złożonych**. Wiele z tych ograniczeń jest teraz określanych na tabelę, w zależności od **tryb przechowywania** tabeli. Na przykład kolumna obliczeniowa w zaimportowanej tabeli może odwoływać się do innych tabel, ale kolumna obliczeniowa w tabeli DirectQuery jest nadal ograniczona tak, aby odwoływać się tylko do kolumn w tej samej tabeli. Inne ograniczenia mają zastosowanie do modelu jako całości, jeśli dowolne tabele w modelu działają w trybie DirectQuery. Na przykład funkcje **QuickInsights** oraz **Pytania i odpowiedzi** nie są dostępne w modelu, jeśli dowolne uwzględnione w nim tabele mają **tryb przechowywania** ustawiony na DirectQuery. 

## <a name="next-steps"></a>Następne kroki

W poniższych artykułach bardziej szczegółowo opisano modele złożone oraz przedstawiono szczegóły trybu DirectQuery.

* [Relacje wiele-do-wielu w programie Power BI Desktop (wersja zapoznawcza)](desktop-many-to-many-relationships.md)
* [Tryb przechowywania w programie Power BI Desktop (wersja zapoznawcza)](desktop-storage-mode.md)

Artykuły dotyczące trybu DirectQuery:

* [Używanie trybu DirectQuery w usłudze Power BI](desktop-directquery-about.md)
* [Źródła danych obsługiwane przez tryb DirectQuery w usłudze Power BI](desktop-directquery-data-sources.md)

