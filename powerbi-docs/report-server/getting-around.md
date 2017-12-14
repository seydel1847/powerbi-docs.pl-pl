---
title: "Podstawowe informacje o portalu internetowym Serwera raportów usługi Power BI"
description: "Informacje dotyczące nawigowania i pracy w portalu internetowym Serwera raportów usługi Power BI."
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/12/2017
ms.author: maggies
ms.openlocfilehash: 7d59531bfed80e854bc19b1df00aaf9cce7144d6
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="navigating-the-power-bi-report-server-web-portal"></a>Nawigowanie w portalu internetowym Serwera raportów usługi Power BI
Portal internetowy Serwera raportów usługi Power BI jest lokalizacją lokalną służącą do wyświetlania raportów usługi Power BI, raportów dla urządzeń przenośnych i raportów podzielonych na strony oraz kluczowych wskaźników wydajności, jak również ich przechowywania i zarządzania nimi.

![Portal internetowy serwera raportów](media/getting-around/report-server-web-portal.png)

Portal internetowy można wyświetlić w dowolnej nowoczesnej przeglądarce. W portalu internetowym raporty i kluczowe wskaźniki wydajności są zorganizowane w folderach i można oznaczać je jako ulubione. W tym miejscu można również przechowywać skoroszyty programu Excel. Z poziomu portalu internetowego można uruchamiać narzędzia niezbędne do tworzenia raportów:

* **Raporty usługi Power BI** utworzone przy użyciu programu Power BI Desktop: można je wyświetlać w portalu internetowym oraz w aplikacjach mobilnych usługi Power BI.
* **Raporty z podziałem na strony** utworzone w programie Report Builder: dokumenty o stałym układzie i nowoczesnym wyglądzie, zoptymalizowane pod kątem drukowania.
* **Kluczowe wskaźniki wydajności** utworzone bezpośrednio w portalu internetowym.

W portalu internetowym można przeglądać foldery na serwerze raportów lub wyszukiwać konkretne raporty. Można wyświetlić raport, jego właściwości ogólne oraz wcześniejsze kopie raportu, które zostały przechwycone w historii raportu. Zależnie od uprawnień może być dostępna opcja subskrybowania raportów w celu ich dostarczania do skrzynki odbiorczej poczty e-mail lub folderu udostępnianego w systemie plików.

## <a name="web-portal-tasks"></a>Zadania w portalu internetowym
Przy użyciu portalu internetowego można wykonywać wiele zadań, w tym:

