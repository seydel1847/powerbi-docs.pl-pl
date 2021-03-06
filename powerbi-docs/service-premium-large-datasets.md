---
title: Obsługa dużych zestawów danych w usłudze Power BI Premium
description: Usługa Power BI Premium obsługuje teraz zestawy danych o rozmiarze do 10 GB.
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: 3aa8ef5ea7a51da226d48869bdf255900dee8d6d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284201"
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Obsługa dużych zestawów danych w usłudze Power BI Premium

Usługa Power BI Premium obsługuje przekazywanie plików programu Power BI Desktop (pbix) o rozmiarze do 10 GB. Po przekazaniu plików zestaw danych można odświeżyć maksymalnie do 12 GB. Aby użyć dużego zestawu danych, opublikuj go w obszarze roboczym przypisanym do pojemności Premium.
 
## <a name="best-practices"></a>Najlepsze rozwiązania

W tej sekcji opisano najlepsze rozwiązania dotyczące pracy z dużymi zestawami danych.

**Duże modele mogą używać bardzo dużej ilości zasobów** w ramach pojemności. W przypadku wszystkich modeli większych niż 1 GB zalecamy użycie co najmniej jednostki SKU P1. Chociaż publikowanie dużych modeli w obszarach roboczych obsługiwanych przez jednostki SKU A do jednostki A3 może zakończyć się powodzeniem, to ich odświeżenie zakończy się niepowodzeniem.

W poniższej tabeli opisano zalecane jednostki SKU dla różnych rozmiarów plików pbix:

   |Jednostka SKU  |Rozmiar pliku pbix   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3, P4, P5    | do 10 GB   |

Jednostka SKU A4 usługi Power BI Embedded jest odpowiednikiem jednostki SKU P1, jednostka A5 jest odpowiednikiem P2, a jednostka A6 — jednostki P3. Pamiętaj, że publikowanie dużych modeli w jednostkach SKU A i EM może spowodować zwrócenie błędów, które nie wiążą się bezpośrednio z ograniczeniem rozmiaru modelu w pojemności udostępnionej. Błędy odświeżania w przypadku dużych modeli w jednostkach SKU A i EM prawdopodobnie będą wskazywać przekroczenia limitu czasu. Pracujemy nad ulepszaniem komunikatów o błędach dla tych scenariuszy.

**Pliki pbix zawierają dane w wysoce skompresowanym stanie**. Te dane prawdopodobnie kilkukrotnie zwiększą swoją objętość po załadowaniu ich do pamięci, a następnie mogą jeszcze bardziej zwiększyć swoją objętość podczas odświeżania danych.

**Zaplanowane odświeżanie dużych zestawów danych może długo trwać** i wymagać wielu zasobów. W związku z tym nie należy planować zbyt wielu jednoczesnych odświeżeń. Zwróć uwagę, że limit czasu dla zadań zaplanowanego odświeżania został podwojony do czterech godzin dla wszystkich zestawów danych w tej pojemności. Zalecamy [odświeżanie przyrostowe](service-premium-incremental-refresh.md), ponieważ jest szybsze, bardziej niezawodne i zużywa mniej zasobów.

**Początkowe ładowanie raportu dużych zestawów danych może długo trwać**, jeśli określony zestaw danych był używany dość dawno temu, ponieważ model jest ładowany do pamięci pojemności Premium. W przypadku dłużej ładowanych raportów postęp ładowania jest widoczny na pasku ładowania.

**Jeśli usuniesz obszar roboczy z pojemności Premium**, dany model i wszystkie powiązane raporty oraz pulpity nawigacyjne nie będą działać.

**Mimo że w pojemności Premium ograniczenia pamięci i czasu dla zapytania są o wiele wyższe**, zdecydowanie zalecamy zastosowanie filtrów i fragmentatorów w celu wyświetlania w wizualizacjach tylko tego, co jest niezbędne.

**Następne kroki**

[Co to jest usługa Power BI Premium?](service-premium.md)
[Informacje o wersji usługi Power BI Premium](service-premium-release-notes.md)
[Oficjalny dokument dotyczący usługi Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)
[Oficjalny dokument dotyczący planowania wdrażania usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)
