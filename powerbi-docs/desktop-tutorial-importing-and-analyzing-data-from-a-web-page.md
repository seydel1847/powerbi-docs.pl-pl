---
title: "Samouczek: Importowanie i analizowanie danych ze strony internetowej przy użyciu programu Power BI Desktop"
description: "Samouczek: Importowanie i analizowanie danych ze strony internetowej przy użyciu programu Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: c5139c6f9f7b2098b51a608fb7719f371173c291
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2017
---
# <a name="analyzing-web-page-data-using-power-bi-desktop-tutorial"></a>Analizowanie danych strony internetowej przy użyciu programu Power BI Desktop (samouczek)
W tym samouczku nauczysz się importować tabelę danych ze strony internetowej i tworzyć raport w celu wizualizacji tych danych. W ramach tego procesu będziesz przechodzić między tabelami dostępnymi na stronie internetowej i stosować czynności przekształcania danych, aby nadać tabeli nowy kształt.

 W tym artykule:

* **Zadanie 1.** Nawiązywanie połączenia z internetowym źródłem danych
* **Zadanie 2.** Kształtowanie danych w widoku zapytań
  * Krok 1. Usuwanie innych kolumn w celu wyświetlenia tylko interesujących kolumn
  * Krok 2. Zastępowanie wartości, aby wyczyścić wartości w zaznaczonej kolumnie
  * Krok 3. Filtrowanie wartości w kolumnie
  * Krok 4. Zmiana nazwy kolumny
  * Krok 5. Filtrowanie wartości null w kolumnie
  * Krok 6. Zmiana nazwy zapytania
  * Kroki zapytania zostały utworzone
* **Zadanie 3.** Tworzenie wizualizacji przy użyciu widoku raportu
  * Krok 1. Ładowanie zapytania do raportu
  * Krok 2. Tworzenie wizualizacji mapy

## <a name="task-1-connect-to-a-web-data-source"></a>Zadanie 1. Nawiązywanie połączenia z internetowym źródłem danych
 W zadaniu 1 zaimportujesz tabelę podsumowania turniejów ze strony Wikipedii dotyczącej Mistrzostw Europy w piłce nożnej UEFA, która jest dostępna pod adresem: http://en.wikipedia.org/wiki/UEFA\_European\_Football\_Championship

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

### <a name="add-a-wikipedia-page-data-source"></a>Dodawanie źródła danych w postaci strony Wikipedii
1. W oknie dialogowym **Wprowadzenie** lub na karcie wstążki **Narzędzia główne** wybierz polecenie **Pobierz dane**.
2. Spowoduje to wyświetlenie okna dialogowego **Pobieranie danych**, w którym można wybierać różne źródła danych w celu importowania danych do programu Power BI Desktop. Wybierzemy pozycję **Internet**, która jest dostępna w grupie **Wszystkie** lub **Inne**.
3. W oknie dialogowym **Zawartość sieci Web** w polu tekstowym **Adres URL** wklej adres URL strony Wikipedii (http://en.wikipedia.org/wiki/UEFA\_European\_Football\_Championship).
4. Kliknij przycisk **OK**.

Po ustanowieniu połączenia ze stroną internetową w oknie dialogowym **Nawigator** zostanie wyświetlona lista tabel dostępnych na tej stronie Wikipedii. Aby zobaczyć podgląd danych, wystarczy raz kliknąć każdą z tych tabel.

W lewym okienku okna dialogowego **Nawigator** wybierz tabelę **Results[edit]**, aby uzyskać podsumowanie turniejów, albo wybierz tabelę **Results[edit]** i wybierz pozycję **Edytuj**. Dzięki temu możliwe będzie przekształcenie tej tabeli przed załadowaniem jej do raportu, ponieważ dane nie mają kształtu, którego potrzebujemy do naszej analizy.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)

To spowoduje umieszczenie podglądu tabeli w widoku zapytania, w którym można zastosować zestaw kroków przekształcania w celu wyczyszczenia danych.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)

## <a name="task-2-shape-data-in-the-subject-table"></a>Zadanie 2. Kształtowanie danych w przedmiotowej tabeli
Teraz, gdy przedmiotowa tabela została wybrana dla zapytania o dane, nauczysz się wykonywać różne czynności kształtowania i czyszczenia danych.

**Krok 1.** Usuwanie innych kolumn w celu wyświetlenia tylko interesujących kolumn

W tym kroku usuniesz wszystkie kolumny oprócz kolumn **Year** i **Final Winners**.

1. W siatce **Podgląd zapytania** wybierz kolumny **Year** i **Final Winners** (użyj kombinacji **CTRL** + **kliknięcie**).
2. Kliknij prawym przyciskiem myszy nagłówek kolumny w siatce **Podgląd zapytania**, a następnie kliknij polecenie **Usuń inne kolumny**, aby usunąć niewybrane kolumny. Zwróć uwagę na to, że ta operacja jest także dostępna na karcie wstążki **Narzędzia główne** w grupie **Zarządzaj kolumnami**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

**Krok 2.** Zastępowanie wartości, aby wyczyścić wartości w zaznaczonej kolumnie

W tym kroku zastąpisz sufiks Details w kolumnie **Year**. Ten sufiks znajduje się w nowym wierszu i dlatego jest niewidoczny w podglądzie tabeli. Jeśli jednak klikniesz w jednej z komórek z wartością liczbową w kolumnie Year, w widoku szczegółowym zostanie wyświetlona pełna wartość.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage5.png)

