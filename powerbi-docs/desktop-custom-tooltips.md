---
title: Dostosowywanie etykietek narzędzi w programie Power BI Desktop
description: Tworzenie niestandardowych etykietek narzędzi dla wizualizacji przy użyciu przeciągania i upuszczania
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 5dfd22f8b45253ece4ed8f699adec9abcaa1a8ed
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721161"
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>Dostosowywanie etykietek narzędzi w programie Power BI Desktop
Etykietki narzędzi to elegancki sposób zapewniania większej ilości informacji kontekstowych i szczegółowych dotyczących punktów danych w wizualizacji. Na poniższej ilustracji przedstawiono etykietkę narzędzia zastosowaną względem wykresu w programie Power BI Desktop.

![Domyślna etykietka narzędzia](media/desktop-custom-tooltips/custom-tooltips-1.png)

Po utworzeniu wizualizacji w domyślnej etykietce narzędzia wyświetlana jest wartość i kategoria punktu danych. Możliwość edytowania informacji zawartych na etykietce narzędzia może być przydatna w wielu sytuacjach i pozwala na przekazanie dodatkowego kontekstu i dodatkowych informacji użytkownikom, którzy wyświetlają wizualizację. Niestandardowe etykietki narzędzi umożliwiają określanie dodatkowych punktów danych, które są wyświetlane jako część etykietki narzędzia.

## <a name="how-to-customize-tooltips"></a>Jak dostosować etykietki narzędzi
Aby utworzyć niestandardową etykietkę narzędzia, w obszarze **Pola** okienka **Wizualizacje** po prostu przeciągnij pole do zasobnika **Etykietki narzędzi** pokazanego na poniższym obrazie. Poniższa ilustracja przedstawia dwa pola umieszczone w zasobniku **Etykietki narzędzi**.

![Dodawanie pól etykietki narzędzia](media/desktop-custom-tooltips/custom-tooltips-2.png)

Po dodaniu etykietek narzędzi do obszaru pól zatrzymanie wskaźnika myszy na punkcie danych na wizualizacji spowoduje wyświetlenie wartości dla tych pól w etykietce narzędzia.

![Niestandardowa etykietka narzędzia](media/desktop-custom-tooltips/custom-tooltips-3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>Dostosowywanie etykietek narzędzi za pomocą agregacji lub przy użyciu szybkich obliczeń
Dostosowywanie etykietki narzędzia można kontynuować, wybierając funkcję agregacji lub *Szybkie obliczenie* poprzez wybranie strzałki obok pola w zasobniku **Etykietki narzędzi** i wybranie odpowiedniej opcji.

![Etykietka narzędzia z szybkim obliczeniem](media/desktop-custom-tooltips/custom-tooltips-4.png)

Istnieje wiele sposobów dostosowywania **etykietek narzędzi** przy użyciu dowolnych pól z zestawu danych celem przekazania skróconych informacji i najważniejszych szczegółów użytkownikom, którzy wyświetlają raporty lub pulpity nawigacyjne.

