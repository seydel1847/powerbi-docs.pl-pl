---
title: Używanie wizualizacji macierzy w programie Power BI Desktop
description: Dowiedz się, jak wizualizacja macierzy umożliwia korzystanie z układów schodkowych i szczegółowego wyróżniania w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 7673e7693c1374b6b82925c704efb52bea346040
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="use-the-matrix-visual-in-power-bi-desktop"></a>Używanie wizualizacji Macierz w programie Power BI Desktop
Funkcja wizualizacji **Macierz** pozwala tworzyć wizualizacje macierzy (czasami określane jako *tabele*) w raportach programu **Power BI Desktop**, a także umożliwia wyróżnianie krzyżowe elementów w macierzy oraz w innych wizualizacjach. Ponadto możesz zaznaczać do wyróżnienia krzyżowego wiersze, kolumny, a nawet pojedyncze komórki. Aby jeszcze skuteczniej wykorzystać miejsce, wizualizacja macierzy obsługuje układ schodkowy.

![](media/desktop-matrix-visual/matrix-visual_2a.png)

Z macierzą jest skojarzonych wiele funkcji. Omówimy je w kolejnych sekcjach tego artykułu.

> [!NOTE]
> Od wersji programu **Power BI Desktop** z lipca 2017 wizualizacja macierzy i tabeli odzwierciedla stylizację (w tym kolorystykę) zastosowanego **motywu raportu**. Te kolory mogą różnić się od oczekiwanych w wizualizacji macierzy. Możesz je zmienić w konfiguracji **motywu raport**. Aby uzyskać więcej informacji o motywach, zobacz [**Korzystanie z motywów raportów w programie Power BI Desktop**](desktop-report-themes.md).
> 
> 

## <a name="understanding-how-power-bi-calculates-totals"></a>W jaki sposób usługa Power BI oblicza sumy

Zanim przejdziemy do sposobu używania wizualizacji **Macierz**, ważne jest, aby zrozumieć, jak usługa Power BI oblicza sumy i sumy częściowe w tabelach i macierzach. W przypadku wierszy sum i sum częściowych miara jest obliczana z uwzględnieniem wszystkich wierszy danych podstawowych — *nie* jest to jedynie proste dodanie wartości w widocznych lub wyświetlanych wierszach. To oznacza, że w wierszu sumy można uzyskać wartości różniące się od oczekiwanych. 

Zobacz następujące wizualizacje **Macierz**. 

![](media/desktop-matrix-visual/matrix-visual_3.png)

W tym przykładzie każdy wiersz w wizualizacji **Macierz** najdalej z prawej strony zawiera *kwotę* dla każdej kombinacji sprzedawca/data. Ze względu na to, że sprzedawca jest wyświetlany w odniesieniu do wielu dat, liczby mogą wystąpić więcej niż raz. Dlatego dokładna suma z danych podstawowych i proste dodanie widocznych wartości nie są równoważne. Jest to typowy wzorzec, gdy sumowana wartość znajduje się po stronie „jeden” w relacji jeden do wielu.

Przeglądając sumy i sumy częściowe należy pamiętać, że wartości te są oparte na danych podstawowych, a nie wyłącznie na wartościach, które są widoczne. 


## <a name="using-drill-down-with-the-matrix-visual"></a>Przechodzenie do szczegółów w wizualizacji macierzy
Wizualizacja **Macierz** oferuje wiele interesujących, niedostępnych wcześniej sposobów przechodzenia do szczegółów. Obejmuje to między innymi przechodzenie do szczegółów w wierszach, kolumnach, a nawet sekcjach i komórkach. Przyjrzyjmy się, jak to działa.

### <a name="drill-down-on-row-headers"></a>Przechodzenie do szczegółów w nagłówkach wierszy
W okienku **Wizualizacje** możesz dodać wiele pól w sekcji **Wiersze** obszaru **Pola**, aby umożliwić przechodzenie do szczegółów w wierszach wizualizacji macierzy. Ta opcja działa podobnie do tworzenia hierarchii, która umożliwia przechodzenie do szczegółów (i wracanie do wyższych poziomów) oraz analizowanie danych na każdym poziomie.

Na poniższej ilustracji sekcja **Wiersze** zawiera pozycje *Category* (Kategoria) i *SubCategory* (Podkategoria). Uzyskany w ten sposób podział na grupy (inaczej hierarchia) pozwala przechodzić do szczegółów.

![](media/desktop-matrix-visual/matrix-visual_4.png)

W lewym górnym rogu wizualizacji, w której utworzono grupy w sekcji **Wiersze**, są wyświetlane ikony *Przejdź do szczegółów* i *Rozwiń*.

![](media/desktop-matrix-visual/matrix-visual_5.png)

