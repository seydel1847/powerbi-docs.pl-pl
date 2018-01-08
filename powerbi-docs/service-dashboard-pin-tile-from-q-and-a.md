---
title: "Przypinanie kafelka do pulpitu nawigacyjnego z narzędzia pytań i odpowiedzi"
description: "Dokumentacja dotycząca sposobu przypinania kafelka do pulpitu nawigacyjnego usługi Power BI z pola pytania narzędzia pytań i odpowiedzi"
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
ms.date: 12/20/2017
ms.author: mihart
ms.openlocfilehash: 8a876c5a05fcdadff1a874148f5d56465bcc8c62
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="pin-a-tile-to-a-dashboard-from-qa"></a>Przypinanie kafelka do pulpitu nawigacyjnego z narzędzia pytań i odpowiedzi
## <a name="how-to-pin-a-tile-from-qa"></a>Przypinanie kafelka z narzędzia pytań i odpowiedzi
Narzędzie pytań i odpowiedzi to narzędzie raportowania ad hoc usługi Power BI. Chcesz znaleźć określone dane szczegółowe? Zadaj pytanie dotyczące danych i odbierz odpowiedź w postaci wizualizacji.

Pytania i odpowiedzi są dostępne na pulpitach nawigacyjnych i w raportach. W tym artykule otworzymy pytania i odpowiedzi z pulpitu nawigacyjnego. Pulpity nawigacyjne są dostępne w usłudze Power BI, ale nie w programie Power BI Desktop. Aby z tego skorzystać, otwórz [pulpit nawigacyjny przykładu Retail Analysis](sample-retail-analysis.md).
> 
> 

1. Otwórz [pulpit nawigacyjny](service-dashboards.md), który ma co najmniej jeden kafelek przypięty z raportu. Gdy zadajesz pytanie, usługa Power BI wyszukuje odpowiedź w dowolnym zestawie danych, który ma kafelek przypięty do tego pulpitu nawigacyjnego.  Aby dowiedzieć się więcej, zobacz [pobieranie danych](service-get-data.md).
2. W polu pytania w górnej części pulpitu nawigacyjnego rozpocznij wpisywanie tego, co chcesz wiedzieć o danych.  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-question-box.png)
3. Na przykład podczas wpisywania „sprzedaż za ostatni rok według miesiąca i terytorium”...  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-type-q-and-a.png)
   
   w polu pytania pojawiają się sugestie.
4. Aby dodać wykres do pulpitu nawigacyjnego jako kafelek, wybierz pinezkę ![](media/service-dashboard-pin-tile-from-q-and-a/pbi_pintile.png) po prawej górnej stronie kanwy.
5. Przypnij kafelek do istniejącego lub nowego pulpitu nawigacyjnego. 

   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin-to-dashboard.png)

   * Istniejący pulpit nawigacyjny: z listy rozwijanej wybierz nazwę pulpitu nawigacyjnego. Twój wybór będzie ograniczony tylko do pulpitów nawigacyjnych wewnątrz bieżącego obszaru roboczego.
   * Nowy pulpit nawigacyjny: wpisz nazwę nowego pulpitu nawigacyjnego a zostanie ona dodana do Twojego bieżącego obszaru roboczego.
6. Wybierz pozycję **Przypnij**.
   
   Komunikat o powodzeniu (w pobliżu prawego górnego rogu) informuje o tym, że wizualizacja została dodana do Twojego pulpitu nawigacyjnego jako kafelek.  
   
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin.png)
7. Wybierz pozycję **Przejdź do pulpitu nawigacyjnego**, aby wyświetlić nowy kafelek. Tam możesz [zmienić nazwę, rozmiar, dodać hiperlink i zmienić położenia kafelka i inne](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym. 
   
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Zagadnienia i rozwiązywanie problemów
* Po rozpoczęciu wprowadzania pytania narzędzie pytań i odpowiedzi natychmiast zaczyna wyszukiwanie najlepszej odpowiedzi we wszystkich zestawach danych skojarzonych z bieżącym pulpitem nawigacyjnym.  „Bieżący pulpit nawigacyjny” to pulpit nawigacyjny wymieniony na górnym pasku nawigacyjnym. Na przykład to pytanie jest zadawane na pulpicie nawigacyjnym **Próbka analizy handlu detalicznego**, który jest częścią obszaru roboczego aplikacji **mihart**.
  
  ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-navbar.png)
* **Skąd narzędzie pytań i odpowiedzi wie, których zestawów danych ma użyć**?  Narzędzie pytań i odpowiedzi ma dostęp do wszystkich zestawów danych, które mają wizualizacje przypięte do tego pulpitu nawigacyjnego.

## <a name="next-steps"></a>Następne kroki
[(Zmienianie nazwy, rozmiaru, dodawanie hiperlinku, zmienianie położenia kafelka i inne](service-dashboard-edit-tile.md)    
[Wyświetlanie kafelka pulpitu nawigacyjnego w trybie koncentracji uwagi](service-focus-mode.md)     
[Powrót do pytań i odpowiedzi w usłudze Power BI](service-q-and-a.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

