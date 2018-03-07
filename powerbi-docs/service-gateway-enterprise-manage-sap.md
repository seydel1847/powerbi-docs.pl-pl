---
title: "Zarządzanie źródłem danych SAP HANA"
description: "Jak zarządzać lokalną bramą danych i źródłami danych należącymi do tej bramy. Ten artykuł dotyczy platformy SAP HANA."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 8f9ec69c2a131a8de8f53385170bbddc59211f7b
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="manage-your-sap-hana-data-source"></a>Zarządzanie źródłem danych SAP HANA
Po zainstalowaniu lokalnej bramy danych musisz dodać źródła danych, które mogą być używane z tą bramą. W tym artykule opisano sposób pracy z bramami i źródłami danych. Źródła danych SAP HANA można użyć na potrzeby zaplanowanego odświeżania lub zapytania bezpośredniego.

## <a name="download-and-install-the-gateway"></a>Pobieranie i instalowanie bramy
Bramę można pobrać z poziomu usługi Power BI. Wybierz pozycję **Pliki do pobrania** > **Brama danych** lub przejdź na [stronę pobierania bramy](https://go.microsoft.com/fwlink/?LinkId=698861).

![](media/service-gateway-enterprise-manage-sap/powerbi-download-data-gateway.png)

## <a name="add-a-gateway"></a>Dodawanie bramy
Aby dodać bramę, po prostu [pobierz](https://go.microsoft.com/fwlink/?LinkId=698861) i zainstaluj ją na serwerze w swoim środowisku. Po zainstalowaniu bramy zostanie ona wyświetlona na liście bram w obszarze **Zarządzanie bramami**.

> [!NOTE]
> Obszar **Zarządzanie bramami** nie zostanie wyświetlony, dopóki użytkownik nie będzie administratorem co najmniej jednej bramy. Może to nastąpić po dodaniu użytkownika jako administratora lub przez zainstalowanie i skonfigurowanie bramy.
> 
> 

## <a name="remove-a-gateway"></a>Usuwanie bramy
Usunięcie bramy spowoduje także usunięcie wszystkich źródeł danych w ramach tej bramy.  Spowoduje to również uszkodzenie wszystkich pulpitów nawigacyjnych i raportów, które są zależne od tych źródeł danych.

1. Wybierz ikonę koła zębatego ![](media/service-gateway-enterprise-manage-sap/pbi_gearicon.png) w prawym górnym rogu, a następnie wybierz pozycję **Zarządzaj bramami**.
2. Wybierz pozycję Brama, a następnie pozycję **Usuń**
   
   ![](media/service-gateway-enterprise-manage-sap/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Dodawanie źródła danych
Źródło danych możesz dodać, wybierając bramę i klikając pozycję **Dodaj źródło danych** lub przechodząc do obszaru Brama i wybierając pozycję **Dodaj źródło danych**.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings1.png)

Następnie możesz wybrać z listy **typ źródła danych**.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings2-sap.png)

W kolejnym kroku podaj informacje dla źródła danych: **serwer**, **nazwę użytkownika** i **hasło**.

> [!NOTE]
> Wszystkie zapytania w tym źródle danych będą wykonywane z użyciem tych poświadczeń. Aby uzyskać dodatkowe informacje, zobacz główny artykuł na temat lokalnej bramy danych, z którego możesz dowiedzieć się więcej na temat przechowywania [poświadczeń](service-gateway-onprem.md#credentials).
> 
> 

![](media/service-gateway-enterprise-manage-sap/datasourcesettings3-sap.png)

Możesz kliknąć pozycję **Dodaj** po wprowadzeniu wszystkich wymaganych informacji.  Teraz możesz używać tego źródła danych na potrzeby zaplanowanego odświeżania lub zapytania bezpośredniego względem lokalnego serwera SAP HANA. W przypadku powodzenia zostanie wyświetlony komunikat *Łączenie przebiegło pomyślnie*.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings4.png)

### <a name="advanced-settings"></a>Ustawienia zaawansowane
Dla źródła danych można skonfigurować poziom prywatności. Służy on do określania sposobu łączenia danych. Jest to używane tylko w przypadku zaplanowanego odświeżania. Nie ma zastosowania względem zapytania bezpośredniego. [Dowiedz się więcej](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-sap/datasourcesettings9.png)

## <a name="remove-a-data-source"></a>Usuwanie źródła danych
Usunięcie źródła danych spowoduje uszkodzenie wszystkich pulpitów nawigacyjnych lub raportów, które są zależne od tego źródła danych.  

Aby usunąć źródło danych, przejdź do obszaru Źródło danych, a następnie wybierz pozycję **Usuń**.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings6.png)

