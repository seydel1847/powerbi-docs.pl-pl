---
title: Certyfikowane wizualizacje niestandardowe w usłudze Power BI
description: Wymagania i proces przesyłania wizualizacji niestandardowej do certyfikacji. Oraz lista certyfikowanych wizualizacji niestandardowych.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/13/2018
ms.author: mihart
ms.openlocfilehash: 49849853d40bca9e2a2c4cb8084018f20ecaeabf
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="getting-a-custom-visual-certified"></a>*Certyfikowanie* wizualizacji niestandardowej
## <a name="what-is-meant-by-certified"></a>Co oznacza *certyfikowanie*?
*Certyfikowana wizualizacja niestandardowa* to wizualizacja, która spełnia zestaw określonych wymagań dotyczących kodu i przeszła restrykcyjne testy bezpieczeństwa.  Zarejestrowane wizualizacje niestandardowe mogą zostać [wyeksportowane do programu PowerPoint](service-publish-to-powerpoint.md) i będą wyświetlane w wiadomościach e-mail, jeśli użytkownik [subskrybuje strony raportu](service-report-subscribe.md). Oczywiście można tego użyć również jak [standardowych własnych wizualizacji](power-bi-custom-visuals.md) dodanych do raportów usługi Power BI i programu Power BI Desktop oraz wyświetlanych w usłudze mobilnej Power BI i osadzonych.

