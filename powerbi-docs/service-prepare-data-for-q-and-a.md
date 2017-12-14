---
title: "Dbanie o poprawne współdziałanie danych z funkcją pytań i odpowiedzi w usłudze Power BI"
description: "Dbanie o poprawne współdziałanie danych z funkcją pytań i odpowiedzi w usłudze Power BI"
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
ms.openlocfilehash: 499c3beca9046af9336de6dfec96994004050986
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="make-your-data-work-well-with-qa-in-power-bi"></a>Dbanie o poprawne współdziałanie danych z funkcją pytań i odpowiedzi w usłudze Power BI
Jeśli jesteś osobą, która tworzy modele danych lub skoroszyty programu Excel, które będą używane z usługą Power BI, czytaj dalej...

W usłudze Power BI funkcja pytań i odpowiedzi może wyszukiwać strukturalne dane i wybierać odpowiednią wizualizację dla danego zapytania — dzięki temu jest tak atrakcyjnym narzędziem.   

Funkcja pytań i odpowiedzi może pracować na dowolnym przekazanym pliku programu Excel, który zawiera tabele, zakresy lub model PowerPivot, ale im więcej optymalizacji i sposobów czyszczenia danych zastosujesz, tym bardziej niezawodna będzie ta funkcja. 

## <a name="how-qa-works"></a>Jak działa funkcja pytań i odpowiedzi
Funkcja pytań i odpowiedzi zawiera zestaw możliwości podstawowego rozumienia języka, który działa wobec obsługiwanych danych. Zawiera również funkcję kontekstowego wyszukiwania słów kluczowych dla tabel programu Excel, kolumn i obliczeniowych nazw pól. Ponadto zawiera wbudowaną wiedzę dotyczącą sposobu filtrowania, sortowania, agregowania, grupowania i wyświetlania danych. 

Na przykład w tabeli programu Excel o nazwie „Sales” z kolumnami „Product”, „Month”, „Units Sold”, „Gross Sales” oraz „Profit” możesz zadawać pytania dotyczące dowolnej z tych jednostek.  Możesz zadać pytania „show sales”, „total profit by month”, „sort products by units sold” i wiele innych. Przeczytaj więcej o [rodzajach pytań, które możesz zadawać](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-1.aspx), [zadawaniu pytań przy użyciu szablonu pytań](service-q-and-a.md) oraz [typach wizualizacji, które możesz określić w zapytaniu funkcji pytań i odpowiedzi](power-bi-visualization-types-for-reports-and-q-and-a.md).

## <a name="prepare-a-workbook-for-qa"></a>Przygotowanie skoroszytu dla funkcji pytań i odpowiedzi
Funkcja pytań i odpowiedzi opiera się na nazwach tabel, kolumn i obliczanych pól, aby odpowiadać na pytania dotyczące danych. Oznacza to, że nazwy nadawane jednostkom w skoroszycie są ważne!

Poniżej przedstawiono kilka wskazówek umożliwiających wydajne użytkowanie funkcji pytań i odpowiedzi w skoroszycie.

* Upewnij się, że dane mają formę tabeli programu Excel. Oto [sposób tworzenia tabeli programu Excel](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US).
* Upewnij się, że nazwy tabel, kolumn i obliczanych pól mają sens w języku angielskim.
  
  Jeśli na przykład masz tabelę z danymi dotyczącymi sprzedaży, nazwij ją „Sales”. Nazwy kolumn typu „Year”, „Product”, „Sales Rep” oraz „Amount” będą dobrze współpracować z funkcją pytań i odpowiedzi.

> [!NOTE]
> Jeśli skoroszyt zawiera model danych Power Pivot, możesz zapewnić jeszcze więcej optymalizacji. Przeczytaj wpis [Demystifying Power BI Q&A part 2](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx) (Zrozumieć funkcję pytań i odpowiedzi usługi Power BI — część 2) od naszego wewnętrznego zespołu ekspertów ds. języka naturalnego.
> 
> 

## <a name="next-steps"></a>Następne kroki
[Pytania i odpowiedzi w usłudze Power BI](service-q-and-a.md)  
[Samouczek: wprowadzenie do funkcji pytań i odpowiedzi w usłudze Power BI](power-bi-visualization-introduction-to-q-and-a.md)  
[Pobieranie danych (dla usługi Power BI)](service-get-data.md)  
[Power BI — podstawowe pojęcia](service-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

