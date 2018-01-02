---
title: Tagowanie pola kodu kreskowego w programie Power BI Desktop dla aplikacji mobilnych
description: "Gdy oznaczysz pole kodu kreskowego w modelu w programie Power BI Desktop, możesz automatycznie filtrować dane dotyczące kodów kreskowych w aplikacji Power BI na telefonie iPhone."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 07/18/2017
ms.author: maggies
ms.openlocfilehash: 029d93df808163ab5ff3015161121dafbbfa175d
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="tag-barcodes-in-power-bi-desktop-for-the-mobile-apps"></a>Tagowanie kodów kreskowych w programie Power BI Desktop dla aplikacji mobilnych
W programie Power BI Desktop możesz [skategoryzować dane](desktop-data-categorization.md) w kolumnie, aby poinformować program Power BI Desktop, jak ma traktować wartości w wizualizacjach w raporcie. Możesz także skategoryzować kolumnę jako **Kod kreskowy**. Gdy Ty lub Twoi współpracownicy [zeskanujecie kod kreskowy na produkcie za pomocą aplikacji Power BI](mobile-apps-scan-barcode-iphone.md) na telefonie iPhone, zostaną wyświetlone wszystkie raporty zawierające ten kod kreskowy. Po otwarciu raportu w aplikacji mobilnej usługa Power BI automatycznie przefiltruje raport, aby uzyskać dane związane z tym kodem kreskowym.

1. W programie Power BI Desktop przejdź do widoku danych.
2. Wybierz kolumnę z danymi kodu kreskowego. Zobacz listę [obsługiwanych formatów kodu kreskowego](#supported-barcode-formats) poniżej.
3. Na karcie **Modelowanie** wybierz pozycję **Kategoria danych** > **Kod kreskowy**.
   
    ![Lista kategorii danych](media/desktop-mobile-barcodes/power-bi-desktop-barcode.png)
4. W widoku raportu dodaj to pole do wizualizacji, które chcesz przefiltrować według kodu kreskowego.
5. Zapisz raport i opublikuj go w usłudze Power BI.

Teraz gdy otworzysz skaner w [aplikacji Power BI dla telefonu iPhone](mobile-ios-ipad-iphone-apps.md) i zeskanujesz kod kreskowy, zobaczysz ten raport na liście raportów. Po otwarciu raportu jego wizualizacje zostaną przefiltrowane według zeskanowanego kodu kreskowego produktu.

## <a name="supported-barcode-formats"></a>Obsługiwane formaty kodu kreskowego
Są to kody kreskowe rozpoznawane przez usługę Power BI, jeśli można oznaczyć je w raporcie usługi Power BI: 

* UPCECode 
* Code39Code  
* A39Mod43Code 
* EAN13Code 
* EAN8Code  
* 93Code  
* 128Code 
* PDF417Code 
* Interleaved2of5Code 
* ITF14Code 

## <a name="next-steps"></a>Następne kroki
* [Skanowanie kodu kreskowego z aplikacji Power BI na telefonie iPhone](mobile-apps-scan-barcode-iphone.md)
* [Problem z skanowaniem kodów kreskowych na telefonie iPhone](mobile-apps-scan-barcode-iphone.md#issues-with-scanning-a-barcode)
* [Kategoryzacja danych w programie Power BI Desktop](desktop-data-categorization.md)  
* Masz pytania? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

