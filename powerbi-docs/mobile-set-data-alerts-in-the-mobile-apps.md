---
title: "Ustawianie alertów danych w aplikacjach mobilnych Power BI"
description: "Dowiedz się, jak ustawić alerty w aplikacjach mobilnych Power BI i w usłudze Power BI, aby otrzymywać powiadomienia, gdy zmiany dotyczące danych na pulpicie nawigacyjnym przekroczą skonfigurowane progi."
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 822285a38e08f173ff8cae69c8e7e8ad94957692
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="set-data-alerts-in-the-power-bi-mobile-apps"></a>Ustawianie alertów danych w aplikacjach mobilnych Power BI
Dotyczy:

| ![Telefon iPhone](media/mobile-set-data-alerts-in-the-mobile-apps/iphone-logo-50-px.png) | ![Tablet iPad](media/mobile-set-data-alerts-in-the-mobile-apps/ipad-logo-50-px.png) | ![Telefon z systemem Android](media/mobile-set-data-alerts-in-the-mobile-apps/android-phone-logo-50-px.png) | ![Tablet z systemem Android](media/mobile-set-data-alerts-in-the-mobile-apps/android-tablet-logo-50-px.png) | ![Tablet z systemem Android](media/mobile-set-data-alerts-in-the-mobile-apps/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| Telefony iPhone |Tablety iPad |Telefony z systemem Android |Tablety z systemem Android |Urządzenia z systemem Windows 10 |

Możesz ustawić alerty w aplikacjach mobilnych Power BI i w usłudze Power BI, aby otrzymywać powiadomienia, gdy zmiany dotyczące danych na pulpicie nawigacyjnym przekroczą skonfigurowane progi. Alerty działają w przypadku kafelków prezentujących pojedyncze liczby, takich jak karty i mierniki, ale nie w przypadku danych przesyłanych strumieniowo. Alerty dotyczące danych można ustawić na urządzeniu przenośnym i wyświetlać je w usłudze Power BI oraz na odwrót. Tylko Ty możesz zobaczyć ustawione przez siebie alerty dotyczące danych, nawet jeśli udostępnisz pulpit nawigacyjny lub migawkę kafelka.

> [!WARNING]
> Powiadomienia o alertach oparte na danych dostarczają informacji o danych. Jeśli urządzenie zostanie skradzione, zalecamy przejście do usługi Power BI i wyłączenie wszystkich reguł alertów opartych na danych. 
> 
> Dowiedz się więcej o [zarządzaniu alertami dotyczącymi danych w usłudze Power BI](service-set-data-alerts.md).
> 
> 

## <a name="data-alerts-on-an-iphone-or-ipad"></a>Alerty dotyczące danych na telefonie iPhone lub tablecie iPad
### <a name="set-an-alert-on-an-iphone-or-ipad"></a>Ustawianie alertu na telefonie iPhone lub tablecie iPad
1. Naciśnij kafelek z liczbą lub miernikiem na pulpicie nawigacyjnym, aby otworzyć go w trybie koncentracji uwagi.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-card-visual.png)
2. Naciśnij ikonę dzwonka ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-alert-icon.png), aby dodać alert.  
3. Naciśnij pozycję **Dodaj regułę alertów**.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-add-alert-rule.png)
4. Wybierz opcję otrzymywania alertu w przypadku wartości powyżej lub poniżej progu, a następnie ustaw wartość progu.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-set-alert-threshold.png)
5. Zdecyduj, czy chcesz otrzymywać alerty co godzinę, czy raz dziennie, a także czy wraz z alertem chcesz otrzymać wiadomość e-mail.
   
   > [!NOTE]
   > Nie będziesz otrzymywać alertów co godzinę ani codziennie, jeśli dane nie zostaną w tym czasie faktycznie odświeżone.
   > 
   > 
6. Możesz też zmienić tytuł alertu.
7. Naciśnij pozycję **Zapisz**.
8. Dla pojedynczego kafelka można ustawić alerty dla wartości zarówno powyżej, jak i poniżej progów. W obszarze **Zarządzanie alertami** naciśnij pozycję **Dodaj regułę alertów**.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-add-another-alert-rule.png)

