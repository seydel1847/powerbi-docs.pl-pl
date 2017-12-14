---
title: "Dziennik zmian w Serwerze raportów usługi Power BI"
description: "Ten dziennik zmian zawiera listę nowych elementów oraz poprawek błędów w każdej wydanej kompilacji Serwera raportów usługi Power BI."
services: powerbi
documentationcenter: 
author: jtarquino
manager: jonhp
backup: maggies
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/17/2017
ms.author: jaimeta
ms.openlocfilehash: e56976943e58aba8c9ef36c576a16ab5eba4c796
ms.sourcegitcommit: 7d4ad2ba92a932d7cc6637348e0774be6623559e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2017
---
# <a name="changelog-for-power-bi-report-server"></a>Dziennik zmian w Serwerze raportów usługi Power BI

Ten dziennik zmian zawiera listę nowych elementów oraz poprawek błędów w każdej wydanej kompilacji Serwera raportów usługi Power BI.

Aby uzyskać szczegółowe informacje o nowych funkcjach, zobacz [Co nowego w Serwerze raportów usługi Power BI](whats-new.md).

## <a name="october-2017"></a>Październik 2017

- **Serwer raportów usługi Power BI**
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

## <a name="next-steps"></a>Następne kroki

[Podręcznik użytkownika](user-handbook-overview.md)  
[Podręcznik administratora](admin-handbook-overview.md)  
[Szybki start: instalowanie serwera raportów usługi Power BI](quickstart-install-report-server.md)  
[Instalowanie programu Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)