---
title: "Samouczek: integracja usługi Power BI z usługą Microsoft Flow"
description: "Dowiedz się, jak tworzyć przepływy wyzwalane przez alerty dotyczące danych w usłudze Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: YhmNstC39Mw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/30/2017
ms.author: mihart
ms.openlocfilehash: efab2e6be1d376a0da70c13bb66144ba34afa58c
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2017
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow i Power BI

[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started) to oferta SaaS umożliwiająca automatyzację przepływów pracy między coraz liczniejszymi aplikacjami i usługami SaaS, z których korzystają użytkownicy biznesowi. Usługa Flow umożliwia automatyzowanie zadań dzięki integracji ulubionych aplikacji i usług (w tym usługi Power BI), co pozwala otrzymywać powiadomienia, synchronizować pliki, zbierać dane i wykonywać inne działania. Automatyzacja przepływów pracy ułatwia obsługę powtarzalnych zadań.

[Już dziś zacznij korzystać z usługi Flow.](https://flow.microsoft.com/documentation/getting-started)

Zobacz, jak Sirui tworzy przepływ, który po wyzwoleniu alertu usługi Power BI wysyła do współpracowników szczegółowe informacje w wiadomości e-mail. Następnie postępuj zgodnie ze szczegółowymi instrukcjami poniżej wideo, aby wypróbować to samodzielnie.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Tworzenie przepływu wyzwalanego przez alert dotyczący danych w usłudze Power BI
Ten samouczek przedstawia tworzenie dwóch różnych przepływów: na podstawie szablonu i od podstaw. Aby kontynuować, [utwórz alert dotyczący danych w usłudze Power BI](service-set-data-alerts.md) i [załóż bezpłatne konto w usłudze Microsoft Flow](https://flow.microsoft.com/en-us/#home-signup).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Tworzenie przepływu korzystającego z usługi Power BI na podstawie szablonu
W tym zadaniu za pomocą szablonu utworzymy prosty przepływ, który jest wyzwalany przez alert dotyczący danych w usłudze Power BI (powiadomienie).

1. Zaloguj się do usługi Microsoft Flow (flow.microsoft.com).
2. Wybierz pozycję **Moje przepływy**.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Wybierz pozycję **Utwórz z szablonu**.
   
    ![](media/service-flow-integration/power-bi-template.png)
4. Znajdź szablony usługi Power BI przy użyciu pola wyszukiwania i wybierz pozycję **Opublikuj wiadomość na kanale Slack, gdy zostanie wyzwolony alert dotyczący danych w usłudze Power BI**.
   
    ![](media/service-flow-integration/power-bi-template2.png)
5. Wybierz pozycję **Użyj tego szablonu**.
   
   ![](media/service-flow-integration/power-bi-use-template.png)
6. Jeśli zostanie wyświetlony monit, połącz się z usługami Slack i Power BI, wybierając pozycję **Zaloguj się** i postępując zgodnie z instrukcjami. Pojawienie się zielonego znacznika wyboru oznacza, że logowanie przebiegło pomyślnie.  Po upewnieniu się, że połączenia działają, wybierz pozycję **Kontynuuj**.
   
   ![](media/service-flow-integration/power-bi-flow-signin.png)

### <a name="build-the-flow"></a>Tworzenie przepływu
Ten szablon zawiera jeden wyzwalacz (alert usługi Power BI dotyczący danych o nowych medalach olimpijskich zdobytych przez Irlandię) i jedną akcję (opublikowanie wiadomości w usłudze Slack). Po wybraniu pola usługa Flow wyświetla zawartość dynamiczną, która można dodać.  W tym przykładzie dołączymy wartość i adres URL kafelka do treści wiadomości.

![](media/service-flow-integration/power-bi-flow-template.png)

1. Z listy rozwijanej wyzwalacza wybierz alert dotyczący danych w usłudze Power BI. Wybierz pozycję **New medal for Ireland**. Aby dowiedzieć się, jak utworzyć alert, zobacz [Alerty dotyczące danych w usłudze Power BI](service-set-data-alerts.md).
   
   ![](media/service-flow-integration/power-bi-trigger-flow.png)
2. Aby opublikować zawartość w usłudze Slack, wprowadź nazwę kanału i tekst wiadomość (możesz również wybrać domyślną wiadomość utworzoną przez usługę Flow). Zwróć uwagę na zawartość dynamiczną, którą dołączyliśmy w polu tekstowym wiadomości.
   
   > [!NOTE]
   > Dodaj znak „@” na początku nazwy kanału.  Na przykład jeśli nazwa kanału usługi Slack to „channelA”, w usłudze Flow wpisz „@channelA”.
   > 
   > 
   
   ![](media/service-flow-integration/power-bi-flow-slacker.png)
3. Gdy wszystko będzie gotowe, wybierz pozycję **Utwórz przepływ** lub **Zapisz przepływ**.  Przepływ zostanie utworzony i oceniony.  Usługa Flow poinformuje Cię w przypadku znalezienia błędów.
4. Jeśli pojawią się błędy, wybierz pozycję **Edytuj przepływ**, aby rozwiązać problemy. W przeciwnym razie wybierz pozycję **Gotowe**, aby uruchomić nowy przepływ.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
5. Otwórz konto usługi Slack, aby zobaczyć komunikat.  
   
   ![](media/service-flow-integration/power-bi-slack-message.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Tworzenie przepływu korzystającego z usługi Power BI od podstaw (pustego)
W tym zadaniu utworzymy od podstaw prosty przepływ, który jest wyzwalany przez alert dotyczący danych w usłudze Power BI (powiadomienie).

1. Zaloguj się do usługi Microsoft Flow.
2. Wybierz pozycję **Moje przepływy** > **Utwórz z pustego**.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Znajdź wyzwalacz usługi Power BI przy użyciu pola wyszukiwania i wybierz pozycję **Wyzwól przepływ za pomocą alertu opartego na danych usługi Power BI**.

### <a name="build-your-flow"></a>Tworzenie przepływu
1. Z listy rozwijanej wybierz nazwę alertu.  Aby dowiedzieć się, jak utworzyć alert, zobacz [Alerty dotyczące danych w usłudze Power BI](service-set-data-alerts.md).
   
    ![](media/service-flow-integration/power-bi-totalstores.png)
2. Wybierz pozycję **Nowy krok** > **Dodaj akcję**.
   
   ![](media/service-flow-integration/power-bi-new-step.png)
3. Poszukaj pozycji **Outlook** i wybierz pozycję **Utwórz zdarzenie**.
   
   ![](media/service-flow-integration/power-bi-create-event.png)
4. Wypełnij pola zdarzenia. Po wybraniu pola usługa Flow wyświetla zawartość dynamiczną, która można dodać.
   
   ![](media/service-flow-integration/power-bi-flow-event.png)
5. Gdy skończysz, wybierz pozycję **Utwórz przepływ**.  Usługa Flow zapisze i oceni przepływ. Jeśli nie ma żadnych błędów, wybierz pozycję **Gotowe**, aby uruchomić przepływ.  Nowy przepływ zostanie dodany do strony **Moje przepływy**.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
6. Po wyzwoleniu przepływu przez alert dotyczący danych w usłudze Power BI w programie Outlook otrzymasz powiadomienie o zdarzeniu, które wygląda mniej więcej tak.
   
    ![](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Następne kroki
* [Rozpoczynanie pracy z usługą Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Ustawianie alertów dotyczących danych w usłudze Power BI](service-set-data-alerts.md)
* [Ustawianie alertów dotyczących danych na telefonie iPhone](mobile-set-data-alerts-in-the-mobile-apps.md)
* [Ustawianie alertów dotyczących danych w aplikacji Power BI dla urządzeń przenośnych w systemie Windows 10](mobile-set-data-alerts-in-the-mobile-apps.md)
* Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

