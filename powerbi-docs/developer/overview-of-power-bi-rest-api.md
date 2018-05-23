---
title: Co mogę zrobić za pomocą interfejsu API usługi Power BI?
description: Co mogę zrobić za pomocą interfejsu API usługi Power BI?
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 07/20/2017
ms.author: maghan
ms.openlocfilehash: 47dd0ab87b78e344de176ebe22a1e5dc9753b9b0
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Co deweloperzy mogą robić z interfejsem API usługi Power BI?
W usłudze Power BI są wyświetlane interakcyjne pulpity nawigacyjne, które można tworzyć i aktualizować z wielu różnych źródeł danych w czasie rzeczywistym. Używając dowolnego języka programowania obsługującego wywołania REST, można tworzyć aplikacje integrujące się z pulpitem nawigacyjnym usługi Power BI w czasie rzeczywistym. Można również integrować kafelki i raporty usługi Power BI w aplikacje.

Deweloperzy mogą również tworzyć własne wizualizacje danych, które mogą być używane w interakcyjnych raportach i pulpitach nawigacyjnych. 

Poniżej przedstawiono niektóre czynności, które można wykonać za pomocą interfejsów API usługi Power BI.

| **Czynność** | **Przejdź tutaj** |
| --- | --- |
| Osadzanie pulpitów nawigacyjnych, raportów i kafelków dla użytkowników usługi Power BI i użytkowników niekorzystających z tej usługi (aplikacja jest właścicielem danych) |[Jak osadzić pulpity nawigacyjne, raporty i kafelki usługi Power BI](embedding-content.md) |
| Rozszerzanie istniejącego biznesowego przepływu pracy w celu wypychania kluczowych danych do pulpitu nawigacyjnego usługi Power BI |[Wypychanie danych do pulpitu nawigacyjnego](walkthrough-push-data.md) |
| Importowanie pliku programu Power BI Desktop |[Importowanie pliku PBIX](https://msdn.microsoft.com/library/mt243837.aspx) |
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

* [Przykład osadzania przy użyciu języka JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo)

## <a name="next-steps"></a>Następne kroki
[Wypychanie danych do zestawu danych](walkthrough-push-data.md)  
[Wprowadzenie do korzystania z narzędzi deweloperskich do tworzenia wizualizacji niestandardowych](../service-custom-visuals-getting-started-with-developer-tools.md) 
[Dokumentacja interfejsu API REST usługi Power BI](https://msdn.microsoft.com/library/mt147898.aspx)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

