---
title: Używanie i optymalizacja pamięci o pojemności Power BI Premium
description: Informacje na temat używania i optymalizacji pamięci o pojemności Power BI Premium.
ms.date: 04/30/2018
ms.topic: conceptual
ms.service: powerbi
ms.component: powerbi-admin
ms.author: susuresh
ms.reviewer: susuresh
author: suds001
manager: kfile
ms.openlocfilehash: 03c5e56c5f516bb1f09f51463d4c533185fbb63c
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34298463"
---
# <a name="power-bi-premium-capacity-resource-management-and-optimization"></a>Optymalizacja zasobów o pojemności Power BI Premium i zarządzanie nimi

W tym artykule opisano sposób zarządzania zasobami w usłudze Power BI Premium oraz przedstawiono wskazówki dotyczące planowania i optymalizowania rozwiązania.

## <a name="premium-capacity-memory-management"></a>Zarządzanie pamięcią o pojemności Premium

 Pamięć o pojemności Premium jest wykorzystywana przez:

* Pamięć używaną przez załadowane zestawy danych
* Pamięć używaną przez operacje odświeżania zestawów danych (zaplanowane i na żądanie)
* Pamięć używaną przez zapytania dotyczące raportu

Jeśli żądanie jest wystawiane względem opublikowanego zestawu danych w ramach pojemności, ten zestaw danych jest ładowany do pamięci z magazynu trwałego (proces ten jest również nazywany ładowaniem obrazu). Utrzymywanie załadowanego zestawu danych w pamięci pomaga szybko odpowiadać na przyszłe zapytania dotyczące tego zestawu danych. Oprócz pamięci potrzebnej do utrzymywania zestawu danych załadowanego do pamięci, zapytania dotyczące raportów i operacje odświeżania zestawu danych również wykorzystują dodatkową pamięć.

### <a name="dataset-memory-estimation"></a>Szacowanie wielkości pamięci zestawu danych

Podczas próby załadowania zestawu danych do pamięci usługa Power BI szacuje wielkość pamięci, która będzie wymagana do wykonania żądanego polecenia przez zestaw danych. Zestawy danych w pamięci mają zazwyczaj większy rozmiar niż w przypadku zapisania ich na dysku. Podczas odświeżania zestawu danych wymagana pojemność pamięci jest co najmniej dwukrotnie większa niż podczas stanu bezczynności.

### <a name="overcommitting-capacity-eviction-and-reloading-of-datasets"></a>Nadmiarowe zatwierdzanie pojemności, eksmisja i ponowne ładowanie zestawów danych

Usługa Power BI Premium umożliwia nadmiarowe zatwierdzanie pojemności. Można na przykład opublikować więcej zestawów danych niż pamięć może pomieścić. Jeśli zestawy danych opublikowane w ramach pojemności potrzebują więcej pamięci niż pomieści pojemność, niektóre z tych zestawów będą przechowywane oddzielnie w magazynie trwałym. Magazyn trwały jest częścią magazynu o wielkości 100 TB skojarzoną z każdą z pojemności.

Które zestawy danych pozostaną w pamięci i co się stanie z innymi zestawami danych? Jak opisano wcześniej, gdy żądanie jest wystawiane na podstawie zestawu danych, jest również ładowane do pamięci (ładowanie obrazu). Żądanie może być zapytaniem dotyczącym raportu lub operacją odświeżania.

Ponieważ można nadmiarowo zatwierdzać pojemność, może ona również powodować wykorzystanie pamięci. Gdy pojemność powoduje wykorzystanie pamięci (ponieważ trzeba załadować nowy zestaw danych lub zapytania dotyczące niektórych załadowanych zestawów danych zwiększają wymaganą pamięć), węzeł *przeprowadza eksmisję co najmniej jednego zestawu danych* zajmującego pamięć w ramach pojemności. Zestawy danych, które są nieaktywne (tzn. aktualnie nie są wykonywane żadne operacje zapytań/odświeżania), są eksmitowane jako pierwsze, a stosowana kolejność eksmisji to „najdawniej używany” (LRU, last recently used). Jeśli nowe polecenia są wydawane do eksmitowanego zestawu danych, usługa próbuje ponownie załadować go do pamięci, potencjalnie powodując eksmisję innych zestawów danych. Takie zachowanie umożliwia efektywniejsze wykorzystanie, ponieważ pozwala pojemności na obsługę o wiele większej liczby zestawów danych niż jej pamięć może pomieścić.

