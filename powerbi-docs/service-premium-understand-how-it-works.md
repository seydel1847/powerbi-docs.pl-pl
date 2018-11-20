---
title: Używanie i optymalizacja pamięci o pojemności Power BI Premium
description: Informacje na temat używania i optymalizacji pamięci o pojemności Power BI Premium.
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: powerbi
ms.component: powerbi-admin
ms.author: mblythe
ms.reviewer: mblythe
author: mgblythe
manager: kfile
ms.openlocfilehash: 534c06c66d561a04dbffc04412095d6924c92781
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2018
ms.locfileid: "51266075"
---
# <a name="microsoft-power-bi-premium-capacity-resource-management-and-optimization"></a>Optymalizacja zasobów firmy Microsoft o pojemności Power BI Premium i zarządzanie nimi

W tym artykule opisano, jak rozwiązanie Power BI Premium zarządza zasobami. Ten artykuł zawiera także przykłady i wskazówki dotyczące rozwiązywania problemów. Omówienie znajdziesz w artykule [Power BI Premium — co to jest?](service-premium.md).

## <a name="premium-capacity-memory-management"></a>Zarządzanie pamięcią o pojemności Premium

 Pamięć o pojemności Premium jest wykorzystywana przez:

* Zestawy danych, które są ładowane do pamięci
* Operacje odświeżania zestawów danych (zaplanowane i na żądanie)
* Obciążenia obsługiwane przez pojemność
* Zapytania dotyczące raportów

Jeśli żądanie jest wystawiane względem opublikowanego zestawu danych w ramach pojemności, ten zestaw danych jest ładowany do pamięci z magazynu trwałego (proces ten jest również nazywany ładowaniem obrazu). Utrzymywanie załadowanego zestawu danych w pamięci pomaga szybko odpowiadać na przyszłe zapytania dotyczące tego zestawu danych. Oprócz pamięci potrzebnej do utrzymywania zestawu danych załadowanego do pamięci zapytania dotyczące raportów i operacje odświeżania zestawu danych wykorzystują dodatkową pamięć.

### <a name="dataset-memory-estimation"></a>Szacowanie wielkości pamięci zestawu danych

Podczas próby załadowania zestawu danych do pamięci usługa Power BI szacuje wielkość pamięci, która będzie wymagana do wykonania żądanego polecenia przez zestaw danych. Zestawy danych w pamięci mają zazwyczaj większy rozmiar niż w przypadku zapisania ich na dysku. Podczas odświeżania zestawu danych usługa Power BI wymaga co najmniej dwukrotnie większej ilości pamięci niż w stanie bezczynności zestawu danych.

### <a name="overcommitting-capacity-eviction-and-reloading-of-datasets"></a>Nadmiarowe zatwierdzanie pojemności, eksmisja i ponowne ładowanie zestawów danych

Rozwiązanie Power BI Premium umożliwia *nadmiarowe zatwierdzanie* pojemności. Można na przykład opublikować więcej zestawów danych niż może być przechowywanych w pojemności. Jeśli opublikowane zestawy danych potrzebują więcej pamięci niż jest dostępne w ramach pojemności, niektóre z tych zestawów są przechowywane oddzielnie w magazynie trwałym. Magazyn trwały jest częścią magazynu o wielkości 100 TB skojarzoną z każdą z pojemności.

