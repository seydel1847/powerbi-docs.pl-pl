---
title: "Certyfikowane wizualizacje niestandardowe w usłudze Power BI"
description: "Wymagania i proces przesyłania wizualizacji niestandardowej do certyfikacji. Oraz lista certyfikowanych wizualizacji niestandardowych."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/20/2017
ms.author: mihart
ms.openlocfilehash: 3d51475b300fadc55f33960b03c3adc0031a39b8
ms.sourcegitcommit: 12236d08c27c7ee3fabb7ef9d767e9dee693f8aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="getting-a-custom-visual-certified"></a>*Certyfikowanie* wizualizacji niestandardowej
## <a name="what-is-meant-by-certified"></a>Co oznacza *certyfikowanie*?
*Certyfikowana wizualizacja niestandardowa* to wizualizacja, która spełnia zestaw określonych wymagań dotyczących kodu i przeszła restrykcyjne testy bezpieczeństwa.  Zarejestrowane wizualizacje niestandardowe mogą zostać [wyeksportowane do programu PowerPoint](service-publish-to-powerpoint.md) i będą wyświetlane w wiadomościach e-mail, jeśli użytkownik [subskrybuje strony raportu](service-report-subscribe.md).

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
| [Aster plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [Bowtie chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838?src=office&tab=Overview) |[Klip wideo](https://youtu.be/So5xKMSpVJI) |
| [BciCalendar (Beyondsoft Calendar)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096?src=office&tab=Overview)  | |
| [Box and Whisker](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [Bullet Chart](https://store.office.com/app.aspx?assetid=WA104380755) |[Klip wideo 1](https://youtu.be/AOlsFYkfkcw)   [Klip wideo 2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet Chart by OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[Klip wideo](https://youtu.be/mtvUNl9bMjA) |
| [Calendar by Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146?src=office&tab=Overview) | |
| [Chiclet slicer](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[Klip wideo](https://youtu.be/iYOkJ1APueY) |
| [Chord Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761?src=office&tab=Overview) |[Klip wideo](https://youtu.be/AQvd2FhRyCI) |
| [Circular gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [Cylindrical gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | |
| [Dial gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) |[Klip wideo](https://youtu.be/AOlsFYkfkcw) |
| [Donut chart (Ring chart) by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[Klip wideo](https://youtu.be/pDToHDFHnq8) |
| [Dot Plot by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104381101?src=office&tab=Overview) |[Klip wideo](https://youtu.be/4lskRgcpFJY) |
| [Drill down donut chart by ZoomCharts](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | |
| [Dual KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[Klip wideo](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112?src=office&tab=Overview) | |
| Enlighten World Flags — wkrótce | |
| Enlighten Stack Shuffle — wkrótce | |
| [Gantt](https://store.office.com/gantt-WA104380765.aspx) |[Klip wideo](https://youtu.be/qJ7s_KrGiUU) |
| [Histogram](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [Horizotal Funnel](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) |[Klip wideo](https://youtu.be/SudZei68PPo) |
| [KPI Indicator](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| [Linear gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[Klip wideo](https://youtu.be/AOlsFYkfkcw) |
| [Mekko chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785?src=office&tab=Overview)  | [Klip wideo](https://youtu.be/90FLCKpgicA)|
| [Play Axis (Dynamic Slicer)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[Klip wideo](https://youtu.be/IvfIP3E6-1Q) |
| [Radar chart](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Ring chart (Donut chart) by MAQSoftware](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824?src=office&tab=Overview) | [Klip wideo](https://youtu.be/pDToHDFHnq8)|
| [Sankey chart](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[Klip wideo](https://youtu.be/WWP9wVUHGaA) |
| [Scroller](https://store.office.com/scroller-WA104381018.aspx) |[Klip wideo](https://youtu.be/uhRFQF2cGSY) |
| [Smart Filter by SQLBI](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[Klip wideo](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[Klip wideo](https://youtu.be/0m3Vnvso9tY) |
| [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [Tachometer](https://store.office.com/tachometer-WA104380937.aspx?) |[Klip wideo](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [Thermometer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847?src=office&tab=Overview) | [Klip wideo](https://youtu.be/SPX9mgrAdBc)|
| [Time series decomposition](https://appsource.microsoft.com/product/power-bi-visuals/WA104380897) | |
| [Table Heatmap](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [Text wrapper](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [Timeline slicer](https://store.office.com/timeline-slicer-WA104380786.aspx) |[Klip wideo](https://youtu.be/ozMtZ4_NZ10) |
| [Tornado chart](https://store.office.com/tornado-chart-WA104380768.aspx) |[Klip wideo](https://youtu.be/AQvd2FhRyCI) |
| [Waffle chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[Klip wideo](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://store.office.com/word-cloud-WA104380752.aspx?) |[Klip wideo](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do korzystania z narzędzi deweloperskich do tworzenia wizualizacji niestandardowych (wersja zapoznawcza)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Wizualizacje niestandardowe — lista odtwarzania firmy Microsoft w serwisie YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Wizualizacje w usłudze Power BI](power-bi-report-visualizations.md)  
[Wizualizacje niestandardowe w usłudze Power BI](power-bi-custom-visuals.md)  
[Publikowanie wizualizacji niestandardowych w witrynie Microsoft AppSource](developer/office-store.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

