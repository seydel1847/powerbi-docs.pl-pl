---
title: "Zapytanie bezpośrednie na platformie SAP HANA w usłudze Power BI"
description: "Zagadnienia dotyczące korzystania z zapytania bezpośredniego na platformie SAP HANA"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 2b2e59371c96928a2b7c6b23bd393a80ecc3041a
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="directquery-and-sap-hana"></a>Zapytanie bezpośrednie i platforma SAP HANA
Dzięki **zapytaniu bezpośredniemu** można połączyć się bezpośrednio ze źródłami danych platformy **SAP HANA**.

Podczas korzystania z platformy **SAP HANA** ważne jest, aby poznać niektóre aspekty traktowania połączeń z tą platformą. Ma to na celu spełnienie następujących warunków:

* Wyniki są zgodnie z oczekiwaniami, gdy widok SAP HANA zawiera nieaddytywne miary (na przykład różne liczby lub średnie zamiast zwykłych sum).
* Zapytania wynikowe są wydajne.

Na początek zaleca się poświęcić trochę czasu na wyjaśnienie zachowania relacyjnego źródła, na przykład programu **SQL Server**, gdy zapytanie zdefiniowane w oknie **Pobieranie danych** lub **Edytor zapytań** wykonuje agregację. W poniższym przykładzie zapytanie zdefiniowane w **Edytorze zapytań** zwraca średnią cenę według kolumny **ProductID**.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

Jeśli dane zostaną zaimportowane do usługi Power BI (w przeciwieństwie do użycia zapytania bezpośredniego), spowoduje to następujące konsekwencje:

* Dane zostaną zaimportowane na poziomie agregacji zdefiniowanym przez zapytanie utworzone w **Edytorze zapytań**. Na przykład średnia cena według produktu. W konsekwencji zostanie utworzona tabela z dwiema kolumnami: *ProductID* i *AveragePrice*, które mogą zostać użyte w wizualizacjach.
* W wizualizacji każda kolejna agregacja (na przykład *Sum*, *Average*, *Min* i inne) jest wykonywana na zaimportowanych danych.  Na przykład dołączenie kolumny *AveragePrice* wizualizacji spowoduje domyślne użycie agregacji *Sum* i zwróci sumę z kolumny *AveragePrice* dla każdego produktu o identyfikatorze  *ProductID*, co w tym konkretnym przypadku da liczbę 13,67. Dotyczy to każdej alternatywnej funkcji agregującej (takiej jak *Min*, *Average* itd.) używanej w wizualizacji. Na przykład funkcja *Average* zwróci dla kolumny *AveragePrice* średnie z wartości 6,66, 4 i 3, co da liczbę 4,56, a *nie* średnią z 6 rekordów z kolumny *Price* tabeli bazowej, czyli liczbę 5,17.

Jeśli zamiast importowania zostanie użyte **zapytanie bezpośrednie**, będzie miała zastosowanie ta sama semantyka i wyniki będą dokładnie takie same:

* Dla tego samego zapytania w warstwie raportowania zostaną przedstawione logicznie dokładnie te same dane — nawet jeśli dane nie zostaną w rzeczywistości zaimportowane.
* W wizualizacji każda kolejna agregacja (*Sum*, *Average*, *Min* i inne) jest znowu wykonywana na tabeli logicznej z zapytania. I ponownie wizualizacja zawierająca funkcję *Average* z kolumny *AveragePrice* zwróci tę samą wartość — 4,56.

Weźmy więc teraz pod uwagę platformę **SAP HANA**. Usługa Power BI może pracować na platformie SAP HANA zarówno w *widokach analitycznych*, jak i *widokach obliczeniowych*, które mogą zawierać miary. Aktualnie w przypadku platformy SAP HANA mają zastosowanie te same zasady, które opisano wcześniej. Zapytanie zdefiniowane w oknie **Pobieranie danych** lub **Edytor zapytań** determinuje dostępne dane. Każda kolejna agregacja w wizualizacji jest wykonywana względem tych danych i ma to zastosowanie zarówno do operacji importowania, jak i zapytania bezpośredniego.

