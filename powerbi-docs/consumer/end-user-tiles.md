---
title: Kafelki pulpitu nawigacyjnego w usłudze Power BI
description: Wszystkie informacje o kafelkach pulpitu nawigacyjnego w usłudze Power BI. Dotyczy to również kafelków, które są tworzone z poziomu usługi SQL Server Reporting Services (SSRS).
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/21/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: f0ff1d9a49e0566119df2c790ad618700c9a9ca3
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565457"
---
# <a name="dashboard-tiles-in-power-bi"></a>Kafelki pulpitu nawigacyjnego w usłudze Power BI
Pulpity nawigacyjne i kafelki pulpitu nawigacyjnego są funkcjami usługi Power BI, a nie programu Power BI Desktop. Chociaż kafelków pulpitów nawigacyjnych nie można tworzyć ani przypinać w usłudze Power BI dla urządzeń mobilnych, [można je wyświetlać i udostępniać](mobile/mobile-tiles-in-the-mobile-apps.md). Ponadto w usłudze Power BI dla urządzeń mobilnych można [dodawać zdjęcia do pulpitu nawigacyjnego za pomocą aplikacji dla telefonu iPhone](mobile/mobile-iphone-app-get-started.md).

## <a name="dashboard-tiles"></a>Aktualizacja kafelków
![Pulpit nawigacyjny usługi Power BI](./media/end-user-tiles/power-bi-dashboard.png)

Kafelek stanowi migawkę danych przypiętą do pulpitu nawigacyjnego. Kafelek może zostać utworzony z raportu, zestawu danych, pulpitu nawigacyjnego, pola pytań i odpowiedzi, programu Excel, a także usług SQL Server Reporting Services (SSRS) i innych.  Ten zrzut ekranu przedstawia wiele różnych kafelków przypiętych do pulpitu nawigacyjnego.

Oprócz przypinania, autonomiczne kafelki można tworzyć bezpośrednio na pulpicie nawigacyjnym za pomocą polecenia [Dodaj kafelek](../service-dashboard-add-widget.md). Autonomiczne kafelki obejmują: pola tekstowe, obrazy, klipy wideo, dane przesyłane strumieniowo oraz treści internetowe.

Potrzebujesz pomocy dotyczącej bloków konstrukcyjnych tworzących usługę Power BI?  Zobacz [Power BI — podstawowe pojęcia](end-user-basic-concepts.md).

> [!NOTE]
> Jeśli zmienia się oryginalna wizualizacja użyta do utworzenia kafelka, kafelek nie ulegnie zmianie.  Jeśli na przykład przypniemy wykres liniowy z raportu, a następnie zmienimy ten wykres liniowy na wykres słupkowy, kafelek pulpitu nawigacyjnego w dalszym ciągu wyświetlać będzie wykres liniowy. Dane zostaną odświeżone, ale typ wizualizacji nie ulegnie zmianie.
> 
> 

## <a name="pin-a-tile-from"></a>Przypinanie kafelka z...
Istnieje wiele sposobów, aby dodać (przypiąć) kafelek na pulpicie nawigacyjnym. Kafelki można przypinać z:

