---
title: "Dwukierunkowe filtrowanie krzyżowe w programie Power BI Desktop (wersja zapoznawcza)"
description: "Włączanie filtrowania krzyżowego za pomocą zapytania bezpośredniego w programie Power BI Desktop"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 7946a9389897c4401e581482c0630547a764616d
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop-preview"></a>Dwukierunkowe filtrowanie krzyżowe przy użyciu zapytania bezpośredniego w programie Power BI Desktop (wersja zapoznawcza)

Podczas filtrowania tabel w celu uzyskania odpowiedniego widoku danych twórcy raportów (i osoby modelujące dane) stają przed wyzwaniem ustalenia, jak filtrowanie jest stosowane do raportu. Kontekst filtru tabeli został ustalony po jednej stronie relacji, ale nie po drugiej, co często wymaga zastosowania złożonych formuł języka DAX w celu uzyskania żądanych wyników.

Dzięki dwukierunkowemu filtrowaniu krzyżowemu twórcy raportów (i osoby modelujące dane) mają większą kontrolę nad sposobem stosowania filtrów podczas pracy z powiązanymi tabelami, umożliwiając zastosowanie tych filtrów po *obu* stronach relacji tabeli. Jest to osiągane przez propagowanie kontekstu filtru do drugiej powiązanej tabeli po drugiej stronie relacji tabeli.

Dostępny jest [szczegółowy oficjalny dokument](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) objaśniający dwukierunkowe filtrowanie krzyżowe w programie Power BI Desktop (ten oficjalny dokument obejmuje również usługi SQL Server Analysis Services 2016, ponieważ zachowują się one tak samo).

* Pobierz oficjalny dokument [Bidirectional cross-filtering for Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) (Dwukierunkowe filtrowanie krzyżowe dla programu Power BI Desktop)

### <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>Włączanie dwukierunkowego filtrowania krzyżowego dla zapytania bezpośredniego
Aby można było używać filtrowania krzyżowego dla zapytania bezpośredniego, należy najpierw je włączyć. Jest to funkcja w wersji zapoznawczej, co oznacza, że jej dostępność i zachowanie może ulec zmianie w kolejnych wersjach programu Power BI Desktop.

Aby włączyć filtrowanie krzyżowe dla zapytania bezpośredniego w programie Power BI Desktop, wybierz pozycję **Plik > Opcje i ustawienia > Opcje**, a następnie zaznacz pole wyboru obok pozycji **Włącz filtrowanie krzyżowe w obu kierunkach dla zapytania bezpośredniego**, jak pokazano na poniższej ilustracji.

![](media/desktop-bidirectional-filtering/bidirectional-filtering_1.png)

> [!NOTE]
> Podczas tworzenia formuł języka DAX filtrowania krzyżowego w programie Power BI Desktop, użyj atrybutu *UserPrincipalName* (który często jest taki sam, jak identyfikator logowania użytkownika, np. *joe@contoso.com*) zamiast atrybutu *UserName*. W takim przypadku może być konieczne utworzenie powiązanej tabeli, która mapuje element *UserName* (lub na przykład element EmployeeID) na element *UserPrincipleName*.
> 
> 

Aby włączyć filtrowanie krzyżowe, w oknie dialogowym **Edytowanie relacji** dla danej relacji należy wybrać następujące opcje:

* Opcja **Kierunek filtrowania krzyżowego** musi być ustawiona na wartość **Obydwa**
* Opcja **Zastosuj filtr zabezpieczeń w obu kierunkach** także musi być zaznaczona
  
  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

Aby uzyskać więcej informacji i zapoznać się z przykładami działania dwukierunkowego filtrowania krzyżowego, zobacz [oficjalny dokument](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) wymieniony wcześniej w tym artykule.

