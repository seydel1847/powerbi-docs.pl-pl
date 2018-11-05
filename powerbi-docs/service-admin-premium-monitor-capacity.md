---
title: Monitorowanie pojemności usługi Power BI Premium w organizacji
description: Używanie portalu administracyjnego usługi Power BI i aplikacji metryk pojemności usługi Power BI Premium
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/09/2018
LocalizationGroup: Premium
ms.openlocfilehash: 2623dd3280636583d5dd6d6e3f57518550032193
ms.sourcegitcommit: 42475ac398358d2725f98228247b78aedb8cbc4f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003207"
---
# <a name="monitor-power-bi-premium-and-power-bi-embedded-capacities"></a>Monitorowanie pojemności w usługach Power BI Premium i Power BI Embedded

Ten artykuł zawiera omówienie monitorowania metryk pojemności usługi Power BI Premium. Monitorowanie użycia pojemności pozwala na świadomy wybór podejścia do zarządzania pojemnościami.

Pojemność można monitorować za pomocą aplikacji metryk pojemności lub portalu administracyjnego w usłudze Power BI Premium. Zalecamy użycie aplikacji, ponieważ oferuje ona o wiele więcej szczegółów, ale w tym artykule opisano obie opcje.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UgsjMbhi_Bk?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="install-the-premium-capacity-metrics-app"></a>Instalowanie aplikacji metryk pojemności usługi Premium

Można przejść bezpośrednio do [aplikacji metryk pojemności usługi Premium](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics) lub zainstalować ją tak jak inne aplikacje w usłudze Power BI.

1. W usłudze Power BI kliknij pozycję **Aplikacje**.

    ![Przechodzenie do pozycji Aplikacje](media/service-admin-premium-monitor-capacity/apps.png)

2. Po prawej stronie kliknij pozycję **Pobierz aplikacje**.

3. W kategorii **Aplikacje** wyszukaj **aplikację metryk pojemności usługi Power BI Premium**.

4. Subskrybuj, aby zainstalować aplikację.

Teraz, po zainstalowaniu aplikacji, będziesz widzieć metryki dotyczące pojemności w swojej organizacji. Przyjrzyjmy się niektórym dostępnym kluczowym metrykom.

## <a name="use-the-metrics-app"></a>Używanie aplikacji metryk

Po otwarciu aplikacji najpierw zostanie wyświetlony pulpit nawigacyjny z podsumowaniem wszystkich pojemności, do których masz uprawnienia administratora.

