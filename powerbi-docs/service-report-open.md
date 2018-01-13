---
title: "Otwieranie raportu w widoku do czytania lub w widoku do edycji w usłudze Power BI"
description: "Otwieranie raportu usługi Power BI w widoku do czytania lub do edycji"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 01/07/2018
ms.author: mihart
ms.openlocfilehash: 1d9c183a7fab95caa44221bd2d252ab92889b3f4
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2018
---
# <a name="open-a-report-in-power-bi-service-apppowerbicom"></a>Otwieranie raportu w usłudze Power BI (app.powerbi.com)
Raporty są dostępne w usłudze Power BI, programie Power BI Desktop, w usłudze Power BI dla urządzeń przenośnych, a nawet w usłudze Power BI Embedded. Ten artykuł dotyczy otwierania raportów w ***usłudze Power BI***.

W usłudze Power BI są dostępne dwa tryby wyświetlania raportów i korzystania z nich: [widok do czytania i widok do edycji](service-reading-view-and-editing-view.md). Widok do czytania jest dostępny dla wszystkich użytkowników i jest w szczególności przeznaczony dla *konsumentów* raportu, natomiast widok do edycji jest dostępny tylko dla *twórców* i właścicieli raportu. 

## <a name="open-a-report-from-a-workspace-via-the-reports-content-view-list"></a>Otwieranie raportu z poziomu obszaru roboczego (za pośrednictwem listy widoku zawartości **Raporty**)

1. Rozpocznij w obszarze roboczym i wybierz kartę **Raporty**, aby wyświetlić wszystkie raporty w tym obszarze roboczym.  
   
   ![](media/service-report-open/power-bi-open-report.png)
1. Wybierz nazwę raportu, aby otworzyć go w widoku do czytania.  
   
    ![](media/service-report-open/power-bi-reading-view.png)
1. Tak [wiele możesz zrobić w widoku do czytania](service-reading-view-and-editing-view.md).  Ten przykładowy raport zawiera wiele stron, dlatego zacznij jego eksplorację od wybrania każdej karty w dolnej części kanwy raportu. 

## <a name="open-a-report-from-a-dashboard"></a>Otwieranie raportu z poziomu pulpitu nawigacyjnego
Istnieje wiele innych sposobów otwierania raportu, na przykład możesz rozpocząć na pulpicie nawigacyjnym i wybrać kafelek, który został utworzony na podstawie raportu.  Wybranie kafelka powoduje otwarcie raportu w widoku do czytania. Aby z tego skorzystać, [otwórz przykładowy pulpit nawigacyjny Sprzedaż i marketing (Sales and Marketing)](sample-datasets.md).

1. Otwórz pulpit nawigacyjny i wybierz kafelek.

   Jeśli wybierzesz kafelek, który został [utworzone za pomocą opcji Pytania i odpowiedzi](service-dashboard-pin-tile-from-q-and-a.md), zostanie otwarty ekran Pytania i odpowiedzi. Jeśli wybierzesz kafelek, który został [utworzony za pomocą widgetu **Dodaj kafelek** pulpitu nawigacyjnego](service-dashboard-add-widget.md), w celu edytowania tego widgetu zostanie otwarty kreator.  

2.  W tym przykładzie wybraliśmy kafelek wykresu kolumnowego „Total Units YTD...”.

    ![](media/service-report-open/power-bi-dashboard.png)

3.  Skojarzony raport zostanie otwarty w widoku do czytania. Zwróć uwagę, że jesteśmy na stronie „YTD Category”. Jest to strona raportu zawierająca wykres kolumnowy, który wybraliśmy na pulpicie nawigacyjnym.

    ![](media/service-report-open/power-bi-report.png)

4. Pozostań w widoku do czytania lub wybierz pozycję **Edytuj raport**, aby otworzyć raport w widoku do edycji. Pamiętaj, że tylko osoby z uprawnieniami do edycji tego raportu mogą go otworzyć w widoku do edycji.

    ![](media/service-report-open/power-bi-edit-report.png)

## <a name="create-a-brand-new-report-from-a-dataset"></a>Tworzenie całkiem nowego raportu z zestawu danych
Raport można także otworzyć z poziomu zestawu danych. Gdy zaczynasz od zestawu danych, kanwa raportu będzie pusta, więc ta metoda jest zalecana dla *twórców* raportu, którzy są zainteresowani utworzeniem nowego raportu na podstawie posiadanego zestawu danych. Tak jak w powyższym przykładzie, aby wykonywać opisane tu czynności, pobierz [aplikację przykładową Sprzedaż i marketing (Sales and Marketing)](sample-datasets.md).

1. Zacznij w obszarze roboczym zawierającym zestaw danych, którego chcesz użyć jako podstawy dla raportu.

   ![](media/service-report-open/power-bi-workspace.png)

2. Wybierz kartę **Zestawy danych**, aby wyświetlić listę wszystkich zestawów danych w tym obszarze roboczym. Jest to nazywane listą widoku zawartości **Zestawy danych**.
   
   ![](media/service-report-open/power-bi-dataset.png)

1. Znajdź odpowiedni zestaw danych i wybierz ikonę **Utwórz raport**, aby otworzyć zestaw danych w widoku do edycji. Jeśli nie masz uprawnień do edycji dla zestawu danych, nie możesz go otworzyć. 
   
    ![](media/service-report-open/power-bi-create-report.png)

3. Zestaw danych zostanie otwarty w edytorze raportów. Po prawej stronie zobaczysz pola danych gotowe do eksplorowania i tworzenia wizualizacji. 

   ![](media/service-report-open/power-bi-blank-canvas.png)

##  <a name="still-more-ways-to-open-a-report"></a>Jeszcze więcej sposobów otwierania raportu
Gdy oswoisz się z nawigowaniem po usłudze Power BI, znajdziesz przepływy pracy, które najlepiej Ci odpowiadają. Oto kilka innych sposobów uzyskiwania dostępu do raportów:
- W lewym okienku nawigacji przy użyciu opcji **Ulubione**, **Ostatnie**, **Aplikacje* i **Udostępnione dla mnie**. 
- Przy użyciu opcji [Wyświetl powiązane](service-related-content.md)
- W wiadomości e-mail, gdy ktoś [udostępni Tobie](service-share-reports.md) lub gdy [ustawisz alert](service-set-data-alerts.md).    
- Z poziomu [Centrum powiadomień](service-notification-center.md)    
- i nie tylko

## <a name="next-steps"></a>Następne kroki
Przeczytaj więcej na temat [raportów w usłudze Power BI](service-reports.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)  
