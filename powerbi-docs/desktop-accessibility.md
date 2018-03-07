---
title: "Ułatwienia dostępu w raportach programu Power BI Desktop"
description: "Funkcje i sugestie dotyczące tworzenia dostępnych raportów w programie Power BI Desktop."
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
ms.date: 11/21/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: c0e11a46e6e228da2f2ca8ac3f7be63ae20c1d92
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="accessibility-in-power-bi-desktop-reports"></a>Ułatwienia dostępu w raportach programu Power BI Desktop
Program **Power BI Desktop** zawiera funkcje, które umożliwiają osobom niepełnosprawnym łatwiejsze korzystanie z raportów programu **Power BI Desktop**. Te funkcje obejmują możliwość korzystania z raportu za pomocą klawiatury lub czytnika ekranu, używania klawisza TAB do przenoszenia fokusu na różne obiekty na stronie oraz celowe używanie znaczników w wizualizacjach.

![Używanie różnych znaczników wykresów liniowych i warstwowych w celu ułatwienia dostępu](media/desktop-accessibility/accessibility_01.png)

> [!NOTE]
> Te funkcje ułatwień dostępu są dostępne w programie **Power BI Desktop** w wersji z czerwca 2017 r. i nowszych. W następnych wersjach planowane jest wprowadzenie kolejnych funkcji ułatwień dostępu.
> 
> 

## <a name="consuming-a-power-bi-desktop-report-with-a-keyboard-or-screen-reader"></a>Korzystanie z raportów programu Power BI Desktop za pomocą klawiatury lub czytnika ekranu
W wersji programu **Power BI Desktop** z września 2017 r. i nowszych możesz nacisnąć klawisz **?**, aby wyświetlić okno z opisem skrótów klawiaturowych ułatwień dostępu dostępnych w programie **Power BI Desktop**.

![Naciśnij klawisz ? w programie Power BI Desktop, aby wyświetlić skróty klawiaturowe ułatwień dostępu.](media/desktop-accessibility/accessibility_03.png)

Dzięki udoskonalonym ułatwieniom dostępu można korzystać z raportu programu **Power BI Desktop** za pomocą klawiatury lub czytnika ekranu, używając następujących technik:

Możesz **przełączać fokus** pomiędzy kartami stron raportu lub obiektami na dowolnej stronie raportu, używając kombinacji klawiszy **Ctrl+F6**.

* Gdy fokus jest ustawiony na *kartach stron raportu*, użyj klawisza *Tab* lub klawiszy *strzałek*, aby przenieść fokus z jednej strony raportu do kolejnej. Tytuł strony raportu i to, czy jest aktualnie zaznaczona, jest odczytywane przez czytnik ekranu. Aby załadować stronę raportu, na której umieszczono fokus, użyj klawisza *Enter* lub *Spacja*.
* Gdy fokus jest ustawiony na załadowaną *stronę raportu*, użyj klawisza *Tab*, aby przenieść fokus na kolejne obiekty na stronie, w tym pola tekstowe, obrazy, kształty lub wykresy. Czytnik ekranu odczytuje typ obiektu i opis tego obiektu wprowadzony przez jego autora. 

Możesz nacisnąć klawisze**Alt+Shift+F10**, aby przenieść fokus na menu wizualizacji.

Możesz nacisnąć klawisze **Alt+Shift+F11**, aby zaprezentować dostępną wersję okna *Pokaż dane*.

![W programie Power BI Desktop naciśnij klawisze Alt+Shift+F11, aby wyświetlić dostępne okno Pokaż dane dla wizualizacji.](media/desktop-accessibility/accessibility_04.png)

Te dodatki ułatwień dostępu zostały utworzone, aby umożliwić użytkownikom pełne korzystanie z raportów programu **Power BI Desktop** przy użyciu klawiatury i czytnika ekranu.

