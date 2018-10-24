---
title: Omówienie okienka Filtry usługi Power BI dla klientów
description: Omówienie okienka Filtry raportu w usłudze Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 09/25/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: c49e075bd7fbe2debb0b577a1ce2771491d5fac4
ms.sourcegitcommit: 52ac456bf2ac025b22ea634c28482f22e1cc19ac
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2018
ms.locfileid: "48908284"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Zapoznaj się z przewodnikiem dotyczącym okienka filtrów raportu
Ten artykuł opisuje okienko Filtry raportu w usłudze Power BI.

Istnieje wiele sposobów, aby filtrować dane w usłudze Power BI i zalecamy zapoznać się najpierw z artykułem [Informacje o filtrach i wyróżnianiu](../power-bi-reports-filters-and-highlighting.md).

![raport w przeglądarce](media/end-user-report-filter/power-bi-browser.png)

## <a name="working-with-the-report-filters-pane"></a>Praca z okienkiem Filtry raportu
Gdy współpracownik udostępni Ci raport, poszukaj okienka **Filtry**. Czasami jest ono zwinięte wzdłuż prawej krawędzi raportu. Wybierz je, aby je rozwinąć.   

![raport w przeglądarce](media/end-user-report-filter/power-bi-expanded.png)

Okienko Filtry zawiera filtry, które zostały dodane do raportu przez *projektanta* raportów. *Klienci* tacy jak Ty mogą wchodzić w interakcje z filtrami i zapisywać swoje zmiany, nie mogą jednak dodawać nowych filtrów do raportu.

W usłudze Power BI raporty zachowują wszelkie zmiany wprowadzone w okienku Filtry. Te zmiany są przekazywane do mobilnej wersji raportu. Aby zresetować okienko Filtry do wartości domyślnych projektanta, wybierz pozycję **Przywróć domyślne** z górnego paska menu.     

## <a name="open-the-filters-pane"></a>Otwieranie okienka Filtry
Po otwarciu raportu okienko Filtry jest wyświetlane wzdłuż prawej strony kanwy raportu. Jeśli okienko nie jest widoczne, wybierz strzałkę w prawym górnym rogu, aby je rozwinąć.  

W tym przykładzie wybraliśmy wizualizację, która ma 6 filtrów. Strona raportu ma także filtry wyświetlane w pozycji **Filtry na poziomie strony**. Istnieje też jeden [filtr przeglądania szczegółowego](../power-bi-report-add-filter.md), zaś cały raport ma też filtr: **FiscalYear** to 2013 lub 2014.

![lista filtrów](media/end-user-report-filter/power-bi-filter-list.png)

Obok nazwy niektórych filtrów wyświetla się słowo **Wszystkie**, co oznacza, że filtr uwzględnia wszystkie wartości.  Na przykład wartość **Chain (Wszystkie)** na poniższym zrzucie ekranu informuje nas, że ta strona raportu uwzględnia dane dotyczące wszystkich sieci sklepów.  Z drugiej strony filtr na poziomie strony **FiscalYear to 2013 lub 2014** informuje nas, że raport uwzględnia tylko dane za lata obrachunkowe 2013 i 2014.

Każda osoba wyświetlająca ten raport może wchodzić w interakcje z tymi filtrami.

* Wyświetlenie szczegółów filtru przez umieszczenie nad nim kursora i wybranie strzałki obok filtru.
  
   ![pokazuje wybraną pozycję Lindseys](media/end-user-report-filter/power-bi-expan-filter.png)
* Zmiana filtru, na przykład zmiana sieci z **Lindseys** na **Fashions Direct**.
  
     ![pokazuje wybraną pozycję Fashions Direct](media/end-user-report-filter/power-bi-filter-chain.png)

* Zresetowanie filtrów do pierwotnego stanu przez wybranie pozycji **Przywróć domyślne** z górnego paska menu.    
    ![przywróć domyślne](media/end-user-report-filter/power-bi-reset-to-default.png)
    