Ładowanie zestawu danych do pamięci to stosunkowo droga operacja. W zależności od rozmiaru zestawu danych może ona potrwać od kilku sekund dla małych zestawów danych do dziesiątek sekund, a nawet minut, dla dużych zestawów danych, takich jak zestawy o rozmiarze ok. 10 GB. Pojemność Premium próbuje zminimalizować liczbę operacji ładowania pojemności, jak najdłużej przechowując w pamięci najdawniej używane zestawy danych. Jeśli jest potrzebna dodatkowa pamięć, trzeba będzie eksmitować niektóre zestawy danych, a system spróbuje wybrać zestaw, który w najmniejszym stopniu wpływa na środowisko użytkownika. Jeśli jest potrzebna dodatkowa pamięć, trzeba będzie eksmitować niektóre zestawy danych, a system spróbuje wybrać zestaw, który w najmniejszym stopniu wpływa na środowisko użytkownika. Na przykład system będzie unikać eksmitowania zestawów danych, które były aktywnie używane w ciągu ostatnich kilku minut, ponieważ mogą wkrótce otrzymywać zapytania.

Sam proces eksmisji jest szybką operacją. Jeśli zestaw danych nie jest aktywnie używany w czasie eksmisji, użytkownik nie będzie mógł określić wpływu powiązanego z eksmisją. Jeśli jednak równocześnie wiele zestawów danych jest aktywnie używanych i nie ma wystarczającej pamięci do obsługi wszystkich tych zestawów, może zostać wykonanych wiele operacji eksmisji. Może to prowadzić do przeładowania, w przypadku którego zestawy danych są eksmitowane i ponownie ładowane w sposób ciągły, a użytkownicy mogą zauważyć znaczące pogorszenie wydajności i czasów odpowiedzi.

### <a name="dataset-refresh-memory-requirement-competing-with-an-active-dataset-memory-requirement"></a>Konkurencja między wymaganiami dotyczącymi pamięci na potrzeby odświeżania zestawu danych i wymaganiami dotyczącymi pamięci aktywnego zestawu danych

Zestawy danych można odświeżać zgodnie z harmonogramem lub na żądanie użytkowników. Jak opisano wcześniej, pamięć wymagana do wykonania pełnych operacji odświeżania jest co najmniej dwukrotnie większa niż rozmiar pamięci załadowanych i pozostających w stanie bezczynności zestawów danych. Przed rozpoczęciem odświeżania jest szacowana wymagana wielkość pamięci. Jeśli całkowita wymagana pamięć jest większa niż pamięć dostępna w pojemności, niektóre zestawy danych są eksmitowane. Kandydaci do eksmisji są wybierani w kolejności najdawniej używanych zestawów danych tj. usługa próbuje zachować jak najwięcej ostatnio używanych zestawów danych w pamięci.

Jeśli mimo przeprowadzenia eksmisji wymagana pamięć jest niedostępna, operacja odświeżania jest umieszczana w kolejce w oczekiwaniu na ponowne podjęcie próby. Usługa ponawia próbę do momentu jej pomyślnego zakończenia lub rozpoczęcia nowej akcji odświeżania.

Jeśli zapytanie interaktywne jest tworzone dla dowolnego zestawu danych w ramach pojemności, a nie ma wystarczającej pamięci z powodu trwającego odświeżania, żądanie to kończy się niepowodzeniem i użytkownik musi podjąć kolejną próbę jego wykonania.

## <a name="cpu-resource-management-in-premium-capacity"></a>Zarządzanie zasobami procesora w ramach pojemności Premium

Istnieją dwa podstawowe elementy wykorzystujące zasoby procesora:

- Zapytania z raportów
- Odświeżanie (przetwarzanie)

### <a name="queries-from-reports"></a>Zapytania z raportów

Zapytania dotyczące raportów wykorzystują zasoby procesora w ramach pojemności. Jeśli raport zawiera zapytania, które są mało wydajne, lub jest używany współbieżnie przez wielu użytkowników, może zużywać duże ilości zasobów procesora, a istniejąca pojemność może być niewystarczająca do obsługi obciążenia.

### <a name="refresh-parallelization-policy"></a>Zasady równoległego przetwarzania odświeżania

Pamięć nie jest jedynym zasobem, który może ograniczać odświeżanie zestawów danych. Istotnym czynnikiem może być także liczba rdzeni wirtualnych na serwerze. Ponieważ każda operacja odświeżania wymaga określonej liczby rdzeni wirtualnych, istnieje limit liczby odświeżeń, które można uruchomić równolegle. Limity dla poszczególnych jednostek SKU zostały szczegółowo opisany w poniższej tabeli. Dodatkowe operacje odświeżania, które wykraczają poza te limity, są umieszczane w kolejce.

 | SKU  | Rdzenie wirtualne zaplecza  | Równoległość odświeżania modelu   |
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

