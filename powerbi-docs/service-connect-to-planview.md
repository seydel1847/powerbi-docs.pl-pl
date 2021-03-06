---
title: Łączenie się z usługą Planview Enterprise przy użyciu usługi Power BI
description: Pakiet zawartości Planview Enterprise dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6095faca7fd0d7d42fd6b3871c9e45658a32a14f
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007736"
---
# <a name="connect-to-planview-enterprise-with-power-bi"></a>Łączenie się z usługą Planview Enterprise przy użyciu usługi Power BI
Pakiet zawartości Planview Enterprise umożliwia wizualizowanie danych dotyczących zasobów i zarządzania pracą w całkiem nowy sposób bezpośrednio w usłudze Power BI. Użyj poświadczeń logowania usługi Planview Enterprise, aby w sposób interaktywny wyświetlić wydatki inwestycyjne w portfolio, ocenić, które z nich przekraczają budżet, a które mieszczą się w jego limitach oraz dowiedzieć się, jak realizowane projekty wpisują się w firmowe priorytety strategiczne. Ponadto można rozszerzyć gotowy do użycia pulpit nawigacyjny i raporty, aby uzyskać szczegółowe informacje, które są dla Ciebie najważniejsze.

Połącz się z [pakietem zawartości Planview Enterprise w usłudze Power BI](https://app.powerbi.com/getdata/services/planview-enterprise)

>[!NOTE]
>Aby zaimportować dane usługi Planview Enterprise do usługi Power BI, trzeba być użytkownikiem usługi Planview Enterprise z włączoną funkcją Reporting Portal Viewer. Zobacz dodatkowe wymagania poniżej.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
    ![](media/service-connect-to-planview/get.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
    ![](media/service-connect-to-planview/services.png)
3. Na stronie usługi Power BI wybierz opcję **Planview Enterprise**, a następnie wybierz pozycję **Pobierz**:  
    ![](media/service-connect-to-planview/planview.png)
4. W polu tekstowym adresu URL usługi Planview Enterprise wprowadź adres URL serwera Planview Enterprise, którego chcesz używać. W polu tekstowym bazy danych usługi Planview Enterprise wprowadź nazwę bazy danych usługi Planview Enterprise, a następnie kliknij przycisk Dalej.  
    ![](media/service-connect-to-planview/params.png)
5. Na liście Metoda uwierzytelniania wybierz opcję **Podstawowa**, jeśli nie jest jeszcze wybrana. W polach **Nazwa użytkownika** i **Hasło** wprowadź odpowiednie wartości dla konta i wybierz przycisk **Zaloguj**.  
   ![](media/service-connect-to-planview/creds.png)
6. W lewym okienku wybierz opcję Planview Enterprise z listy pulpitów nawigacyjnych.  
     Usługa Power BI zaimportuje dane usługi Planview Enterprise do pulpitu nawigacyjnego. Pamiętaj, że ładowanie danych może zająć trochę czasu.  
    ![](media/service-connect-to-planview/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="system-requirements"></a>Wymagania systemowe
Aby zaimportować dane usługi Planview Enterprise do usługi Power BI, trzeba być użytkownikiem usługi Planview Enterprise z włączoną funkcją Reporting Portal Viewer. Zobacz dodatkowe wymagania poniżej.

W tej procedurze przyjęto, że zalogowano się już na stronie głównej usługi Microsoft Power BI przy użyciu konta usługi Power BI. Jeśli nie masz konta usługi Power BI, przejdź na stronę [powerbi.com](https://powerbi.microsoft.com/get-started/) i w sekcji **Power BI — Udostępnianie i współpraca w chmurze** wybierz pozycję **Wypróbuj bezpłatnie**. Następnie kliknij pozycję **Pobierz dane**.

## <a name="next-steps"></a>Następne kroki:

[Co to jest usługa Power BI?](power-bi-overview.md)

[Pobieranie danych dla usługi Power BI](service-get-data.md)