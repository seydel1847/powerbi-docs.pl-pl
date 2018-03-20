---
title: "Łączenie się z usługą Adobe Analytics w programie Power BI Desktop (wersja zapoznawcza)"
description: "Łatwo nawiązuj połączenie z usługą Adobe Analytics i używaj jej w programie Power BI Desktop"
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
ms.date: 03/09/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: efd6d066e2f98f86248730917c2f4aa0c8a39983
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2018
---
# <a name="connect-to-adobe-analytics-in-power-bi-desktop-preview"></a>Łączenie się z usługą Adobe Analytics w programie Power BI Desktop (wersja zapoznawcza)
W programie **Power BI Desktop** możesz nawiązać połączenie z usługą **Adobe Analytics** i korzystać z danych źródłowych w taki sam sposób, jak w przypadku dowolnego innego źródła danych w programie Power BI Desktop. 

![Pobieranie danych z usługi Adobe Analytics](media/desktop-connect-adobe-analytics/connect-adobe-analytics_01.png)

## <a name="enable-the-adobe-analytics-connector-preview"></a>Włączanie łącznika rozwiązania Adobe Analytics (wersja zapoznawcza) 
Ponieważ łącznik rozwiązania **Adobe Analytics** jest obecnie w wersji zapoznawczej, musisz włączyć funkcję wersji zapoznawczej, aby łącznik był dostępny w oknie **Pobieranie danych**. Aby włączyć wersję zapoznawczą łącznika, wybierz pozycję **Plik > Opcje i ustawienia > Opcje > Funkcje wersji zapoznawczej** w programie Power BI Desktop, a następnie zaznacz pole wyboru obok pozycji **Zakładki**. 

![Włączanie wersji zapoznawczej łącznika Adobe Analytics w obszarze Opcje](media/desktop-connect-adobe-analytics/connect-adobe-analytics_02.png)

Musisz ponownie uruchomić program **Power BI Desktop** po dokonaniu wyboru, aby włączyć wersję zapoznawczą łącznika Adobe Analytics.

## <a name="connect-to-adobe-analytics-data"></a>Łączenie z danymi usługi Adobe Analytics
Aby nawiązać połączenie z danymi **Adobe Analytics**, wybierz pozycję **Pobierz dane** z poziomu wstążki **Narzędzia główne** w programie Power BI Desktop. Wybierz pozycję **Usługi online** z listy kategorii po lewej stronie. Zostanie wyświetlony **łącznik Adobe Analytics**.

![Pobieranie danych z usługi Adobe Analytics](media/desktop-connect-adobe-analytics/connect-adobe-analytics_01.png)

W wyświetlonym oknie **Adobe Analytics** wybierz przycisk **Zaloguj**, a następnie podaj poświadczenia, aby zalogować się do konta usługi Adobe Analytics. Zostanie wyświetlone okno logowania Adobe, jak pokazano na poniższej ilustracji.

![Logowanie się w usłudze Adobe Analytics](media/desktop-connect-adobe-analytics/connect-adobe-analytics_03.png)

Po wyświetleniu monitu wprowadź nazwę użytkownika i hasło. Po nawiązaniu połączenia możesz wyświetlić podgląd i wybrać wiele wymiarów i miar w oknie dialogowym **Nawigator** usługi Power BI, aby utworzyć pojedyncze tabelaryczne dane wyjściowe. Możesz też podać wszelkie niezbędne parametry wejściowe wymagane dla wybranych elementów. 

![Wybieranie danych przy użyciu nawigatora](media/desktop-connect-adobe-analytics/connect-adobe-analytics_04.png)

Możesz użyć polecenia **Załaduj** dla wybranej tabeli, co spowoduje pobranie całej tabeli do programu **Power BI Desktop**, lub możesz użyć polecenia **Edytuj** w stosunku do zapytania, co spowoduje otworzenie okna **Edytor zapytań** umożliwiającego filtrowanie i uściślenie zestawu danych, którego chcesz użyć. Następnie możesz załadować ten dopracowany zestaw danych do programu **Power BI Desktop**.

![Ładowanie lub edytowanie danych w nawigatorze](media/desktop-connect-adobe-analytics/connect-adobe-analytics_05.png)


## <a name="next-steps"></a>Następne kroki
Z poziomu programu Power BI Desktop możesz łączyć się z danymi różnego rodzaju. Więcej informacji na temat źródeł danych znajdziesz w następujących zasobach:

* [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)
* [Łączenie się ze skoroszytami programu Excel w programie Power BI Desktop](desktop-connect-excel.md)   
* [Wprowadzanie danych bezpośrednio w programie Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

