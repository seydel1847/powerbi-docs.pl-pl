---
title: "Udostępnianie pulpitów nawigacyjnych współpracownikom i innym osobom — Power BI"
description: "Jak udostępnić pulpity nawigacyjne usługi Power BI współpracownikom z danej organizacji i spoza niej oraz najważniejsze informacje o udostępnianiu."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: monitoring
qualitydate: 08/14/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/18/2017
ms.author: maggies
ms.openlocfilehash: 4cc7f12eb4964c67ae9f91cfcb51eac77d690555
ms.sourcegitcommit: ea247cb3cfc1cac076d4b076c1ad8e2fc37e15a1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2017
---
# <a name="share-your-power-bi-dashboards-with-coworkers-and-others"></a>Udostępnianie pulpitów nawigacyjnych usługi Power BI współpracownikom i innym osobom
*Udostępnianie* to świetna metoda na zapewnienie kilku osobom dostępu do Twojego pulpitu nawigacyjnego i raportów. Usługa Power BI zapewnia [kilka sposobów współpracy i rozpowszechniania pulpitów nawigacyjnych](service-how-to-collaborate-distribute-dashboards-reports.md). Udostępnianie to jedna z tych metod.

![Ikona udostępniania na liście pulpitów nawigacyjnych](media/service-share-dashboards/power-bi-share-dash.png)