Poniżej opisano kilka typowych scenariuszy i akcje wykonywane przez usługę:

 **Dwadzieścia zaplanowanych odświeżeń przesłanych jednocześnie** — usługa Power BI próbuje uruchomić pierwsze odświeżenia (*x*) jednocześnie. Wartość *x* jest określona w zasadach równoległego przetwarzania odświeżania dla danej jednostki SKU. Jeżeli usługa Power BI nie może uzyskać wystarczającej pamięci przez eksmisję nieaktywnych zestawów danych (zestawów danych ostatnio nieużywanych), nie wszystkie odświeżenia (*x*) zostaną uruchomione jednocześnie. Każde odświeżenie, którego nie można uruchomić, jest przechowywane w kolejce do momentu, gdy będzie ono możliwe.

 **Dwa odświeżenia uruchomione jednocześnie, w przypadku gdy wystarczy pamięci na zakończenie tylko jednego z nich** — uruchamiane jest to, które można zakończyć. Próba uruchomienia drugiej operacji zostanie ponowiona później.

 **Wiele zestawów danych jest uwzględnianych w zapytaniu, podczas gdy kilka zestawów danych jest odświeżanych** — jeśli nie ma wystarczającej ilości pamięci, usługa Power BI podejmuje próbę zatrzymania aktywnych odświeżeń, aby nadać priorytet zapytaniom interaktywnym. Spowoduje to obniżenie wydajności odświeżania.

 **Zestaw danych wymaga zbyt dużej ilości pamięci do odświeżenia przy bieżącym rozmiarze pojemności** — odświeżanie nie powiedzie się. Próby uzyskania większej ilości pamięci przez eksmisję nie są podejmowane.

 **Odświeżanie pojedynczego zestawu danych wymagającego zwiększonych zasobów pamięci**  — jeśli wzrost zasobów pamięci jest większy niż zasoby pamięci dostępne przez eksmisję nieaktywnych zestawów danych, próba odświeżenia zostanie ponowiona później, gdy będzie dostępna wystarczająca ilość pamięci do jej obsługi.

 **Zapytanie jest wykonywane dla zestawu danych, który nie może uzyskać wystarczającej ilości pamięci przez eksmitowanie wszystkich nieaktywnych zestawów danych i odświeżeń** — te zapytania kończą się niepowodzeniem. W przypadku takich wymagań dotyczących obciążeń należy zakupić większą pojemność.

## <a name="troubleshooting-and-testing"></a>Rozwiązywanie problemów i testowanie

Jeśli raporty działają wolno lub nie odpowiadają, należy uruchomić testowanie tylko dla jednego użytkownika w raporcie. Następnie należy rozpocząć zwiększanie obciążenia użytkowników współbieżnych w celu zidentyfikowania limitu. W wielu przypadkach dostrajanie języka DAX (zapytań dotyczących raportów) może znacząco zmienić wydajność raportów (i zwiększyć liczbę współbieżnych użytkowników obsługiwanych w ramach danej pojemności).

Użyj pojemności usługi Power BI Embedded na platformie Azure do testowania różnych jednostek SKU i określenia najlepszych jednostek SKU w warstwie Premium dla oczekiwanego obciążenia. Jednostka SKU usługi Power BI Embedded A4 jest odpowiednikiem wersji P1, A5 = P2 i A6 = P3. Na platformie Azure można łatwo przełączać się między jednostkami SKU przez skalowanie w górę i w dół w witrynie Azure Portal. Po znalezieniu jednostki SKU najlepiej odpowiadającej obciążeniu i zakończeniu testowania można usunąć jednostkę SKU.

W niektórych przypadkach otwarcie pliku PBIX modelu na komputerze oraz sprawdzenie pamięci i użycia procesora dostarcza wiele informacji o problemie. Nie jest to pomocne w przypadku bardzo dużych modeli, ale w przypadku niektórych mniejszych modeli można spróbować otworzyć i odświeżyć model z komputera, a także wykonać dotyczące go zapytania. Sprawdź rozmiar modelu, pamięć i użycie procesora po otwarciu modelu. Spróbuj odświeżyć i wykonać zapytanie. Za pomocą menedżera zadań można sprawdzić zużycie procesora i pamięci dla lokalnego pliku PBIX. Czasami na podstawie tych metryk na komputerze można ustalić, czy niższa pojemność Premium, taka jak P1/P2, będzie niewystarczająca dla danego rozwiązania.
