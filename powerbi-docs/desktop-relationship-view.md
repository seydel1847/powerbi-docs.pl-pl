---
title: Widok relacji w programie Power BI Desktop
description: Widok relacji w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 178f3cd9015af503ff12875548822ba1ab5365c3
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54272771"
---
# <a name="relationship-view-in-power-bi-desktop"></a>Widok relacji w programie Power BI Desktop
W **widoku relacji** są wyświetlane wszystkie tabele, kolumny i relacje w modelu. Może to być szczególnie przydatne, gdy model zawiera złożone relacje między wieloma tabelami.

Spójrzmy na przykład.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  Ikona Widok relacji — Kliknij, aby wyświetlić model w widoku relacji.

**B.** Relacja — Możesz zatrzymać kursor na relacji, aby wyświetlić używane kolumny. Kliknij dwukrotnie relację, aby otworzyć ją w oknie dialogowym **Edytowanie relacji**. 

Na powyższej ilustracji możesz zobaczyć, że w tabeli *Stores* znajduje się kolumna *StoreKey* powiązana z tabelą *Sales*, która również zawiera kolumnę *StoreKey*. Widzimy, że jest to relacja *Wiele do jednego* (\*:1), a ikona pośrodku linii pokazuje, że kierunek filtra krzyżowego jest ustawiony na *Oba*. Strzałka na ikonie pokazuje kierunek przepływu kontekstu filtru.

Aby dowiedzieć się więcej na temat relacji, zobacz [Tworzenie relacji i zarządzanie nimi w programie Power BI Desktop](desktop-create-and-manage-relationships.md).

