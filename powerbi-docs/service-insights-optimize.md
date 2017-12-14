---
title: "Optymalizacja danych pod kątem szybkiego wglądu w szczegółowe dane w usłudze Power BI"
description: "Optymalizacja danych pod kątem szybkiego wglądu w szczegółowe dane w usłudze Power BI. Jeśli usługa Power BI nie znajduje szczegółowych informacji w Twoich danych, możesz zrobić kilka rzeczy, aby rozwiązać ten problem"
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
ms.date: 09/02/2017
ms.author: mihart
ms.openlocfilehash: 61901d0055c22540ec2f10bedbbb8cf641d606e9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="optimize-your-data-for-power-bi-quick-insights"></a>Optymalizacja danych pod kątem szybkiego wglądu w szczegółowe dane w usłudze Power BI
Czy chcesz poprawić wyniki szybkiego wglądu w szczegółowe dane?  Jeśli jesteś właścicielem zestawu danych, wypróbuj poniższe metody:

* Ukryj/odkryj kolumny w zestawie danych. Funkcja szybkiego wglądu w szczegółowe dane w usłudze Power BI nie wyszukuje ukrytych kolumn.  Ukryj zduplikowane lub niepotrzebne kolumny i odkryj kolumny zawierające interesujące dane.
* Użyj połączenia różnych typów danych, takich jak nazwy, godziny, daty i liczby.
* Unikaj kolumn ze zduplikowanymi informacjami (lub ukryj je).  Oszczędza to cenny czas poświęcany na wyszukiwanie znaczących wzorców.  Przykład zduplikowanych informacji: jedna kolumna zawiera pełne nazwy województw, a inna kolumna zawiera skróty nazw województw.
* Czy został wyświetlony komunikat o błędzie informujący, że dane nie są statystycznie istotne?  Może się to zdarzyć w przypadku modeli, które są bardzo proste, nie mają wielu danych albo nie mają kolumn dat ani kolumn liczbowych. Aby wygenerować szczegółowe informacje, zestaw danych musi mieć co najmniej jeden wymiar i jedną miarę.

### <a name="next-steps"></a>Następne kroki
[Szybki wgląd w szczegółowe dane w usłudze Power BI](service-insights.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

