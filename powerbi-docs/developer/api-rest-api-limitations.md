---
title: Ograniczenia interfejsu API REST usługi Power BI
description: 'Interfejs API REST usługi Power BI ma następujące ograniczenia:'
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: df17563d384359fe33123ed87743754bb33bf04d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277986"
---
# <a name="power-bi-rest-api-limitations"></a>Ograniczenia interfejsu API REST usługi Power BI  
  
**Dotyczące wierszy POST**  
  
* Maksymalnie 75 kolumn
* Maksymalnie 75 tabel
* Maksymalnie 10 000 wierszy na pojedyncze żądanie wierszy POST  
* 1 000 000 dodanych wierszy na godzinę na zestaw danych  
* Maksymalnie 5 oczekujących żądań wierszy POST na zestaw danych  
* 120 żądań wierszy POST na minutę na zestaw danych
* Jeśli tabela ma co najmniej 250 000 wierszy, 120 żądań wierszy POST na godzinę na zestaw danych    
* Maksymalnie 200 000 przechowywanych wierszy na tabelę w zestawie danych FIFO  
* Maksymalnie 5 000 000 przechowywanych wierszy na tabelę w zestawie danych typu „brak zasad przechowywania”  
* 4000 znaków na wartość w kolumnie typu ciąg w operacji dotyczącej wierszy POST
  
## <a name="see-also"></a>Zobacz także

[Azure AD service limits and restrictions](https://docs.microsoft.com/azure/active-directory/active-directory-service-limits-restrictions)  (Limity i ograniczenia usługi Azure AD)  
[Omówienie interfejsu API REST usługi Power BI](https://docs.microsoft.com/rest/api/power-bi/)