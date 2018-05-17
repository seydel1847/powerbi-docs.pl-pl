---
title: Kategoryzacja danych w programie Power BI Desktop
description: Kategoryzacja danych w programie Power BI Desktop
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
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: f5eb26eee9bedbdd804dfba1912a1aa328310816
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="data-categorization-in-power-bi-desktop"></a>Kategoryzacja danych w programie Power BI Desktop
W programie **Power BI Desktop** możesz określić kategorię danych dla kolumny, aby poinformować program Power BI Desktop, jak powinien traktować jej wartości w wizualizacji.

Gdy program Power BI Desktop importuje dane, pobiera nie tylko same dane, ale także m.in. nazwy tabel i kolumn, informacje o tym, czy dane są kluczem podstawowym itd.  Dzięki tym informacjom program Power BI Desktop przyjmuje pewne założenia, aby zapewnić Ci dobre środowisko domyślne podczas tworzenia wizualizacji. 

Oto przykład: gdy program Power BI Desktop wykrywa, że kolumna zawiera wartości liczbowe, zakłada, że prawdopodobnie zechcesz agregować je w jakiś sposób, dlatego umieszcza ją w obszarze Wartości. Albo zakłada, że kolumna zawierająca wartości daty/godziny prawdopodobnie będzie używana jako oś hierarchii czasu na wykresie liniowym.

Jednak w pewnych sytuacjach, na przykład w przypadku lokalizacji geograficznej, jest to nieco trudniejsze. Rozważ następującą tabelę z arkusza programu Excel:

![](media/desktop-data-categorization/datacategorizationtable.png)

Czy program Power BI Desktop powinien traktować kody w kolumnie GeoCode jako skrót kraju, czy stanu USA?  Nie jest to oczywiste, ponieważ taki kod może oznaczać i jedno, i drugie.  Na przykład AL może oznaczać Alabamę lub Albanię, AR może oznaczać Arkansas lub Argentynę, a CA może oznaczać Kalifornię lub Kanadę. Ma to duże znaczenie, gdy tworzymy wykres naszego pola GeoCode na mapie.  Czy program Power BI Desktop powinien wyświetlać mapę świata z wyróżnionymi krajami, czy mapę Stanów Zjednoczonych z wyróżnionymi stanami?  Kategorię danych możesz określić w taki sposób. Kategoryzacja danych dodatkowo precyzuje informacje, za pomocą których program Power BI Desktop może tworzyć lepsze wizualizacje.  

**Aby określić kategorię danych**

1. W widoku raportu lub widoku danych na liście **Pola** wybierz pole, które ma być sortowane według innej kategoryzacji.
2. Na wstążce na karcie **Modelowanie** kliknij listę rozwijaną **Kategoria danych**.  Zostanie wyświetlona lista kategorii danych, które możesz wybrać dla kolumny.  Niektóre opcje mogą być wyłączone, jeśli nie współpracują one z bieżącym typem danych kolumny.  Na przykład jeśli kolumna ma typ danych binarnych, program Power BI Desktop nie pozwoli wybrać kategorii danych geograficznych. 

![](media/desktop-data-categorization/datacategorization.gif)

I to wszystko.  Każde zachowanie, które jest zwykle związane z wizualizacją, będzie teraz działać automatycznie.  

Może również zainteresować Cię [filtrowanie lokalizacji geograficznych dla aplikacji mobilnych usługi Power BI](desktop-mobile-geofiltering.md).

