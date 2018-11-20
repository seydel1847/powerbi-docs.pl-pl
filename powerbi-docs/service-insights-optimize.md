---
title: Optymalizacja danych pod kątem szybkiego wglądu w szczegółowe dane usługi Power BI
description: Optymalizacja danych pod kątem szybkiego wglądu w szczegółowe dane usługi Power BI. Jeśli usługa Power BI nie znajduje szczegółowych informacji w Twoich danych, możesz zrobić kilka rzeczy, aby rozwiązać ten problem
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2017
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 33d8911ee819bbc1ac37976f077edabee368f5aa
ms.sourcegitcommit: a186679e8dae85dce23f6365bf5c36d7f407f15b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2018
ms.locfileid: "51850573"
---
# <a name="optimize-your-data-for-power-bi-quick-insights"></a>Optymalizacja danych pod kątem szybkiego wglądu w szczegółowe dane w usłudze Power BI
Czy chcesz poprawić wyniki szybkiego wglądu w szczegółowe dane?  Jeśli jesteś właścicielem zestawu danych, wypróbuj poniższe metody:

* Ukryj/odkryj kolumny w zestawie danych. Funkcja szybkiego wglądu w szczegółowe dane w usłudze Power BI nie wyszukuje ukrytych kolumn.  Ukryj zduplikowane lub niepotrzebne kolumny i odkryj kolumny zawierające interesujące dane.
* Użyj połączenia różnych typów danych, takich jak nazwy, godziny, daty i liczby.
* Unikaj kolumn ze zduplikowanymi informacjami (lub ukryj je).  Oszczędza to cenny czas poświęcany na wyszukiwanie znaczących wzorców.  Przykład zduplikowanych informacji: jedna kolumna zawiera pełne nazwy województw, a inna kolumna zawiera skróty nazw województw.
* Czy został wyświetlony komunikat o błędzie informujący, że dane nie są statystycznie istotne?  Może się to zdarzyć w przypadku modeli, które są bardzo proste, nie mają wielu danych albo nie mają kolumn dat ani kolumn liczbowych. Aby wygenerować szczegółowe informacje, zestaw danych musi mieć co najmniej jeden wymiar i jedną miarę.

### <a name="next-steps"></a>Następne kroki
[Szybki wgląd w szczegółowe dane w usłudze Power BI](consumer/end-user-insights.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