### <a name="manage-alerts-on-your-iphone-or-ipad"></a>Zarządzanie alertami na telefonie iPhone lub tablecie iPad
Możesz zarządzać poszczególnymi alertami na urządzeniu przenośnym lub [zarządzać wszystkimi alertami w usłudze Power BI](service-set-data-alerts.md).

1. Na pulpicie nawigacyjnym naciśnij kafelek z liczbą lub miernikiem, dla którego ustawiono alert.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-card-visual.png)
2. Naciśnij ikonę dzwonka ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-has-alert-icon.png).  
3. Naciśnij nazwę alertu, aby go edytować, naciśnij suwak, aby wyłączyć alerty w wiadomościach e-mail, lub naciśnij ikonę kosza na śmieci, aby usunąć ten alert.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-edit-delete-alert.png)

## <a name="data-alerts-on-an-android-device"></a>Alerty dotyczące danych na urządzeniu z systemem Android
### <a name="set-an-alert-on-an-android-device"></a>Ustawianie alertu na urządzeniu z systemem Android
1. Na pulpicie nawigacyjnym usługi Power BI naciśnij kafelek z liczbą lub miernikiem, aby go otworzyć.  
2. Naciśnij ikonę dzwonka ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-alert-icon.png), aby dodać alert.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-tap-alert.png)
3. Naciśnij ikonę znaku plus (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-plus-alert.png)
4. Wybierz opcję otrzymywania alertu w przypadku wartości powyżej lub poniżej progu, a następnie wpisz wartość progu.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-tablet-set-alert-condition.png)
5. Naciśnij pozycję **Gotowe**.
6. Zdecyduj, czy chcesz otrzymywać alerty co godzinę, czy raz dziennie, a także czy wraz z alertem chcesz otrzymać wiadomość e-mail.
   
   > [!NOTE]
   > Nie będziesz otrzymywać alertów co godzinę ani codziennie, jeśli dane nie zostaną w tym czasie faktycznie odświeżone.
   > 
   > 
7. Możesz też zmienić tytuł alertu.
8. Naciśnij pozycję **Zapisz**.

### <a name="manage-alerts-on-an-android-device"></a>Zarządzanie alertami na urządzeniu z systemem Android
Możesz zarządzać poszczególnymi alertami w aplikacji mobilnej Power BI lub [zarządzać wszystkimi alertami w usłudze Power BI](service-set-data-alerts.md).

1. Na pulpicie nawigacyjnym naciśnij kafelek z kartą lub miernikiem, dla którego ustawiono alert.  
2. Naciśnij ikonę nieprzezroczystego dzwonka ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-filled-alert-bell.png).  
3. Naciśnij alert, aby zmienić wartość lub aby go wyłączyć.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-manage-alerts.png)
4. Naciśnij ikonę znaku plus (+), aby dodać kolejny alert do tego samego kafelka.
5. Aby całkowicie usunąć alert, naciśnij ikonę kosza na śmieci ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-delete-alert-icon.png).

## <a name="data-alerts-on-a-windows-device"></a>Alerty dotyczące danych na urządzeniu z systemem Windows
### <a name="set-data-alerts-on-a-windows-device"></a>Ustawianie alertów dotyczących danych na urządzeniu z systemem Windows
1. Naciśnij kafelek z liczbą lub miernikiem na pulpicie nawigacyjnym, aby go otworzyć.  
2. Naciśnij ikonę dzwonka ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-alert-bell-off.png), aby dodać alert.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-tap-alert.png)
3. Naciśnij ikonę znaku plus (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-no-alerts-yet.png)
4. Wybierz opcję otrzymywania alertu w przypadku wartości powyżej lub poniżej progu, a następnie wpisz wartość progu.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-set-alert.png)
5. Zdecyduj, czy chcesz otrzymywać alerty co godzinę, czy raz dziennie, a także czy wraz z alertem chcesz otrzymać wiadomość e-mail.
   
   > [!NOTE]
   > Nie będziesz otrzymywać alertów co godzinę ani codziennie, jeśli dane nie zostaną w tym czasie faktycznie odświeżone.
   > 
   > 