Podobnie jak w przypadku innych wizualizacji, przyciski te umożliwiają przechodzenie do szczegółów i wracanie do bardziej ogólnych poziomów hierarchii. W tym przypadku możemy przejść do szczegółów z grupy *Category* (Kategoria) do grupy *SubCategory* (Podkategoria). Widać to na poniższej ilustracji, gdzie wybrano ikonę przejścia do szczegółów o jeden poziom (przypominającą widły).

![](media/desktop-matrix-visual/matrix-visual_6.png)

Oprócz korzystania z tych ikon możesz kliknąć dowolny nagłówek wiersza prawym przyciskiem myszy i wybrać z menu opcję przejścia do szczegółów.

![](media/desktop-matrix-visual/matrix-visual_7.png)

Wyświetlane menu zawiera kilka opcji, które generują różne wyniki:

Wybranie opcji **Przejdź do szczegółów** rozwija macierz dla poziomu *tego* wiersza (klikniętego prawym przyciskiem myszy) — *z wykluczeniem* wszystkich pozostałych nagłówków wierszy. Na poniższej ilustracji kliknięto prawym przyciskiem pozycję *Computers*  (Komputery) i wybrano polecenie **Przejdź do szczegółów**. Zauważ, że pozostałe wiersze najwyższego poziomu nie są już widoczne w macierzy. Ta funkcja okaże się szczególnie przydatna, kiedy przejdziemy do sekcji na temat **wyróżniania krzyżowego**.

![](media/desktop-matrix-visual/matrix-visual_8.png)

Możesz kliknąć ikonę **Uogólnij**, aby wrócić do widoku najwyższego poziomu. Jeśli z menu podręcznego wybierzesz opcję **Pokaż następny poziom**, uzyskasz listę alfabetyczną wszystkich pozycji następnego poziomu (w tym przypadku z pola *SubCategory* (Podkategoria)) bez podziału na kategorie wyższego poziomu.

![](media/desktop-matrix-visual/matrix-visual_8a.png)

Gdy klikniesz ikonę **Uogólnij** w lewym górnym rogu, aby wyświetlić wszystkie kategorie najwyższego poziomu w macierzy, a następnie ponownie klikniemy prawym przyciskiem myszy i wybierzemy opcję **Rozwiń do następnego poziomu**, zobaczysz następujący widok:

![](media/desktop-matrix-visual/matrix-visual_9.png)

Są również dostępne elementy menu **Dołącz** i **Wyklucz**, które pozwalają odpowiednio zachować lub usunąć wiersz macierzy kliknięty prawym przyciskiem myszy (wraz z wszystkimi podkategoriami).

### <a name="drill-down-on-column-headers"></a>Przechodzenie do szczegółów w nagłówkach kolumn
Możesz przechodzić do szczegółów **kolumn** podobnie jak w przypadku wierszy. Na poniższej ilustracji widać, że w obszarze **Kolumny** znajdują się dwa pola. Tworzą one hierarchię podobną do wierszy z poprzedniego artykułu. W obszarze **Kolumny** znajdują się pozycje *Class* (Klasa) i *Color* (Kolor).

![](media/desktop-matrix-visual/matrix-visual_10.png)

Po kliknięciu kolumny prawym przyciskiem myszy w wizualizacji **Macierz** widzimy opcję przejścia do szczegółów. Na poniższej ilustracji klikniemy prawym przyciskiem myszy pozycję *Deluxe* (Luksusowe) i wybierzemy polecenie **Przejdź do szczegółów**.

![](media/desktop-matrix-visual/matrix-visual_11.png)

Wybranie polecenia **Przejdź do szczegółów** spowoduje wyświetlenie kolejnego poziomu hierarchii kolumn *Deluxe* (Luksusowe) — w tym przypadku *Color* (Kolor).

![](media/desktop-matrix-visual/matrix-visual_12.png)

Pozostałe elementy menu kontekstowego działają na kolumnach tak samo jak na wierszach (zobacz poprzednią sekcję **Przechodzenie do szczegółów w nagłówkach wierszy**). Do kolumn — podobnie jak do wierszy — można stosować polecenia **Pokaż następny poziom**, **Rozwiń do następnego poziomu**, **Dołącz** i **Wyklucz**.

> [!NOTE]
> Ikony przechodzenia do szczegółów i uogólniania w lewym górnym rogu wizualizacji macierzy dotyczą tylko wierszy. Aby przejść do szczegółów kolumny, trzeba użyć menu kontekstowego.
> 
> 

## <a name="stepped-layout-with-matrix-visuals"></a>Układ schodkowy wizualizacji macierzy
Wizualizacja **Macierz** automatycznie tworzy wcięcia podkategorii w hierarchii pod każdym elementem nadrzędnym. Jest to tak zwany **układ schodkowy**.

W *pierwotnej* wersji wizualizacji macierzy podkategorie były wyświetlane w odrębnej kolumnie, przez co zajmowały o wiele więcej miejsca. Na poniższej ilustracji przedstawiono tabelę w pierwotnej wizualizacji **macierzy**. Zwróć uwagę na oddzielną kolumnę podkategorii.