* Wyświetlanie, wyszukiwanie, drukowanie i subskrybowanie raportów.
* Tworzenie, zabezpieczanie i obsługa hierarchii folderów w celu organizowania elementów na serwerze.
* Konfigurowanie właściwości wykonywania, historii i parametrów raportu.
* Tworzenie harmonogramów udostępnionych oraz udostępnionych źródeł danych w celu łatwiejszego zarządzania harmonogramami i połączeniami ze źródłami danych.
* Tworzenie subskrypcji opartych na danych w celu wprowadzania raportów dla dużej listy adresatów.
* Tworzenie połączonych raportów w celu ponownego wykorzystania istniejącego raportu na różne sposoby oraz zmiany jego przeznaczenia.
* Pobieranie i otwieranie wspólnych narzędzi, takich jak programy Power BI Desktop (serwer raportów), Report Builder oraz Mobile Report Publisher.
* [Tworzenie kluczowych wskaźników wydajności](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services).
* Przesyłanie opinii lub próśb o dodanie funkcji.
* [Oznaczanie portalu internetowego marką](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal).
* [Praca z kluczowymi wskaźnikami wydajności](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services).
* [Praca z udostępnionymi zestawami danych](https://docs.microsoft.com/sql/reporting-services/work-with-shared-datasets-web-portal).

## <a name="web-portal-roles-and-permissions"></a>Role i uprawnienia w portalu internetowym
Portal internetowy jest aplikacją internetową uruchamianą w przeglądarce. Po uruchomieniu portalu internetowego wyświetlane strony, linki i opcje różnią się zależnie od Twoich uprawnień na serwerze raportów. Jeśli masz przypisaną rolę o pełnych uprawnieniach, masz dostęp do kompletnego zestawu menu i stron aplikacji do zarządzania serwerem raportów. Jeśli masz przypisaną rolę z uprawnieniami do wyświetlania i uruchamiania raportów, są wyświetlane tylko menu i strony niezbędne do wykonywania tych działań. Można mieć przypisane inne role na poszczególnych serwerach raportów, a nawet w przypadku różnych raportów i folderów na jednym serwerze raportów.

## <a name="start-the-web-portal"></a>Uruchamianie portalu internetowego
1. Otwórz przeglądarkę internetową.
   
    Zapoznaj się z listą [obsługiwanych przeglądarek internetowych i ich wersji](browser-support.md).
2. Na pasku adresu wpisz adres URL portalu internetowego.
   
    Domyślny adres URL to *http://[NazwaKomputera]/reports*.
   
    Serwer raportów może być skonfigurowany do używania konkretnego portu. Na przykład *http://[NazwaKomputera]:80/reports* lub *http://[NazwaKomputera]:8080/reports*
   
    Zauważ, że portal internetowy grupuje elementy w następujących kategoriach:
   
   * Kluczowe wskaźniki wydajności
   * Raporty dla urządzeń przenośnych
   * Raporty z podziałem na strony
   * Raporty programu Power BI Desktop
   * Skoroszyty programu Excel
   * Zestawy danych
   * Źródła danych
   * Zasoby

## <a name="create-and-edit-power-bi-desktop-reports-pbix-files"></a>Tworzenie i edytowanie raportów programu Power BI Desktop (pliki pbix)
W portalu internetowym można wyświetlać, przekazywać, tworzyć i organizować uprawnienia do raportów programu Power BI Desktop oraz zarządzać nimi.

### <a name="create-a-power-bi-desktop-report"></a>Tworzenie raportu programu Power BI Desktop
1. Wybierz pozycję **Nowy** > **Raport usługi Power BI**.
   
    ![Tworzenie nowego raportu usługi Power BI](media/getting-around/report-server-web-portal-new-powerbi-report.png)
   
    Zostanie otwarta aplikacja Power BI Desktop.
   
    ![Aplikacja Power BI Desktop](media/getting-around/report-server-powerbi-desktop-start.png)
2. Utwórz swój raport usługi Power BI. Szczegółowe informacje zawiera temat [Szybki start: raporty usługi Power BI](quickstart-create-powerbi-report.md).
3. Przekaż raport na serwer raportów.

### <a name="edit-an-existing-power-bi-desktop-report"></a>Edytowanie istniejącego raportu programu Power BI Desktop
1. Wybierz przycisk wielokropka (**...**) w prawym górnym rogu kafelka raportu, a następnie wybierz polecenie **Edytuj w programie Power BI Desktop**.
   
    ![Edytowanie w programie Power BI Desktop](media/getting-around/report-server-web-portal-pbix-ellipsis.png)
   
    Zostanie otwarta aplikacja Power BI Desktop.
2. Wprowadź zmiany i zapisz... [jak?]

## <a name="create-and-edit-paginated-reports-rdl-files"></a>Tworzenie i edytowanie raportów z podziałem na strony (pliki rdl)
W portalu internetowym można wyświetlać, przekazywać, tworzyć i organizować uprawnienia do raportów z podziałem na strony oraz zarządzać nimi.

### <a name="create-a-paginated-report"></a>Tworzenie raportu z podziałem na strony
1. Wybierz pozycję **Nowy** > **Raport z podziałem na strony**.
   
    Zostanie otwarta aplikacja Report Builder.
   
    ![Nowy raport programu Report Builder](media/getting-around/report-server-report-builder-new.png)
2. Utwórz raport z podziałem na strony. Szczegółowe informacje zawiera temat [Szybki start: raporty z podziałem na strony](quickstart-create-paginated-report.md).
3. Przekaż raport na serwer raportów.

### <a name="edit-an-existing-paginated-report"></a>Edytowanie istniejącego raportu z podziałem na strony
1. Wybierz przycisk wielokropka (...) w prawym górnym rogu kafelka raportu, a następnie wybierz polecenie **Edytuj w programie Report Builder**.
   
    ![Edytowanie w programie Report Builder](media/getting-around/report-server-web-portal-rdl-ellipsis.png)
   
    Zostanie otwarta aplikacja Report Builder.
2. Wprowadź zmiany i zapisz.

## <a name="upload-and-organize-excel-workbooks"></a>Przekazywanie i organizowanie skoroszytów programu Excel
Uprawnienia do raportów programu Power BI Desktop oraz skoroszytów programu Excel można przekazywać i organizować oraz zarządzać nimi. Będą one pogrupowane razem w portalu internetowym.

Skoroszyty są przechowywane na Serwerze raportów usługi Power BI, podobnie jak inne pliki zasobów. Wybranie jednego ze skoroszytów powoduje jego pobranie na lokalny pulpit. Wprowadzone zmiany można zapisać przez ponowne przekazanie go na serwer raportów.

## <a name="manage-items-in-the-web-portal"></a>Zarządzanie elementami w portalu internetowym
Serwer raportów usługi Power BI umożliwia szczegółową kontrolę nad elementami, które są przechowywane w portalu internetowym. Na przykład można skonfigurować subskrypcje, buforowanie, migawki i zabezpieczenia dla poszczególnych raportów z podziałem na strony.

1. Wybierz przycisk wielokropka (...) w prawym górnym rogu elementu i wybierz polecenie **Zarządzaj**.
   
    ![Wybieranie polecenia Zarządzaj](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. Wybierz właściwość lub inną funkcję, którą chcesz ustawić.
   
    ![Wybieranie właściwości](media/getting-around/report-server-web-portal-manage-properties.png)
3. Wybierz pozycję **Zastosuj**.

Dowiedz się więcej o [pracy z subskrypcjami w portalu internetowym](https://docs.microsoft.com/sql/reporting-services/working-with-subscriptions-web-portal).

## <a name="tag-your-favorite-reports-and-kpis"></a>Tagowanie ulubionych raportów i kluczowych wskaźników wydajności
Raporty i kluczowe wskaźniki wydajności, które mają zostać dodane do ulubionych, można otagować. Łatwiej będzie je odnaleźć, ponieważ są zgromadzone w jednym folderze Ulubione zarówno w portalu internetowym, jak i w aplikacjach mobilnych usługi Power BI. 

1. Wybierz przycisk wielokropka (**…**) w prawym górnym rogu kluczowego wskaźnika wydajności lub raportu, który chcesz dodać do ulubionych, a następnie wybierz polecenie **Dodaj do ulubionych**.
   
    ![Dodawanie do ulubionych](media/getting-around/report-server-web-portal-favorite-ellipsis.png)
2. Wybierz pozycję **Ulubione** na wstążce w portalu internetowym, aby wyświetlić ten element wraz z innymi ulubionymi elementami na stronie Ulubione w portalu internetowym.
   
    ![Wyświetlanie Ulubionych](media/getting-around/report-server-web-portal-favorites.png)
   
    Teraz w aplikacjach mobilnych usługi Power BI te ulubione elementy są wyświetlane wraz z ulubionymi pulpitami nawigacyjnymi z usługi Power BI.
   
    ![Wyświetlanie Ulubionych w aplikacji mobilnej](media/getting-around/power-bi-iphone-faves-report-server.png)

## <a name="hide-or-view-items-in-the-web-portal"></a>Ukrywanie lub wyświetlanie elementów w portalu internetowym
W portalu internetowym można ukrywać elementy oraz wyświetlać ukryte elementy.

### <a name="hide-an-item"></a>Ukrywanie elementu
1. Wybierz przycisk wielokropka (...) w prawym górnym rogu elementu i wybierz polecenie **Zarządzaj**.
   
    ![Wybieranie polecenia Zarządzaj](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. Wybierz pozycję **Ukryj ten element**.
   
    ![Wybieranie pozycji Ukryj](media/getting-around/report-server-web-portal-hide-property.png)
3. Wybierz pozycję **Zastosuj**.

### <a name="view-hidden-items"></a>Wyświetlanie ukrytych elementów
1. Wybierz pozycję **Kafelki** (lub **Lista**) w prawym górnym rogu, a następnie wybierz polecenie **Pokaż ukryte elementy**.
   
    Elementy zostaną wyświetlone. Są one wygaszone, ale mimo to można je otworzyć i edytować.
   
    ![Wyświetlanie ukrytych elementów](media/getting-around/report-server-web-portal-show-hidden-grayed.png)

## <a name="search-for-items"></a>Wyszukiwanie elementów
Wprowadzenie terminu wyszukiwania umożliwia wyświetlenie wszystkich elementów, do których masz dostęp. Wyniki są podzielone na kategorie: kluczowe wskaźniki wydajności, raporty, zestawy danych i inne elementy. Z wynikami można wchodzić w interakcje i dodawać je do ulubionych.  

![Wyszukiwanie elementów](media/getting-around/report-server-web-portal-search.png)

## <a name="move-or-delete-items-in-list-view"></a>Przenoszenie lub usuwanie elementów w widoku listy
Domyślnie zawartość portalu internetowego jest wyświetlana w widoku kafelków.

Ten widok można zmienić na widok listy, w którym możliwe jest łatwe przenoszenie lub usuwanie wielu elementów naraz. 

1. Wybierz pozycję **Kafelki** > **Lista**.
   
    ![Przełączanie widoków](media/getting-around/report-server-web-portal-list-view.png)
2. Wybierz elementy, a następnie wybierz pozycję **Przenieś** lub **Usuń**.

## <a name="next-steps"></a>Następne kroki
[Podręcznik użytkownika](user-handbook-overview.md)  
[Szybki start: raporty z podziałem na strony](quickstart-create-paginated-report.md)  
[Szybki start: raporty usługi Power BI](quickstart-create-powerbi-report.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

