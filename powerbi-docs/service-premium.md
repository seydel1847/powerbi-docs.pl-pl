---
title: Czym jest usługa Microsoft Power BI Premium?
description: Usługa Power BI Premium została opracowana z myślą o pojemności dla organizacji lub zespołu, aby zapewniać jeszcze bardziej niezawodną wydajność i większe woluminy danych — bez potrzeby kupowania licencji użytkowników.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 09/11/2018
LocalizationGroup: Premium
ms.openlocfilehash: 0723ddb57131fed499d4ac86666b3cd6d8bcbd2d
ms.sourcegitcommit: 833cf1252807721fb1b3000487bd032bfd6c8c98
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/04/2018
ms.locfileid: "48271813"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Czym jest usługa Microsoft Power BI Premium?

Usługa Microsoft Power BI Premium zapewnia zasoby dedykowane do uruchamiania usługi Power BI dla organizacji lub zespołu. Zapewnia ona bardziej niezawodną wydajność i umożliwia przetwarzanie większych ilości danych. Ponadto usługa Premium umożliwia szeroką dystrybucję zawartości bez potrzeby zakupu licencji usługi Pro dla użytkowników, którzy mają ją wyświetlać.

Możesz wykorzystać usługę Power BI Premium, przydzielając obszary robocze do *pojemności Premium*. Pojemność Premium jest dedykowanym zasobem dla Twojej organizacji. Obszary robocze nieprzypisane do pojemności Premium znajdują się w *pojemności udostępnionej*. W przypadku pojemności udostępnionej obciążenia są uruchamiane na zasobach komputerowych udostępnianych przez innych klientów. 

W pojemności udostępnionej usługa Power BI stosuje większe limity wobec poszczególnych użytkowników, aby zapewnić jakość środowiska dla wszystkich użytkowników. Domyślnie obszar roboczy, w tym osobisty obszar *Mój obszar roboczy* i obszar roboczy aplikacji.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>Warstwy pojemności

Poniżej przedstawiono podsumowanie różnic między pojemnością udostępnioną oraz pojemnością Premium.

|  | Pojemność udostępniona | Pojemność Power BI Premium |
| --- | --- | --- |
| **Częstotliwość odświeżania** |8/dzień |48/dzień |
| **Izolacja z dedykowanym sprzętem** |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne") |
| **Dystrybucja na poziomie przedsiębiorstwa do** ***wszystkich użytkowników*** | | |
| Aplikacje i udostępnianie |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne")<sup>1</sup> |
| Osadzone interfejsy API i kontrolki |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne")<sup>2</sup> |
| **Publikowanie raportów usługi Power BI lokalnie** |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne") |

*<sup>1</sup> Aby uzyskać więcej informacji, zobacz [Power BI features by license type](service-features-license-type.md) (Funkcje usługi Power BI według typu licencji).*  
*<sup>2</sup> Przyszłe ulepszenia w usłudze Power BI Premium.*

Aby rozpocząć używanie pojemności Power BI Premium, przypisz obszar roboczy do pojemności. Gdy pojemność Premium obsługuje obszar roboczy, otrzymujesz następujące korzyści:

* **Zaplanowane odświeżanie**: w przypadku pojemności udostępnionej zaplanowane operacje odświeżania zestawów danych importowanych modeli są ograniczone do ośmiu razy dziennie. W przypadku zestawów danych w obszarach roboczych Premium można zaplanować odświeżanie maksymalnie 48 razy dziennie. Operacje odświeżania pamięci podręcznej trybu DirectQuery są nadal ograniczone do ośmiu razy dziennie w pojemności Premium.

* **Izolacja z dedykowanym sprzętem**: w przypadku pojemności udostępnionej zapotrzebowanie na zasoby innych obciążeń może mieć wpływ na wydajność raportów i pulpitów nawigacyjnych. Natomiast pojemność Premium zapewnia bardziej spójną, niezawodną wydajność dla obciążeń przez izolowanie ich od innych niepowiązanych obciążeń.

Jeśli aplikacja jest wspierana przez pojemność Premium (tj. została opublikowana z obszaru roboczego aplikacji obecnie przypisanego do warstwy Premium), opublikowana aplikacja może być używana przez dowolnego użytkownika w organizacji niezależnie od przypisanej do niego licencji.

Aby dowiedzieć się więcej na temat przypisywania obszarów roboczych do pojemności Premium, zobacz [Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md).

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Węzły pojemności Premium

