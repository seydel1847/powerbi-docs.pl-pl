---
title: "Używanie zapytania bezpośredniego w usłudze Power BI"
description: "Opis używania zapytania bezpośredniego z poziomu usługi Power BI"
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
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 572f64cc0e6ba97c62c9a088c60cf3887bacc6ae
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="using-directquery-in-power-bi"></a>Używanie zapytania bezpośredniego w usłudze Power BI
Możesz połączyć się z szeroką gamą różnych źródeł danych, korzystając z programu **Power BI Desktop** lub **usługi Power BI**, i te połączenia z danymi możesz wykonywać w różny sposób. Możesz albo *zaimportować* dane do usługi Power BI, co jest najczęściej używanym sposobem pobierania danych, lub możesz połączyć się bezpośrednio z danymi w ich oryginalnym repozytorium źródłowym, co jest nazywane **zapytaniem bezpośrednim**. W tym artykule zostało opisane **zapytanie bezpośrednie** i jego możliwości, łącznie z następującymi tematami:

* Różne opcje łączności dla zapytania bezpośredniego
* Wskazówki dotyczące tego, kiedy należy rozważyć użycie zapytania bezpośredniego zamiast importu
* Wady wynikające z użycia zapytania bezpośredniego
* Najlepsze rozwiązania dla używania zapytania bezpośredniego

W skrócie najlepszym rozwiązaniem dla używania funkcji importowania w porównaniu z zapytaniem bezpośrednim jest poniższe:

* Należy **importować** dane do usługi Power BI, gdzie tylko to możliwe. Wykorzystuje to przewagę wysokowydajnego aparatu zapytań usługi Power Bi oraz zapewnia obsługę danych o wysokiej interakcyjności i z pełnymi funkcjami.
* Jeśli Twoje cele nie mogą być osiągnięte przez zaimportowanie danych, rozważ użycie **zapytania bezpośredniego**. Na przykład, jeśli dane często się zmieniają i raporty muszą odzwierciedlać najnowsze dane, zapytanie bezpośrednie może być najlepsze. Jednak używanie zapytania bezpośredniego będzie, ogólnie mówiąc, przydatne tylko wtedy, gdy podstawowe źródło danych może zapewnić interaktywne zapytania (poniżej 5 sekund) dla typowego zagregowanego zapytania i będzie mogło obsłużyć obciążenie zapytaniami, które zostaną wygenerowane. Ponadto należy dokładnie rozważyć listę ograniczeń towarzyszących użyciu zapytania bezpośredniego, aby upewnić się, że nadal można osiągnąć swoje cele.

Zestaw możliwości oferowany przez usługę Power BI dla obu trybów łączności — importu i zapytania bezpośredniego — ewoluuje wraz z upływem czasu. Będzie to obejmowało zapewnienie większej elastyczności podczas korzystania z importowanych danych, ponieważ import może być używany w większości przypadków, jak również wyeliminowanie niektórych wad korzystania z zapytania bezpośredniego. Niezależnie od ulepszeń, podczas używania zapytania bezpośredniego wydajność bazowego źródła danych zawsze pozostanie główną kwestią do rozważenia. Jeśli to bazowe źródło danych jest powolne, wówczas używanie zapytań bezpośrednich do tego źródła pozostanie niecelowe.