* Usunięcie filtru przez wybranie symbolu **x** obok jego nazwy.
  
  Usunięcie filtru spowoduje usunięcie go z listy, ale nie spowoduje usunięcia danych z raportu.  Jeśli na przykład usuniesz filtr **FiscalYear to 2013 lub 2014**, dane roku obrachunkowego pozostaną w raporcie, ale nie będzie on już filtrowany, aby wyświetlać tylko dane dla roku 2013 i 2014. Będą wyświetlane dane dostępne dla wszystkich lat obrachunkowych.  Jednak po usunięciu filtru nie będzie można go modyfikować, ponieważ zostanie usunięty z listy. Lepszym rozwiązaniem jest wyczyszczenie filtru przy użyciu ikony gumki ![ikona gumki](media/end-user-report-filter/power-bi-eraser-icon.png).
  
  ![wyróżnione x](media/end-user-report-filter/power-bi-delete-filter.png)



## <a name="clear-a-filter"></a>Czyszczenie filtru
 W zaawansowanym lub podstawowym trybie filtrowania wybierz ikonę gumki  ![ikona gumki](media/end-user-report-filter/pbi_erasericon.jpg) aby wyczyścić filtr. 


## <a name="types-of-filters-text-field-filters"></a>Typy filtrów: filtry pól tekstowych
### <a name="list-mode"></a>Tryb listy
Zaznaczenie pola wyboru powoduje wybranie lub anulowanie wyboru wartości. Pola wyboru **Wszystkie** można użyć do przełączenia stanu (zaznaczenia lub usunięcia zaznaczenia) wszystkich pól wyboru. Pola wyboru reprezentują wszystkie dostępne wartości dla danego pola.  Dostosowanie filtru powoduje aktualizację instrukcji w oparciu o wybrane opcje. 

![filtr trybu listy](media/end-user-report-filter/pbi_restatement.png)

Zwróć uwagę na zmianę instrukcji na „to Amarilla lub Carretera”

### <a name="advanced-mode"></a>Tryb zaawansowany
Wybierz pozycję **Filtrowanie zaawansowane**, aby przejść do trybu zaawansowanego. Wskaż pola do uwzględnienia za pomocą kontrolek list rozwijanych i pól tekstowych. Wybierając pozycję **I** albo **Lub**, można tworzyć złożone wyrażenia filtrowania. Po ustawieniu odpowiednich wartości wybierz przycisk **Zastosuj filtr**.  

![tryb zaawansowany](media/end-user-report-filter/aboutfilters.png)

## <a name="types-of-filters-numeric-field-filters"></a>Typy filtrów: filtry pól liczbowych
### <a name="list-mode"></a>Tryb listy
Jeśli wartości są wartościami skończonymi, po wybraniu nazwy pola zostanie wyświetlona lista.  Zobacz **Filtry pól testowych** &gt; **Tryb listy** powyżej, aby uzyskać pomoc dotyczącą używania pól wyboru.   

### <a name="advanced-mode"></a>Tryb zaawansowany
Jeśli wartości są wartościami nieskończonymi lub reprezentują zakres, po wybraniu nazwy pola zostanie otwarty zaawansowany tryb filtru. Określ zakres wartości, które mają być wyświetlane, za pomocą listy rozwijanej i pól tekstowych. 

![filtr zaawansowany](media/end-user-report-filter/pbi_dropdown-and-text.png)

Wybierając pozycję **I** albo **Lub**, można tworzyć złożone wyrażenia filtrowania. Po ustawieniu odpowiednich wartości wybierz przycisk **Zastosuj filtr**.

## <a name="types-of-filters-date-and-time"></a>Typy filtrów: data i godzina
### <a name="list-mode"></a>Tryb listy
Jeśli wartości są wartościami skończonymi, po wybraniu nazwy pola zostanie wyświetlona lista.  Zobacz **Filtry pól testowych** &gt; **Tryb listy** powyżej, aby uzyskać pomoc dotyczącą używania pól wyboru.   

### <a name="advanced-mode"></a>Tryb zaawansowany
Jeśli wartości pól reprezentują datę lub godzinę, przy użyciu filtrów daty/godziny można określić czas rozpoczęcia i zakończenia.  

![filtr daty/godziny](media/end-user-report-filter/pbi_date-time-filters.png)


## <a name="next-steps"></a>Następne kroki
[Dowiedz się, jak i dlaczego dochodzi do wzajemnego filtrowania i wyróżniania krzyżowego wizualizacji na stronie raportu](end-user-interactions.md)