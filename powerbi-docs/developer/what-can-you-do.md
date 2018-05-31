---
title: Co deweloperzy mogą robić z usługą Power BI?
description: 'Usługa Power BI oferuje szeroką gamę opcji dla deweloperów. Obejmuje to różne możliwości: od osadzania po wizualizacje niestandardowe i przesyłanie strumieniowe zestawów danych.'
author: markingmyname
ms.author: maghan
ms.date: 05/03/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: ee9f5b2e89a1746267090da3485076d67a99d6f9
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34290573"
---
# <a name="what-can-developers-do-with-power-bi"></a>Co deweloperzy mogą robić z usługą Power BI?

Deweloperzy mają różne opcje uwzględniania zawartości usługi Power BI w aplikacjach. Obejmują one **osadzanie przy użyciu usługi Power BI**, **wizualizacje niestandardowe** i **wypychanie danych do usługi Power BI**.

## <a name="embedding"></a>Osadzanie
Usługa Power BI (SaaS) i usługa Power BI Embedded na platformie Azure (PaaS) mają interfejsy API umożliwiające osadzanie pulpitów nawigacyjnych i raportów. Oznacza to zestaw funkcji oraz dostęp do najnowszych funkcji usługi Power BI — takich jak pulpity nawigacyjne, bramy i obszary robocze aplikacji — podczas osadzania zawartości.

![Przykład usługi PBIE](media/what-can-you-do/what-can-you-do-01.png)

## <a name="develop-custom-visuals"></a>Tworzenie wizualizacji niestandardowych
Wizualizacje niestandardowe umożliwiają tworzenie własnych wizualizacji do użytku w raportach usługi Power BI. Wizualizacje niestandardowe są pisane w języku TypeScript będącym nadzbiorem języka JavaScript. Język TypeScript obsługuje niektóre zaawansowane funkcje i wczesny dostęp do funkcji ES6/ES7. Style wizualizacji są obsługiwane za pomocą kaskadowych arkuszy stylów (CSS). Dla wygody używany jest kompilator wstępny języka Less, obsługujący niektóre funkcje zaawansowane, takie jak zagnieżdżanie, zmienne, warunki, pętle itp. Jeśli nie chcesz używać żadnych z tych funkcji, możesz zapisać w pliku języka Less zwykły kod CSS.

![Przykład wizualizacji niestandardowej](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Wypychanie danych do usługi Power BI
Za pomocą interfejsu API usługi Power BI możesz wypychać dane do zestawu danych. Umożliwia to dodanie wiersza do tabeli w zestawie danych. Nowe dane mogą wówczas zostać odzwierciedlone na kafelkach na pulpicie nawigacyjnym i w wizualizacjach w raporcie.

![Przykład wypychania danych](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>Następne kroki
[Osadzanie przy użyciu usługi Power BI](embedding.md)  
[Publikowanie wizualizacji niestandardowych w Sklepie Office](office-store.md)  
[Wypychanie danych do pulpitu nawigacyjnego](walkthrough-push-data.md)
