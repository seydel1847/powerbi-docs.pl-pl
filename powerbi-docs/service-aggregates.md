---
title: "Agregowanie (suma, średnia, wartość maksymalna itp.) w usłudze Power BI"
description: "Zmienianie agregacji na wykresie (suma, średnia, wartość maksymalna itp.) w usłudze Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/23/2017
ms.author: mihart
ms.openlocfilehash: c1b926e129e8d82edd9c329a51623908c4e7c9e0
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2017
---
# <a name="aggregates-in-power-bi"></a>Agregowanie w usłudze Power BI
## <a name="what-is-an-aggregate"></a>Co to jest agregacja?
Czasami trzeba za pomocą operacji matematycznych połączyć ze sobą wartości wierszy w kolumnie. Operacja matematyczna może dotyczyć sumy, średniej, wartości maksymalnej, liczby elementów itp. Łączenie wartości danych wierszy w kolumnie nazywa się agregowaniem. Wynikiem tej operacji matematycznej jest *agregacja*. 

Pole numeryczne jest wartością, która będzie agregowana (na przykład sumowana lub uśredniana) względem określonego pola kategorii.  Na przykład „kwoty sprzedaży według produktu” i „liczba wad według regionu”. Pola numeryczne często nazywa się **miarami**. Na liście pól miary są wyświetlane z symbolem ∑. Aby uzyskać więcej informacji, zobacz [The report editor... take a tour](service-the-report-editor-take-a-tour.md) (Edytor raportów — przewodnik).

Czasami *miara* przyjmuje postać *miary obliczanej*. Miary obliczane w usłudze Power BI są importowane z danymi (zdefiniowanymi w modelu danych, na którym jest oparty Twój raport). Każda miara obliczana ma własną ustaloną formułę. Nie można zmienić używanej agregacji, jeśli, na przykład, jest to suma, pozostanie sumą. Na liście pól *miary obliczane* są wyświetlane z symbolem kalkulatora. Aby uzyskać więcej informacji na temat tworzenia miar obliczanych, zobacz [Miary w programie Power BI Desktop](desktop-measures.md).

Chociaż pola kategorii nie są polami numerycznymi, można je agregować.  Gdy pola kategorii są umieszczane w zasobniku *tylko liczbowe*, takim jak **Wartości** lub **Etykietki**, usługa Power BI może zliczać wystąpienia każdej kategorii lub unikatowe wystąpienia każdej kategorii.  W przypadku ciągów i dat usługa Power BI oferuje kilka dodatkowych opcji agregacji: najwcześniejsze, najnowsze, pierwsze i ostatnie.  

## <a name="why-dont-aggregates-work-the-way-i-want-them-to"></a>Dlaczego agregowanie nie działa odpowiednio?
Praca z agregacjami w usłudze Power BI może sprawiać kłopot, kiedy na przykład usługa Power BI nie pozwala Ci zmienić agregacji w przypadku pola numerycznego lub kiedy nie chcesz agregować pola (np. Rok), ale chcesz jedynie zliczyć jego wystąpienia.

Najczęstszym źródłem problemu jest rodzaj kategorii, do której zostało przydzielone pole w zbiorze danych usługi Power BI. Jeśli pole zostało sklasyfikowane jako tekst, nie będzie możliwe obliczenie sumy ani średniej. Niestety [tylko właściciel zestawu danych może zmienić sposób klasyfikacji pola](desktop-measures.md).  