Jednak ze względu na charakter platformy HANA zapytanie zdefiniowane w początkowym oknie dialogowym **Pobieranie danych** lub **Edytor zapytań** jest zawsze zapytaniem agregującym i zwykle obejmuje miary, a rzeczywista agregacja, która zostanie użyta, jest definiowana w widoku platformy HANA.

W przykładzie odpowiadającym znajdującemu się wyżej przykładowi z programu SQL Server przedstawiono widok platformy HANA zawierający kolumny **ID**, **ProductID**, **DepotID** i miary, w tym miarę **AveragePrice** zdefiniowaną w widoku jako **Średnia cena**.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_02.png)

Jeśli w oknie **Pobieranie danych** wybrano dane dla miar **ProductID** i **AveragePrice**, w widoku definiowane jest zapytanie z żądaniem danych zagregowanych (w powyższym przykładzie dla uproszczenia użyto pseudojęzyka SQL, który nie odpowiada dokładnie składni języka HANA SQL). W przypadku takiego zapytania wszelkie dalsze agregacje zdefiniowane w wizualizacji prowadzą do większej agregacji wyników. Tak samo jak w zamieszczonym powyżej przykładzie dla programu **SQL Server**, ma to zastosowanie zarówno dla operacji importowania, jak i zapytania bezpośredniego. Należy zauważyć, że w przypadku użycia zapytania bezpośredniego zapytanie pochodzące z okna **Pobieranie danych** lub **Edytor zapytań** zostanie użyte w podwyborach dokonanych w obrębie pojedynczego zapytania wysłanego do platformy HANA i dlatego w takim przypadku w rzeczywistości wszystkie dane nie zostaną wczytane przed dalszym ich agregowaniem.

W konsekwencji podczas korzystania z zapytania bezpośredniego na platformie HANA należy uwzględnić następujące istotne kwestie:

* Należy zwrócić uwagę na kolejne agregacje wykonywane w wizualizacjach, gdy miara na platformie HANA nie jest addytywna (na przykład nie jest to prosta funkcja *Sum*, *Min* czy *Max*).
* W oknie **Pobieranie danych** lub **Edytor zapytań** należy korzystać tylko z wymaganych kolumn w celu zwrócenia niezbędnych danych ze względu na fakt, że wynik będzie zapytaniem, które musi być zapytaniem uzasadnionym możliwym do przesłania na platformę HANA. Na przykład jeśli wybrano dziesiątki kolumn z przekonaniem, że mogą one być wymagane w kolejnych wizualizacjach, to nawet w przypadku zapytania bezpośredniego prosta wizualizacja będzie oznaczać, że zapytanie agregujące używane w podwyborze będzie zawierać te dziesiątki kolumn, co zwykle doprowadza do znacznego zmniejszenia wydajności.

Spójrzmy na przykład. W poniższym przykładzie wybranie pięciu kolumn (CalendarQuarter, Color, LastName, ProductLine, SalesOrderNumber) w oknie dialogowym **Pobieranie danych** wraz z miarą OrderQuantity oznacza, że późniejsze utworzenie prostej wizualizacji zawierającej funkcję Min OrderQuantity spowoduje wysłanie następującego zapytania SQL do platformy HANA. Zacieniony fragment to podwybór zawierający zapytanie z okna dialogowego **Pobieranie danych** / **Edytor zapytań**. Jeśli ten podwybór daje wynik o bardzo dużej kardynalności, to najprawdopodobniej wynikowa wydajność platformy HANA będzie niska.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

W związku z tym zaleca się, aby elementy wybierane w oknie **Pobieranie danych** lub **Edytor zapytań** były ograniczone do tych elementów, które są niezbędne, co w wyniku da rozsądne zapytanie dla platformy HANA.

### <a name="next-steps"></a>Następne kroki
Aby uzyskać więcej informacji na temat zapytania bezpośredniego, zapoznaj się z następującymi zasobami:

* [Zapytanie bezpośrednie w usłudze Power BI](desktop-directquery-about.md)
* [Źródła danych obsługiwane przez zapytanie bezpośrednie](desktop-directquery-data-sources.md)
* [Zapytanie bezpośrednie i system SAP BW](desktop-directquery-sap-bw.md)
* [Lokalna brama danych](service-gateway-onprem.md)

