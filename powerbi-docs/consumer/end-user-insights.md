---
title: Uruchamianie i wyświetlanie szczegółowych informacji na kafelkach pulpitu nawigacyjnego
description: Jako użytkownik końcowy usługi Power BI dowiedz się, jak uzyskać szczegółowe informacje dotyczące kafelków pulpitu nawigacyjnego.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 8bae8475ee4bbe91ea27f3a9e30a3323a92a8250
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2018
ms.locfileid: "53280264"
---
# <a name="view-data-insights-on-dashboard-tiles-with-power-bi"></a>Wyświetlanie szczegółowych informacji dotyczących kafelków pulpitu nawigacyjnego w usłudze Power BI
Każdy kafelek wizualizacji na pulpicie nawigacyjnym umożliwia rozpoczęcie eksploracji danych. Wybranie kafelka powoduje otwarcie raportu, w którym można filtrować i sortować oraz analizować zestaw danych będący podstawą raportu. Po uruchomieniu wglądu w szczegółowe dane usługa Power BI przeprowadza dla Ciebie eksplorację danych.

Uruchom szybki wgląd w szczegółowe dane, aby generować interesujące, interaktywne wizualizacje na podstawie danych. Szybki wgląd w szczegółowe dane można uruchamiać na określonym kafelku pulpitu nawigacyjnego. Można nawet uruchamiać wgląd w szczegółowe dane na wglądzie w szczegółowe dane!

Wgląd w szczegółowe dane działa w oparciu o rosnący [zestaw zaawansowanych algorytmów analitycznych](end-user-insight-types.md), opracowywany we współpracy z działem badań firmy Microsoft. Będziemy z niego nadal korzystać, aby umożliwić większej liczbie użytkowników uzyskiwanie przydatnego wglądu w dane na nowe i intuicyjne sposoby.

## <a name="run-insights-on-a-dashboard-tile"></a>Uruchamianie wglądu w szczegółowe dane dla kafelka pulpitu nawigacyjnego
Po uruchomieniu wglądu w szczegółowe dane na kafelku pulpitu nawigacyjnego usługa Power BI wyszukuje tylko te dane, które zostały użyte do utworzenia tego kafelka pulpitu nawigacyjnego. 

1. [Otwórz pulpit nawigacyjny](end-user-dashboards.md).
2. Zatrzymaj wskaźnik myszy nad kafelkiem. Wybierz wielokropek (...) i wybierz pozycję **Wyświetl szczegółowe dane**. 

    ![tryb menu wielokropka](./media/end-user-insights/power-bi-hover.png)


3. Kafelek zostanie otwarty w [trybie koncentracji uwagi](end-user-focus.md) z kartami wglądu w szczegółowe dane widocznymi z prawej strony.    
   
    ![Tryb koncentracji uwagi](./media/end-user-insights/pbi-insights-tile.png)    
4. Czy jeden z wglądów przykuł Twoje zainteresowanie? Wybierz kartę tego wglądu, aby dokładniej go zbadać. Wybrany wgląd w szczegółowe dane jest wyświetlany po lewej stronie i na nowych kartach wglądu, wyłącznie na podstawie danych w tym pojedynczym wglądzie w szczegółowe dane, wyświetlanym wzdłuż prawej strony.    

 ## <a name="interact-with-the-insight-cards"></a>Praca z kartami wglądu w szczegółowe dane
Po otwarciu szczegółowych informacji kontynuuj eksplorowanie.

   * Filtruj wizualizację na kanwie.  Aby wyświetlić filtry, w prawym górnym rogu wybierz strzałkę, aby rozwinąć okienko Filtry.

     ![rozwinięte menu danych szczegółowych i filtrów](./media/end-user-insights/power-bi-insights-on-insights.png)
   
   * Uruchom wgląd w szczegółowe dane na samej karcie wglądu w szczegółowe dane. To działanie jest często określane jako **powiązane wglądy w szczegółowe dane**. W prawym górnym rogu wybierz ikonę żarówki ![ikona uzyskiwania szczegółowych danych](./media/end-user-insights/power-bi-bulb-icon.png) lub pozycję **Uzyskaj szczegółowe dane**.
     
     ![pasek narzędzi z ikoną Uzyskaj szczegółowe dane](./media/end-user-insights/power-bi-autoinsights-tile.png)
     
     Wgląd w szczegółowe dane jest wyświetlany po lewej stronie i na nowych kartach, wyłącznie na podstawie danych w tym pojedynczym wglądzie w szczegółowe dane, wyświetlanym wzdłuż prawej strony.
     
     ![szczegółowy wgląd w szczegółowe dane](./media/end-user-insights/power-bi-insights-on-insights-new.png)

Aby wrócić do oryginalnej kanwy wglądu w szczegółowe dane, w lewym górnym rogu wybierz pozycję **Wyjdź z trybu koncentracji uwagi**.

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów
- Opcja **Wyświetl szczegółowe dane** nie działa w przypadku trybu DirectQuery — działa tylko z danymi przekazanymi do usługi Power BI.
- Opcja **Wyświetl szczegółowe dane** nie działa ze wszystkimi typami kafelka pulpitu nawigacyjnego. Na przykład nie jest dostępna dla wizualizacji niestandardowych.<!--[custom visuals](end-user-custom-visuals.md)-->


## <a name="next-steps"></a>Następne kroki
Dowiedz się więcej na temat [dostępnych typów szybkiego wglądu w szczegółowe dane](end-user-insight-types.md)

