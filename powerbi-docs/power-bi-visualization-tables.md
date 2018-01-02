---
title: "Wizualizacje tabel w raportach i na pulpitach nawigacyjnych usługi Power BI (samouczek)"
description: "Porady dotyczące pracy z wizualizacjami tabel w raportach i na pulpitach nawigacyjnych usługi Power BI, w tym informacje o sposobie zmieniania szerokości kolumn."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: e4a2e162ca193af756e7182fb118bc7e72d38d28
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="working-with-tables-in-power-bi-reports-and-dashboards-tutorial"></a>Praca z tabelami w raportach i na pulpitach nawigacyjnych usługi Power BI (samouczek)
Tabela to siatka zawierająca powiązane dane w postaci logicznej serii wierszy i kolumn. Może również zawierać nagłówki i wiersze sum. Tabele dobrze się sprawdzają w przypadku porównań ilościowych, gdy analizuje się wiele wartości z jednej kategorii. Na przykład ta tabela zawiera 5 różnych miar dla **kategorii**.

![](media/power-bi-visualization-tables/table.png)

## <a name="when-to-use-a-table"></a>Kiedy używać tabeli
Tabele są doskonałym wyborem do następujących celów:

* Wyświetlanie i porównywanie szczegółowych danych i dokładnych wartości (zamiast ich reprezentacji wizualnych)
* Wyświetlanie danych w formacie tabelarycznym
* Wyświetlanie danych liczbowych według kategorii   

> [!NOTE]
> Jeśli tabela zawiera zbyt wiele wartości, warto rozważyć przekonwertowanie jej na macierz i (lub) zastosowanie funkcji przechodzenia do szczegółów.
> 
> 

## <a name="create-a-table"></a>Tworzenie tabeli
Aby móc wykonywać te instrukcje, zaloguj się w usłudze Power BI, a następnie wybierz pozycję **Pobierz dane > Przykłady > Retail Analysis Sample**. Utworzymy tabelę przedstawioną powyżej, aby wyświetlić wartości sprzedaży według kategorii produktów.

1. W obszarze **Mój obszar roboczy** wybierz kartę Zestawy danych i przewiń w dół do zestawu danych próbki danych do analizy handlu detalicznego.  Wybierz ikonę **Utwórz raport**.
   
    ![](media/power-bi-visualization-tables/power-bi-create-report.png)
2. W edytorze raportu wybierz pozycję **Item (Element)** > **Category (Kategoria)**.  Usługa Power BI automatycznie tworzy tabelę, która zawiera wszystkie kategorie.
   
    ![](media/power-bi-visualization-tables/power-bi-table1.png)
3. Wybierz pozycję **Sales (Sprzedaż) > Average Unit Price (Średnia cena jednostkowa)**, **Sales (Sprzedaż) > Last Year Sales (Sprzedaż w zeszłym roku)** oraz **Sales (Sprzedaż) > This Year Sales (Sprzedaż w tym roku)** i wybierz wszystkie 3 opcje: Value (Wartość), Goal (Cel) i Status (Stan).   
4. W okienku Wizualizacje odszukaj obszar **Wartości**, a następnie przeciągaj i upuszczaj wartości, aż kolejność kolumn będzie zgodna z pierwszą ilustracją na tej stronie.  Obszar Wartości powinien wyglądać następująco.
   
    ![](media/power-bi-visualization-tables/power-bi-table2.png)
5. Przypnij tabelę do pulpitu nawigacyjnego, wybierając ikonę pinezki.  
   
     ![](media/power-bi-visualization-tables/pbi_pintile.png)

## <a name="format-the-table"></a>Formatowanie tabeli
Istnieje bardzo wiele sposobów formatowania tabeli. Omówimy tu tylko niektóre z nich. Dobrym sposobem na dowiedzenie się więcej o innych opcjach formatowania jest otwarcie okienka formatowania (ikona wałka do malowania ![](media/power-bi-visualization-tables/power-bi-format.png)) i przejrzenie opcji.

* Spróbuj sformatować siatkę tabeli. W tym miejscu dodaliśmy niebieską siatkę pionową, dodaliśmy więcej miejsca do wierszy oraz zwiększyliśmy nieco obramowanie oraz rozmiar tekstu.
  
    ![](media/power-bi-visualization-tables/power-bi-table-grid2-new.png)
  
    ![](media/power-bi-visualization-tables/power-bi-table-grid3.png)
