---
title: Pokazywanie elementów bez danych w usłudze Power BI
description: Dowiedz się, jak usługa Power BI obsługuje i wyświetla elementy bez danych
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/03/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: a687e42ef2963ce5e85bd1e0be72c2562afa5b6c
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279992"
---
# <a name="show-items-with-no-data-in-power-bi"></a>Pokazywanie elementów bez danych w usłudze Power BI

Usługa Power BI umożliwia wizualizowanie wszelkiego rodzaju danych z różnych źródeł. Podczas tworzenia wizualizacji usługa Power BI wyświetla tylko odpowiednie dane, co umożliwia prawidłowe zarządzanie sposobem przedstawiania i wyświetlania tych danych. Usługa Power BI wybiera odpowiednie dane na podstawie konfiguracji wizualizacji oraz podstawowego modelu danych. W tym artykule opisano zachowanie usługi Power BI podczas określania odpowiednich danych oraz przedstawiono przykłady ilustrujące sposób dokonywania takich wyborów.

![Jak włączyć funkcję Pokaż elementy bez danych](media/desktop-show-items-no-data/show-items-no-data_02.png)

## <a name="determining-relevant-data"></a>Określanie odpowiednich danych

Aby rozpocząć pracę i zrozumieć, jak usługa Power BI określa odpowiednie dane do wyświetlenia, przyjrzyjmy się przykładowej, prostej tabeli. Używając modelu reprezentowanego w sekcji przykładów na końcu tego artykułu, należy wziąć pod uwagę utworzenie tabeli z następującymi ustawieniami:

**1. Grupy z tej samej tabeli:** *Product[Color] — Product[Size]*

|*Product[Color]*  |*Product[Size]*  |
|---------|---------|
|Niebieski     |Duży         |
|Niebieski     |Średni         |
|Niebieski     |Mały         |
|Red     |Duży         |

W tym przykładzie usługa Power BI wyświetla kombinacje elementów *[Color-Size]* znajdujące się w tabeli *[Product]*. 

Teraz przyjrzyjmy się innej kombinacji:

**2. Grupy z różnych, ale bezpośrednio powiązanych tabel, i miara:** *ProductStyle[Finish] - Product[Color] - Sum(Sales[Quantity])*

|*ProductStyle[Finish]*  |*Product[Color]*  |*[SumQuantity]*  |
|---------|---------|---------|
|Połysk     |Niebieski         |10         |
|Matowe     |Niebieski         |15         |

W tym przykładzie usługa Power BI wyświetla tylko te kombinacje, które istnieją. Na przykład kombinacje nie będą wyświetlane („Brak” + „Niebieski”) lub („Matowe” + „Czerwone”), ponieważ nie istnieją w modelu. Warunek określający, które kombinacje istnieją, jest niepustą wartością elementu *Sum(Sales[Quantity])*.

Teraz przyjrzyjmy się innemu przypadkowi: 

**3. Grupy z różnych, ale powiązanych tabel, bez miary:** *ProductStyle[Finish] — Product[Color]*

|*ProductStyle[Finish]*  |*Product[Color]*  |
|---------|---------|
|Połysk     |Niebieski         |
|Połysk     |Red         |
|Matowe     |Niebieski         |

Ponieważ nie ma jawnej miary, a dwie tabele są bezpośrednio powiązane, usługa Power BI próbuje wstrzyknąć miarę w celu ograniczenia wynikowych kombinacji. W tym przypadku usługa Power BI wstrzykuje miarę *CALCULATE(COUNTROWS(„Product”))*, która nie powinna być pusta, ponieważ tabela *Product* jest wspólna dla obu tabel.

W efekcie usługa Power BI wyświetla kombinacje, które mają wpisy w tabeli Product, co wyklucza kombinacje *(„Brak” + „Niebieski”)* i *(„Matowe” + „Czerwony”)*.

**4. Grupy z różnych i niepowiązanych tabel**

Przykładowy model nie ma tej kombinacji, ale w przypadku grup z różnych i niepowiązanych tabel usługa Power BI nie może utworzyć powiązania między kolumnami. Wynikiem jest sprzężenie krzyżowe wszystkich wartości poszczególnych kolumn. W tej sytuacji usługa Power BI generuje błąd typu *nieograniczone sprzężenie*, ponieważ takie sprzężenia krzyżowe są drogie do obliczenia w bazie danych i nie oferują użytkownikowi wielu informacji. 

