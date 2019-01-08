---
title: Łączenie się z pakietem zawartości comScore Digital Analytix przy użyciu usługi Power BI
description: Pakiet zawartości comScore Digital Analytix dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 7a6e6979a6281ef6b00a84cff138818869b113e6
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008033"
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

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

<a name="Requirements"></a>

## <a name="system-requirements"></a>Wymagania systemowe
Aby nawiązać połączenie, wymagane jest konto użytkownika usługi comScore DAx i dostęp do interfejsu API comScore DAx. Skontaktuj się z administratorem usługi comScore DAx, aby potwierdzić swoje konto.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Poniżej zamieszczono więcej informacji o tym, jak znaleźć poszczególne parametry usługi comScore.

**Centrum danych**

Centrum danych, z którym nawiązywane jest połączenie, zależy od używanego adresu URL usługi comScore.

Jeśli używasz adresu URL https://dax.comscore.com, wprowadź wartość „US”, a jeśli używasz adresu URL https://dax.comscore.eu, wprowadź wartość „EU”.

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

