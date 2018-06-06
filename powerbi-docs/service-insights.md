---
title: Automatyczne generowanie wglądu w szczegółowe dane przy użyciu usługi Power BI
description: Dowiedz się, jak uzyskać wgląd w szczegółowe dane dla zestawów danych i kafelków pulpitu nawigacyjnego.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 8be938b1a75f754b7c23a57a5a0ccfdb4e60032b
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34561890"
---
# <a name="automatically-generate-data-insights-with-power-bi"></a>Automatyczne generowanie wglądu w szczegółowe dane przy użyciu usługi Power BI
Masz nowy zestaw danych i nie bardzo wiesz, gdzie zacząć?  Musisz szybko utworzyć pulpit nawigacyjny?  Chcesz wyszukać szczegółowe informacje, które mogły zostać pominięte?

Uruchom szybki wgląd w szczegółowe dane, aby generować interesujące, interaktywne wizualizacje na podstawie danych. Szybki wgląd w szczegółowe dane można uruchamiać na całym zestawie danych (szybki wgląd w szczegółowe dane) lub na konkretnym kafelku pulpitu nawigacyjnego (wgląd w szczegółowe informacje dla zakresu). Możesz nawet uruchamiać wgląd w szczegółowe dane wewnątrz wglądu w szczegółowe dane.

> **UWAGA**: wgląd w szczegółowe dane nie działa w przypadku zapytania bezpośredniego — działa tylko z danymi przekazanymi do usługi Power BI.
> 

Wgląd w szczegółowe dane działa w oparciu o rosnący [zestaw zaawansowanych algorytmów analitycznych](service-insight-types.md), opracowywany we współpracy z działem badań firmy Microsoft. Będziemy z niego nadal korzystać, aby umożliwić większej liczbie użytkowników uzyskiwanie przydatnego wglądu w dane na nowe i intuicyjne sposoby.

## <a name="run-quick-insights-on-a-dataset"></a>Uruchamianie szybkiego wglądu w szczegółowe dane dla zestawu danych
Obejrzyj, jak Amanda uruchamia szybki wgląd na zestawie danych, otwiera wgląd w trybie koncentracji uwagi, przypina jeden z wglądów jako kafelek na swoim pulpicie nawigacyjnym, a następnie uzyskuje wgląd w szczegółowe dane dla kafelka pulpitu nawigacyjnego.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Teraz Twoja kolej. Poznaj funkcję wglądu w szczegółowe dane za pomocą [próbki danych do analizy jakości dostawców](sample-supplier-quality.md).

1. Na karcie **Zestawy danych** wybierz wielokropek (...) i wybierz pozycję **Uzyskaj szczegółowe dane**.
   
    ![Karta Zbiory danych](media/service-insights/power-bi-ellipses.png)
   
    ![menu wielokropka](media/service-insights/power-bi-tab.png)
2. Usługa Power BI wykorzystuje [wiele zaawansowanych algorytmów](service-insight-types.md) do wyszukiwania trendów w zestawie danych.
   
    ![Okno dialogowe wyszukiwania szczegółowych danych](media/service-insights/pbi_autoinsightssearching.png)
3. W ciągu kilku szczegółowe informacje będą gotowe.  Wybierz pozycję **Wyświetl szczegółowe dane**, aby wyświetlić wizualizacje.
   
    ![komunikat dotyczący sukcesu](media/service-insights/pbi_autoinsightsuccess.png)
   
   > **UWAGA**: Niektóre zestawy danych nie mogą wygenerować wglądu w szczegółowe dane, ponieważ dane nie są statystycznie istotne.  Aby dowiedzieć się więcej, zobacz [Optymalizacja danych na potrzeby wglądu w szczegółowe dane](service-insights-optimize.md).
   > 
   > 