![Błąd pokazywany w przypadku nieograniczonego sprzężenia](media/desktop-show-items-no-data/show-items-no-data_01.png)


## <a name="showing-items-with-no-data"></a>Pokazywanie elementów bez danych

W poprzedniej sekcji opisano sposób wybierania odpowiednich danych do wyświetlenia przez usługę Power BI. Ale w niektórych przypadkach *chcesz* pokazać elementy bez danych. 

Funkcja **Pokaż elementy bez danych** umożliwia wykonanie właśnie tej czynności — uwzględnienia wierszy i kolumn danych, które nie zawierają danych miar (puste wartości miar).

Aby włączyć funkcję **Pokaż elementy bez danych**, wybierz wizualizację, a następnie w zasobniku **Pola** kliknij prawym przyciskiem myszy pole i z wyświetlonego menu wybierz pozycję **Pokaż elementy bez danych**, jak pokazano na poniższej ilustracji:

![Jak włączyć funkcję Pokaż elementy bez danych](media/desktop-show-items-no-data/show-items-no-data_02.png)


Funkcja **Pokaż elementy bez danych** *nie* przynosi efektów w następujących okolicznościach:

* Do wizualizacji nie dodano miar, a kolumny grupowania pochodzą z tej samej tabeli
* Grupy nie są powiązane; usługa Power BI nie uruchamia zapytań dotyczących wizualizacji z nie powiązanymi grupami
* Miara nie jest powiązana z żadną grupą; dzieje się tak, ponieważ miara nigdy nie będzie pusta w przypadku tylko niektórych kombinacji grup
* Istnieje zdefiniowany przez użytkownika filtr miar, który wyklucza miary puste — na przykład: *SalesAmount > 0*

### <a name="how-show-items-with-no-data-works"></a>Jak działa funkcja Pokaż elementy bez danych

Najbardziej interesujące zastosowania funkcji **Pokaż elementy bez danych** występują w przypadku istnienia miar. Przyjrzyjmy się sytuacji, w której grupy pochodzą z tej samej tabeli lub mogą być powiązane za pośrednictwem ścieżki w modelu. Na przykład kolumna *ProductStyle* jest bezpośrednio powiązana z tabelą *Product* i pośrednio powiązana z tabelą *Sales*, kolumny *ProductStyle* i *ProductCategory* mogą być powiązane za pośrednictwem tabeli *Product* itd.

Przyjrzyjmy się kilku interesującym przypadkom i porównajmy sytuacje, w których funkcja **Pokaż elementy bez danych** jest wyłączona, a następnie włączona. 

**1. Grupowanie kolumn z tej samej tabeli:** *Product[Color] — Product[Size] — Sum(Sales[Quantity])*

Sposób wyświetlania w przypadku wyłączenia funkcji **Pokaż elementy bez danych**:

|*Product[Color]*  |*Product[Size]*  |*[SumQuantity]*  |
|---------|---------|---------|
|Niebieski     |Średni         |15         |
|Niebieski     |Mały         |10         |

Sposób wyświetlania w przypadku włączenia funkcji **Pokaż elementy bez danych**:

|*Product[Color]*  |*Product[Size]*  |*[SumQuantity]*  |
|---------|---------|---------|
|Niebieski     |Duży         |         |
|Niebieski     |Średni         |15         |
|Niebieski     |Mały         |10         |
|Red     |Duży         |         |

Zwróć uwagę, jak dwie nowe kombinacje zostały pokazane po włączeniu funkcji: *Niebieski — duże* i *Czerwony — duże*. Obydwa wpisy nie mają odpowiadającej wartości *Quantity* w tabeli *Sales*. Są jednak wyświetlane w tabeli *Product*.

**2. Grupowanie kolumn z powiązanych tabel:** *ProductStyle[Finish] - Product[Color] - Sum(Sales[Quantity])*

Sposób wyświetlania w przypadku wyłączenia funkcji **Pokaż elementy bez danych**:

|*ProductStyle[Finish]*  |*Product[Color]*  |*[SumQuantity]*  |
|---------|---------|---------|
|Połysk     |Niebieski         |10         |
|Matowe     |Niebieski         |15         |

