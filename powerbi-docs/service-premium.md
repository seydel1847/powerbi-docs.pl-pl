---
title: Power BI Premium — co to jest?
description: Usługa Power BI Premium została opracowana z myślą o pojemności dla organizacji lub zespołu, aby zapewniać jeszcze bardziej niezawodną wydajność i większe woluminy danych — bez potrzeby kupowania licencji użytkowników.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2018
LocalizationGroup: Premium
ms.openlocfilehash: f7024b3e4827201edb4137eb513333030e39059f
ms.sourcegitcommit: 2bdcb9e9959302a35ee90a145e4ff832a02aacb9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43250755"
---
# <a name="power-bi-premium---what-is-it"></a>Power BI Premium — co to jest?
Usługa Power BI Premium zapewnia zasoby dedykowane do uruchamiania usługi Power BI dla organizacji lub zespołu. Zapewnia ona bardziej niezawodną wydajność i umożliwia przetwarzanie większych ilości danych. Ponadto usługa Premium umożliwia szeroką dystrybucję zawartości bez potrzeby zakupu licencji dla użytkowników, którzy mają ją wyświetlać.

Możesz wykorzystać usługę Power BI Premium, przydzielając obszary robocze do pojemności Premium. *Pojemność Premium* jest dedykowanym zasobem dla Twojej organizacji. Obszary robocze, które nie są przypisane do pojemności Premium, znajdują się w pojemności udostępnionej.

W przypadku *pojemności udostępnionej* obciążenia są uruchamiane na zasobach komputerowych udostępnianych przez innych klientów. W pojemności udostępnionej wobec użytkowników stosuje się większe limity, aby zapewnić jakość środowiska dla wszystkich użytkowników.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>Warstwy pojemności

Istnieją dwa typy pojemności w usłudze Power BI. Pojemność udostępniona oraz pojemność Power BI Premium. Poniżej przedstawiono różnice między nimi.

|  | Pojemność udostępniona | Pojemność Power BI Premium |
| --- | --- | --- |
| **Częstotliwość odświeżania** |8/dzień |48/dzień |
| **Izolacja z dedykowanym sprzętem** |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne") |
| **Dystrybucja na poziomie przedsiębiorstwa do** ***wszystkich użytkowników*** | | |
| Aplikacje i udostępnianie |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne")<sup>1</sup> |
| Osadzone interfejsy API i kontrolki |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne")<sup>2</sup> |
| **Publikowanie raportów usługi Power BI lokalnie** |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne") |

*<sup>1</sup> Aby uzyskać więcej informacji, zobacz funkcjonalność [Możliwości użytkowników w usługach Power BI Pro i Power BI Premium](service-free-vs-pro.md).*  
*<sup>2</sup> Przyszłe usprawnienia do wdrożenia w usłudze Power BI Premium po ogólnym udostępnieniu.*

### <a name="premium-capacity"></a>Pojemność Premium

Aby rozpocząć używanie pojemności Power BI Premium, musisz przypisać obszar roboczy do pojemności. Aby uzyskać więcej informacji o sposobie przypisywania obszaru roboczego do pojemności Premium, zobacz [Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md).

Kiedy pojemność Premium obsługuje obszar roboczy, możesz cieszyć się korzyściami usługi Power BI Premium.

* **Zaplanowane odświeżanie**: w przypadku pojemności udostępnionej zaplanowane odświeżanie importowanych modeli jest ograniczone do 8 razy dziennie. Liczba odświeżeń jest zwiększana do 48 razy dziennie w przypadku zestawów danych w obszarach roboczych Premium. Nie ma to zastosowania do ustawień zaplanowanego odświeżania pamięci podręcznej w przypadku trybu zapytania bezpośredniego. Pozostają one takie same w pojemności Premium i udostępnionej.
* **Izolacja z dedykowanym sprzętem**: zgodnie z naturą pojemności udostępnionej na wydajność raportów i pulpitów nawigacyjnych może mieć wpływ zapotrzebowanie na zasoby innych obciążeń w pojemności, niezależnie od zabezpieczeń przed takim zapotrzebowaniem. Z drugiej strony pojemność Premium zapewnia bardziej spójną, niezawodną wydajność dla obciążeń poprzez izolowanie ich od innych niepowiązanych obciążeń.

Jeśli aplikacja jest wspierana przez pojemność Premium (tj. została opublikowana z obszaru roboczego aplikacji obecnie przypisanego do warstwy Premium), opublikowana aplikacja może być używana przez dowolnego użytkownika w organizacji niezależnie od przypisanej do niego licencji.

### <a name="shared-capacity"></a>Pojemność udostępniona

Domyślnie obszar roboczy znajduje się w pojemności udostępnionej. Dotyczy to również osobistego obszaru *Mój obszar roboczy* wraz z obszarami roboczymi aplikacji. Pojemność udostępniona jest środowiskiem użytkownika znanym z usługi Power BI, w którym obciążenia są uruchamiane na zasobach komputerowych udostępnianych przez innych klientów.

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Węzły pojemności Premium

Usługa Power BI Premium jest dostępna z konfiguracjami węzłów z różnymi pojemnościami rdzeni wirtualnych. Aby uzyskać więcej informacji na temat określonych ofert i kosztów jednostek SKU, zobacz [Cennik usługi Power BI](https://powerbi.microsoft.com/pricing/). Dostępny jest również [kalkulator kosztów](https://powerbi.microsoft.com/calculator/). Aby uzyskać informacje na temat planowania pojemności dla osadzonych funkcji analitycznych, zobacz [Oficjalny dokument dotyczący planowania wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy).

* Węzły P mogą być używane do wdrożeń osadzonych lub usługi.
* Węzły EM mogą być używane wyłącznie do wdrożeń osadzonych. Węzły EM nie mają dostępu do możliwości premium, takich jak udostępnianie aplikacji użytkownikom, którzy nie mają licencji usługi Power BI Pro.

>[!NOTE]
>Linki w tej tabeli działają prawidłowo wyłącznie dla użytkowników, którzy są administratorami globalnymi usługi Office 365 — inni zobaczą błąd 404.

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
Usługa Power BI Premium obejmuje uprawnienia do lokalnego uruchomienia serwera raportów usługi Power BI. Aby uzyskać więcej informacji, zobacz [Wprowadzenie do serwera raportów usługi Power BI](report-server/get-started.md).

## <a name="next-steps"></a>Następne kroki
[Power BI Premium — często zadawane pytania](service-premium-faq.md)  
[Informacje o wersji usługi Power BI Premium](service-premium-release-notes.md)  
[Jak kupić usługę Power BI Premium](service-admin-premium-purchase.md)  
[Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md)  
[Oficjalny dokument firmy Microsoft na temat usługi Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[Oficjalny dokument dotyczący planowania wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy)  
[Administrowanie usługą Power BI w organizacji](service-admin-administering-power-bi-in-your-organization.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)