---
title: Certyfikowane wizualizacje niestandardowe w usłudze Power BI
description: Wymagania i proces przesyłania wizualizacji niestandardowej do certyfikacji. Oraz lista certyfikowanych wizualizacji niestandardowych.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/21/2018
ms.openlocfilehash: fd352cd78225e647acf53c2af899e4d2fc662376
ms.sourcegitcommit: 458e091a0a0bfb71ea3980d44df6408f48bab586
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2018
ms.locfileid: "52289271"
---
# <a name="certified-custom-visuals"></a>Certyfikowane wizualizacje niestandardowe

## <a name="what-are-certified-custom-visuals"></a>Co to są **_certyfikowane_** wizualizacje niestandardowe?

Certyfikowane wizualizacje niestandardowe to wizualizacje na platformie **Marketplace**, które spełniają **określone wymagania dotyczące kodu** i zostały przetestowane i zatwierdzone przez zespół usługi **Microsoft Power BI**. Certyfikowane wizualizacje niestandardowe oferują więcej funkcji. Możesz na przykład [eksportować je do programu PowerPoint](consumer/end-user-powerpoint.md) oraz wyświetlać je w wiadomościach e-mail otrzymywanych przez użytkowników, którzy [subskrybują strony raportów](consumer/end-user-subscribe.md).

**Certyfikowanych wizualizacji niestandardowych** używa się tak samo, jak [zwykłych wizualizacji niestandardowych](power-bi-custom-visuals.md). Certyfikowane wizualizacje niestandardowe można dodawać do **usługi Power BI** lub **raportu w programie Power BI Desktop**. Można także wyświetlać je za pomocą **usługi Power BI dla urządzeń przenośnych** oraz **usługi Power BI Embedded**.

Wykonywane testy mają na celu sprawdzenie, czy wizualizacja nie korzysta z usług ani zasobów zewnętrznych. Firma **Microsoft** *nie* jest autorem wizualizacji niestandardowych tworzonych przez inne firmy, dlatego zalecamy użytkownikom bezpośredni kontakt z autorami w celu zweryfikowania funkcjonalności takich wizualizacji.

Proces certyfikacji jest opcjonalny — to od dewelopera zależy, czy chce, aby jego wizualizacja dostępna na platformie Marketplace była certyfikowana.  

