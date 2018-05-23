---
title: Eksplorowanie raportów w aplikacjach mobilnych Power BI
description: Dowiedz się więcej na temat przeglądania raportów i korzystania z nich w aplikacji mobilnej Power BI na swoim telefonie lub tablecie. Raporty możesz tworzyć w usłudze Power BI lub programie Power BI Desktop, a następnie korzystać z nich w aplikacjach mobilnych.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 03/22/2018
ms.author: maggies
ms.openlocfilehash: 6d7ab55c3ecbb13b40354f67263d597f0e1179f7
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Eksplorowanie raportów w aplikacjach mobilnych Power BI
Dotyczy:

| ![Telefon iPhone](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Tablet iPad](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Telefon z systemem Android](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Tablet z systemem Android](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Urządzenia z systemem Windows 10](media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| Telefony iPhone |Urządzenia iPad |Telefony z systemem Android |Tablety z systemem Android |Urządzenia z systemem Windows 10 |

Raport usługi Power BI to interaktywny widok danych z wizualizacjami reprezentującymi różne wyniki i szczegółowe informacje uzyskane na podstawie tych danych. Wyświetlanie raportów w aplikacjach mobilnych Power BI to trzeci krok w procesie składającym się z trzech kroków.

1. [Tworzenie raportów w programie Power BI Desktop](desktop-report-view.md). Możesz nawet [zoptymalizować raport pod kątem telefonów](mobile-apps-view-phone-report.md) w programie Power BI Desktop. 
2. Publikowanie tych raportów w usłudze Power BI [(https://powerbi.com)](https://powerbi.com) lub na [Serwerze raportów usługi Power BI](report-server/get-started.md).  
3. Korzystanie z tych raportów w aplikacjach mobilnych Power BI.

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>Otwieranie raportu usługi Power BI w aplikacji mobilnej
Raporty usługi Power BI są przechowywane w różnych miejscach w aplikacji mobilnej, w zależności od tego, skąd pochodzą. Mogą znajdować się w sekcji Aplikacje, Udostępnione dla mnie lub Obszary robocze (w tym Mój obszar roboczy) albo na serwerze raportów. Czasami przejście do raportu odbywa się za pośrednictwem powiązanego pulpitu nawigacyjnego, a czasami jest on na liście.

* Na pulpicie nawigacyjnym naciśnij ikonę wielokropka (...) w prawym górnym rogu kafelka i wybierz polecenie **Otwórz raport**.
  
  ![Otwieranie raportu](media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  Opcja otworzenia raportu nie jest dostępna dla wszystkich kafelków. Na przykład naciśnięcie kafelka utworzonego przez zadanie pytania w polu Pytania i odpowiedzi nie spowoduje otworzenia raportu. 
  
  Na telefonie raport zostanie otwarty w orientacji poziomej, chyba że jest on [zoptymalizowany pod kątem wyświetlania na telefonie](mobile-reports-in-the-mobile-apps.md#view-reports-optimized-for-phones).
  
  ![Raport na telefonie w orientacji poziomej](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-landscape.png)

## <a name="view-reports-optimized-for-phones"></a>Wyświetlanie raportów zoptymalizowanych pod kątem telefonów
Autorzy raportów usługi Power BI mogą utworzyć układ raportu zoptymalizowany specjalnie pod kątem telefonów. Strony raportów zoptymalizowane pod kątem telefonów mają dodatkowe funkcje: na przykład można wyszczególniać i sortować wizualizacje oraz uzyskiwać dostęp do [filtrów, które autor raportu dodał do strony raportu](mobile-apps-view-phone-report.md#filter-the-report-page-on-a-phone). W telefonie zostanie otwarty raport odfiltrowany do wartości filtrowanych w raporcie w Internecie z komunikatem informującym o aktywnych filtrach na stronie. Filtry można zmienić w telefonie.

Zoptymalizowany raport ma na liście raportów specjalną ikonę ![Ikona raportu zoptymalizowanego pod kątem telefonów](media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png):

![Otwieranie raportu zoptymalizowanego pod kątem telefonów](media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

Po wyświetleniu tego raportu na telefonie zostanie on otwarty w widoku pionowym.

![Raport w widoku pionowym](media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

 Raport może zawierać zarówno strony zoptymalizowane pod kątem telefonów, jak i niezoptymalizowane. W takim przypadku podczas przeglądania raportu widok będzie się zmieniać z pionowego na poziomy, odpowiednio dla każdej strony.

Dowiedz się więcej na temat [raportów zoptymalizowanych pod kątem wyświetlania na telefonach](mobile-apps-view-phone-report.md).

## <a name="use-slicers-to-filter-a-report"></a>Filtrowanie raportu za pomocą fragmentatorów
Podczas projektowania raportu w programie Power BI Desktop lub za pomocą usługi Power BI należy wziąć pod uwagę możliwość [dodania fragmentatorów do strony raportu](power-bi-visualization-slicers.md). Możesz razem ze współpracownikami korzystać z fragmentatorów do filtrowania strony w przeglądarce i w aplikacjach mobilnych. Po wyświetleniu raportu w telefonie możecie wyświetlać fragmentatory i korzystać z nich w orientacji poziomej oraz na stronie zoptymalizowanej pod kątem orientacji pionowej telefonu. Wartość wybrana w filtrze lub fragmentatorze w przeglądarce zostanie również wybrana w przypadku wyświetlenia strony w aplikacji mobilnej. Zobaczysz komunikat informujący o aktywnych filtrach na stronie.  

* Wybranie wartości we fragmentatorze na stronie raportu spowoduje przefiltrowanie innych wizualizacji na tej stronie.
  
  ![Fragmentator raportu](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  Na tej ilustracji fragmentator filtruje wykres kolumnowy, aby wyświetlić tylko wartości z lipca.

## <a name="cross-filter-and-highlight-a-report"></a>Filtrowanie krzyżowe i wyróżnianie raportu
Po wybraniu wartości w wizualizacji inne wizualizacje nie są filtrowane. Zamiast tego wyróżniane są powiązane wartości w innych wizualizacjach.

* Naciśnij wartość w wizualizacji.
  
  ![Filtrowanie krzyżowe strony](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  Po naciśnięciu kolumny Large w jednej wizualizacji wyróżniane są powiązane wartości w innych wizualizacjach. 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>Sortowanie wizualizacji na urządzeniu iPad lub tablecie
* Naciśnij wykres, ikonę wielokropka (**...**), a następnie nazwę pola.
  
   ![Sortowanie wizualizacji](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* Aby odwrócić porządek sortowania, ponownie naciśnij ikonę wielokropka (**...**) i tę samą nazwę pola.

## <a name="drill-down-on-an-ipad-or-a-tablet"></a>Przechodzenie do szczegółów na urządzeniu iPad lub tablecie
Jeśli autor raportu dodał możliwość przechodzenia do szczegółów wizualizacji, na urządzeniu iPad lub tablecie możesz przejść do szczegółów w wizualizacji, aby zobaczyć wartości, które tworzą jedną jej część. [Możliwość przechodzenia do szczegółów możesz dodać do wizualizacji](power-bi-visualization-drill-down.md) w programie Power BI Desktop lub usłudze Power BI. 

> [!NOTE]
> Obecnie przechodzenie do szczegółów nie działa w przypadku map na urządzeniu iPad ani tablecie.
> 
> 

* Naciśnij wizualizację. Jeśli w górnych rogach znajdują się ikony strzałek w górę i w dół ![Ikony Uogólnij i Przejdź do szczegółów](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-down.png), możesz przejść do szczegółów. Aby przejść do szczegółów dotyczących jednej wartości, naciśnij strzałkę w prawym górnym rogu, a następnie naciśnij wartość w wizualizacji — w tym przypadku ciemnoniebieski bąbelek FD-04.
  
  ![Przechodzenie do szczegółów w wizualizacji](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-one.png)
* Aby uogólnić, naciśnij strzałkę w górę w lewym górnym rogu.
  
  ![Uogólnianie](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up.png)

## <a name="go-back-to-my-workspace"></a>Powrót do sekcji Mój obszar roboczy
* Naciśnij strzałkę obok nazwy raportu, a następnie naciśnij polecenie **Mój obszar roboczy**.
  
  ![Powrót](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-back.png)

## <a name="next-steps"></a>Następne kroki
* [Wyświetlanie raportów usługi Power BI zoptymalizowanych pod kątem telefonu i interakcje z nimi](mobile-apps-view-phone-report.md)
* [Tworzenie wersji raportu zoptymalizowanej pod kątem telefonów](desktop-create-phone-report.md)
* Masz pytania? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

