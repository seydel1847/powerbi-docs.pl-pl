---
title: "Zawartość usługi Power BI Pro — co to jest?"
description: "Usługa Power BI Premium została opracowana z myślą o pojemności dla organizacji lub zespołu, aby zapewniać jeszcze bardziej niezawodną wydajność i większe woluminy danych — bez potrzeby kupowania licencji użytkowników."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/10/2017
ms.author: asaxton
ms.openlocfilehash: 816f1151b6f49ace8151f1c26aee18a8c746ff08
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-premium---what-is-it"></a>Power BI Premium — co to jest?
Usługa Power BI Premium zapewnia zasoby dedykowane do uruchamiania usługi Power BI dla organizacji lub zespołu, zapewniając jeszcze bardziej niezawodną wydajność i większe woluminy danych. Ponadto usługa Premium umożliwia szeroką dystrybucję zawartości bez potrzeby zakupu licencji dla użytkowników, którzy mają ją wyświetlać.

Możesz wykorzystać usługę Power BI Premium, przydzielając obszary robocze do pojemności Premium. *Pojemność Premium* jest dedykowanym zasobem dla Twojej organizacji. Obszary robocze, które nie są przypisane do pojemności Premium, znajdą się w pojemności udostępnionej.

*Pojemność udostępniona* jest środowiskiem użytkownika znanym z usługi Power BI, w którym obciążenia są uruchamiane na zasobach komputerowych udostępnianych przez innych klientów. W pojemności udostępnionej wobec użytkowników stosuje się większe limity, aby zapewnić jakość środowiska dla wszystkich użytkowników.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>Warstwy pojemności
Istnieją dwa typy pojemności w usłudze Power BI. Pojemność udostępniona oraz pojemność Power BI Premium. Poniżej przedstawiono różnice między nimi.

|  | Pojemność udostępniona | Pojemność Power BI Premium |
| --- | --- | --- |
| **Częstotliwość odświeżania** |8/dzień |Bez ograniczeń |
| **Izolacja z dedykowanym sprzętem** |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne") |
| **Dystrybucja na poziomie przedsiębiorstwa do** ***wszystkich użytkowników*** | | |
| Aplikacje |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne")<sup>1</sup> |
| Osadzone interfejsy API i kontrolki |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne")<sup>2</sup> |
| **Publikowanie raportów usługi Power BI lokalnie** |![](media/service-premium/not-available.png "Niedostępne") |![](media/service-premium/available.png "Dostępne") |

*<sup>1</sup> Zużycie użytkownika bezpłatnego w aplikacjach obejmuje wyświetlanie zawartości w Internecie i na urządzeniach przenośnych, używanie funkcji pytań i odpowiedzi, szybkiego wglądu, Cortany, eksportowania do formatu CSV, programu Excel i PowerPoint*   
*<sup>2</sup> Przyszłe usprawnienia do wdrożenia w usłudze Power BI Premium po ogólnym udostępnieniu.*

### <a name="premium-capacity"></a>Pojemność Premium
Aby rozpocząć używanie pojemności Power BI Premium, musisz przypisać obszar roboczy do pojemności. Aby uzyskać więcej informacji o sposobie przypisywania obszaru roboczego do pojemności Premium, zobacz [Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md).

Kiedy obszar roboczy jest wspierany przez pojemność Premium, możesz cieszyć się korzyściami usługi Power BI Premium.

* Zaplanowane odświeżanie: użytkownicy wcześniej byli ograniczeni do 8 odświeżeń dziennie podczas planowania odświeżania z zaimportowanymi modelami. To ograniczenie zostało zniesione dla zestawów danych w obszarach roboczych Premium. Nie ma to zastosowania do ustawień zaplanowanego odświeżania pamięci podręcznej w przypadku trybu zapytania bezpośredniego. Pozostają one takie same w pojemności Premium i udostępnionej.
* Izolacja z dedykowanym sprzętem — zgodnie z naturą pojemności udostępnionej na wydajność raportów i pulpitów nawigacyjnych może mieć wpływ zapotrzebowanie na zasoby innych obciążeń w pojemności, niezależnie od zabezpieczeń przed takim zapotrzebowaniem. Z drugiej strony pojemność Premium zapewnia bardziej spójną, niezawodną wydajność dla obciążeń poprzez izolowanie ich od innych niepowiązanych obciążeń.