W razie jakichkolwiek problemów zapoznaj się z sekcją **Porady i rozwiązywanie problemów** w tym artykule.  Jeśli nie znajdziesz tam odpowiedzi, opublikuj swoje pytanie na [forum społeczności usługi Power BI](http://community.powerbi.com), aby uzyskać szybką odpowiedź bezpośrednio od zespołu usługi Power BI.

## <a name="change-how-a-numeric-field-is-aggregated"></a>Zmienianie sposobu agregacji pola numerycznego
Załóżmy, że istnieje wykres sumujący dane sprzedaży z różnych regionów, ale wolisz wyświetlić dane uśrednione. 

1. W widoku do edycji raportów dodaj do wizualizacji miarę.
2. Znajdź odpowiednie pole w okienku wizualizacji, kliknij je prawym przyciskiem myszy i wybierz odpowiedni typ agregacji. Jeśli nie widzisz potrzebnej opcji agregacji, skontaktuj się z właścicielem zestawu danych. Problem może dotyczyć zaklasyfikowania pola przez właściciela.  
   
   ![](media/service-aggregates/aggregate_new.png)
   
   > [!NOTE]
   > Opcje dostępne na liście rozwijanej będą się różnić w zależności od 1) wybranego pola oraz 2) sposobu sklasyfikowania pola przez właściciela zestawu danych.
   > 
   > 

Niektóre opcje dostępne w ramach agregowania pola:

* **Nie sumuj.** Po wybraniu tej opcji wszystkie wartości w danym polu są traktowane odrębnie i nie są sumowane. Często używana jest w przypadku kolumny liczbowej identyfikatora, której nie należy sumować.
* **Suma.** Sumuje wszystkie wartości w danym polu.
* **Średnia.** Przyjmuje średnią arytmetyczną wartości.
* **Minimum.** Wyświetla najmniejszą wartość.
* **Maksimum.** Wyświetla największą wartość.
* **Liczność (niepuste).** Zlicza wartości w danym polu, które nie są puste.
* **Liczność (unikatowe).** Zlicza różne wartości w danym polu.
* **Odchylenie standardowe.**
* **Wariancja.**
* **Mediana.**  Wyświetla wartość mediany (środkowa). Jest to wartość, która ma taką samą liczbę elementów powyżej, jak i poniżej.  W przypadku dwóch wartości mediany usługa Power BI uśredni je.

Jako przykładu użyjemy następujących danych:

| Kraj | Kwota |
|:--- |:--- |
| Stany Zjednoczone |100 |
| Zjednoczone Królestwo |150 |
| Kanada |100 |
| Niemcy |125 |
| Francja | |
| Japonia |125 |
| Australia |150 |

Otrzymane wyniki będą wyglądać następująco:

* **Nie sumuj:** każda wartość jest wyświetlana osobno
* **Suma:** 750
* **Średnia:** 125
* **Maksimum:** 150
* **Minimum:** 100
* **Liczność (niepuste):** 6
* **Liczność (unikatowe):** 4
* **Odchylenie standardowe:** 20,4124145...
* **Wariancja:** 416,666...
* **Mediana:** 125

## <a name="use-a-non-aggregated-field-as-a-numeric-field"></a>Używanie pola niezagregowanego jako pola numerycznego
Możesz użyć pola niezagregowanego jako pola numerycznego. Na przykład jeśli masz pole Nazwa produktu, możesz dodać je jako wartość, a następnie ustawić dla niego opcję **Liczność** lub **Liczność unikatowych wartości**. 

1. Możesz na przykład wybierać kolejno pozycje **Sklep > Sieć**.
   
   ![](media/service-aggregates/count-of-chain-do_not_summarize.png)
2. Jeśli natomiast zmienisz domyślną opcję agregacji **Nie sumuj** na **Liczność (unikatowe)**, usługa Power BI zliczy liczbę różnych sieci. W tym przypadku istnieją dwie sieci: Fashions Direct i Lindseys.
   
   ![](media/service-aggregates/aggregates_count.png)
3. Zmiana opcji agregacji na **Liczność** spowoduje, że usługa Power BI zliczy wszystkie elementy. W tym przypadku **Sieć** ma 104 wpisy. Po dodaniu filtru w kolumnie **Sieć** zauważysz, że 37 wierszy dotyczy sieci Fashions Direct, a 67 wierszy dotyczy sieci Lindseys.  
   
   ![](media/service-aggregates/count_of_chain_104.png)

## <a name="tips-and-troubleshooting"></a>Porady i rozwiązywanie problemów
Pytanie: Dlaczego nie mam dostępu do opcji **Nie sumuj**?