6. Możesz też zmienić tytuł alertu.
7. Naciśnij znacznik wyboru.
8. Dla pojedynczego kafelka można ustawić alerty dla wartości zarówno powyżej, jak i poniżej progów. W obszarze **Zarządzanie alertami** naciśnij znak plus (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-add-another-alert.png)

### <a name="manage-alerts-on-a-windows-device"></a>Zarządzanie alertami na urządzeniu z systemem Windows
Możesz zarządzać poszczególnymi alertami w aplikacji mobilnej Power BI lub [zarządzać wszystkimi alertami w usłudze Power BI](service-set-data-alerts.md).

1. Na pulpicie nawigacyjnym naciśnij kafelek z kartą lub miernikiem, dla którego ustawiono alert.  
2. Naciśnij ikonę dzwonka ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-alert-bell-on.png).  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-has-alerts.png)
3. Naciśnij alert, aby zmienić wartość lub aby go wyłączyć.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-add-another-alert.png)
4. Aby całkowicie usunąć alert, kliknij go prawym przyciskiem myszy lub naciśnij i przytrzymaj, a następnie wybierz pozycję **Usuń**.

## <a name="receiving-alerts"></a>Otrzymywanie alertów
Alerty otrzymujesz w [Centrum powiadomień](mobile-apps-notification-center.md) usługi Power BI na urządzeniu przenośnym lub w usłudze Power BI wraz z powiadomieniami o nowych pulpitach nawigacyjnych udostępnionych Ci przez inne osoby.

Dla źródeł danych jest często skonfigurowane codzienne odświeżanie, a inne są odświeżane jeszcze częściej. Gdy po odświeżeniu danych na pulpicie nawigacyjnym śledzone dane osiągną jeden z ustawionych progów, zostanie wykonanych kilka działań.

1. Usługa Power BI sprawdza, czy od ostatniego wysłania alertu upłynęła więcej niż godzina lub więcej niż 24 godziny (w zależności od wybranej opcji).
   
   Jeśli dane przekroczą wyznaczony próg, otrzymasz alert co godzinę lub co 24 godziny.
2. Jeśli ustawiony przez Ciebie alert ma wysyłać wiadomości e-mail, w swojej skrzynce odbiorczej znajdziesz wiadomość podobną do tej.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/powerbi-alerts-email.png)
3. Usługa Power BI dodaje komunikat do **Centrum powiadomień** oraz ikonę nowego alertu do odpowiedniego kafelka ![](media/mobile-set-data-alerts-in-the-mobile-apps/powerbi-alert-tile-notification-icon.png).
4. Naciśnij przycisk nawigacji globalnej ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-alert-global-nav-button.png) w celu [otwarcia **Centrum powiadomień**](mobile-apps-notification-center.md), aby wyświetlić szczegóły alertu.
   
     ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-notifications.png) 

> [!NOTE]
> Alerty działają tylko z odświeżonymi danymi. Podczas odświeżania danych usługa Power BI sprawdza, czy został dla nich ustawiony alert. Jeśli dane osiągną wartość progową alertu, alert zostanie wywołany.
> 
> 

## <a name="tips-and-troubleshooting"></a>Porady i rozwiązywanie problemów
* Alerty nie są obecnie obsługiwane przez kafelki usługi Bing ani kafelki kart z miarami daty i godziny.
* Alerty działają tylko z danymi liczbowymi.
* Alerty działają tylko z odświeżonymi danymi. Nie działają z danymi statycznymi.
* Alerty nie działają z kafelkami zawierającymi dane przesyłane strumieniowo.

## <a name="next-steps"></a>Następne kroki
* [Manage your alerts in the Power BI service](service-set-data-alerts.md) (Zarządzanie alertami dotyczącymi danych w usłudze Power BI)
* [Power BI Mobile Notification Center](mobile-apps-notification-center.md) (Mobilne centrum powiadomień usługi Power BI)
* Masz pytania? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

