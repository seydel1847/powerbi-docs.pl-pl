---
title: Wyświetlanie raportu
description: W tym temacie opisano, jak konsumenci i użytkownicy końcowi usługi Power BI mogą otwierać i wyświetlać raport usługi Power BI.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
ms.openlocfilehash: df28cd585998b8877a788e709eaf6b22474e6122
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2018
ms.locfileid: "53281058"
---
# <a name="view-a-report-in-power-bi-service-for-consumers"></a>Wyświetlanie raportu w usłudze Power BI dla *użytkowników*
Raport zawiera co najmniej jedną stronę wizualizacji. Raporty są tworzone przez *projektantów raportów* usługi Power BI i [udostępniane *użytkownikom* bezpośrednio](end-user-shared-with-me.md) lub jako część [aplikacji](end-user-apps.md). 

Istnieje wiele różnych sposobów otwierania raportu, a my przedstawimy dwa z nich: otwieranie ze strony głównej i otwieranie z pulpitu nawigacyjnego. 

<!-- add art-->


## <a name="open-a-report-from-your-home-page"></a>Otwieranie raportu ze strony głównej
Otworzymy raport, który został Ci udostępniony bezpośrednio, a następnie otworzymy raport, który został udostępniony jako część aplikacji.

   ![Strona główna](./media/end-user-report-open/power-bi-home.png)

### <a name="open-a-report-that-has-been-shared-with-you"></a>Otwieranie raportu, który został Tobie udostępniony
*Projektanci* usługi Power BI mogą udostępnić raport bezpośrednio, klikając przycisk **Udostępnij** na pasku menu u góry. Zawartość udostępniona w ten sposób zostaje wyświetlona w kontenerze **Udostępnione mi** na lewym pasku nawigacji oraz w sekcji **Udostępnione mi** na Twojej stronie głównej.

1. Otwórz usługę Power BI (app.powerbi.com).

2. Na pasku nawigacji po lewej stronie wybierz pozycję **Strona główna (wersja zapoznawcza)**, aby otworzyć stronę główną.  

   ![Strona główna](./media/end-user-report-open/power-bi-select-home.png)
   
3. Przewiń w dół, aż zobaczysz pozycję **Udostępnione mi**. Poszukaj ikony raportu ![ikona raportu](./media/end-user-report-open/power-bi-report-icon.png). Na tym zrzucie ekranu znajdują się dwa raporty: *Financial* i *Northwind*. 
   
   ![sekcja Udostępnione mi na stronie głównej](./media/end-user-report-open/power-bi-shared.png)

4. Aby otworzyć raport wystarczy wybrać jedną z *kart* raportu.

   ![strona raportu](./media/end-user-report-open/power-bi-report1.png)

5. Zwróć uwagę na karty u dołu. Każda karta reprezentuje *stronę* raportu. Obecnie mamy otwartą stronę *IT Spend Trend* (Trend dotyczący wydatków informatycznych). Wybierz inną kartę, aby otworzyć kolejną stronę raportu. 

   ![karty strony raportu](./media/end-user-report-open/power-bi-tabs.png)

6. Teraz możemy zobaczyć jedynie część strony raportu. Aby zmienić sposób wyświetlania strony (powiększenie), wybierz pozycje **Widok** > **Dopasuj do strony**.

   ![zmień powiększenie](./media/end-user-report-open/power-bi-fit.png)

   ![dopasuj do strony](./media/end-user-report-open/power-bi-report2.png)

### <a name="open-a-report-that-is-part-of-an-app"></a>Otwieranie raportu, który jest częścią aplikacji
W przypadku otrzymania aplikacji od współpracowników lub z usługi AppSource te aplikacje są dostępne ze strony głównej oraz z kontenera **Aplikacje** na pasku nawigacji po lewej stronie. [Aplikacja](end-user-apps.md) to pakiet pulpitów nawigacyjnych i raportów.

1. Wróć do strony głównej, wybierając pozycję **Strona główna (wersja zapoznawcza)** na pasku nawigacji po lewej stronie.

7. Przewiń w dół, aż zobaczysz pozycję **Moje aplikacje**.

   ![Strona główna](./media/end-user-report-open/power-bi-my-apps.png)

8. Wybierz jedną z aplikacji, aby ją otworzyć. W zależności od opcji ustawionych przez *projektanta* aplikacji, aplikacja otworzy pulpit nawigacyjny, raport lub listę zawartości aplikacji. Jeśli wybranie aplikacji:
    - powoduje otwarcie raportu, wszystko jest gotowe.
    - powoduje otwarcie pulpitu nawigacyjnego, zobacz [Otwieranie raportu z poziomu pulpitu nawigacyjnego](#Open-a-report-from-a-dashboard) poniżej.
    - powoduje otwarcie listy zawartości aplikacji, w obszarze **Raporty** wybierz raport, aby go otworzyć.


## <a name="open-a-report-from-a-dashboard"></a>Otwieranie raportu z poziomu pulpitu nawigacyjnego
Raporty można otwierać z poziomu pulpitu nawigacyjnego. Większość kafelków pulpitu nawigacyjnego jest *przypiętych* z raportów. Wybranie kafelka powoduje otwarcie raportu, który został użyty do utworzenia kafelka. 

1. Na pulpicie nawigacyjnym wybierz kafelek. W tym przykładzie wybraliśmy kafelek wykresu kolumnowego „Total Units YTD...”.

    ![pulpit nawigacyjny z wybranym kafelkiem](./media/end-user-report-open/power-bi-dashboard.png)

2.  Skojarzony raport zostanie otwarty. Zwróć uwagę, że jesteśmy na stronie „YTD Category”. Jest to strona raportu zawierająca wykres kolumnowy, który wybraliśmy na pulpicie nawigacyjnym.

    ![otwieranie raportu w Widoku do czytania](./media/end-user-report-open/power-bi-report-new.png)

> [!NOTE]
> Nie wszystkie kafelki prowadzą do raportu. Jeśli wybierzesz kafelek, który został [utworzone za pomocą opcji Pytania i odpowiedzi](end-user-q-and-a.md), zostanie otwarty ekran Pytania i odpowiedzi. Jeśli wybierzesz kafelek, który został [utworzony za pomocą widżetu pulpitu nawigacyjnego **Dodaj kafelek**](../service-dashboard-add-widget.md), może się zdarzyć kilka różnych rzeczy.  


##  <a name="still-more-ways-to-open-a-report"></a>Jeszcze więcej sposobów otwierania raportu
Gdy oswoisz się z nawigowaniem po usłudze Power BI, znajdziesz przepływy pracy, które najlepiej Ci odpowiadają. Oto kilka innych sposobów uzyskiwania dostępu do raportów:
- Z poziomu lewego okienka nawigacji przy użyciu opcji **Ulubione** i **Ostatnie**    
- Przy użyciu opcji [Wyświetl powiązane](end-user-related.md)    
- W wiadomości e-mail, gdy ktoś [udostępni Tobie](../service-share-reports.md) lub gdy [ustawisz alert](end-user-alerts.md)    
- Z poziomu [Centrum powiadomień](end-user-notification-center.md)    
- i nie tylko

## <a name="next-steps"></a>Następne kroki
Istnieje [wiele sposobów interakcji z raportem](end-user-reading-view.md).  Rozpocznij eksplorację od wybrania każdej karty w dolnej części kanwy raportu.

