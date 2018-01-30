---
title: "Łączenie z pakietem zawartości SweetIQ przy użyciu usługi Power BI"
description: "Pakiet zawartości SweetIQ dla usługi Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: eff79e26549ee67482a6876dc7850d2a922a4586
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
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

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="finding-parameters"></a>Znajdowanie parametrów
Identyfikator klienta i klucz interfejsu API dla tego pakietu zawartości nie są tożsame z nazwą użytkownika i hasłem usługi SweetIQ.

Wybierz identyfikator klienta dla jednego z klientów, do których konto ma dostęp. Listę klientów można znaleźć w obszarze „Zarządzanie klientami” na koncie usługi SweetIQ.

Skontaktuj się z administratorem, aby otrzymać klucz interfejsu API w celu uzyskania dostępu do danych dla konkretnego klienta.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych dla usługi Power BI](service-get-data.md)
