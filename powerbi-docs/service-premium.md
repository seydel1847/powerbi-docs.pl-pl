---
title: Czym jest usługa Microsoft Power BI Premium?
description: Usługa Power BI Premium została opracowana z myślą o pojemności dla organizacji lub zespołu, aby zapewniać jeszcze bardziej niezawodną wydajność i większe woluminy danych — bez potrzeby kupowania licencji użytkowników.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/15/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 6cc26f386a77ad8482d7f1af69fd0fdf2b7de5ac
ms.sourcegitcommit: a20825ebd0ef4c2cb77232e3dd0e9f8260cacf71
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2019
ms.locfileid: "54324025"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Czym jest usługa Microsoft Power BI Premium?

Usługa Microsoft Power BI Premium zapewnia zasoby dedykowane do uruchamiania usługi Power BI dla organizacji. Zapewnia ona bardziej niezawodną wydajność i umożliwia przetwarzanie większych ilości danych. Ponadto usługa Premium umożliwia szeroką dystrybucję zawartości bez potrzeby zakupu licencji usługi Pro dla użytkowników zawartości. Aby uzyskać informacje o opcjach zakupu, zobacz [Jak kupić usługę Power BI Premium](service-admin-premium-purchase.md).   

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="premium-capacity-and-shared-capacity"></a>Pojemność Premium i pojemność udostępniona

Wykorzystaj usługę Power BI Premium, przydzielając obszary robocze do *pojemności Premium*. Pojemność Premium jest dedykowanym zasobem dla Twojej organizacji. Obszary robocze nieprzypisane do pojemności Premium znajdują się w *pojemności udostępnionej*. W przypadku pojemności udostępnionej obciążenia są uruchamiane na zasobach komputerowych udostępnianych przez innych klientów.

Na poniższej ilustracji przedstawiono relację między pojemnością Premium i pojemnością udostępnioną na przykładzie organizacji Contoso.

![Ilustracja przedstawiająca usługę Power BI Premium](media/service-premium/premium-chart.png)

| Warstwowy | Opis |
| --- | --- |
| **(1)** Elementy w ramach pojemności Premium | <ul><li>Uzyskiwanie dostępu do obszarów roboczych aplikacji (jako członkowie lub administratorzy) oraz publikowanie aplikacji wymaga licencji usługi Power BI Pro.<li>Udostępnianie aplikacji wymaga licencji Pro, ale korzystanie z aplikacji już nie.<li>Wszyscy odbiorcy pulpitu nawigacyjnego, niezależnie od przypisanej do nich licencji, mogą ustawiać alerty dotyczące danych.<li>Interfejsy API REST do osadzania używają konta usługi z licencją Pro, a nie konta użytkownika.</ul> |
| **(2)** Mój obszar roboczy w pojemności udostępnionej | <ul><li>Udostępnianie i używanie aplikacji wymaga licencji Pro.</ul> |
| **(3)** Obszary robocze aplikacji w pojemności udostępnionej | <ul><li>Każde użycie aplikacji wymaga licencji Pro.</ul>|
| | |

W pojemności udostępnionej usługa Power BI stosuje większe limity wobec poszczególnych użytkowników, aby zapewnić jakość środowiska dla wszystkich użytkowników. Domyślnie obszar roboczy, w tym osobisty obszar *Mój obszar roboczy* i obszar roboczy aplikacji.

Poniższa tabela zawiera podsumowanie różnic między pojemnością udostępnioną a pojemnością Premium:

