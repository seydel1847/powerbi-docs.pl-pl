---
title: Tagowanie pola kodu kreskowego w programie Power BI Desktop dla aplikacji mobilnych
description: Gdy oznaczysz pole kodu kreskowego w modelu w programie Power BI Desktop, możesz automatycznie filtrować dane dotyczące kodów kreskowych w aplikacji Power BI na telefonie iPhone.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/16/2018
ms.author: maggies
LocalizationGroup: Model your data
ms.openlocfilehash: 584947dcd92078ea025468f5a38fc7fed3e2616a
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54289905"
---
# <a name="tag-barcodes-in-power-bi-desktop-for-the-mobile-apps"></a>Tagowanie kodów kreskowych w programie Power BI Desktop dla aplikacji mobilnych
W programie Power BI Desktop możesz [skategoryzować dane](desktop-data-categorization.md) w kolumnie, aby poinformować program Power BI Desktop, jak ma traktować wartości w wizualizacjach w raporcie. Możesz także skategoryzować kolumnę jako **Kod kreskowy**. Gdy Ty lub Twoi współpracownicy [zeskanujecie kod kreskowy na produkcie za pomocą aplikacji Power BI](consumer/mobile/mobile-apps-scan-barcode-iphone.md) na telefonie iPhone, zostaną wyświetlone wszystkie raporty zawierające ten kod kreskowy. Po otwarciu raportu w aplikacji mobilnej usługa Power BI automatycznie przefiltruje raport, aby uzyskać dane związane z tym kodem kreskowym.

1. W programie Power BI Desktop przejdź do widoku danych.
2. Wybierz kolumnę z danymi kodu kreskowego. Zobacz listę [obsługiwanych formatów kodu kreskowego](#supported-barcode-formats) poniżej.
3. Na karcie **Modelowanie** wybierz pozycję **Kategoria danych** > **Kod kreskowy**.
   
    ![Lista kategorii danych](media/desktop-mobile-barcodes/power-bi-desktop-barcode.png)
4. W widoku raportu dodaj to pole do wizualizacji, które chcesz przefiltrować według kodu kreskowego.
5. Zapisz raport i opublikuj go w usłudze Power BI.

Teraz gdy otworzysz skaner w [aplikacji Power BI dla telefonu iPhone](consumer/mobile/mobile-iphone-app-get-started.md) i zeskanujesz kod kreskowy, zobaczysz ten raport na liście raportów. Po otwarciu raportu jego wizualizacje zostaną przefiltrowane według zeskanowanego kodu kreskowego produktu.

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
* [Skanowanie kodu kreskowego z aplikacji Power BI na telefonie iPhone](consumer/mobile/mobile-apps-scan-barcode-iphone.md)
* [Problem z skanowaniem kodów kreskowych na telefonie iPhone](consumer/mobile/mobile-apps-scan-barcode-iphone.md#issues-with-scanning-a-barcode)
* [Kategoryzacja danych w programie Power BI Desktop](desktop-data-categorization.md)  
* Masz pytania? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

