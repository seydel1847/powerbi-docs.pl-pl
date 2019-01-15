---
title: 'Samouczek: Ustawianie alertów dotyczących danych w usłudze Power BI'
description: Z tego samouczka dowiesz się, jak ustawić alerty, aby otrzymywać powiadomienia, gdy zmiany dotyczące danych w pulpitach nawigacyjnych przekroczą ustalone progi w usłudze Microsoft Power BI.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: JbL2-HJ8clE
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: tutorial
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 83032e97d9d6b2628d7adfefa95996cff469c4f5
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277855"
---
# <a name="tutorial-set-data-alerts-in-power-bi-service"></a>Samouczek: Ustawianie alertów dotyczących danych w usłudze Power BI
Ustaw alerty, aby otrzymywać powiadomienia, gdy zmiany dotyczące danych w pulpitach nawigacyjnych przekroczą ustalone progi. 

Alerty dla kafelków możesz ustawiać, jeśli masz licencję usługi Power BI Pro lub jeśli udostępniono Ci pulpit nawigacyjny z [pojemności Premium](../service-premium.md). Alerty można ustawić tylko dla kafelków przypiętych z poziomu wizualizacji raportu oraz tylko dla mierników, kluczowych wskaźników wydajności i kart. Alerty można ustawić dla wizualizacji utworzonych na podstawie zestawów danych przesyłania strumieniowego, które zostały przypięte z poziomu raportu do pulpitu nawigacyjnego, ale nie można ich ustawić dla kafelków przesyłania strumieniowego utworzonych bezpośrednio na pulpicie nawigacyjnym przy użyciu pozycji **Dodaj kafelek** > **Niestandardowe dane przesyłane strumieniowo**. 

Tylko Ty możesz zobaczyć ustawione przez siebie alerty, nawet jeśli udostępniasz pulpit nawigacyjny. Alerty dotyczące danych są w pełni zsynchronizowane między platformami. Możesz je ustawiać i wyświetlać [w aplikacjach mobilnych Power BI](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) i w usłudze Power BI. 

![kafelki](../media/service-set-data-alerts/powerbi-alert-types-new.png)

> [!WARNING]
> Powiadomienia o alertach oparte na danych dostarczają informacji o danych. Jeśli dane usługi Power BI są przeglądane na urządzeniu przenośnym i to urządzenie zostanie skradzione, zaleca się wyłączenie wszystkich reguł alertów opartych na danych przy użyciu usługi Power BI.
> 

Niniejszy samouczek obejmuje poniższe tematy.
> [!div class="checklist"]
> * Kto może ustawiać alerty
> * Jakie wizualizacje obsługują alerty
> * Kto może wyświetlać alerty
> * Czy alerty działają w programie Power BI Desktop i w wersji mobilnej
> * Jak utworzyć alert
> * Dokąd przychodzą alerty