**Wizualizacje niestandardowe, które nie są certyfikowane**, nie muszą być niebezpieczne. Niektóre wizualizacje nie są certyfikowane, ponieważ nie spełniają pewnych [wymagań dotyczących certyfikacji](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Mogą na przykład łączyć się z usługą zewnętrzną, jak w przypadku wizualizacji map czy wizualizacji korzystających z bibliotek komercyjnych.

Jesteś deweloperem internetowym i chcesz utworzyć własne wizualizacje oraz dodać je do witryny  **[Microsoft AppSource](https://appsource.microsoft.com)**? Aby dowiedzieć się, jak to zrobić, zobacz  **[Tworzenie wizualizacji niestandardowej w usłudze Power BI](developer/custom-visual-develop-tutorial.md)**.

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Usuwanie certyfikowanych wizualizacji niestandardowych usługi Power BI

Firma Microsoft może według własnego uznania usunąć wizualizację z [listy certyfikowanych wizualizacji](#list-of-custom-visuals-that-have-been-certified).

## <a name="getting-a-custom-visualcertified"></a>Certyfikowanie wizualizacji niestandardowej

### <a name="certification-requirements"></a>Wymagania dotyczące certyfikacji

Aby [certyfikować](#certified-custom-visuals) swoją wizualizację niestandardową, sprawdź, czy spełnia ona poniższe wymagania:  

* Wizualizacja jest zatwierdzona w witrynie Microsoft AppSource. Wizualizacja niestandardowa powinna być dostępna na naszej [platformie handlowej](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals).
* Wizualizacja niestandardowa jest zapisana przy użyciu interfejsu API w wersji 1.2 lub nowszej.
* Repozytorium kodu jest dostępne do przeglądu przez zespół usługi Power BI (na przykład kod źródłowy JavaSCriptS lub TypeScript w formacie czytelnym dla człowieka jest dla nas dostępny w witrynie GitHub).

    >[!Note]
    > Nie musisz publicznie udostępniać kodu w witrynie Github.

* Wizualizacja korzysta wyłącznie ze składników OSS dostępnych do przeglądu publicznie (publicznych bibliotek JS lub TypeScript). Kod źródłowy jest dostępny do przeglądu i nie ma znanych luk w zabezpieczeniach. Nie możemy zweryfikować wizualizacji niestandardowej korzystającej ze składników komercyjnych.

* Wizualizacja nie korzysta z usług ani zasobów zewnętrznych, a więc między innymi nie wymaga wysyłania żadnych żądań HTTP/S ani WebSocket z usługi Power BI do jakichkolwiek innych usług. 

> [!TIP]
> Zalecamy użycie programu EsLint z domyślnym zestawem reguł zabezpieczeń w celu wstępnego zweryfikowania kodu przed przesłaniem.

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>Proces przesyłania wizualizacji niestandardowej do certyfikacji

Aby przesłać wizualizację niestandardową do certyfikacji:

1. Wyślij wiadomość e-mail do zespołu pomocy technicznej w zakresie wizualizacji niestandardowych usługi Power BI (pbicvsupport@microsoft.com). W wiadomości e-mail uwzględnij następujące informacje:
    * Tytuł: Visual Certification Request
    * Link do repozytorium w witrynie GitHub, w którym znajduje się kod źródłowy wizualizacji w formacie czytelnym dla człowieka.
    * [Zapewnij zgodność z wymogami](#certification-requirements).
    * Udostępnij kod do przeglądu.

2. Zespół ds. wizualizacji niestandardowych w firmie Microsoft powiadomi Cię, gdy Twoja wizualizacja niestandardowa zostanie certyfikowana i dodana do [listy wizualizacji certyfikowanych](#list-of-custom-visuals-that-have-been-certified) lub odrzucona (wówczas do powiadomienia będzie dołączony raport z informacjami, co należy naprawić). Deweloper odpowiada za utrzymanie komunikacji z firmą Microsoft i zaktualizowanie certyfikowanych wizualizacji w wymagany sposób.

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
| [Filtrowanie według listy firmy Devscope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381413) | [Klip wideo](https://youtu.be/RetEWGwBu0I) |
| [Force-Directed Graph](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) | [Klip wideo](https://youtu.be/YsTa7uyJ4sg) |
| [Funnel with Source firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381334) | [Klip wideo](https://youtu.be/R_EcimsLI8U) |
| [Gantt](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380765) | [Klip wideo](https://youtu.be/qJ7s_KrGiUU) |
| [Wykres Gantta firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381364) | [Klip wideo](https://youtu.be/vJLV9JRCpI8) |
| [Globe Data Bars](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381344) | |
| [Grid by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380825) | [Klip wideo](https://youtu.be/VOPoDJgZfOY) |
| [Wykres hierarchiczny firmy Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333) | [Klip wideo](https://youtu.be/0ZGzJaq_KT4) |
| [Histogram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380776) | |
| [Histogram z punktami firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381032) | [Klip wideo](https://youtu.be/-ILF--wExrw) |
| [Horizontal Funnel firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) | [Klip wideo](https://youtu.be/SudZei68PPo) |
| [Image firmy CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381297) | |
| [Siatka obrazów](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381355) | |
| [Infographic Designer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898) | |
| [Wykres KPI firmy Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381432) | |
| [KPI Column firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380996) | [Klip wideo](https://youtu.be/rU0xoOlIq1U) |
| [KPI Grid firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380947) | [Klip wideo](https://youtu.be/dM4PvZh71V0) |
| [KPI Indicator](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380832) | |
| [KPI Ticker by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | [Klip wideo](https://youtu.be/cudG4gsZ2V8) |
| [Miernik liniowy firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821) | [Klip wideo](https://youtu.be/7_jFaM30dkc) |
| [Wykres LineDot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766) | |
| [Wykres Mekko](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380785) | [Klip wideo](https://youtu.be/90FLCKpgicA) |
| [Wiele kluczowych wskaźników wydajności](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381763) | |
| [Overview firmy CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381477) | |
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
| [Synoptic Panel firmy OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380873) | |
| [Table Heatmap](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380818) | |
| [Tachometer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380937) | [Klip wideo](https://youtu.be/C3OXdETbS9o) |
| [Filtr tekstowy](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381309) | |
| [Text Wrapper firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [Thermometer firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380847) | [Klip wideo](https://youtu.be/SPX9mgrAdBc) |
| [Fragmentator Time Brush](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380798) | |
| [Fragmentator osi czasu](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380786) | [Klip wideo](https://youtu.be/ozMtZ4_NZ10) |
| [Timeline firmy CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381427) | [Klip wideo](https://youtu.be/szNi9YgXFJc) |
| [Tornado chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380768) | [Klip wideo](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [Trading Chart firmy MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380823) | [Klip wideo](https://youtu.be/xhTR6y6J9Ko) |
| [Ultimate Variance](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140) | [Klip wideo](https://youtu.be/pDYF8iZxERs) |
| [Ultimate Waterfall](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | [Klip wideo](https://youtu.be/0BZsVCQdEkc) |
| [Lista użytkowników firmy CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381426) | |
| [Wykres Waffle](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049) | [Klip wideo](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380752) | [Klip wideo](https://youtu.be/AblTenl9fqo) |

## <a name="next-steps"></a>Następne kroki

* [Tworzenie wizualizacji niestandardowej w usłudze Power BI](developer/custom-visual-develop-tutorial.md)
* [Wizualizacje niestandardowe — lista odtwarzania firmy Microsoft w serwisie YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Wizualizacje w usłudze Power BI](visuals/power-bi-report-visualizations.md)  
* [Wizualizacje niestandardowe w usłudze Power BI](power-bi-custom-visuals.md)  
* [Publikowanie wizualizacji niestandardowych w witrynie Microsoft AppSource](developer/office-store.md)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)