![](media/desktop-matrix-visual/matrix-visual_14.png)

Na poniższej ilustracji przedstawiono wizualizację **Macierz** z **układem schodkowym**. Zwróć uwagę, że w kategorii *Computers* (Komputery) widać nieznacznie przesunięte podkategorie — Computers Accessories (Akcesoria komputerowe), Desktops (Komputery biurkowe), Laptops (Laptopy), Monitors (Monitory) itd. — dzięki czemu wizualizacja jest czytelniejsza i zajmuje mniej miejsca.

![](media/desktop-matrix-visual/matrix-visual_13.png)

Możesz łatwo dopasować ustawienia układu schodkowego. Po wybraniu wizualizacji **Macierz** w sekcji **Format** (ikona wałka do malowania) okienka **Wizualizacje** rozwiń sekcję **Nagłówki wierszy**. Masz dwie opcje: przełącznik **Układ schodkowy** (włącza lub wyłącza ten układ) oraz **Wcięcie układu schodkowego** (określa głębokość wcięcia w pikselach).

![](media/desktop-matrix-visual/matrix-visual_15.png)

Wyłączenie opcji **Układ schodkowy** powoduje, że podkategorie są wyświetlane w odrębnej kolumnie, a nie z wcięciami pod kategorią nadrzędną.

## <a name="subtotals-with-matrix-visuals"></a>Sumy częściowe w wizualizacji macierzy
W wizualizacji macierzy możesz włączyć lub wyłączyć sumy częściowe wierszy i kolumn. Na poniższej ilustracji widać **włączone** sumy częściowe wierszy.

![](media/desktop-matrix-visual/matrix-visual_20.png)

W sekcji **Format** okienka **Wizualizacje** rozwiń kartę **Sumy częściowe** i przesuń suwak **Sumy częściowe wierszy** do pozycji **Wyłącz**. Spowoduje to ukrycie sum częściowych.

![](media/desktop-matrix-visual/matrix-visual_21.png)

Taki sam proces dotyczy sum częściowych kolumn.

## <a name="cross-highlighting-with-matrix-visuals"></a>Wyróżnianie krzyżowe w wizualizacji macierzy
Przy użyciu wizualizacji **Macierz** można zaznaczyć dowolne elementy macierzy w celu wyróżnienia krzyżowego. Kiedy zaznaczysz kolumnę w wizualizacji **Macierz**, zostanie ona wyróżniona we wszystkich innych wizualizacjach na stronie raportu. Była to wspólna funkcja innych wizualizacji i zaznaczonych punktów danych, dlatego teraz wizualizacja **Macierz** oferuje tę samą funkcję.

Wyróżnianie krzyżowe reaguje także na kliknięcia z wciśniętym klawiszem Ctrl. Na przykład poniższa ilustracja zawiera kolekcję podkategorii zaznaczonych w wizualizacji **Macierz**. Zauważ, że elementy niezaznaczone w wizualizacji są wygaszone, a pozostałe wizualizacje na stronie odzwierciedlają zaznaczenie z wizualizacji **Macierz**.

![](media/desktop-matrix-visual/matrix-visual_16.png)

## <a name="shading-and-font-colors-with-matrix-visuals"></a>Cieniowanie i kolory czcionek w wizualizacji macierzy
Wizualizacja **Macierz** pozwala zastosować **formatowanie warunkowe** (kolory i cieniowanie) do tła komórek macierzy oraz do tekstu i wartości.

Aby użyć formatowania warunkowego, wykonaj jedną z tych czynności po wybraniu wizualizacji macierzy:

* W okienku **Pola** kliknij pole prawym przyciskiem myszy i wybierz z menu polecenie **Formatowanie warunkowe**.
  
  ![](media/desktop-matrix-visual/matrix-visual_17.png)
* Możesz też w okienku **Format** rozwinąć kartę **Formatowanie warunkowe** i przesunąć suwak obok opcji **Skale koloru tła** lub **Skale koloru czcionki** do pozycji **Włącz**. Włączenie dowolnej opcji powoduje wyświetlenie linku do okna *Kontrolki zaawansowane*, które umożliwia dostosowanie kolorów i wartości formatowania kolorów.
  
  ![](media/desktop-matrix-visual/matrix-visual_18.png)

Niezależnie od wybranej metody wynik będzie taki sam. Wybranie opcji *Kontrolki zaawansowane* powoduje wyświetlenie następującego okna dialogowego, w którym możesz dostosować opcje:

![](media/desktop-matrix-visual/matrix-visual_19.png)

## <a name="next-steps"></a>Następne kroki

Może zainteresują Cię również następujące artykuły:

* [Używanie linii siatki i przyciągania do siatki w raportach programu Power BI Desktop](desktop-gridlines-snap-to-grid.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Typy danych w programie Power BI Desktop](desktop-data-types.md)

 