Jeśli nie masz konta usługi Power BI, na początku [zacznij korzystać z bezpłatnej wersji próbnej](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="set-data-alerts-in-power-bi-service"></a>Ustawianie alertów dotyczących danych w usłudze Power BI
Zobacz, jak Amanda dodaje alerty do kafelków pulpitu nawigacyjnego. Następnie postępuj zgodnie ze szczegółowymi instrukcjami poniżej wideo, aby wypróbować to samodzielnie.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JbL2-HJ8clE" frameborder="0" allowfullscreen></iframe>

W tym przykładzie użyto kafelka karty z pulpitu nawigacyjnego [przykładu Retail Analysis](http://go.microsoft.com/fwlink/?LinkId=529778).

1. Z poziomu miernika, kluczowego wskaźnika wydajności lub kafelka karty pulpitu nawigacyjnego wybierz wielokropek.
   
   ![kafelek Total Scores](media/end-user-alerts/powerbi-card.png)
2. Wybierz ikonę dzwonka ![Ikona alertu](media/end-user-alerts/power-bi-bell-icon.png) lub pozycję **Zarządzaj alertami**, aby dodać jeden lub więcej alertów dla pozycji **Total stores**.
   
1. W okienku **Zarządzanie alertami** wybierz pozycję **+ Dodaj regułę alertu**.  Upewnij się, że suwak jest w pozycji **Włączony**, i nadaj tytuł alertowi. Tytuły ułatwiają rozpoznawanie alertów.
   
   ![okno zarządzania alertami](media/end-user-alerts/powerbi-alert-title.png)
4. Przewiń w dół, a następnie wprowadź szczegóły alertu.  W tym przykładzie utworzymy alert, który raz dziennie będzie powiadamiał, jeśli łączna liczba sklepów przekroczy wartość 100. Alerty zostaną wyświetlone w centrum powiadomień. Poza tym usługa Power BI wyśle wiadomość e-mail.
   
   ![okno zarządzania alertami, ustawianie progu](media/end-user-alerts/power-bi-set-alert-details.png)
5. Wybierz pozycję **Zapisz i zamknij**.

## <a name="receiving-alerts"></a>Otrzymywanie alertów
Gdy śledzone dane osiągają jeden z ustawionych progów, wykonywanych jest kilka działań. Najpierw usługa Power BI sprawdza, czy od ostatniego wysłania alertu upłynęła więcej niż godzina lub więcej niż 24 godziny (w zależności od wybranej opcji). Jeśli dane przekroczą wyznaczony próg, otrzymasz alert.

Następnie usługa Power BI wysyła alert do centrum powiadomień i, opcjonalnie, w wiadomości e-mail. Każdy alert zawiera bezpośredni link do danych. Wybierz link, aby wyświetlić odpowiedni kafelek.  

1. Jeśli ustawiony przez Ciebie alert ma wysyłać wiadomości e-mail, w swojej skrzynce odbiorczej znajdziesz wiadomość podobną do tej.
   
   ![Wiadomość e-mail z alertem](media/end-user-alerts/powerbi-alerts-email.png)
2. Usługa Power BI dodaje komunikat do **centrum powiadomień** oraz ikonę nowego alertu do odpowiedniego kafelka.
   
   ![Ikona powiadomienia w usłudze Power BI](media/end-user-alerts/powerbi-alert-notifications.png)
3. Otwórz centrum powiadomień, aby wyświetlić szczegóły alertu.
   
    ![odczytywanie alertu](media/end-user-alerts/powerbi-alert-notification.png)
   
   > [!NOTE]
   > Alerty działają tylko z odświeżonymi danymi. Podczas odświeżania danych usługa Power BI sprawdza, czy został dla nich ustawiony alert. Jeśli dane osiągną wartość progową alertu, alert zostanie wywołany.
   > 
   > 

## <a name="managing-alerts"></a>Zarządzanie alertami
Istnieje wiele sposobów zarządzania alertami: z poziomu kafelka pulpitu nawigacyjnego, z poziomu menu ustawień usługi Power BI oraz z poziomu pojedynczego kafelka w [aplikacji mobilnej usługi Power BI na telefonie iPhone](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) lub [aplikacji mobilnej usługi Power BI dla systemu Windows 10](mobile/mobile-set-data-alerts-in-the-mobile-apps.md).

### <a name="from-the-tile-itself"></a>Z poziomu kafelka
1. Jeśli chcesz zmienić lub usunąć alert dla danego kafelka, otwórz ponownie okno **Zarządzanie alertami**, wybierając ikonę dzwonka ![ikona alertu](media/end-user-alerts/power-bi-bell-icon.png). Zostaną wyświetlone wszystkie alerty ustawione dla danego kafelka.
   
    ![okno zarządzania alertami](media/end-user-alerts/powerbi-see-alerts.png).
2. Aby zmodyfikować alert, wybierz strzałkę po lewej stronie nazwy alertu.
   
    ![strzałka obok nazwy alertu](media/end-user-alerts/powerbi-see-alerts-arrow.png).
3. Aby usunąć alert, wybierz kosz na śmieci po prawej stronie nazwy alertu.
   
      ![wybrana ikona pojemnika na śmieci](media/end-user-alerts/powerbi-see-alerts-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Z poziomu menu ustawień usługi Power BI
1. Wybierz ikonę koła zębatego z paska menu usługi Power BI.
   
    ![ikona koła zębatego](media/end-user-alerts/powerbi-gear-icon.png).
2. W obszarze **Ustawienia** wybierz pozycję **Alerty**.
   
    ![Karta Alerty w oknie Ustawienia](media/end-user-alerts/powerbi-alert-settings.png)
3. W tym miejscu można włączyć i wyłączyć alerty, otworzyć okno **Zarządzanie alertami**, aby zmienić alert, a także usunąć alert.

## <a name="tips-and-troubleshooting"></a>Porady i rozwiązywanie problemów
* Alerty nie są obecnie obsługiwane przez kafelki usługi Bing ani kafelki kart z miarami daty i godziny.
* Alerty działają tylko z liczbowymi typami danych.
* Alerty działają tylko z odświeżonymi danymi. Nie działają z danymi statycznymi.
* Alerty będą działać w przypadku zestawów danych przesyłania strumieniowego tylko wtedy, gdy zostanie utworzona wizualizacja raportu dla kluczowego wskaźnika wydajności, karty lub miernika, która następnie zostanie przypięta do pulpitu nawigacyjnego.

## <a name="clean-up-resources"></a>Czyszczenie zasobów
Instrukcje dotyczące usuwania alertów zostały omówione powyżej. W skrócie, wybierz ikonę koła zębatego z paska menu usługi Power BI. W obszarze **Ustawienia** wybierz pozycję **Alerty** i usuń alert.

> [!div class="nextstepaction"]
> [Ustawianie alertów dotyczących danych na urządzeniu przenośnym](mobile/mobile-set-data-alerts-in-the-mobile-apps.md)


