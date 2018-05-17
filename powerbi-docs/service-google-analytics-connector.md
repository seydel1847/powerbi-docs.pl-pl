---
title: 'Usługa innego dostawcy: łącznik usługi Google Analytics dla programu Power BI Desktop'
description: 'Usługa innego dostawcy: łącznik usługi Google Analytics dla programu Power BI Desktop'
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
LocalizationGroup: Connect to data
ms.openlocfilehash: 9ed35befba78a99f4923eda3adb83414a3f197dc
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="google-analytics-connector-for-power-bi-desktop"></a>Łącznik usługi Google Analytics dla programu Power BI Desktop
> [!NOTE]
> Pakiet zawartości usługi Google Analytics oraz łącznik dla programu Power BI Desktop korzystają z interfejsu Core Reporting API usługi Google Analytics. Oznacza to, że funkcje i dostępność mogą z czasem ulec zmianie.
> 
> 

Nawiązanie połączenia z danymi usługi Google Analytics jest możliwe za pomocą łącznika **Google Analytics**. Aby nawiązać połączenie, wykonaj następujące kroki:

1. W programie **Power BI Desktop** wybierz polecenie **Pobierz dane** na karcie **Narzędzia główne** wstążki.
2. W oknie **Pobieranie danych** wybierz pozycję **Usługi online** z kategorii w lewym okienku.
3. Wybierz pozycję **Google Analytics** z opcji w okienku po prawej stronie.
4. W dolnej części okna wybierz przycisk **Połącz**.  
   ![](media/service-google-analytics-connector/tps_googleanalytics_1.png)

Zostanie wyświetlone okno dialogowe zawierające wyjaśnienie, że łącznik jest usługą innej firmy, ostrzeżenie, że funkcje i dostępność mogą z czasem ulec zmianie, a także inne wyjaśnienia.  
![](media/service-google-analytics-connector/tps_googleanalytics_2.png)

Po naciśnięciu przycisku **Kontynuuj** zostanie wyświetlony monit o zalogowanie się do usługi Google Analytics.  
![](media/service-google-analytics-connector/tps_googleanalytics_3.png)

Po wprowadzeniu poświadczeń zostanie wyświetlony monit, że usługa Power BI chce uzyskać dostęp w trybie offline. Oto jak uzyskać dostęp do danych usługi Google Analytics za pomocą programu **Power BI Desktop**.  

Po zaakceptowaniu program **Power BI Desktop** wyświetli informację, że użytkownik jest już zalogowany.  
![](media/service-google-analytics-connector/tps_googleanalytics_5.png)

Wybierz przycisk **Połącz**, aby program **Power BI Desktop** nawiązał połączenie z danymi usługi Google Analytics i załadował je.  
![](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>Zmiany dotyczące interfejsu API
Staramy się wydawać aktualizacje z zachowaniem zgodności wprowadzanych zmian, mimo to zmiany interfejsu API mogą mieć wpływ na wyniki generowanych zapytań. W niektórych przypadkach określone zapytania mogą nie być już dłużej obsługiwane. Ze względu na tę zależność firma Microsoft nie może zagwarantować wyników zapytań przy korzystaniu z tego łącznika.

Więcej informacji na temat zmian interfejsu API Google Analytics można znaleźć w jego [dzienniku zmian](https://developers.google.com/analytics/devguides/changelog).

