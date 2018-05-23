---
title: Wyświetlanie raportów dla urządzeń przenośnych i kluczowych wskaźników wydajności usług SSRS w aplikacji mobilnej dla systemu Windows 10 — Power BI
description: Aplikacja mobilna usługi Power BI dla systemu Windows 10 zapewnia mobilny dostęp na żywo z obsługą dotykową do ważnych lokalnych informacji biznesowych.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 7bbf03c35284924c415a9ae1348528ed80c3f2fe
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="view-reporting-services-ssrs-mobile-reports-and-kpis-in-the-windows-10-power-bi-mobile-app"></a>Wyświetlanie raportów dla urządzeń przenośnych i kluczowych wskaźników wydajności usług Reporting Services (SSRS) w aplikacji mobilnej usługi Power BI dla systemu Windows 10
Aplikacja mobilna usługi Power BI dla systemu Windows 10 zapewnia mobilny dostęp na żywo z obsługą dotykową do ważnych lokalnych informacji biznesowych w usługach SQL Server 2016 Reporting Services. 

![Raporty usług Reporting Services dla urządzeń przenośnych](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="first-things-first"></a>Wszystko po kolei
[Utwórz raporty usług Reporting Services dla urządzeń przenośnych](https://msdn.microsoft.com/library/mt652547.aspx) za pomocą programu SQL Server 2016 Enterprise Edition Mobile Report Publisher i opublikuj je w [portalu internetowym usług Reporting Services](https://msdn.microsoft.com/library/mt637133.aspx). Utwórz kluczowe wskaźniki wydajności bezpośrednio w portalu internetowym. Uporządkuj je w folderach i oznacz swoje ulubione, aby móc je łatwo odnaleźć. 

Następnie w aplikacji mobilnej Power BI dla systemu Windows 10 wyświetl raporty dla urządzeń przenośnych i kluczowe wskaźniki wydajności uporządkowane w folderach lub zebrane jako ulubione. 

> [!NOTE]
> Na urządzeniu musi działać system Windows 10. Aplikacja działa najlepiej na urządzeniach z co najmniej 1 GB pamięci RAM i 8 GB pamięci wewnętrznej.
> 
> 

## <a name="explore-samples-without-a-sql-server-2016-reporting-services-server"></a>Eksplorowanie przykładów bez serwera usług SQL Server 2016 Reporting Services
Nawet jeśli nie masz dostępu do portalu internetowego usług Reporting Services, możesz nadal eksplorować funkcje raportów usług Reporting Services dla urządzeń przenośnych.

1. Na urządzeniu z systemem Windows 10 otwórz aplikację usługi Power BI.
2. Naciśnij przycisk nawigacji globalnej ![Przycisk nawigacji globalnej](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) w lewym górnym rogu.
3. Naciśnij ikonę **Ustawienia** ![Ikona Ustawienia](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png), kliknij prawym przyciskiem myszy lub naciśnij i przytrzymaj pozycję **Połącz z serwerem**, a następnie naciśnij pozycję **Wyświetl przykłady**.
   
   ![Wyświetlanie przykładów usług SSRS](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-connect-ssrs-samples.png)
4. Otwórz folder Raporty sprzedaży detalicznej lub Raporty sprzedaży, aby zapoznać się z kluczowymi wskaźnikami wydajności i raportami dla urządzeń przenośnych.
   
   ![Przykładowe kluczowe wskaźniki wydajności i raporty dla urządzeń przenośnych](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-ssrs-sample-kpis.png)

Przeglądaj przykłady, aby korzystać z kluczowych wskaźników wydajności i raportów dla urządzeń przenośnych.

## <a name="connect-to-a-reporting-services-report-server"></a>Łączenie się z serwerem raportów usług Reporting Services
1. U dołu lewego paska nawigacyjnego naciśnij pozycję **Ustawienia** ![Ikona Ustawienia](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png)
2. Naciśnij pozycję **Połącz z serwerem**.
3. Wprowadź adres serwera oraz swoją nazwę użytkownika i hasło. Adres serwera podaj w następującym formacie:
   
     `http://<servername>/reports` lub `https://<servername>/reports`
   
   > [!NOTE]
   > Uwzględnij ciąg **http** lub **https** na początku parametrów połączenia.
   > 
   > 
   
    Naciśnij pozycję **Opcja zaawansowana**, jeśli chcesz nadać serwerowi nazwę.
4. Naciśnij znacznik wyboru, aby nawiązać połączenie. 
   
   Spowoduje to wyświetlenie serwera na lewym pasku nawigacyjnym.
   
   ![Serwer na lewym pasku nawigacyjnym](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-server.png)
   
   >[!TIP]
   >W dowolnym momencie naciśnij przycisk nawigacji globalnej ![Przycisk nawigacji globalnej](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png), aby przejść między raportami usług Reporting Services dla urządzeń przenośnych i pulpitami nawigacyjnymi w usłudze Power BI. 
   > 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>Wyświetlanie raportów dla urządzeń przenośnych i kluczowych wskaźników wydajności usług Reporting Services w aplikacji Power BI
Raporty dla urządzeń przenośnych i kluczowe wskaźniki wydajności usług Reporting Services są wyświetlane w tych samych folderach, w których się znajdują w portalu internetowym usług Reporting Services.

![Foldery raportów](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-folders.png)

* Naciśnij kluczowy wskaźnik wydajności, aby zobaczyć go w trybie koncentracji uwagi.
  
    ![Kluczowy wskaźnik wydajności w trybie koncentracji uwagi](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-kpis.png)
* Naciśnij raport dla urządzeń przenośnych, aby otworzyć go i korzystać z niego w aplikacji Power BI.
  
    ![Raport usług Reporting Services dla urządzeń przenośnych](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Wyświetlanie ulubionych kluczowych wskaźników wydajności i raportów
Kluczowe wskaźniki wydajności i raporty dla urządzeń przenośnych można oznaczyć jako ulubione w portalu internetowym usług Reporting Services, a następnie wyświetlać je w jednym wygodnym folderze na swoim urządzeniu z systemem Windows 10 wraz z ulubionymi pulpitami nawigacyjnymi i raportami usługi Power BI.

* Naciśnij pozycję **Ulubione**.
  
   ![Ikona Ulubione](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-favorite-menu.png)
  
   Wszystkie ulubione elementy z portalu internetowego zostaną wyświetlone na tej stronie.
  
   ![Strona Ulubione](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-favorites.png)

Dowiedz się więcej na temat [ulubionych w aplikacjach mobilnych Power BI](mobile-apps-favorites.md).

## <a name="remove-a-connection-to-a-report-server"></a>Usuwanie połączenia z serwerem raportów
Aplikacja mobilna Power BI w danym momencie może być połączona tylko z jednym serwerem raportów. Jeśli chcesz się połączyć z innym serwerem, musisz rozłączyć połączenie z obecnym.

1. U dołu lewego paska nawigacyjnego naciśnij pozycję **Ustawienia** ![Ikona Ustawienia](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png).
2. Naciśnij i przytrzymaj nazwę serwera, z którym nie chcesz mieć nawiązanego połączenia.
3. Naciśnij pozycję **Usuń serwer**.
   
    ![Usuwanie serwera](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-remove-server-menu.png)

## <a name="create-reporting-services-mobile-reports-and-kpis"></a>Tworzenie raportów dla urządzeń przenośnych i kluczowych wskaźników wydajności usług Reporting Services
Raporty dla urządzeń przenośnych i kluczowe wskaźniki wydajności usług Reporting Services nie są tworzone w aplikacji mobilnej Power BI. Można je utworzyć w programie SQL Server Mobile Report Publisher i portalu internetowym usług SQL Server 2016 Reporting Services.

* [Utwórz własne raporty usług Reporting Services dla urządzeń przenośnych](https://msdn.microsoft.com/library/mt652547.aspx) i opublikuj je w portalu internetowym usług Reporting Services.
* Utwórz [kluczowe wskaźniki wydajności w portalu internetowym usług Reporting Services](https://msdn.microsoft.com/library/mt683632.aspx)

## <a name="next-steps"></a>Następne kroki
* [Wprowadzenie do aplikacji mobilnej Power BI dla systemu Windows 10](mobile-windows-10-phone-app-get-started.md)  
* [Wprowadzenie do usługi Power BI](service-get-started.md)  
* Masz pytania? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

