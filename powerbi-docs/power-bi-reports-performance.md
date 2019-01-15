---
title: Wydajność usługi Power BI — najlepsze rozwiązania
description: Ten artykuł zawiera wskazówki dotyczące tworzenia szybkich i niezawodnych raportów w usłudze Power BI
author: MarkMcGeeAtAquent
ms.author: kfile
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/18/2018
LocalizationGroup: Reports
ms.openlocfilehash: f603a733c6c604a89b0b9608904acdf13b66b713
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54287789"
---
# <a name="power-bi-performance-best-practices"></a>Wydajność usługi Power BI — najlepsze rozwiązania

Ten artykuł zawiera wskazówki dotyczące tworzenia szybkich i niezawodnych raportów w usłudze Power BI.  

## <a name="use-filters-to-limit-report-visuals-to-display-only-whats-needed"></a>Wyświetlanie w wizualizacjach raportu tylko tego, co niezbędne, przy użyciu filtrów 

Im więcej danych do wyświetlenia w wizualizacji, tym wolniej ta wizualizacja będzie ładowana. Mimo że ta zasada wydaje się oczywista, można o niej łatwo zapomnieć. Załóżmy na przykład, że masz duży zestaw danych. Na jego podstawie tworzysz raport z tabelą w tabeli. Użytkownicy końcowi stosują fragmentatory na stronie, aby uzyskać odpowiednie wiersze — na ogół interesuje ich tylko kilkadziesiąt z nich.

Powszechnym błędem jest brak filtrowania widoku domyślnego tabeli i wyświetlanie na przykład ponad 100 milionów wierszy. Dane dla tych wierszy muszą być ładowane do pamięci i dekompresowane przy każdym odświeżeniu. Powoduje to ogromne obciążenia pamięci. Rozwiązanie: zmniejsz maksymalną liczbę elementów wyświetlanych w tabeli za pomocą filtru „N pierwszych”. Maksymalna liczba elementów może być dużo większa niż to, czego potrzebują użytkownicy, na przykład 10 000. W rezultacie z punktu widzenia użytkownika nic się nie zmieni, ale wykorzystanie pamięci przez raport zmniejszy się o wiele rzędów wielkości, a wydajność odpowiednio wzrośnie.

Podejście podobne do powyższego jest zalecane dla wszystkich wizualizacji w raportach. Zadaj sobie pytanie, czy wszystkie dane w tej wizualizacji są potrzebne? Czy istnieją sposoby na odfiltrowanie ilości danych pokazywanych w wizualizacji przy minimalnym wpływie na użytkownika końcowego? Pamiętaj, że tabele w szczególności mogą zużywać dużo zasobów.

## <a name="limit-visuals-on-report-pages"></a>Ograniczanie wizualizacji na stronach raportu

Powyższa zasada w tej samej mierze dotyczy liczby wizualizacji w konkretnym raporcie. Zdecydowanie zaleca się, aby ograniczyć liczbę wizualizacji w określonym raporcie tylko do tego, co niezbędne. Strony przeglądania szczegółowego to bardzo dobry sposób na dostarczenie dodatkowych informacji bez upychania kolejnych wizualizacji w raporcie.  

## <a name="optimize-your-model"></a>Optymalizowanie modelu

Oto niektóre najlepsze rozwiązania:

- Nieużywane tabele i kolumny powinny być w miarę możliwości usuwane. 
- Unikaj liczności unikatowych wartości na polach o dużej kardynalności, tj. milionów wartości odrębnych.  
- Podejmij kroki w celu uniknięcia pól ze zbędną precyzją i dużą kardynalnością. Możesz na przykład rozdzielić wysoce unikatowe wartości daty i godziny na osobne kolumny, takie jak Miesiąc, Rok, Dzień itd. Natomiast tam, gdzie można, zastosuj zaokrąglanie do pól o wysokiej precyzji, aby zmniejszyć kardynalność (np. 13,29889 -> 13,3).
- Używaj liczb całkowitych zamiast ciągów tam, gdzie to możliwe.
- Z rozwagą korzystaj z funkcji języka DAX, które muszą sprawdzać każdy wiersz w tabeli — na przykład RANKX — w najgorszym przypadku te funkcje mogą wykładniczo wydłużyć czas wykonywania i zwiększyć wymagania dotyczące pamięci, biorąc pod uwagę liniowy wzrost rozmiaru tabeli.
- Podczas nawiązywania połączenia ze źródłami danych za pomocą zapytania bezpośredniego rozważ indeksowanie kolumn, które zazwyczaj są filtrowane lub ponownie dzielone — znacznie poprawia to czas reakcji raportu.  

