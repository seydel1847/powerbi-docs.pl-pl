---
title: Integracja usługi Power BI z usługą Microsoft Flow
description: Dowiedz się, jak tworzyć przepływy wyzwalane przez alerty dotyczące danych w usłudze Power BI.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: YhmNstC39Mw
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: 2d73710b9fc41a8cb6a3d8287dc939323d71f7dd
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54289813"
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow i Power BI

[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started) to oferta SaaS umożliwiająca automatyzację przepływów pracy między coraz liczniejszymi aplikacjami i usługami SaaS, z których korzystają użytkownicy biznesowi. Usługa Flow umożliwia automatyzowanie zadań dzięki integracji ulubionych aplikacji i usług (w tym usługi Power BI), co pozwala otrzymywać powiadomienia, synchronizować pliki, zbierać dane i wykonywać inne działania. Automatyzacja przepływów pracy ułatwia obsługę powtarzalnych zadań.

[Już dziś zacznij korzystać z usługi Flow.](https://flow.microsoft.com/documentation/getting-started)

Zobacz, jak Sirui tworzy przepływ, który po wyzwoleniu alertu usługi Power BI wysyła do współpracowników szczegółowe informacje w wiadomości e-mail. Następnie postępuj zgodnie ze szczegółowymi instrukcjami poniżej wideo, aby wypróbować to samodzielnie.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Tworzenie przepływu wyzwalanego przez alert dotyczący danych w usłudze Power BI

### <a name="prerequisites"></a>Wymagania wstępne
Ten samouczek przedstawia tworzenie dwóch różnych przepływów: na podstawie szablonu i od podstaw. Aby kontynuować, [utwórz alert dotyczący danych w usłudze Power BI](service-set-data-alerts.md), utwórz konto usługi Slack i [załóż bezpłatne konto w usłudze Microsoft Flow](https://flow.microsoft.com/en-us/#home-signup).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Tworzenie przepływu korzystającego z usługi Power BI na podstawie szablonu
W tym zadaniu za pomocą szablonu utworzymy prosty przepływ, który jest wyzwalany przez alert dotyczący danych w usłudze Power BI (powiadomienie).

1. Zaloguj się do usługi Microsoft Flow (flow.microsoft.com).
2. Wybierz pozycję **Moje przepływy**.
   
   ![Pasek menu przepływu](media/service-flow-integration/power-bi-my-flows.png)
3. Wybierz pozycję **Utwórz z szablonu**.
   
    ![Pasek menu Moje przepływy](media/service-flow-integration/power-bi-template.png)
4. Znajdź szablony usługi Power BI przy użyciu pola wyszukiwania i wybierz pozycję **Wyślij wiadomość e-mail do wybranych odbiorców po wyzwoleniu alertu danych dotyczących danych usługi Power BI > Kontynuuj**.
   
    ![wyniki wyszukiwania](media/service-flow-integration/power-bi-flow-alert.png)


### <a name="build-the-flow"></a>Tworzenie przepływu
Ten szablon zawiera jeden wyzwalacz (alert usługi Power BI dotyczący danych o nowych medalach olimpijskich zdobytych przez Irlandię) i jedną akcję (wysłanie wiadomości e-mail). Po wybraniu pola usługa Flow wyświetla zawartość dynamiczną, która można dodać.  W tym przykładzie dołączymy wartość i adres URL kafelka do treści wiadomości.

![szablon przepływu](media/service-flow-integration/power-bi-template1.png)

1. Z listy rozwijanej wyzwalacza wybierz alert dotyczący danych w usłudze Power BI. Wybierz pozycję **New medal for Ireland**. Aby dowiedzieć się, jak utworzyć alert, zobacz [Alerty dotyczące danych w usłudze Power BI](service-set-data-alerts.md).
   
   ![lista rozwijana alertu](media/service-flow-integration/power-bi-trigger-flow.png)
2. Wprowadź co najmniej jeden prawidłowy adres e-mail, a następnie wybierz opcję **Edytuj** (pokazana poniżej) lub **Dodaj zawartość dynamiczną**. 
   
   ![Ekran wysyłania wiadomości e-mail](media/service-flow-integration/power-bi-flow-email.png)

3. Przepływ tworzy tytuł i komunikat, który można zachować lub zmodyfikować. Wszystkie wartości ustawione podczas tworzenia alertu w usłudze Power BI są dostępne do użycia — po prostu umieść kursor w miejscu, a następnie wybierz w obszarze wyróżnionym na szaro. 

   ![Ekran wysyłania wiadomości e-mail](media/service-flow-integration/power-bi-flow-email-default.png)

1.  Na przykład, jeśli utworzono tytuł alertu w usłudze Power BI o treści **Zdobyliśmy kolejny medal**, można wybrać opcję **Tytuł alertu**, aby ten tekst dodać do pola Temat wiadomości e-mail.

    ![tworzenie wiadomości e-mail](media/service-flow-integration/power-bi-flow-message.png)

    Możesz zaakceptować domyślną treść wiadomości e-mail lub utworzyć własną. Powyższy przykład obejmuje kilka zmian wiadomości.

1. Gdy wszystko będzie gotowe, wybierz pozycję **Utwórz przepływ** lub **Zapisz przepływ**.  Przepływ zostanie utworzony i oceniony.  Usługa Flow poinformuje Cię w przypadku znalezienia błędów.
2. Jeśli pojawią się błędy, wybierz pozycję **Edytuj przepływ**, aby rozwiązać problemy. W przeciwnym razie wybierz pozycję **Gotowe**, aby uruchomić nowy przepływ.
   
   ![komunikat dotyczący sukcesu](media/service-flow-integration/power-bi-flow-running.png)
5. Po wyzwoleniu alertu dotyczącego danych wiadomości e-mail zostaną wysłane na wskazane przez Ciebie adresy.  
   
   ![wiadomość e-mail z alertem](media/service-flow-integration/power-bi-flow-email2.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Tworzenie przepływu korzystającego z usługi Power BI od podstaw (pustego)
W tym zadaniu utworzymy od podstaw prosty przepływ, który jest wyzwalany przez alert dotyczący danych w usłudze Power BI (powiadomienie).

1. Zaloguj się do usługi Microsoft Flow.
2. Wybierz pozycję **Moje przepływy** > **Utwórz z pustego**.
   
   ![Górny pasek menu przepływu](media/service-flow-integration/power-bi-my-flows.png)
3. Znajdź wyzwalacz usługi Power BI przy użyciu pola wyszukiwania i wybierz pozycję **Power BI - when a data driven alert is triggered** (Power BI — gdy alert sterowany danymi jest wyzwalany).

### <a name="build-your-flow"></a>Tworzenie przepływu
1. Z listy rozwijanej wybierz nazwę alertu.  Aby dowiedzieć się, jak utworzyć alert, zobacz [Alerty dotyczące danych w usłudze Power BI](service-set-data-alerts.md).
   
    ![wybieranie nazwy alertu](media/service-flow-integration/power-bi-totalstores2.png)
2. Wybierz pozycję **Nowy krok** > **Dodaj akcję**.
   
   ![dodawanie nowego kroku](media/service-flow-integration/power-bi-new-step.png)
3. Poszukaj pozycji **Outlook** i wybierz pozycję **Utwórz zdarzenie**.
   
   ![tworzenie przepływu](media/service-flow-integration/power-bi-create-event.png)
4. Wypełnij pola zdarzenia. Po wybraniu pola usługa Flow wyświetla zawartość dynamiczną, która można dodać.
   
   ![kontynuowanie tworzenia przepływu](media/service-flow-integration/power-bi-flow-event.png)
5. Gdy skończysz, wybierz pozycję **Utwórz przepływ**.  Usługa Flow zapisze i oceni przepływ. Jeśli nie ma żadnych błędów, wybierz pozycję **Gotowe**, aby uruchomić przepływ.  Nowy przepływ zostanie dodany do strony **Moje przepływy**.
   
   ![kończenie przepływu](media/service-flow-integration/power-bi-flow-running.png)
6. Po wyzwoleniu przepływu przez alert dotyczący danych w usłudze Power BI w programie Outlook otrzymasz powiadomienie o zdarzeniu, które wygląda mniej więcej tak.
   
    ![Przepływ wyzwala powiadomienie programu Outlook](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Następne kroki
* [Rozpoczynanie pracy z usługą Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Ustawianie alertów dotyczących danych w usłudze Power BI](service-set-data-alerts.md)
* [Ustawianie alertów dotyczących danych na telefonie iPhone](consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* [Ustawianie alertów dotyczących danych w aplikacji Power BI dla urządzeń przenośnych w systemie Windows 10](consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

