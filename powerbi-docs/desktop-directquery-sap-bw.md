---
title: Zapytanie bezpośrednie i system SAP Business Warehouse (BW) w usłudze Power BI
description: Zagadnienia dotyczące korzystania z zapytania bezpośredniego w systemie SAP Business Warehouse (BW)
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 03/07/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a8fde13b0beeb57fb5d25aa35002358f04ab6cad
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="directquery-and-sap-business-warehouse-bw"></a>Zapytanie bezpośrednie i system SAP Business Warehouse (BW)
Dzięki **zapytaniu bezpośredniemu** można połączyć się bezpośrednio ze źródłami danych systemu **SAP Business Warehouse (BW)**. Ponieważ system SAP BW jest źródłem danych OLAP (wielowymiarowym), korzystanie z zapytania bezpośredniego dla źródeł danych SAP BW różni się istotnie od korzystania z niego dla źródeł relacyjnych, takich jak program SQL Server. Te różnice można podsumować w następujący sposób:

* W przypadku korzystania z **zapytania bezpośredniego** dla relacyjnego źródła danych używany jest zestaw zapytań (zdefiniowanych w oknie dialogowym**Pobieranie danych** lub **Edytor zapytań**) logicznie definiujących dane dostępne na liście pól. *Nie jest* tak w przypadku nawiązywania połączenia ze źródłem danych OLAP, takim jak SAP BW. Zamiast tego podczas nawiązywania połączenia z serwerem SAP przy użyciu opcji **Pobierz dane** zaznaczone jest tylko zapytanie Infocube lub BEx. Wtedy wszystkie kluczowe wartości i wymiary z wybranego zapytania Infocube/BEx są dostępne na liście pól.   
* Podczas nawiązywania połączenia z systemem SAP BW nie jest również używany **Edytor zapytań**. Ustawienia źródła danych (na przykład nazwa serwera) można zmienić, wybierając kolejno pozycje **Edytuj zapytania > Ustawienia źródła danych**. Ustawienia dowolnych parametrów można zmienić, wybierając pozycje **Edytuj zapytania > Zarządzaj parametrami**.
* Ze względu na unikatowy charakter źródeł danych OLAP, oprócz normalnych ograniczeń dotyczących zapytań bezpośrednich, istnieją dodatkowe ograniczenia (zarówno w przypadku modelowania, jak i wizualizacji). Ograniczenia te zostały opisane w dalszej części tego artykułu.

Ponadto *bardzo ważna* jest świadomość, że wiele funkcji systemu SAP BW nie jest obsługiwanych w usłudze Power BI, i że cechy publicznego interfejsu systemu SAP BW powodują, że w pewnych istotnych przypadkach wyniki widoczne w usłudze Power BI nie będą zgodne z tymi wyświetlanymi podczas korzystania z narzędzia SAP. Te ograniczenia są opisane w dalszej części tego artykułu. Należy zapoznać się dokładnie z tymi ograniczeniami i różnicami w działaniu, aby mieć pewność, że wyniki widoczne w usłudze Power BI, zwrócone przez interfejs publiczny SAP, będą interpretowane prawidłowo.  

> [!NOTE]
> Możliwość używania zapytania bezpośredniego za pośrednictwem programu SAP BW była w wersji zapoznawczej do czasu wydania aktualizacji programu Power BI Desktop w marcu 2018 r. W wersji zapoznawczej opinie i sugerowane ulepszenia wywoływały zmianę, która miała wpływ na raporty utworzone za pomocą tej wersji zapoznawczej. Teraz, gdy zapytania bezpośrednie za pośrednictwem programu SAP BW stały się ogólnie dostępne (wersja GA), *konieczne jest* usunięcie wszystkich istniejących (opartych na wersji zapoznawczej) raportów korzystających z zapytań bezpośrednich za pośrednictwem programu SAP BW, które zostały utworzone w wersji wcześniejszej niż GA. W raportach utworzonych przy użyciu zapytań bezpośrednich za pośrednictwem programu SAP BW w wersji wcześniejszej niż GA będą występowały błędy podczas odświeżania, ponieważ nastąpi próba odświeżenia metadanych ze zmienionym bazowym modułem programu SAP BW. Należy ponownie utworzyć te raporty, bazując na pustym raporcie, przy użyciu zapytań bezpośrednich za pośrednictwem programu SAP BW w wersji ogólnie dostępnej (GA). 

