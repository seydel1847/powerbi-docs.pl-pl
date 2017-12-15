---
title: "Usługa innego dostawcy: łącznik serwisu Facebook dla programu Power BI Desktop"
description: "Usługa innego dostawcy: łącznik serwisu Facebook dla programu Power BI Desktop"
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
ms.date: 07/20/2017
ms.author: davidi
ms.openlocfilehash: ee79f7a677f7f64b05df83b09ffba02978e1ac62
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Łącznik serwisu Facebook dla programu Power BI Desktop
Łącznik serwisu Facebook w programie **Power BI Desktop** jest zależny od interfejsu API Graph serwisu Facebook. Oznacza to, że funkcje i dostępność mogą z czasem ulec zmianie.

Możesz zapoznać się z [samouczkiem dotyczącym łącznika serwisu Facebook dla programu Power BI Desktop](desktop-tutorial-facebook-analytics.md).

Wersja 1.0 interfejsu API Graph serwisu Facebook została wycofana 30 <sup>kwietnia</sup> 2015 r. Usługa Power BI korzysta z interfejsu API Graph na zapleczu łącznika serwisu Facebook, co umożliwia nawiązanie połączenia z danymi i analizowanie ich.

Zapytania, które zostały utworzone przed 30 <sup>kwietnia</sup> 2015 r., mogą nie zwracać danych lub zwracać ich mniejszą ilość. Po 30 <sup>kwietnia</sup> 2015 r. usługa Power BI korzysta z interfejsu Facebook API w wersji 2.2. Jeśli zapytanie zostało utworzone przed 30 kwietnia 2015 r. i nie było używane od tego czasu, prawdopodobnie należy uwierzytelnić się ponownie, aby zatwierdzić nowy zestaw uprawnień, o które poprosimy.

Staramy się wydawać aktualizacje z zachowaniem zgodności wprowadzanych zmian, mimo to zmiany interfejsu API mogą mieć wpływ na wyniki generowanych zapytań. W niektórych przypadkach określone zapytania mogą nie być już dłużej obsługiwane. Ze względu na tę zależność firma Microsoft nie może zagwarantować wyników zapytań przy korzystaniu z tego łącznika.

Więcej informacji o zmianach w interfejsie Facebook API jest dostępnych [tutaj](https://developers.facebook.com/docs/apps/changelog#v2_0).

