---
title: Importowanie i wyświetlanie wskaźników KPI w usłudze Power BI
description: Importowanie i wyświetlanie wskaźników KPI
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: deb6da926cafd78bfc12931ee731a6e2b2d6d44d
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="import-and-display-kpis-in-power-bi"></a>Importowanie i wyświetlanie wskaźników KPI w usłudze Power BI
Za pomocą programu **Power BI Desktop** można importować i wyświetlać wskaźniki KPI w tabelach, macierzach oraz kartach.

Wykonaj następujące kroki, aby zaimportować i wyświetlić wskaźniki KPI.

1. Zacznij od skoroszytu programu Excel zawierającego model Power Pivot i wskaźniki KPI. W tym ćwiczeniu używany jest skoroszyt o nazwie *KPIs*.

1. Zaimportuj skoroszyt program Excel do usługi Power BI przy użyciu pozycji **Plik -> Importuj -> Zawartość skoroszytu programu Excel**. Możesz też [dowiedzieć się, jak importować skoroszyty](desktop-import-excel-workbooks.md). 

1. Po zaimportowaniu do usługi Power BI wskaźnik KPI zostanie wyświetlony w okienku **Pola** jako oznaczony ikoną ![sygnalizacji ulicznej](media/desktop-import-and-display-kpis/traffic.png). Aby użyć wskaźnika KPI w raporcie, rozwiń jego zawartość, ujawniając pola **Wartość**, **Cel** i **Stan**.

    ![](media/desktop-import-and-display-kpis/desktoppreviewfeatureon2.png)

1. Zaimportowanych wskaźników KPI najlepiej używać w standardowych typach wizualizacji, takich jak typ **Tabela**. Usługa Power BI oferuje również typ wizualizacji **Wskaźnik KPI**, który powinien być używany tylko do tworzenia nowych kluczowych wskaźników wydajności.
   
    ![](media/desktop-import-and-display-kpis/desktoppreviewfeatureon3.png)

To już wszystko. Wskaźników KPI można użyć do wyróżnienia trendów, postępu lub innych istotnych wskaźników.
