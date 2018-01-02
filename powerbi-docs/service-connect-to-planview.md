---
title: "Łączenie się z usługą Planview Enterprise przy użyciu usługi Power BI"
description: "Pakiet zawartości Planview Enterprise dla usługi Power BI"
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
ms.openlocfilehash: 12346c0a9a580b2c3dd36c61a00d27097e1b3937
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
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

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](service-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="system-requirements"></a>Wymagania systemowe
Aby zaimportować dane usługi Planview Enterprise do usługi Power BI, trzeba być użytkownikiem usługi Planview Enterprise z włączoną funkcją Reporting Portal Viewer. Zobacz dodatkowe wymagania poniżej.

W tej procedurze przyjęto, że zalogowano się już na stronie głównej usługi Microsoft Power BI przy użyciu konta usługi Power BI. Jeśli nie masz konta usługi Power BI, utwórz nowe, bezpłatne konto usługi Power BI na stronie głównej usługi Power BI, a następnie kliknij opcję Pobierz dane.

## <a name="next-steps"></a>Następne kroki:

[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych dla usługi Power BI](service-get-data.md)