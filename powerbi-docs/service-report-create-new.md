---
title: 'Tworzenie nowego raportu z zestawu danych '
description: Tworzenie nowego raportu usługi Power BI na podstawie zestawu danych.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/24/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: a5762964b75d73d8dabceac58c47f616753b94cc
ms.sourcegitcommit: e17fc3816d6ae403414cf5357afbf6a492822ab8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/04/2018
ms.locfileid: "52830191"
---
# <a name="create-a-new-report-in-power-bi-service-by-importing-a-dataset"></a>Tworzenie nowego raportu w usłudze Power BI przez zaimportowanie zestawu danych
Po zapoznaniu się z tematem [Raporty w usłudze Power BI](consumer/end-user-reports.md) możesz teraz utworzyć własny raport. Istnieje wiele sposobów tworzenia raportów. W tym artykule zaczniemy od utworzenia podstawowego raportu na podstawie zestawu danych programu Excel przy użyciu usługi Power BI. Kiedy zapoznasz się z podstawami tworzenia raportów, możesz przejść do bardziej zaawansowanych tematów dostępnych w sekcji **Następne kroki** u dołu strony.  

## <a name="prerequisites"></a>Wymagania wstępne
> - Usługa Power BI (w celu tworzenia raportów za pomocą programu Power BI Desktop zobacz [Widok raportu w programie Desktop](desktop-report-view.md))  
> - Zestaw danych Próbka analizy handlu detalicznego

## <a name="import-the-dataset"></a>Importowanie zestawu danych
W przypadku tej metody tworzenia raportu punktem wyjścia jest zestaw danych i pusta kanwa raportu. Na użytek tej procedury [pobierz przykładowy zestaw danych programu Excel noszący nazwę Retail Analysis](http://go.microsoft.com/fwlink/?LinkId=529778) i zapisz go na swoim koncie w usłudze OneDrive dla Firm (opcja preferowana) lub lokalnie.

1. Utworzymy raport w obszarze roboczym usługi Power BI, więc wybierz istniejący obszar roboczy lub utwórz nowy.
   
   ![lista obszarów roboczych aplikacji](media/service-report-create-new/power-bi-workspaces2.png)
2. W dolnej części lewego okienka nawigacji wybierz opcję **Pobierz dane**.
   
   ![Pobierz dane](media/service-report-create-new/power-bi-get-data3.png)
3. Wybierz pozycję **Pliki** i przejdź do miejsca, w którym został zapisany przykładowy zestaw danych Retail Analysis.
   
    ![wybieranie pozycji Pliki](media/service-report-create-new/power-bi-select-files.png)
4. W ramach tego ćwiczenia wybierz pozycję **Importuj**.
   
   ![wybieranie pozycji Importuj](media/service-report-create-new/power-bi-import.png)
5. Po zaimportowaniu zestawu danych wybierz pozycję **Wyświetl zestaw danych**.
   
   ![wybieranie pozycji Wyświetl zestaw danych](media/service-report-create-new/power-bi-view-dataset.png)
6. Wyświetlenie zestawu danych powoduje otwarcie edytora raportów.  Zostanie wyświetlona pusta kanwa i narzędzia do edycji raportów.
   
   ![edytor raportów](media/service-report-create-new/power-bi-blank-report.png)

> **PORADA**: jeśli nie masz doświadczenia w pracy z kanwą do edycji raportów lub chcesz przypomnieć sobie te informacje, przed dalszym działaniem [zapoznaj się z edytorem raportów](service-the-report-editor-take-a-tour.md).
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Dodawanie miernika promieniowego do raportu
Po zaimportowaniu zestawu danych można już udzielać odpowiedzi na pytania.  Dyrektor ds. marketingu chce wiedzieć, jak blisko mamy do osiągnięcia tegorocznych celów w zakresie sprzedaży. Miernik [dobrze wizualizuje](visuals/power-bi-report-visualizations.md) ten typ danych.

1. W okienku Pola wybierz pozycję **Sales** > **This Year Sales** > **Value**.
   
    ![wykres słupkowy w edytorze raportów](media/service-report-create-new/power-bi-report-step1.png)
2. Skonwertuj wizualizację na miernik, wybierając szablon miernika ![ikona miernika](media/service-report-create-new/powerbi-gauge-icon.png) w okienku **Wizualizacje**.
   
    ![Element wizualny w formie miernika w edytorze raportów](media/service-report-create-new/power-bi-report-step2.png)
3. Przeciągnij pozycję **Sales** > **This Year Sales** > **Goal** do obszaru **Wartość docelowa**. Wygląda na to, że jesteśmy bardzo blisko celu.
   
    ![Element wizualny w formie miernika z wartością Cel jako wartością docelową](media/service-report-create-new/power-bi-report-step3.png)
4. Teraz jest dobry moment na [zapisanie raportu](service-report-save.md).
   
   ![Menu Plik](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Dodawanie wykresu warstwowego i fragmentatora do raportu
Nasz dyrektor ma jeszcze kilka dodatkowych pytań. Chce wiedzieć, jak tegoroczna sprzedaż wypada w porównaniu z ubiegłym rokiem. Wyniki mają uwzględniać poszczególne okręgi.

1. Na początek zróbmy nieco miejsca na kanwie. Zaznacz miernik i przenieś go w prawy górny róg. Następnie chwyć i przeciągnij jeden z rogów, aby zmniejszyć miernik.
2. Kliknij poza miernikiem, aby miernik nie był już zaznaczony. W okienku Pola wybierz pozycję **Sales** > **This Year Sales** > **Value**, a następnie wybierz pozycję **Sales** > **Last Year Sales**.
   
    ![edytor raportów z miernikiem i wykresem słupkowym](media/service-report-create-new/power-bi-report-step4.png)
3. Skonwertuj wizualizację na wykres warstwowy, wybierając szablon wykresu warstwowego ![ikona wykresu](media/service-report-create-new/power-bi-areachart-icon.png) w okienku **Wizualizacje**.
4. Wybierz pozycję **Time** > **Period**, aby dodać ją do obszaru **Oś**.
   
    ![edytor raportów z aktywnym wykresem warstwowym](media/service-report-create-new/power-bi-report-step5.png)
5. Aby posortować wizualizacje według okresu, wybierz wielokropek, a następnie polecenie **Sortuj według okresu**.
6. Teraz dodajmy fragmentator. Wybierz puste miejsce na kanwie, a następnie wybierz szablon fragmentatora ![ikona fragmentatora](media/service-report-create-new/power-bi-slicer-icon.png)    . Spowoduje to dodanie pustego fragmentatora do kanwy.
   
    ![kanwa raportu](media/service-report-create-new/power-bi-report-step6.png)    
7. W okienku Pola wybierz pozycję **District** > **District**. Przenieś fragmentator i zmień jego rozmiar.
   
    ![Edytor raportów, dodawanie pozycji District](media/service-report-create-new/power-bi-report-step7.png)  
8. Za pomocą fragmentatora poszukaj wzorców i danych szczegółowych według okręgu.
   
   ![film wideo dotyczący użycia fragmentatora](media/service-report-create-new/power-bi-slicer-video2.gif)  

Kontynuuj przeglądanie danych i dodawanie wizualizacji. Po znalezieniu szczególnie interesujących danych szczegółowych [przypnij je do pulpitu nawigacyjnego](service-dashboard-pin-tile-from-report.md).

## <a name="next-steps"></a>Następne kroki

* Dowiedz się, jak [przypinać wizualizacje do pulpitu nawigacyjnego](service-dashboard-pin-tile-from-report.md)   
* Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

