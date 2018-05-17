---
title: Widok relacji w programie Power BI Desktop
description: Widok relacji w programie Power BI Desktop
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
ms.openlocfilehash: 310babc105289e747a885f8809bfdf0d494fa9b2
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="relationship-view-in-power-bi-desktop"></a>Widok relacji w programie Power BI Desktop
W **widoku relacji** są wyświetlane wszystkie tabele, kolumny i relacje w modelu. Może to być szczególnie przydatne, gdy model zawiera złożone relacje między wieloma tabelami.

Spójrzmy na przykład.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  Ikona Widok relacji — Kliknij, aby wyświetlić model w widoku relacji.

**B.** Relacja — Możesz zatrzymać kursor na relacji, aby wyświetlić używane kolumny. Kliknij dwukrotnie relację, aby otworzyć ją w oknie dialogowym **Edytowanie relacji**. 

Na powyższej ilustracji możesz zobaczyć, że w tabeli *Stores* znajduje się kolumna *StoreKey* powiązana z tabelą *Sales*, która również zawiera kolumnę *StoreKey*. Widzimy, że jest to relacja *Wiele do jednego* (\*:1), a ikona pośrodku linii pokazuje, że kierunek filtra krzyżowego jest ustawiony na *Oba*. Strzałka na ikonie pokazuje kierunek przepływu kontekstu filtru.

Aby dowiedzieć się więcej na temat relacji, zobacz [Tworzenie relacji i zarządzanie nimi w programie Power BI Desktop](desktop-create-and-manage-relationships.md).

