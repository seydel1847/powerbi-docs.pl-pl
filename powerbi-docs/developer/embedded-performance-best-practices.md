---
title: Wydajność usługi Power BI Embedded — najlepsze rozwiązania
description: Ten artykuł zawiera wskazówki dotyczące najlepszych rozwiązań z zakresu analizy osadzonej
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-embedded
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: e28801a15cf50351d737af63bc48f655ca85d28f
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008171"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Wydajność usługi Power BI Embedded — najlepsze rozwiązania

Ten artykuł zawiera zalecenia dotyczące szybszego renderowanie raportów, pulpitów nawigacyjnych i kafelków w aplikacji

## <a name="embed-parameters"></a>Parametry osadzania

Metoda Powerbi.embed() odbiera kilka parametrów umożliwiających osadzenie raportu, pulpitu nawigacyjnego lub kafelka. Te parametry mają wpływ na wydajność.

### <a name="embed-url"></a>Adres URL osadzania

Unikaj samodzielnego generowania adresu URL osadzania. Zamiast tego uzyskaj adres URL osadzania, wywołując interfejs API [Uzyskiwanie raportów](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Freports%2Fgetreportsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=22lkqRM2w1MQfrM8dooedaPqqIU8PufTq9TT4VDzRo0%3D&reserved=0), [Uzyskiwanie pulpitów nawigacyjnych](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgetdashboardsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=nfWRgbSoXVF42Rg%2Ba9491u19uksXp%2FAyz%2Fa%2Ba7%2FCtdA%3D&reserved=0) lub [Uzyskiwanie kafelków](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgettilesingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256178318&sdata=LgZ27TynNpqQJDrb3aHWGQXIS%2FzichAO9De5M2uhF1Q%3D&reserved=0). Dodaliśmy do adresu URL nowy parametr o nazwie **_config_**, którego zadaniem jest zwiększenie wydajności.

### <a name="permissions"></a>Uprawnienia

Podaj uprawnienia do **wyświetlania**, jeśli nie masz zamiaru osadzić raportu w **trybie edycji**. Dzięki temu kod osadzania nie spowoduje zainicjowania składników, które są używane w trybie edycji.

### <a name="filters-bookmarks-and-slicers"></a>Filtry, zakładki i fragmentatory

Wizualizacje raportów są zwykle zapisywane z informacjami buforowanymi. Informacje buforowane zapewniają widoczny wzrost wydajności. Raporty renderują informacje buforowane w czasie wykonywania zapytań. Jeśli określono filtry, zakładki lub fragmentatory, informacje buforowane nie są istotne. Wizualizacje są renderowane tylko po uruchomieniu zapytania wizualizacji.

Jeśli osadzasz raporty przy użyciu tych samych filtrów, to aby uniknąć przekazywania listy filtrów w konfiguracji obciążenia, zapisz raport z wcześniej zastosowanymi filtrami.

## <a name="preload"></a>Ładowanie wstępne

Użyj interfejsu API *preload* (ładowanie wstępne) języka JavaScript, aby zwiększyć wydajność dla użytkowników końcowych.
Interfejs Powerbi.preload() pobiera kod javascript, pliki css i inne artefakty, który są używane później do osadzania w raporcie.

Wywołaj interfejs ładowania wstępnego, jeśli nie osadzasz raportu natychmiast. Na przykład jeśli osadzasz raport po kliknięciu przycisku, lepiej wywołać interfejs ładowania wstępnego podczas ładowania poprzedniej strony. Dzięki temu, kiedy użytkownik aplikacji kliknie przycisk, renderowanie będzie szybsze.

## <a name="measure-performance"></a>Mierzenie wydajności

Aby zmierzyć wydajność, użyj następujących parametrów:

1. Loaded: (Załadowane:) czas do momentu zainicjowania raportu (użytkownik nie widzi opóźnienia).
2. Rendered: (Renderowane:) czas do całkowitego wyrenderowania z użyciem rzeczywistych danych. Zdarzenie z renderowaniem jest wyzwalane każdorazowo po ponownym wyrenderowaniu raportu (czyli po zastosowaniu filtrów). Aby najpierw zmierzyć raport, upewnij się, że obliczenia są wykonywane względem pierwszego zgłoszonego zdarzenia.

Informacje buforowane są renderowane wtedy, kiedy są dostępne, ale jeszcze nie mamy zdarzenia dla tych informacji.

## <a name="update-tools-and-sdk-packages"></a>Aktualizacja narzędzi i pakietów SDK

Zapewnij aktualność narzędzi i pakietów SDK.

* Zawsze używaj najnowszej wersji programu [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/).

* Zainstaluj najnowszą wersję [zestawu SDK klienta usługi Power BI](https://github.com/Microsoft/PowerBI-JavaScript). Stale publikujemy nowe udoskonalenia, więc zaglądaj tu od czasu do czasu.

* Pakiety do zainstalowania:
    * Pakiet Npm: powerbi-client
    * Pakiet NuGet: Microsoft.PowerBI.JavaScript

> [!Note]
> Należy pamiętać, że czas ładowania zależy głównie od elementów związanych z raportem i samych danych. Te czynniki to na przykład liczba wizualizacji, rozmiar danych oraz złożoności zapytań i miar obliczeniowych. Postępuj zgodnie z [najlepszymi rozwiązaniami](../power-bi-reports-performance.md), aby skrócić czas ładowania raportu.

## <a name="next-steps"></a>Następne kroki

* [Wydajność raportów usługi Power BI — najlepsze rozwiązania](../power-bi-reports-performance.md)
* [Jak rozwiązywać problemy z usługą Power BI Embedded](embedded-troubleshoot.md)
* [Power BI Embedded — często zadawane pytania](embedded-faq.md)
