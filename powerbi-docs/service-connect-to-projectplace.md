---
title: Nawiązywanie połączenia z narzędziem Projectplace przy użyciu usługi Power BI
description: Narzędzie Projectplace dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 9c98257ac352893d074ea91c27e8b1cf3d83e4a3
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007642"
---
# <a name="connect-to-projectplace-by-planview-with-power-bi"></a>Nawiązywanie połączenia z narzędziem Projectplace od firmy Planview przy użyciu usługi Power BI
Z pakietem zawartości Projectplace od firmy Planview możesz wizualizować dane projektu opracowywanego we współpracy, korzystając z zupełnie nowych sposobów bezpośrednio w usłudze Power BI. Użyj poświadczeń logowania narzędzia Projectplace, aby interaktywnie wyświetlić kluczowe statystyki dotyczące projektu, znaleźć najbardziej aktywnych i produktywnych członków zespołu oraz zidentyfikować karty i działania z ryzykiem w wielu projektach na koncie Projectplace. Ponadto można rozszerzyć gotowy do użycia pulpit nawigacyjny i raporty, aby uzyskać szczegółowe informacje, które są dla Ciebie najważniejsze.

[Nawiązywanie połączenia z pakietem zawartości Projectplace w usłudze Power BI](https://app.powerbi.com/getdata/services/projectplace)

>[!NOTE]
>Aby zaimportować dane Projectplace do usługi Power BI, musisz być użytkownikiem narzędzia Projectplace. Zobacz dodatkowe wymagania poniżej.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
    ![](media/service-connect-to-projectplace/get.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
    ![](media/service-connect-to-projectplace/services.png)
3. Na stronie usługi Power BI wybierz opcję **Projectplace od firmy Planview**, a następnie wybierz pozycję **Pobierz**:  
   
    ![](media/service-connect-to-projectplace/projectplace.png)
4. W polu tekstowym Adres URL strumieniowego źródła danych OData wprowadź adres URL strumieniowego źródła danych OData narzędzia Projectplace, którego chcesz użyć, jak pokazano na poniższej ilustracji:
   
    ![](media/service-connect-to-projectplace/params.png)
5. Na liście Metoda uwierzytelniania wybierz opcję **OAuth**, jeśli nie jest jeszcze wybrana. Wybierz opcję **Zaloguj** i postępuj zgodnie z przepływem logowania.  
   
   ![](media/service-connect-to-projectplace/creds.png)
6. W lewym okienku wybierz opcję **Projectplace** z listy pulpitów nawigacyjnych. Usługa Power BI zaimportuje dane Projectplace do pulpitu nawigacyjnego. Należy pamiętać, że ładowanie danych może zająć trochę czasu.  
   
    Pulpit nawigacyjny zawiera kafelki, które wyświetlają dane z bazy danych Projectplace. Na poniższej ilustracji przedstawiono przykład domyślnego pulpitu nawigacyjnego Projectplace w usłudze Power BI.
   
    ![](media/service-connect-to-projectplace/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="system-requirements"></a>Wymagania systemowe
Aby zaimportować dane Projectplace do usługi Power BI, musisz być użytkownikiem narzędzia Projectplace. W tej procedurze przyjęto, że zalogowano się już na stronie głównej usługi Microsoft Power BI przy użyciu konta usługi Power BI. Jeśli nie masz konta usługi Power BI, przejdź na stronę [powerbi.com](https://powerbi.microsoft.com/get-started/) i w sekcji **Power BI — Udostępnianie i współpraca w chmurze** wybierz pozycję **Wypróbuj bezpłatnie**. Następnie kliknij pozycję **Pobierz dane**.

## <a name="next-steps"></a>Następne kroki
[Co to jest usługa Power BI?](power-bi-overview.md)

[Power BI — podstawowe pojęcia](consumer/end-user-basic-concepts.md)

