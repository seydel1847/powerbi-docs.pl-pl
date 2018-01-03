---
title: "Dostosowywanie etykietek narzędzi w programie Power BI Desktop"
description: "Tworzenie niestandardowych etykietek narzędzi dla wizualizacji przy użyciu przeciągania i upuszczania"
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: a159dffc439f756741ca6782a95e0badd3cc0588
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2017
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>Dostosowywanie etykietek narzędzi w programie Power BI Desktop
Etykietki narzędzi to elegancki sposób zapewniania większej ilości informacji kontekstowych i szczegółowych dotyczących punktów danych w wizualizacji. Na poniższej ilustracji przedstawiono etykietkę narzędzia zastosowaną względem wykresu w programie Power BI Desktop.

![](media/desktop-custom-tooltips/custom-tooltips_1.png)

Po utworzeniu wizualizacji w domyślnej etykietce narzędzia wyświetlana jest wartość i kategoria punktu danych. Możliwość edytowania informacji zawartych na etykietce narzędzia może być przydatna w wielu sytuacjach i pozwala na przekazanie dodatkowego kontekstu i dodatkowych informacji użytkownikom, którzy wyświetlają wizualizację. Niestandardowe etykietki narzędzi umożliwiają określanie dodatkowych punktów danych, które są wyświetlane jako część etykietki narzędzia.

## <a name="how-to-customize-tooltips"></a>Jak dostosować etykietki narzędzi
Aby utworzyć niestandardową etykietkę narzędzia, w obszarze **Pola** okienka **Wizualizacje** po prostu przeciągnij pole do zasobnika **Etykietki narzędzi** pokazanego na poniższym obrazie. Poniższa ilustracja przedstawia cztery pola umieszczone w zasobniku **Etykietki narzędzi**.

![](media/desktop-custom-tooltips/custom-tooltips_2.png)

Po dodaniu etykietek narzędzi do obszaru pól najechanie kursorem na punkt danych na wizualizacji spowoduje wyświetlenie wartości dla tych pól w etykietce narzędzia.

![](media/desktop-custom-tooltips/custom-tooltips_3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>Dostosowywanie etykietek narzędzi za pomocą agregacji lub przy użyciu szybkich obliczeń
Dostosowywanie etykietki narzędzia można kontynuować, wybierając funkcję agregacji lub *Szybkie obliczenie* poprzez wybranie strzałki obok pola w zasobniku **Etykietki narzędzi** i wybranie odpowiedniej opcji.

![](media/desktop-custom-tooltips/custom-tooltips_4.png)

Istnieje wiele sposobów dostosowywania **etykietek narzędzi** przy użyciu dowolnych pól z zestawu danych celem przekazania skróconych informacji i najważniejszych szczegółów użytkownikom, którzy wyświetlają raporty lub pulpity nawigacyjne.
