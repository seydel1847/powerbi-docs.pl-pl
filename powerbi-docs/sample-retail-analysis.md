---
title: "Próbka analizy handlu detalicznego dla usługi Power BI: krótki przewodnik"
description: "Próbka analizy handlu detalicznego dla usługi Power BI: krótki przewodnik"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 12/04/2017
ms.author: mihart
ms.openlocfilehash: 09e245e625c9e0859f93837e56b564218e327926
ms.sourcegitcommit: 54da95f184dd0f7bb59bb0bc8775a1d93129b195
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2017
---
# <a name="retail-analysis-sample-for-power-bi-take-a-tour"></a>Próbka analizy handlu detalicznego dla usługi Power BI: krótki przewodnik

Ten przykładowy pulpit nawigacyjny dla branży i raport będący jego podstawą przedstawiają analizę danych sprzedaży detalicznej towarów w wielu sklepach i regionach. Metryki dotyczą porównania tegorocznej i ubiegłorocznej wydajności w następujących obszarach: sprzedaż, liczba jednostek, marża brutto i odchylenia, a także analizy nowych sklepów. Są to prawdziwe dane pochodzące z firmy obviEnce ([www.obvience.com](http://www.obvience.com)) przedstawione w sposób anonimowy.

[!Note] Możesz również [pobrać sam zestaw danych (skoroszyt programu Excel) omawiany w tym przykładzie](http://go.microsoft.com/fwlink/?LinkId=529778). Skoroszyt zawiera arkusze programu Power View, które można wyświetlać i modyfikować.  Aby wyświetlić nieprzetworzone dane, wybierz pozycje **Power Pivot > Zarządzaj**. 

![](media/sample-retail-analysis/retail1.png)

## <a name="start-on-the-dashboard-and-open-the-report"></a>Rozpoczynanie z poziomu pulpitu nawigacyjnego i otwieranie raportu
1. Na pulpicie nawigacyjnym wybierz kafelek „Total Stores” (Łączna liczba sklepów):
   
   ![](media/sample-retail-analysis/retail-analysis-7.png)  
   
   Nastąpi przekierowanie na stronę raportu „Store Sales Overview” (Przegląd danych dotyczących sprzedaży). Jak widać, firma dysponuje 104 sklepami, spośród których 10 zostało niedawno otwartych. Sklepy należą do dwóch sieci: Fashions Direct i Lindseys. Średnia powierzchnia sklepów Fashions Direct jest większa.
2. Na wykresie kołowym wybierz pozycję **Fashions Direct**.
   
   ![](media/sample-retail-analysis/retail3.png)  
   
   Zwróć uwagę na wyniki zaprezentowane na wykresie bąbelkowym:
   
   ![](media/sample-retail-analysis/pbi_sample_retanlbubbles.png)  
   
   W regionie FD-01 występuje najwyższa średnia sprzedaż na metr kwadratowy, region FD-02 ma najniższe odchylenie wartości sprzedaży w porównaniu z ostatnim rokiem, a w regionach FD-03 i FD-04 odnotowano najgorsze wyniki.
3. Wybierz pojedyncze bąbelki lub inne wykresy, aby zobaczyć jak poszczególne elementy są ze sobą powiązane.
4. Aby powrócić do pulpitu nawigacyjnego, wybierz odpowiednią nazwę w górnym pasku nawigacyjnym (linki do stron nadrzędnych). 
   
   ![](media/sample-retail-analysis/power-bi-breadcrumbs.png)
5. Na pulpicie nawigacyjnym wybierz kafelek o nazwie „This Year’s Sales” (Sprzedaż w tym roku).
   
   ![](media/sample-retail-analysis/pbi_sample_retanlthisyrsales.png)
   
   Jest to równoważne wprowadzeniu wyrażenia „This year sales” (Sprzedaż w tym roku) w polu pytań.
   
   Zostanie wyświetlony następujący ekran:
   
   ![](media/sample-retail-analysis/retail7.png)

## <a name="review-a-tile-created-with-power-bi-qa"></a>Przegląd kafelka utworzonego za pomocą aparatu Pytania i odpowiedzi usługi Power BI
Teraz postaramy się uzyskać bardziej szczegółowe informacje.

1. W polu pytań dodaj wyrażenie „this year sales **by district**” (sprzedaż w tym roku według regionu). Sprawdź otrzymany wynik: odpowiedź jest automatycznie umieszczana na wykresie słupkowym i sugerowane są inne wyrażenia:
   
   ![](media/sample-retail-analysis/retail8.png)
2. Teraz zmień pytanie na „this year sales **by zip and chain**” (sprzedaż w tym roku według kodu pocztowego i nazwy sieci sklepów).
   
   Zauważ, że w miarę wpisywania uzyskujesz odpowiedź w postaci odpowiednich wykresów.
3. Poeksperymentuj z różnymi pytaniami i zobacz jakie otrzymasz wyniki.
4. W dowolnym momencie możesz powrócić do pulpitu nawigacyjnego.

## <a name="dive-deeper-into-the-data"></a>Szczegółowe informacje o danych
Teraz przyjrzyjmy się bardziej szczegółowym danym, uwzględniając wyniki osiągane w poszczególnych regionach.

1. Na pulpicie nawigacyjnym wybierz kafelek porównujący sprzedaż z tego roku ze sprzedażą z roku poprzedniego.
   
   ![](media/sample-retail-analysis/pbi_sample_retanlareacht.png)
   
   Zwróć uwagę na dużą zmienność wartości procentowej odchylenia w odniesieniu do ostatniego roku i na szczególnie niekorzystne wyniki odnotowane w styczniu, kwietniu i lipcu.
   
   ![](media/sample-retail-analysis/pbi_sample_retanlsalesvarcol.png)
   
   Przekonajmy się, czy uda nam się ustalić, co może być powodem otrzymania tak słabych rezultatów.
2. Wybierz wykres bąbelkowy, a następnie pozycję **020-Mens** (020-Mężczyźni).
   
   ![](media/sample-retail-analysis/retail11.png)  
   
   Zauważ, że spadek odnotowany w kwietniu miał większy wpływ na ogólną sytuację firmy niż na samą kategorię mężczyzn (chociaż dane ze stycznia i lipca i tak były niezadowalające).
3. Teraz wybierz bąbelek **010-Womens** (010-Kobiety).
   
   ![](media/sample-retail-analysis/retail12.png)
   
   Kategoria uwzględniająca kobiety wypadła znacznie gorzej w stosunku do ogólnej sytuacji firmy we analizowanych wszystkich miesiącach i o wiele gorzej w prawie każdym miesiącu w porównaniu z rokiem poprzednim.
4. Ponownie wybierz bąbelek, aby wyczyścić filtr.

## <a name="try-out-the-slicer"></a>Używanie fragmentatora
Przyjrzyjmy się danym dotyczącym poszczególnych regionów.

1. Z fragmentatora po lewej stronie wybierz osobę o nazwisku Allan Guinot.
   
   ![](media/sample-retail-analysis/retail13.png)
   
   Zwróć uwagę, że w regionie zarządzanym przez Allana wyniki sprzedaży w marcu i czerwcu były lepsze od zeszłorocznych.
2. Mając nadal zaznaczone nazwisko Allana, wybierz bąbelek dotyczący danych na temat kobiet.
   
   ![](media/sample-retail-analysis/power-bi-allan.png)
   
   Zauważ, że w przypadku kategorii uwzględniającej kobiety zarządzany przez niego region nigdy nawet nie zdołał osiągnąć sprzedaży na tym samym poziomie co w zeszłym roku.
3. Wypróbuj kombinacje innych kierowników regionów z poszczególnymi kategoriami. Jakie wnioski zauważasz?
4. W dowolnym momencie powróć do pulpitu nawigacyjnego.

## <a name="what-is-our-data-telling-us-about-sales-growth-this-year"></a>Co o tegorocznym wzroście sprzedaży mówią nam dane?
Ostatni aspekt, który przeanalizujemy dotyczy rozwoju firmy, czyli nowych sklepów otwartych w tym roku.

1. Wybierz kafelek „Stores Opened This Year” (Sklepy otwarte w tym roku).
   
   ![](media/sample-retail-analysis/retail15.png)
   
   Jak widać na kafelku, sieć Fashions Direct otwarła w tym roku więcej sklepów niż sieć Lindseys.
2. Przyjrzyj się wykresowi „Sales Per Sq Ft by Name” (Sprzedaż na m2 według nazwy).
   
   ![](media/sample-retail-analysis/retail14.png)
   
    Obserwujemy dość znaczną różnicę w średniej sprzedaży na m2 w nowych sklepach.
3. Kliknij element legendy dotyczący sieci Fashions Direct na prawym górnym wykresie. Nawet w obrębie tej samej sieci wyniki sprzedaży najlepszego sklepu (Winchester Fashions Direct) znacznie przewyższają wyniki najgorszego sklepu (Cincinnati 2 Fashions Direct), odnotowując odpowiednio wartości 21,22 USD i 12,86 USD.
   
   ![](media/sample-retail-analysis/power-bi-lindseys.png)
4. Z poziomu fragmentatora kliknij pozycję Winchester Fashions Direct i przyjrzyj się wykresowi liniowemu. Pierwsze wyniki sprzedaży uwzględniają dane z lutego.
5. We fragmentatorze kliknij sklep Cincinnati 2 Fashions. Zostanie wyświetlony wykres liniowy, z którego dowiesz się, że został on otwarty w czerwcu i jest najprawdopodobniej najgorzej prosperującym sklepem.
6. Tak jak poprzednio, wypróbuj inne możliwości, klikając różne słupki, linie i bąbelki na wykresach. Jakie inne wnioski jesteś w stanie wyciągnąć?

Pracując na danych w tym środowisku, nie musisz się niczego obawiać. Zawsze możesz zrezygnować z zapisania wprowadzonych zmian. Jeśli jednak je zapiszesz, możesz przejść do obszaru Pobieranie danych i pobrać nową kopię zestawu danych użytego w tym przykładzie.

## <a name="connect-to-your-data"></a>Łączenie z danymi
Mamy nadzieję, że dzięki temu przewodnikowi wiesz już, że pulpity nawigacyjne usługi Power BI, aparat Pytania i odpowiedzi oraz raporty mogą okazać się niezastąpione w uzyskiwaniu informacji o danych sieci sprzedaży. Teraz Twoja kolej. Połącz się ze swoimi danymi. Usługa Power BI umożliwia nawiązanie połączenia z różnymi źródłami danych. Dowiedz się więcej o [rozpoczynaniu pracy z usługą Power BI](service-get-started.md).

## <a name="next-steps"></a>Następne kroki
* [Pobieranie przykładowych pakietów zawartości dotyczących analizy handlu detalicznego](sample-tutorial-connect-to-the-samples.md)    
* [Pobieranie przykładowego skoroszytu programu Excel dla usługi Power BI](http://go.microsoft.com/fwlink/?LinkId=529778)    
* [Pobieranie danych (dla usługi Power BI)](service-get-data.md)    
* [Power BI — podstawowe pojęcia](service-basic-concepts.md)    
* Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)
