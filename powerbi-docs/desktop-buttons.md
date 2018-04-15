---
title: Korzystanie z przycisków w usłudze Power BI
description: Przyciski w programie Power BI Desktop umożliwiają tworzenie raportów i pulpitów nawigacyjnych, które zachowują się jak aplikacje, a także pogłębianie zaangażowania użytkowników
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/04/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 7858c76703feb53ebb74bec998ecbebcba3994cc
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/06/2018
---
# <a name="using-buttons-in-power-bi"></a>Korzystanie z przycisków w usłudze Power BI
Przy użyciu **przycisków** w usłudze Power BI można tworzyć raporty i pulpity nawigacyjne, które zachowują się podobnie do aplikacji, i dzięki temu tworzyć angażujące środowisko użytkownika, w którym użytkownicy mogą najeżdżać kursorem, klikać i wchodzić w inne interakcje z zawartością usługi Power BI. Możesz dodać przyciski do raportów w programie **Power BI Desktop**, a następnie udostępnić lub opublikować te raporty w usłudze Power BI, aby utworzyć pulpity nawigacyjne, które będą zapewniać zachowanie podobne do aplikacji dla użytkowników.

![Przyciski w usłudze Power BI](media/desktop-buttons/desktop-buttons_01.png)

Przyciski tworzone w programie **Power BI Desktop** są dostępne do użycia w raportach lub pulpitach nawigacyjnych publikowanych w **usłudze Power BI**.

## <a name="creating-buttons-in-reports"></a>Tworzenie przycisków w raportach
Aby utworzyć przycisk w raporcie w programie **Power BI Desktop**, na wstążce **Narzędzia główne** wybierz opcję **Przyciski**. Zostanie wyświetlone menu rozwijane, w którym możesz wybrać żądany przycisk ze zbioru opcji, jak pokazano na poniższej ilustracji. 

![Dodawanie kontrolki przycisku w programie Power BI Desktop](media/desktop-buttons/desktop-buttons_02.png)

Gdy utworzysz przycisk i wybierzesz go na kanwie raportów, w okienku **Wizualizacje** zostanie wyświetlonych wiele sposobów dostosowania przycisku zgodnie z wymaganiami. Przykładowo możesz włączyć lub wyłączyć opcję **Tekst przycisku**, przełączając suwak na tej karcie w okienku **Wizualizacje**. Możesz też zmienić ikonę przycisku, wypełnienie przycisku, tytuł oraz akcję podejmowaną po kliknięciu przycisku przez użytkownika w raporcie lub pulpicie nawigacyjnym, a także inne właściwości.

![Formatowanie przycisku w programie Power BI Desktop](media/desktop-buttons/desktop-buttons_03.png)

## <a name="set-button-properties-when-idle-hovered-over-or-selected"></a>Ustawianie właściwości przycisku w przypadku bezczynności, najechania kursorem lub wybrania

Przyciski w usłudze Power BI mają trzy stany: domyślny (wyświetlanie przycisku bez najechania kursorem lub wybrania), po najechaniu kursorem lub po wybraniu (często zwanym *kliknięciem*. Wiele kart w okienku **Wizualizacje** można zmodyfikować indywidualnie w oparciu o te trzy stany, co zapewnia dużą elastyczność w zakresie dostosowywania przycisków.

Następujące karty w okienku **Wizualizacje** umożliwiają dostosowywanie formatowania lub zachowania przycisku w oparciu o jego trzy stany:

* Tekst przycisku
* Ikona
* Kontur
* Wypełnij

Aby wybrać sposób wyświetlania przycisku dla każdego stanu, rozwiń jedną z tych kart i wybierz opcję z listy rozwijanej wyświetlonej u góry karty. Na poniższej ilustracji możesz zobaczyć rozwiniętą kartę **Kontur** z wybraną listą rozwijaną wyświetlającą trzy stany:

![Trzy stany przycisku w programie Power BI Desktop](media/desktop-buttons/desktop-buttons_04.png)


## <a name="select-the-action-for-a-button"></a>Wybieranie akcji dla przycisku

Możesz wybrać akcję, która zostanie podjęta, gdy użytkownik wybierze przycisk w usłudze Power BI. Możesz uzyskać dostęp do opcji dotyczących akcji przycisków z poziomu karty **Akcja** w okienku **Wizualizacje**.

![Akcja przycisku w usłudze Power BI](media/desktop-buttons/desktop-buttons_05.png)

Dostępne są następujące opcje dla akcji przycisków:

* Wstecz
* Zakładka
* Pytania i odpowiedzi

Wybranie opcji **Wstecz** spowoduje przeniesienie użytkownika z powrotem do poprzedniej strony raportu. Jest to zwłaszcza przydatne w przypadku stron szczegółowych.

Wybranie opcji **Zakładka** spowoduje wyświetlenie strony raportu skojarzonej z zakładką zdefiniowaną dla bieżącego raportu. Możesz [dowiedzieć się więcej o zakładkach w usłudze Power BI](desktop-bookmarks.md). 

Wybranie opcji **Pytania i odpowiedzi** z listy rozwijanej spowoduje wyświetlenie okna **Eksplorator funkcji Pytania i odpowiedzi**. 

Niektóre przyciski będą mieć automatycznie wybraną akcję domyślną. Na przykład przycisk typu **Pytania i odpowiedzi** automatycznie wybierze opcję **Pytania i odpowiedzi** jako akcję domyślną. Możesz dowiedzieć się więcej o **Eksploratorze funkcji Pytania i odpowiedzi**, sprawdzając [ten wpis w blogu](https://powerbi.microsoft.com/blog/power-bi-desktop-april-2018-feature-summary/#Q&AExplorer).

Możesz wypróbować lub przetestować przyciski utworzone dla raportu przy użyciu kombinacji *CTRL + KLIKNIĘCIE* na przycisku, którego chcesz użyć. 

## <a name="next-steps"></a>Następne kroki
Aby uzyskać więcej informacji o podobnych funkcjach lub interakcji z przyciskami, sprawdź następujące artykuły:

* [Używanie przeglądania szczegółowego w programie Power BI Desktop](desktop-drillthrough.md)
* [Wyświetlanie kafelka pulpitu nawigacyjnego lub wizualizacji raportu w trybie koncentracji uwagi](service-focus-mode.md)
* [Używanie zakładek w celu udostępniania szczegółowych informacji i tworzenia historii w usłudze Power BI](desktop-bookmarks.md)
