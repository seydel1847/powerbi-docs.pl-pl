---
title: Gdzie znajduje się moja dzierżawa usługi Power BI?
description: Dowiedz się, gdzie znajduje się Twoja dzierżawa usługi Power BI i jak jest wybierana ta lokalizacja. Ważne jest, aby to zrozumieć, ponieważ może to wpływać na interakcje z usługą.
services: powerbi
documentationcenter: ''
author: mgblythe
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
ms.date: 08/10/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 22b5319cf95beb3ea4a4a498c7174a701e56fb95
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/08/2018
---
# <a name="where-is-my-power-bi-tenant-located"></a>Gdzie znajduje się moja dzierżawa usługi Power BI?
<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Dowiedz się, gdzie znajduje się Twoja dzierżawa usługi Power BI i jak jest wybierana ta lokalizacja. Ważne jest, aby to zrozumieć, ponieważ może to wpływać na interakcje z usługą.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>Jak ustalić, gdzie znajduje się Twoja dzierżawa usługi Power BI
Aby znaleźć region, gdzie znajduje się Twoja dzierżawa, możesz wykonać następujące czynności.

1. Wybierz znak **?** w usłudze Power BI.
2. Wybierz pozycję **Informacje o usłudze Power BI**.
3. Wyszukaj wartość obok pozycji **Twoje dane są przechowywane w**. Jest to region, w którym się znajdujesz.

![](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>Jak jest wybierany region danych
Region danych zależy od kraju, który został wybrany podczas pierwszego tworzenia dzierżawy. Dotyczy to logowania się do usługi Office 365, oprócz usługi Power BI, ponieważ te informacje są udostępnione. Jeśli jest to nowa dzierżawa, podczas tworzenia konta zostanie wyświetlona lista rozwijana krajów.

![](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Ten wybór jest podstawą ustalenia lokalizacji przechowywania danych. Usługa Power BI wybierze region danych najbliższy do tego wyboru.

> [!WARNING]
> Nie można zmienić tego wyboru!
> 
> 

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