Bez względu na to, czy zawartość jest udostępniona w organizacji, czy poza nią, zarówno osoba udostępniająca, jak i adresaci zawartości muszą mieć [licencję na usługę Power BI Pro](service-free-vs-pro.md) lub zawartość musi być uwzględniona w [pojemności Premium](service-premium.md). Masz jakieś sugestie? Zespół zajmujący się usługą Power BI chętnie zapozna się z Twoją opinią. Aby ją przekazać, przejdź do [witryny społeczności usługi Power BI](https://community.powerbi.com/).

Pulpit nawigacyjny można udostępnić z poziomu Mój obszar roboczy lub z obszaru roboczego aplikacji. Osoby, którym udostępniasz pulpit nawigacyjny, mogą go wyświetlać i korzystać z niego, ale nie mogą go edytować. O ile nie zastosowano [zabezpieczeń na poziomie wiersza](service-admin-rls.md), osoby te widzą na pulpicie nawigacyjnym i w raportach te same dane co Ty. Współpracownicy, którym udostępniono pulpit nawigacyjny, mogą udostępnić go swoim współpracownikom, jeśli mają na to zezwolenie. Osoby spoza organizacji mogą wyświetlać pulpit nawigacyjny oraz korzystać z niego, ale nie mogą go udostępniać. 

[Pulpit nawigacyjny można także udostępnić za pomocą aplikacji mobilnych Power BI](mobile-share-dashboard-from-the-mobile-apps.md). Pulpity nawigacyjne mogą być udostępniane za pomocą usługi Power BI i aplikacji mobilnych Power BI, ale nie z poziomu programu Power BI Desktop.

## <a name="video-share-a-dashboard"></a>Klip wideo: Udostępnianie pulpitu nawigacyjnego
Zobacz, jak Amanda udostępnianie swój pulpit nawigacyjny współpracownikom ze swojej firmy i osobom spoza niej. Następnie postępuj zgodnie ze szczegółowymi instrukcjami poniżej wideo, aby wypróbować to samodzielnie.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard"></a>Udostępnianie pulpitu nawigacyjnego
1. W obszarze Mój obszar roboczy lub w obszarze roboczym aplikacji otwórz pulpit nawigacyjny i wybierz pozycję **Udostępnij** ![Ikona udostępniania](media/service-share-dashboards/power-bi-share-icon.png).
2. W polu u góry wprowadź pełne adresy e-mail użytkowników indywidualnych, grup dystrybucyjnych lub grup zabezpieczeń. Zawartości nie można udostępniać dynamicznym listom dystrybucyjnym. 
   
   Udostępnianie osobom, których adresy nie należą do Twojej organizacji, jest możliwe, ale w takiej sytuacji zostanie wyświetlone ostrzeżenie.
   
   ![Ostrzeżenie dotyczące udostępniania zewnętrznego](media/service-share-dashboards/power-bi-share-dialog-warning.png)  
3. Jeśli chcesz, możesz dodać wiadomość. Jest to opcjonalne.
4. Aby umożliwić współpracownikom udostępnianie Twojego pulpitu nawigacyjnego innym osobom, zobacz **Zezwalanie adresatom na udostępnianie pulpitu nawigacyjnego**.
   
   Zezwalanie innym na udostępnianie jest nazywane *udostępnianiem dalej*. Jeśli zezwolisz innym na udostępnianie dalej, może się to odbyć z poziomu usługi Power BI i aplikacji mobilnych lub też przez przesłanie dalej wiadomości e-mail z zaproszeniem do innych osób w danej organizacji. Zaproszenie wygasa po upływie miesiąca. Nie można udostępnić dalej zawartości osobom spoza organizacji. Jako właściciel pulpitu nawigacyjnego możesz wyłączyć udostępnianie dalej lub włączyć je w indywidualnych przypadkach. Zobacz: [Anulowanie udostępniania pulpitu nawigacyjnego lub uniemożliwianie innym udostępniania](service-share-dashboards.md#stop-sharing-a-dashboard-or-stop-others-from-sharing) poniżej.
5. Wybierz pozycję **Udostępnij**.
   
   ![Wybieranie przycisku Udostępnij](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Usługa Power BI wysyła wiadomość e-mail z zaproszeniem do osób, ale nie do grup. Wiadomość zawiera link do udostępnionego pulpitu nawigacyjnego. Zostaje wyświetlone powiadomienie **Powodzenie**. 
   
   Kiedy adresat w Twojej organizacji kliknie link, usługa Power BI doda dany pulpit nawigacyjny do jego listy **Udostępnione mi**. Użytkownik taki może wybrać Twoje imię i nazwisko, aby wyświetlić wszystkie pulpity nawigacyjne, które zostały przez Ciebie udostępnione. 
   
   ![Strona listy Udostępnione mi](media/service-share-dashboards/power-bi-shared-with-me-list-page.png)
   
   Kiedy adresat spoza Twojej organizacji kliknie link, zobaczy pulpit nawigacyjny, ale nie w standardowym portalu usługi Power BI. Aby uzyskać szczegółowe informacje, zobacz [Udostępnianie pulpitu nawigacyjnego osobom spoza organizacji](service-share-dashboards.md#share-a-dashboard-with-people-outside-your-organization) poniżej.

## <a name="who-has-access-to-a-dashboard-you-shared"></a>Kto ma dostęp do udostępnionego pulpitu nawigacyjnego?
Czasami zachodzi potrzeba wyświetlenia osób, którym został przez Ciebie udostępniony pulpit nawigacyjny, oraz użytkowników, którym z kolei udostępniły pulpit te osoby.

1. Na liście pulpitów nawigacyjnych lub w obrębie samego pulpitu nawigacyjnego wybierz pozycję **Udostępnij** ![Ikona udostępniania](media/service-share-dashboards/power-bi-share-icon.png). 
2. W oknie dialogowym **Udostępnianie pulpitu nawigacyjnego** wybierz kartę **Dostęp**.
   
    ![Okno dialogowe Udostępnianie pulpitu nawigacyjnego, karta Dostęp](media/service-share-dashboards/power-bi-share-dialog-access.png)
   
    Osoby spoza organizacji są oznaczone jako **Gość**.

## <a name="stop-sharing-a-dashboard-or-stop-others-from-sharing"></a>Anulowanie udostępniania pulpitu nawigacyjnego lub uniemożliwianie innym udostępniania
Tylko właściciel pulpitu nawigacyjnego może włączyć i wyłączyć możliwość jego udostępniania dalej.

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>Jeśli zaproszenie do udostępniania nie zostało jeszcze wysłane
* Wyczyść pole wyboru **Zezwalaj adresatom na udostępnianie pulpitu nawigacyjnego** w dolnej części zaproszenia przed jego wysłaniem.

### <a name="if-youve-already-shared-the-dashboard"></a>Jeśli pulpit nawigacyjny został już udostępniony
1. Na liście pulpitów nawigacyjnych lub w obrębie samego pulpitu nawigacyjnego wybierz pozycję **Udostępnij** ![Ikona udostępniania](media/service-share-dashboards/power-bi-share-icon.png). 
2. W oknie dialogowym **Udostępnianie pulpitu nawigacyjnego** wybierz kartę **Dostęp**.
   
    ![Okno dialogowe Udostępnianie pulpitu nawigacyjnego, karta Dostęp](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. Wybierz przycisk wielokropka (**...**) obok pozycji **Odczyt i udostępnianie dalej** i wybierz pozycję:
   
   ![Wielokropek obok pozycji Odczyt i udostępnianie dalej](media/service-share-dashboards/power-bi-change-access.png)
   
   * **Odczyt**, aby uniemożliwić danej osobie udostępnianie tej zawartości innym.
   * **Usuń dostęp**, aby uniemożliwić danej osobie wyświetlenie pulpitu nawigacyjnego.

4. W oknie dialogowym **Usuń dostęp** zdecyduj, czy chcesz też usunąć dostęp do powiązanej zawartości, takiej jak raporty i zestawy danych. Jeśli usuwasz elementy z ikoną ostrzeżenia ![Ikona ostrzeżenia usługi Power BI](media/service-share-dashboards/power-bi-warning-icon.png), najlepiej jest usunąć powiązaną zawartość, ponieważ nie będzie ona wyświetlana poprawnie.

## <a name="share-a-dashboard-with-people-outside-your-organization"></a>Udostępnianie pulpitu nawigacyjnego osobom spoza organizacji
Jeśli udostępnisz pulpit nawigacyjny osobom spoza organizacji, otrzymają one wiadomość e-mail z linkiem do udostępnionego pulpitu nawigacyjnego. Aby wyświetlić pulpit nawigacyjny, muszą się one zalogować do usługi Power BI. Jeśli dana osoba nie ma licencji na usługę Power BI Pro, może utworzyć konto w tej usłudze po kliknięciu linku.

Po utworzeniu konta użytkownik zobaczy udostępniony pulpit nawigacyjny w osobnym oknie przeglądarki (a nie w standardowym portalu usługi Power BI), bez lewego okienka nawigacji. Aby w przyszłości uzyskać dostęp do tego pulpitu nawigacyjnego, użytkownik musi dodać do zakładek otrzymany link.

Użytkownik spoza organizacji nie może edytować jakiejkolwiek zawartości w tym pulpicie nawigacyjnym lub raporcie. Może korzystać z wykresów w raporcie (wyróżniać je krzyżowo) i zmieniać dowolne filtry/fragmentatory dostępne w raportach połączonych z pulpitem nawigacyjnym, ale nie może zapisywać wprowadzonych zmian.

Udostępniony pulpit nawigacyjny może być wyświetlany tylko przez bezpośrednich adresatów. Na przykład w przypadku wysłania wiadomości e-mail na adres Vicki@contoso.com tylko Vicki może wyświetlić pulpit nawigacyjny. Nikt inny nie widzi tego pulpitu nawigacyjnego, nawet jeśli ma link. Aby Vicki uzyskała dostęp do tego pulpitu nawigacyjnego, musi użyć tego samego adresu e-mail, na który została wysłana wiadomość. Jeśli Vicki utworzy konto przy użyciu innego adresu e-mail, nie będzie miała dostępu do pulpitu nawigacyjnego.

Osoby spoza organizacji nie zobaczą żadnych danych, jeśli w modelach tabelarycznych lokalnych usług Analysis Services zostały zaimplementowane zabezpieczenia na poziomie roli lub wiersza.

Jeśli wyślesz link z aplikacji mobilnej Power BI do osoby spoza organizacji, a ona kliknie ten link, pulpit nawigacyjny zostanie otwarty w przeglądarce, a nie w aplikacji mobilnej Power BI.

## <a name="limitations-and-considerations"></a>Ograniczenia i istotne zagadnienia
Ważne kwestie dotyczące udostępniania pulpitów nawigacyjnych:

* Ogólnie rzecz biorąc, zarówno Ty, jak i Twoi współpracownicy widzicie na pulpicie nawigacyjnym te same dane. Jeśli zatem masz uprawnienia do wyświetlania większej ilości danych niż oni, współpracownicy będą mogli zobaczyć wszystkie te dane na Twoim pulpicie nawigacyjnym. Jeśli jednak do zestawu danych wyświetlanych na pulpicie nawigacyjnym zastosowano [zabezpieczenia na poziomie wiersza](service-admin-rls.md), wówczas dane dostępne dla poszczególnych użytkowników zależą od ich poświadczeń.
* Każda osoba, której udostępniasz swój pulpit nawigacyjny, może go wyświetlać i korzystać z raportów za pomocą [widoku do czytania](service-report-open-in-reading-view.md). Nie może jednak tworzyć raportów ani zapisywać zmian w istniejących raportach.
* Nikt nie może wyświetlić ani pobrać zestawu danych.
* Każdy może ręcznie [odświeżyć dane pulpitu nawigacyjnego](refresh-data.md).
* Jeśli korzystasz z usługi Office 365 do obsługi poczty e-mail, możesz udostępnić pulpit nawigacyjny członkom grupy dystrybucyjnej, wprowadzając adres e-mail skojarzony z daną grupą.
* Współpracownicy, którzy mają adres e-mail w tej samej domenie co Ty, oraz współpracownicy, którzy korzystają z innej domeny, ale zarejestrowanej w ramach tej samej dzierżawy, mogą udostępniać pulpit nawigacyjny innym osobom. Załóżmy na przykład, że domeny contoso.com i contoso2.com są zarejestrowane w ramach tej samej dzierżawy. Jeśli Twój adres e-mail to konrads@contoso.com, wówczas zarówno posiadacz adresu ravali@contoso.com, jak i adresu gustav@contoso2.com może udostępniać pulpit nawigacyjny, o ile dostał od Ciebie uprawnienia do udostępniania.
* Jeśli Twoi współpracownicy mają już dostęp do określonego pulpitu nawigacyjnego, możesz wysłać bezpośredni link do niego, kopiując adres URL dostępny podczas korzystania z tego pulpitu nawigacyjnego. Na przykład: `https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx`
* Analogicznie, jeśli Twoi współpracownicy mają już dostęp do określonego pulpitu nawigacyjnego, możesz [wysłać bezpośredni link do jego raportu źródłowego](service-share-reports.md). 

## <a name="troubleshoot-sharing"></a>Rozwiązywanie problemów z udostępnianiem

### <a name="my-dashboard-recipients-see-a-lock-icon-in-a-tile-or-a-permission-required-message"></a>Odbiorcy mojego pulpitu nawigacyjnego widzą ikonę blokady na kafelku albo komunikat „Wymagane uprawnienie”

Osoby, którym udostępniasz pulpit nawigacyjny, mogą widzieć na nim zablokowany kafelek albo komunikat „Wymagane uprawnienie” przy próbie wyświetlenia raportu.

![Zablokowany kafelek usługi Power BI](media/service-share-dashboards/power-bi-locked_tile_small.png)

Jeśli tak, musisz udzielić im uprawnienia do bazowego zestawu danych. Oto jak to zrobić.

1. Przejdź na kartę **Zestawy danych** na liście zawartości.

1. Wybierz wielokropek (**...**) obok zestawu danych > **Zarządzaj uprawnieniami**.

    ![Zarządzanie uprawnieniami](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

3. Wybierz pozycję **Dodaj użytkownika**.

    ![Wybieranie pozycji Dodaj użytkownika](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. Wprowadź pełne adresy e-mail osób, grup dystrybucyjnych lub grup zabezpieczeń. Zawartości nie można udostępniać dynamicznym listom dystrybucyjnym.

    ![Dodawanie adresów e-mail](media/service-share-dashboards/power-bi-add-user-dataset.png)

5. Wybierz pozycję **Dodaj**.

### <a name="i-cant-share-a-dashboard"></a>Nie mogę udostępnić pulpitu nawigacyjnego

Aby udostępnić pulpit nawigacyjny, musisz mieć uprawnienie do udostępniania dalej jego bazowej zawartości — wszystkich powiązanych raportów i zestawów danych. Jeśli zobaczysz komunikat z informacją, że nie możesz udostępnić zawartości, poproś autora raportu o uprawnienie do udostępniania dalej tych raportów i zestawów danych.


## <a name="next-steps"></a>Następne kroki
* Chcesz przesłać opinię? Jeśli masz sugestie, przejdź do [witryny społeczności usługi Power BI](https://community.powerbi.com/).
* [Jak współpracować nad pulpitami nawigacyjnymi i raportami oraz je udostępniać?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Udostępnianie tylko raportu usługi Power BI](service-share-reports.md)
* Masz pytania? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/).

