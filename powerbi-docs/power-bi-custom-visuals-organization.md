---
title: Korzystanie z wizualizacji niestandardowych organizacji w usłudze Power BI
description: Tworzenie i korzystanie z wizualizacji niestandardowych organizacji oraz zarządzanie nimi w usłudze Power BI
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 10/29/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: e34491ebc1cc7554e8c8c000da7528754b5a673b
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223104"
---
# <a name="use-organizational-custom-visuals-in-power-bi"></a>Korzystanie z wizualizacji niestandardowych organizacji w usłudze Power BI

Niestandardowe elementy wizualne w usłudze Power BI służą do tworzenia unikatowego typu wizualizacji dostosowanych do potrzeb użytkownika lub przedstawianych wyników analiz. Te wizualizacje niestandardowe są często tworzone przez deweloperów, gdy bogaty zestaw elementów wizualnych dostępnych się w usłudze Power BI nie spełnia ich wymagań. 

W niektórych organizacjach wizualizacje niestandardowe mają szczególne znaczenie. Mogą one być niezbędne do przekazania określonych danych lub wyników analiz specyficznych dla organizacji, mogą mieć określone wymagania dotyczące danych lub też wyróżniać metody firm prywatnych. Takie organizacje muszą opracować niestandardowe elementy wizualne, udostępnić je w organizacji oraz zadbać o ich odpowiednie utrzymanie. Niestandardowe elementy wizualne usługi Power BI dają organizacjom taką możliwość.

Na poniższej ilustracji przedstawiono przepływ wizualizacji niestandardowych organizacji w usłudze Power BI od administratora przez fazy projektowania i utrzymania aż do analityka danych.

![Obraz wizualizacji niestandardowej](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

Wizualizacje organizacji są wdrażane i zarządzane przez administratora usługi Power BI w portalu administratora. Po wdrożeniu w repozytorium organizacji użytkownicy mogą łatwo odnajdywać i importować wizualizacje niestandardowe organizacji do swoich raportów bezpośrednio w programie Power BI Desktop.

Aby dowiedzieć się więcej o sposobach użycia wizualizacji niestandardowych organizacji w utworzonych raportach, zobacz artykuł: [Wizualizacje niestandardowe w usłudze Power BI](power-bi-custom-visuals.md).

## <a name="administer-organizational-custom-visuals"></a>Administrowanie wizualizacjami niestandardowymi organizacji

Aby dowiedzieć się więcej na temat sposobu administrowania i zarządzania wizualizacjami niestandardowymi organizacji oraz ich wdrażania, zobacz artykuł zawierający [więcej informacji o wdrażaniu wizualizacji niestandardowych organizacji i zarządzaniu nimi](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> Wizualizacja niestandardowa może zawierać kod stwarzający zagrożenie dla bezpieczeństwa i prywatności. Przed wdrożeniem wizualizacji niestandardowej w repozytorium organizacji upewnij się, że jej autor i źródło należą do zaufanych.

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia

Istnieje kilka zagadnień i ograniczeń, które trzeba znać.

Administrator:

* Starsze wizualizacje niestandardowe (np. wizualizacje niestandardowe, które nie są wbudowane w nowych interfejsach API objętych kontrolą wersji) nie są obsługiwane.

* Jeśli wizualizacja niestandardowa zostanie usunięta z repozytorium, wszystkie istniejące raporty, które z niej korzystają, zakończą renderowanie. Operacja usunięcia z repozytorium jest nieodwracalna. Aby tymczasowo wyłączyć niestandardowy element wizualny, użyj funkcji „Wyłącz”.

Użytkownik końcowy:

* Wizualizacje niestandardowe organizacji to prywatne wizualizacje zaimportowane z repozytorium organizacji. Ponieważ są to wizualizacje prywatne, nie można ich [eksportować do programu PowerPoint](https://docs.microsoft.com/power-bi/consumer/end-user-powerpoint) ani wyświetlać w wiadomościach e-mail otrzymywanych, gdy użytkownik [subskrybuje strony raportu](https://docs.microsoft.com/power-bi/consumer/end-user-subscribe). Tylko [certyfikowane wizualizacje niestandardowe](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified) importowane bezpośrednio z platformy handlowej obsługują te funkcje.

* Wizualizacja Visio, wizualizacja PowerApps, wizualizacja Mapbox oraz wizualizacja GlobeMap z platformy handlowej AppSource nie będą renderowane, jeśli zostaną wdrożone za pośrednictwem repozytorium organizacji.

## <a name="troubleshoot"></a>Rozwiąż problemy

Aby uzyskać informacje dotyczące rozwiązywania problemów, odwiedź stronę [Rozwiązywanie problemów z wizualizacjami niestandardowymi usługi Power BI](power-bi-custom-visuals-troubleshoot.md).

## <a name="faq"></a>Często zadawane pytania

Aby uzyskać więcej informacji i odpowiedzi na pytania, odwiedź stronę [często zadawanych pytań dotyczących wizualizacji niestandardowych usługi Power BI](power-bi-custom-visuals-faq.md#organizational-custom-visuals).

Masz więcej pytań? [Odwiedź Społeczność usługi Power BI](http://community.powerbi.com/).