## <a name="additional-modeling-restrictions"></a>Dodatkowe ograniczenia modelowania
Najważniejsze dodatkowe ograniczenia dotyczące modelowania w przypadku nawiązywania połączenia z systemem SAP BW przy użyciu zapytania bezpośredniego w usłudze Power BI są następujące:

* **Brak obsługi kolumn obliczeniowych:** Możliwość tworzenia kolumn obliczeniowych jest wyłączona. Oznacza to również, że funkcje grupowania i klastrowania, które tworzą kolumny obliczeniowe, nie są dostępne.
* **Dodatkowe ograniczenia dotyczące miar:** Istnieją dodatkowe ograniczenia dotyczące wyrażeń języka DAX, które mogą zostać użyte w miarach, odzwierciedlające poziom obsługi oferowany przez system SAP BW.
* **Brak obsługi definiowania relacji:** Relacje są integralną częścią zewnętrznego źródła danych SAP, dlatego nie można definiować dodatkowych relacji w modelu.
* **Brak widoku danych:** W **widoku danych** zwykle są wyświetlane szczegółowe dane tabel. Ze względu na charakter źródeł OLAP, takich jak system SAP BW, ten widok nie jest dostępny w przypadku połączenia z systemem SAP BW.
* **Stałe szczegóły kolumn i miar:** Lista kolumn i miar na liście pól jest ustalana przez bazowe źródło danych i nie można jej zmienić. Nie można na przykład usunąć kolumny ani zmienić typu danych (można jednak zmienić jej nazwę).
* **Dodatkowe ograniczenia dotyczące języka DAX:** Istnieją dodatkowe ograniczenia dotyczące wyrażeń języka DAX, które mogą zostać użyte w definicjach miar, odzwierciedlające ograniczenia w źródle. Nie można na przykład zastosować funkcji agregującej do tabeli.

## <a name="additional-visualization-restrictions"></a>Dodatkowe ograniczenia wizualizacji
Najważniejsze dodatkowe ograniczenie dotyczące wizualizacji w przypadku nawiązywania połączenia z systemem SAP BW przy użyciu zapytania bezpośredniego w usłudze Power BI są następujące:

* **Brak agregacji kolumn:** Nie można zmienić sposobu agregacji kolumny w wizualizacji — zawsze jest to opcja *Nie sumuj*.
* **Wyłączone filtrowanie miar:** Filtrowanie miar jest wyłączone, co odzwierciedla obsługę oferowaną przez system SAP BW.
* **Wybór wielokrotny i opcja dołączania/wykluczania:** Możliwość wielokrotnego wyboru punktów danych w wizualizacji jest wyłączona, jeśli punkty przedstawiają wartości z więcej niż jednej kolumny. Na przykład gdy wykres słupkowy przedstawia sprzedaż według kraju z legendą zawierającą kategorie, wybranie punktów (USA, rowery) i (Francja, odzież) nie jest możliwe. Podobnie nie jest możliwe wybranie punktu (USA, rowery) i wykluczenie go z wizualizacji. Oba ograniczenia odzwierciedlają obsługę oferowaną przez system SAP BW.

## <a name="support-for-sap-bw-features"></a>Obsługa funkcji systemu SAP BW
Poniższa tabela zawiera listę wszystkich funkcji systemu SAP BW, które nie są w pełni obsługiwane lub działają inaczej w przypadku korzystania z usługi Power BI.   

