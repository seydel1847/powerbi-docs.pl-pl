---
title: Ustawienie Przyjmij integralność referencyjną w programie Power BI Desktop
description: Korzystając z zapytań bezpośrednich, dowiedz się, jak w programie Power BI Desktop przyjmować integralność referencyjną
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
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 9e65546296b4afcb97deae4f2f417cdc517a9b17
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="assume-referential-integrity-settings-in-power-bi-desktop"></a>Ustawienie Przyjmij integralność referencyjną w programie Power BI Desktop
Podczas łączenia się ze źródłem danych za pomocą **zapytania bezpośredniego**, możesz użyć opcji **Przyjmij integralność referencyjną**, aby umożliwić wykonywanie wydajniejszych zapytań kierowanych do źródła danych. Ta funkcja ma kilka wymagań co do danych bazowych i jest dostępna tylko podczas korzystania z **zapytań bezpośrednich**.

Ustawienie **Przyjmij integralność referencyjną** umożliwia zapytaniom kierowanym do źródła danych na stosowanie instrukcji **INNER JOIN** zamiast **OUTER JOIN**, co zwiększa ich wydajność.

![](media/desktop-assume-referential-integrity/assume-referential-integrity_1.png)

## <a name="requirements-for-using-assume-referential-integrity"></a>Wymagania dotyczące korzystania z ustawienia Przyjmij integralność referencyjną
To jest ustawienie zaawansowane i jest włączone tylko podczas łączenia się z danymi za pomocą **zapytania bezpośredniego**. Następujące wymagania są niezbędne, aby ustawienie **Przyjmij integralność referencyjną** działało poprawnie:

* Dane w kolumnie **Od** w relacji nigdy nie mają wartości *Null* ani nie są *puste*.
* Dla każdej wartości w kolumnie **Od** istnieje odpowiadająca wartość w kolumnie **Do**.

W tym kontekście kolumna **Od** jest stroną *Wiele* w relacji *jeden do wielu* lub jest kolumną w pierwszej tabeli w relacji *jeden do jednego*.

## <a name="example-of-using-assume-referential-integrity"></a>Przykład użycia ustawienia Przyjmij integralność referencyjną
W poniższym przykładzie pokazano, jak ustawienie **Przyjmij integralność referencyjną** działa, gdy jest używane w połączeniach danych. Przykład łączy się ze źródłem danych zawierającym tabele **Orders**, **Products** i **Depots**.

1. Na następującej ilustracji z tabelami **Orders** i **Products** zwróć uwagę na istnienie integralności referencyjnej między kolumnami **Orders[ProductID]** i **Products[ProductID]**. Kolumna **[ProductID]** w tabeli **Orders** nigdy nie zawiera wartości *Null*, a każda wartość pojawia się także w tabeli **Products**. Dlatego ustawienie **Przyjmij integralność referencyjną** powinno zostać ustawione w celu uzyskania wydajniejszych zapytań (jego zastosowanie nie powoduje zmian wartości pokazywanych na wizualizacjach).
   
   ![](media/desktop-assume-referential-integrity/assume-referential-integrity_2.png)
2. Na następnej ilustracji zwróć uwagę na to, że nie istnieje integralność referencyjna między kolumną **Orders[DepotID]** i kolumną **Depots[DepotID]**, ponieważ w kolumnie **DepotID** pojawia się wartość *Null* dla niektórych wartości *Orders*. W efekcie ustawienia **Przyjmij integralność referencyjną** *nie powinno* się ustawiać.
   
   ![](media/desktop-assume-referential-integrity/assume-referential-integrity_3.png)
3. Między kolumnami **Orders[CustomerID]** i **Customers[CustID]** w następujących tabelach nie istnieje integralność referencyjna. Kolumna **CustomerID** zawiera wartości (w tym przypadku *CustX*), które nie istnieją w kolumnie *Customers*. W efekcie ustawienia **Przyjmij integralność referencyjną** *nie powinno* się ustawiać.
   
   ![](media/desktop-assume-referential-integrity/assume-referential-integrity_4.png)

## <a name="setting-assume-referential-integrity"></a>Ustawienie Przyjmij integralność referencyjną
Aby włączyć tę funkcję, zaznacz pole wyboru obok tekstu **Przyjmij integralność referencyjną**, jak pokazano na poniższej ilustracji.

![](media/desktop-assume-referential-integrity/assume-referential-integrity_1.png)

Gdy ustawienie jest zaznaczone, jest weryfikowane względem danych w celu upewnienia się, że nie istnieją wiersze o wartości *Null* ani niedopasowane wiersze. *Jednak* w sytuacjach, gdy istnieje bardzo duża ilość danych, weryfikacja nie gwarantuje nieistnienia problemów z integralnością referencyjną.

Dodatkowo weryfikacja następuje w trakcie edytowania relacji i *nie odzwierciedla* żadnych kolejnych zmian w danych.

## <a name="what-happens-if-you-incorrectly-set-assume-referential-integrity"></a>Co się stanie, jeśli niepoprawnie ustawisz opcję Przyjmij integralność referencyjną?
Włączenie ustawienia **Przyjmij integralność referencyjną** przy istniejących problemach z integralnością referencyjną danych nie spowoduje błędów. Spowoduje jednak pojawienie się pewnych niespójności w danych. Na przykład w przypadku relacji do tabeli **Depots** opisanej powyżej efekt byłby następujący:

* Wizualizacja pokazująca sumę wartości *Order Qty* pokazywałaby wartość 40.
* Wizualizacja pokazująca wartość *Order Qty by Depot City* pokazywałaby łączną wartość wynoszącą tylko *30*, ponieważ nie uwzględniałaby zamówienia Order z identyfikatorem równym 1, dla którego kolumna **DepotID** zawiera wartość *Null*.

## <a name="next-steps"></a>Następne kroki
Dowiedz się więcej na temat [zapytań bezpośrednich](desktop-use-directquery.md)

Uzyskaj więcej informacji o [relacjach w usłudze Power BI](desktop-create-and-manage-relationships.md)

Dowiedz się więcej na temat [widoku relacji w programie Power BI Desktop](desktop-relationship-view.md).