* [pytań i odpowiedzi usługi Power BI](../service-dashboard-pin-tile-from-q-and-a.md)
* [raportu](../service-dashboard-pin-tile-from-report.md)
* [innego pulpitu nawigacyjnego](../service-pin-tile-to-another-dashboard.md)
* [skoroszytu programu Excel w usłudze OneDrive dla Firm](../service-dashboard-pin-tile-from-excel.md)
* [usługi Power BI Publisher dla programu Excel](../publisher-for-excel.md)
* [szybkiego wglądu w szczegółowe dane](end-user-insights.md)
* [usługi SSRS](https://msdn.microsoft.com/library/mt604784.aspx)

Autonomiczne kafelki obrazów, pól tekstowych, klipów wideo, danych przesyłanych strumieniowo i treści internetowych można tworzyć bezpośrednio na pulpicie nawigacyjnym za pomocą polecenia [Dodaj kafelek](../service-dashboard-add-widget.md).

  ![Ikona dodawania kafelka](./media/end-user-tiles/add_widgetnew.png)

## <a name="interacting-with-tiles-on-a-dashboard"></a>Interakcja z kafelkami na pulpicie nawigacyjnym
### <a name="move-and-resize-a-tile"></a>Przenoszenie i zmienianie rozmiaru kafelka
Chwyć kafelek i [przemieszczaj go na pulpicie nawigacyjnym](../service-dashboard-edit-tile.md). Aktywuj i wybierz uchwyt ![uchwyt](./media/end-user-tiles/resize-handle.jpg), aby zmienić rozmiar kafelka.

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>Najeżdżanie kursorem na kafelek w celu zmiany wyglądu i zachowania
1. Najedź kursorem na kafelek, aby wyświetlić wielokropek.
   
    ![wielokropek kafelka](./media/end-user-tiles/ellipses_new.png)
2. Wybierz symbol wielokropka, aby otworzyć menu akcji kafelka.
   
    ![ikona wielokropka](./media/end-user-tiles/power-bi-tile-menu.png)
   
    W tym miejscu można wykonać następujące czynności:
   
   * [Otworzyć raport, który został użyty do utworzenia tego kafelka ](end-user-reports.md) ![ikona raportu](./media/end-user-tiles/chart-icon.jpg)  
   
   * [Otworzyć arkusz, który został użyty do utworzenia tego kafelka ](end-user-reports.md) ![ikona arkusza](./media/end-user-tiles/power-bi-open-worksheet.png)  
     
    * [Wyświetlić w trybie koncentracji uwagi ](end-user-focus.md) ![ikona koncentracji uwagi](./media/end-user-tiles/fullscreen-icon.jpg)  
     * [Wyeksportować dane użyte na kafelku](end-user-export-data.md) ![ikona eksportowania danych](./media/end-user-tiles/export-icon.png)
     * [Edytować tytuł i podtytuł, dodać hiperlink](../service-dashboard-edit-tile.md) ![ikona edytowania](./media/end-user-tiles/pencil-icon.jpg)
     * [Uruchomić szczegółowe informacje](end-user-insights.md) ![ikona szczegółowych informacji](./media/end-user-tiles/power-bi-insights.png)
     * [Przypiąć kafelek do innego pulpitu nawigacyjnego](../service-pin-tile-to-another-dashboard.md)
       ![ikona przypinania](./media/end-user-tiles/pin-icon.jpg)
     * [Usunąć kafelek](../service-dashboard-edit-tile.md)
     ![ikona usuwania](./media/end-user-tiles/trash-icon.png)
3. Aby zamknąć menu akcji, wybierz pusty obszar na kanwie.

### <a name="select-click-a-tile"></a>Wybieranie (klikanie) kafelka
To co dzieje się po wybraniu kafelka, zależy od sposobu, w jaki kafelek został utworzony, a także od tego, czy ma on [niestandardowy link](../service-dashboard-edit-tile.md). Jeśli ma on niestandardowy link, wybranie kafelka spowoduje przejście do tego linku. W przeciwnym razie wybranie kafelka spowoduje przejście do raportu, skoroszytu programu Excel Online, raportu lokalnej usługi SSRS lub do pytania sekcji pytań i odpowiedzi, które zostały użyte do utworzenia kafelka.

> [!NOTE]
> Wyjątek stanowią kafelki wideo utworzone bezpośrednio na pulpicie nawigacyjnym za pomocą polecenia **Dodaj kafelek**. Wybranie kafelka wideo (utworzonego w ten sposób) spowoduje odtworzenie filmu wideo bezpośrednio na pulpicie nawigacyjnym.   
> 
> 

## <a name="considerations-and-troubleshooting"></a>Zagadnienia i rozwiązywanie problemów
* Jeśli raport, który został użyty do utworzenia wizualizacji, nie został zapisany, wybranie kafelka nie wywoła żadnej akcji.
* Jeśli kafelek został utworzony na podstawie skoroszytu w usłudze Excel Online, a nie masz co najmniej uprawnień do odczytu tego skoroszytu, wybranie kafelka nie spowoduje otwarcia skoroszytu w usłudze Excel Online.
* W przypadku kafelków utworzonych bezpośrednio na pulpicie nawigacyjnym za pomocą polecenia **Dodaj kafelek**, jeśli został ustawiony niestandardowy hiperlink, wybranie tytułu, podtytułu lub kafelka spowoduje otwarcie tego adresu URL.  W przeciwnym razie domyślnie wybranie jednego z kafelków utworzonych bezpośrednio na pulpicie nawigacyjnym dla obrazu, kodu internetowego lub pola tekstowego nie wywoła żadnej akcji.
* Jeśli nie masz uprawnień do raportu w ramach usługi SSRS, wybranie kafelka utworzonego na bazie usługi SSRS spowoduje wyświetlenie strony informującej o braku dostępu (rsAccessDenied).
* Jeśli nie masz dostępu do sieci, w której znajduje się serwer usługi SSRS, wybranie kafelka utworzonego na bazie usługi SSRS spowoduje wyświetlenie strony informującej o braku możliwości zlokalizowania serwera (HTTP 404). Urządzenie musi mieć dostęp do sieci i serwera raportów, aby wyświetlić raport.
* Jeśli zmienia się oryginalna wizualizacja użyta do utworzenia kafelka, kafelek nie ulegnie zmianie.  Jeśli na przykład przypniemy wykres liniowy z raportu, a następnie zmienimy ten wykres liniowy na wykres słupkowy, kafelek pulpitu nawigacyjnego w dalszym ciągu wyświetlać będzie wykres liniowy. Dane zostaną odświeżone, ale typ wizualizacji nie ulegnie zmianie.

## <a name="next-steps"></a>Następne kroki
[Tworzenie karty (kafelka z dużą liczbą) dla pulpitu nawigacyjnego](../visuals/power-bi-visualization-card.md)

[Pulpity nawigacyjne w usłudze Power BI](end-user-dashboards.md)  

[Odświeżanie danych](../refresh-data.md)

[Power BI — podstawowe pojęcia](end-user-basic-concepts.md)

[Eksportowanie kafelka do programu PowerPoint](http://blogs.msdn.com/b/powerbidev/archive/2015/09/28/integrating-power-bi-tiles-into-office-documents.aspx)

[Przypinanie elementów usług Reporting Services do pulpitów nawigacyjnych usługi Power BI](https://msdn.microsoft.com/library/mt604784.aspx)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

