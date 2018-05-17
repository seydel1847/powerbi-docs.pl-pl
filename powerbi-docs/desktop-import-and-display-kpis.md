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
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 5cb7370942cdd4b50c8315a075eb7a178b05a692
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
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
