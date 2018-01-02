---
title: Widok relacji w programie Power BI Desktop
description: Widok relacji w programie Power BI Desktop
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
ms.openlocfilehash: aeb58b33d2496da3a05a0faf3882b235b3a6e54f
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2017
---
# <a name="relationship-view-in-power-bi-desktop"></a>Widok relacji w programie Power BI Desktop
W **widoku relacji** są wyświetlane wszystkie tabele, kolumny i relacje w modelu. Może to być szczególnie przydatne, gdy model zawiera złożone relacje między wieloma tabelami.

Spójrzmy na przykład.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  Ikona Widok relacji — Kliknij, aby wyświetlić model w widoku relacji.

**B.** Relacja — Możesz zatrzymać kursor na relacji, aby wyświetlić używane kolumny. Kliknij dwukrotnie relację, aby otworzyć ją w oknie dialogowym **Edytowanie relacji**. 

Na powyższej ilustracji możesz zobaczyć, że w tabeli *Stores* znajduje się kolumna *StoreKey* powiązana z tabelą *Sales*, która również zawiera kolumnę *StoreKey*. Widzimy, że jest to relacja *Wiele do jednego* (\*:1), a ikona pośrodku linii pokazuje, że kierunek filtra krzyżowego jest ustawiony na *Oba*. Strzałka na ikonie pokazuje kierunek przepływu kontekstu filtru.

Aby dowiedzieć się więcej na temat relacji, zobacz [Tworzenie relacji i zarządzanie nimi w programie Power BI Desktop](desktop-create-and-manage-relationships.md).

