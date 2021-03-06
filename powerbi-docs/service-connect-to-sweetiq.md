---
title: Łączenie z pakietem zawartości SweetIQ przy użyciu usługi Power BI
description: Pakiet zawartości SweetIQ dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 535a5b0d24abcd76d7c7b9becedad152e17829ed
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007757"
---
# <a name="connect-to-sweetiq-with-power-bi"></a>Łączenie z pakietem zawartości SweetIQ przy użyciu usługi Power BI
Pakiet zawartości usługi Power BI pobiera dane z konta usługi SweetIQ i generuje zestaw gotowych zawartości, pozwalając łatwo eksplorować dane. Pakiet zawartości SweetIQ umożliwia analizowanie danych dotyczących lokalizacji, ofert, ocen i recenzji. Dane będą odświeżane codziennie, zapewniając aktualność monitorowanych danych.

Połącz się z [pakietem zawartości SweetIQ](https://app.powerbi.com/groups/me/getdata/services/sweetiq) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. W okienku nawigacji po lewej stronie kliknij pozycję **Pobierz dane.**
   
    ![](media/service-connect-to-sweetiq/getdata.png)
2. Wybierz pozycję **SweetIQ** i kliknij przycisk **Pobierz.**
   
    ![](media/service-connect-to-sweetiq/sweetiq.png)
3. Podaj identyfikator klienta usługi SweetIQ. Zazwyczaj jest to wartość alfanumeryczna. Poniżej zamieszczono szczegółowe informacje o tym, jak znaleźć tę wartość.
   
    ![](media/service-connect-to-sweetiq/parameter.png)
4. Jako typ uwierzytelniania wybierz **Klucz** i podaj klucz interfejsu API usługi Sweet IQ. Zazwyczaj jest to wartość alfanumeryczna. Poniżej zamieszczono szczegółowe informacje o tym, jak znaleźć tę wartość.
   
    ![](media/service-connect-to-sweetiq/credentials.png)
5. Usługa Power BI rozpocznie ładowanie danych, co może nieco potrwać w zależności od rozmiaru danych na koncie. Po zakończeniu procesu importowania w okienku nawigacji po lewej stronie wyświetlony zostanie nowy pulpit nawigacyjny, raport i zestaw danych.
   
    ![](media/service-connect-to-sweetiq/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="finding-parameters"></a>Znajdowanie parametrów
Identyfikator klienta i klucz interfejsu API dla tego pakietu zawartości nie są tożsame z nazwą użytkownika i hasłem usługi SweetIQ.

Wybierz identyfikator klienta dla jednego z klientów, do których konto ma dostęp. Listę klientów można znaleźć w obszarze „Zarządzanie klientami” na koncie usługi SweetIQ.

Skontaktuj się z administratorem, aby otrzymać klucz interfejsu API w celu uzyskania dostępu do danych dla konkretnego klienta.

## <a name="next-steps"></a>Następne kroki
[Co to jest usługa Power BI?](power-bi-overview.md)

[Pobieranie danych dla usługi Power BI](service-get-data.md)

