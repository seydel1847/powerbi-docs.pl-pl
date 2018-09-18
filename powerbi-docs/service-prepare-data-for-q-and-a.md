---
title: Jak zapewnić poprawne współdziałanie danych programu Excel z funkcją Pytania i odpowiedzi w usłudze Power BI
description: Jak zapewnić poprawne współdziałanie danych z funkcją Pytania i odpowiedzi w usłudze Power BI
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: efc806787f2a1d5cd110439c1c5505bb7e77e980
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44727472"
---
# <a name="how-to-make-your-excel-data-work-well-with-qa-in-power-bi"></a>Jak zapewnić poprawne współdziałanie danych programu Excel z funkcją Pytania i odpowiedzi w usłudze Power BI
Jeśli jesteś osobą, która tworzy modele danych lub skoroszyty programu Excel, które będą używane z usługą Power BI, czytaj dalej...

W usłudze Power BI funkcja pytań i odpowiedzi może wyszukiwać strukturalne dane i wybierać odpowiednią wizualizację dla danego zapytania — dzięki temu jest tak atrakcyjnym narzędziem.   

Funkcja pytań i odpowiedzi może pracować na dowolnym przekazanym pliku programu Excel, który zawiera tabele, zakresy lub model PowerPivot, ale im więcej optymalizacji i sposobów czyszczenia danych zastosujesz, tym bardziej niezawodna będzie ta funkcja.  Jeśli planujesz udostępniać raporty i pulpity nawigacyjne oparte na Twoim zestawie danych, najlepiej zapewnić współpracownikom możliwość łatwego zadawania pytań i uzyskiwania użytecznych odpowiedzi.

### <a name="how-qa-works-with-excel"></a>Jak funkcja Pytania i odpowiedzi współdziała z programem Excel
Funkcja pytań i odpowiedzi zawiera zestaw możliwości podstawowego rozumienia języka, który działa wobec obsługiwanych danych. Zawiera również funkcję kontekstowego wyszukiwania słów kluczowych dla tabel programu Excel, kolumn i obliczeniowych nazw pól. Ponadto zawiera wbudowaną wiedzę dotyczącą sposobu filtrowania, sortowania, agregowania, grupowania i wyświetlania danych. 

Na przykład w tabeli programu Excel o nazwie „Sales” z kolumnami „Product”, „Month”, „Units Sold”, „Gross Sales” oraz „Profit” możesz zadawać pytania dotyczące dowolnej z tych jednostek.  Możesz zadać pytania „show sales”, „total profit by month”, „sort products by units sold” i wiele innych. Przeczytaj więcej o [rodzajach pytań, które możesz zadawać](power-bi-q-and-a.md) oraz [typach wizualizacji, które możesz określić w zapytaniu funkcji Pytania i odpowiedzi](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).

### <a name="prepare-an-excel-dataset-for-qa"></a>Przygotowywanie zestawu danych programu Excel na potrzeby funkcji Pytania i odpowiedzi
Funkcja pytań i odpowiedzi opiera się na nazwach tabel, kolumn i obliczanych pól, aby odpowiadać na pytania dotyczące danych. Oznacza to, że nazwy nadawane jednostkom w skoroszycie są ważne!

Poniżej przedstawiono kilka wskazówek umożliwiających wydajne użytkowanie funkcji pytań i odpowiedzi w skoroszycie.

* Upewnij się, że dane mają formę tabeli programu Excel. Oto [sposób tworzenia tabeli programu Excel](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US).
* Upewnij się, że nazwy tabel, kolumn i obliczanych pól mają sens w języku naturalnym.
  
  Jeśli na przykład masz tabelę z danymi dotyczącymi sprzedaży, nazwij ją „Sales”. Nazwy kolumn typu „Year”, „Product”, „Sales Rep” oraz „Amount” będą dobrze współpracować z funkcją pytań i odpowiedzi.

* Jeśli skoroszyt zawiera model danych Power Pivot, możesz zapewnić jeszcze więcej optymalizacji. Przeczytaj wpis [Demystifying Power BI Q&A part 2](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx) (Zrozumieć funkcję pytań i odpowiedzi usługi Power BI — część 2) od naszego wewnętrznego zespołu ekspertów ds. języka naturalnego.

* Otwórz zestaw danych w programie Power BI Desktop i twórz nowe kolumny, twórz miary obliczeniowe, łącz pola w celu tworzenia unikatowych wartości, klasyfikuj dane według typu (np. daty, ciągi, dane geograficzne, obrazy, adresy URL) i wykonuj inne działania.

## <a name="next-steps"></a>Następne kroki
Powrót do [pytań i odpowiedzi w usłudze Power BI](power-bi-q-and-a.md)  
[Przygotowywanie lokalnych zestawów danych pod kątem funkcji Pytania i odpowiedzi](service-q-and-a-direct-query.md)   
[Pytania i odpowiedzi — szybki start](power-bi-visualization-introduction-to-q-and-a.md)  
[Pobieranie danych (dla usługi Power BI)](service-get-data.md)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