| Funkcja | Opis |
| --- | --- |
| Obliczenia lokalne |Obliczenia lokalne zdefiniowane w zapytaniu BEx zmienią liczby wyświetlane za pomocą takich narzędzi jak BEx Analyzer. Nie są one jednak odzwierciedlane w liczbach zwracanych z systemu SAP za pośrednictwem publicznego interfejsu MDX. <br/> <br/> **Dlatego liczby wyświetlane w wizualizacji usługi Power BI mogą różnić się od tych w odpowiedniej wizualizacji w narzędziu SAP.**<br/> <br/>  Na przykład podczas nawiązywania połączenia z modułem zapytania z zapytania BEx, w przypadku wybrania typu agregacji Skumulowane (tzn. suma bieżąca), usługa Power BI zwróci bazowe liczby, ignorując to ustawienie.  Analityk może zastosować obliczenia sum bieżących lokalnie w usłudze Power BI, ale musi zachować ostrożność podczas interpretowania liczb, jeśli nie zostanie to zrobione. |
| Agregacje |W niektórych przypadkach (zwłaszcza gdy mamy do czynienia z wieloma walutami) liczby zagregowane zwracane przez interfejs publiczny systemu SAP nie są zgodne z tymi wyświetlanymi przez narzędzia SAP. <br/> <br/> **Dlatego liczby wyświetlane w wizualizacji usługi Power BI mogą różnić się od tych w odpowiedniej wizualizacji w narzędziu SAP.** <br/> <br/> Na przykład sumy w różnych walutach są wyświetlane jako „*” w narzędziu BEx Analyzer, ale suma zwrócona przez interfejs publiczny systemu SAP nie ma już żadnej informacji, że taka zagregowana liczba jest bez znaczenia. Taka sama liczba jest następnie wyświetlana w usłudze Power BI (na przykład suma wartości w USD, EUR i AUD). |
| Formatowanie waluty |Formatowanie waluty (na przykład $2 300 lub 4000 AUD) nie jest widoczne w usłudze Power BI. |
| Jednostki miary |Jednostki miary (na przykład 230 kg) nie są widoczne w usłudze Power BI. |
| Klucz a tekst (krótki, średni, długi) |W przypadku cech z systemu SAP BW, takich jak CentrumKosztów, lista pól jest wyświetlana jako pojedyncza kolumna Centrum kosztów.  Użycie tej kolumny spowoduje wyświetlenie domyślnego tekstu.  Pokazanie ukrytych pól umożliwi również wyświetlenie kolumny unikatowej nazwy (która zwraca unikatową nazwę przypisaną przez system SAP BW będącą podstawą unikatowości).<br/> <br/>  Klucz i inne pola tekstowe nie są dostępne. |
| Wiele hierarchii cechy |W systemie **SAP** cecha może mieć wiele hierarchii. Wtedy w narzędziach takich jak BEx Analyzer, gdy ta cecha jest uwzględniona w zapytaniu, użytkownik może wybrać hierarchię, którą chce użyć. <br/> <br/> W usłudze **Power BI** różne hierarchie są widoczne na liście pól jako różne hierarchie tego samego wymiaru.  Jednak wybranie wielu poziomów z dwóch różnych hierarchii tego samego wymiaru doprowadzi do zwrócenia pustych danych przez system SAP. |
| Obsługa niewyrównanych hierarchii |![](media/desktop-directquery-sap-bw/directquery-sap-bw_01.png) |
| Współczynnik skalowania/odwrócony znak |W systemie SAP kluczowa wartość może mieć współczynnik skalowania (na przykład 1000) zdefiniowany jako opcja formatowania, co oznacza, że cała wyświetlana treść będzie skalowana o ten współczynnik. <br/> <br/> Może mieć również ustawioną właściwość, która powoduje odwrócenie znaku. Skorzystanie z takich kluczowych wartości w usłudze Power BI (w wizualizacji lub w ramach obliczeń) spowoduje użycie nieskalowanej liczby (a znak nie zostanie odwrócony). Bazowy współczynnik skalowania nie jest dostępny. W wizualizacjach usługi Power BI jednostki skalowania wyświetlane na osi (K, M, B) można określać w ramach formatowania wizualizacji. |
| Hierarchie, w których poziomy są wyświetlane/ukrywane dynamicznie |Podczas początkowego nawiązywania połączenia z systemem SAP BW pobierane są informacje dotyczące poziomów hierarchii, co powoduje wyświetlenie zestawu pól na liście pól. Te informacje są buforowane, dlatego jeśli zestaw poziomów zmieni się, to zestaw pól zostanie zmieniony dopiero po wywołaniu polecenia Odśwież. <br/> <br/> Można to zrobić wyłącznie w programie **Power BI Desktop**. Wywołanie polecenia Odśwież w celu odzwierciedlenia zmian poziomów nie może nastąpić w usłudze Power BI po opublikowaniu. |
| Domyślny filtr |Zapytanie BEx może obejmować domyślne filtry, które zostaną zastosowane automatycznie przez narzędzie SAP BEx Analyzer. Nie są one widoczne, dlatego użycie takiego samego zapytania w usłudze Power BI nie spowoduje domyślnie zastosowania tych samych filtrów. |
| Ukryte wartości kluczowe |W zapytaniu BEx można kontrolować widoczność wartości kluczowych, a ukryte wartości nie będą widoczne w narzędziu SAP BEx Analyzer. Nie jest to odzwierciedlane przez publiczny interfejs API, dlatego ukryte wartości kluczowe nadal będą widoczne na liście pól. Można jednak je ukryć w usłudze Power BI. |
| Formatowanie liczb |Formatowanie liczb (liczba miejsc dziesiętnych, punkt dziesiętny itp.) nie zostanie automatycznie odzwierciedlone w usłudze Power BI. Można jednak później określić takie formatowanie w usłudze Power BI. |
| Przechowywanie wersji hierarchii |System SAP BW umożliwia przechowywanie różnych wersji hierarchii, na przykład hierarchii Centrum kosztów na rok 2007 oraz 2008. Tylko najnowsza wersja będzie dostępna w usłudze Power BI, ponieważ informacje dotyczące wersji nie są udostępniane przez publiczny interfejs API. |
| Hierarchie zależne od czasu |Podczas korzystania z usługi Power BI hierarchie zależne od czasu są obliczane według bieżącej daty. |
| Przeliczanie walut |System SAP BW obsługuje przeliczanie walut na podstawie kursów przechowywanych w module. Takich możliwości nie ma w publicznym interfejsie API, a w związku z tym są niedostępne w usłudze Power BI. |
| Kolejność sortowania |W systemie SAP można zdefiniować kolejność sortowania cechy (według tekstu lub klucza). Ta kolejność sortowania nie jest jednak uwzględniana w usłudze Power BI. Na przykład miesiące mogą być wyświetlane w kolejności „Czerwiec”, „Kwiecień” itd. <br/> <br/> W usłudze Power BI nie można zmienić takiej kolejności sortowania. |
| Nazwy techniczne |W obszarze **Pobierz dane** są widoczne nazwy (opisy) cech/miar i nazwy techniczne. Lista pól będzie zawierać wyłącznie nazwy cech/miar (opisy). |
| Atrybuty |W usłudze Power BI nie można uzyskać dostępu do atrybutów cechy. |
| Ustawienia języka użytkownika końcowego |Ustawienia regionalne używane do nawiązania połączenia z systemem SAP BW stanowią część szczegółów połączenia i nie odzwierciedlają ustawień regionalnych końcowego użytkownika raportu. |
| Zmienne tekstowe |W systemie SAP BW nazwy pól mogą zawierać symbole zastępcze dla zmiennych (na przykład „Wartości rzeczywiste $YEAR$”), które będą następnie zastępowane przez wybraną wartość. Na przykład jeśli dla zmiennej wybrano rok 2016, odpowiednie pole jest wyświetlane jako „Wartości rzeczywiste 2016” w narzędziach BEx. <br/> <br/> Nazwa kolumny w usłudze Power BI nie zmieni się w zależności od wartości zmiennej, a w związku z tym zostanie wyświetlona jako „Wartości rzeczywiste $YEAR$”.  Nazwę kolumny można jednak zmienić w usłudze Power BI. |
| Zmienne wyjściowe klienta | Zmienne wyjściowe klienta nie są ujawniane w publicznym interfejsie API, w związku z czym nie są obsługiwane przez usługę Power BI. |
| Charakterystyczne struktury | Wszelkie charakterystyczne struktury w podstawowym źródle SAP BW spowodują ujawnienie zwiększonej ilości miar w usłudze Power BI. Na przykład w przypadku dwóch miar Sales i Costs oraz charakterystycznej struktury obejmującej miary Budget i Actual zostaną ujawnione cztery miary: Sales.Budget, Sales.Actual, Costs.Budget, Costs.Actual. |


## <a name="next-steps"></a>Następne kroki
Aby uzyskać więcej informacji na temat zapytania bezpośredniego, zapoznaj się z następującymi zasobami:

* [Zapytanie bezpośrednie w usłudze Power BI](desktop-directquery-about.md)
* [Źródła danych obsługiwane przez zapytanie bezpośrednie](desktop-directquery-data-sources.md)
* [Zapytanie bezpośrednie i platforma SAP HANA](desktop-directquery-sap-hana.md)

