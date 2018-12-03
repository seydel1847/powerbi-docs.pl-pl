---
title: Dwukierunkowe filtrowanie krzyżowe w programie Power BI Desktop
description: Włączanie filtrowania krzyżowego za pomocą zapytania bezpośredniego w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 58fbef3f8622121100ce77ae69d6c17cbeb46510
ms.sourcegitcommit: 05303d3e0454f5627eccaa25721b2e0bad2cc781
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/28/2018
ms.locfileid: "52578318"
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop"></a>Dwukierunkowe filtrowanie krzyżowe przy użyciu zapytania bezpośredniego w programie Power BI Desktop

Podczas filtrowania tabel w celu uzyskania odpowiedniego widoku danych twórcy raportów (i osoby modelujące dane) stają przed wyzwaniem ustalenia, jak filtrowanie jest stosowane do raportu. Kontekst filtru tabeli został ustalony po jednej stronie relacji, ale nie po drugiej, co często wymaga zastosowania złożonych formuł języka DAX w celu uzyskania żądanych wyników.

Dzięki dwukierunkowemu filtrowaniu krzyżowemu twórcy raportów (i osoby modelujące dane) mają większą kontrolę nad sposobem stosowania filtrów podczas pracy z powiązanymi tabelami, umożliwiając zastosowanie tych filtrów po *obu* stronach relacji tabeli. Jest to osiągane przez propagowanie kontekstu filtru do drugiej powiązanej tabeli po drugiej stronie relacji tabeli.

Dostępny jest [szczegółowy oficjalny dokument](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) objaśniający dwukierunkowe filtrowanie krzyżowe w programie Power BI Desktop (ten oficjalny dokument obejmuje również usługi SQL Server Analysis Services 2016, ponieważ zachowują się one tak samo).

* Pobierz oficjalny dokument [Bidirectional cross-filtering for Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) (Dwukierunkowe filtrowanie krzyżowe dla programu Power BI Desktop)

### <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>Włączanie dwukierunkowego filtrowania krzyżowego dla zapytania bezpośredniego

Aby włączyć filtrowanie krzyżowe, w oknie dialogowym **Edytowanie relacji** dla danej relacji należy wybrać następujące opcje:

* Opcja **Kierunek filtrowania krzyżowego** musi być ustawiona na wartość **Obydwa**
* Opcja **Zastosuj filtr zabezpieczeń w obu kierunkach** także musi być zaznaczona

  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

> [!NOTE]
> Podczas tworzenia formuł języka DAX filtrowania krzyżowego w programie Power BI Desktop, użyj atrybutu *UserPrincipalName* (który często jest taki sam, jak identyfikator logowania użytkownika, np. <em>joe@contoso.com</em>) zamiast atrybutu *UserName*. W takim przypadku może być konieczne utworzenie powiązanej tabeli, która mapuje element *UserName* (lub na przykład element EmployeeID) na element *UserPrincipalName*.

Aby uzyskać więcej informacji i zapoznać się z przykładami działania dwukierunkowego filtrowania krzyżowego, zobacz [oficjalny dokument](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) wymieniony wcześniej w tym artykule.

