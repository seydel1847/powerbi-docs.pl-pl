---
title: Może być konieczny dodatkowy zakup — wytyczne dotyczące wizualizacji usługi Power BI
description: Dowiedz się, jak publikować swoje wizualizacje niestandardowe w usłudze AppSource do użytku przez inne osoby, które dokonają zakupu.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/26/2018
ms.openlocfilehash: 9ef7890c6f80845a9e6d1bd02e35778ed866ff54
ms.sourcegitcommit: 35d763dfc75c229204d36fd8b35c1e860786b707
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2018
ms.locfileid: "52332222"
---
# <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Wskazówki dotyczące wizualizacji usługi Power BI wymagająych dodatkowego zakupu

Do niedawna na platformie **Marketplace (AppSource)** akceptowane były tylko bezpłatne wizualizacje usługi Power BI. Te zasady zostały zmienione — obecnie można przesyłać do witryny **AppSource** również wizualizacje z oznaczeniem „Może być konieczny dodatkowy zakup”. Wizualizacje wymagające dodatkowego zakupu są podobne do dodatków oferowanych w Sklepie Office z oznaczeniem „zakupy w aplikacji”. Deweloperzy mogą również przesyłać te wizualizacje do certyfikacji po ich zatwierdzeniu przez zespół platformy **AppSource** i spełnieniu wymagań dotyczących certyfikacji opisanych w [artykule dotyczącym certyfikowanych wizualizacji niestandardowych](../power-bi-custom-visuals-certified.md).

> [!Note]
> Certyfikowana wizualizacja nie może korzystać z zewnętrznych zasobów ani usług.

## <a name="whats-changing-in-the-submission-process"></a>Co ulega zmianie w procesie przesyłania?

Deweloperzy mogą przekazywać swoje wizualizacje zawierające funkcje wymagające zakupu w aplikacji do witryny AppSource za pośrednictwem pulpitu nawigacyjnego sprzedawcy, tak samo, jak w przypadku wizualizacji bezpłatnych. Aby wskazać, że przekazywana wizualizacja zawiera funkcje wymagające zakupu w aplikacji, deweloperzy powinni w uwagach na pulpicie nawigacyjnym sprzedawcy wpisać „Visual with in-app purchases” (Wizualizacja z zakupami w aplikacji). Ponadto deweloperzy muszą przekazać klucz licencji lub token, umożliwiający zespołowi weryfikacyjnemu weryfikację funkcji wymagających zakupu w aplikacji. Po weryfikacji i zatwierdzeniu wizualizacji będzie ona widoczna w witrynie AppSource z adnotacją „Może być konieczny dodatkowy zakup” w sekcji zawierającej opcje ceny.

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>Co to jest wizualizacja usługi Power BI zawierająca funkcje wymagające zakupu w aplikacji?

Wizualizacja zawierająca funkcje wymagające zakupu w aplikacji to bezpłatna wizualizacja, która jednak oprócz bezpłatnych funkcji zawiera również funkcje dodatkowe, których użycie wymaga dodatkowej opłaty. Deweloperzy muszą poinformować użytkowników o tym, jakie funkcje wymagają dodatkowego zakupu, w opisie wizualizacji. Obecnie firma Microsoft nie zapewnia natywnych interfejsów API do obsługi zakupów w aplikacjach i dodatkach. Deweloperzy mogą korzystać z dowolnego systemu płatności innej firmy do obsługi tych zakupów. Zapoznaj się z [zasadami](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads) sklepu.

## <a name="logo-guidelines"></a>Wytyczne dotyczących logo

W tej sekcji opisano specyfikacje dotyczące logo i logotypów dodawanych w wizualizacjach.

> [!NOTE]
> Logo są dozwolone wyłącznie w trybie edycji. Logo nie mogą być widoczne w trybie wyświetlania.

![definitions](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![things-to-keep](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![things-to](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![size-and-format ](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![margins-and](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![edit-mode](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>Najlepsze rozwiązania

### <a name="visual-landing-page"></a>Strona docelowa wizualizacji

Strona docelowa pozwala wyjaśnić użytkownikom, w jaki sposób mogą korzystać z wizualizacji oraz jak mogą zakupić licencję. Nie należy umieszczać na niej automatycznie odtwarzanych filmów wideo. Należy dodać tylko treści przydatne dla użytkowników, na przykład informacje lub linki do informacji o zakupie licencji oraz instrukcje korzystania z funkcji wymagających zakupu w aplikacji.

### <a name="license-key-and-token"></a>Klucz licencji i token

Dla wygody użytkowników dodaj pola związane z kluczem licencji lub tokenem w górnej części okienka Formatowanie.

## <a name="next-steps"></a>Następne kroki

Dowiedz się, jak publikować swoje wizualizacje niestandardowe w usłudze [AppSource](office-store.md) do użytku przez inne osoby.