Sposób wyświetlania w przypadku włączenia funkcji **Pokaż elementy bez danych**:

|*ProductStyle[Finish]*  |*Product[Color]*  |*[SumQuantity]*  |
|---------|---------|---------|
|Połysk     |Niebieski         |10         |
|Połysk     |Red         |         |
|Matowe     |Niebieski         |15         |
|Brak     |         |         |

Zwróć uwagę, jak elementy *(Czerwony-połysk)* i *(Brak, puste)* zostały wyświetlone jako kombinacje. Oto przyczyny ich wyświetlenia:
* Usługa Power BI najpierw rozważyła element ProductStyle[Finish] i wybrała wartości do wyświetlenia — spowodowało to wynik Połysk, Matowe, Brak.
* Przy użyciu każdej z tych wartości usługa Power BI wybrała wszystkie odpowiadające wpisy *Product[Color]*. 
* Ponieważ wartość *Brak* nie odpowiada żadnemu elementowi *Product[Color]*, dla tej wartości pojawia się puste pole.

Ważne jest, aby zauważyć, że mechanizm wybierania wartości dla kolumn zależy od kolejności i można go traktować jako operację *lewe sprzężenie zewnętrzne* między tabelami. Zmiana kolejności wyników spowoduje również zmianę wyników.

Przyjrzyjmy się przykładowi zmiany kolejności i wpływowi tej zmiany na wyniki. Jest to taki sam element jak **2** w tej sekcji ze zmienioną kolejnością.

**Product[Color] — ProductStyle[Finish] — Sum(Sales[Quantity])**

Sposób wyświetlania w przypadku włączenia funkcji **Pokaż elementy bez danych**:

|*Product[Color]* |*ProductStyle[Finish]*  |*[SumQuantity]*  |
|---------|---------|---------|
|Niebieski     |Połysk         |10         |
|Niebieski     |Matowe         |15         |
|Red     |Połysk         |         |

W tym przypadku zauważ, że wartość *ProductStyle[Finish]=Brak* nie jest wyświetlana w tabeli. Dzieje się tak dlatego, że w tym przypadku usługa Power BI najpierw wybrała wszystkie wartości kolumny *Color* tabeli *Product*. Następnie dla każdego koloru usługa Power BI wybrała odpowiednie wartości *Finish*, które zawierały dane. Ponieważ wartość *Brak* nie jest wyświetlana w żadnej kombinacji elementu *Color*, nie jest wybierana.

## <a name="example-data-model"></a>Przykładowy model danych

W tej sekcji przedstawiono przykładowy model danych używany w przykładach w tym artykule.

**Model**: ![Relacje w modelu danych](media/desktop-show-items-no-data/show-items-no-data_03.png)


**Dane**:

|Product[ProductId]|    Product[ProductName]|   Product[Color]| Product[Size]|  Product[CategoryId]|    Product[StyleId]|
|---------|---------|---------|---------|---------|---------|
|1  |Prod1  |Niebieski   |Mały  |1  |1 |
|2  |Prod2  |Niebieski   |Średni |2  |2 |
|3  |Prod3  |Red    |Duży  |1  |1 |
|4  |Prod4  |Niebieski   |Duży  |2  |2 |


|ProductCategory[CategoryId]|   ProductCategory[CategoryName]|
|---------|---------|
|1  |Telefon   |
|2  |Aparat |
|3  |Telewizor |


|ProductStyle[StyleId]| ProductStyle[Finish]|   ProductStyle[Polished]|
|---------|---------|---------|
|1  |Połysk  |Tak |
|2  |Matowe  |Nie |
|3  |Brak   |Nie |


|Sales[SaleId]| Sales[ProductId]|   Sales[Date]|    Sales[Quantity]|
|---------|---------|---------|---------|
|1  |1  |2012-01-01 0:00| 10 |
|2  |2  |2013-01-01 0:00| 15 |



## <a name="next-steps"></a>Następne kroki

W tym artykule opisano sposób włączania funkcji **Pokaż elementy bez danych** w usłudze Power BI. Może zainteresują Cię również następujące artykuły: 

* [Domyślny element członkowski wielowymiarowych modeli w usłudze Power BI](desktop-default-member-multidimensional-models.md)
