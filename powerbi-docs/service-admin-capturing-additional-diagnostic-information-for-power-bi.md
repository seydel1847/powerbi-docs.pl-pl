---
title: Przechwytywanie dodatkowych informacji diagnostycznych
description: Przechwytywanie dodatkowych informacji diagnostycznych
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 06/28/2017
ms.author: maghan
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 65954c19087e9c9968c549f610d4e36e942e3206
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="capturing-additional-diagnostic-information"></a>Przechwytywanie dodatkowych informacji diagnostycznych
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Przechwytywanie dodatkowych informacji diagnostycznych dotyczących usługi Power BI
Instrukcje te zapewniają dwie potencjalne opcje ręcznego gromadzenia dodatkowych informacji diagnostycznych od internetowego klienta usługi Power BI.  Należy postępować zgodnie z tylko jedną z tych opcji.

## <a name="network-capture---edge--internet-explorer"></a>Przechwytywanie sieci — przeglądarki Edge i Internet Explorer
1. Przejdź do usługi [Power BI](https://app.powerbi.com) za pomocą przeglądarki Edge lub Internet Explorer.
2. Otwórz narzędzia deweloperskie przeglądarki Edge, naciskając klawisz F12.
3. Spowoduje to wyświetlenie okna Narzędzia dla deweloperów: 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. Przejdź do karty Sieć. Wyświetlony zostanie ruch, który został już przechwycony. 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. Możesz wybrać w oknie i odtworzyć dowolny problem, który mógł wystąpić. Okno narzędzi dla deweloperów możesz w każdej chwili ukryć i pokazać podczas sesji, naciskając klawisz F12.
6. Aby zatrzymać przechwytywanie, możesz wybrać czerwony kwadrat na karcie sieciowej w obszarze narzędzi dla deweloperów.
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. Wybierz ikonę dyskietki, aby **wyeksportować jako HAR**
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. Podaj nazwę pliku i zapisz plik HAR.
   
    Plik HAR będzie zawierał wszystkie informacje dotyczące żądań sieci między oknem przeglądarki i usługą Power BI.  Obejmuje to identyfikatory działań dla każdego żądania, dokładny znacznik czasu dla każdego żądania oraz wszelkie informacje o błędzie zwracane do klienta.  Ten ślad zawiera również dane używane do wypełniania elementów wizualnych wyświetlonych na ekranie.
9. Możesz udostępnić pliku HAR do obsługi podczas przeglądu.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

