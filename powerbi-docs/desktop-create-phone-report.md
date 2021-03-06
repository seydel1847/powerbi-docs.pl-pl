---
title: Tworzenie raportów zoptymalizowanych pod kątem aplikacji mobilnych
description: Dowiedz się, jak zoptymalizować strony raportów dla aplikacji mobilnych usługi Power BI przez utworzenie pionowej wersji raportu przeznaczonej specjalnie dla telefonów i tabletów.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/10/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 8808391d0794ec4a487526cc5bbe4216fe0f75a6
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54275323"
---
# <a name="create-reports-optimized-for-the-power-bi-mobile-apps"></a>Tworzenie raportów zoptymalizowanych pod kątem aplikacji mobilnych usługi Power BI
Środowisko wyświetlania raportów w aplikacjach mobilnych na telefonie lub tablecie można ulepszyć. Utwórz raport w układzie pionowym przeznaczony specjalnie dla telefonów i tabletów. Optymalne wyświetlanie raportów możesz osiągnąć, dostosowując je w programie Power BI Desktop i usłudze Power BI przez zmianę rozmieszczenia i rozmiarów wizualizacji w układzie pionowym. Nie trzeba uwzględniać wszystkich wizualizacji. Ponadto można tworzyć [*dynamiczne* wizualizacje](#optimize-a-visual-for-any-size) i [dynamiczne fragmentatory](#enhance-slicers-to-to-work-well-in-phone-reports), które dostosowują swój rozmiar, gdy są wyświetlane w telefonie. Oprócz tego po dodaniu filtrów do raportu filtry te będą automatycznie wyświetlane w raporcie zoptymalizowanym. Czytelnicy raportu mogą je widzieć i filtrować raport za ich pomocą.

![Zoptymalizowany raport na telefonie](media/desktop-create-phone-report/desktop-create-phone-report-1.png)

## <a name="lay-out-a-portrait-version-of-a-report-page"></a>Projektowanie układu pionowej wersji strony raportu

Po utworzeniu raportu można go zoptymalizować pod kątem telefonów i tabletów.

1. W widoku raportu w programie Power BI Desktop na karcie **Widok** wybierz pozycję **Układ telefonu**.  
   
    ![Ikona układu telefonu](media/desktop-create-phone-report/desktop-create-phone-report-3.png)
   
    W usłudze Power BI wybierz kolejno pozycje **Edytuj raport** > **Układ mobilny**.

    Zostanie wyświetlona pusta kanwa w kształcie ekranu telefonu. Wszystkie wizualizacje ze strony oryginalnego raportu są wyświetlane w okienku Wizualizacje po prawej stronie.

3. Aby dodać wizualizację do układu telefonu, przeciągnij ją z okienka Wizualizacje na kanwę telefonu.
   
    Raporty na telefon używają układu siatki. Gdy przeciągasz wizualizacje na kanwę, są one przyciągane do siatki.
   
    ![Przeciąganie i upuszczanie wizualizacji](media/desktop-create-phone-report/desktop-create-phone-report-4.gif)
   
    Do strony raportu na telefon możesz dodać niektóre lub wszystkie wizualizacje ze strony głównego raportu. Każdą wizualizację można dodać tylko raz.

4. Rozmiar wizualizacji na siatce można zmieniać podobnie jak w przypadku kafelków na pulpitach nawigacyjnych i mobilnych pulpitach nawigacyjnych.
   
   Siatka raportu na telefon przystosowuje się do różnych rozmiarów telefonów, więc raport wygląda dobrze zarówno na telefonie z małym, jak i dużym ekranem.
   
   ![Zmiana rozmiaru wizualizacji](media/desktop-create-phone-report/desktop-create-phone-report-5.gif)

## <a name="optimize-a-visual-for-any-size"></a>Optymalizacja wizualizacji pod kątem dowolnej wielkości
Wizualizację na pulpicie nawigacyjnym lub w raporcie można ustawić jako *dynamiczną*. Wizualizacje takie mogą zmieniać się dynamicznie w celu wyświetlenia maksymalnej ilości danych i szczegółowych informacji niezależnie od rozmiaru ekranu. 

Gdy wizualizacja zmienia rozmiar, usługa Power BI nadaje priorytet widokowi danych. Może ona na przykład usuwać dopełnienia i automatycznie przenosić legendę na górę wizualizacji, tak aby wizualizacja dostarczała odpowiednią ilość informacji, nawet gdy się zmniejszy.

![Elastyczna zmiana rozmiaru wizualizacji](media/desktop-create-phone-report/desktop-create-phone-report-6.gif)

Włączenie lub wyłączenie elastyczności każdej wizualizacji zależy od użytkownika. Dowiedz się więcej na temat [optymalizacji wizualizacji](visuals/desktop-create-responsive-visuals.md).

## <a name="considerations-when-creating-phone-report-layouts"></a>Zagadnienia dotyczące tworzenia układów raportu na telefon
* W przypadku raportów o wielu stronach można zoptymalizować wszystkie strony lub tylko niektóre. 
* Jeśli kolor tła strony raportu został określony, raport na telefon będzie miał taki sam kolor tła.
* Nie można modyfikować ustawień formatowania tylko dla telefonu. Formatowanie jest wspólne dla głównego i mobilnego układu. Na przykład rozmiary czcionek będą takie same.
* Aby wprowadzić zmiany w wizualizacji, na przykład zmienić formatowanie, zestaw danych, filtry lub inny atrybut, wróć do zwykłego trybu tworzenia raportów.
* Usługa Power BI dostarcza domyślne tytuły i nazwy stron dla raportów na telefon w aplikacji mobilnej. Jeśli utworzono wizualizacje tekstowe dla tytułów i nazw stron w raporcie, rozważ rezygnację z dodawania ich do raportów na telefon.     

## <a name="remove-a-visual-from-the-phone-layout"></a>Usuwanie wizualizacji z układu na telefon
* Aby usunąć wizualizację, kliknij przycisk X w prawym górnym rogu wizualizacji na kanwie telefonu lub zaznacz ją i wybierz pozycję **Usuń**.
  
   Usunięcie wizualizacji w tym miejscu powoduje jej usunięcie wyłącznie na kanwie układu telefonu. Działanie to nie ma wpływu na wizualizację i oryginalny raport.
  
   ![Usuwanie wizualizacji](media/desktop-create-phone-report/desktop-create-phone-report-7.gif)

## <a name="enhance-slicers-to-work-well-in-phone-reports"></a>Ulepszanie fragmentatorów w celu zapewnienia ich prawidłowego działania w raportach na telefon
Fragmentatory oferują filtrowanie danych raportu na kanwie. Podczas projektowania fragmentatorów w zwykłym trybie tworzenia raportów można zmodyfikować niektóre ustawienia fragmentatorów, aby były bardziej użyteczne w raportach na telefon:

* Zdecyduj, czy czytelnicy raportu mogą wybierać tylko jeden czy więcej niż jeden element.
* Umieść ramkę wokół fragmentatora, aby ułatwić przeglądanie raportu.
* Ustaw fragmentator w pionie, w poziomie lub jako *dynamiczny*. 

Jeśli ustawisz fragmentator jako dynamiczny, zmiana jego kształtu i rozmiaru będzie powodować wyświetlanie większej lub mniejszej liczby opcji. Fragmentator może być długi, krótki, szeroki lub wąski. Jeśli odpowiednio go zmniejszysz, stanie się jedynie ikoną filtru na stronie raportu. 

![Dynamiczny fragmentator usługi Power BI](media/desktop-create-phone-report/desktop-create-phone-report-8.png)

Przeczytaj więcej na temat [tworzenia fragmentatorów dynamicznych](power-bi-slicer-filter-responsive.md).

## <a name="publish-a-phone-report"></a>Publikowanie raportu na telefon
* Aby opublikować raport w wersji na telefon, można [opublikować główny raport z programu Power BI Desktop do usługi Power BI](desktop-upload-desktop-files.md), a wersja na telefon zostanie opublikowana w tym samym czasie.
  
    Dowiedz się więcej o [udostępnianiu i uprawnieniach w usłudze Power BI](service-how-to-collaborate-distribute-dashboards-reports.md).

## <a name="view-optimized-and-unoptimized-reports-on-a-phone-or-tablet"></a>Wyświetlanie zoptymalizowanych i niezoptymalizowanych raportów na telefonie lub tablecie
W aplikacjach mobilnych na telefony usługa Power BI automatycznie wykrywa zoptymalizowane i niezoptymalizowane raporty na telefon. Jeśli dostępny jest raport zoptymalizowany pod kątem telefonu, aplikacja Power BI na telefon automatycznie otwiera raport w trybie raportu na telefon.

Jeśli nie jest dostępny żaden raport zoptymalizowany pod kątem telefonu, raporty będą otwierane w niezoptymalizowanym widoku poziomym.  

Podczas wyświetlania raportu na telefon zmiana orientacji telefonu na poziomą spowoduje otwarcie raportu w niezoptymalizowanym widoku z oryginalnym układem raportu bez względu na to, czy raport jest zoptymalizowany, czy nie.

Jeśli zoptymalizowane są tylko niektóre strony, w widoku pionowym czytelnicy zobaczą komunikat informujący, że raport jest dostępny w widoku poziomym.

![Niezoptymalizowana strona na telefonie](media/desktop-create-phone-report/desktop-create-phone-report-9.png)

Czytelnik raportu może obrócić telefon lub tablet na bok, aby wyświetlić stronę w widoku poziomym. Dowiedz się więcej na temat [podejmowania interakcji z raportami usługi Power BI zoptymalizowanymi pod kątem trybu pionowego](consumer/mobile/mobile-apps-view-phone-report.md).

## <a name="next-steps"></a>Następne kroki
* [Tworzenie widoku pulpitu nawigacyjnego dla telefonu w usłudze Power BI](service-create-dashboard-mobile-phone-view.md)
* [Wyświetlanie raportów usługi Power BI zoptymalizowanych pod kątem telefonu](consumer/mobile/mobile-apps-view-phone-report.md)
* [Tworzenie elastycznych wizualizacji zoptymalizowanych pod kątem dowolnego rozmiaru](visuals/desktop-create-responsive-visuals.md)
* Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

