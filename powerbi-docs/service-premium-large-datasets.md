---
title: Obsługa dużych zestawów danych w usłudze Power BI Premium
description: Usługa Power BI Premium obsługuje teraz zestawy danych o rozmiarze do 10 GB.
services: powerbi
documentationcenter: ''
author: jocaplan
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/27/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: 1c617624d93dfa6c4193c77d36b6f6cec2992a03
ms.sourcegitcommit: 312390f18b99de1123bf7a7674c6dffa8088529f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Obsługa dużych zestawów danych w usłudze Power BI Premium

Usługa Power BI Premium obsługuje przekazywanie plików programu Power BI Desktop (pbix) o rozmiarze do 10 GB. Po przekazaniu plików zestaw danych można odświeżyć maksymalnie do 12 GB. Aby użyć dużego zestawu danych, opublikuj go w obszarze roboczym przypisanym do pojemności Premium.
 
## <a name="best-practices"></a>Najlepsze rozwiązania

W tej sekcji opisano najlepsze rozwiązania dotyczące pracy z dużymi zestawami danych.

**Duże modele mogą wymagać wielu zasobów** pojemności. W przypadku modeli większych niż 1 GB zalecamy co najmniej jednostkę SKU P1. W poniższej tabeli opisano zalecane jednostki SKU dla różnych rozmiarów plików pbix:


   |Jednostka SKU  |Rozmiar pliku pbix   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3    | do 10 GB   |



**Pliki pbix zawierają dane w wysoce skompresowanym stanie**. Te dane prawdopodobnie kilkukrotnie zwiększą swoją objętość po załadowaniu ich do pamięci, a następnie mogą jeszcze bardziej zwiększyć swoją objętość podczas odświeżania danych.

**Zaplanowane odświeżanie dużych zestawów danych może długo trwać** i wymagać wielu zasobów. W związku z tym nie należy planować zbyt wielu jednoczesnych odświeżeń. Zwróć uwagę, że limit czasu dla zadań zaplanowanego odświeżania został podwojony do czterech godzin dla wszystkich zestawów danych w tej pojemności.

**Początkowe ładowanie raportu dużych zestawów danych może długo trwać**, jeśli określony zestaw danych był używany dość dawno temu, ponieważ model jest ładowany do pamięci pojemności Premium. W przypadku dłużej ładowanych raportów postęp ładowania jest widoczny na pasku ładowania.

**Jeśli usuniesz obszar roboczy z pojemności Premium**, dany model i wszystkie powiązane raporty oraz pulpity nawigacyjne nie będą działać.

**Mimo że w pojemności Premium ograniczenia pamięci i czasu dla zapytania są o wiele wyższe**, zdecydowanie zalecamy zastosowanie filtrów i fragmentatorów w celu wyświetlania w wizualizacjach tylko tego, co jest niezbędne.

## <a name="next-steps"></a>Następne kroki
[Power BI Premium — co to jest?](service-premium.md)  
[Informacje o wersji usługi Power BI Premium](service-premium-release-notes.md)  
[Oficjalny dokument firmy Microsoft na temat usługi Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[Oficjalny dokument dotyczący planowania wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy)  
[Aktywacja rozszerzonej wersji próbnej Pro](service-extended-pro-trial.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)
