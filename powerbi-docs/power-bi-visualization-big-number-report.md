---
title: "Tworzenie kafelka z dużą liczbą za pomocą raportu usługi Power BI"
description: "Tworzenie kafelka z dużą liczbą za pomocą raportu usługi Power BI"
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
ms.openlocfilehash: 9f748ed1d3a34c6c6aceb14337bbb780598a15f9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-big-number-tile-from-a-power-bi-report"></a>Tworzenie kafelka z dużą liczbą za pomocą raportu usługi Power BI
Czasami jedna liczba jest najważniejsza i chcesz ją śledzić na swoim pulpicie nawigacyjnym usługi Power BI, np. łączna sprzedaż, udział w rynku rok do roku lub całkowite możliwości. Możesz utworzyć kafelek z dużą liczbą, [zadając pytanie w polu pytań i odpowiedzi](power-bi-visualization-big-number.md) lub w raporcie usługi Power BI. W tym artykule wyjaśniono, jak utworzyć ją w raporcie.

1. Utwórz [pulpit nawigacyjny](service-dashboards.md) i [pobierz dane](service-get-data.md).
   
   Jeśli potrzebujesz danych do eksperymentowania, [pobierz przykład analizy detalicznej](sample-retail-analysis.md). 
2. Otwórz raport w [widoku do edycji](service-reading-view-and-editing-view.md).
3. W raporcie znajdź stronę z pustym miejscem lub [dodaj nową stronę do raportu](power-bi-report-add-page.md).
4. Na liście pól wybierz pole liczby, którą chcesz wyświetlić.
   
   W tym przykładzie **otwórz licznik magazynów** w tabeli **Magazyn**. Usługa Power BI tworzy wykres kolumnowy dla jednej liczby.
   
   ![](media/power-bi-visualization-big-number-report/pbi_rptnumbertilechart.png)
5. W okienku Wizualizacje wybierz ikonę karty.
   
   ![](media/power-bi-visualization-big-number-report/pbi_changechartcard.png)
6. Umieść kursor nad kartą i wybierz ikonę pinezki ![](media/power-bi-visualization-big-number-report/pbi_pintile.png), aby dodać kafelek do pulpitu nawigacyjnego. 
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-icon.png)
7. Przypnij kafelek do istniejącego lub nowego pulpitu nawigacyjnego. 
   
   * Istniejący pulpit nawigacyjny: z listy rozwijanej wybierz nazwę pulpitu nawigacyjnego.
   * Nowy pulpit nawigacyjny: wpisz nazwę nowego pulpitu nawigacyjnego.
8. Wybierz pozycję **Przypnij**.
   
   Komunikat o powodzeniu (w prawym górnym rogu) informuje o tym, że wizualizacja została dodana do pulpitu nawigacyjnego jako kafelek.
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-success-message.png)
9. Wybierz pozycję **Przejdź do pulpitu nawigacyjnego**. Tam możesz [edytować i przenieść](service-dashboard-edit-tile.md) przypiętą wizualizację.

## <a name="next-steps"></a>Następne kroki
[Kafelki pulpitu nawigacyjnego w usłudze Power BI](service-dashboard-tiles.md)

[Pulpity nawigacyjne w usłudze Power BI](service-dashboards.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