Które zestawy danych pozostaną w pamięci i co się stanie z innymi zestawami danych? Jak opisano wcześniej, gdy żądanie jest wystawiane na podstawie zestawu danych, jest również ładowane do pamięci (ładowanie obrazu). Żądanie może być zapytaniem dotyczącym raportu lub operacją odświeżania. Ale ponieważ można nadmiarowo zatwierdzać pojemność, może ona również powodować wykorzystanie pamięci. Gdy pojemność powoduje wykorzystanie pamięci, węzeł *eksmituje* z pamięci jeden lub większą liczbę zestawów danych. Nieaktywne zestawy danych (dla których aktualnie nie są wykonywane żadne operacje zapytania/odświeżania) są eksmitowane jako pierwsze. Następnie kolejność eksmitowania bazuje na mierze „najdawniej używane” (LRU). Jeśli nowe polecenia są wydawane do eksmitowanego zestawu danych, usługa próbuje ponownie załadować go do pamięci, potencjalnie powodując eksmisję innych zestawów danych. Takie zachowanie umożliwia efektywniejsze wykorzystanie, ponieważ pozwala pojemności na obsługę o wiele większej liczby zestawów danych niż jej pamięć może pomieścić.

Ładowanie zestawu danych do pamięci to stosunkowo droga operacja. W zależności od rozmiaru zestawu danych może ona potrwać od kilku sekund dla małych zestawów danych do dziesiątek sekund, a nawet minut, dla znaczących zestawów danych, takich jak zestawy o rozmiarze ok. 10 GB. Pojemność Premium próbuje zminimalizować liczbę operacji ładowania pojemności, jak najdłużej przechowując w pamięci najdawniej używane zestawy danych. Jeśli jest potrzebna dodatkowa pamięć, trzeba będzie eksmitować niektóre zestawy danych, a system spróbuje wybrać zestaw, który w najmniejszym stopniu wpływa na środowisko użytkownika. Jeśli jest potrzebna dodatkowa pamięć, trzeba będzie eksmitować niektóre zestawy danych, a system spróbuje wybrać zestaw, który w najmniejszym stopniu wpływa na środowisko użytkownika. Na przykład system będzie unikał eksmitowania zestawów danych, które były aktywnie używane w ciągu ostatnich kilku minut. W przypadku takich zestawów istnieje duże prawdopodobieństwo, że zostanie dla nich wkrótce wykonane ponowne zapytanie.

Sam proces eksmisji jest szybką operacją. Jeśli zestaw danych nie jest aktywnie używany w czasie eksmisji, użytkownik nie będzie mógł określić wpływu powiązanego z eksmisją. Jeśli jednak równocześnie wiele zestawów danych jest aktywnie używanych i nie ma wystarczającej pamięci do obsługi wszystkich tych zestawów, może zostać wykonanych wiele operacji eksmisji. Istnienie zbyt wielu aktywnych zestawów danych może doprowadzić do przeładowania, w przypadku którego zestawy danych są eksmitowane i ponownie ładowane w sposób ciągły, a użytkownicy mogą zauważyć znaczące pogorszenie wydajności i czasów odpowiedzi.

### <a name="dataset-refresh-memory-requirement-competing-with-an-active-dataset-memory-requirement"></a>Konkurencja między wymaganiami dotyczącymi pamięci na potrzeby odświeżania zestawu danych i wymaganiami dotyczącymi pamięci aktywnego zestawu danych

Zestawy danych można odświeżać zgodnie z harmonogramem lub na żądanie użytkowników. Jak opisano wcześniej, pamięć wymagana do wykonania pełnych operacji odświeżania jest co najmniej dwukrotnie większa niż rozmiar pamięci załadowanych i pozostających w stanie bezczynności zestawów danych. Przed rozpoczęciem odświeżania jest szacowana wymagana wielkość pamięci. Jeśli całkowita wymagana pamięć jest większa niż pamięć dostępna w pojemności, niektóre zestawy danych są eksmitowane. Tu również eksmitowanie bazuje na mierze „najdawniej używane” (LRU).

Jeśli mimo przeprowadzenia eksmisji wymagana pamięć jest niedostępna, operacja odświeżania jest umieszczana w kolejce w oczekiwaniu na ponowne podjęcie próby. Usługa ponawia próbę do momentu jej pomyślnego zakończenia lub rozpoczęcia nowej akcji odświeżania.

