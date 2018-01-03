---
title: "Ustawianie alertów dotyczących danych w usłudze Power BI"
description: "Dowiedz się, jak ustawić alerty, aby otrzymywać powiadomienia, gdy zmiany dotyczące danych w pulpitach nawigacyjnych przekroczą ustalone progi w usłudze Microsoft Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: JbL2-HJ8clE
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/06/2017
ms.author: mihart
ms.openlocfilehash: cfbd7d124784b15b432921554c8ac5bbe321846c
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="data-alerts-in-power-bi-service"></a>Alerty dotyczące danych w usłudze Power BI
Ustaw alerty, aby otrzymywać powiadomienia, gdy zmiany dotyczące danych w pulpitach nawigacyjnych przekroczą ustalone progi. Alerty można ustawić tylko dla kafelków przypiętych z poziomu wizualizacji raportu i tylko dla mierników, kluczowych wskaźników wydajności i kart. Alerty można ustawić dla wizualizacji utworzonych na podstawie zestawów danych przesyłania strumieniowego, które zostały przypięte z poziomu raportu do pulpitu nawigacyjnego, ale nie można ich ustawić dla kafelków przesyłania strumieniowego utworzonych bezpośrednio na pulpicie nawigacyjnym przy użyciu pozycji **Dodaj kafelek** > **Niestandardowe dane przesyłane strumieniowo**. Tylko Ty możesz zobaczyć ustawione przez siebie alerty, nawet jeśli udostępniasz pulpit nawigacyjny. Alerty dotyczące danych są w pełni zsynchronizowane między platformami. Możesz je ustawiać i wyświetlać [w aplikacjach mobilnych Power BI](mobile-set-data-alerts-in-the-mobile-apps.md) i w usłudze Power BI. Nie są dostępne w programie Power BI Desktop. Alerty można nawet [zautomatyzować i zintegrować z usługą Microsoft Flow](https://flow.microsoft.com) - [spróbuj to zrobić samodzielnie](service-flow-integration.md).

![](media/service-set-data-alerts/powerbi-alert-types-new.png)

> [!WARNING]
> Powiadomienia o alertach oparte na danych dostarczają informacji o danych. Jeśli dane usługi Power BI są przeglądane na urządzeniu przenośnym i to urządzenie zostanie skradzione, zaleca się wyłączenie wszystkich reguł alertów opartych na danych przy użyciu usługi Power BI.
> 
> 

## <a name="set-data-alerts-in-power-bi-service"></a>Ustawianie alertów dotyczących danych w usłudze Power BI
Zobacz, jak Amanda dodaje alerty do kafelków pulpitu nawigacyjnego. Następnie postępuj zgodnie ze szczegółowymi instrukcjami poniżej wideo, aby wypróbować to samodzielnie.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JbL2-HJ8clE" frameborder="0" allowfullscreen></iframe>

W tym przykładzie użyto kafelku karty z pulpitu nawigacyjnego przykładu Retail Analysis.

1. Rozpocznij na pulpicie nawigacyjnym. Z poziomu miernika, kluczowego wskaźnika wydajności lub kafelka karty pulpitu nawigacyjnego wybierz wielokropek.
   
   ![](media/service-set-data-alerts/powerbi-card.png)
2. Wybierz ikonę dzwonka ![](media/service-set-data-alerts/power-bi-bell-icon.png), aby dodać jeden lub więcej alertów dla pozycji **Total stores**.
   
   ![](media/service-set-data-alerts/powerbi-set-alert.png)
3. Na początek upewnij się, że suwak jest w pozycji **Włączony** i nadaj tytuł alertowi. Tytuły ułatwiają rozpoznawanie alertów.
   
   ![](media/service-set-data-alerts/powerbi-alert-title.png)
4. Przewiń w dół, a następnie wprowadź szczegóły alertu.  W tym przykładzie utworzymy alert, który raz dziennie będzie powiadamiał, jeśli łączna liczba sklepów przekroczy wartość 100. Alerty zostaną wyświetlone w centrum powiadomień. Poza tym usługa Power BI wyśle wiadomość e-mail.
   
   ![](media/service-set-data-alerts/powerbi-set-alert-details.png)
5. Wybierz pozycję **Zapisz**.

## <a name="receiving-alerts"></a>Otrzymywanie alertów
Gdy śledzone dane osiągną jeden z ustawionych progów, zostanie wykonanych kilka działań. Najpierw usługa Power BI sprawdzi, czy od ostatniego wysłania alertu upłynęła więcej niż godzina lub więcej niż 24 godziny (w zależności od wybranej opcji). Jeśli dane przekroczą wyznaczony próg, otrzymasz alert.

Następnie usługa Power BI wysyła alert do centrum powiadomień i, opcjonalnie, w wiadomości e-mail. Każdy alert zawiera bezpośredni link do danych. Wybierz link, aby wyświetlić odpowiedni kafelek, gdzie możesz eksplorować, udostępniać i zdobywać dodatkowe informacje.  

1. Jeśli ustawiony przez Ciebie alert ma wysyłać wiadomości e-mail, w swojej skrzynce odbiorczej znajdziesz wiadomość podobną do tej.
   
   ![](media/service-set-data-alerts/powerbi-alerts-email.png)
2. Usługa Power BI dodaje komunikat do **centrum powiadomień** oraz ikonę nowego alertu do odpowiedniego kafelka.
   
   ![](media/service-set-data-alerts/powerbi-alert-notifications.png)
3. Otwórz centrum powiadomień, aby wyświetlić szczegóły alertu.
   
    ![](media/service-set-data-alerts/powerbi-alert-notfication.png)
   
   > [!NOTE]
   > Alerty działają tylko z odświeżonymi danymi. Podczas odświeżania danych usługa Power BI sprawdza, czy został dla nich ustawiony alert. Jeśli dane osiągną wartość progową alertu, alert zostanie wywołany.
   > 
   > 

## <a name="managing-alerts"></a>Zarządzanie alertami
Istnieją trzy sposoby zarządzania alertami: z poziomu kafelka pulpitu nawigacyjnego, z poziomu menu ustawień usługi Power BI, a także z poziomu pojedynczych kafelków w [aplikacji mobilnej usługi Power BI na telefonie iPhone](mobile-set-data-alerts-in-the-mobile-apps.md) lub [aplikacji mobilnej usługi Power BI dla systemu Windows 10](mobile-set-data-alerts-in-the-mobile-apps.md).

### <a name="from-the-tile-itself"></a>Z poziomu kafelka
1. Jeśli chcesz zmienić lub usunąć alert dla danego kafelka, otwórz ponownie okno **Zarządzanie alertami**, wybierając ikonę dzwonka ![](media/service-set-data-alerts/power-bi-bell-icon.png). Zostaną wyświetlone wszystkie alerty ustawione dla danego kafelka.
   
    ![](media/service-set-data-alerts/powerbi-see-alerts.png).
2. Aby zmodyfikować alert, wybierz strzałkę po lewej stronie nazwy alertu.
   
    ![](media/service-set-data-alerts/powerbi-see-alerts-arrow.png).
3. Aby usunąć alert, wybierz kosz na śmieci po prawej stronie nazwy alertu.
   
      ![](media/service-set-data-alerts/powerbi-see-alerts-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Z poziomu menu ustawień usługi Power BI
1. Wybierz ikonę koła zębatego z paska menu usługi Power BI.
   
    ![](media/service-set-data-alerts/powerbi-gear-icon.png).
2. W obszarze **Ustawienia** wybierz pozycję **Alerty**.
   
    ![](media/service-set-data-alerts/powerbi-alert-settings.png)
3. W tym miejscu można włączyć i wyłączyć alerty, otworzyć okno **Zarządzanie alertami**, aby zmienić alert, a także usunąć alert.

## <a name="tips-and-troubleshooting"></a>Porady i rozwiązywanie problemów
* Alerty nie są obecnie obsługiwane przez kafelki usługi Bing ani kafelki kart z miarami daty i godziny.
* Alerty działają tylko z liczbowymi typami danych.
* Alerty działają tylko z odświeżonymi danymi. Nie działają z danymi statycznymi.
* Alerty będą działać w przypadku zestawów danych przesyłania strumieniowego tylko wtedy, gdy zostanie utworzona wizualizacja raportu dla kluczowego wskaźnika wydajności, karty lub miernika, która następnie zostanie przypięta do pulpitu nawigacyjnego.

## <a name="next-steps"></a>Następne kroki
[Tworzenie przepływu Microsoft Flow zawierającego alert dotyczący danych](service-flow-integration.md)    
[Ustawianie alertów dotyczących danych na urządzeniu przenośnym](mobile-set-data-alerts-in-the-mobile-apps.md)    
[Wprowadzenie do usługi Power BI](service-get-started.md)    
Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)