Jeśli aplikacja jest wspierana przez pojemność Premium (tj. została opublikowana z obszaru roboczego aplikacji obecnie przypisanego do warstwy Premium), opublikowana aplikacja może być używana przez dowolnego użytkownika w organizacji niezależnie od przypisanej do niego licencji. Oznacza to, że nawet bezpłatni użytkownicy usługi Power BI mogą korzystać z tych opublikowanych aplikacji.

### <a name="shared-capacity"></a>Pojemność udostępniona
Domyślnie obszar roboczy będzie znajdować się w pojemności udostępnionej. Dotyczy to również osobistego obszaru *Mój obszar roboczy* wraz z obszarami roboczymi aplikacji. Pojemność udostępniona jest środowiskiem użytkownika znanym z usługi Power BI, w którym obciążenia są uruchamiane na zasobach komputerowych udostępnianych przez innych klientów.

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Węzły pojemności Premium
Usługa Power BI Premium jest dostępna z konfiguracjami węzłów z różnymi pojemnościami rdzeni wirtualnych. Aby uzyskać więcej informacji na temat określonych ofert i kosztów jednostek SKU, zobacz [Cennik usługi Power BI](https://powerbi.microsoft.com/pricing/). Dostępny jest również [kalkulator kosztów](https://powerbi.microsoft.com/calculator/). Aby uzyskać informacje na temat planowania pojemności dla osadzonych funkcji analitycznych, zobacz [Oficjalny dokument dotyczący planowania wdrożenia usługi Power BI Enterprise](https://aka.ms/pbienterprisedeploy).

* Węzły P mogą być używane do wdrożeń osadzonych lub usługi
* Węzły EM mogą być używane wyłącznie do wdrożeń osadzonych

| Węzeł pojemności | Całkowita liczba rdzeni<br/>*(Wewnętrzna baza danych + fronton)* | Rdzenie wewnętrznej bazy danych | Rdzenie frontonu | Limity zapytania bezpośredniego/połączenia na żywo | Maksymalne renderowanie strony w godzinie szczytu | Dostępność |
| --- | --- | --- | --- | --- | --- | --- |
| [EM3 (z miesiąca na miesiąc)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 rdzenie wirtualne |2 rdzenie, 10 GB pamięci RAM |2 rdzenie | |601-1,200 |Dostępne |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 rdzeni wirtualnych |4 rdzenie, 25 GB pamięci RAM |4 rdzenie |30 na sekundę |1,201-2,400 |Dostępne (opcja [z miesiąca na miesiąc](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1) jest również dostępna) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 rdzeni wirtualnych |8 rdzeni, 50 GB pamięci RAM |8 rdzeni |60 na sekundę |2,401-4,800 |Dostępne |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 rdzenie wirtualne |16 rdzeni, 100 GB pamięci RAM |16 rdzeni |120 na sekundę |4,801-9600 |Dostępne |

* Rdzenie frontonu odpowiadają za usługę internetową, pulpit nawigacyjny oraz zarządzanie dokumentami raportów, zarządzanie uprawnieniami dostępu, planowanie, interfejsy API, przekazywanie i pobieranie oraz ogólnie za wszystkie elementy związane ze środowiskiem użytkownika.
* Rdzenie wewnętrznej bazy danych odpowiadają za ciężkie obciążenia: przetwarzanie zapytań, zarządzanie pamięcią podręczną, uruchamianie serwerów R, odświeżanie danych, przetwarzanie języka naturalnego, źródła danych w czasie rzeczywistym oraz renderowanie raportów i obrazów po stronie serwera. Ponadto w przypadku rdzeni wewnętrznej bazy danych zarezerwowana jest pewna ilość pamięci. Dostępność wystarczającej pamięci staje się szczególnie ważna w przypadku obsługi dużych modeli danych lub dużej liczby aktywnych zestawów danych.

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

