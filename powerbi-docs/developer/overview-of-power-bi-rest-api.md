---
title: Co mogę zrobić za pomocą interfejsu API usługi Power BI?
description: Co mogę zrobić za pomocą interfejsu API usługi Power BI?
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 8a688f46a46dbb1015629c7785d96b62d4f8df26
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/06/2018
ms.locfileid: "34813248"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Co deweloperzy mogą robić z interfejsem API usługi Power BI?
W usłudze Power BI są wyświetlane interakcyjne pulpity nawigacyjne, które można tworzyć i aktualizować z wielu różnych źródeł danych w czasie rzeczywistym. Używając dowolnego języka programowania obsługującego wywołania REST, można tworzyć aplikacje integrujące się z pulpitem nawigacyjnym usługi Power BI w czasie rzeczywistym. Można również integrować kafelki i raporty usługi Power BI w aplikacje.

Deweloperzy mogą również tworzyć własne wizualizacje danych, które mogą być używane w interakcyjnych raportach i pulpitach nawigacyjnych. 

Poniżej przedstawiono niektóre czynności, które można wykonać za pomocą interfejsów API usługi Power BI.

| **Czynność** | **Przejdź tutaj** |
| --- | --- |
| Osadzanie pulpitów nawigacyjnych, raportów i kafelków dla użytkowników usługi Power BI i użytkowników niekorzystających z tej usługi (aplikacja jest właścicielem danych) |[Jak osadzić pulpity nawigacyjne, raporty i kafelki usługi Power BI](embedding-content.md) |
| Rozszerzanie istniejącego biznesowego przepływu pracy w celu wypychania kluczowych danych do pulpitu nawigacyjnego usługi Power BI |[Wypychanie danych do pulpitu nawigacyjnego](walkthrough-push-data.md) |
| Uwierzytelnianie w usłudze Power BI |[Uwierzytelnianie w usłudze Power BI](get-azuread-access-token.md) |
| Tworzenie wizualizacji niestandardowej |[Tworzenie niestandardowych wizualizacji przy użyciu narzędzi deweloperskich](../service-custom-visuals-getting-started-with-developer-tools.md) |

> [!NOTE]
> Interfejsy API usługi Power BI nadal odwołują się do obszarów roboczych aplikacji jako grup. Wszystkie odwołania do grup oznaczają, że pracujesz z obszarami roboczymi aplikacji.
> 
> 

## <a name="power-bi-developer-samples"></a>Przykłady Dewelopera usługi Power BI
Przykłady Dewelopera usługi Power BI obejmują elementy do osadzania pulpitów nawigacyjnych, raportów i kafelków.

[Przykłady Dewelopera usługi Power BI](https://github.com/Microsoft/PowerBI-Developer-Samples)

* Przykłady w kategorii **Aplikacja jest właścicielem danych** dotyczą osadzania w przypadku użytkowników niekorzystających z usługi Power BI.
* Przykłady w kategorii **Użytkownik jest właścicielem danych** dotyczą osadzania w przypadku użytkowników usługi Power BI.

## <a name="github-repositories"></a>Repozytoria GitHub
* [Zestaw SDK .NET](https://github.com/Microsoft/PowerBI-CSharp)
* [Interfejs API JavaScript](https://github.com/Microsoft/PowerBI-JavaScript)
* [Wizualizacje niestandardowe](https://github.com/Microsoft/PowerBI-visuals)

## <a name="developer-tools"></a>Narzędzia deweloperskie
Poniżej wymieniono narzędzia ułatwiające tworzenie elementów usługi Power BI.

[Narzędzie obsługi dołączania](https://aka.ms/embedsetup) umożliwia szybkie rozpoczęcie pracy i pobranie przykładowej aplikacji w celu rozpoczęcia osadzania zawartości usługi Power BI.

Wybierz rozwiązanie, które jest odpowiednie dla Ciebie:
* [Osadzanie dla swoich klientów](embedding.md#embedding-for-your-customers) zapewnia możliwość osadzenia pulpitów nawigacyjnych i raportów u użytkowników, którzy nie mają konta w usłudze Power BI. Uruchom rozwiązanie [osadzania dla klientów](https://aka.ms/embedsetup/AppOwnsData).
* [Osadzanie dla swojej organizacji](embedding.md#embedding-for-your-organization) umożliwia rozszerzanie usługi Power BI. Uruchom rozwiązanie [osadzania dla organizacji](https://aka.ms/embedsetup/UserOwnsData).

Aby uzyskać pełen przykład użycia interfejsu API języka JavaScript, można użyć [narzędzia Playground](https://microsoft.github.io/PowerBI-JavaScript/demo). Jest to szybki sposób na zapoznanie się z różnymi typami przykładów usługi Power BI Embedded. Możesz również uzyskać więcej informacji na temat interfejsu API języka JavaScript odwiedzając stronę [wiki Power BI-JavaScript](https://github.com/Microsoft/powerbi-javascript/wiki).

## <a name="next-steps"></a>Następne kroki
[Wypychanie danych do zestawu danych](walkthrough-push-data.md)  
[Wprowadzenie do korzystania z narzędzi deweloperskich do tworzenia wizualizacji niestandardowych](../service-custom-visuals-getting-started-with-developer-tools.md) 
[Dokumentacja interfejsu API REST usługi Power BI](https://docs.microsoft.com/rest/api/power-bi/)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)