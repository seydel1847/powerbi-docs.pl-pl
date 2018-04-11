---
title: Łączenie się z pakietem zawartości comScore Digital Analytix przy użyciu usługi Power BI
description: Pakiet zawartości comScore Digital Analytix dla usługi Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: c7e476cb9e5a210ce2d37691c44ed05dd9f3c256
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-comscore-digital-analytix-with-power-bi"></a>Łączenie się z pakietem zawartości comScore Digital Analytix przy użyciu usługi Power BI
Za pomocą pakietu zawartości dla usługi Power BI możesz wizualizować i eksplorować dane usługi comScore Digital Analytix. Dane będą odświeżane automatycznie raz dziennie.

Połącz się z [pakietem zawartości comScore dla usługi Power BI.](https://app.powerbi.com/getdata/services/comscore)

>[!NOTE]
>Aby nawiązać połączenie z pakietem zawartości, potrzebne jest konto użytkownika usługi comScore DAx oraz dostęp do interfejsu API comScore. [Szczegółowe informacje](#Requirements) można znaleźć poniżej.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję Pobierz dane w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-connect-to/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-connect-to/services.png)
3. Wybierz pozycję **comScore Digital Analytix** \> **Pobierz**.
   
   ![](media/service-connect-to-connect-to/comscore.png)
4. Wprowadź centrum danych, identyfikator klienta comScore oraz witrynę, z którą chcesz nawiązać połączenie. Zobacz [Znajdowanie parametrów usługi comScore](#FindingParams) poniżej, aby uzyskać więcej informacji na temat znajdowania tych wartości.
   
   ![](media/service-connect-to-connect-to/parameters.png)
5. Podaj nazwę użytkownika comScore i hasło, aby nawiązać połączenie. Poniżej znajdują się szczegółowe informacje dotyczące uzyskiwania tej wartości.
   
   ![](media/service-connect-to-connect-to/creds.png)
6. Proces importowania rozpocznie się automatycznie. Po zakończeniu nowy pulpit nawigacyjny, raport i model zostaną wyświetlone w okienku nawigacji. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

<a name="Requirements"></a>

## <a name="system-requirements"></a>Wymagania systemowe
Aby nawiązać połączenie, wymagane jest konto użytkownika usługi comScore DAx i dostęp do interfejsu API comScore DAx. Skontaktuj się z administratorem usługi comScore DAx, aby potwierdzić swoje konto.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Poniżej zamieszczono więcej informacji o tym, jak znaleźć poszczególne parametry usługi comScore.

**Centrum danych**

Centrum danych, z którym nawiązywane jest połączenie, zależy od używanego adresu URL usługi comScore.

Jeśli używasz adresu https://dax.comscore.com, wprowadź wartość „US”. Jeśli używasz adresu https://dax.comscore.eu, wprowadź wartość „EU”.

![](media/service-connect-to-connect-to/comscore_url.png) 

**Klient**

Klient jest tym samym parametrem, który podajesz podczas logowania się do usługi comScore DAx.

![](media/service-connect-to-connect-to/comscore_signin.png) 

**Witryna**

Witryna comScore określa witrynę, której dane chcesz wyświetlić. Listę witryn można znaleźć z poziomu konta usługi comScore.

![](media/service-connect-to-connect-to/comscore_sites.png)

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)