1. Wizualizacje są wyświetlane w specjalnej kanwie **Szybki wgląd w szczegółowe dane**, z maksymalnie 32 oddzielnymi kartami wglądów. Każda karta zawiera wykres lub wykres i krótki opis.
   
    ![Kanwy szybkiego wglądu w szczegółowe dane](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-insight-cards"></a>Praca z kartami wglądu w szczegółowe dane
  ![ikona przypinania](media/service-insights/pbi_hover.png)

1. Umieść kursor nad kartą i wybierz ikonę pinezki, aby dodać wizualizację do pulpitu nawigacyjnego.
2. Zatrzymaj wskaźnik myszy nad kartą, wybierz wielokropek (...) i wybierz pozycję **Wyświetl szczegółowe dane**. Spowoduje to otwarcie szczegółowych danych na pełnym ekranie.
   
    ![Pełny ekran szczegółowych danych](media/service-insights/power-bi-insight-focus.png)
3. W trybie koncentracji uwagi możesz wykonywać następujące czynności:
   
   * Filtrowanie wizualizacji.  Aby wyświetlić filtry, w prawym górnym rogu wybierz strzałkę, aby rozwinąć okienko Filtry.
        ![rozwinięte menu danych szczegółowych i filtrów](media/service-insights/power-bi-insights-filter-new.png)
   * Przypnij kartę wglądu do pulpitu nawigacyjnego, wybierając ikonę pinezki ![ikona pinezki](media/service-insights/power-bi-pin-icon.png) lub pozycję **Przypnij wizualizację**.
   * Uruchom wgląd w szczegółowe dane na samej karcie. To działanie jest często określane jako **wgląd w szczegółowe dane w zakresie**. W prawym górnym rogu wybierz ikonę żarówki ![ikona uzyskiwania szczegółowych danych](media/service-insights/power-bi-bulb-icon.png) lub pozycję **Uzyskaj szczegółowe dane**.
     
       ![pasek narzędzi z ikoną Uzyskaj szczegółowe dane](media/service-insights/pbi-autoinsights-tile.png)
     
     Wgląd w szczegółowe dane jest wyświetlany po lewej stronie i na nowych kartach, wyłącznie na podstawie danych w tym pojedynczym wglądzie w szczegółowe dane, wyświetlanym wzdłuż prawej strony.
     
       ![szczegółowy wgląd w szczegółowe dane](media/service-insights/power-bi-insights-on-insights-new.png)
4. Aby wrócić do oryginalnej kanwy wglądu w szczegółowe dane, w lewym górnym rogu wybierz pozycję **Wyjdź z trybu koncentracji uwagi**.

## <a name="run-insights-on-a-dashboard-tile"></a>Uruchamianie wglądu w szczegółowe dane dla kafelka pulpitu nawigacyjnego
Zamiast wyszukiwać szczegółowe informacje dla całego zestawu danych, możesz zawęzić kryteria wyszukiwania do danych używanych do utworzenia pojedynczego kafelka pulpitu nawigacyjnego. To działanie jest też często określane jako **wgląd w szczegółowe dane w zakresie**.

1. Otwórz pulpit nawigacyjny.
2. Zatrzymaj wskaźnik myszy nad kafelkiem. Wybierz wielokropek (...) i wybierz pozycję **Wyświetl szczegółowe dane**. Kafelek zostanie otwarty w [trybie koncentracji uwagi](service-focus-mode.md) z kartami wglądu w szczegółowe dane widocznymi z prawej strony.    
   
    ![Tryb koncentracji uwagi](media/service-insights/pbi-insights-tile.png)    
4. Czy jeden z wglądów przykuł Twoje zainteresowanie? Wybierz kartę tego wglądu, aby dokładniej go zbadać. Wybrany wgląd w szczegółowe dane jest wyświetlany po lewej stronie i na nowych kartach wglądu, wyłącznie na podstawie danych w tym pojedynczym wglądzie w szczegółowe dane, wyświetlanym wzdłuż prawej strony.    
6. Możesz dalej przeszukiwać dane, a po znalezieniu interesującego wglądu przypiąć go do pulpitu nawigacyjnego, wybierając pozycję **Przypnij wizualizację** w prawym górnym rogu.

## <a name="next-steps"></a>Następne kroki
Jeśli jesteś właścicielem zestawu danych, [zoptymalizuj go pod kątem szybkiego wglądu w szczegółowe dane](service-insights-optimize.md)

Dowiedz się więcej na temat [dostępnych typów szybkiego wglądu w szczegółowe dane](service-insight-types.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