![Pulpit nawigacyjny aplikacji Metryki](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Raport składa się z trzech kart, które bardziej szczegółowo opisujemy w poniższych sekcjach.

* **Filtry stosowane do wszystkich stron**: umożliwia odfiltrowanie pozostałych stron w raporcie pod kątem określonej pojemności.
* **Zestawy danych**: dostarcza szczegółowe metryki dotyczące kondycji zestawów danych w ramach Twoich pojemności.
* **System**: zapewnia ogólne metryki wydajności, takie jak wysokie wykorzystanie pamięci i procesora. 

### <a name="filters-applied-to-all-pages-tab"></a>Karta Filtry stosowane do wszystkich stron

Na karcie **Filtry stosowane do wszystkich stron** możesz wybrać pojemność, zestaw danych i zakres dat w ciągu ostatnich siedmiu dni. Filtry zostaną następnie zastosowane do wszystkich odpowiednich stron i kafelków w raporcie. Jeśli nie zostaną wybrane żadne filtry, w raporcie będą domyślnie wyświetlane metryki z poprzedniego tygodnia dla każdej pojemności, która należy do Ciebie.

![Karta Filtry](media/service-admin-premium-monitor-capacity/filters-tab.png)

### <a name="datasets-tab"></a>Karta Zbiory danych

Na karcie **Zestawy danych** znajdują się zbiorcze metryki w aplikacji. Używając przycisków w górnej części karty, możesz przejść do różnych obszarów: **Podsumowanie**, **Odświeżenia**, **Czasy trwania zapytań**, **Oczekiwania zapytań** i **Zestawy danych**.

![Karta Zbiory danych](media/service-admin-premium-monitor-capacity/datasets-tab.png)

#### <a name="summary-area"></a>Obszar Podsumowanie

Obszar **Podsumowanie** przedstawia widok Twoich pojemności w oparciu o jednostki, zasoby systemowe i obciążenia zestawu danych.

| | **Metryki** |
| --- | --- |
| **Jednostki** | * Liczba pojemności, których jesteś właścicielem<br> * Odrębna liczba zestawów danych w pojemności<br> * Odrębna liczba obszarów roboczych w pojemności |
| **System** | * Średnie użycie pamięci w GB w ciągu ostatnich siedmiu dni<br> * Najwyższe zużycie pamięci w GB w ciągu ostatnich siedmiu dni oraz czas lokalny wystąpienia tego zużycia<br> * Liczba, która wskazuje, ile razy procesor przekroczył 80% progów w ciągu ostatnich siedmiu dni z podziałem na trzyminutowe przedziały<br> * Największa liczba przypadków, gdy procesor przekroczył 80% w ciągu ostatnich siedmiu dni z podziałem na przedziały o długości jednej godziny, oraz czas lokalny tych przypadków<br> * Liczba, która wskazuje, ile razy zapytania bezpośrednie/połączenia na żywo przekroczyły 80% progów w ciągu ostatnich siedmiu dni z podziałem na trzyminutowe przedziały<br> * Największa liczba przypadków, gdy zapytania bezpośrednie/połączenia na żywo przekroczyły 80% w ciągu ostatnich siedmiu dni z podziałem na przedziały o długości jednej godziny, oraz czas lokalny tych przypadków |
| **Obciążenia zestawu danych** | * Łączna liczba odświeżeń w ciągu ostatnich siedmiu dni<br> * Łączna liczba pomyślnych odświeżeń w ciągu ostatnich siedmiu dni<br> * Łączna liczba nieudanych odświeżeń w ciągu ostatnich siedmiu dni<br> * Łączna liczba odświeżeń nieudanych z powodu braku pamięci<br> * Średni czas trwania odświeżania jest mierzony w minutach, czas potrzebny do ukończenia operacji<br> * Średni czas oczekiwania na odświeżenie jest mierzony w minutach, średnie opóźnienie między zaplanowanym czasem i uruchomieniem operacji<br> * Łączna liczba zapytań uruchomionych w ciągu ostatnich siedmiu dni<br> * Łączna liczba pomyślnych zapytań w ciągu ostatnich siedmiu dni<br> * Łączna liczba nieudanych zapytań w ciągu ostatnich siedmiu dni<br> * Średni czas trwania zapytania jest mierzony w minutach, czas potrzebny do ukończenia operacji<br> * Łączna liczba modeli wykluczonych z powodu wykorzystania pamięci |
|  |  |

#### <a name="refreshes-area"></a>Obszar Odświeżenia

Obszar **Odświeżenia** zawiera listę ukończonych odświeżeń, miar powodzenia, średnich/maksymalnych czasów oczekiwania na odświeżenie i średnich/maksymalnych czasów trwania odświeżania. Lista ta jest podzielona na fragmenty według zestawów danych w ciągu ostatnich siedmiu dni. Dwa dolne wykresy przedstawiają porównanie odświeżeń z zużyciem w GB oraz średnimi czasami oczekiwania z podziałem na przedziały o długości jednej godziny w czasie lokalnym. Górne wykresy słupkowe zawierają listę pięciu najważniejszych zestawów danych według średniego czasu wymaganego do ukończenia odświeżania zestawu danych (czasu trwania odświeżania) oraz średniego czasu oczekiwania na odświeżenie. Wiele dużych wzrostów czasów oczekiwania na odświeżenie wskazuje na wyczerpywanie pojemności.

#### <a name="query-durations-area"></a>Obszar Czasy trwania zapytań

Obszar **Czasy trwania zapytań** zawiera łączną liczbę uruchomień zapytań oraz średni/maksymalny czas trwania w milisekundach. Te dane są dzielone na fragmenty według zestawów danych, obszaru roboczego i przedziałów godzinowych w ciągu ostatnich siedmiu dni. Dolny wykres przedstawia porównanie liczby zapytań i średniego czasu trwania (w milisekundach) z zużyciem pamięci w GB z podziałem na przedziały o długości jednej godziny w czasie lokalnym.

Prawy górny wykres przedstawia histogram rozkładu czasów trwania zapytań. Histogram jest podzielony według zgłoszonych czasów trwania zapytań w milisekundach na następujące kategorie: interwały o długości <= 30 ms, 30–100 ms, 100–300 ms, 300 ms–1 s, 1 s–3 s, 3 s–10 s, 10 s–30 s i > 30 s.

Prawy dolny wykres zawiera listę pięciu najważniejszych zestawów danych według średniego czasu trwania zapytania wymaganego do wykonania zapytań.

Długie czasy trwania zapytań i długie czasy oczekiwania wskazują na pojemności uruchomione w warstwie Gorąca. Mogą również oznaczać, że pojedynczy zestaw danych powoduje problemy i wymaga dalszych badań.

#### <a name="query-waits-area"></a>Obszar Oczekiwania zapytań

Obszar **Oczekiwania zapytań** zawiera łączną liczbę uruchomionych zapytań, łączną liczbę zapytań, licznik oczekiwania dla zapytań na żywo/zapytań bezpośrednich i średni/maksymalny czas oczekiwania zgłaszany w milisekundach. Te dane są dzielone na fragmenty według zestawów danych, obszaru roboczego i przedziałów godzinowych w ciągu ostatnich siedmiu dni. Dolny wykres przedstawia porównanie liczby oczekiwań zapytań i średniego czasu oczekiwania (w milisekundach) z zużyciem pamięci w GB z podziałem na przedziały o długości jednej godziny w czasie lokalnym.

Prawy górny wykres przedstawia histogram rozkładu czasów oczekiwania zapytań. Histogram jest podzielony według zgłoszonych czasów trwania zapytań w milisekundach na następujące kategorie: interwały o długości <= 50 ms, 50–100 ms, 100–200 ms, 200–400 ms, 400 ms–1 s, 1 s–5 s i > 5 s.

Prawy dolny wykres zawiera listę pięciu najważniejszych zestawów danych według średniego czasu oczekiwania wymaganego do uruchamiania zapytań.

#### <a name="datasets-area"></a>Obszar Zestawy danych

Obszar **Zestawy danych** przedstawia kompletne zestawy danych wykluczone z powodu dużego wykorzystania pamięci według godziny.

### <a name="system-tab"></a>Karta System

Karta **System** przedstawia liczbę przypadków wysokiego wykorzystania procesora (liczba przypadków przekroczenia 80% wykorzystania), wysokie wykorzystanie zapytań bezpośrednich/połączeń na żywo i zużycie pamięci.

![Raport systemu w usłudze Premium](media/service-admin-premium-monitor-capacity/system-tab.png)

## <a name="monitor-power-bi-embedded-capacity"></a>Monitorowanie pojemności usługi Power BI Embedded

Aplikacja metryk pojemności programu Power BI Premium służy również do monitorowania pojemności *jednostek SKU A* w usłudze Power BI Embedded. Te pojemności będą wyświetlane w raporcie, tak długo jak będziesz administratorem pojemności. Jednak odświeżanie raportu nie powiedzie się, chyba że udzielisz określonych uprawnień do usługi Power BI w ramach swoich jednostek SKU A:

1. Otwórz pojemność w witrynie Azure Portal.
1. Kliknij pozycję **Kontrola dostępu (Zarządzanie dostępem i tożsamościami)** i dodaj do roli czytelnika aplikację „Power BI Premium”. Jeśli nie możesz znaleźć aplikacji według nazwy, możesz również dodać ją przy użyciu jej identyfikatora klienta: cb4dc29f-0bf4-402a-8b30-7511498ed654.

    ![Uprawnienia do usługi Power BI Embedded](media/service-admin-premium-monitor-capacity/embedded-permissions.png)

> [!NOTE]
> Użycie pojemności usługi Power BI Embedded można monitorować w aplikacji lub w witrynie Azure Portal, ale nie w portalu administracyjnym usługi Power BI.

## <a name="basic-monitoring-in-the-admin-portal"></a>Podstawowe monitorowanie w portalu administracyjnym

Obszar **Ustawienia pojemności** w portalu administracyjnym udostępnia cztery mierniki, które wskazują obciążenia umieszczone w pojemności i zasoby wykorzystywane przez tę pojemność w ciągu ostatnich siedmiu dni. Te cztery kafelki działają w godzinowym przedziale czasu, który wskazuje liczbę godzin w ciągu ostatnich siedmiu dni, gdy odpowiednia metryka przekroczyła wartość 80%. Ta metryka wskazuje potencjalne obniżenie wydajności środowiska użytkownika końcowego.

![Użycie w ciągu 7 dni](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **Metryka** | **Opis** |
| --- | --- |
| Procesor CPU |Ile razy wykorzystanie procesora CPU przekroczyło 80%. |
| Przeładowywanie pamięci |Reprezentuje wykorzystanie pamięci rdzeni wewnętrznej bazy danych. Ta metryka w szczególności obrazuje, ile razy zestawy danych zostały usunięte z pamięci z powodu braku pamięci wynikającego z używania wielu zestawów danych. |
| Memory Usage (Użycie pamięci) |Średnie użycie pamięci przedstawiane w gigabajtach (GB). |
| Zapytania bezpośrednie | Ile razy liczba zapytań bezpośrednich i połączeń na żywo przekroczyła 80% limitu. <br> * Łączna liczba zapytań w trybie DirectQuery i zapytań w ramach połączeń na żywo występujących w ciągu sekundy jest ograniczona. * Limity wynoszą 30/s (P1), 60/s (P2) i 120/s (P3). * Liczba zapytań bezpośrednich i zapytań w ramach połączeń na żywo wlicza się do powyższych limitów. Na przykład, jeśli w ciągu sekundy wystąpiło 15 zapytań bezpośrednich i 15 połączeń na żywo, limit został osiągnięty.<br>* Ma to jednakowe zastosowanie się do połączeń lokalnych i połączeń w chmurze. |
|  |  |

Metryki odzwierciedlają wykorzystanie w ostatnim tygodniu.  Jeśli chcesz wyświetlić bardziej szczegółowy widok metryki, możesz to zrobić, klikając dowolny kafelek podsumowania.  Spowoduje to przejście do szczegółowych wykresów dla każdej metryki Twojej pojemności Premium. Na poniższym wykresie przedstawiono szczegółowe informacje dotyczące metryki procesora.

![Szczegółowy wykres użycia procesora CPU](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

Wykresy te są podsumowywane co godzinę dla ostatniego tygodnia i mogą pomóc określić, kiedy w Twojej pojemności Premium mogły wystąpić określone zdarzenia dotyczące wydajności.

Dane źródłowe dla dowolnej metryki można wyeksportować do pliku csv.  Dzięki temu uzyskasz szczegółowe informacje w przedziałach trzyminutowych dla poszczególnych dni w ostatnim tygodniu.

## <a name="next-steps"></a>Następne kroki

Teraz, gdy już znasz sposób monitorowania pojemności usługi Power BI Premium, dowiedz się więcej na temat optymalizowania pojemności.

> [!div class="nextstepaction"]
> [Optymalizacja zasobów o pojemności Power BI Premium i zarządzanie nimi](service-premium-understand-how-it-works.md)