|  | Pojemność udostępniona | Pojemność Power BI Premium |
| --- | --- | --- |
| **Częstotliwość odświeżania** |8/dzień |48/dzień |
| Izolacja dzięki specjalnemu sprzętowi |![Niedostępne](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| Dystrybucja do *wszystkich użytkowników* w przedsiębiorstwie | | |
| Aplikacje i udostępnianie |![Niedostępne](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| Osadzone interfejsy API i kontrolki |![Niedostępne](media/service-premium/not-available.png) |![](media/service-premium/available.png)<sup>[1](#fnt1)</sup> |
| Publikowanie raportów usługi Power BI lokalnie |![Niedostępne](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| | | |

<a name="fnt1">1</a> Przyszłe ulepszenia w usłudze Power BI Premium.



### <a name="premium-capacity-nodes"></a>Węzły pojemności Premium

Usługa Power BI Premium jest dostępna z konfiguracjami węzłów z różnymi pojemnościami rdzeni wirtualnych. Aby uzyskać więcej informacji na temat określonych ofert i kosztów jednostek SKU, zobacz [Cennik usługi Power BI](https://powerbi.microsoft.com/pricing/). Dostępny jest również [kalkulator kosztów](https://powerbi.microsoft.com/calculator/). Aby uzyskać informacje na temat planowania pojemności dla osadzonych funkcji analitycznych, zobacz [Oficjalny dokument dotyczący planowania wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy). Podsumowując:

* Węzły P mogą być używane do wdrożeń osadzonych lub usługi.

* Węzły EM mogą być używane wyłącznie do wdrożeń osadzonych. Węzły EM nie mają dostępu do możliwości premium, takich jak udostępnianie aplikacji użytkownikom, którzy nie mają licencji usługi Power BI Pro.

| Węzeł pojemności | Całkowita liczba rdzeni wirtualnych<br/>*(Wewnętrzna baza danych i fronton)*  | Rdzenie wirtualne wewnętrznej bazy danych <sup>[1](#fn1)</sup> | Rdzenie wirtualne frontonu <sup>[2](#fn2)</sup> | Limity zapytania bezpośredniego/połączenia na żywo | Maksymalna liczba jednoczesnych odświeżeń |  Dostępność
| --- | --- | --- | --- | --- | --- | --- | --- |
| EM1 (z miesiąca na miesiąc) |1 rdzeń wirtualny |0,5 rdzenia wirtualnego, 2,5 GB pamięci RAM |0,5 rdzenia wirtualnego |3,75 na sekundę |  1 | Dostępne |
| EM2 (z miesiąca na miesiąc) |2 rdzenie wirtualne |1 rdzeń wirtualny, 5 GB pamięci RAM |1 rdzeń wirtualny |7,5 na sekundę |  2 | Dostępne |
| EM3 (z miesiąca na miesiąc) |4 rdzenie wirtualne |2 rdzenie wirtualne, 10 GB pamięci RAM |2 rdzenie wirtualne | | 3 |  Dostępne |
| P1 |8 rdzeni wirtualnych |4 rdzenie wirtualne, 25 GB pamięci RAM |4 rdzenie wirtualne |30 na sekundę | 6 | Dostępne (opcja z miesiąca na miesiąc jest również dostępna) |
| P2 |16 rdzeni wirtualnych |8 rdzeni wirtualnych, 50 GB pamięci RAM |8 rdzeni wirtualnych |60 na sekundę | 12 | Dostępne |
| P3 |32 rdzenie wirtualne |16 rdzeni wirtualnych, 100 GB pamięci RAM |16 rdzeni wirtualnych |120 na sekundę | 24 | Dostępne |
| | | | | | | |

<a name="fn1">1</a>: Rdzenie wirtualne frontonu są odpowiedzialni za usługę sieci web. Na przykład pulpit nawigacyjny oraz zarządzanie dokumentami raportów, zarządzanie uprawnieniami dostępu, planowanie, interfejsy API, przekazywanie i pobieranie oraz ogólnie za wszystkie elementy związane ze środowiskiem użytkownika. 

<a name="fn2">2</a>: Rdzenie wirtualne zaplecza odpowiadają za ciężkie obciążenia: przetwarzanie zapytań, zarządzanie pamięcią podręczną, uruchamianie serwerów języka R, odświeżanie danych, przetwarzanie języka naturalnego, źródła danych w czasie rzeczywistym oraz renderowanie raportów i obrazów po stronie serwera. Ponadto w przypadku rdzeni wirtualnych zaplecza zarezerwowana jest pewna ilość pamięci. Dostępność wystarczającej pamięci staje się szczególnie ważna w przypadku obsługi dużych modeli danych lub dużej liczby aktywnych zestawów danych.

## <a name="workloads-in-premium-capacity"></a>Obciążenia w pojemności Premium

Obciążenia w usłudze Power BI można traktować jako jedną z wielu usług, które można udostępnić użytkownikom. Domyślnie pojemności usług **Power BI Premium** i **Power BI Embedded** obsługują tylko obciążenie skojarzone z uruchamianiem zapytań usługi Power BI w chmurze.

Oferujemy teraz obsługę wersji zapoznawczej dwóch dodatkowych obciążeń: **Raporty podzielone na strony** i **Przepływy danych**. Te obciążenia można włączyć w portalu administracyjnym usługi Power BI lub za pośrednictwem interfejsu API REST usługi Power BI. Można również ustawić maksymalną ilość pamięci, której może używać każde obciążenie, aby kontrolować wzajemny wpływ obciążeń. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie obciążeń](service-admin-premium-manage.md#configure-workloads).

### <a name="default-memory-settings"></a>Domyślne ustawienia pamięci

W poniższych tabelach przedstawiono domyślne i minimalne wartości pamięci w oparciu o różne dostępne [węzły pojemności](#premium-capacity-nodes). Pamięć jest przydzielana dynamicznie do przepływów danych, ale jest przydzielana statycznie do raportów podzielonych na strony. Aby uzyskać więcej informacji, zobacz następną sekcję: [Zagadnienia dotyczące raportów podzielonych na strony](#considerations-for-paginated-reports).

#### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Jednostki SKU pakietu Microsoft Office dla scenariuszy SaaS (software as a service)

|                     | EM3                      | P1                       | P2                      | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|
| Raporty z podziałem na strony | Nie dotyczy | Domyślna 20%; minimalna 10% | Domyślna 20%; minimalna 5% | Domyślna 20%; minimalna 2,5% |
| Przepływy danych | Domyślna 20%; minimalna 8%  | Domyślna 20%; minimalna 4%  | Domyślna 20%; minimalna 2% | Domyślna 20%; minimalna 1%  |
| | | | | |

#### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Jednostki SKU platformy Microsoft Azure dla scenariuszy PaaS (platform as a service)

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| Raporty z podziałem na strony | Nie dotyczy                      | NIE DOTYCZY                      | Nie dotyczy                     | Domyślna 20%; minimalna 10% | Domyślna 20%; minimalna 5% | Domyślna 20%; minimalna 2,5% |
| Przepływy danych         | Domyślna 27%; minimalna 27% | Domyślna 20%; minimalna 16% | Domyślna 20%; minimalna 8% | Domyślna 20%; minimalna 4%  | Domyślna 20%; minimalna 2% | Domyślna 20%; minimalna 1%   |

### <a name="considerations-for-paginated-reports"></a>Zagadnienia dotyczące raportów podzielonych na strony

Należy zwrócić uwag ę, że raporty podzielone na strony umożliwiają uruchamianie własnego kodu podczas renderowania raportu (na przykład w przypadku dynamicznego zmieniania koloru tekstu na podstawie zawartości). Biorąc pod uwagę ten fakt, zabezpieczamy pojemność usługi Power BI Premium, uruchamiając raporty podzielone na strony w obszarze zawartym w pojemności. Przypisujemy wybraną maksymalną ilość pamięci do tego obszaru, bez względu na to, czy obciążenie jest aktywne. Jeśli używasz przepływów danych lub raportów usługi Power BI w ramach tej samej pojemności, upewnij się, że ustawiany poziom pamięci jest wystarczająco niski i nie wpływa negatywnie na inne obciążenia.

w rzadkich przypadkach raporty podzielone na strony mogą stać się niedostępne. W takiej sytuacji obciążenie pokazuje stan błędu w portalu administracyjnym, a użytkownicy widzą przekroczenia limitu czasu renderowania raportu. Aby rozwiązać ten problem, wyłącz obciążenie, a następnie włącz je ponownie.

## <a name="power-bi-report-server"></a>serwerze raportów usługi Power BI

Usługa Power BI Premium obejmuje także możliwość lokalnego uruchomienia serwera raportów usługi Power BI w organizacji. Aby dowiedzieć się więcej, zobacz [Wprowadzenie do serwera raportów usługi Power BI](report-server/get-started.md).

## <a name="next-steps"></a>Następne kroki

[Power BI Premium — często zadawane pytania](service-premium-faq.md)
[Jak kupić usługę Power BI Premium](service-admin-premium-purchase.md)
[Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md)
[Oficjalny dokument dotyczący usługi Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)
[Oficjalny dokument dotyczący planowania wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)