## <a name="manage-administrators"></a>Zarządzanie administratorami
Na karcie Administratorzy bramy możesz dodawać i usuwać użytkowników (lub grupy zabezpieczeń), którzy mogą administrować bramą.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings8.png)

## <a name="manage-users"></a>Zarządzanie użytkownikami
Na karcie Użytkownicy dla źródła danych można dodawać i usuwać użytkowników (lub grupy zabezpieczeń), którzy mogą używać tego źródła danych.

> [!NOTE]
> Lista użytkowników służy jedynie do kontrolowania, którzy użytkownicy mogą publikować raporty. Właściciele raportów mogą tworzyć pulpity nawigacyjne lub pakiety zawartości i udostępniać je innym użytkownikom.
> 
> 

![](media/service-gateway-enterprise-manage-sap/datasourcesettings5.png)

## <a name="using-the-data-source"></a>Używanie źródła danych
Po utworzeniu źródło danych będzie dostępne do użycia z połączeniami zapytań bezpośrednich lub za pośrednictwem zaplanowanego odświeżania.

> [!NOTE]
> Nazwy serwera i bazy danych muszą być zgodne między programem Power BI Desktop i źródłem danych w ramach lokalnej bramy danych.
> 
> 

Połączenie między zestawem danych i źródłem danych w obrębie bramy jest oparte na nazwie serwera i nazwie bazy danych. Muszą one być zgodne. Na przykład jeśli podasz adres IP jako nazwę serwera w programie Power BI Desktop, konieczne będzie użycie adresu IP dla źródła danych w ramach konfiguracji bramy. Jeśli używasz nazwy *SERWER\WYSTĄPIENIE* w programie Power BI Desktop, konieczne będzie użycie tej samej nazwy w źródle danych skonfigurowanym dla bramy.

Dotyczy to zarówno zapytania bezpośredniego, jak i zaplanowanego odświeżania.

### <a name="using-the-data-source-with-directquery-connections"></a>Używanie źródeł danych z połączeniami zapytań bezpośrednich
Musisz sprawdzić, czy nazwa serwera i nazwa bazy danych w programie Power BI Desktop i skonfigurowanym źródle danych dla bramy są zgodne. Ponadto do publikowania zestawów danych zapytania bezpośredniego wymagane jest, aby użytkownik znajdował się na liście na karcie **Użytkownicy** źródła danych. Wybór zapytania bezpośredniego odbywa się podczas pierwszego importu danych w programie Power BI Desktop. [Dowiedz się więcej](desktop-use-directquery.md)

Po opublikowaniu zestawu danych w programie Power BI Desktop lub za pomocą funkcji **Pobierz dane** raporty powinny działać. Po utworzeniu źródła danych w obrębie bramy może upłynąć kilka minut, zanim będzie można używać połączenia.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Używanie źródła danych z zaplanowanym odświeżaniem
Jeśli znajdujesz się na liście na karcie **Użytkownicy** źródła danych skonfigurowanego w obrębie bramy, a nazwy serwera i bazy danych są zgodne, brama zostanie wyświetlona jako opcja, która może zostać użyta z zaplanowanym odświeżaniem.

![](media/service-gateway-enterprise-manage-sap/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Następne kroki
[Lokalna brama danych](service-gateway-onprem.md)  
[Lokalna brama danych — szczegóły](service-gateway-onprem-indepth.md)  
[Rozwiązywanie problemów z lokalną bramą danych](service-gateway-onprem-tshoot.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

