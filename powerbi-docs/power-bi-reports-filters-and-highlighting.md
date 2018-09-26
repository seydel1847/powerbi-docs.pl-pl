---
title: Informacje o filtrach i wyróżnianiu w raportach usługi Power BI
description: Informacje o filtrach i wyróżnianiu w raportach usługi Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/26/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: de4fc463b02e8cae59f20216b5b1d30be431ae98
ms.sourcegitcommit: fb1885da7cf11367660edbf7b7346dc039ee9b5d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/26/2018
ms.locfileid: "47187173"
---
# <a name="about-filters-and-highlighting-in-power-bi-reports"></a>Informacje o filtrach i wyróżnianiu w raportach usługi Power BI
***Filtry*** usuwają wszystkie dane oprócz tych, na których chcesz skupić uwagę.  ***Wyróżnianie*** nie jest filtrowaniem, ponieważ nie usuwa danych, a jedynie wyróżnia pewien podzbiór widocznych danych; niewyróżnione dane pozostają widoczne, ale są przygaszone.

Istnieje wiele różnych sposobów filtrowania i wyróżniania raportów w usłudze Power BI. Zebranie wszystkich tych informacji w jednym artykule byłoby zbyt mylące, postanowiliśmy więc następująco podzielić ten temat:

* Wprowadzenie do filtrów i wyróżniania (artykuł, który aktualnie czytasz)
* Dostępne sposoby [tworzenia i używania filtrów oraz wyróżniania w widoku do edycji/raportach, których jesteś właścicielem](power-bi-report-add-filter.md). Posiadając uprawnienia do edytowania raportu, można tworzyć, modyfikować i usuwać filtry oraz wyróżnienia w raportach.
* Dostępne sposoby [używania filtrów oraz wyróżniania w raporcie udostępnionym lub w widoku do czytania raportu](consumer/end-user-reading-view.md). Dostępne możliwości są bardziej ograniczone, usługa Power BI wciąż udostępnia jednak szeroką gamę opcji filtrowania i wyróżniania.  
* [Szczegółowy przewodnik dotyczący kontrolek filtrowania i wyróżniania dostępnych w widoku do edycji](consumer/end-user-report-filter.md), w tym dokładny przegląd typów filtrów (np. daty i godziny, numeryczne, tekstowe) i różnica między opcjami podstawowymi i zaawansowanymi.
* Skoro już wiesz, jak wygląda domyślne działanie filtrów i wyróżniania, [dowiedz się, jak zmienić sposób wzajemnego filtrowania i wyróżniania dla wizualizacji na stronie](consumer/end-user-interactions.md)

