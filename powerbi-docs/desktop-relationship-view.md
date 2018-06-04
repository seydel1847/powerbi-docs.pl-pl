---
title: Widok relacji w programie Power BI Desktop
description: Widok relacji w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 58886dc1ae5490113d4d0ba9af00d16aefecbe71
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34287031"
---
# <a name="relationship-view-in-power-bi-desktop"></a>Widok relacji w programie Power BI Desktop
W **widoku relacji** są wyświetlane wszystkie tabele, kolumny i relacje w modelu. Może to być szczególnie przydatne, gdy model zawiera złożone relacje między wieloma tabelami.

Spójrzmy na przykład.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  Ikona Widok relacji — Kliknij, aby wyświetlić model w widoku relacji.

**B.** Relacja — Możesz zatrzymać kursor na relacji, aby wyświetlić używane kolumny. Kliknij dwukrotnie relację, aby otworzyć ją w oknie dialogowym **Edytowanie relacji**. 

Na powyższej ilustracji możesz zobaczyć, że w tabeli *Stores* znajduje się kolumna *StoreKey* powiązana z tabelą *Sales*, która również zawiera kolumnę *StoreKey*. Widzimy, że jest to relacja *Wiele do jednego* (\*:1), a ikona pośrodku linii pokazuje, że kierunek filtra krzyżowego jest ustawiony na *Oba*. Strzałka na ikonie pokazuje kierunek przepływu kontekstu filtru.

Aby dowiedzieć się więcej na temat relacji, zobacz [Tworzenie relacji i zarządzanie nimi w programie Power BI Desktop](desktop-create-and-manage-relationships.md).