1. Wybierz kolumnę **Year**.
2. Na wstążce **Widok zapytania** kliknij pozycję **Zamień wartości** na karcie **Narzędzia główne** lub kliknij prawym przyciskiem myszy kolumnę **Year**, a następnie kliknij polecenie **Zamień wartości**, aby zastąpić sufiks Details pustym tekstem.
3. W oknie dialogowym **Zamienianie wartości** wpisz wartość Details w polu tekstowym **Wartość do znalezienia** i pozostaw pole tekstowe **Zamień na** puste.
4. Kliknij przycisk **OK**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

 **Krok 3.** Filtrowanie wartości w kolumnie

W tym kroku odfiltrujesz zawartość kolumny **Year**, aby wyświetlać tylko wiersze, które nie zawierają słowa „Year”.

1. Kliknij strzałkę listy rozwijanej filtru w kolumnie **Year**.
2. Na liście rozwijanej **Filtr** usuń zaznaczenie opcji **Year**.
3. Kliknij przycisk **OK**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

**Krok 4.** Zmiana nazwy kolumny

Wyczyściliśmy dane w kolumnie **Year**, a teraz zajmiemy się kolumną **Final Winner**.

Mamy do czynienia tylko z listą zwycięzców, dlatego możemy zmienić nazwę tej kolumny na **Country**.

1. Wybierz kolumnę **Final Winner** w obszarze podglądu zapytania.
2. Na wstążce **Widok zapytania** w obszarze karty **Przekształć** w grupie **Dowolna kolumna** znajdziesz pozycję **Zmień nazwę**.
3. Wybranie tej pozycji spowoduje umożliwienie edycji nazwy kolumny. Zmienimy nazwę tej kolumny na **Country**.

**Krok 5.** Filtrowanie wartości null w kolumnie

Musimy również odfiltrować wartości null z kolumny **Country**. W tym celu możesz użyć menu filtru w sposób zaprezentowany w kroku 3 lub możesz wykonać następujące czynności:

1. Kliknij prawym przyciskiem myszy w jednej z komórek kolumny **Country**, która zawiera wartość null.
2. W menu kontekstowym wybierz polecenie **Filtry tekstu -\> Nie równa się**.
3. Spowoduje to utworzenie nowego kroku filtru w celu usunięcia wierszy z wartościami null z kolumny **Country**.

**Krok 6.** Nazwanie zapytania

W tym kroku nadamy ostatecznemu zapytaniu nazwę **Euro Cup Winners**.

1. W okienku **Ustawienia zapytania** w polu tekstowym **Nazwa** wprowadź wartość **Euro Cup Winners**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

## <a name="task-3-create-visualizations-using-the-report-view"></a>Zadanie 3. Tworzenie wizualizacji przy użyciu widoku raportu
Nadaliśmy danym kształt, którego potrzebujemy do naszej analizy, a teraz możemy załadować tabelę wynikową do naszego raportu i utworzyć kilka wizualizacji.

**Krok 1.** Ładowanie zapytania do raportu

Aby załadować wyniki zapytania do programu Power BI Desktop i utworzyć raport, wybierzemy pozycję **Zamknij i załaduj** ze wstążki **Narzędzia główne**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)

Wywoła to ocenę zapytania i spowoduje załadowanie danych wynikowych tabeli do raportu. W programie Power BI Desktop wybierz ikonę **Raport**, aby wyświetlić widok Raport w programie Power BI Desktop.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage10.png)

Pola tabeli wynikowej będą widoczne w okienku **Pola** po prawej stronie widoku **Raport**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)

**Krok 2.** Tworzenie wizualizacji mapy

Aby utworzyć wizualizację, można przeciągnąć pola z **listy pól** i upuścić je na **kanwie raportu**.

1. Przeciągnij pole **Country** i upuść je na **kanwie raportu**. Spowoduje to utworzenie nowej wizualizacji na **kanwie raportu**. W tym przypadku mamy listę krajów, dlatego zostanie utworzona **Wizualizacja mapy**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage12.png)
2. Typ wizualizacji można łatwo zmienić, klikając inną ikonę w okienku **Wizualizacja**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage13.png)
3. Pozostawimy typ wizualizacji **Mapa**. Możemy również zmienić rozmiar wizualizacji, przeciągając jeden z jej narożników, aż do osiągnięcia żądanego rozmiaru.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)
4. Zwróć uwagę na to, że aktualnie wszystkie punkty na mapie mają ten sam rozmiar. Chcemy to zmienić, aby kraje, które więcej razy wygrały Mistrzostwa Europy, reprezentować większym punktem na mapie. W tym celu możemy przeciągnąć pole **Year** z **listy pól** do pola **Wartości** w dolnej połowie **okienka pól**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)

Jak widać wizualizacje w raporcie można bardzo łatwo dostosować, aby przedstawić dane w żądany sposób. Program Power BI Desktop zapewnia kompleksowy zbiór funkcji przeznaczonych do pobierania danych z różnorodnych źródeł danych i kształtowania ich odpowiednio do potrzeb analizy w celu zaprezentowania tych danych w interaktywnych, zaawansowanych wizualizacjach. Gdy raport jest gotowy, można [przekazać go do usługi Power BI](desktop-upload-desktop-files.md) i tworzyć na jego podstawie pulpity nawigacyjne, które następnie można udostępniać innym użytkownikom usługi Power BI.

To już koniec samouczka **Importowanie danych z Internetu**. Ukończony plik programu Power BI Desktop możesz pobrać [tutaj](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Data_From_The_Web.pbix).

## <a name="where-else-can-i-get-more-information"></a>Gdzie znajdę więcej informacji?
* [Zapoznaj się z innymi samouczkami dotyczącymi programu Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Obejrzyj filmy wideo dotyczące programu Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Odwiedź forum usługi Power BI](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Przeczytaj blog poświęcony usłudze Power BI](http://go.microsoft.com/fwlink/?LinkID=519327)