Jeśli zapytanie interaktywne jest tworzone dla dowolnego zestawu danych w ramach pojemności, a nie ma wystarczającej pamięci z powodu trwającego odświeżania, żądanie to kończy się niepowodzeniem i użytkownik musi podjąć kolejną próbę jego wykonania.

### <a name="workloads"></a>Obciążenia

Domyślnie pojemności usług **Power BI Premium** i **Power BI Embedded** obsługują tylko obciążenie skojarzone z uruchamianiem zapytań usługi Power BI w chmurze. Oferujemy teraz obsługę wersji zapoznawczej dwóch dodatkowych obciążeń: **Raporty podzielone na strony** i **Przepływy danych**. W przypadku jej włączenia te obciążenia będą mogły wpływać na użycie pamięci w pojemności. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie obciążeń](service-admin-premium-manage.md#configure-workloads).

## <a name="cpu-resource-management-in-premium-capacity"></a>Zarządzanie zasobami procesora w ramach pojemności Premium

Istnieją dwa podstawowe elementy wykorzystujące zasoby procesora:

* Zapytania z raportów
* Odświeżanie (przetwarzanie)

### <a name="queries-from-reports"></a>Zapytania z raportów

Zapytania dotyczące raportów wykorzystują zasoby procesora w ramach pojemności. Jeśli raporty zawierają nieefektywne zapytania lub korzysta z nich jednocześnie wielu użytkowników, mogą one wykorzystywać dużo zasobów procesora CPU. Istniejąca pojemność może nie być wystarczająca do obsługi takiego obciążenia.

### <a name="refresh-parallelization-policy"></a>Zasady równoległego przetwarzania odświeżania

Pamięć nie jest jedynym zasobem, który może ograniczać odświeżanie zestawów danych. Istotnym czynnikiem może być także liczba rdzeni wirtualnych na serwerze. Ponieważ każda operacja odświeżania wymaga określonej liczby rdzeni wirtualnych, istnieje limit liczby odświeżeń, które można uruchomić równolegle. Limity dla poszczególnych jednostek SKU zostały szczegółowo opisany w poniższej tabeli. Dodatkowe operacje odświeżania, które wykraczają poza te limity, są umieszczane w kolejce.

 | SKU | Rdzenie wirtualne zaplecza | Równoległość odświeżania modelu |
 | --- | --- | --- |
 | A1  | 0,5  | 1  |
 | A2  | 1  | 2  |
 | A3  | 2  | 3  |
 | A4  | 4  | 6  |
 | A5  | 8  | 12  |
 | A6  | 16  | 24  |
 | EM1  | 0,5  | 1  |
 | EM2  | 1  | 2  |
 | EM3  | 2  | 3  |
 | P1  | 4  | 6  |
 | P2  | 8  | 12  |
 | P3  | 16  | 24  |
 | P4  | 32  | 48  |
 | P5  | 64  | 96  |

 > [!TIP]
> Jeśli operacje odświeżania są opóźnione, sprawdź liczbę odświeżeń równoległych obsługiwanych w ramach pojemności.

## <a name="example-scenarios"></a>Przykładowe scenariusze

Oto kilka typowych scenariuszy i akcje wykonywane przez usługę:

**Dwadzieścia zaplanowanych operacji odświeżania przesłanych w tym samym czasie**. Usługa Power BI próbuje uruchomić pierwsze *x* operacji odświeżania w tym samym czasie. Wartość *x* jest określona w zasadach równoległego przetwarzania odświeżania dla danej jednostki SKU. Jeżeli usługa Power BI nie może uzyskać wystarczającej pamięci przez eksmisję nieaktywnych zestawów danych (zestawów danych ostatnio nieużywanych), nie wszystkie odświeżenia (*x*) zostaną uruchomione jednocześnie. Każde odświeżenie, którego nie można uruchomić, jest przechowywane w kolejce do momentu, gdy będzie ono możliwe.

**Dwa odświeżenia uruchomione jednocześnie, w przypadku gdy wystarczy pamięci na zakończenie tylko jednego z nich**. Uruchamiane jest to, które można zakończyć. Próba uruchomienia drugiej operacji zostanie ponowiona później.

**Wiele zestawów danych jest uwzględnianych w zapytaniu, podczas gdy kilka zestawów danych jest odświeżanych**. Jeśli nie ma wystarczającej ilości pamięci, usługa Power BI podejmuje próbę zatrzymania aktywnych odświeżeń, aby nadać priorytet zapytaniom interaktywnym. Powoduje to obniżenie wydajności odświeżania.

**Zestaw danych wymaga zbyt dużej ilości pamięci do odświeżenia przy bieżącym rozmiarze pojemności**. Odświeżanie kończy się niepowodzeniem. Próby uzyskania większej ilości pamięci przez eksmisję nie są podejmowane.

**Odświeżanie pojedynczego zestawu danych wymagającego zwiększonych zasobów pamięci**. Jeśli wzrost zasobów pamięci jest większy niż zasoby pamięci dostępne przez eksmisję nieaktywnych zestawów danych, próba odświeżenia zostanie ponowiona później, gdy będzie dostępna wystarczająca ilość pamięci do jej obsługi.

**Zapytanie jest wykonywane dla zestawu danych, który nie może uzyskać wystarczającej ilości pamięci przez eksmitowanie wszystkich nieaktywnych zestawów danych i odświeżeń**. Te zapytania kończą się niepowodzeniem. W przypadku takich wymagań dotyczących obciążeń należy zakupić większą pojemność.

## <a name="troubleshooting-and-testing"></a>Rozwiązywanie problemów i testowanie

Jeśli raporty działają wolno lub nie odpowiadają, należy uruchomić testowanie tylko dla jednego użytkownika w raporcie. Następnie należy rozpocząć zwiększanie obciążenia użytkowników współbieżnych w celu zidentyfikowania limitu. W wielu przypadkach dostrajanie zapytań języka DAX może znacznie zmienić wydajność raportów. Dostrajanie zapytań zwiększa także liczbę jednocześnie obsługiwanych użytkowników przez pojemności. [Monitorowanie pojemności](service-admin-premium-monitor-capacity.md) umożliwia identyfikowanie potencjalnych problemów z wydajnością.

Użyj pojemności usługi Power BI Embedded na platformie Azure do testowania różnych jednostek SKU i określenia najlepszych jednostek SKU w warstwie Premium dla oczekiwanego obciążenia. Jednostka SKU usługi Power BI Embedded A4 jest odpowiednikiem wersji P1, A5 = P2 i A6 = P3. Na platformie Azure można łatwo przełączać się między jednostkami SKU przez skalowanie w górę i w dół w witrynie Azure Portal. Po znalezieniu jednostki SKU najlepiej odpowiadającej obciążeniu i zakończeniu testowania można usunąć jednostkę SKU.

W niektórych przypadkach otwarcie pliku programu Power BI Desktop (pbix) modelu na komputerze oraz sprawdzenie pamięci i użycia procesora dostarcza wiele informacji o problemie. Nie jest to pomocne w przypadku bardzo dużych modeli, ale w przypadku niektórych mniejszych modeli można spróbować otworzyć i odświeżyć model z komputera, a także wykonać dotyczące go zapytania. Sprawdź rozmiar modelu, pamięć i użycie procesora po otwarciu modelu. Spróbuj odświeżyć i wykonać zapytanie. Za pomocą menedżera zadań można sprawdzić zużycie procesora i pamięci dla lokalnego pliku. Czasami na podstawie tych metryk na komputerze można ustalić, czy niższa pojemność Premium, taka jak P1/P2, będzie niewystarczająca dla danego rozwiązania.

## <a name="next-steps"></a>Następne kroki

[Zarządzanie pojemnościami w usługach Power BI Premium i Power BI Embedded](service-admin-premium-manage.md)