Aby uzyskać więcej wskazówek dotyczących optymalizacji źródeł danych pod kątem zapytań bezpośrednich, zobacz [Zapytania bezpośrednie w usłudze Microsoft SQL Server 2016 Analysis Services](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/).

## <a name="directquery-and-live-connection-understand-underlying-data-source-performance"></a>Zapytanie bezpośrednie i połączenie na żywo: zrozumienie wydajności bazowego źródła danych

W przypadku zapytania bezpośredniego i połączenia na żywo, kiedy użytkownicy wyświetlają raport usługi Power BI, usługa Power BI wysyła zapytania w czasie rzeczywistym do bazowego źródła danych. Gdy źródło danych zwróci dane dla zapytania, raport jest renderowany. W związku z tym wydajność raportu w tych przypadkach zależy w dużym stopniu od wydajności bazowego źródła danych.

W takiej sytuacji ważne jest, aby poznać wydajność bazowego źródła danych. Różne źródła danych oferują różne narzędzia umożliwiające poznanie wydajności zapytania. Na przykład programy SQL Server i Azure SQL udostępniają magazyn zapytań, który przechwytuje historię zapytań i statystyki czasu wykonywania.

Z zasady podczas wdrażania raportów usługi Power BI opartych na zapytaniu bezpośrednim i połączeniu na żywo spróbuj wykonać czynności, które będą wykonywać użytkownicy, w programie Power BI Desktop. Jeśli raport ładuje się wolno w programie Power BI Desktop, prawie na pewno będzie także ładować się wolno w usłudze dla użytkowników końcowych. 

## <a name="directquery-best-practices"></a>Najlepsze rozwiązania dotyczące zapytania bezpośredniego

W poniższej sekcji opisano ogólne najlepsze rozwiązania dotyczące nawiązywania połączenia za pośrednictwem zapytania bezpośredniego.
  
### <a name="db-design-guidance"></a>Wskazówki dotyczące projektowania bazy danych

- Wypychaj miary i kolumny obliczeniowe do źródła tam, gdzie to możliwe — im bliżej źródła się znajdują, tym wyższe prawdopodobieństwo wydajności.
- Optymalizuj! Poznaj plany wykonywania zapytań, dodawaj indeksy dla często filtrowanych kolumn itd.

### <a name="modeling-guidance"></a>Wskazówki dotyczące modelowania

- Zacznij w programie Power BI Desktop.
- Unikaj złożonych zapytań w Edytorze zapytań.
- Nie używaj względnego filtrowania danych w Edytorze zapytań.  
- Na początku twórz proste miary i stopniowo zwiększaj ich złożoność.
- Unikaj relacji na kolumnach obliczeniowych i kolumnach unikatowych identyfikatorów.
- Spróbuj ustawić opcję „Przyjmij integralność referencyjną” dla relacji — w wielu przypadkach może to znacznie poprawić wydajność zapytań.  

### <a name="general"></a>Ogólne

- Najpierw zastosuj filtry.
- Rozważ wyłączenie interakcji między wizualizacjami — skróci to czas ładowania zapytań w przypadku wyróżniania krzyżowego.
- Ogranicz liczbę wizualizacji i danych na wizualizację, jak opisano powyżej.
- Włączenie zabezpieczeń na poziomie wiersza może mieć znaczący wpływ na wydajność. Przetestuj różne role zabezpieczeń na poziomie wiersza, które będą przyjmować użytkownicy.
- Istnieją limity czasu na poziomie zapytania wymuszane przez usługę w celu zapewnienia, że długo wykonywane zapytania nie zajmą wszystkich zasobów systemowych. Zapytania trwające dłużej niż 225 sekund przekroczą limit czasu i spowodują wystąpienie błędu na poziomie wizualizacji.

## <a name="understand-dashboards-and-query-caches"></a>Opis pulpitów nawigacyjnych i pamięci podręcznej zapytań

Wizualizacje przypięte do pulpitów nawigacyjnych są obsługiwane przez pamięć podręczną zapytań, gdy pulpit nawigacyjny jest ładowany. Z drugiej strony, podczas wyświetlania raportu zapytania są na bieżąco wysyłane do źródła danych — do usługi Power BI (w przypadku importowania) lub określonego przez Ciebie źródła danych (w przypadku zapytania bezpośredniego lub połączenia na żywo).  

