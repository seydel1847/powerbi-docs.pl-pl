---
title: Dziennik zmian w Serwerze raportów usługi Power BI
description: Ten dziennik zmian zawiera listę nowych elementów oraz poprawek błędów w każdej wydanej kompilacji Serwera raportów usługi Power BI.
services: powerbi
documentationcenter: ''
author: jtarquino
manager: jonhp
backup: maggies
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/11/2017
ms.author: tankas
ms.openlocfilehash: 1345cfee8eb92b9b4e3cf883f19edddee859a1c3
ms.sourcegitcommit: c9905e625ba14dc28ad23835f320e49631c51d0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/29/2018
---
# <a name="changelog-for-power-bi-report-server"></a>Dziennik zmian w Serwerze raportów usługi Power BI

Ten dziennik zmian zawiera listę nowych elementów oraz poprawek błędów w każdej wydanej kompilacji Serwera raportów usługi Power BI.

Aby uzyskać szczegółowe informacje o nowych funkcjach, zobacz [Co nowego w Serwerze raportów usługi Power BI](whats-new.md). 

## <a name="march-2018"></a>Marzec 2018
- **Serwer raportów usługi Power BI**
    - *Wersja 1.2.6660.39920 (kompilacja 15.0.2.389), data wydania: 28 marca 2018 r.*
        - Poprawki błędów
            - W przypadku raportów usługi Power BI (PBIX) naprawiono błąd polegający na tym, że eksport danych nie działał z poziomu wizualizacji usługi Power BI
            - W przypadku raportów usługi Power BI (PBIX) naprawiono błąd polegający na tym, że filtry adresów URL nie działały
            - W przypadku raportów podzielonych na strony (RDL) naprawiono błąd polegający na tym, że obrazy nie były prawidłowo wyświetlane w programie IE11 po uaktualnieniu serwera raportów usługi Power BI do wersji wydanej w marcu

    - *Wersja 1.2.6648.38132 (kompilacja 15.0.2.378), data wydania: 19 marca 2018 r.*
        - Aktualizacje zabezpieczeń
        - Usprawnienia w zakresie ułatwień dostępu
        - Poprawki błędów
            - W przypadku raportów z podziałem na strony (RDL) poprawiono widoczność parametrów w połączonym raporcie, który zostaje przywrócony po edytowaniu jego właściwości
            - Poprawka portalu internetowego z uwierzytelnianiem opartym na formularzach niestandardowych, który ignorował przesuwany plik cookie wygaśnięcia
            - Poprawka funkcji eksportowania do programu Word, która tworzyła wiersze o nierównej wysokości, jeśli zawartość wiersza była pusta
            - W przypadku raportów z podziałem na strony (RDL) poprawiono parametry połączenia oparte na wyrażeniach, które były usuwane w przypadku zmiany poświadczenia dla źródła danych
            - Poprawka możliwości używania wskaźników KPI z wartościami tekstowymi
            - W przypadku raportów z podziałem na strony (RDL) poprawiono możliwość przydzielania nowego zestawu danych do istniejącego raportu z podziałem na strony (RDL)
            - Inne poprawki w zakresie stabilności i użyteczności

- **Power BI Desktop (zoptymalizowany pod kątem serwera raportów usługi Power BI)**
    - Wersja: 2.56.5023.1043 (marzec 2018 r.), data wydania: 19 marca 2018 r.
        - Zmiany wymagane do nawiązania połączenia z serwerem raportów usługi Power BI (marzec 2018 r.)

## <a name="october-2017"></a>Październik 2017

