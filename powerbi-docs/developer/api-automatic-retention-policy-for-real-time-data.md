---
title: Interfejsy API usługi Power BI używające zasad automatycznego przechowywania danych w czasie rzeczywistym
description: Dowiedz się więcej o zasadach automatycznego przechowywania w usłudze Power BI
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 9b5923c7bd92b1fe53ebb7ab9416aca8cece3cfa
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54294385"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Zasady automatycznego przechowywania danych w czasie rzeczywistym

Zasady automatycznego przechowywania w usłudze Power BI to parametr ciągu zapytania, który umożliwia domyślnym zasadom przechowywania automatyczne oczyszczanie starych danych przy jednoczesnym zachowaniu stałego przepływu nowych danych przesyłanych do pulpitu nawigacyjnego. Pierwsze zasady przechowywania noszą nazwę *Podstawowe, pierwszy na wejściu — pierwszy na wyjściu (FIFO)*. Po ich włączeniu dane są zbierane w tabeli do momentu osiągnięcia 200 000 wierszy. Gdy dane przekroczą 200 000 wierszy, najstarsze wiersze zostaną usunięte z zestawu danych. Te zasady obsługują od 200 000 do 210 000 wierszy zawierających tylko najnowsze dane.  
  
<center>

![zasady przechowywania](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Zasady przechowywania są włączane podczas tworzenia zestawów danych po raz pierwszy. W tym celu musisz tylko dodać parametr zapytania „defaultRetentionPolicy” do wywołania zestawów danych POST i ustawić go na *basicFIFO*.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}