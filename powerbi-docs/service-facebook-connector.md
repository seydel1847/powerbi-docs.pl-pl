---
title: 'Usługa innego dostawcy: łącznik serwisu Facebook dla programu Power BI Desktop'
description: 'Usługa innego dostawcy: łącznik serwisu Facebook dla programu Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 02/22/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6e33e1a27903cc3fbce5c3f504287fa96dbf8305
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Łącznik serwisu Facebook dla programu Power BI Desktop
Łącznik serwisu Facebook w programie **Power BI Desktop** jest zależny od interfejsu API Graph serwisu Facebook. Oznacza to, że funkcje i dostępność mogą z czasem ulec zmianie.

Możesz zapoznać się z [samouczkiem dotyczącym łącznika serwisu Facebook dla programu Power BI Desktop](desktop-tutorial-facebook-analytics.md).

Wersja 1.0 interfejsu API Graph serwisu Facebook została wycofana 30 <sup>kwietnia</sup> 2015 r. Usługa Power BI korzysta z interfejsu API Graph na zapleczu łącznika serwisu Facebook, co umożliwia nawiązanie połączenia z danymi i analizowanie ich.

Zapytania, które zostały utworzone przed 30 <sup>kwietnia</sup> 2015 r., mogą nie zwracać danych lub zwracać ich mniejszą ilość. Po 30 kwietnia <sup></sup>2015 r. usługa Power BI korzysta z interfejsu Facebook API w wersji 2.8. Jeśli zapytanie zostało utworzone przed 30 kwietnia 2015 r. i nie było używane od tego czasu, prawdopodobnie należy uwierzytelnić się ponownie, aby zatwierdzić nowy zestaw uprawnień, o które poprosimy.

Staramy się wydawać aktualizacje z zachowaniem zgodności wprowadzanych zmian, mimo to zmiany interfejsu API mogą mieć wpływ na wyniki generowanych zapytań. W niektórych przypadkach określone zapytania mogą nie być już dłużej obsługiwane. Ze względu na tę zależność firma Microsoft nie może zagwarantować wyników zapytań przy korzystaniu z tego łącznika.

Więcej informacji o zmianach w interfejsie Facebook API jest dostępnych [tutaj](https://developers.facebook.com/docs/apps/changelog#v2_0).