Jesteś deweloperem internetowym i chcesz utworzyć własne wizualizacje oraz dodać je do witryny [Microsoft AppSource](https://appsource.microsoft.com)? Aby uzyskać pomocne informacje, zobacz [Wprowadzenie do korzystania z narzędzi deweloperskich](service-custom-visuals-getting-started-with-developer-tools.md).


## <a name="certification-requirements"></a>Wymagania dotyczące certyfikacji
* Wizualizacja jest zatwierdzona w witrynie Microsoft AppSource.    
* Wizualizacja niestandardowa jest zapisana przy użyciu interfejsu API w wersji 1.2 lub nowszej.    
* Repozytorium kodu jest dostępne do przeglądu (np. kod wizualizacji jest dostępny za pośrednictwem witryny GitHub).    
* Wizualizacja korzysta wyłącznie ze składników OSS dostępnych do przeglądu publicznie.    
* Wizualizacja nie korzysta z usług ani zasobów zewnętrznych.    

> **PORADA**: zalecamy użycie programu EsLint z domyślnym zestawem reguł zabezpieczeń w celu wstępnego zweryfikowania kodu przed przesłaniem.
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>Proces przesyłania wizualizacji niestandardowej do certyfikacji
Aby przesłać wizualizację niestandardową do certyfikacji:

1. Wyślij wiadomość e-mail do działu pomocy technicznej w zakresie wizualizacji niestandardowych usługi Power BI (pbicvsupport@microsoft.com). W wiadomości e-mail uwzględnij następujące informacje:    
   
   * Tytuł: Visual Certification Request    
   * Link do repozytorium w witrynie GitHub, w którym znajduje się kod źródłowy wizualizacji    
   * Zapewnij zgodność z wymogami (zobacz powyżej)    
   * Udostępnij wyniki przeglądu kodu i zabezpieczeń    

2. Zespół ds. wizualizacji niestandardowych w firmie Microsoft powiadomi, kiedy Twoja wizualizacja niestandardowa zostanie certyfikowana i dodana do listy wizualizacji certyfikowanych (poniżej) lub odrzucona (wówczas do powiadomienia będzie dołączony raport z informacjami, co należy naprawić). Deweloper odpowiada za utrzymanie komunikacji z firmą Microsoft i zaktualizowanie certyfikowanych wizualizacji w wymagany sposób.

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Usuwanie certyfikowanych wizualizacji niestandardowych usługi Power BI
Firma Microsoft, według własnego uznania, może usunąć daną wizualizację z listy certyfikowanych wizualizacji.  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>Lista certyfikowanych wizualizacji
| Link do witryny AppSource | Link do klipu wideo |
| --- | --- |
| [Aster Plot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759) | |
| [Kalendarz Beyondsoft](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096) | |
| [Wykres Bowtie firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380838) | [Klip wideo](https://youtu.be/So5xKMSpVJI) |
| [Wykres pudełkowy](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380831) | |
| [Wykres w formie skrzynki i wąsów firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381351) | [Klip wideo](https://youtu.be/JoHaFLfhXdo) |
| [Brick Chart firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | [Klip wideo](https://youtu.be/hA3DOsvn2xY) |
| [Wykres bąbelkowy firmy Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340) | |
| [Bullet Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380755) | [Klip wideo](https://youtu.be/AOlsFYkfkcw) |
| [Bullet Chart by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380953) | [Klip wideo](https://youtu.be/mtvUNl9bMjA) |
| [Calendar by Tallan](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381146) | |
| [Candlestick by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | [Klip wideo](https://youtu.be/nT_18gyRxPo) |
| [Card with States firmy OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380967) | |
| [Fragmentator Chiclet](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380756) | |
| [Chord](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380761) | [Klip wideo](https://youtu.be/AQvd2FhRyCI) |
| [Miernik okrągły firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380837) | [Klip wideo](https://youtu.be/9NHXALkBXuY) |
| [Mapa klastra](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380806) | |
| [Miernik cylindryczny firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | [Klip wideo](https://youtu.be/DgdoWi7Gcxo) |
| [Miernik zegarowy](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) | |
| [Wykres punktowy](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760) | |
| [Dot Plot by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380949) | [Klip wideo](https://youtu.be/By16pX9KT40) |
| [Drilldown Cartogram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045) | |
| [Drilldown Choropleth](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044) | |
| [Przechodzenie do szczegółów na wykresie kolumnowym](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380857) | [Klip wideo](https://youtu.be/lBy2gQQ5YsQ) |
| [Przechodzenie do szczegółów na wykresie kolumnowym dla danych opartych na czasie](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | [Klip wideo](https://youtu.be/T_mRou18vx0) |
| [Przechodzenie do szczegółów na wykresie pierścieniowym](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | [Klip wideo](https://youtu.be/AUVFrSHmPeo) |
| [Dual KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380774) | |
| [Dynamic Tooltip by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380983) | [Klip wideo](https://youtu.be/Z-tl97BpEr0) |
| [Enhanced Scatter](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | [Klip wideo](https://youtu.be/xCfM0cjM4do) |
| [Enlighten Aquarium](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381112) | |
| [Enlighten Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960) | |
| [Enlighten Stack Shuffle](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Wykres waflowy Enlighten](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Force-Directed Graph](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) | [Klip wideo](https://youtu.be/YsTa7uyJ4sg) |
| [Funnel with Source firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381334) | [Klip wideo](https://youtu.be/R_EcimsLI8U) |
| [Gantt](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380765) | [Klip wideo](https://youtu.be/qJ7s_KrGiUU) |
| [Wykres Gantta firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381364) | [Klip wideo](https://youtu.be/vJLV9JRCpI8) |
| [Globe Data Bars](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381344) | |
| [Wykres hierarchiczny firmy Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333) | [Klip wideo](https://youtu.be/0ZGzJaq_KT4) |
| [Histogram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380776) | |
| [Histogram z punktami firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381032) | [Klip wideo](https://youtu.be/-ILF--wExrw) |
| [Horizontal Funnel firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) | [Klip wideo](https://youtu.be/SudZei68PPo) |
| [Image firmy CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381297) | |
| [Siatka obrazów](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381355) | |
| [Infographic Designer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898) | |
| [Wykres KPI firmy Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381432) | |
| [KPI Indicator](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380832) | |
| [KPI Ticker by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | [Klip wideo](https://youtu.be/cudG4gsZ2V8) |
| [Miernik liniowy firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821) | [Klip wideo](https://youtu.be/7_jFaM30dkc) |
| [Wykres LineDot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766) | |
| [Wykres Mekko](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380785) | [Klip wideo](https://youtu.be/90FLCKpgicA) |
| [Play Axis (Dynamic Slicer)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380981) | |
| [Power KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381083) | [Klip wideo](https://youtu.be/IvfIP3E6-1Q) |
| [Power KPI — macierz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381299) | [Klip wideo](https://youtu.be/1enze8pcGzY) |
| [Pulse Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | [Klip wideo](https://youtu.be/DQWdcQtjDVw) |
| [Wykres kwadrantowy firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381011) | [Klip wideo](https://youtu.be/ppBnyhqWNC0) |
| [Wykres radarowy](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380771) | |
| [Ring Chart firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) | [Klip wideo](https://youtu.be/pDToHDFHnq8) |
| [Rotating Chart firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007) | [Klip wideo](https://youtu.be/d5xBCMmb3hU) |
| [Wykres Sankeya](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380777) | [Klip wideo](https://youtu.be/WWP9wVUHGaA) |
| [Scroller](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381018) | |
| [Smart Filter firmy SQLBI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380859) | [Klip wideo](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910) | [Klip wideo](https://youtu.be/0m3Vnvso9tY) |
| [Wykres strumieniowy](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772) | |
| [Sunburst](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767) | |
| [Table Heatmap](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380818) | |
| [Tachometer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380937) | [Klip wideo](https://youtu.be/C3OXdETbS9o) |
| [Filtr tekstowy](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381309) | |
| [Text Wrapper firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [Thermometer](https://appsource.microsoft.com/en-us/product/office/WA104379807) | |
| [Fragmentator osi czasu](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380786) | [Klip wideo](https://youtu.be/ozMtZ4_NZ10) |
| [Tornado chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380768) | [Klip wideo](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [Trading Chart firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380823) | [Klip wideo](https://youtu.be/xhTR6y6J9Ko) |
| [Ultimate Variance](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140) | [Klip wideo](https://youtu.be/pDYF8iZxERs) |
| [Ultimate Waterfall](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | [Klip wideo](https://youtu.be/0BZsVCQdEkc) |
| [Lista użytkowników firmy CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381426) | |
| [Wykres Waffle](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049) | [Klip wideo](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380752) | [Klip wideo](https://youtu.be/AblTenl9fqo) |

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do korzystania z narzędzi deweloperskich do tworzenia wizualizacji niestandardowych (wersja zapoznawcza)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Wizualizacje niestandardowe — lista odtwarzania firmy Microsoft w serwisie YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Wizualizacje w usłudze Power BI](power-bi-report-visualizations.md)  
[Wizualizacje niestandardowe w usłudze Power BI](power-bi-custom-visuals.md)  
[Publikowanie wizualizacji niestandardowych w witrynie Microsoft AppSource](developer/office-store.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