> [!TIP]
> Skąd usługa Power BI wie, jak powiązane są dane?  Wykorzystuje ona relacje między różnymi tabelami i polami w źródłowym [modelu danych](https://support.office.com/article/Create-a-Data-Model-in-Excel-87e7a54c-87dc-488e-9410-5c75dbcb0f7b?ui=en-US&rs=en-US&ad=US), aby umożliwić wzajemne interakcje elementów na stronie raportu.
> 
> 

## <a name="introduction-to-filters-and-highlighting-in-reports-using-the-filters-pane"></a>Wprowadzenie do filtrów i wyróżniania w raportach z wykorzystaniem okienka filtrów
 W tym artykule przedstawiono podstawowe informacje dotyczące filtrowania i wyróżniania w usłudze Power BI.  W programie Power BI Desktop środowisko użytkownika jest jednak prawie identyczne.  

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Filtry i wyróżnianie może być stosowane za pomocą okienka **Filtry** lub przez dokonywanie wyboru bezpośrednio w raporcie (ad hoc, zobacz u dołu strony). Okienko Filtry zawiera używane w raporcie tabele i pola oraz ewentualne zastosowane filtry. Filtry dzielą się na **filtry na poziomie strony**, **filtry na poziomie raportu**, **filtry przeglądania szczegółowego** i **filtry na poziomie wizualizacji**.  Filtry na poziomie wizualizacji będą widoczne tylko po wybraniu wizualizacji na kanwie raportów.

> [!TIP]
> Jeśli obok filtra widoczny jest wyraz **Wszystkie**, oznacza to, że całe pole jest uwzględniane jako filtr.  Na przykład **Sieć(Wszystkie)** na poniższym zrzucie ekranu informuje nas, że ta strona raportu uwzględnia dane dotyczące wszystkich sieci sklepów.  Z drugiej strony filtr na poziomie strony **FiscalYear to 2013 lub 2014** informuje nas, że raport uwzględnia tylko dane za lata obrachunkowe 2013 i 2014.
> 
> 

## <a name="filters-in-reading-view-versus-editing-view"></a>Filtry w widoku do czytania a filtry w widoku do edycji
Istnieją dwa tryby interakcji z raportami: [Widok do czytania i Widok do edycji](consumer/end-user-reading-view.md).  Dostępne możliwości filtrowania zależą od trybu, w którym pracujesz.

* Widok do edycji umożliwia dodawanie filtrów raportu, strony, przeglądania szczegółowego i wizualizacji. Po zapisaniu raportu te filtry są zapisywane razem z nim, nawet jeśli otworzysz go w aplikacji mobilnej. Osoby wyświetlające raport w widoku do czytania mogą wchodzić w interakcje z filtrami, które zostały dodane, ale nie mogą dodawać nowych filtrów.
* W widoku do czytania możesz wchodzić w interakcje z dowolnymi filtrami, które istnieją już w raporcie, oraz zapisywać dokonywane wybory.  Nie można jednak dodawać nowych filtrów.

### <a name="the-filters-pane-in-reading-view"></a>Okienko filtrów w widoku do czytania
Jeśli masz tylko dostęp do raportu w widoku do czytania, okienko filtrów będzie wyglądać podobnie do poniższego:

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Ta strona raportu ma 6 filtrów na poziomie strony oraz 1 filtr na poziomie raportu.

Aby sprawdzić, czy istnieją filtry na poziomie wizualizacji, wybierz wizualizację. Na poniższej ilustracji wykres bąbelkowy ma 6 filtrów.

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

W widoku do czytania przeglądaj dane, modyfikując istniejące filtry. Wprowadzone zmiany są zapisywane z raportem, nawet wtedy, gdy raport jest otwierany w aplikacji mobilnej. Więcej informacji zawiera artykuł [Widok do czytania i widok do edycji w usłudze Power BI](consumer/end-user-reading-view.md)

### <a name="the-filters-pane-in-editing-view"></a>Okienko filtrów w widoku do edycji
Jeśli masz uprawnienia właściciela do raportu i otworzysz go w widoku do edycji, zobaczysz, że **Filtry** to tylko jedno z dostępnych okienek do edycji.

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Podobnie jak w Widoku do czytania (powyżej), można zauważyć, że ta strona raportu ma 6 filtrów na poziomie strony oraz 1 filtr na poziomie raportu. Wybierając wykres bąbelkowy, można sprawdzić, że ma także 6 filtrów na poziomie wizualizacji.

Widok do edycji daje jednak znacznie więcej możliwości dotyczących filtrów i wyróżniania. Podstawowa różnica polega na możliwości dodawania nowych filtrów. Informacje na temat wykonywania tej i wielu innych czynności można znaleźć w temacie [Dodawanie filtru do raportu](power-bi-report-add-filter.md)

## <a name="ad-hoc-filtering-and-highlighting"></a>Filtrowanie i wyróżnianie ad hoc
Wybierz pole na kanwie raportu, aby przefiltrować i wyróżnić pozostałą część strony. Aby usunąć puste miejsce w ramach tej samej wizualizacji, zaznacz je. Tego typu filtrowanie i wyróżnianie stanowi ciekawy sposób, aby szybko sprawdzać wpływy danych. Aby dostosować sposób działania tego typu wzajemnego filtrowania i wyróżniania, zobacz [Interakcje wizualne](consumer/end-user-interactions.md).

![](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)

Podczas zamykania raportu zmiany są zapisywane. Aby cofnąć filtrowanie i wrócić do domyślnego filtrowania, fragmentowania, przechodzenia do szczegółów i sortowania ustawionego przez autora raportu, wybierz pozycję **Przywróć domyślne** z górnego paska menu.

![](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

## <a name="next-steps"></a>Następne kroki
[Interakcja z filtrami i wyróżnianie (w widoku do czytania)](consumer/end-user-reading-view.md)

[Dodawanie filtru do raportu (w widoku do edycji)](power-bi-report-add-filter.md)

[Zapoznaj się z przewodnikiem po filtrach raportów](consumer/end-user-report-filter.md)

[Zmiana sposobu wzajemnego filtrowania i wyróżniania wizualizacji raportu](consumer/end-user-interactions.md)

Przeczytaj więcej na temat [raportów w usłudze Power BI](consumer/end-user-reports.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

