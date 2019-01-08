---
title: Łączenie się z usługą SparkPost za pomocą usługi Power BI
description: Usługa SparkPost dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 48cdff67e613093c3ac473b0a505a6f0d57f4f2d
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008102"
---
# <a name="connect-to-sparkpost-with-power-bi"></a>Łączenie się z usługą SparkPost za pomocą usługi Power BI
Pakiet zawartości Power BI dla usługi SparkPost pozwala wyodrębnić cenne zestawy danych z konta SparkPost do jednego wnikliwego pulpitu nawigacyjnego. Przy użyciu pakietu zawartości SparkPost można zwizualizować ogólne statystyki dotyczące poczty e-mail, w tym domen, kampanii i zaangażowania przez usługodawcę internetowego.

Połącz się z [pakietem zawartości SparkPost dla usługi Power BI](https://app.powerbi.com/getdata/services/spark-post).

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-sparkpost/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-sparkpost/services.png)
3. Wybierz pakiet zawartości **SparkPost**, a następnie kliknij przycisk **Pobierz**. 
   
   ![](media/service-connect-to-sparkpost/sparkpost.png)
4. Po wyświetleniu monitu podaj klucz interfejsu API SparkPost oraz wybierz pozycję Zaloguj się. Poniżej znajdują się szczegółowe informacje dotyczące [wyszukiwania tych parametrów](#FindingParams).
   
   ![](media/service-connect-to-sparkpost/creds.png)
5. Rozpocznie się ładowanie danych. Może to chwilę potrwać, w zależności od rozmiaru konta. Po zaimportowaniu danych przez usługę Power BI w lewym okienku nawigacji zobaczysz domyślny pulpit nawigacyjny, raport i zestaw danych wypełniony statystykami dotyczącymi poczty e-mail z ostatnich 90 dni. Nowe elementy są oznaczone żółtą gwiazdką \*.
   
   ![](media/service-connect-to-sparkpost/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Pakiet zawartości SparkPost dla usługi Power BI zawiera takie informacje jak unikatowe kliknięcia oraz współczynniki akceptacji, odrzuceń, opóźnień i porzuceń oraz inne dane.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Pakiet zawartości używa klucza interfejsu API do połączenia konta SparkPost z usługą Power BI. Klucz interfejsu API można znaleźć na swoim koncie w obszarze Konto \> Interfejs API i SMTP (więcej szczegółów [tutaj](https://support.sparkpost.com/customer/portal/articles/1933377-create-api-keys)). Zalecane jest używanie klucza interfejsu API z uprawnieniami `Message Events: Read-only ` i `Metrics: Read-only`.

![](media/service-connect-to-sparkpost/sparkpost1.png)