W tym temacie omówiono zapytania bezpośrednie z usługi Power BI, a nie usługi SQL Server Analysis Services. Zapytanie bezpośrednie jest również funkcją **usług SQL Server Analysis Services** i wiele opisanych poniżej szczegółów ma zastosowanie do ich użycia, chociaż są również istotne różnice. Aby uzyskać informacje na temat używania zapytania bezpośredniego z usługami SQL Server Analysis Services, zobacz [oficjalny dokument zawierający szczegółowe dane na temat zapytania bezpośredniego w usługach SQL Server Analysis Services 2016](http://download.microsoft.com/download/F/6/F/F6FBC1FC-F956-49A1-80CD-2941C3B6E417/DirectQuery%20in%20Analysis%20Services%20-%20Whitepaper.pdf).  

Ten artykuł koncentruje się na zalecanym przepływie pracy dla zapytania bezpośredniego, w którym raport zostanie utworzony w programie **Power BI Desktop**, ale obejmuje również połączenie bezpośrednie w **usłudze Power BI**.

## <a name="power-bi-connectivity-modes"></a>Tryby łączności usługi Power BI
Usługa Power BI łączy się z bardzo dużą liczbą różnych źródeł danych obejmujących:

* Usługi online (Salesforce, Dynamics 365, inne)
* Bazy danych (SQL Server, Access, Amazon Redshift, inne)
* Pliki proste (Excel, JSON, inne)
* Inne źródła danych (Spark, witryny internetowe, Microsoft Exchange, inne)

Dla tych źródeł istnieje zazwyczaj możliwość importowania danych do usługi Power BI. W przypadku niektórych z nich istnieje również możliwość nawiązywania połączeń za pomocą zapytania bezpośredniego. Dokładny zestaw źródeł, które obsługują zapytanie bezpośrednie jest opisany w artykule [Data Sources supported by DirectQuery](desktop-directquery-data-sources.md) (Źródła danych obsługiwane przez zapytanie bezpośrednie). Więcej źródeł będzie obsługiwać zapytanie bezpośrednie w przyszłości, koncentrując się głównie na źródłach, po których można oczekiwać zapewnienia dobrej wydajności zapytania interakcyjnego.

Usługi **SQL Server Analysis Services** stanowią specjalny przypadek. Podczas nawiązywania połączenia z usługami SQL Server Analysis Services możesz wybrać importowanie danych lub użycie *połączenia na żywo*.  Użycie połączenia na żywo jest podobne do zapytania bezpośredniego w tym, że do bazowego źródła danych jest zawsze wysyłane zapytanie w celu odświeżenia wizualizacji, ale *połączenie na żywo* różni się w wielu innych kwestiach, więc jest używany inny termin (*na żywo* a *zapytanie bezpośrednie*).

Te trzy opcje nawiązywania połączenia z danymi – **import**, **zapytanie bezpośrednie** i **połączenie na żywo** – zostały szczegółowo objaśnione w poniższych sekcjach.

### <a name="import-connections"></a>Połączenia importowania
W przypadku korzystania z pozycji **Pobierz dane** w programie **Power BI Desktop** do nawiązywania połączenia ze źródłem danych, takim jak SQL Server, i po wybraniu pozycji **Import**, połączenie to zachowuje się w następujący sposób:

* Podczas początkowego korzystania z pozycji **Pobierz dane** każdy wybrany zestaw tabel definiuje zapytanie, które zwróci zestaw danych (te zapytania można edytować przed załadowaniem danych, na przykład w celu zastosowania filtrów lub agregacji danych, lub przyłączenia innych tabel).
* Podczas ładowania wszystkie dane zdefiniowane przez te zapytania zostaną zaimportowane do pamięci podręcznej usługi Power BI.
* Podczas tworzenia wizualizacji w programie **Power BI Desktop** zostanie wysłane zapytanie do zaimportowanych danych. Magazyn usługi Power BI zapewnia, że zapytania będą bardzo szybkie, dlatego wszystkie zmiany w wizualizacji zostaną natychmiast odzwierciedlone.
* Wszelkie zmiany w danych źródłowych nie zostaną odzwierciedlone w żadnych wizualizacjach. Konieczne jest *odświeżenie*, po którym dane zostaną ponownie importowane.
* Podczas publikowania raportu (pliku pbix) w **usłudze Power BI** zestaw danych jest tworzony i przekazywany do usługi Power BI.  Importowane dane są dołączane do tego zestawu danych. Następnie można skonfigurować planowane odświeżanie danych, na przykład w celu ponownego importowania danych każdego dnia. W zależności od lokalizacji oryginalnego źródła danych może być konieczne skonfigurowanie lokalnej bramy danych.
* Podczas otwierania istniejącego raportu w **usłudze Power BI** lub tworzenia nowych raportów do zaimportowanych danych jest ponownie wysyłane zapytanie, zapewniając możliwość interakcji.
* Wizualizacje lub całe strony raportu można przypinać jako kafelki pulpitu nawigacyjnego. Kafelki będą automatycznie odświeżane przy każdym odświeżeniu bazowego zestawu danych.  

### <a name="directquery-connections"></a>Połączenia zapytania bezpośredniego
W przypadku korzystania z pozycji **Pobierz dane** w programie **Power BI Desktop** do nawiązywania połączenia ze źródłem danych i po wybraniu pozycji **Zapytanie bezpośrednie** połączenie to zachowuje się w następujący sposób:

* Podczas początkowego korzystania z pozycji **Pobierz dane** następuje wybór źródła. W przypadku źródeł relacyjnych oznacza to wybranie zestawu tabel, z których każda nadal definiuje zapytanie zwracające logicznie zestaw danych. Dla wielowymiarowych źródeł, takich jak SAP BW, wybrane jest tylko określone źródło.
* Jednak po obciążeniu żadne dane faktycznie nie będą importowane do magazynu usługi Power BI. Zamiast tego podczas tworzenia wizualizacji w programie **Power BI Desktop** zapytania będą wysyłane do bazowego źródła danych w celu pobrania niezbędnych danych. Następnie czas potrzebny do odświeżenia wizualizacji będzie zależeć od wydajności bazowego źródła danych.
* Wszelkie zmiany w danych źródłowych nie zostaną natychmiast odzwierciedlone w żadnych istniejących wizualizacjach. Nadal jest wymagane odświeżanie, po czym niezbędne zapytania zostaną ponownie wysłane dla każdej wizualizacji, a wizualizacja zostanie zaktualizowana odpowiednio do potrzeb.
* Podczas publikowania raportu do **usługi Power BI** ponownie powstanie zestaw danych w usłudze Power BI, podobnie jak w przypadku importowania. Jednak *żadne dane* nie zostaną dołączone do tego zestawu danych.
* Podczas otwierania istniejącego raportu w **usłudze Power BI** lub tworzenia nowego raportu do bazowego źródła danych jest ponownie wykonywane zapytanie w celu pobrania niezbędnych danych. W zależności od lokalizacji oryginalnego źródła danych może być konieczne skonfigurowanie lokalnej bramy danych, jak to jest wymagane dla trybu importu, jeśli dane są odświeżane.
* Wizualizacje lub całe strony raportu można przypinać jako kafelki pulpitu nawigacyjnego. Aby upewnić się, że otwieranie pulpitu nawigacyjnego będzie szybkie, kafelki są automatycznie odświeżane zgodnie z harmonogramem (na przykład co godzinę). Częstotliwość tego odświeżania można kontrolować, aby odzwierciedlić częstotliwość zmiany danych oraz jak ważne jest, aby zobaczyć najnowsze dane. W związku z tym podczas otwierania pulpitu nawigacyjnego kafelki będą odzwierciedlać dane według czasu ostatniego odświeżenia i niekoniecznie najnowsze zmiany w bazowym źródle. Otwarty pulpit nawigacyjny można zawsze odświeżyć, aby upewnić się, że jest on aktualny.    

### <a name="live-connections"></a>Połączenia na żywo
Podczas nawiązywania połączenia z usługami **SQL Server Analysis Services** (SSAS) istnieje możliwość zaimportowania danych albo połączenia się z wybranym modelem danych na żywo. W przypadku wybrania **importu** należy następnie zdefiniować zapytanie do zewnętrznego źródła usług SSAS i dane zostaną normalnie zaimportowane. Jeśli wybrano **połączenie na żywo** następnie nie jest definiowane żadne zapytanie, a cały zewnętrzny model jest wyświetlany na liście pól. W przypadku wybrania **zapytania bezpośredniego**, w miarę budowy wizualizacji, zapytania są wysyłane do źródła zewnętrznego usług SSAS. Jednak, w odróżnieniu od zapytania bezpośredniego, nie ma żadnego znaczenia, w którym nowym *modelu* jest tworzony, innymi słowy, nie jest możliwe zdefiniowanie nowych kolumn obliczeniowych, hierarchii, relacji itd. Zamiast tego po prostu jest nawiązywane bezpośrednie połączenie z zewnętrznym modelem usług SSAS.

Sytuacja opisana w poprzednim akapicie ma zastosowanie do nawiązywania połączenia również z następującymi źródłami z tą różnicą, że nie jest dostępna opcja importowania danych:

* Zestawy danych usługi Power BI (na przykład podczas nawiązywania połączenia z zestawem danych usługi Power BI, który został wcześniej utworzony i opublikowany w usłudze, aby utworzyć nowy raport na ich podstawie)
* Usługa Common Data Service

Zachowanie raportów za pośrednictwem usług SSAS podczas publikowania w **usłudze Power BI** jest podobne do raportów zapytania bezpośredniego w następujący sposób:

* Podczas otwierania istniejącego raportu w **usłudze Power BI** lub tworzenia nowego raportu, do bazowego źródła usług SSAS jest wysyłane zapytanie (być może wymagające lokalnej bramy danych)
* Kafelki pulpitu nawigacyjnego są automatycznie odświeżane zgodnie z harmonogramem (na przykład co godzinę lub z dowolną inną zdefiniowaną częstotliwością)

Istnieją jednak również istotne różnice łącznie z tym, że dla połączeń na żywo tożsamość użytkownika otwierającego raport zawsze zostanie przekazana do źródła usług SSAS.

Odsuwając na bok te porównania skoncentrujmy się wyłącznie na **zapytaniach bezpośrednich** w pozostałej części tego artykułu.

## <a name="when-is-directquery-useful"></a>Kiedy zapytanie bezpośrednie jest przydatne?
W poniższej tabeli opisano scenariusze, w których połączenie z zapytaniem bezpośrednim może być szczególnie przydatne łącznie z przypadkami, w których pozostawienie danych w oryginalnym źródle mogłoby być uważane za korzystne. Opis zawiera omówienie tego, czy określony scenariusz jest dostępny w usłudze Power BI.

| Ograniczenie | Opis |
| --- | --- |
| Dane zmieniają się często i wymagane jest raportowanie prawie „w czasie rzeczywistym” |Modele z zaimportowanymi danymi można odświeżać co najwyżej raz na godzinę. W związku z tym, jeśli dane zmieniają się nieustannie i raporty muszą pokazywać najnowsze dane, wówczas używanie funkcji importowania z zaplanowanym odświeżaniem po prostu nie spełnia tych wymagań. Należy zapamiętać, że możliwe jest też przesyłanie strumieniowe danych bezpośrednio do usługi Power BI, chociaż w tym przypadku istnieją ograniczenia wielkości obsługiwanych danych. <br/> <br/> Z kolei użycie zapytania bezpośredniego oznacza, że otwieranie lub odświeżanie raportu lub pulpitu nawigacyjnego zawsze wyświetli najnowsze dane w źródle. Ponadto kafelki pulpitu nawigacyjnego można aktualizować częściej (nawet co 15 minut). |
| Dane są bardzo duże |Jeśli dane są bardzo duże, wówczas na pewno nie będzie celowe importowanie ich wszystkich. Natomiast zapytanie bezpośrednie nie wymaga przesyłania dużych danych, ponieważ zostanie wysłane zapytanie. <br/> <br/> Jednak duże dane mogą również oznaczać, że wydajność zapytań dla tego bazowego źródła będzie za mała (zgodnie z opisem w sekcji *Implikacje używania zapytania bezpośredniego* w dalszej części tego artykułu). I oczywiście nie zawsze jest konieczne importowanie pełnych szczegółowych danych. Zamiast tego dane mogą być wstępnie zagregowane podczas importowania (a **Edytor zapytań** ułatwia wykonanie właśnie tego). W skrajnej sytuacji będzie można zaimportować jedynie zagregowane dane potrzebne do każdej wizualizacji. Pomimo, że zapytanie bezpośrednie jest najprostszym podejściem do obsługi dużej ilości danych, należy zawsze pamiętać, że importowanie zagregowanych danych może być rozwiązaniem, jeśli bazowe źródło jest za wolne. |
| Zasady zabezpieczeń są zdefiniowane w bazowym źródle |Po zaimportowaniu danych usługa Power BI połączy się ze źródłem danych przy użyciu bieżących poświadczeń użytkowników (z programu Power BI Desktop) lub poświadczeń określonych w ramach konfigurowania zaplanowanego odświeżania (z usługi Power BI). W związku z tym podczas publikowania i udostępniania takiego raportu należy zwrócić uwagę na to, aby udostępniać go tylko użytkownikom, którzy mogą zobaczyć te same dane, lub zdefiniować zabezpieczenia na poziomie wiersza jako część zestawu danych. <br/> <br/> Jest to najlepsze rozwiązanie, ponieważ zapytanie bezpośrednie zawsze wysyła zapytanie do bazowego źródła, co powinno umożliwić zastosowanie wszelkich zabezpieczeń w tym bazowym źródle. Jednak obecnie usługa Power BI będzie zawsze łączyć się z bazowym źródłem przy użyciu tych samych poświadczeń, które zostałyby użyte do importu. <br/> <br/> W związku z tym, dopóki usługa Power BI umożliwia przekazanie tożsamości użytkownika raportu do bazowego źródła, zapytanie bezpośrednie nie oferuje żadnych korzyści dotyczących zabezpieczeń źródła danych. |
| Mają zastosowanie ograniczenia suwerenności danych |Niektóre organizacje mają zasady dotyczące suwerenności danych, co oznacza, że dane nie mogą opuścić lokalizacji organizacji. Rozwiązania oparte na imporcie będą wyraźnie stwarzać problemy. Z kolei dla zapytań bezpośrednich te dane pozostają w bazowym źródle. <br/> <br/> Jednak należy zauważyć, że nawet z zapytaniem bezpośrednim niektóre pamięci podręczne danych na poziomie wizualizacji są zachowywane w usłudze Power BI (z powodu zaplanowanego odświeżania kafelków). |
| Bazowe źródło danych to źródło OLAP zawierające miary |Jeśli bazowe źródło danych zawiera *miary * (np. SAP HANA lub SAP Business Warehouse), importowanie danych powoduje inne problemy. Oznacza to, że zaimportowane dane są na określonym poziomie agregacji zgodnie z definicją w zapytaniu. Na przykład pomiar TotalSales według klasy, roku i miasta. Następnie, jeśli wizualizacja jest budowana, pytanie o dane na wyższym poziomie agregacji (na przykład TotalSales według roku) powoduje dalsze agregowanie zagregowanej wartości. Jest to poprawne dla miar dodawania (takich jak Sum, Min), ale jest problem z innymi niż dodawanie (takie jak Average, DistinctCount). <br/> <br/> Aby ułatwić uzyskiwanie poprawnych zagregowanych danych (zgodnych z potrzebami konkretnej wizualizacji) bezpośrednio ze źródła, byłoby konieczne wysyłanie zapytań dla poszczególnych wizualizacji, jak w zapytaniu bezpośrednim. <br/> <br/> Podczas łączenia się z systemem SAP Business Warehouse (BW) wybranie zapytania bezpośredniego umożliwia takie traktowanie miar. Obsługa systemu SAP BW jest dokładnie omówiona w temacie [Zapytanie bezpośrednie i system SAP BW](desktop-directquery-sap-bw.md). <br/> <br/> Jednak obecnie zapytanie bezpośrednie za pośrednictwem platformy SAP HANA traktuje to tak samo, jak relacyjne źródło, a tym samym zapewnia zachowanie podobne do importowania. Zostało to dokładniej omówione w [DirectQuery and SAP HANA](desktop-directquery-sap-hana.md) (Zapytanie bezpośrednie i platforma SAP HANA). |

Dlatego w podsumowaniu, mając na uwadze bieżące możliwości zapytania bezpośredniego w usłudze Power BI, scenariusze, które zapewniają korzyści, są następujące:

* Dane zmieniają się często i wymagane jest raportowanie prawie „w czasie rzeczywistym”
* Obsługa bardzo dużej ilości danych bez konieczności wstępnej agregacji
* Mają zastosowanie ograniczenia suwerenności danych
* Źródło jest źródłem wielowymiarowym zawierającym miary (jak system SAP BW)

Należy zauważyć, że szczegóły na poprzedniej liście odnoszą się jedynie do używania usługi Power BI. Zawsze istnieje możliwość, aby zamiast tego używać zewnętrznego modelu usług SQL Server Analysis Services (lub usług Azure Analysis Services) do importowania danych, a następnie za pomocą usługi Power BI nawiązać połączenie z tym modelem. Chociaż to podejście wymagałoby dodatkowych umiejętności, zapewnia ono większą elastyczność. Na przykład można importować dużo większe ilości danych i nie ma ograniczenia częstotliwości odświeżania danych.

## <a name="implications-of-using-directquery"></a>Implikacje wynikające z użycia zapytania bezpośredniego
Użycie **zapytania bezpośredniego** ma potencjalnie negatywne konsekwencje zgodnie z opisem w tej sekcji. Niektóre z tych ograniczeń nieco się różnią w zależności od dokładnego źródła, które jest używane. Zostanie to przywołane tam, gdzie ma zastosowanie, a oddzielne tematy obejmują te źródła, które różnią się znacznie.  

### <a name="performance-and-load-on-the-underlying-source"></a>Wydajności i obciążenia w bazowym źródle
Podczas korzystania z **zapytania bezpośredniego** cały proces w dużym stopniu zależy od wydajności bazowego źródła danych. Jeśli odświeżenie każdej wizualizacji (na przykład po zmianie wartości fragmentatora) zajmuje kilka sekund (<5 s), wówczas takie zachowanie jest uzasadnione, chociaż nadal może wydawać się wolne w porównaniu do natychmiastowej reakcji, do której się przyzwyczailiśmy podczas importowania danych do usługi Power BI. Jeśli zamiast tego powolność źródła oznacza, że odświeżanie poszczególnych wizualizacji trwa dłużej (dziesiątki sekund), wówczas doświadczenie staje się wyjątkowo niekorzystne, prawdopodobnie nawet do punktu, gdzie zapytanie przekroczy limit czasu.

Wraz z wydajnością bazowego źródła należy zwrócić szczególną uwagę na obciążenie, które to źródło będzie musiało obsłużyć (co, oczywiście, w efekcie często wpływa na wydajność). Zgodnie z dalszym opisem poniżej każdy użytkownik, który otwiera udostępniony raport, który jest okresowo odświeżany, będzie wysyłać co najmniej jedno zapytanie na wizualizację do bazowego źródła. Ten fakt wymaga, aby źródło mogło obsłużyć takie obciążenie zapytaniami, zachowując jednocześnie nadal rozsądną wydajność.

### <a name="limited-to-a-single-source"></a>Ograniczenie do pojedynczego źródła
Podczas importowania danych możliwe jest połączenie danych z wielu źródeł w jednym modelu, na przykład można łatwo dołączyć pewne dane z firmowej bazy danych programu SQL Server do pewnych danych lokalnych utrzymywanych w pliku programu Excel. Nie jest to możliwe w razie użycia zapytania bezpośredniego. Po wybraniu zapytania bezpośredniego dla źródła będzie możliwe użycie danych tylko z jednego źródła (na przykład pojedynczej bazy danych programu SQL Server).

### <a name="limited-data-transformations"></a>Ograniczone przekształcenia danych
Analogicznie istnieją ograniczenia dotyczące przekształceń danych, które mogą być stosowane w ramach **edytora zapytań**. Do importowanych danych może zostać łatwo zastosowany zaawansowany zbiór przekształceń w celu oczyszczenia i ponownego ukształtowania danych przed ich użyciem do tworzenia wizualizacji (np. podczas analizowania dokumentów JSON lub przestawiania danych z formularza o orientacji kolumnowej do wierszowej). Te przekształcenia są bardziej ograniczone dla zapytania bezpośredniego. Najpierw podczas łączenia ze źródłem OLAP, takim jak SAP Business Warehouse, nie można w ogóle zdefiniować przekształceń i cały zewnętrzny „model” jest pobierany ze źródła. W przypadku źródeł relacyjnych, takich jak program SQL Server, nadal można zdefiniować zestaw przekształceń na zapytanie, ale te przekształcenia są ograniczone ze względu na wydajność. Dowolne takie przekształcenia będą musiały być zastosowane do każdego zapytania do bazowego źródła, a nie raz podczas odświeżania danych, w związku z czym są one ograniczone do tych przekształceń, które w uzasadniony sposób można przetłumaczyć w pojedyncze zapytanie natywne. Jeśli używasz transformacji, która jest zbyt złożona, otrzymasz błąd mówiący, że musi ona zostać usunięta albo model musi zostać przełączony w tryb importu.

Ponadto zapytanie wynikające z okna dialogowego **Pobieranie danych** lub **Edytora zapytań** będzie używane w podwyborze w ramach zapytań generowanych i wysyłanych w celu pobrania danych niezbędnych dla wizualizacji. W związku z tym zapytanie zdefiniowane w edytorze zapytań musi być prawidłowe w tym kontekście. W szczególności oznacza to, że nie jest możliwe użycie zapytania korzystającego ze wspólnych wyrażeń tabel ani takiego, które wywołuje procedury składowane.

### <a name="modelling-limitations"></a>Ograniczenia modelowania
Termin *modelowanie* w tym kontekście oznacza czynność uściślenia i wzbogacenia nieprzetworzonych danych w ramach tworzenia raportu, który je wykorzystuje. Przykłady obejmują:

* Definiowanie relacji między tabelami
* Dodawanie nowych obliczeń (kolumn i miar obliczeniowych)
* Zmianę nazwy i ukrywanie kolumn i miar
* Definiowanie hierarchii
* Definiowanie formatowania, domyślnego podsumowania i kolejności sortowania dla kolumny
* Grupowanie lub klastrowanie wartości

Podczas używania **zapytania bezpośredniego** nadal można wprowadzać wiele z tych wzbogaceń modelu i na pewno nadal istnieje zasada, że są wzbogacane nieprzetworzone dane, aby ulepszyć ich późniejsze wykorzystanie. Jednak podczas korzystania z zapytania bezpośredniego niektóre możliwości modelowania są niedostępne lub ograniczone. Ograniczenia są zazwyczaj stosowane, aby uniknąć problemów z wydajnością. Zestaw ograniczeń, które są wspólne dla wszystkich źródeł zapytania bezpośredniego, jest wyświetlany na poniższej liście punktowanej. Dodatkowe ograniczenia, które mogą być stosowane do poszczególnych źródeł, zgodnie z opisem w *określonych szczegółowych informacjach dotyczących źródła danych* znajdują się pod koniec tego artykułu.

* **Brak wbudowanej hierarchii dat:** podczas importowania danych, domyślnie każda kolumna data/data i godzina ma też wbudowaną hierarchię dat, która jest domyślnie dostępna. Na przykład jeśli zaimportowano tabelę zamówień sprzedaży wraz z kolumną OrderDate, to następnie podczas używania kolumny OrderDate w wizualizacji będzie możliwe wybranie odpowiedniego używanego poziomu (rok, miesiąc, dzień). Ta wbudowana hierarchia dat nie jest dostępna podczas używania trybu zapytania bezpośredniego. Należy jednak pamiętać, że jeśli tabela Data jest dostępna w bazowym źródle (co jest często spotykane w wielu magazynach danych), wówczas funkcje analizy czasowej języka DAX mogą być normalnie używane.
* **Ograniczenia w kolumnach obliczeniowych:** kolumny obliczeniowe są ograniczone do wierszy wewnątrz, jak w programie, i mogą odwoływać się tylko do wartości innych kolumn tej samej tabeli bez korzystania z jakichkolwiek funkcji agregujących. Ponadto dopuszczalne funkcje skalarne języka DAX (takie jak LEFT()) zostaną ograniczone do tych, które można po prostu przenieść do bazowego źródła, więc będą się różnić w zależności od dokładnych możliwości źródła. Funkcje, które nie są obsługiwane, nie będą wyświetlane w funkcji autouzupełniania podczas używania języka DAX dla kolumny obliczeniowej i spowodują błąd, jeśli zostaną użyte.
* **Brak obsługi funkcji języka DAX nadrzędny-podrzędny:** w przypadku modelu zapytania bezpośredniego nie jest możliwe używanie rodziny funkcji PATH() języka DAX, które zazwyczaj obsługują struktury nadrzędny-podrzędny (na przykład wykres kont lub hierarchii pracowników).
* **Ograniczenia (domyślne) dla miar:** domyślnie są ograniczone funkcje i wyrażenia języka DAX, które mogą być używane w miarach. Ponownie autouzupełnianie ograniczy wymienione funkcje i wystąpi błąd, jeśli jest używana nieprawidłowa funkcja lub wyrażenie. Przyczyną jest po prostu zapewnienie, że domyślnie miary są ograniczone do prostych miar, które prawdopodobnie samodzielnie nie spowodują problemów z wydajnością. Użytkownicy zaawansowani mogą zdecydować się na obejście tego ograniczenia, wybierając pozycje **Plik > Opcje**, a następnie **Ustawienia > Opcje > Zapytanie bezpośrednie** i zaznaczając opcję *Zezwalaj na nieograniczone miary w trybie zapytania bezpośredniego*. Gdy ta opcja jest zaznaczona, można użyć dowolnego wyrażenia języka DAX prawidłowego dla miary. Użytkownicy muszą być jednak świadomi, że niektóre wyrażenia, które dobrze działają po zaimportowaniu danych, mogą znacznie spowalniać zapytania do źródła danych zaplecza w trybie zapytania bezpośredniego.
  
  * Na przykład domyślnie:
    
    * Będzie można tworzyć miary, które po prostu sumują kwoty sprzedaży:
      
          SalesAmount = SUMX(Web_Sales, [ws_sales_price]* [ws_quantity])
    * W ten sposób *nie* będzie możliwe tworzenie miary, która następnie uśrednia te kwoty sprzedaży dla wszystkich elementów:
      
          AverageItemSalesAmount = AVERAGEX('Item', [SalesAmount])
    
    Przyczyną jest to, że taka miara może powodować niską wydajność, jeśli było bardzo wiele elementów.
* **Tabele obliczeniowe nie są obsługiwane:** możliwość definiowania tabeli obliczeniowej przy użyciu wyrażenia języka DAX nie jest obsługiwana w trybie zapytania bezpośredniego.
* **Filtrowanie relacji jest ograniczone do jednego kierunku:** w przypadku używania zapytania bezpośredniego nie jest możliwe ustawienie kierunku filtru krzyżowego w relacji na „Both”. Na przykład, mając trzy poniższe tabele, nie można będzie utworzyć wizualizacji pokazującej każdą wartość Customer[Gender] i liczbę elementów Product[Category] zakupionych dla każdej z tych wartości. Korzystanie z takiego dwukierunkowego filtrowania jest opisane [w tym szczegółowym oficjalnym dokumencie](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional cross-filtering in Analysis Services 2016 and Power BI.docx) (w tym dokumencie przedstawiono przykłady w kontekście usług SQL Server Analysis Services, ale podstawowe punkty mają w równym stopniu zastosowanie do usługi Power BI).
  
  ![](media/desktop-directquery-about/directquery-about_01.png)
  
  Ponownie ograniczenia są nakładane ze względu na ich wpływ na wydajność. Jednym szczególnie ważnym zastosowaniem tego jest to, że podczas definiowania zabezpieczenia na poziomie wiersza jako części raportu, wspólnym wzorcem jest posiadanie relacji wiele do wielu między użytkownikami a jednostkami, do których mogą uzyskać dostęp, a korzystanie z filtrowania dwukierunkowego jest niezbędne do wyegzekwowania tego. Jednak filtrowanie dwukierunkowe w modelach zapytania bezpośredniego powinno być używane rozsądnie ze zwróceniem szczególnej uwagi na jakikolwiek niekorzystny wpływ na wydajność.  
* **Brak klastrowania:** podczas używania zapytania bezpośredniego nie jest możliwe używanie możliwości klastrowania, aby automatycznie znaleźć grupy

### <a name="reporting-limitations"></a>Ograniczenia dotyczące raportowania
Prawie wszystkie funkcje raportowania są obsługiwane w modelach zapytania bezpośredniego. W efekcie tak długo, jak długo bazowe źródło zapewnia odpowiedni poziom wydajności, można używać tego samego zestawu wizualizacji. Jednak istnieją pewne ważne ograniczenia dotyczące niektórych innych możliwości oferowanych w **usłudze Power BI** po opublikowaniu raportu zgodnie z opisem w następujących punktach:

* **Funkcja szybkiego wglądu w szczegółowe dane nie jest obsługiwana:** funkcja szybkiego wglądu w szczegółowe dane usługi Power BI wyszukuje różne podzbiory zestawu danych, stosując zestaw zaawansowanych algorytmów w celu odnajdywania potencjalnie interesujących szczegółowych informacji. Biorąc pod uwagę potrzebę bardzo wysokiej wydajności zapytań, ta funkcja nie jest dostępna w zestawach danych używających zapytania bezpośredniego.
* **Funkcja pytań i odpowiedzi nie jest obsługiwana:** funkcja pytań i odpowiedzi usługi Power BI pozwala eksplorować dane, korzystając z intuicyjnych możliwości języka naturalnego, oraz uzyskiwać odpowiedzi w formie wykresów i schematów. Jednak nie jest to obecnie obsługiwane dla zestawów danych używających zapytania bezpośredniego.
* **Używanie funkcji Eksploruj w programie Excel prawdopodobnie spowoduje mniejszą wydajność:** istnieje możliwość eksplorowania danych przy użyciu funkcji „Eksploruj w programie Excel” w zestawie danych. Pozwoli to na tworzenie w programie Excel tabel i wykresów przestawnych. Chociaż ta funkcja jest obsługiwana w zestawach danych przy użyciu zapytania bezpośredniego, wydajność jest zazwyczaj mniejsza niż tworzenie wizualizacji w usłudze Power BI, a w związku z tym, jeśli korzystanie z programu Excel jest ważne dla scenariuszy, należy uwzględnić to w decyzjach o używaniu zapytania bezpośredniego.

### <a name="security"></a>Zabezpieczenia
Zgodnie z opisem we wcześniejszej części tego artykułu, raport używający **zapytania bezpośredniego** będzie zawsze używać tych samych stałych poświadczeń do nawiązania połączenia z bazowym źródłem danych po opublikowaniu w **usłudze Power BI**. Ponownie należy pamiętać, że odnosi się to do zapytania bezpośredniego, a nie połączeń na żywo z usługami SQL Server Analysis Services i tym to się różni. Dlatego natychmiast po opublikowaniu raportu zapytania bezpośredniego konieczne jest skonfigurowanie poświadczeń użytkownika, które będą używane. Dopóki nie zostanie to zrobione otwarcie raportu w usłudze Power BI spowoduje błąd.

Gdy zostaną podane poświadczenia użytkownika, wówczas te poświadczenia będą używane *niezależnie od użytkownika, który otworzy raport*. W tym zakresie jest to dokładnie takie samo, jak dla importowanych danych, w tym sensie, że każdy użytkownik będzie widział te same dane, chyba że zabezpieczenia na poziomie wiersza zostały zdefiniowane jako część raportu. Dlatego taką samą uwagę należy zwrócić na udostępnianie raportu, jeśli istnieją jakiekolwiek reguły zabezpieczeń zdefiniowane w bazowym źródle.

### <a name="behavior-in-the-power-bi-service"></a>Zachowanie w usłudze Power BI
W tej sekcji opisano zachowanie raportu **zapytania bezpośredniego** w **usłudze Power BI** przede wszystkim, aby móc zrozumieć stopień obciążenia, które zostanie przyłożone do źródła danych zaplecza, zakładając liczbę użytkowników, którym raport i pulpit nawigacyjny zostaną udostępnione, złożoność raportu i to, czy zabezpieczenia na poziomie wiersza zostały zdefiniowane w raporcie.

#### <a name="reports--opening-interacting-with-editing"></a>Raporty — otwierania, interakcje, edytowanie
Gdy raport jest otwierany, zostaną odświeżone wizualizacje na aktualnie widocznej stronie. Każda wizualizacja wymaga co najmniej jednego zapytania do bazowego źródła danych. Niektóre wizualizacje mogą wymagać więcej niż jednego zapytania (na przykład jeśli zostały pokazane wartości zagregowane z dwóch różnych tabel faktów lub zawierające bardziej złożoną miarę, lub zawierające podsumowania miar innych niż addytywne, takich jak Count Distinct). Przeniesienie na nową stronę spowoduje odświeżenie tych wizualizacji, co utworzy nowy zestaw zapytań do bazowego źródła.

Każdy interakcja użytkownika w raporcie może spowodować odświeżenie wizualizacji. Na przykład wybranie innej wartości fragmentatora będzie wymagać wysłania nowego zestawu zapytań, aby odświeżyć wszystkie objęte wizualizacje. To samo jest prawdziwe dla kliknięcia wizualizacji w celu krzyżowego wyróżnienia innych wizualizacji lub dla zmiany filtru.  

Podobnie edytowanie nowego raportu będzie, oczywiście, wymagać wysłania zapytań dla każdego kroku na ścieżce do utworzenia końcowej żądanej wizualizacji.

Istnieje pewne buforowanie wyników, aby odświeżanie wizualizacji było natychmiastowe, jeśli ostatnio zostały uzyskane dokładnie takie same wyniki. Takie pamięci podręczne nie są współdzielone przez użytkowników, jeśli zabezpieczenia na poziomie wiersza są zdefiniowane jako część raportu.

#### <a name="dashboard-refresh"></a>Odświeżanie pulpitu nawigacyjnego
Poszczególne wizualizacje lub całe strony można przypiąć do pulpitu nawigacyjnego jako kafelki. Kafelki oparte na zestawach danych **zapytania bezpośredniego** są następnie automatycznie odświeżane zgodnie z harmonogramem, co powoduje wysyłanie zapytań do źródła danych zaplecza. Domyślnie następuje to co godzinę, ale można to skonfigurować jako część ustawień zestawu danych w zakresie od co tydzień i do co 15 minut.

Jeśli żadne zabezpieczenia na poziomie wiersza nie są zdefiniowane w modelu, oznacza to, że każdy kafelek będzie odświeżany raz, a wyniki zostaną udostępnione wszystkim użytkownikom. Jeśli zdefiniowano zabezpieczenia na poziomie wiersza, wówczas może wystąpić efekt dużego mnożnika — każdy kafelek wymaga oddzielnych zapytań dla poszczególnych użytkowników, które mają być wysyłane do bazowego źródła.  

Dlatego pulpit nawigacyjny mający dziesięć kafelków, udostępniony 100 użytkownikom, utworzony na zestawie danych za pomocą **zapytania bezpośredniego** z zabezpieczeniami na poziomie wiersza i mający odświeżanie skonfigurowane co 15 minut, spowoduje co najmniej 1000 zapytań wysyłanych co 15 minut do źródła zaplecza.

Dlatego należy zwrócić szczególną uwagę na stosowanie zabezpieczeń na poziomie wiersza i konfigurowanie harmonogramu odświeżania.

#### <a name="timeouts"></a>Limity czasu
Limit czasu równy cztery minuty jest stosowany do poszczególnych kwerend w **usłudze Power BI**, zaś zapytania trwające dłużej po prostu zakończą się niepowodzeniem. Jak już wcześniej podkreślono, zaleca się stosowanie zapytania bezpośredniego dla źródeł, które zapewniają prawie interaktywną wydajność zapytań, więc to ograniczenie jest przeznaczone do zapobiegania problemom zbyt długich czasów wykonania.

### <a name="other-implications"></a>Inne implikacje
Niektóre inne ogólne implikacje dotyczące używania **zapytania bezpośredniego** są następujące:

* **Jeśli dane ulegają zmianie, należy je odświeżyć, aby zapewnić wyświetlanie najnowszych danych:** zakładając korzystanie z pomięci podręcznych, nie ma żadnej gwarancji, że wizualizacja zawsze wyświetla najnowsze dane. Na przykład wizualizacja może wyświetlać transakcje z ostatniego dnia. Następnie, z powodu zmiany fragmentatora, może on się odświeżyć, aby wyświetlać transakcje z ostatnich dwóch dni łącznie z pewnymi najnowszymi nowo dodanymi transakcjami. Przywrócenie początkowej wartości fragmentatora spowodowałoby ponowne wyświetlenie wcześniej uzyskanej buforowanej wartości, która nie zawiera nowo dodanych transakcji, które były widoczne wcześniej.
  
  Wybranie odświeżania wyczyści wszelkie pomięci podręczne i odświeży wszystkie wizualizacje na stronie, aby wyświetlić najnowsze dane.
* **Jeśli dane ulegają zmianie, nie ma żadnej gwarancji spójności między wizualizacjami:** różne wizualizacje, czy to na tej samej stronie, czy też na różnych stronach, mogą być odświeżane w różnym czasie. W związku z tym, jeśli dane w bazowym źródle ulegną zmianie, nie ma gwarancji, że każda wizualizacja będzie pokazywać dane dla dokładnie tej samej chwili czasu. Rzeczywiście, zakładając, że czasami dla pojedynczej wizualizacji wymagane jest więcej niż jedno zapytanie (na przykład aby uzyskać szczegółowe informacje i sumy), wówczas spójność nawet w ramach pojedynczej wizualizacji nie jest gwarantowana. Aby to zagwarantować, będzie wymagany narzut na odświeżenie wszystkich wizualizacji po każdym odświeżeniu dowolnej wizualizacji przy użyciu takich kosztownych funkcji, jak izolacja migawki w bazowym źródle danych.
  
  Ten problem można zminimalizować w dużym stopniu wybierając ponownie odświeżanie, aby odświeżyć wszystkie wizualizacje na stronie. Należy też zauważyć, że nawet w przypadku używania trybu importu istnieje podobny problem zagwarantowania spójności w przypadku importowania danych z więcej niż jednej tabeli.
* **Odświeżanie w programie Power BI Desktop jest potrzebne, aby odzwierciedlić zmiany metadanych:** po opublikowaniu raportu odświeżanie po prostu odświeży wizualizacje w raporcie. Jeśli schemat bazowego źródła uległ zmianie, wówczas te zmiany nie są automatycznie stosowane do zmiany dostępnych pól na liście pól. W związku z tym, jeśli tabele lub kolumny zostały usunięte z bazowego źródła, może to spowodować niepowodzenie zapytania podczas odświeżania. Otwarcie raportu w programie Power BI Desktop i wybieranie pozycji Odśwież zaktualizuje pola w modelu, aby odzwierciedlić zmiany.
* **Ograniczenie do miliona wierszy zwracanych na dowolne zapytanie:** istnieje stały limit miliona wierszy dotyczący liczby wierszy, które mogą zostać zwrócone w dowolnym pojedynczym zapytaniu do bazowego źródła. Nie ma to zazwyczaj praktycznych skutków, a same wizualizacje nie będą wyświetlać tak wielu punktów. Jednak ograniczenie może wystąpić w przypadkach, gdy usługa Power BI nie w pełni optymalizuje wysyłane zapytania i są żądane pewne wyniki pośrednie, które przekraczają ograniczenie. Może to również wystąpić podczas tworzenia wizualizacji na ścieżce do bardziej uzasadnionego stanu końcowego. Na przykład uwzględnienie tabel Customer i TotalSalesQuantity osiągnie to ograniczenie, jeśli było tam ponad 1 mln klientów, dopóki nie zostanie zastosowany pewien filtr.
  
  Zwracanym błędem będzie „Zestaw wyników zapytania skierowanego do zewnętrznego źródła danych przekracza dozwoloną maksymalną liczbę wierszy wynoszącą 1 000 000 wierszy.”.
* **Nie można zmienić trybu z importu na zapytanie bezpośrednie:** należy zapamiętać, że chociaż ogólnie jest możliwe przełączenie modelu z trybu zapytania bezpośredniego na używanie trybu importu, oznacza to, że należy zaimportować wszystkie niezbędne dane. Ponadto nie jest możliwe przełączenie powrotne (przede wszystkim z powodu zestawu funkcji nieobsługiwanych w trybie zapytania bezpośredniego). Modele zapytania bezpośredniego za pośrednictwem wielowymiarowych źródeł, takich jak SAP BW, również nie mogą być przełączane z zapytania bezpośredniego na import z powodu zupełnie różnego traktowania miar zewnętrznych.

## <a name="directquery-in-the-power-bi-service"></a>Zapytanie bezpośrednie w usłudze Power BI
Wszystkie źródła są obsługiwane z programu **Power BI Desktop**. Niektóre źródła są również dostępne bezpośrednio w **usłudze Power BI**. Na przykład dla użytkownika biznesowego istnieje możliwość użycia usługi Power BI, aby nawiązać połączenie ze swoimi danymi w tabeli Salesforce, i uzyskania od razu pulpitu nawigacyjnego bez korzystania z programu **Power BI Desktop**.

Bezpośrednio w usłudze są dostępne tylko dwa spośród źródeł obsługujących zapytanie bezpośrednie:

* Spark
* Azure SQL Data Warehouse

Jednak zdecydowanie zaleca się, aby jakiekolwiek użycie **zapytania bezpośredniego** dla tych dwóch źródeł było uruchamiane z poziomu programu **Power BI Desktop**. Przyczyną jest to, że w na początkowym etapie nawiązywania połączenia w **usłudze Power BI** zostanie zastosowanych wiele kluczowych ograniczeń. Oznacza to, że chociaż punkt początkowy był łatwy (rozpoczyna się w usłudze Power BI), istnieją ograniczenia dotyczące dalszego ulepszania wynikowego raportu (na przykład nie jest możliwe późniejsze utworzenie jakichkolwiek obliczeń lub skorzystanie z wielu funkcji analitycznych, lub nawet odświeżenie metadanych, aby odzwierciedlały zmiany w bazowym schemacie).   

## <a name="guidance-for-using-directquery-successfully"></a>Wskazówki dotyczące pomyślnego używania zapytania bezpośredniego
Jeśli zamierzasz używać **zapytania bezpośredniego**, wówczas ta sekcja zawiera pewne wskazówki wysokiego poziomu mówiące, jak zapewnić powodzenie. Wskazówki zawarte w tej sekcji są pochodną implikacji używania zapytania bezpośredniego, które zostały opisane w tym artykule.

### <a name="backend-data-source-performance"></a>Wydajność źródła danych zaplecza
Zdecydowanie zaleca się weryfikację, czy proste wizualizacje będą mogły się odświeżyć w odpowiednim czasie. Powinno to się odbyć w ciągu 5 sekund, aby mieć rozsądne doświadczenie interaktywne. Oczywiście, jeśli dla wizualizacji trwa to dłużej niż 30 sekund, istnieje duże prawdopodobieństwo, że inne problemy wystąpią po opublikowaniu raportu, co spowoduje, że rozwiązanie nie będzie działać.

Jeśli zapytania są przetwarzane wolno, pierwszym punktem dochodzenia jest zbadanie zapytań wysyłanych do bazowego źródła i przyczyny obserwowania wydajności zapytania. Ten temat nie obejmuje szerokiej gamy najlepszych rozwiązań optymalizacji bazy danych dla pełnego zestawu bazowych źródeł, ale odnosi się do standardowych rozwiązań baz danych, które dotyczą większości sytuacji:

* Relacje na podstawie kolumn liczb całkowitych zazwyczaj mają lepszą wydajność niż sprzężenia w kolumnach innych typów danych
* Należy utworzyć odpowiednie indeksy, co zwykle oznacza użycie w tych źródłach indeksów magazynu kolumn, które je obsługują (na przykład SQL Server).
* Wszelkie niezbędne statystyki w źródle powinny zostać zaktualizowane

### <a name="model-design-guidance"></a>Wskazówki dotyczące projektowania modelu
Podczas definiowania modelu należy wziąć pod uwagę poniższe:

* **Unikaj złożonych zapytań w edytorze zapytań.** Zapytanie, które jest definiowane w edytorze zapytań, zostanie zamienione na pojedyncze zapytanie języka SQL, które następnie zostanie uwzględnione w podwyborze każdego zapytania wysyłanego do tej tabeli. Jeśli to zapytanie jest złożone, może to spowodować problemy z wydajnością dla każdego wysyłanego zapytania. Rzeczywiste zapytanie języka SQL dla zestawu kroków można uzyskać, wybierając ostatni krok w edytorze zapytań i wybierając pozycję *Wyświetl zapytanie natywne* z menu kontekstowego.
* **Zachowaj proste miary.** Co najmniej początkowo zalecane jest ograniczenie miar do prostych wartości zagregowanych. Następnie, jeśli zachowują się one w zadowalający sposób, można zdefiniować bardziej złożone miary, ale zwracając uwagę na wydajność każdej z nich.
* **Unikaj relacji w kolumnach obliczeniowych.** Ma to zastosowanie szczególnie do baz danych, gdy konieczne jest wykonanie sprzężeń wielokolumnowych. Usługa Power BI obecnie nie zezwala na oparcie relacji na wielu kolumnach jako kluczu obcym/podstawowym. Typowym obejściem jest łączenie kolumn ze sobą przy użyciu kolumny obliczeniowej i oparcie na tym sprzężenia. Chociaż to obejście jest uzasadnione dla importowanych danych, w przypadku **zapytania bezpośredniego** jego wynikiem jest sprzężenie na wyrażeniu, które często uniemożliwia korzystanie z jakichkolwiek indeksów i prowadzi do niskiej wydajności. Jedynym obejściem jest rzeczywista materializacja wielu kolumn do jednej kolumny w źródłowej bazie danych.
* **Unikaj relacji w kolumnach typu uniqueidentifier.** Usługa Power BI nie obsługuje natywnie typu danych uniqueidentifier. Dlatego definiowanie relacji między kolumnami typu uniqueidentifier spowoduje zapytania ze sprzężeniem obejmującym rzutowanie. Ponownie często prowadzi to do niskiej wydajności. Dopóki ta sprawa nie zostanie specjalnie zoptymalizowana, jedynym obejściem jest zmaterializowanie kolumn alternatywnego typu w źródłowej bazie danych.
* **Ukrywaj kolumnę *do* w relacjach.** Kolumna *do* w relacjach (często klucz podstawowy w tabeli *do*) powinna być ukryta, dzięki czemu nie pojawi się na liście pól i nie można jej będzie użyć w wizualizacjach. Często kolumny, na których oparto relacje, są faktycznie *kolumnami systemowymi* (na przykład klucze zastępcze w magazynie danych) i ukrywanie takich kolumn jest zawsze dobrym rozwiązaniem. Jeśli kolumna ma znaczenie, należy wprowadzić kolumnę obliczeniową, która jest widoczna i ma proste wyrażenie równości z kluczem podstawowym. Na przykład:
  
      ProductKey_PK   (Destination of a relationship, hidden)
      ProductKey (= [ProductKey_PK],   visible)
      ProductName
      ...
  
  Przyczyną takiego postępowania jest po prostu chęć uniknięcia problemu z wydajnością, który może w przeciwnym razie wystąpić, jeśli wizualizacja zawiera kolumnę klucza podstawowego.
* **Sprawdź wszystkie zastosowania kolumn obliczeniowych i zmian typu danych.** Korzystanie z tych funkcji nie musi być szkodliwe, ale powodują one, że zapytania wysłane do bazowego źródła zawierają wyrażenia zamiast prostych odwołań do kolumn, co ponownie może spowodować, że indeksy nie są używane.  
* **Unikaj stosowania (wersji zapoznawczej) dwukierunkowego filtrowania krzyżowego w relacjach.**
* **Eksperymentuj z ustawieniem *Przyjmij integralność referencyjną*.** Ustawienie *Przyjmij integralność referencyjną* w relacjach umożliwia używanie w zapytaniach instrukcji INNER JOIN zamiast OUTER JOIN. Zwykle zwiększa to wydajność zapytań, chociaż zależy od szczegółowych informacji na temat źródła danych.
* **Nie używaj względnego filtrowania danych w edytorze zapytań.** Istnieje możliwość zdefiniowania względnego filtrowania danych w edytorze zapytań. Na przykład, aby odfiltrować do wierszy, gdzie data mieści się w ciągu ostatnich 14 dni.
  
  ![](media/desktop-directquery-about/directquery-about_02.png)
  
  Jednak zostanie to przetłumaczone jako filtr oparty na stałej dacie, jak w chwili utworzenia zapytania. Można to zaobserwować, wyświetlając natywne zapytanie.
  
  ![](media/desktop-directquery-about/directquery-about_03.png)
  
  To prawie na pewno nie jest to, czego chcieliśmy. Aby upewnić się, że filtr jest stosowany na podstawie daty z chwili wykonania raportu, należy zamiast tego zastosować filtr w raporcie jako filtr raportu. Obecnie byłoby to wykonywane przez utworzenie kolumny obliczeniowej obliczającej liczbę dni, które upłynęły (przy użyciu funkcji DATE() języka DAX), a następnie użycie tej kolumny obliczeniowej w filtrze.

### <a name="report-design-guidance"></a>Wskazówki dotyczące projektowania raportu
Podczas tworzenia raportu za pomocą połączenia zapytania bezpośredniego należy stosować się do poniższych wskazówek:

* **Rozważ użycie opcji redukcji zapytania:** usługa Power BI zapewnia w raporcie opcje wysyłania mniejszej liczby zapytań oraz wyłączenia niektórych interakcji, które mogłyby spowodować pogorszenie środowiska pracy w przypadku, gdy wykonanie wynikowych zapytań zajmuje dużo czasu. Aby uzyskać dostęp do tych opcji w programie **Power BI Desktop**, wybierz kolejno pozycje **Plik > Opcje i Ustawienia > Opcje** oraz **Redukcja zapytania**. 

   ![](media/desktop-directquery-about/directquery-about_03b.png)

    Zaznaczenie pól wyboru w obszarze **Redukcja zapytania** umożliwia wyłączenie krzyżowego wyróżniania w całym raporcie. Można również wyświetlić przycisk *Zastosuj* dla wybranych opcji fragmentatorów i/lub filtrów, co umożliwia wybranie wielu opcji fragmentatorów i filtrów przed ich zastosowaniem. Zapytania zostaną wysłane dopiero po wybraniu przycisku **Zastosuj** na fragmentatorze. Wybrane opcje zostaną następnie użyte do filtrowania danych.

    Te opcje będą stosowane w raporcie podczas pracy w programie **Power BI Desktop**, a także podczas korzystania z niego w **usłudze Power BI**.

* **Najpierw zastosuj filtry:** zawsze stosuj wszelkie stosowne filtry na początku tworzenia wizualizacji. Na przykład zamiast przeciągania kolumn TotalSalesAmount i ProductName, a następnie filtrowania według konkretnego roku, zastosuj filtr według roku na samym początku. Jest tak, ponieważ każdy krok w procesie tworzenia wizualizacji będzie wysyłać zapytanie i chociaż jest możliwe późniejsze wprowadzenie innej zmiany przed ukończeniem pierwszego zapytania, nadal pozostawia to niepotrzebne obciążenie w bazowym źródle. Wczesne zastosowanie filtrów najczęściej powoduje, że te pośrednie zapytania są mniej kosztowne. Ponadto niezastosowanie filtrów odpowiednio wcześniej może spowodować przekroczenie powyższego ograniczenia liczby wierszy do 1 miliona.
* **Ogranicz liczbę wizualizacji na stronie:** gdy strona jest otwierana (lub nastąpiła zamiana pewnego fragmentatora na poziomie strony lub filtra), wówczas są odświeżane wszystkie wizualizacje na stronie. Istnieje też ograniczenie liczby zapytań, które są wysyłane równolegle, dlatego w miarę zwiększania liczby wizualizacji niektóre z nich zostaną odświeżone szeregowo, wydłużając czas niezbędny do odświeżenia całej strony. Z tego powodu zaleca się ograniczenie liczby wizualizacji na jednej stronie i zamiast tego użycie większej liczby prostszych stron.
* **Rozważ wyłączenie interakcji między wizualizacjami:** domyślnie wizualizacje na stronie raportu mogą służyć do krzyżowego filtrowania i wyróżniania innych wizualizacji na stronie. Na przykład po wybraniu „1999” na wykresie kołowym, wykres kolumnowy zostanie krzyżowo wyróżniony, aby pokazać sprzedaż według kategorii dla „1999”.                                                                  
  
  ![](media/desktop-directquery-about/directquery-about_04.png)
  
  W zapytaniu bezpośrednim takie filtrowanie i wyróżnianie krzyżowe wymaga wysłania zapytania do bazowego źródła. Z tego względu interakcję należy wyłączyć, jeżeli czas reakcji na wybory użytkowników byłby zbyt długi. Interakcję można wyłączyć dla całego raportu (jak opisano powyżej w części *Opcje redukcji zapytania*) lub w indywidualnym przypadku, zgodnie z opisem [w tym artykule](service-reports-visual-interactions.md).

Oprócz powyższej listy sugestii należy pamiętać, że każda z poniższych możliwości raportowania może spowodować problemy z wydajnością:

* **Filtry miary:** wizualizacje zawierające miary (lub agregaty kolumn) mogą zawierać filtry w tych miarach. Na przykład poniższa wizualizacja przedstawia kolumnę SalesAmount posortowaną według kategorii, ale tylko tych kategorii, gdzie sprzedaż przekracza 20 mln.
  
  ![](media/desktop-directquery-about/directquery-about_05.png)
  
  Spowoduje to wysłanie dwóch zapytań do bazowego źródła:
  
  * Pierwsze zapytanie pobierze kategorie spełniające warunek (Sprzedaż > 20 mln)
  * Drugie zapytanie pobiera następnie dane niezbędne dla wizualizacji, w tym kategorie, które spełniają warunek w klauzuli WHERE.  
  
  Zazwyczaj działa to świetnie w przypadku setek lub tysięcy kategorii, jak w poniższym przykładzie. Wydajność może się zmniejszyć, jeśli liczba kategorii jest znacznie większa (i rzeczywiście zapytanie zakończy się niepowodzeniem, gdyby istniał ponad milion kategorii spełniających warunek, z powodu ograniczenia liczby wierszy do miliona, które zostało omówione powyżej).
* **Górne N filtrów:** można zdefiniować zaawansowane filtry do filtrowania tylko N górnych (lub dolnych) wartości uporządkowanych według pewnej miary, na przykład zawierających tylko 10 górnych kategorii w wizualizacji powyżej. Ponownie spowoduje to wysłanie dwóch zapytań do bazowego źródła. Jednak pierwsze zapytanie zwróci wszystkie kategorie z bazowego źródła, a następnie górne N (TopN) jest określanych na podstawie zwróconych wyników. W zależności od kardynalności objętej kolumny może to prowadzić do problemów z wydajnością (lub niepowodzenia zapytania z powodu ograniczenia liczby wierszy do 1 mln).
* **Mediana:** ogólnie rzecz biorąc, wszelkie agregacje (Sum, Count Distinct itd.) są wypychane do bazowego źródła. Jednak nie jest to spełnione dla mediany, ponieważ ta wartość zagregowana nie jest zwykle obsługiwana przez bazowe źródło. W takich przypadkach szczegółowe dane są pobierane z bazowego źródła i mediana jest obliczana na podstawie zwracanych wyników. Jest to uzasadnione, gdy mediana ma być obliczana dla stosunkowo małej liczby wyników, ale problemy z wydajnością (lub niepowodzenia zapytań z powodu ograniczenie liczby wierszy do 1 mln) wystąpią, jeśli kardynalność jest duża.  Na przykład mediana populacji kraju może mieć uzasadnienie, ale mediana ceny sprzedaży już raczej nie.
* **Zaawansowane filtry tekstowe („zawiera” i podobne):** podczas filtrowania według kolumny tekstowej zaawansowane filtrowanie dopuszcza takie filtry, jak „zawiera” i „zaczyna się od” itd. Te filtry na pewno mogą spowodować pogorszenie wydajności dla niektórych źródeł danych. W szczególności domyślny filtr „zawiera” nie powinien być używany, jeśli tym, co naprawdę potrzebne, jest dokładna zgodność („równy” lub „nierówny”). Mimo że wyniki mogą być takie same, w zależności od rzeczywistych danych, wydajność może się znacząco różnić z powodu używania indeksów.
* **Fragmentatory wielokrotnego wyboru:** domyślnie fragmentatory zezwalają tylko na pojedynczy wybór. Dopuszczenie filtrów wielokrotnego wyboru może spowodować pewne problemy z wydajnością, ponieważ gdy użytkownik wybierze zestaw elementów we fragmentatorze (na przykład dziesięć produktów, którymi jest zainteresowany), wówczas każdy nowy wybór spowoduje wysłanie zapytań do źródła zaplecza. O ile użytkownik może wybrać następny element przed zakończeniem zapytania, powoduje to dodatkowe obciążenie bazowego źródła.

* **Należy rozważyć wyłączenie sum na wizualizacjach:** domyślnie w tabelach i matrycach są wyświetlane sumy i sumy częściowe. W wielu przypadkach aby uzyskać wartości dla takich sum, należy wysłać oddzielne zapytania do bazowego źródła. Dotyczy to każdego użycia agregacji *DistinctCount* oraz wszystkich przypadków wykonywania zapytania bezpośredniego za pośrednictwem oprogramowania SAP BW lub SAP HANA. Takie sumy należy wyłączyć (przy użyciu okienka **Format**), jeśli nie są wymagane. 

### <a name="diagnosing-performance-issues"></a>Diagnozowanie problemów z wydajnością
W tej sekcji opisano sposób diagnozowania problemów z wydajnością lub sposób uzyskania bardziej szczegółowych informacji umożliwiających optymalizację raportów.

Zdecydowanie zaleca się, aby cała diagnostyka problemów z wydajnością zaczynała się w programie **Power BI Desktop**, a nie w **usłudze Power BI**. Najczęściej problemy z wydajnością są po prostu powodowane przez poziom wydajności bazowego źródła i jest je łatwiej zidentyfikować oraz zdiagnozować w znacznie bardziej izolowanym środowisku programu **Power BI Desktop** i początkowo eliminować niektóre składniki (na przykład bramę usługi Power BI). Tylko wtedy, gdy zostanie stwierdzone, że problemy z wydajnością nie są obecne w programie Power BI Desktop, dochodzenie powinno się skoncentrować na szczegółach raportu w usłudze Power BI.

Podobnie zaleca się, aby najpierw spróbować wyizolować wszelkie problemy poszczególnych wizualizacji, a nie wielu wizualizacji na stronie.

Powiedzmy więc, że te kroki (w poprzednich akapitach w tej sekcji) zostały wykonane — mamy teraz pojedynczą wizualizację na stronie w programie **Power BI Desktop**, który nadal jest powolny. Aby ustalić zapytania, które są wysyłane do bazowego źródła przez program Power BI Desktop, można wyświetlić informacje o śladzie/diagnostyce, które mogą być emitowane przez to źródło. Takie ślady mogą również zawierać przydatne informacje na temat szczegółów sposobu wykonania zapytania i możliwości jego ulepszenia.

Co więcej, nawet w przypadku braku takich śladów ze źródła, istnieje możliwość wyświetlania zapytań wysłanych przez usługę Power BI wraz z ich czasami wykonywania zgodnie z dalszym opisem.

#### <a name="determining-the-queries-sent-by-power-bi-desktop"></a>Określanie zapytań wysłanych przez program Power BI Desktop
Domyślnie program **Power BI Desktop** rejestruje zdarzenia podczas danej sesji w pliku śladu o nazwie FlightRecorderCurrent.trc.

W przypadku niektórych źródeł **zapytania bezpośredniego** ten dziennik zawiera wszystkie zapytania wysłane do bazowego źródła danych (pozostałe źródła zapytania bezpośredniego zostaną uwzględnione w przyszłości). Do źródeł, które wysyłają zapytania do dziennika, należą:

* SQL Server
* Azure SQL Database
* Azure SQL Data warehouse
* Oracle
* Teradata
* SAP HANA

Plik śledzenia znajduje się w folderze **AppData** bieżącego użytkownika:

    \<User>\AppData\Local\Microsoft\Power BI Desktop\AnalysisServicesWorkspaces

Oto prosty sposób uzyskania dostępu do tego folderu: W programie **Power BI Desktop** wybierz pozycję **Plik > Opcje i Ustawienia > Opcje**, a następnie wybierz **Diagnostyka**. Zostanie wyświetlone następujące okno dialogowe:

![](media/desktop-directquery-about/directquery-about_06.png)

Po wybraniu linku *Otwórz folder śladów* w obszarze **Opcje diagnostyki** zostanie otwarty następujący folder:

    \<User>\AppData\Local\Microsoft\Power BI Desktop\Traces

Przejście do folderu nadrzędnego tego folderu powoduje wyświetlenie folderu zawierającego *AnalysisServicesWorkspaces*, który będzie zawierał jeden podfolder obszaru roboczego dla każdego otwartego wystąpienia programu **Power BI Desktop**. Nazwy tych podfolderów mają sufiks w postaci liczby całkowitej, taki jak *AnalysisServicesWorkspace2058279583*.

Wewnątrz tego folderu jest podfolder *\Data*, który zawiera plik śledzenia FlightRecorderCurrent.trc dla bieżącej sesji usługi Power BI. Odpowiedni folder obszaru roboczego jest usuwany podczas kończenia skojarzonej sesji programu Power BI Desktop.

Pliki śledzenia można odczytać przy użyciu narzędzia **SQL Server Profiler**, które jest dostępne bezpłatnie do pobrania jako część pakietu **SQL Server Management Studio**. Możesz je uzyskać z [tej lokalizacji](https://msdn.microsoft.com/library/mt238290.aspx).

Po pobraniu i zainstalowaniu pakietu **SQL Server Management Studio** uruchom narzędzie **SQL Server Profiler**.

![](media/desktop-directquery-about/directquery-about_07.png)

Aby otworzyć plik śledzenia, należy wykonać następujące czynności:

1. W narzędziu **SQL Server Profiler** wybierz pozycję **Plik > Otwórz > Plik śledzenia**
2. Wprowadź ścieżkę do pliku śledzenia w aktualnie otwartej sesji usługi Power BI, taką jak:
   
         C:\Users\<user>\AppData\Local\Microsoft\Power BI Desktop\AnalysisServicesWorkspaces\AnalysisServicesWorkspace2058279583\Data
3. Otwórz plik FilghtRecorderCurrent.trc

Wyświetlane są wszystkie zdarzenia z bieżącej sesji. Przykład z adnotacjami jest pokazany poniżej i wyróżnia grupy zdarzeń. Każda grupa ma poniższe:

* Zdarzenie *Początek zapytania* i *Koniec zapytania*, które reprezentują początek i koniec zapytania w języku DAX wygenerowanego przez interfejs użytkownika (na przykład z wizualizacji lub podczas wypełniania listy wartości w filtrze interfejsu użytkownika)
* Jedną lub więcej par zdarzeń *Początek zapytania bezpośredniego* i *Koniec zapytania bezpośredniego*, które reprezentują zapytanie wysyłane do bazowego źródła danych w ramach oceny zapytania w języku DAX.

Należy pamiętać, że wiele zapytań języka DAX może być wykonywanych równolegle, dlatego zdarzenia z różnych grup mogą się przeplatać. Wartość identyfikatora działania może służyć do określenia, które zdarzenia należą do tej samej grupy.

![](media/desktop-directquery-about/directquery-about_08.png)

Inne interesujące kolumny są następujące:

* **TextData:** tekstowe szczegóły zdarzenia. Dla zdarzeń „Początek/koniec zdarzenia” będzie to zapytanie w języku DAX. Dla zdarzeń „Początek/koniec zapytania bezpośredniego” będzie to zapytanie w języku SQL wysyłane do bazowego źródła. Kolumna TextData dla aktualnie wybranego zdarzenia jest też wyświetlana w regionie u dołu.
* **EndTime:** godzina zakończenia zdarzenia.
* **Czas trwania:** czas trwania (w milisekundach) potrzebny do wykonania zapytania w języku DAX lub SQL.
* **Błąd:** wskazuje, czy wystąpił błąd (w takim przypadku zdarzenie jest również wyświetlane na czerwono).

Należy pamiętać, że na powyższej ilustracji niektóre mniej interesujące kolumny zostały zawężone, aby poprawić widoczność interesujących kolumn.

Zalecane podejście do przechwytywania śladu, aby pomóc zdiagnozować potencjalny problem z wydajnością jest następujące:

* Otwórz pojedynczą sesję programu **Power BI Desktop** (aby uniknąć nieporozumień spowodowanych przez wiele folderów obszaru roboczego)
* Wykonaj zestaw stanowiących przedmiot zainteresowania akcji w programie **Power BI Desktop**. Poza tym dodaj kilka dodatkowych akcji, aby upewnić się, że interesujące zdarzenia zostały przesłane do pliku śledzenia.
* Otwórz program **SQL Server Profiler** i sprawdź ślad zgodnie z wcześniejszym opisem. Należy pamiętać, że plik śledzenia zostanie usunięty podczas zamykania programu **Power BI Desktop**. Również dodatkowe akcje w programie Power BI Desktop nie będą natychmiast widoczne — plik śledzenia należy zamknąć i otworzyć ponownie, aby zobaczyć nowe zdarzenia.
* Poszczególne sesje nie powinny być zbyt duże (dziesięć sekund akcji, nie setki), aby ułatwić Interpretowanie pliku śledzenia (i ponieważ istnieje ograniczenie rozmiaru pliku śledzenia, więc dla bardzo długich sesji istnieje prawdopodobieństwo usunięcia wcześniejszych zdarzeń).

#### <a name="understanding-the-form-of-query-sent-by-power-bi-desktop"></a>Opis formularza zapytania wysyłanego przez program Power BI Desktop
Ogólny format zapytań tworzonych i wysyłanych przez program **Power BI Desktop** używa podwyborów dla każdej przywoływanej tabeli, gdzie podwybór jest definiowany przez zapytanie zdefiniowane w **edytorze zapytań**. Załóżmy na przykład następujące tabele TPC-DS w programie SQL Server:

![](media/desktop-directquery-about/directquery-about_09.png)

Rozpatrzmy następujące zapytanie:

![](media/desktop-directquery-about/directquery-about_10.png)

To zapytanie spowoduje wyświetlenie następującej wizualizacji:

![](media/desktop-directquery-about/directquery-about_11.png)

Odświeżanie tej wizualizacji spowoduje zapytanie w języku SQL, które zostało pokazane poniżej następnego akapitu. Jak można stwierdzić, istnieją trzy podwybory dla kolumn Web Sales, Item i Date_dim, z których każda zwraca wszystkie kolumny odpowiedniej tabeli, chociaż w rzeczywistości wizualizacja odwołuje się tylko do czterech kolumn. Te zapytania w podwyborach (są one przyciemnione) są dokładnie wynikiem zapytań zdefiniowanych w **edytorze zapytań**. Nie stwierdzono, żeby użycie podwyborów w ten sposób wpływało na wydajność dla źródeł danych do tej pory obsługiwanych dla zapytania bezpośredniego. Źródła danych, takie jak SQL Server, po prostu optymalizują odwołania do innych kolumn.

Jedną z przyczyn stosowania tego wzorca przez usługi Power BI jest to, że użyte zapytanie SQL może zostać podane bezpośrednio przez analityka, dlatego jest ono używane „jak podano” bez próby jego przepisania.

![](media/desktop-directquery-about/directquery-about_12.png)

## <a name="next-steps"></a>Następne kroki
W tym artykule opisano aspekty **zapytania bezpośredniego**, które są wspólne dla wszystkich źródeł danych. Istnieją pewne szczegóły specyficzne dla poszczególnych źródeł. Zobacz następujące tematy dotyczące konkretnych źródeł:

* [Zapytanie bezpośrednie i platforma SAP HANA](desktop-directquery-sap-hana.md)
* [Zapytanie bezpośrednie i system SAP BW](desktop-directquery-sap-bw.md)

Aby uzyskać więcej informacji na temat **zapytania bezpośredniego**, zapoznaj się z następującymi zasobami:

* [Źródła danych obsługiwane przez zapytanie bezpośrednie](desktop-directquery-data-sources.md)

