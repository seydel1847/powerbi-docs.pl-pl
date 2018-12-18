---
title: Wprowadzenie do pulpitów nawigacyjnych dla projektantów usługi Power BI
description: Pulpity nawigacyjne to kluczowy element usługi Power BI. Są to pojedyncze strony (często nazywane kanwą), które umożliwiają przekazywanie informacji za pomocą wizualizacji.
author: maggieMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/10/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 7a1187373304387ac511053d241e5cfb31f7fcd9
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2018
ms.locfileid: "53280586"
---
# <a name="intro-to-dashboards-for-power-bi-designers"></a>Wprowadzenie do pulpitów nawigacyjnych dla projektantów usługi Power BI

***Pulpit nawigacyjny*** usługi Power BI to pojedyncza strona, często nazywana kanwą, umożliwiająca przekazywanie informacji za pomocą wizualizacji. Ponieważ jest to tylko jedna strona, dobrze zaprojektowany pulpit nawigacyjny zawiera tylko najistotniejsze informacje. Czytelnicy mogą wyświetlać powiązane raporty, aby uzyskać szczegółowe informacje.

![pulpit nawigacyjny](media/service-dashboards/power-bi-dashboard2.png)

Pulpity nawigacyjne są funkcją usługi Power BI. Nie są one dostępne w programie Power BI Desktop. Nie można tworzyć pulpitów nawigacyjnych na urządzeniach przenośnych, ale można je na nich [wyświetlać i udostępniać](mobile-apps-view-dashboard.md).

## <a name="dashboard-basics"></a>Podstawowe informacje o pulpitach nawigacyjnych 

Wizualizacje widoczne na pulpicie nawigacyjnym to *kafelki*. Możesz *przypinać* kafelki z raportów do pulpitu nawigacyjnego. Jeśli jesteś nowym użytkownikiem usługi Power BI, zapoznaj się z podstawowymi informacjami w temacie [Power BI — podstawowe pojęcia](service-basic-concepts.md).

> [!IMPORTANT]
> Do tworzenia pulpitów nawigacyjnych jest wymagana licencja usługi [Power BI Pro](service-free-vs-pro.md).

Wizualizacje na pulpicie nawigacyjnym pochodzą z raportów, a każdy raport jest tworzony w oparciu o zestaw danych. Pulpit nawigacyjny można porównać do drzwi prowadzących do bazowych raportów i zestawów danych. Wybierając wizualizację, możesz przejść do raportu (i zestawu danych), który został użyty do jej utworzenia.

![diagram przedstawiający relację między pulpitami nawigacyjnymi, raportami, zestawami danych](media/service-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>Zalety pulpitów nawigacyjnych
Pulpity nawigacyjne to świetny sposób na monitorowanie sytuacji w firmie i błyskawiczne zapoznanie się ze wszystkimi najistotniejszymi metrykami. Wizualizacje na pulpicie nawigacyjnym mogą pochodzić z jednego bazowego zestawu danych lub raportu albo wielu zestawów danych lub raportów. Pulpit nawigacyjny łączy dane lokalne i przechowywane w chmurze, zapewniają skonsolidowany widok bez względu na to, gdzie znajdują się dane.

Pulpit nawigacyjny jest nie tylko atrakcyjny wizualnie. Jest wysoce interakcyjny, a jego kafelki są aktualizowane na bieżąco, odzwierciedlając zmiany w danych bazowych.

## <a name="dashboards-versus-reports"></a>Pulpity nawigacyjne a raporty
[Raporty](service-reports.md) i pulpity nawigacyjne wydają się podobne, ponieważ oba te elementy mają postać kanwy z wizualizacjami. Istnieją jednak podstawowe różnice.

| **Funkcja** | **Pulpity nawigacyjne** | **Raporty** |
| --- | --- | --- |
| Strony |Jedna strona |Jedna lub kilka stron |
| Źródła danych |Co najmniej jeden raport i co najmniej jeden zestaw danych na pulpit nawigacyjny |Jeden zestaw danych na raport |
| Dostępność w programie Power BI Desktop |Nie | Można tworzyć i wyświetlać raporty w programie Power BI Desktop |
| Subskrybuj |Można subskrybować pulpit nawigacyjny |Można subskrybować strony raportu |
| Filtrowanie |Nie można filtrować ani wycinać |Wiele różnych sposobów filtrowania, wyróżniania i wycinania |
| Polecane |Można ustawić jeden pulpit nawigacyjny jako „proponowany” |Nie można tworzyć proponowanych raportów |
| Dodaj do ulubionych | Można oznaczać pulpity nawigacyjne jako *ulubione* | Można ustawiać raporty jako *ulubione*
| Ustawianie alertów |Dostępne dla kafelków pulpitu nawigacyjnego w pewnych okolicznościach |Niedostępne z poziomu raportów |
| Zapytania w języku naturalnym (Pytania i odpowiedzi) |Dostępne na pulpitach nawigacyjnych | Dostępne w raportach |
| Wyświetlanie tabel i pól bazowego zestawu danych |Nie. Można eksportować dane, ale nie można wyświetlać tabel i pól na pulpicie nawigacyjnym. |Tak. Można wyświetlać tabele, pola i wartości zestawu danych. |


## <a name="next-steps"></a>Następne kroki
* Dobrze poznaj pulpity nawigacyjne, eksperymentując na jednym z naszych [przykładowych pulpitów nawigacyjnych](sample-tutorial-connect-to-the-samples.md).
* Uzyskaj informacje o [kafelkach pulpitu nawigacyjnego](service-dashboard-tiles.md).
* Chcesz śledzić wybrany kafelek pulpitu nawigacyjnego i otrzymać wiadomość e-mail po osiągnięciu przez niego określonego progu? [Utwórz alerty kafelków](service-set-data-alerts.md).
* Dowiedz się, jak używać funkcji [pytań i odpowiedzi w usłudze Power BI](power-bi-tutorial-q-and-a.md), aby zadawać pytania dotyczące danych i uzyskiwać odpowiedzi w formie wizualizacji.