> [!NOTE]
> Gdy przypinasz kafelki raportów na żywo do pulpitu nawigacyjnego, nie są one obsługiwane przez pamięć podręczną zapytań — zamiast tego zachowują się one jak raporty i na bieżąco wysyłają zapytania do źródła zaplecza.

Jak sugeruje nazwa, pobieranie danych z pamięci podręcznej zapytań zapewnia lepszą i stabilniejszą wydajność niż poleganie na źródle danych. Jednym ze sposobów wykorzystania tej funkcjonalności jest ustawianie pulpitów nawigacyjnych jako pierwszej strony docelowej dla użytkowników. Przypnij często używane i popularne wizualizacje do pulpitów nawigacyjnych. Dzięki temu pulpity nawigacyjne staną się cenną „pierwszą linią obrony”, zapewniając stałą wydajność z mniejszym obciążeniem pojemności. Użytkownicy nadal mogą kliknąć, aby wyświetlić raport w celu uzyskania szczegółowych informacji.  
 

W przypadku zapytań bezpośrednich i połączeń na żywo ta pamięć podręczna zapytań jest aktualizowana okresowo przez wysyłanie zapytań do źródła danych. Domyślnie ta operacja jest wykonywana co godzinę, ale można skonfigurować inny okres w ustawieniach zestawu danych. Podczas każdej aktualizacji pamięci podręcznej zapytań do bazowego źródła danych są wysyłane zapytania w celu zaktualizowania tej pamięci podręcznej. Liczba wygenerowanych zapytań zależy od liczby wizualizacji przypiętych do pulpitów nawigacyjnych opartych na tym źródle danych. Pamiętaj, że włączenie zabezpieczeń na poziomie wiersza powoduje generowanie zapytań dla każdego innego kontekstu zabezpieczeń. Jeśli na przykład istnieją dwie różne role użytkowników z dwoma różnymi widokami danych, to podczas odświeżania pamięci podręcznej zapytań są generowane dwa zestawy zapytań. 

## <a name="understand-custom-visual-performance"></a>Opis wydajności wizualizacji niestandardowych 

Ustaw dla każdej wizualizacji niestandardowej jej własne tempo, aby zapewnić wysoką wydajność. Źle zoptymalizowane wizualizacje niestandardowe mogą negatywnie wpłynąć na wydajność całego raportu. 

## <a name="deep-dive-into-query-performance-with-sql-profiler-and-power-bi-desktop"></a>Szczegółowy wgląd w wydajność zapytań za pomocą programów SQL Profiler i Power BI Desktop

Aby zapoznać się z bardziej szczegółowymi informacjami o tym, które wizualizacje zajmują najwięcej czasu i zasobów, możesz połączyć program SQL Profiler z programem Power BI Desktop w celu uzyskania pełnego widoku wydajności zapytań.

> [!NOTE]
> Program Power BI Desktop obsługuje nawiązywanie połączenia z portem diagnostycznym. Port diagnostyczny umożliwia innym narzędziom nawiązywanie połączenia i przeprowadzanie śledzeń w celach diagnostycznych. *Wprowadzanie jakichkolwiek zmian w modelu nie jest obsługiwane! Zmiany w modelu mogą prowadzić do uszkodzenia i utraty danych.*

Instrukcje są następujące:
  
1. **Zainstaluj program SQL Server Profiler i uruchom program Power BI Desktop**

   Program SQL Server Profiler jest dostępny w ramach programu SQL Server Management Studio.

2. **Określ port używany przez program Power BI Desktop**

   Uruchom wiersz polecenia lub program PowerShell z uprawnieniami administratora, a następnie użyj polecenia netstat, aby znaleźć port, którego używa program Power BI Desktop do analizy:

   `> netstat -b -n`

   W wyniku powinna zostać wyświetlona lista aplikacji i ich otwartych portów, na przykład:  

   `TCP    [::1]:55786            [::1]:55830            ESTABLISHED`

   [msmdsrv.exe]

   Wyszukaj port używany przez program msmdsrv.exe i zapisz go do późniejszego użycia. W tym przypadku użyj portu 55786.
3. **Połącz program SQL Server Profiler z programem Power BI Desktop**

   - Uruchom program SQL Server Profiler z menu **Start**.
   - Wybierz pozycję **Plik** > **New Trace** (Plik > Nowe śledzenie).
   - Typ serwera: Analysis Services
   - Server name: localhost:[numer portu znaleziony powyżej]
   - Na następnym ekranie wybierz pozycję **Run** (Uruchom).
   - Teraz program SQL Profiler działa i aktywnie profiluje zapytania, które wysyła program Power BI Desktop. 
   - Gdy zapytania są wykonywane, możesz zobaczyć ich czasy trwania i czasy procesora CPU — korzystając z tych informacji, możesz określić, które zapytania są wąskimi gardłami.  

