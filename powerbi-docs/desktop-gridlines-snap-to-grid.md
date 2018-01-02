---
title: "Używanie linii siatki i przyciągania do siatki w raportach programu Power BI Desktop"
description: "Używanie linii siatki, przyciągania do siatki, porządku osi Z, wyrównania i rozkładania w raportach programu Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 7dc805f8e791a839bc6b69eb07a71496b64844a2
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2017
---
# <a name="use-gridlines-and-snap-to-grid-in-power-bi-desktop-reports"></a>Używanie linii siatki i przyciągania do siatki w raportach programu Power BI Desktop
Kanwa raportu programu **Power BI Desktop** udostępnia linie siatki, które pozwalają starannie wyrównywać wizualizacje na stronie raportu, i oferuje również funkcję przyciągania do siatki, dzięki czemu wizualizacje w raportach wyglądają przejrzyście, są wyrównane i mają równe odstępy.

W programie **Power BI Desktop** można również dostosować porządek osi Z (przesuwanie do przodu i do tyłu) obiektów w raporcie, a także wyrównać lub równomierne rozłożyć wybrane wizualizacje na kanwie.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_0.png)

### <a name="enabling-gridlines-and-snap-to-grid"></a>Włączanie linii siatki i przyciągania do siatki
Aby włączyć linie siatki i przyciąganie do siatki, wybierz wstążkę **Widok**, a następnie zaznacz pola wyboru dla opcji **Pokaż linie siatki** i **Przyciągaj obiekty do siatki**. Możesz zaznaczyć jedno pole lub oba, działają one niezależnie.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_1.png)

> [!NOTE]
> Jeśli opcje **Pokaż linie siatki** i **Przyciągaj obiekty do siatki** są wyłączone, połącz się z dowolnym źródłem danych, a zostaną one włączone.
> 
> 

### <a name="using-gridlines"></a>Używanie linii siatki
Linie siatki to prowadnice wizualizacji, które umożliwiają sprawdzenie, czy dwie lub większa liczba wizualizacji jest prawidłowo wyrównana. Gdy próbujesz określić, czy dwie (lub więcej) wizualizacje są wyrównane w poziomie lub pionie, używasz linii siatki, aby wizualnie ustalić, czy ich obramowania są wyrównane.

Możesz użyć kombinacji *CTRL+kliknięcie*, aby wybrać więcej niż jedną wizualizację jednocześnie, co powoduje wyświetlenie obramowań wszystkich zaznaczonych wizualizacji, dzięki czemu możesz łatwo sprawdzić, czy wizualizacje są dobrze wyrównane.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_2.png)

#### <a name="using-gridlines-inside-visuals"></a>Używanie linii siatki wewnątrz wizualizacji
W usłudze Power BI linie siatki znajdują się również wewnątrz wizualizacji —są one wizualnymi prowadnicami umożliwiającymi porównywanie punktów danych i wartości. Począwszy od wersji programu **Power BI Desktop** z września 2017 r., liniami siatki wewnątrz wizualizacji można zarządzać przy użyciu kart **Oś X** lub **Oś Y** (odpowiednio w zależności od typu wizualizacji), które znajdują się w sekcji **Format** okienka **Wizualizacje**. Można zarządzać następującymi elementami linii siatki wewnątrz wizualizacji:

* Włączanie i wyłączanie linii siatki
* Zmienianie koloru linii siatki
* Dostosowywanie obrysu (szerokości) linii siatki
* Wybieranie stylu linii siatki w wizualizacji, takiego jak ciągła, kreskowana lub kropkowana

Modyfikowanie niektórych elementów linii siatki może być szczególnie przydatne w raportach, w których wizualizacje mają ciemne tło. Poniższy obraz przedstawia sekcję *Linie siatki* na karcie **Oś X**.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_9.png)

### <a name="using-snap-to-grid"></a>Używanie przyciągania do siatki
Po włączeniu opcji **Przyciągaj obiekty do siatki** wszystkie wizualizacje na kanwie programu **Power BI Desktop**, które będziesz przenosić (lub których rozmiar będziesz zmieniać), będą automatycznie wyrównywane do najbliższej osi siatki, znacznie ułatwiając wyrównywanie dwóch lub większej liczby wizualizacji do tej samej lokalizacji pionowej lub poziomej bądź do tego samego rozmiaru.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_3.png)

I to wszystko, jeśli chodzi o używanie **linii siatki** i **przyciągania do siatki** w celu zapewnienia starannego wyrównania wizualizacji w raportach.

### <a name="using-z-order-align-and-distribute"></a>Używanie porządku osi Z, wyrównywania i rozkładania
Można również zarządzać kolejnością od przodu do tyłu wizualizacji w raporcie, co często jest nazywane *porządkiem osi Z* elementów. Dzięki temu możesz dowolnie nakładać na siebie wizualizacje, a następnie dostosować kolejność od przodu do tyłu każdej wizualizacji. To ustalanie kolejności wykonuje się przy użyciu przycisków **Przesuń do przodu** i **Przesuń do tyłu** znajdujących się w sekcji **Rozmieszczanie** wstążki **Formatowanie**, która jest wyświetlana po zaznaczeniu jednej lub kilku wizualizacji na stronie (ta wstążka nie jest dostępna, jeśli żadna wizualizacja nie jest zaznaczona).

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_4.png)

Wstążka **Formatowanie** umożliwia także wyrównywanie wizualizacji na wiele różnych sposobów. Dzięki temu możesz mieć pewność, że wizualizacje na stronie będą wyświetlane z wyrównaniem, które Twoim zdaniem wygląda i sprawdza się najlepiej.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_5.png)

Gdy jest zaznaczona jedna wizualizacja, użycie przycisku **Wyrównaj** wyrównuje tę wizualizację do krawędzi (lub środka) kanwy raportu, jak pokazano na poniższej ilustracji.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_6.png)

Gdy są wybrane co najmniej dwie wizualizacje, są one wyrównywane do siebie i do wyrównania jest używane istniejące wyrównane obramowanie wizualizacji. Na przykład po zaznaczeniu dwóch wizualizacji i wybraniu przycisku *Wyrównaj do lewej* zaznaczone wizualizacje zostaną wyrównane do skrajnego lewego obramowania wszystkich zaznaczonych wizualizacji.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_7.png)

Możesz również równomiernie rozłożyć wizualizacje na kanwie raportu w pionie lub w poziomie. Wystarczy użyć przycisku **Rozłóż** na wstążce **Formatowane**.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_8.png)

Dzięki wybraniu kilku opcji z tych narzędzi linii siarki, wyrównywania i rozkładania Twoje raporty będą wyglądały dokładnie tak, jak chcesz.

