---
title: 'Usługa innej firmy: Łącznik serwisu Facebook dla programu Power BI Desktop'
description: 'Usługa innej firmy: Łącznik serwisu Facebook dla programu Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a8b37606b602a24aa4a0995e138a52a86e0f945c
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54295649"
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Łącznik serwisu Facebook dla programu Power BI Desktop
Łącznik serwisu Facebook w programie **Power BI Desktop** jest zależny od interfejsu API Graph serwisu Facebook. Oznacza to, że funkcje i dostępność mogą z czasem ulec zmianie.

Możesz zapoznać się z [samouczkiem dotyczącym łącznika serwisu Facebook dla programu Power BI Desktop](desktop-tutorial-facebook-analytics.md).

Wersja 1.0 interfejsu API Graph serwisu Facebook została wycofana 30 <sup>kwietnia</sup> 2015 r. Usługa Power BI korzysta z interfejsu API Graph na zapleczu łącznika serwisu Facebook, co umożliwia nawiązanie połączenia z danymi i analizowanie ich.

Zapytania, które zostały utworzone przed 30 <sup>kwietnia</sup> 2015 r., mogą nie zwracać danych lub zwracać ich mniejszą ilość. Po 30 kwietnia <sup></sup>2015 r. usługa Power BI korzysta z interfejsu Facebook API w wersji 2.8. Jeśli zapytanie zostało utworzone przed 30 kwietnia 2015 r. i nie było używane od tego czasu, prawdopodobnie należy uwierzytelnić się ponownie, aby zatwierdzić nowy zestaw uprawnień, o które poprosimy.

Staramy się wydawać aktualizacje z zachowaniem zgodności wprowadzanych zmian, mimo to zmiany interfejsu API mogą mieć wpływ na wyniki generowanych zapytań. W niektórych przypadkach określone zapytania mogą nie być już dłużej obsługiwane. Ze względu na tę zależność firma Microsoft nie może zagwarantować wyników zapytań przy korzystaniu z tego łącznika.

Więcej informacji o zmianach w interfejsie Facebook API jest dostępnych [tutaj](https://developers.facebook.com/docs/apps/changelog#v2_0).