Za pośrednictwem programu SQL Profiler możesz zidentyfikować zapytania, które zajmują najwięcej czasu procesora CPU i które prawdopodobnie są wąskimi gardłami wydajności. Wizualizacje, które wykonują te zapytania, powinny być dalej optymalizowane.

## <a name="gateway-best-practices"></a>Najlepsze rozwiązania dotyczące bramy

Brama danych lokalnych jest doskonałym narzędziem do łączenia usługi Power BI z danymi lokalnymi. Jednocześnie, przy słabym planowaniu, może również stać się wąskim gardłem dla wydajności raportu. Dotyczy to zwłaszcza zestawów danych zapytań bezpośrednich i połączeń na żywo, gdzie wszystkie zapytania i odpowiedzi na nie przechodzą przez tę bramę. Poniżej przedstawiono najlepsze rozwiązania umożliwiające zapewnienie wysokiej wydajności bramy: 

- **Użyj trybu przedsiębiorstwa**, a nie trybu osobistego.
- **Zalecana specyfikacja sprzętowa dla bramy** — osiem rdzeni procesora CPU, 16 GB pamięci RAM.
- **Konfiguracja monitorowania** — skonfiguruj monitorowanie wydajności na maszynie bramy, aby uzyskać informacje, czy brama jest przeciążona i staje się wąskim gardłem. Aby uzyskać więcej informacji, zobacz [Rozwiązywanie problemów z lokalną bramą danych](service-gateway-onprem-tshoot.md).
- **Skalowanie w górę i skalowanie w poziomie** — jeśli brama rzeczywiście staje się wąskim gardłem, rozważ skalowanie w górę (tj. przeniesienie bramy na wydajniejszą maszynę z lepszym procesorem i większą ilością pamięci RAM) lub skalowanie w poziomie (na przykład podzielenie zestawów danych na kilka bram). 
- **Odrębne importowanie a zapytanie bezpośrednie** — w przypadku skalowania w poziomie weź pod uwagę oddzielenie bram odpowiedzialnych za import od bram odpowiedzialnych za zapytania bezpośrednie.

## <a name="network-latency"></a>Opóźnienie sieci

Opóźnienie sieci może wpłynąć na wydajność raportu, zwiększając czas wymagany na dotarcie żądania do usługi Power BI i na dostarczenie odpowiedzi. Dzierżawy w usłudze Power BI są przypisywane do określonych regionów. Możesz sprawdzić, jaki jest region „domowy” Twojej dzierżawy, przechodząc do witryny powerbi.com, wybierając ikonę ? w prawym górnym rogu, a następnie wybierając pozycję **Power BI — informacje**. Gdy użytkownicy z dzierżawy uzyskują dostęp do usługi Power BI, ich żądania są zawsze kierowane do tego regionu. Gdy żądanie dotrze do usługi Power BI, usługa może wysłać dodatkowe żądania — na przykład do bazowego źródła danych lub do bramy — które również podlegają opóźnieniu sieci.

Narzędzia takie jak [Azure Speed Test](http://azurespeedtest.azurewebsites.net/) mogą wskazać wielkość opóźnienia sieci między klientem a regionem platformy Azure. Ogólnie rzecz biorąc, w celu zminimalizowania wpływu opóźnienia sieci staraj się, aby źródła danych, bramy i klaster usługi Power BI znajdowały się jak najbliżej siebie. Jeśli opóźnienie sieci jest problemem, możesz spróbować umiejscowić bramy i źródła danych bliżej klastra usługi Power BI, umieszczając je na maszynach wirtualnych.

Aby dodatkowo poprawić opóźnienie sieci, rozważ użycie usługi [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/), która może utworzyć szybsze, bardziej niezawodne połączenia sieciowe między Twoimi klientami a centrami danych platformy Azure.

## <a name="next-steps"></a>Następne kroki

- [Planowanie wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy) — wszechstronne wskazówki dotyczące wielkoskalowych wdrożeń usługi Power BI
- [Zapytania bezpośrednie w usłudze SQL Server 2016 Analysis Services](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/)
- [[YouTube] Tworzenie szybkich i niezawodnych raportów w usłudze Power BI](https://www.youtube.com/watch?v=GhiJABR7XX0)
- [[YouTube] Wdrożenia usługi Power BI Enterprise](https://www.youtube.com/watch?v=K-zEWICvICM)