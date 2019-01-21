---
title: Przechowywanie wersji modeli danych usługi Power BI
description: Model danych ujawniany przez usługę OData
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 75ef3116facc2784dfe9f343261db3a00f6f8300
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54286432"
---
# <a name="data-model-versioning"></a>Przechowywanie wersji modelu danych

Model danych ujawniany przez usługę OData, taki jak model danych usługi Power BI, definiuje kontrakt między usługą OData i jej klientami. Usługi mogą rozszerzać model tylko do takiego stopnia, aby nie przerywać działania istniejących klientów. Zmiany powodujące niezgodność, takie jak usuwanie właściwości lub zmienianie typu istniejących właściwości, wymagają udostępnienia nowej wersji usługi pod innym głównym adresem URL usługi dla nowego modelu.  
  
Następujące dodatki do modelu danych są uznawane za bezpieczne i nie wymagają przechowywania wersji punktu wejścia usług.  
  
* Dodawanie właściwości, która może mieć wartość null lub ma wartość domyślną; jeśli ma ona taką samą nazwę jak istniejąca właściwość dynamiczna, musi być tego samego typu (lub typu bazowego) co istniejąca właściwość dynamiczna  
* Dodawanie właściwości nawigacji, która może mieć wartość null lub wartość kolekcji; jeśli ma ona taką samą nazwę jak istniejąca właściwość dynamiczna nawigacji, musi być tego samego typu (lub typu bazowego) co istniejąca właściwość dynamiczna nawigacji  
* Dodawanie nowego typu jednostki do modelu  
* Dodawanie nowego typu złożonego do modelu  
* Dodawanie nowego zestawu jednostek  
* Dodawanie nowego pojedynczego wystąpienia  
* Dodawanie akcji, funkcji, importu akcji lub importu funkcji
* Dodawanie parametru akcji dopuszczającego wartość null  
* Dodawanie wyliczenia lub definicji typu  
* Dodawanie dowolnych adnotacji do elementu modelu, w przypadku którego do prawidłowej interakcji z usługą nie jest wymagane zrozumienie przez klienta  
  
Klienci ***POWINNI*** być przygotowywani na to, że usługi będą wprowadzać takie przyrostowe zmiany w modelu. W szczególności klienci powinni być przygotowani na odbieranie właściwości i typów pochodnych, które wcześniej nie zostały zdefiniowane przez usługę.  
  
Usługi ***NIE POWINNY*** zmieniać modelu danych w zależności od uwierzytelnionego użytkownika. Jeśli model danych zależy od użytkownika lub grupy użytkowników, wszystkie zmiany MUSZĄ być bezpieczne (zgodnie z definicją podaną w tej sekcji) w przypadku porównywania pełnego modelu do modelu widocznego dla użytkowników z ograniczonymi autoryzacjami.  
  
Aby uzyskać więcej informacji o standardach modelu danych OData, zobacz [OData Version 4.0 Part 1: Protocol Plus Errata 02](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html) (Protokół OData w wersji 4.0, część 1: protokół i errata 02).  
  
## <a name="see-also"></a>Zobacz także
[Omówienie interfejsu API REST usługi Power BI](https://docs.microsoft.com/rest/api/power-bi/)  