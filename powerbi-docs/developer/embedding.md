---
title: Osadzanie przy użyciu usługi Power BI
description: Usługa Power BI oferuje interfejsy API do osadzania Twoich pulpitów nawigacyjnych i raportów w aplikacjach.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 2e899593cbe3453381dd2d3457cec97467aec4d6
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34561752"
---
# <a name="embedding-with-power-bi"></a>Osadzanie przy użyciu usługi Power BI
Usługa Power BI oferuje interfejsy API do osadzania Twoich pulpitów nawigacyjnych i raportów w aplikacjach. Interfejsy API usługi Power BI oferują spójny zestaw funkcji oraz dostęp do najnowszych elementów usługi Power BI — takich jak pulpity nawigacyjne, bramy i obszary robocze aplikacji — podczas osadzania zawartości.

## <a name="a-single-api"></a>Pojedynczy interfejs API
Istnieją dwa główne scenariusze osadzania zawartości usługi Power BI.  Osadzanie dla użytkowników w organizacji (mających licencję usługi Power BI) i osadzanie dla użytkowników i klientów bez konieczności posiadania licencji usługi Power BI. Interfejs API REST usługi Power BI umożliwia oba scenariusze. 

W przypadku klientów i użytkowników bez licencji usługi Power BI można osadzać pulpity nawigacyjne i raporty w swojej niestandardowej aplikacji przy użyciu tego samego interfejsu API, aby obsłużyć swoją organizację lub klientów. Klienci widzą dane zarządzane przez aplikację. A użytkownicy usługi Power BI w organizacji będą mieć dodatkowe opcje wyświetlania *własnych danych* bezpośrednio w usłudze Power BI lub w kontekście osadzonej aplikacji. Możesz wykorzystać wszystkie zalety języka JavaScript i interfejsów API REST do swoich potrzeb osadzania.

Aby zobaczyć przykład działania osadzania, zobacz [Przykład osadzania przy użyciu języka JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Osadzanie dla swojej organizacji
Osadzanie dla swojej organizacji umożliwia rozszerzanie usługi Power BI. Wymaga to, aby użytkownicy Twojej aplikacji zalogowali się w usłudze Power BI, gdy będą chcieli wyświetlić swoją zawartość. Gdy ktoś w Twojej organizacji się zaloguje, będzie miał dostęp tylko do pulpitów nawigacyjnych i raportów, których jest właścicielem lub które zostały mu udostępnione w usłudze Power BI. 

*Do przykładów osadzania dla swojej organizacji należą wewnętrzne aplikacje internetowe, składnik Web Part usługi SharePoint Online i integracja aplikacji Microsoft Teams.*

W przypadku osadzania dla swojej organizacji zobacz poniższe tematy:

* [Integrowanie raportu w aplikacji](integrate-report.md)
* [Integrowanie pulpitu nawigacyjnego w aplikacji](integrate-dashboard.md)
* [Integrowanie kafelka w aplikacji](integrate-tile.md)

Podczas osadzania dla użytkowników usługi możliwości samoobsługi, takie jak edytowanie, zapisywanie i inne, są dostępne za pośrednictwem [interfejsu API języka JavaScript](https://github.com/Microsoft/PowerBI-JavaScript).

Możesz użyć [narzędzia obsługi dołączania na potrzeby osadzania w organizacji](https://aka.ms/embedsetup/UserOwnsData), aby szybko zacząć pracę i pobrać przykładową aplikację, która przeprowadzi Cię przez proces integracji raportu organizacji.

## <a name="embedding-for-your-customers"></a>Osadzanie dla swoich klientów
Osadzanie dla swoich klientów zapewnia możliwość osadzenia pulpitów nawigacyjnych i raportów u użytkowników, którzy nie mają konta w usłudze Power BI. Twoi klienci nie muszą nic wiedzieć o usłudze Power BI. Do utworzenia aplikacji osadzonej jest potrzebne co najmniej jedno konto usługi Power BI Pro. Konto usługi Power BI Pro działa jako konto główne dla Twojej aplikacji. Myśl o tym, jak o koncie serwera proxy. Konto Power BI Pro umożliwia też generowanie osadzonych tokenów zapewniających dostęp do pulpitów nawigacyjnych i raportów w ramach usługi Power BI. Należą one do Twojej usługi i są przez nią zarządzane. 

*Przykładem osadzania dla swoich klientów jest aplikacja niezależnego dostawcy oprogramowania sprzedawana innym firmom.*

![Przepływ osadzania dla swoich klientów](media/embedding/powerbi-embed-flow.png)

Aby osadzić pulpity nawigacyjne, raporty i kafelki, użyj tych samych interfejsów API, które byłyby używane do osadzania dla swojej organizacji.

> [!IMPORTANT]
> Chociaż osadzanie ma zależność od usługi Power BI, nie ma zależności od usługi Power BI dla Twoich klientów. Nie będą oni musieli tworzyć konta w usłudze Power BI w celu wyświetlenia zawartości osadzonej w aplikacji.
> 

Gdy wszystko jest gotowe do przejścia do środowiska produkcyjnego, obszar roboczy Twojej aplikacji musi zostać przypisany do pojemności. Usługa Power BI Embedded, w ramach platformy Microsoft Azure, oferuje pojemność do wykorzystania dla Twoich aplikacji.

Aby uzyskać szczegółowe informacje na temat osadzania, zobacz [Jak osadzić pulpity nawigacyjne, raporty i kafelki usługi Power BI](embedding-content.md).

Możesz użyć [narzędzia obsługi dołączania na potrzeby osadzania dla klientów](https://aka.ms/embedsetup/AppOwnsData), aby szybko zacząć pracę i pobrać przykładową aplikację, która przeprowadzi Cię przez proces integracji raportu w aplikacji.

Jeśli była używana usługa Kolekcje obszarów roboczych usługi Power BI w ramach platformy Azure, zobacz [Migracja zawartości z usługi platformy Azure Kolekcje obszarów roboczych usługi Power BI](migrate-from-powerbi-embedded.md), aby uzyskać informacje o sposobie migracji swojej zawartości.

## <a name="next-steps"></a>Następne kroki
[Jak osadzić pulpity nawigacyjne, raporty i kafelki usługi Power BI](embedding-content.md)  
[Jak migrować zawartość kolekcji obszarów roboczych usługi Power BI Embedded do usługi Power BI](migrate-from-powerbi-embedded.md)  
[Power BI Premium — co to jest?](../service-premium.md)  
[Repozytorium Git interfejsu API języka JavaScript](https://github.com/Microsoft/PowerBI-JavaScript)  
[Repozytorium Git języka C# usługi Power BI](https://github.com/Microsoft/PowerBI-CSharp)  
[Przykład osadzania przy użyciu języka JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Oficjalny dokument dotyczący planowania pojemności na potrzeby osadzonej analizy](https://aka.ms/pbiewhitepaper)  
[Oficjalny dokument na temat usługi Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