- **Serwer raportów usługi Power BI**
    - *Wersja 1.1.6582.41691 (kompilacja 14.0.600.442), data wydania: 10 stycznia 2018 r.*
        - Aktualizacje zabezpieczeń
        - Poprawki błędów
            - Poprawka dla Model.GetParameters zwracającego 400
            - Poprawka dla ustawiania udostępnionego zestawu danych na istniejące raporty z podziałem na strony (RDL)
            - Poprawka dla wyjątku ExecutionNotFoundException podczas eksportowania raportu z wartościami różnych parametrów do formatu PDF

    - *Wersja 1.1.6551.5155 (kompilacja 14.0.600.438), data wydania: 11 grudnia 2017 r.*
        - Poprawki błędów
            - Nie można zapisać danych po odświeżeniu dla niektórych raportów w programie Power BI Desktop.

    - *Wersja 1.1.6530.30789 (kompilacja 14.0.600.437), data wydania: 17 listopada 2017 r.*
        - Poprawki błędów
            - Poprawka dotycząca scenariuszy uwierzytelniania podstawowego 
            - Poprawka dotycząca wyboru dni roboczych na stronie harmonogramu w obszarach subskrypcji, planów odświeżania pamięci podręcznej i migawek historii w witrynie Portal
            - Poprawka w raportach podzielonych na strony (RDL) dotycząca obsługi wyrażeń w polu tekstowym — jeśli właściwość CanGrow miała wartość false, kolory i czcionki nie były wyświetlane prawidłowo
            - Poprawka w raportach usługi Power BI (PBIX) dotycząca wyświetlania pustej wizualizacji po dodaniu legendy do wykresu liniowego

    - *Wersja 1.1.6514.9163 (kompilacja 14.0.600.434), data wydania: 1 listopada 2017 r.*
        - Poprawki błędów
            - Poprawka dotycząca problemów z niezawodnością przekazywania raportów PBIX o rozmiarze przekraczającym 500 MB
            - Poprawka dotycząca problemów z ładowaniem raportów PBIX o rozmiarze przekraczającym 1 GB

    - *Wersja 1.1.6513.3500 (kompilacja 14.0.600.433), data wydania: 31 października 2017 r.*
        - Funkcje
            - Obsługa osadzonego modelu danych
            - Wyświetlanie skoroszytów programu Excel (z włączoną integracją programu Office Online Server)
            - Odświeżanie danych według harmonogramu (PBIX)
            - Obsługa zapytań bezpośrednich
            - Obsługa dużych plików (do 2 GB)
            - Publiczny interfejs API REST
            - Obsługa udostępnionych zestawów danych w programie Power BI Desktop (za pośrednictwem usługi oData)
            - Obsługa parametru URL dla plików PBIX
            - Usprawnienia w zakresie ułatwień dostępu

- **Power BI Desktop (zoptymalizowany pod kątem serwera raportów usługi Power BI)**
    - *Wersja: 2.51.4885.2501 (październik 2017 r.), data wydania: 10 stycznia 2018 r.*
        - Aktualizacje zabezpieczeń

    - *Wersja: 2.51.4885.1423 (październik 2017), data wydania: 17 listopada 2017 r.*
        - Poprawki błędów
            - Poprawka dotycząca problemów z uruchamianiem 32-bitowego programu Power BI Desktop w systemach operacyjnych opartych na architekturze x86
            - Poprawka dotycząca wyświetlania linii siatki osi X w raportach usługi Power BI (PBIX)
            - Inne poprawki drobnych błędów

    - *Wersja: 2.51.4885.1041 (październik 2017), data wydania: 31 października 2017 r.*
        - Funkcje
            - Zmiany wymagane do nawiązania połączenia z Serwerem raportów usługi Power BI (październik 2017)

## <a name="june-2017"></a>Czerwiec 2017

- **Serwer raportów usługi Power BI**
    - *Kompilacja 14.0.600.309, data wydania: 10 stycznia 2018 r.*
        - Aktualizacje zabezpieczeń

    - *Kompilacja 14.0.600.305, data wydania: 19 września 2017 r.*  
        - Poprawki błędów
            - Aktualizacja do najnowszej wersji [kontrolki internetowej Map Bing](https://msdn.microsoft.com/library/mt712542.aspx)

    - *Kompilacja 14.0.600.301, data wydania: 11 lipca 2017 r.*
        - Poprawki błędów
            - Tag {{UserId}} jest rozpoznawany jako przechowywane poświadczenia zamiast użytkownika uruchamiającego raport w usłudze Power BI
            - Niektóre obrazy nie są renderowane w raportach Serwera raportów usługi Power BI
            - Nie można zmienić nazwy raportu na Serwerze raportów usługi Power BI
            - Nie można załadować niestandardowych wizualizacji w aplikacji Power BI dla urządzeń przenośnych (wymagana jest ponowna instalacja aplikacji mobilnej w celu wyczyszczenia lokalnej pamięci podręcznej)

    - *Kompilacja 14.0.600.271, data wydania: 12 czerwca 2017 r.*
        - Pierwsze wydanie Serwera raportów usługi Power BI

- **Power BI Desktop (zoptymalizowany pod kątem serwera raportów usługi Power BI)**
    - *Wersja: 2.47.4766.4901 (czerwiec 2017 r.), data wydania: 10 stycznia 2018 r.*
        - Aktualizacje zabezpieczeń

## <a name="next-steps"></a>Następne kroki

[Podręcznik użytkownika](user-handbook-overview.md)  
[Podręcznik administratora](admin-handbook-overview.md)  
[Szybki start: instalowanie serwera raportów usługi Power BI](quickstart-install-report-server.md)  
[Instalowanie programu Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)
