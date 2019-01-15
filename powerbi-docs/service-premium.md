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
ms.date: 10/21/2018
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 1749fc932b3aa6cfb86de87bc9ecd71f78d92af5
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54281970"
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

W poniższej tabeli przedstawiono podsumowanie różnic między pojemnością udostępnioną oraz pojemnością Premium.

|  | Pojemność udostępniona | Pojemność Power BI Premium |
| --- | --- | --- |
| **Częstotliwość odświeżania** |8/dzień |48/dzień |
| **Izolacja z dedykowanym sprzętem** |![Niedostępne](media/service-premium/not-available.png) |![Dostępne](media/service-premium/available.png) |
| **Dystrybucja na poziomie przedsiębiorstwa do** _**wszystkich użytkowników**_ | | |
| Aplikacje i udostępnianie |![Niedostępne](media/service-premium/not-available.png) |![Dostępne](media/service-premium/available.png) |
| Osadzone interfejsy API i kontrolki |![Niedostępne](media/service-premium/not-available.png) |![Niedostępne](media/service-premium/available.png)<sup>2</sup> |
| **Publikowanie raportów usługi Power BI lokalnie** |![Niedostępne](media/service-premium/not-available.png) |![Dostępne](media/service-premium/available.png) |
| | | |

*<sup>1</sup> Aby uzyskać więcej informacji, zobacz [Power BI features by license type](service-features-license-type.md) (Funkcje usługi Power BI według typu licencji).*  
*<sup>2</sup> Przyszłe ulepszenia w usłudze Power BI Premium.*

Aby dowiedzieć się więcej na temat przypisywania obszarów roboczych do pojemności Premium, zobacz [Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md).

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Węzły pojemności Premium

Usługa Power BI Premium jest dostępna z konfiguracjami węzłów z różnymi pojemnościami rdzeni wirtualnych. Aby uzyskać więcej informacji na temat określonych ofert i kosztów jednostek SKU, zobacz [Cennik usługi Power BI](https://powerbi.microsoft.com/pricing/). Dostępny jest również [kalkulator kosztów](https://powerbi.microsoft.com/calculator/). Aby uzyskać informacje na temat planowania pojemności dla osadzonych funkcji analitycznych, zobacz [Oficjalny dokument dotyczący planowania wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy). Podsumowując:

* Węzły P mogą być używane do wdrożeń osadzonych lub usługi.

* Węzły EM mogą być używane wyłącznie do wdrożeń osadzonych. Węzły EM nie mają dostępu do możliwości premium, takich jak udostępnianie aplikacji użytkownikom, którzy nie mają licencji usługi Power BI Pro.

>[!NOTE]
>Linki w tej tabeli działają prawidłowo wyłącznie dla użytkowników, którzy są administratorami globalnymi usługi Office 365. Inni zobaczą błąd 404.

| Węzeł pojemności | Całkowita liczba rdzeni wirtualnych<br/>*(Wewnętrzna baza danych + fronton)* | Rdzenie wirtualne zaplecza | Rdzenie wirtualne frontonu | Limity zapytania bezpośredniego/połączenia na żywo | Dostępność |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (z miesiąca na miesiąc)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 rdzeń wirtualny |0,5 rdzenia wirtualnego, 2,5 GB pamięci RAM |0,5 rdzenia wirtualnego |3,75 na sekundę |Dostępne |
| [EM2 (z miesiąca na miesiąc)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 rdzenie wirtualne |1 rdzeń wirtualny, 5 GB pamięci RAM |1 rdzeń wirtualny |7,5 na sekundę |Dostępne |
| [EM3 (z miesiąca na miesiąc)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 rdzenie wirtualne |2 rdzenie wirtualne, 10 GB pamięci RAM |2 rdzenie wirtualne | |Dostępne |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 rdzeni wirtualnych |4 rdzenie wirtualne, 25 GB pamięci RAM |4 rdzenie wirtualne |30 na sekundę |Dostępne (opcja [z miesiąca na miesiąc](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1) jest również dostępna) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 rdzeni wirtualnych |8 rdzeni wirtualnych, 50 GB pamięci RAM |8 rdzeni wirtualnych |60 na sekundę |Dostępne |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 rdzenie wirtualne |16 rdzeni wirtualnych, 100 GB pamięci RAM |16 rdzeni wirtualnych |120 na sekundę |Dostępne |
| | | | | | | |

* Rdzenie wirtualne frontonu odpowiadają za zarządzanie usługami internetowymi, pulpitami nawigacyjnymi i dokumentami raportów, zarządzanie uprawnieniami dostępu, planowanie, interfejsy API, przekazywanie i pobieranie oraz ogólnie za wszystkie elementy związane ze środowiskiem użytkownika.

* Rdzenie wirtualne zaplecza odpowiadają za ciężkie obciążenia: przetwarzanie zapytań, zarządzanie pamięcią podręczną, uruchamianie serwerów języka R, odświeżanie danych, przetwarzanie języka naturalnego, źródła danych w czasie rzeczywistym oraz renderowanie raportów i obrazów po stronie serwera. Ponadto w przypadku rdzeni wirtualnych zaplecza zarezerwowana jest pewna ilość pamięci. Dostępność wystarczającej pamięci staje się szczególnie ważna w przypadku obsługi dużych modeli danych lub dużej liczby aktywnych zestawów danych.

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

Jeśli używasz obciążenia raportów podzielonych na strony, weź pod uwagę następujące zagadnienia.

* **Alokacja pamięci w raportach podzielonych na strony**: raporty podzielone na strony umożliwiają uruchamianie własnego kodu podczas renderowania raportu (na przykład w przypadku dynamicznego zmieniania koloru tekstu na podstawie zawartości). Biorąc pod uwagę ten fakt, zabezpieczamy pojemność usługi Power BI Premium, uruchamiając raporty podzielone na strony w obszarze zawartym w pojemności. Przypisujemy wybraną maksymalną ilość pamięci do tego obszaru, bez względu na to, czy obciążenie jest aktywne. Jeśli używasz przepływów danych lub raportów usługi Power BI w ramach tej samej pojemności, upewnij się, że ustawiany poziom pamięci jest wystarczająco niski i nie wpływa negatywnie na inne obciążenia.

* **Raporty podzielone na strony są niedostępne**: w rzadkich przypadkach raporty podzielone na strony mogą stać się niedostępne. W takiej sytuacji obciążenie pokazuje stan błędu w portalu administracyjnym, a użytkownicy widzą przekroczenia limitu czasu renderowania raportu. Aby rozwiązać ten problem, wyłącz obciążenie, a następnie włącz je ponownie.

## <a name="power-bi-report-server"></a>serwerze raportów usługi Power BI

Usługa Power BI Premium obejmuje także możliwość lokalnego uruchomienia serwera raportów usługi Power BI w organizacji. Aby dowiedzieć się więcej, zobacz [Wprowadzenie do serwera raportów usługi Power BI](report-server/get-started.md).

## <a name="next-steps"></a>Następne kroki

[Power BI Premium — Często zadawane pytania](service-premium-faq.md)
[Jak kupić usługę Power BI Premium](service-admin-premium-purchase.md)
[Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md)
[Oficjalny dokument dotyczący usługi Microsoft Power BI](https://aka.ms/pbipremiumwhitepaper)
[Oficjalny dokument dotyczący planowania wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy)
[Administrowanie usługą Power BI w organizacji](service-admin-administering-power-bi-in-your-organization.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)