Odpowiedź: Wybrane pole jest prawdopodobnie miarą obliczaną. Pamiętaj, że każda miara obliczana ma własną ustaloną formułę. Nie możesz zmienić wykonywanych obliczeń.

Pytanie: Skoro wybrane przeze mnie pole **jest** numeryczne, dlaczego jedynymi dostępnymi opcjami są **Liczność** i **Liczność unikatowych wartości**?

Odpowiedź: Prawdopodobnie właściciel zestawu danych przypadkowo lub celowo *nie* sklasyfikował pola jako liczby. Załóżmy, że zestaw danych zawiera pole **Rok**. Właściciel zestawu danych może sklasyfikować go jako tekst, ponieważ bardziej prawdopodobne jest, że pole **Rok** będzie zliczane (tj. liczba osób urodzonych w 1974 r.), a nie sumowane lub uśredniane. Jeśli jesteś właścicielem, możesz otworzyć zestaw danych w programie Power BI Desktop i użyć karty **Modelowanie**, aby zmienić typ danych.  

Odpowiedź: Inna możliwość może dotyczyć upuszczenia pola do *zasobnika*, który dopuszcza tylko wartości kategorii.  W takim przypadku jedynymi dostępnymi opcjami będą Liczność i Liczność unikatowych wartości.

Odpowiedź: Trzecia możliwość polega na tym, że używasz pola dla osi. Posłużmy się przykładem. Na osi wykresu słupkowego usługa Power BI wyświetla po jednym pasku dla każdej unikatowej wartości — wartości pola nie są przez nią w ogóle agregowane. 

>[!NOTE]
>Wyjątkiem od tej reguły są wykresy punktowe, które *wymagają* wartości zagregowanych dla osi X i Y.


Pytanie: Mam diagram punktowy i *nie* chcę, aby moje pole było agregowane.  Co mam zrobić?

Odpowiedź: Dodaj pole do zasobnika **Szczegóły**, a nie do zasobników osi X i Y.

Pytanie: Podczas dodawania pól numerycznych do wizualizacji większość z nich przyjmuje wartość domyślną sumowania, ale dla niektórych wartość domyślna to średnia lub liczność albo jeszcze inne opcje agregacji.  Dlaczego domyślna opcja agregacji nie jest zawsze taka sama?

Odpowiedź: Właściciele zestawów danych mają możliwość ustawienia wartości domyślnej sumowania dla każdego pola. Jeśli jesteś właścicielem zestawu danych, zmień domyślną wartość sumowania na karcie **Modelowanie** programu Power BI Desktop.

Pytanie: Wybrane przeze mnie pole **jest** numeryczne, ale na liście rozwijanej nie są wyświetlane żadne opcje agregacji. Dlaczego tak się dzieje?

Odpowiedź: Jeśli pole zawiera ikonę kalkulatora, oznacza to, że jest *miarą obliczaną*, a każda miara obliczana ma własną ustaloną formułę, której nie można zmienić w usłudze Power BI. Przeprowadzane obliczenia mogą dotyczyć prostej agregacji, takiej jak średnia lub suma, ale równie dobrze mogłyby obejmować bardziej skomplikowane operacje, takie jak „procent łącznego wkładu względem kategorii nadrzędnej” lub „suma bieżąca obliczana od początku roku”. Usługa Power BI nie będzie obliczać sumy ani średniej dla otrzymanych wyników, zamiast tego ponownie zliczy wartości (przy użyciu ustalonej formuły) dla każdego punktu danych.

Pytanie: Jestem właścicielem zestawu danych i chcę mieć pewność, że pole nigdy nie będzie agregowane.

Odpowiedź: W programie Power BI Desktop na karcie **Modelowanie** ustaw kolumnę **Typ danych** na wartość **Tekst**.

Pytanie: Na liście rozwijanej nie pojawia się opcja **Nie sumuj**.

Odpowiedź: Spróbuj usunąć pole i dodać je ponownie.

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

