---
title: Używanie przeglądania szczegółowego w programie Power BI Desktop
description: Dowiedz się, jak przechodzić do szczegółowych danych na nowej stronie raportu w programie Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: d0c78643d285099f7b7856704ac7ee350ff9f93a
ms.sourcegitcommit: 509be8852ba7595b9441c9479224f9dca298b26d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/09/2018
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Używanie przeglądania szczegółowego w programie Power BI Desktop
**Przeglądanie szczegółowe** w programie **Power BI Desktop** umożliwia utworzenie strony w raporcie, która koncentruje się na określonej jednostce — takiej jak dostawca, klient lub producent. Dzięki tej skoncentrowanej stronie użytkownicy mogą kliknąć prawym przyciskiem myszy punkt danych na innej stronie raportu i użyć przeglądania szczegółowego, aby przejść do tej skoncentrowanej strony w celu uzyskania szczegółów przefiltrowanych do danego kontekstu.

![korzystanie z przeglądania szczegółowego](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Korzystanie z przeglądania szczegółowego
1. Aby używać **przeglądania szczegółowego**, utwórz stronę raportu zawierającą wizualizacje, które chcesz zobaczyć, dotyczące typu jednostki, dla którego zapewnisz przeglądanie szczegółowe. 

    Jeśli na przykład chcesz dostarczyć przeglądanie szczegółowe dla producentów, możesz utworzyć stronę przeglądania szczegółowego z wizualizacjami przedstawiającymi sprzedaż całkowitą, sumę wysłanych jednostek, sprzedaż według kategorii, sprzedaż według regionu i tak dalej. W ten sposób, gdy przejdziesz do szczegółów znajdujących się na tej stronie, wizualizacje będą dotyczyć wybranego producenta.

2. Następnie na tej stronie przeglądania szczegółowego w sekcji **Pola** okienka **Wizualizacje** przeciągnij pole, którego szczegóły chcesz przeglądać, do obszaru **Filtry przeglądania szczegółowego**.

    ![obszar przeglądania szczegółowego](media/desktop-drillthrough/drillthrough_02.png)

    Po dodaniu pola do obszaru **Filtry przeglądania szczegółowego** program **Power BI Desktop** automatycznie utworzy wizualizację przycisku *wstecz*. Ta wizualizacja stanie się przyciskiem w opublikowanych raportach i umożliwi użytkownikom korzystającym z raportu w **usłudze Power BI** łatwy powrót do strony raportu, z której przyszli (jest to strona, na której została wybrana opcja przeglądania szczegółowego).

    ![obraz przeglądania szczegółowego](media/desktop-drillthrough/drillthrough_03.png)

## <a name="use-your-own-image-for-a-back-button"></a>Używanie własnego obrazu na przycisku Wstecz    
 Przycisk Wstecz jest obrazem, dlatego możesz zamienić obraz tej wizualizacji na inny dowolny obraz, i nadal będzie on działać jako przycisk Wstecz umożliwiający użytkownikom raportu powrót do ich oryginalnej strony.

1. Na karcie **Narzędzia główne** kliknij pozycję **Obraz**, a następnie zlokalizuj swój obraz i umieść go na stronie przeglądania szczegółowego.
2. Wybierz nowy obraz na stronie przeglądania szczegółowego, a następnie w sekcji formatowania obrazu ustaw suwak **Link** na pozycję oznaczającą włączenie i ustaw pozycję **Typ** na wartość **Wstecz**. Twój obraz działa teraz jako przycisk Wstecz.

    ![użycie obrazu dla przycisku wstecz](media/desktop-drillthrough/drillthrough_05.png)

    Gdy strona **przeglądania szczegółowego** będzie gotowa, a użytkownicy klikną prawym przyciskiem myszy punkt danych w raporcie, który używa pola umieszczonego w obszarze **Filtry przeglądania szczegółowego**, zostanie wyświetlone menu kontekstowe obsługujące przechodzenie do szczegółów na tej stronie.

    ![menu przeglądania szczegółowego](media/desktop-drillthrough/drillthrough_04.png)

    Gdy użytkownicy raportu wybiorą opcję przeglądania szczegółowego, strona zostanie odfiltrowana w celu wyświetlenia informacji na temat punktu danych, który kliknięto prawym przyciskiem myszy. Jeśli na przykład użytkownik kliknie prawym przyciskiem myszy punkt danych firmy Contoso (producent) i wybierze przeglądanie szczegółowe, strona przeglądania szczegółowego, do której przejdzie użytkownik, będzie filtrowana w celu wyświetlenia informacji o firmie Contoso.

## <a name="pass-all-filters-in-drillthrough"></a>Przekazywanie wszystkich filtrów w przeglądaniu szczegółowym

Począwszy od programu **Power BI Desktop** w wersji z maja 2018 r. wszelkie zastosowane filtry można przekazać do okna przeglądania szczegółowego. Na przykład można mieć wybraną tylko konkretną kategorię produktów i wizualizacje przefiltrowane pod kątem tej kategorii, a następnie wybrać przeglądanie szczegółowe. Może Cię zainteresować, jak wyglądałoby przeglądanie szczegółowe z zastosowanymi wszystkimi tymi filtrami.

Aby zachować wszystkie zastosowane filtry, w sekcji **Przeglądanie szczegółowe** okienka **Wizualizacje** po prostu ustaw przełącznik **Przekaż wszystkie filtry** na pozycję **Włączone**. 

![zachowanie wszystkich filtrów](media/desktop-drillthrough/drillthrough_06.png)

W wersjach programu **Power BI Desktop** sprzed maja 2018 r. działanie jest odpowiednikiem ustawienia tego przełącznika na pozycję **Wyłączone**.

Gdy następnie będziesz przechodzić do szczegółów w wizualizacji, zobaczysz, które filtry zostały zastosowane w efekcie zastosowania filtrów tymczasowych w wizualizacjach źródłowych. W oknie przeglądania szczegółowego te filtry przejściowe są pokazywane kursywą. 

![filtry przejściowej pokazywane kursywą](media/desktop-drillthrough/drillthrough_07.png)

Pamiętaj, że można to zrobić na stronach etykietek, ale będzie to dziwne doświadczenie (etykietki będą wyglądały na działające nieprawidłowo), wiec robienie tego z etykietkami nie jest zalecane.

To wszystko na temat używania **przeglądania szczegółowego** w raportach. Jest to doskonały sposób wyświetlania rozszerzonych informacji na temat jednostki wybranej dla filtru przeglądania szczegółowego.

## <a name="next-steps"></a>Następne kroki

Może zainteresują Cię również następujące artykuły:

* [Korzystanie z fragmentatorów w programie Power BI Desktop](desktop-slicers.md)