Usługa Power BI Premium jest dostępna z konfiguracjami węzłów z różnymi pojemnościami rdzeni wirtualnych. Aby uzyskać więcej informacji na temat określonych ofert i kosztów jednostek SKU, zobacz [Cennik usługi Power BI](https://powerbi.microsoft.com/pricing/). Dostępny jest również [kalkulator kosztów](https://powerbi.microsoft.com/calculator/). Aby uzyskać informacje na temat planowania pojemności dla osadzonych funkcji analitycznych, zobacz [Oficjalny dokument dotyczący planowania wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy).

* Węzły P mogą być używane do wdrożeń osadzonych lub usługi.

* Węzły EM mogą być używane wyłącznie do wdrożeń osadzonych. Węzły EM nie mają dostępu do możliwości premium, takich jak udostępnianie aplikacji użytkownikom, którzy nie mają licencji usługi Power BI Pro.

>[!NOTE]
>Linki w tej tabeli działają prawidłowo wyłącznie dla użytkowników, którzy są administratorami globalnymi usługi Office 365. Inni zobaczą błąd 404.

| Węzeł pojemności | Całkowita liczba rdzeni wirtualnych<br/>*(Wewnętrzna baza danych + fronton)* | Rdzenie wirtualne zaplecza | Rdzenie wirtualne frontonu | Limity zapytania bezpośredniego/połączenia na żywo | Maksymalne renderowanie strony w godzinie szczytu | Dostępność |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (z miesiąca na miesiąc)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 rdzeń wirtualny |0,5 rdzenia wirtualnego, 2,5 GB pamięci RAM |0,5 rdzenia wirtualnego |3,75 na sekundę |150–300 |Dostępne |
| [EM2 (z miesiąca na miesiąc)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 rdzenie wirtualne |1 rdzeń wirtualny, 5 GB pamięci RAM |1 rdzeń wirtualny |7,5 na sekundę |301–600 |Dostępne |
| [EM3 (z miesiąca na miesiąc)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 rdzenie wirtualne |2 rdzenie wirtualne, 10 GB pamięci RAM |2 rdzenie wirtualne | |601–1200 |Dostępne |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 rdzeni wirtualnych |4 rdzenie wirtualne, 25 GB pamięci RAM |4 rdzenie wirtualne |30 na sekundę |1,201-2,400 |Dostępne (opcja [z miesiąca na miesiąc](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1) jest również dostępna) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 rdzeni wirtualnych |8 rdzeni wirtualnych, 50 GB pamięci RAM |8 rdzeni wirtualnych |60 na sekundę |2,401-4,800 |Dostępne |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 rdzenie wirtualne |16 rdzeni wirtualnych, 100 GB pamięci RAM |16 rdzeni wirtualnych |120 na sekundę |4,801-9600 |Dostępne |

* Rdzenie wirtualne frontonu odpowiadają za zarządzanie usługami internetowymi, pulpitami nawigacyjnymi i dokumentami raportów, zarządzanie uprawnieniami dostępu, planowanie, interfejsy API, przekazywanie i pobieranie oraz ogólnie za wszystkie elementy związane ze środowiskiem użytkownika.

* Rdzenie wirtualne zaplecza odpowiadają za ciężkie obciążenia: przetwarzanie zapytań, zarządzanie pamięcią podręczną, uruchamianie serwerów języka R, odświeżanie danych, przetwarzanie języka naturalnego, źródła danych w czasie rzeczywistym oraz renderowanie raportów i obrazów po stronie serwera. Ponadto w przypadku rdzeni wirtualnych zaplecza zarezerwowana jest pewna ilość pamięci. Dostępność wystarczającej pamięci staje się szczególnie ważna w przypadku obsługi dużych modeli danych lub dużej liczby aktywnych zestawów danych.

## <a name="power-bi-report-server"></a>Serwer raportów usługi Power BI
Usługa Power BI Premium obejmuje także możliwość lokalnego uruchomienia serwera raportów usługi Power BI w organizacji. Aby dowiedzieć się więcej, zobacz [Wprowadzenie do serwera raportów usługi Power BI](report-server/get-started.md).

## <a name="next-steps"></a>Następne kroki
[Power BI Premium — często zadawane pytania](service-premium-faq.md)  
[Informacje o wersji usługi Power BI Premium](service-premium-release-notes.md)  
[Jak kupić usługę Power BI Premium](service-admin-premium-purchase.md)  
[Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md)  
[Oficjalny dokument firmy Microsoft na temat usługi Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[Oficjalny dokument dotyczący planowania wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy)  
[Administrowanie usługą Power BI w organizacji](service-admin-administering-power-bi-in-your-organization.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)
