---
title: "Lokalna brama danych — często zadawane pytania"
description: "To jest sekcja często zadawanych pytań dotyczących lokalnej bramy danych. W jednym miejscu znajdują się tutaj często zadawane pytania dotyczące bramy."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: d06a83584bb1b270eb10f6c7098358e718f3492f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="on-premises-data-gateway-faq"></a>Lokalna brama danych — często zadawane pytania
<!-- Shared FAQ shared Include -->
[!INCLUDE [gateway-onprem-faq-shared-include](./includes/gateway-onprem-faq-shared-include.md)]

## <a name="analysis-services"></a>Analysis Services
**Pytanie:** Czy mogę użyć pliku msdmpump.dll, aby utworzyć niestandardowe obowiązujące mapowania nazw użytkowników w usługach Analysis Services?  
**Odpowiedź:** Nie. Nie jest to obecnie obsługiwane.

**Pytanie:** Czy mogę użyć bramy, aby nawiązać połączenie z wystąpieniem wielowymiarowych (OLAP)?  
**Odpowiedź:** Tak. Lokalna brama danych obsługuje połączenia na żywo z modelami tabelarycznymi i wielowymiarowymi usług Analysis Services.

**Pytanie:** Co zrobić, jeśli brama została zainstalowana na komputerze znajdującym się w innej domenie niż mój serwer lokalny używający uwierzytelniania systemu Windows?  
**Odpowiedź:** Nie możemy udzielić jednoznacznej odpowiedzi. Wszystko zależy od relacji zaufania między tymi dwiema domenami. Jeśli dwie różne domeny znajdują się w modelu domen zaufania, to brama być może będzie mogła nawiązać połączenie z serwerem usług Analysis Services, a obowiązująca nazwa użytkownika zostanie rozpoznana. Jeśli nie, może wystąpić błąd logowania.

**Pytanie:** Jak sprawdzić obowiązującą nazwę użytkownika przekazywaną do mojego lokalnego serwera usług Analysis Services?  
**Odpowiedź:** Na to pytanie udzieliliśmy odpowiedzi w [artykule dotyczącym rozwiązywania problemów](service-gateway-onprem-tshoot.md).

**Pytanie:** Mam 25 baz danych w usługach Analysis Services. Czy istnieje sposób jednoczesnego włączenia ich na potrzeby bramy?  
**Odpowiedź:** Nie. Zaimplementowanie takiej możliwości jest zaplanowane, ale nie ustaliliśmy jeszcze harmonogramu.

## <a name="administration"></a>Administracja
**Pytanie:** Czy brama może mieć więcej niż jednego administratora?  
**Odpowiedź:** Tak. Podczas zarządzania bramą możesz przejść na kartę administratora, aby dodać dodatkowych administratorów.

**Pytanie:** Czy administrator bramy musi być administratorem na maszynie, na której zainstalowano bramę?  
**Odpowiedź:** Nie. Administrator bramy jest używany do zarządzania bramą z poziomu usługi.

**Pytanie:** Czy mogę uniemożliwić użytkownikom w organizacji utworzenie bramy?  
**Odpowiedź:** Nie. Zaimplementowanie takiej możliwości jest zaplanowane, ale nie ustaliliśmy jeszcze harmonogramu.

**Pytanie:** Czy mogę uzyskać informacje dotyczące użycia oraz statystyki związane z bramą w mojej organizacji?  
**Odpowiedź:** Nie. Zaimplementowanie takiej możliwości jest zaplanowane, ale nie ustaliliśmy jeszcze harmonogramu.

## <a name="power-bi"></a>Power BI
**Pytanie:** Czy muszę uaktualnić bramę osobistą?
**Odpowiedź:** Nie, możesz korzystać z bramy osobistej na potrzeby usługi Power BI.

**Pytanie:** Jak często kafelki na pulpicie nawigacyjnym w usłudze Power BI są odświeżane, gdy połączenie zostało nawiązane za pośrednictwem lokalnej bramy danych?  
**Odpowiedź:** Co około 10 minut. Połączenia w trybie zapytania bezpośredniego działają właśnie w taki sposób. Nie oznacza to, że kafelek wysyła zapytanie do serwera lokalnego i wyświetla nowe dane co 10 minut.

**Pytanie:** Czy mogę przekazać skoroszyty programu Excel z modelami danych dodatku Power Pivot, które nawiązują połączenie z lokalnymi źródłami danych? Czy na potrzeby takiego scenariusza wymagana jest brama?  
**Odpowiedź:** Tak, możesz przekazać skoroszyt. Brama nie jest potrzebna. Ponieważ jednak dane będą znajdować się w modelu danych programu Excel, raporty w usłudze Power BI oparte na skoroszycie programu Excel nie będą raportami na żywo. Aby odświeżyć raporty w usłudze Power BI, za każdym razem konieczne będzie ponowne przekazanie zaktualizowanego skoroszytu. Możesz też użyć bramy z funkcją zaplanowanego odświeżania.

**Pytanie:** Jeśli użytkownicy udostępniają pulpity nawigacyjne z połączeniem zapytania bezpośredniego, to czy inni użytkownicy będą mogli wyświetlać dane, nawet jeśli nie będą mieli takich samych uprawnień?  
**Odpowiedź:** W przypadku pulpitu nawigacyjnego połączonego z usługami Analysis Services dla użytkowników będą widoczne tylko te dane, do których mają dostęp. Jeśli użytkownicy nie mają takich samych uprawnień, nie będą dla nich widoczne żadne dane. W przypadku innych źródeł danych wszyscy użytkownicy będą współdzielić poświadczenia wprowadzone przez administratora dla danego źródła danych.

**Pytanie:** Dlaczego nie mogę nawiązać połączenia ze swoim serwerem Oracle?  
**Odpowiedź:** Aby nawiązać połączenie z serwerem Oracle, konieczne może być zainstalowanie klienta Oracle i skonfigurowanie pliku tnsnames.ora przy użyciu odpowiednich informacji o serwerze. Jest to oddzielna instalacja poza bramą. Aby uzyskać więcej informacji, zobacz [Instalowanie klienta Oracle](service-gateway-onprem-manage-oracle.md#installing-the-oracle-client).

**Pytanie:** Czy brama będzie działać z usługą ExpressRoute?  
**Odpowiedź:** Tak. Aby uzyskać więcej informacji na temat usług ExpressRoute i Power BI, zobacz [Usługi Power BI i ExpressRoute](service-admin-power-bi-expressroute.md).

## <a name="next-steps"></a>Następne kroki
[Lokalna brama danych](service-gateway-onprem.md)  
[Lokalna brama danych — szczegóły](service-gateway-onprem-indepth.md)  
[Rozwiązywanie problemów z lokalną bramą danych](service-gateway-onprem-tshoot.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