* W nagłówkach kolumn zmieniliśmy kolor tła, dodaliśmy obramowanie i zwiększyliśmy rozmiar czcionki. 
  
    ![](media/power-bi-visualization-tables/power-bi-table-column.png)
  
    ![](media/power-bi-visualization-tables/power-bi-table-column2.png)
* Po dodaniu jeszcze kilku opcji formatowania tabela wygląda tak. Ponieważ istnieje tak wiele opcji formatowania, najlepiej jest rozpocząć zapoznawanie się z nimi od zwykłej tabeli: otwórz okienko formatowania ![](media/power-bi-visualization-tables/power-bi-format.png) i zacznij przeglądać opcje. 
  
    ![](media/power-bi-visualization-tables/power-bi-table-format.png)

### <a name="conditional-formatting"></a>Formatowanie warunkowe
Jeden z typów formatowania jest określany jako *formatowanie warunkowe*. Jest on stosowany do pól w obszarze **Wartość** w okienku **Wizualizacje** w usłudze Power BI lub programie Desktop. 

Za pomocą formatowania warunkowego dla tabel można określić niestandardowe kolory czcionek i kolory tła komórek na podstawie wartości komórek. Można nawet używać gradientów kolorów. 

1. W okienku **Wizualizacje** w usłudze Power BI lub programie Desktop w obszarze **Wartości** wybierz strzałkę w dół obok wartości, którą chcesz sformatować (lub kliknij to pole prawym przyciskiem myszy). Można zarządzać tylko formatowaniem warunkowym pól w obszarze **Wartości** w obszarze **Pola**.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-background.png)
2. Wybierz pozycję **Skale kolorów tła**. W wyświetlonym oknie dialogowym można skonfigurować kolor, a także wartości *Minimum* i *Maksimum*. W przypadku wybrania pola **Rozbieżność** można skonfigurować też wartość opcjonalną *Środek*.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)
   
    Zastosujmy formatowanie niestandardowe do naszych wartości Average Unit Price (Średnia cena jednostkowa). Wybierz pozycję **Rozbieżność**, dodaj kolory i wybierz przycisk **OK**. 
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
3. Dodaj do tabeli nowe pole zawierające wartości zarówno dodatnie, jak i ujemne.  Wybierz pozycję **Sales (Sprzedaż) > Total Sales Variance (Całkowita wariancja sprzedaży)**. 
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)
4. Dodaj formatowanie warunkowe w postaci paska danych, wybierając strzałkę w dół obok pozycji **Total Sales Variance** (Całkowita wariancja sprzedaży) i wybierając pozycję **Formatowanie warunkowe > Paski danych**.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars.png)
5. W wyświetlonym oknie dialogowym ustaw kolory dla opcji **Pasek dodatni** oraz **Pasek ujemny**, umieść znacznik wyboru obok pozycji **Pokaż tylko pasek** i wprowadź inne zmiany według własnego uznania.
   
    ![](media/power-bi-visualization-tables/power-bi-data-bars.png)
   
    Po wybraniu przycisku **OK** paski danych zastąpią wartości liczbowe w tabeli, co ułatwi jej przeglądanie.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)
6. Aby usunąć formatowanie warunkowe z wizualizacji, wystarczy ponownie kliknąć pole prawym przyciskiem myszy i wybrać pozycję **Usuń formatowanie warunkowe**.

> [!TIP]
> Formatowanie warunkowe jest również dostępne w okienku formatowania (ikona wałka do malowania). Wybierz wartość do sformatowania, a następnie włącz opcję **Skale kolorów** lub **Paski danych**, aby zastosować ustawienia domyślne. Aby natomiast dostosować ustawienia, wybierz pozycję **Kontrolki zaawansowane**.
> 
> 

## <a name="adjust-the-column-width-of-a-table"></a>Dopasowywanie szerokości kolumn w tabeli
Czasami usługa Power BI obcina nagłówek kolumny w raporcie i na pulpicie nawigacyjnym. Aby wyświetlić całą nazwę kolumny, przesuń kursor myszy na miejsce z prawej strony nagłówka w celu wyświetlenia strzałki podwójnej, zaznacz i przeciągnij.

![](media/power-bi-visualization-tables/resizetable.gif)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

