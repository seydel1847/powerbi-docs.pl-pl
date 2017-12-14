---
title: 'Tworzenie nowego raportu z zestawu danych '
description: "Tworzenie nowego raportu usługi Power BI na podstawie zestawu danych."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: f4afb1eaa1b3012fdbdb0eff35e9eff695cc32e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-new-power-bi-report-by-importing-a-dataset"></a>Tworzenie nowego raportu usługi Power BI przez zaimportowanie zestawu danych
Po zapoznaniu się z tematem [Raporty w usłudze Power BI](service-reports.md) możesz teraz utworzyć własny raport. Istnieje wiele sposobów tworzenia raportów. W tym artykule zaczniemy od utworzenia podstawowego raportu na podstawie zestawu danych programu Excel. Kiedy zapoznasz się z podstawami tworzenia raportów, możesz przejść do bardziej zaawansowanych tematów dostępnych w sekcji **Następne kroki** u dołu strony.  

> **PORADA**: aby utworzyć raport przez skopiowanie istniejącego raportu, zobacz [Kopiowanie raportu](power-bi-report-copy.md).
> 
> 

## <a name="import-the-dataset"></a>Importowanie zestawu danych
W przypadku tej metody tworzenia raportu punktem wyjścia jest zestaw danych i pusta kanwa raportu. Na użytek tej procedury [pobierz przykładowy zestaw danych programu Excel noszący nazwę Retail Analysis](http://go.microsoft.com/fwlink/?LinkId=529778) i zapisz go na swoim koncie w usłudze OneDrive dla Firm (opcja preferowana) lub lokalnie.

1. Utworzymy raport w obszarze roboczym usługi Power BI, więc wybierz istniejący obszar roboczy lub utwórz nowy.
   
   ![](media/service-report-create-new/power-bi-workspaces2.png)
2. Wybierz pozycję **Pobierz dane** znajdującą się z lewej strony paska nawigacyjnego na dole.
   
   ![](media/service-report-create-new/power-bi-get-data3.png)
3. Wybierz pozycję **Pliki** i przejdź do miejsca, w którym został zapisany przykładowy zestaw danych Retail Analysis.
   
    ![](media/service-report-create-new/power-bi-select-files.png)
4. W ramach tego ćwiczenia wybierz pozycję **Importuj**.
   
   ![](media/service-report-create-new/power-bi-import.png)
5. Po zaimportowaniu zestawu danych wybierz pozycję **Wyświetl zestaw danych**.
   
   ![](media/service-report-create-new/power-bi-view-dataset.png)
6. Wyświetlenie zestawu danych powoduje otwarcie edytora raportów.  Zostanie wyświetlona pusta kanwa i narzędzia do edycji raportów.
   
   ![](media/service-report-create-new/power-bi-blank-report.png)

> **PORADA**: jeśli nie masz doświadczenia w pracy z kanwą do edycji raportów lub chcesz przypomnieć sobie te informacje, przed dalszym działaniem [zapoznaj się z edytorem raportów](service-the-report-editor-take-a-tour.md).
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Dodawanie miernika promieniowego do raportu
Po zaimportowaniu zestawu danych można już udzielać odpowiedzi na pytania.  Dyrektor ds. marketingu chce wiedzieć, jak blisko mamy do osiągnięcia tegorocznych celów w zakresie sprzedaży. Miernik [dobrze wizualizuje](power-bi-report-visualizations.md) ten typ danych.

1. W okienku Pola wybierz pozycję **Sales** > **This Year Sales** > **Value**.
   
    ![](media/service-report-create-new/power-bi-report-step1.png)
2. Skonwertuj wizualizację na miernik, wybierając szablon miernika ![](media/service-report-create-new/powerbi-gauge-icon.png) w okienku **Wizualizacje**.
   
    ![](media/service-report-create-new/power-bi-report-step2.png)
3. Przeciągnij pozycję **Sales** > **This Year Sales** > **Goal** do obszaru **Wartość docelowa**. Wygląda na to, że jesteśmy bardzo blisko celu.
   
    ![](media/service-report-create-new/power-bi-report-step3.png)
4. Teraz jest dobry moment na [zapisanie raportu](service-report-save.md).
   
   ![](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Dodawanie wykresu warstwowego i fragmentatora do raportu
Nasz dyrektor ma jeszcze kilka dodatkowych pytań. Chce wiedzieć, jak tegoroczna sprzedaż wypada w porównaniu z ubiegłym rokiem. Wyniki mają uwzględniać poszczególne okręgi.

1. Na początek zróbmy nieco miejsca na kanwie. Zaznacz miernik i przenieś go w prawy górny róg. Następnie chwyć i przeciągnij jeden z rogów, aby zmniejszyć miernik.
2. Kliknij poza miernikiem, aby miernik nie był już zaznaczony. W okienku Pola wybierz pozycję **Sales** > **This Year Sales** > **Value**, a następnie wybierz pozycję **Sales** > **Last Year Sales**.
   
    ![](media/service-report-create-new/power-bi-report-step4.png)
3. Skonwertuj wizualizację na wykres warstwowy, wybierając szablon wykresu warstwowego ![](media/service-report-create-new/power-bi-areachart-icon.png) w okienku **Wizualizacje**.
4. Wybierz pozycję **Time** > **Period**, aby dodać ją do obszaru **Oś**.
   
    ![](media/service-report-create-new/power-bi-report-step5.png)
5. Aby posortować wizualizację, wybierz wielokropek i wybierz polecenie **Sortuj według: Okres**.
6. Teraz dodajmy fragmentator. Wybierz puste miejsce na kanwie, a następnie wybierz szablon fragmentatora ![](media/service-report-create-new/power-bi-slicer-icon.png). Spowoduje to dodanie pustego fragmentatora do kanwy.
   
    ![](media/service-report-create-new/power-bi-report-step6.png)    
7. W okienku Pola wybierz pozycję **District** > **District**. Przenieś fragmentator i zmień jego rozmiar.
   
    ![](media/service-report-create-new/power-bi-report-step7.png)  
8. Za pomocą fragmentatora poszukaj wzorców i danych szczegółowych według okręgu.
   
   ![](media/service-report-create-new/power-bi-slicer-video2.gif)  
9. Opcjonalnie można kontynuować dodawanie wizualizacji.

## <a name="next-steps"></a>Następne kroki
* [Tworzenie kopii raportu](power-bi-report-copy.md)
* [Zapisywanie raportu](service-report-save.md)    
* [Dodawanie nowej strony do raportu](power-bi-report-add-page.md)  
* Dowiedz się, jak [przypinać wizualizacje do pulpitu nawigacyjnego](service-dashboard-pin-tile-from-report.md)    
* Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

