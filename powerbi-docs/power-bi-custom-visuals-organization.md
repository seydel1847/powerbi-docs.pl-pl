---
title: "Korzystanie z wizualizacji niestandardowych organizacji w usłudze Power BI"
description: "Tworzenie i korzystanie z wizualizacji niestandardowych organizacji oraz zarządzanie nimi w usłudze Power BI"
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/06/2018
ms.author: maghan
ms.openlocfilehash: 2c90ea4a7e95c354b6dfaec04cff7e5e4009b55f
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2018
---
# <a name="using-organization-custom-visuals-in-power-bi-preview"></a>Korzystanie z wizualizacji niestandardowych organizacji w usłudze Power BI (wersja zapoznawcza)

Niestandardowe elementy wizualne w usłudze Power BI służą do tworzenia unikatowego typu wizualizacji dostosowanych do potrzeb użytkownika lub przedstawianych wyników analiz. Te wizualizacje niestandardowe są często tworzone przez deweloperów, gdy bogaty zestaw elementów wizualnych dostępnych się w usłudze Power BI nie spełnia ich wymagań. 

W niektórych organizacjach wizualizacje niestandardowe mają szczególne znaczenie. Mogą one być niezbędne do przekazania określonych danych lub wyników analiz specyficznych dla organizacji, mogą mieć określone wymagania dotyczące danych lub też wyróżniać metody firm prywatnych. Takie organizacje muszą opracować niestandardowe elementy wizualne, udostępnić je w organizacji oraz zadbać o ich odpowiednie utrzymanie. Niestandardowe elementy wizualne usługi Power BI (teraz w wersji zapoznawczej) dają organizacjom taką możliwość. 

Na poniższej ilustracji przedstawiono proces przepływu wizualizacji niestandardowych organizacji (w wersji zapoznawczej) w usłudze Power BI od administratora przez fazy projektowania i utrzymania, aż do analityka danych.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

## <a name="how-to-enable-organizational-custom-visuals-preview"></a>Jak włączyć wizualizacje niestandardowe organizacji (w wersji zapoznawczej)

Wizualizacje niestandardowe organizacji są obecnie dostępne w wersji zapoznawczej, dlatego należy włączyć tę funkcję w programie Power BI Desktop. Aby włączyć tę funkcję wersji zapoznawczej, wybierz na wstążce kolejno opcje Plik > Opcje i ustawienia > Opcje, a następnie w okienku po lewej stronie wybierz funkcje wersji zapoznawczej. Zaznacz pole wyboru Wizualizacje niestandardowe mojej organizacji, zgodnie z rysunkiem poniżej.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-02.jpg)

Wizualizacje organizacji są wdrażane i zarządzane przez administratora usługi Power BI w portalu administratora. Po wdrożeniu w repozytorium organizacji użytkownicy mogą łatwo odnajdywać i importować wizualizacje niestandardowe organizacji do swoich raportów bezpośrednio w programie Power BI Desktop.

## <a name="using-organizational-custom-visuals"></a>Korzystanie z wizualizacji niestandardowych organizacji

Aby dowiedzieć się więcej o sposobach użycia wizualizacji niestandardowych organizacji w utworzonych raportach, zobacz artykuł: [Wizualizacje niestandardowe w usłudze Power BI](power-bi-custom-visuals.md).
 
## <a name="administering-organizational-custom-visuals"></a>Administrowanie wizualizacjami niestandardowymi organizacji

Aby dowiedzieć się więcej na temat sposobu administrowania i zarządzania wizualizacjami niestandardowymi organizacji oraz ich wdrażania, zobacz artykuł zawierający [więcej informacji o wdrażaniu wizualizacji niestandardowych organizacji i zarządzaniu nimi](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> Wizualizacja niestandardowa może zawierać kod stwarzający zagrożenie dla bezpieczeństwa i prywatności. Przed wdrożeniem wizualizacji niestandardowej w repozytorium organizacji upewnij się, że jej autor i źródło należą do zaufanych. 
> 

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia
 
Ponieważ wizualizacje niestandardowe organizacji są dostępne w wersji zapoznawczej, warto uwzględnić pewne aspekty i ograniczenia.
 
Administrator:

* Starsze wizualizacje niestandardowe (np. wizualizacje niestandardowe, które nie są wbudowane w nowych interfejsach API objętych kontrolą wersji) nie są obsługiwane.

* Przeprowadzenie aktualizacji „w miejscu” nie jest jeszcze obsługiwane. Aby zaktualizować wizualizację, musisz przekazać nową wersję wizualizacji do repozytorium organizacji (upewniając się, że ma ona taki sam identyfikator Visual ID w pliku PBIVIZ). Autorzy raportów mogą następnie zaimportować nową wersję do raportu i zastąpić w miejscu bieżącą wersję wizualizacji w raporcie.

* Jeśli wizualizacja niestandardowa zostanie usunięta z repozytorium, wszystkie istniejące raporty, które z niej korzystają, zakończą renderowanie. Operacja usunięcia z repozytorium jest nieodwracalna.
 
Użytkownik końcowy:

* Korzystanie z tej samej wizualizacji (tego samego identyfikatora Visual ID) z publicznej platformy handlowej (AppSource) oraz z repozytorium organizacji nie jest obsługiwane. W tym przypadku zostanie użyta ostatnio zaimportowana wizualizacja.

* Zewnętrzne udostępnianie elementów wizualnych organizacji w pulpitach nawigacyjnych i raportach nie jest obsługiwane. Użytkownicy spoza organizacji, którzy wyświetlają pulpit nawigacyjny zawierający wizualizację niestandardową organizacji, zobaczą pustą wizualizację. 

* Wizualizacje organizacji nie obsługują kolekcji obszarów roboczych usługi Power BI.

* Wizualizacje niestandardowe organizacji w raportach publikowanych w Internecie nie będą renderowane.

* Wizualizacja Visio, wizualizacja PowerApps oraz wizualizacja GlobeMap z platformy handlowej AppSource nie będą renderowane, jeśli zostaną wdrożone za pośrednictwem repozytorium organizacji.

* Jeśli administrator usunie z repozytorium wizualizację niestandardową użytą w raporcie, dana wizualizacja nie będzie renderowana i należy ją usunąć z raportu, by móc go zapisać.