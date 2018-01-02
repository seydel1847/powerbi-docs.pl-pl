---
title: "Tworzenie kafelka z dużą liczbą za pomocą funkcji Pytania i odpowiedzi"
description: "Tworzenie kafelka z dużą liczbą dla pulpitu nawigacyjnego usługi Power BI przez zadanie pytania"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 559484c341ec017890a4075a393d5ce211843b5f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-big-number-tile-from-qa"></a>Tworzenie kafelka z dużą liczbą za pomocą funkcji Pytania i odpowiedzi
Czasami jedna liczba jest najważniejsza i chcesz ją śledzić na swoim pulpicie nawigacyjnym usługi Power BI, np. łączna sprzedaż, udział w rynku rok do roku lub całkowite możliwości. Możesz [utworzyć kafelek z dużą liczbą w raporcie usługi Power BI](power-bi-visualization-big-number-report.md), zadając pytanie w polu Pytania i odpowiedzi. W tym artykule wyjaśniono, jak utworzyć kafelek za pomocą funkcji Pytania i odpowiedzi.

![](media/power-bi-visualization-big-number/pbi_opptuntiescard.png)

Skorzystanie z pola pytania jest najprostszym sposobem utworzenia takiego kafelka z liczbą.

1. Utwórz [pulpit nawigacyjny](service-dashboards.md) i [pobierz dane](service-get-data.md). W tym przypadku jest używany [przykład Opportunity Analysis](sample-opportunity-analysis.md).
2. W polu pytania w górnej części pulpitu nawigacyjnego rozpocznij wpisywanie tego, co chcesz wiedzieć o danych. W tym przypadku jest używany przykład Opportunity Analysis.
   
   ![](media/power-bi-visualization-big-number/power-bi-q-and-a-box.png)
3. Na przykład wpisz w polu pytania „number of opportunities” (liczba możliwości).
   
   ![](media/power-bi-visualization-big-number/power-bi-ask.png)
   
   W polu pytania zostanie zasugerowana zmiana frazy na **Showing opportunity count** (Wyświetlanie liczby możliwości) i zostanie wyświetlona łączna ich liczba.  
4. Wybierz ikonę pinezki ![](media/power-bi-visualization-big-number/pbi_pintile.png) w prawym górnym rogu, aby dodać kafelek z liczbą do pulpitu nawigacyjnego. 
   
   ![](media/power-bi-visualization-big-number/power-bi-pin.png)
5. Przypnij kafelek do istniejącego lub nowego pulpitu nawigacyjnego. 
   
   * Istniejący pulpit nawigacyjny: z listy rozwijanej wybierz nazwę pulpitu nawigacyjnego. Twój wybór będzie ograniczony tylko do tych pulpitów nawigacyjnych wewnątrz bieżącego obszaru roboczego.
   * Nowy pulpit nawigacyjny: wpisz nazwę nowego pulpitu nawigacyjnego a zostanie ona dodana do Twojego bieżącego obszaru roboczego.
6. Wybierz pozycję **Przypnij**.
   
   Komunikat o powodzeniu (w prawym górnym rogu) informuje o tym, że wizualizacja została dodana do pulpitu nawigacyjnego jako kafelek.  
   
   ![](media/power-bi-visualization-big-number/power-bi-success.png)
7. Wybierz pozycję **Przejdź do pulpitu nawigacyjnego**, aby wyświetlić nowy kafelek. Tam możesz [zmienić nazwę, rozmiar, dodać hiperlink i zmienić położenia kafelka i inne](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym. 
   
   ![](media/power-bi-visualization-big-number/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów
Jeśli pole pytania nie jest w ogóle widoczne, skontaktuj się z administratorem systemu lub dzierżawy.

## <a name="next-steps"></a>Następne kroki
[Kafelki pulpitu nawigacyjnego w usłudze Power BI](service-dashboard-tiles.md)  
[Pulpity nawigacyjne w usłudze Power BI](service-dashboards.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