## <a name="tips-for-creating-accessible-reports"></a>Wskazówki dotyczące tworzenia raportów z ułatwieniami dostępu
Poniższe wskazówki mogą pomóc tworzyć bardziej dostępne raporty programu **Power BI Desktop**.

* W przypadku wizualizacji **liniowych**, **warstwowych**, **kombi**, **punktowych** i **bąbelkowych** włącz znaczniki i użyj innego *kształtu znacznika* dla każdego wiersza.
  
  * Aby włączyć *znaczniki*, wybierz sekcję **Formatowanie** w okienku **Wizualizacje**, rozwiń sekcję **Kształty**, a następnie przewiń w dół, aż znajdziesz przełącznik **Znaczniki**. Ustaw go w pozycji *Włączone*.
  * Następnie wybierz nazwy poszczególnych wierszy (lub obszarów, jeśli korzystasz z wykresu **warstwowego**) z pola listy rozwijanej w sekcji **Kształty**. Poniżej listy rozwijanej możesz dostosować wiele aspektów znacznika zastosowanego do wybranego wiersza, w tym jego kształt, kolor i rozmiar.
  
  ![Używanie różnych znaczników wykresów liniowych i warstwowych w celu ułatwienia dostępu](media/desktop-accessibility/accessibility_01.png)
  
  * Używanie innego *kształtu znacznika* dla każdego wiersza ułatwia użytkownikowi raportu odróżnienie wierszy (lub obszarów).
* W nawiązaniu do poprzedniego punktu — nie należy używać koloru do przekazywania informacji. Pomocne jest używanie kształtów w wierszach (znaczników, jak opisano w poprzednich punktach).
* Wybierz z galerii motywów *motyw*, który ma duży kontrast i jest przyjazny daltonistom, i zaimportuj go, używając funkcji [**Motywy** w wersji zapoznawczej](desktop-report-themes.md).
* Dla każdego obiektu w raporcie wprowadź *tekst alternatywny*. Daje to gwarancję. że użytkownicy raportu zrozumieją, co chcesz przekazać za pomocą wizualizacji, nawet jeśli nie widzą wizualizacji, obrazów, kształtów lub pól tekstowych. Możesz wprowadzić *tekst alternatywny* dla dowolnego obiektu w raporcie programu **Power BI Desktop**, zaznaczając ten obiekt (na przykład wizualizację, kształt itp.), a następnie w okienku **Wizualizacje** wybierając sekcję **Formatowanie**, rozwijając listę **Ogólne**, a następnie przewijając w dół i wypełniając pole tekstowe **Tekst alternatywny**.
  
  ![Można dodać tekst alternatywny do dowolnego obiektu w raporcie, wybierając kolejno pozycje Wizualizacje > Formatowanie > Ogólne > Tekst alternatywny.](media/desktop-accessibility/accessibility_02.png)
* Upewnij się, że w raportach zastosowano odpowiedni kontrast pomiędzy kolorem tekstu a kolorem tła.
* Użyj rozmiarów tekstu i czcionek, które można łatwo odczytać. Mały tekst lub czcionki, które trudno odczytać, nie ułatwiają dostępu.
* Do wszystkich wizualizacji dołącz tytuł, etykiety osi i etykiety danych.

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia
Istnieje kilka znanych problemów i ograniczeń dotyczących funkcji ułatwień dostępu. Opisano je na poniższej liście:

* Oprogramowanie JAWS jest obsługiwane w raportach wyświetlanych w **usłudze Power BI**. Dotyczy to również osadzonych raportów. Oprogramowanie JAWS jest również obsługiwane w programie **Power BI Desktop**, należy jednak otworzyć czytnik ekranu przed otwarciem plików programu **Power BI Desktop**, aby czytnik ekranu działał poprawnie.

## <a name="next-steps"></a>Następne kroki
* [Używanie motywów raportów w programie Power BI Desktop (wersja zapoznawcza)](desktop-report-themes.md)

