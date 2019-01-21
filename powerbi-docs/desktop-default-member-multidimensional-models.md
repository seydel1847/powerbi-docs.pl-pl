---
title: Domyślny element członkowski wielowymiarowych modeli w usłudze Power BI
description: Dowiedz się, jak usługa Power BI zachowuje się podczas pracy z domyślnymi elementami członkowskimi w modelach wielowymiarowych
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/10/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 01b0cdf70c985169d474a130ed4ad846ad708963
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284753"
---
# <a name="default-member-in-multidimensional-models-in-power-bi"></a>Domyślny element członkowski wielowymiarowych modeli w usłudze Power BI

Można nawiązywać połączenie z modelami wielowymiarowymi w usłudze Power BI i tworzyć raporty, które wizualizują wszystkie rodzaje danych w modelu. Podczas pracy z modelami wielowymiarowymi usługa Power BI stosuje reguły do sposobu przetwarzania danych na podstawie kolumny zdefiniowanej jako *domyślny element członkowski*. 

Podczas pracy z modelami wielowymiarowymi usługa Power BI obsługuje dane z modelu na podstawie miejsca użycia kolumny, która zawiera element **DefaultMember**. Atrybut *DefaultMember* jest ustawiany w języku CSDL (Conceptual Schema Definition Language, język definicji schematu koncepcyjnego) dla określonej kolumny w modelu wielowymiarowym. Dowiedz się więcej o domyślnym elemencie członkowskim z [artykułu dotyczącego właściwości atrybutów](https://docs.microsoft.com/sql/analysis-services/multidimensional-models/attribute-properties-define-a-default-member?view=sql-server-2017). Podczas wykonywania zapytania w języku DAX domyślny element członkowski określony w modelu jest stosowany automatycznie.

W tym artykule przedstawiono, jak usługa Power BI zachowuje się w różnych okolicznościach podczas pracy z modelami wielowymiarowymi, w zależności od tego, gdzie znaleziono *domyślny element członkowski*. 

## <a name="working-with-filter-cards"></a>Praca z kartami filtrów

Podczas tworzenia karty filtru w polu z domyślnym elementem członkowskim wartość domyślna pola elementu członkowskiego jest wybierana automatycznie na karcie filtru. W wyniku wszystkie wizualizacje, na które wpływa karta filtru, zachowują swoje modele domyślne w bazie danych. Wartości na takich kartach filtrów odzwierciedlają ten domyślny element członkowski.

Jeśli domyślny element członkowski zostanie usunięty, anulowanie wyboru wartości powoduje wyczyszczenie jej we wszystkich wizualizacjach, w których karta filtru ma zastosowanie, a wyświetlane wartości nie odzwierciedlają domyślnego elementu członkowskiego.

Na przykład załóżmy, że mamy kolumnę *Waluta*, która ma domyślny element członkowski ustawiony na *USD*:

* W tym przypadku, jeśli będziemy mieć kartę przedstawiającą wartość *Łączna sprzedaż*, do wartości zostanie zastosowany domyślny element członkowski i zobaczymy sprzedaż odpowiadającą walucie „USD”.
* Jeśli przeciągniemy kolumnę *Waluta* do okienka karty filtru, zobaczymy, że waluta *USD* została wybrana jako domyślna. Wartość *Łączna sprzedaż* pozostanie taka sama, ponieważ będzie stosowany domyślny element członkowski.
* Jednak jeśli usuniemy zaznaczenie wartości *USD* z karty filtru, domyślny element członkowski kolumny *Waluta* zostanie wyczyszczony, a wartość *Łączna sprzedaż* będzie odzwierciedlać wszystkie waluty.
* W rezultacie po wybraniu innej wartości na karcie filtru (na przykład wartości *EURO*), oraz domyślnego elementu członkowskiego, wartość *Łączna sprzedaż* odzwierciedla filtr *Waluta IN {USD, EURO}*.

## <a name="grouping-behavior"></a>Zachowanie grupowania

W usłudze Power BI każde grupowanie wizualizacji na podstawie kolumny, która ma *domyślny element członkowski*, powoduje wyczyszczenie w usłudze Power BI *domyślnego elementu członkowskiego* dla tej kolumny oraz odpowiedniej ścieżki relacji atrybutów. Gwarantuje to, że w wizualizacji będą wyświetlane wszystkie wartości, a nie tylko wartości domyślne.

## <a name="attribute-relationship-paths-arps"></a>Ścieżki relacji atrybutów (ARP, Attribute relationship path)

Ścieżki relacji atrybutów (ARP) udostępniają *domyślne elementy członkowskie* z zaawansowanymi funkcjami, ale również wprowadzają pewien stopień złożoności. Po napotkaniu ścieżek ARP usługa Power BI używa ich do wyczyszczenia dodatkowych domyślnych elementów członkowskich dla innych kolumn w celu zapewnienia spójnego i dokładnego sposobu obsługi danych w wizualizacjach.

Zapoznajmy się z przykładem, aby dokładniej objaśnić zachowanie. Weźmy pod uwagę następującą konfigurację ścieżek ARP:

![Ścieżki ARP w modelu wielowymiarowym](media/desktop-default-member-multidimensional-models/default-members_01.png)

Załóżmy teraz, że ustawiono *domyślne elementy członkowskie* dla następujących kolumn:

* Miasto > Seattle
* Stan > WA
* Kraj > USA
* Populacja > Duża

Sprawdźmy teraz, co się stanie w przypadku użycia każdej z tych kolumn w usłudze Power BI. Poniżej przedstawiono wyniki grupowania wizualizacji w oparciu o poszczególne kolumny:

* **Miasto** — usługa Power BI wyświetla wszystkie miasta, czyszcząc wszystkie **domyślne elementy członkowskie** kolumn *Miasto*, *Stan* i *Kraj*, ale zachowuje **domyślny element członkowski** kolumny *Populacja*; usługa Power BI wyczyściła całą ścieżkę ARP dla kolumny *Miasto*.
    > [!NOTE]
    > Kolumna *Populacja* nie znajduje się na ścieżce ARP kolumny *Miasto*. Jest ona powiązana wyłącznie z kolumną *Stan* i dlatego usługa Power BI jej nie czyści.
* **Stan** — usługa Power BI wyświetla wszystkie *stany*, czyszcząc wszystkie **domyślne elementy członkowskie** kolumn *Miasto*, *Stan*, *Kraj* i *Populacja*.
* **Kraj** — usługa Power BI wyświetla wszystkie kraje, czyszcząc wszystkie **domyślne elementy członkowskie** kolumn *Miasto*, *Stan* i *Kraj*, ale zachowuje **domyślny element członkowski** kolumny *Populacja*.
* **Miasto i stan** — usługa Power BI czyści wszystkie **domyślne elementy członkowskie** wszystkich kolumn.

Grupy wyświetlane w wizualizacji mają wyczyszczoną całą ścieżkę ARP. 

Jeśli grupa nie jest wyświetlana w wizualizacji, ale jest częścią ścieżki ARP innej pogrupowanej kolumny, mają zastosowanie następujące reguły:

* Nie wszystkie gałęzie ścieżki ARP są czyszczone automatycznie.
* Grupa jest nadal filtrowana według niewyczyszczonego **domyślnego elementu członkowskiego**.

### <a name="slicers-and-filter-cards"></a>Fragmentatory i karty filtrów

W przypadku pracy z fragmentatorami lub kartami filtrów występuje następujące zachowanie:

* Po załadowaniu danych do fragmentatora lub filtru karty usługa Power BI przeprowadza grupowanie w wizualizacji na podstawie kolumny, dlatego zachowanie wyświetlania jest zgodne z opisem w poprzedniej sekcji.

Ponieważ fragmentatory i karty filtrów są często używane do interakcji z innymi wizualizacjami, logika czyszczenia **domyślnych elementów członkowskich** w uwzględnionych wizualizacjach działa zgodnie z opisem w poniższej tabeli. 

W tej tabeli korzystamy z przykładowych danych używanych wcześniejszej w tym artykule:

![Zachowanie funkcji czyszczenia domyślnego elementu członkowskiego usługi Power BI z użyciem fragmentatorów i kart filtrów](media/desktop-default-member-multidimensional-models/default-members_02.png)

W takich okolicznościach obowiązują następujące reguły dotyczące zachowania usługi Power BI.

Usługa Power BI czyści **domyślny element członkowski** dla danej kolumny, jeśli:

* Usługa Power BI grupuje według tej kolumny
* Usługa Power BI grupuje według kolumny powiązanej z tą kolumną (w dowolnym miejscu ścieżki ARP, w górę lub w dół)
* Usługa Power BI filtruje według kolumny znajdującej się na ścieżce ARP (w górę lub w dół)
* Kolumna ma kartę filtru ze stanem *WSZYSTKIE*
* Kolumna ma kartę filtru z dowolną wybraną wartością (usługa Power BI otrzymuje filtr dla kolumny)

Usługa Power BI nie czyści **domyślnego elementu członkowskiego** dla danej kolumny, jeśli:

* Kolumna ma kartę filtru ze stanem domyślnym, a usługa Power BI grupuje według kolumny w obrębie ścieżki ARP.
* Kolumna znajduje się powyżej innej kolumny na ścieżce ARP, a usługa Power BI ma kartę filtru dla innej kolumny w stanie domyślnym.


## <a name="next-steps"></a>Następne kroki

W tym artykule opisano zachowanie usługi Power BI podczas pracy z domyślnymi elementami członkowskimi w modelach wielowymiarowych. Może zainteresują Cię również następujące artykuły: 

* [Pokazywanie elementów bez danych w usłudze Power BI](desktop-show-items-no-data.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
