---
title: Ponowne uruchamianie pojemności usługi Power BI Premium
description: Dowiedz się, jak ponownie uruchomić pojemność usługi Power BI Premium, aby rozwiązać problemy z wydajnością.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/10/2018
ms.author: mblythe
LocalizationGroup: Premium
ms.openlocfilehash: f27bc96fc1bea9ff4720d320bda7b448687739a8
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282200"
---
# <a name="restart-a-power-bi-premium-capacity"></a>Ponowne uruchamianie pojemności usługi Power BI Premium

Administrator usługi Power BI czasami musi ponownie uruchomić pojemność Premium. W tym artykule wyjaśniono, jak ponownie uruchomić pojemność i odpowiedziano na kilka pytań związanych z ponownym uruchamianiem i wydajnością.

## <a name="why-does-power-bi-provide-this-option"></a>Dlaczego usługa Power BI udostępnia tę opcję?

Usługa Power BI zapewnia użytkownikom możliwość wykonywania złożonych analiz ogromnych ilości danych. Niestety, użytkownicy mogą powodować problemy z wydajnością, przeciążając usługę Power BI zadaniami, pisząc zbyt złożone zapytania, tworząc odwołania cykliczne itd.

Pojemność udostępniona usługi Power BI oferuje pewną ochronę przed takimi sytuacjami, ograniczając rozmiary plików, harmonogramy odświeżania oraz inne aspekty usługi. Natomiast w przypadku pojemności usługi Power BI Premium te limity są wyższe. W związku z tym pojedynczy raport z nieprawidłowym wyrażeniem DAX lub bardzo złożonym modelem może spowodować poważne problemy z wydajnością. Podczas przetwarzania raportu mogą zostać wykorzystane wszystkie zasoby dostępne w pojemności. 

Ochrona użytkowników pojemności Premium w usłudze Power BI przed takimi problemami jest nieustannie ulepszana. Udostępniamy także administratorom narzędzia służące do wykrywania przeciążeń pojemności i analizowania ich przyczyny. Aby uzyskać więcej informacji, zobacz naszą [krótką sesję szkoleniową](https://www.youtube.com/watch?v=UgsjMbhi_Bk&feature=youtu.be) i [dłuższą sesję szkoleniową](https://www.microsoft.com/businessapplicationssummit/video/BAS2018-2174). Jednocześnie niezbędne są możliwości rozwiązywania poważnych problemów, gdy te problemy wystąpią. Najszybszym sposobem rozwiązania tych problemów jest ponowne uruchomienie pojemności.

## <a name="is-the-restart-process-safe-will-i-lose-any-data"></a>Czy proces ponownego uruchamiania jest bezpieczny? Czy utracę jakiekolwiek dane?

Żadne zapisane dane, definicje, raporty ani pulpity nawigacyjne w ramach pojemności nie zostaną w żaden sposób zmienione po ponownym uruchomieniu. Ponowne uruchomienie pojemności powoduje zatrzymanie wszystkich trwających zaplanowanych odświeżeń i odświeżeń ad hoc. Odświeżenia zostaną ponownie uruchomione po udostępnieniu pojemności. Użytkownicy wchodzący w interakcję z pojemnością utracą niezapisaną pracę. Po ukończeniu ponownego uruchamiania powinni oni odświeżyć swoje przeglądarki.

## <a name="how-do-i-restart-a-capacity"></a>Jak mogę ponownie uruchomić pojemność?

Wykonaj następujące kroki, aby ponownie uruchomić pojemność.

1. W portalu administracyjnym usługi Power BI przejdź do swojej pojemności na karcie **Ustawienia pojemności**. 

1. Dodaj *flagę funkcji* **CapacityRestart** do adresu URL pojemności: https://app.powerbi.com/admin-portal/capacities/<YourCapacityId>?capacityRestartButton=true.

1. W obszarze **Ustawienia zaawansowane** > **PONOWNE URUCHAMIANIE POJEMNOŚCI** wybierz pozycję **Uruchom ponownie pojemność**.

    ![Ponowne uruchamianie pojemności](media/service-admin-premium-restart/restart-capacity.png)

1. W oknie dialogowym **Ponowne uruchamianie pojemności** wybierz opcję **Tak, ponownie uruchom pojemność**.

    ![Potwierdzanie ponownego uruchamiania](media/service-admin-premium-restart/confirm-restart.png)

## <a name="how-can-i-prevent-issues-from-happening-in-the-future"></a>Jak mogę zapobiec występowaniu problemów w przyszłości?

Najlepszym sposobem zapobiegania problemom jest nauczenie użytkowników efektywnego modelowania danych. Aby uzyskać więcej informacji, zobacz naszą [sesję szkoleniową](https://www.microsoft.com/businessapplicationssummit/video/BAS2018-2170).

Ponadto zalecamy regularne [monitorowanie swoich pojemności](service-admin-premium-monitor-capacity.md) pod kątem trendów wskazujących podstawowe problemy. Planujemy regularnie wydawać wersje aplikacji do monitorowania i innych narzędzi, aby umożliwić skuteczniejsze monitorowanie pojemności i zarządzanie nimi.

## <a name="next-steps"></a>Następne kroki

[Power BI Premium — co to jest?](service-premium.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)
