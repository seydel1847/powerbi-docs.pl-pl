---
title: Przechwytywanie dodatkowych informacji diagnostycznych
description: Przechwytywanie dodatkowych informacji diagnostycznych
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 76860e740d43a1907692a7cd4fed1a6df68c93d4
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="capturing-additional-diagnostic-information"></a>Przechwytywanie dodatkowych informacji diagnostycznych
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Przechwytywanie dodatkowych informacji diagnostycznych dotyczących usługi Power BI
Instrukcje te zapewniają dwie potencjalne opcje ręcznego gromadzenia dodatkowych informacji diagnostycznych od internetowego klienta usługi Power BI.  Należy postępować zgodnie z tylko jedną z tych opcji.

## <a name="network-capture---edge--internet-explorer"></a>Przechwytywanie sieci — przeglądarki Edge i Internet Explorer
1. Przejdź do usługi [Power BI](https://app.powerbi.com) za pomocą przeglądarki Microsoft Edge lub Internet Explorer.
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

