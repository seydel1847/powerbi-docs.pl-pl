---
title: Tworzenie i publikowanie aplikacji z pulpitami nawigacyjnymi i raportami w usłudze Power BI
description: Dowiedz się, jak tworzyć i publikować aplikacje, czyli kolekcje pulpitów nawigacyjnych i raportów utworzone w celu udostępnienia najważniejszych metryk dla organizacji.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/22/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: c2f2fcca7c1d915f94960824d32a5d4f18a978b6
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="create-and-publish-apps-with-dashboards-and-reports-in-power-bi"></a>Tworzenie i publikowanie aplikacji z pulpitami nawigacyjnymi i raportami w usłudze Power BI

W usłudze Power BI można tworzyć *aplikacje*, aby zebrać w jednym miejscu powiązane pulpity nawigacyjne i raporty, a następnie publikować je dla dużych grup użytkowników w organizacji. Można również łączyć się z [aplikacjami usługi Power BI dla usług zewnętrznych](service-connect-to-services.md), takich jak Google Analytics i Microsoft Dynamics CRM.

![Aplikacje usługi Power BI](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

Aby sprawnie działać, użytkownicy biznesowi często potrzebują wielu pulpitów nawigacyjnych i raportów usługi Power BI. Aplikacje zbierają wszystkie te elementy w jednym miejscu, tak aby nie trzeba było pamiętać nazw i lokalizacji wszystkich pulpitów nawigacyjnych.  

Dzięki aplikacjom usługi Power BI, dostępnym teraz w wersji zapoznawczej, możesz tworzyć kolekcje pulpitów nawigacyjnych i raportów i udostępniać te aplikacje całej organizacji lub konkretnym osobom lub grupom. Z perspektywy administratora lub autora raportu aplikacje ułatwiają zarządzanie uprawnieniami do kolekcji pulpitów nawigacyjnych.

Użytkownicy biznesowi mogą uzyskać te aplikacje na kilka różnych sposobów. Jeśli administrator usługi Power BI przyzna Ci odpowiednie uprawnienia, możesz automatycznie instalować je na kontach usługi Power BI swoich współpracowników. Jeśli nie, mogą oni zainstalować aplikacje z witryny Microsoft AppSource lub otrzymać bezpośredni link. Mogą łatwo odnaleźć Twoją zawartość lub do niej wrócić, ponieważ wszystko znajduje się w jednym miejscu. Mogą automatycznie uzyskiwać aktualizacje, a Ty możesz kontrolować, jak często dane są odświeżane. Dowiedz się więcej na temat [aplikacji dla użytkowników biznesowych](service-install-use-apps.md).

### <a name="licenses-for-apps"></a>Licencje na aplikacje
Będąc twórcą aplikacji, potrzebujesz licencji usługi Power BI Pro. Użytkownicy aplikacji mają dwie opcje.

* Opcja 1. Wszyscy użytkownicy biznesowi potrzebują licencji usługi **Power BI Pro**, aby móc wyświetlać Twoją aplikację. 
* Opcja 2. Użytkownicy wersji bezpłatnej w Twojej organizacji mogą wyświetlać zawartość aplikacji, jeśli Twoja aplikacja jest przechowywana w pojemności usługi Power BI Premium. Przeczytaj artykuł [Co to jest usługa Power BI Premium?](service-premium.md), aby zapoznać się ze szczegółowymi informacjami.

### <a name="apps-and-organizational-content-packs"></a>Aplikacje i pakiety zawartości organizacji
Aplikacje są kolejnym etapem ewolucji pakietów zawartości organizacji. Jeśli masz już pakiety zawartości organizacji, będą one nadal działały równolegle z aplikacjami.

Wiesz już, czym są aplikacje, przejdźmy więc do *obszarów roboczych aplikacji*, w których możesz tworzyć aplikacje. 

## <a name="video-apps-and-app-workspaces"></a>Film wideo: aplikacje i obszary robocze aplikacji
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="app-workspaces"></a>Obszary robocze aplikacji
*Obszar roboczy aplikacji* to miejsce, w którym są tworzone aplikacje — a więc zanim utworzysz aplikację, musisz utworzyć obszar roboczy aplikacji. Jeśli masz już doświadczenie w pracy w obszarze roboczym grupy w usłudze Power BI, obszary robocze aplikacji nie będą niczym nowym. Są one kolejnym etapem ewolucji obszarów roboczych grupy — obszarów tymczasowych i kontenerów zawartości w aplikacji. 

Możesz dodawać współpracowników do tych obszarów jako członków lub administratorów. Wszyscy członkowie i administratorzy obszarów roboczych aplikacji muszą mieć licencje usługi Power BI Pro. W obszarze roboczym możecie wspólnie pracować nad pulpitami nawigacyjnymi, raportami i innymi artykułami, które mają zostać rozpowszechnione wśród większej liczby osób lub nawet w całej organizacji. 

Gdy zawartość jest gotowa, możesz wybrać, które pulpity nawigacyjne i raporty chcesz opublikować, a następnie opublikować aplikację. Możesz przesłać bezpośredni link większej grupie odbiorców. Mogą oni również znaleźć Twoją aplikację na karcie Aplikacje, przechodząc do pozycji **Pobierz i odkryj więcej aplikacji w usłudze AppSource**. Te osoby nie mogą zmodyfikować zawartości aplikacji, ale mogą jej używać w usłudze Power Bu lub jednej z aplikacji mobilnych i samodzielnie filtrować, wyróżniać i sortować dane. 

## <a name="create-an-app-workspace"></a>Tworzenie obszaru roboczego aplikacji
[!INCLUDE [powerbi-service-create-app-workspace](./includes/powerbi-service-create-app-workspace.md)]

Jest pusty, musisz więc dodać do niego zawartość. Pamiętaj, że po jego utworzeniu może upłynąć około godziny, zanim obszar roboczy zostanie rozpropagowany w usłudze Office 365. 

Dodawanie zawartości jest podobne do dodawania zawartości w oknie Mój obszar roboczy, z tym, że inne osoby w obszarze roboczym mogą go również wyświetlać i na nim pracować. Różnica polega na tym, że po zakończeniu pracy możesz opublikować zawartość jako aplikację. W obszarze roboczym aplikacji możesz przesłać pliki lub połączyć się z nimi, a także połączyć się z usługami innych firm, tak jak w oknie Mój obszar roboczy. Na przykład:

* [Łączenie się z usługami](service-connect-to-services.md) takimi jak Microsoft Dynamics CRM, Salesforce i Google Analytics.
* [Pobieranie danych z plików](service-get-data-from-files.md) takich jak pliki programu Excel, pliki CSV lub pliki programu Power BI Desktop (PBIX).

Po wyświetleniu zawartości w obszarze roboczym aplikacji właściciel jest wyświetlany jako nazwa obszaru roboczego aplikacji.

## <a name="add-an-image-to-your-app-optional"></a>Dodawanie obrazu do aplikacji (opcjonalnie)
Usługa Power BI domyślnie tworzy niewielki kolorowy okrąg dla aplikacji, zawierający inicjały jej nazwy. Istnieje jednak możliwość dostosowania przez dodanie obrazu. Aby dodać obraz, potrzebujesz licencji usługi Exchange Online.

1. Wybierz pozycję **Obszary robocze**, wybierz symbol wielokropka (...) znajdujący się obok obszaru roboczego, a następnie wybierz opcję **Członkowie**. 
   
     ![Wybieranie członków obszaru roboczego](media/service-create-distribute-apps/power-bi-apps-workspace-members.png)
   
    Konto usługi Office 365 Outlook dla obszaru roboczego otwiera się w nowym oknie przeglądarki.
2. Gdy umieścisz kursor na kolorowym okręgu w lewym górnym rogu, zamieni się on w ikonę ołówka. Wybierz ją.
   
     ![Ikona ołówka usługi Office 365](media/service-create-distribute-apps/power-bi-apps-workspace-edit-image.png)
3. Ponownie wybierz ikonę ołówka i znajdź obraz, którego chcesz użyć.
   
     ![Ponowne wybieranie ikony ołówka](media/service-create-distribute-apps/power-bi-apps-workspace-edit-group.png)
4. Wybierz pozycję **Zapisz**.
   
     ![Wybieranie pozycji Zapisz](media/service-create-distribute-apps/power-bi-apps-workspace-save-image.png)
   
    Obraz zastąpi kolorowy okrąg w oknie usługi Office 365 Outlook. 
   
     ![Dostosowany obraz](media/service-create-distribute-apps/power-bi-apps-workspace-image-in-office-365.png)
   
    Po kilku minutach pojawi się również w aplikacji w usłudze Power BI.
   
     ![Dostosowany obraz](media/service-create-distribute-apps/power-bi-apps-image.png)

## <a name="publish-your-app"></a>Publikowanie aplikacji
Jeśli pulpity nawigacyjne i raporty w obszarze roboczym aplikacji są gotowe, możesz opublikować je jako aplikację. Pamiętaj, że nie musisz publikować wszystkich raportów i pulpitów nawigacyjnych w obszarze roboczym. Możesz opublikować tylko te, które są gotowe.

1. W widoku listy obszarów roboczych zdecyduj, które pulpity nawigacyjne i raporty chcesz dołączyć do aplikacji.

     ![Wybieranie, które pulpity nawigacyjne opublikować](media/service-create-distribute-apps/power-bi-apps-incude-dashboard.png)

     Jeśli zdecydujesz się nie publikować raportu, wyświetlone zostanie ostrzeżenie obok tego raportu i powiązanego z nim pulpitu nawigacyjnego. W dalszym ciągu możesz opublikować aplikację, ale na powiązanym pulpicie nawigacyjnym nie będzie kafelków z tego raportu.

     ![Ostrzeżenie dotyczące powiązanego pulpitu nawigacyjnego](media/service-create-distribute-apps/power-bi-apps-report-warning.png)

2. Wybierz przycisk **Opublikuj aplikację** w prawym górnym rogu, aby rozpocząć proces udostępniania całej zawartości w tym obszarze roboczym.
   
     ![Opublikuj aplikację](media/service-create-distribute-apps/power-bi-apps-publish-button.png)

3. W obszarze **Szczegóły** wypełnij pole z opisem, aby ułatwić odnalezienie aplikacji. Możesz ją spersonalizować, ustawiając kolor tła.
   
     ![Szczegóły aplikacji](media/service-create-distribute-apps/power-bi-apps-details.png)

4. W obszarze **Zawartość** możesz zobaczyć treść, która zostanie opublikowana jako część aplikacji, czyli wszystko, co zostało przez Ciebie zaznaczone w tym obszarze roboczym. Możesz również skonfigurować stronę docelową aplikacji — pulpit nawigacyjny lub raport, który zostanie wyświetlony natychmiast po przejściu do Twojej aplikacji. Możesz wybrać opcję **Brak**. Wtedy użytkownicy przejdą do listy całej zawartości w aplikacji. 
   
     ![Zawartość aplikacji](media/service-create-distribute-apps/power-bi-apps-content.png)

5. W obszarze **Dostęp** możesz zdecydować, kto ma dostęp do aplikacji: wszyscy w Twojej organizacji, określone osoby, czy grupy zabezpieczeń usługi Active Directory. Jeśli masz odpowiednie uprawnienia, możesz zdecydować się na zainstalowanie aplikacji automatycznie dla odbiorców. To ustawienie można włączyć w [portalu administracyjnym usługi Power BI](#how-to-enable-pushing-apps). Aby dowiedzieć się więcej, zapoznaj się z uwagami dotyczącymi [wypychania aplikacji](#how-to-enable-pushing-apps).

    ![Dostęp do aplikacji](media/service-create-distribute-apps/power-bi-apps-access.png)

6. Po wybraniu opcji **Zakończ** wyświetlony zostanie komunikat potwierdzający gotowość do publikacji. W oknie dialogowym potwierdzającym powodzenie możesz skopiować adres URL, który jest bezpośrednim linkiem do tej aplikacji, i wysłać go do osób, którym udostępniono aplikację.
   
     ![Zakończenie publikowania aplikacji](media/service-create-distribute-apps/power-bi-apps-success.png)

Użytkownicy biznesowi, którym udostępniono aplikację, mogą ją odnaleźć na kilka różnych sposobów. Jeśli można zainstalować ją automatycznie, pojawi się w obszarze Aplikacje na ich kontach usługi Power BI. Możesz wysłać im bezpośredni link do aplikacji. Mogą oni również wyszukać ją w witrynie Microsoft AppSource, gdzie wyświetlane są wszystkie aplikacje, do których mają dostęp. Niezależnie od sposobu jej uzyskania, zawsze po wybraniu pozycji Aplikacje zobaczą tę aplikację swojej liście.

Dowiedz się więcej na temat [aplikacji dla użytkowników biznesowych](service-install-use-apps.md).

## <a name="change-your-published-app"></a>Zmienianie opublikowanej aplikacji
Po opublikowaniu aplikacji możesz chcieć ją zmienić lub zaktualizować. Łatwo jest zaktualizować aplikację, jeśli jesteś administratorem lub członkiem obszaru roboczego aplikacji. 

1. Otwórz obszar aplikacji odpowiadający aplikacji. 
   
     ![Otwieranie obszaru roboczego](media/service-create-distribute-apps/power-bi-apps-open-workspace.png)
2. Otwórz pulpit nawigacyjny lub raport. Widzisz, że możesz wprowadzić dowolne zmiany.
   
     Obszar roboczy aplikacji to obszar przygotowawczy, a więc zmiany nie zostaną wprowadzone w działającej aplikacji do momentu jej ponownego opublikowania. To umożliwia wprowadzanie zmian bez wpływu na opublikowane aplikacje.  
 
3. Wróć do listy zawartości obszaru roboczego aplikacji i wybierz opcję **Zaktualizuj aplikację**.
   
     ![Przycisk aktualizowania aplikacji](media/service-create-distribute-apps/power-bi-app-update-button.png)

4. Jeśli chcesz, możesz zaktualizować obszary **Szczegóły**, **Zawartość** i **Dostęp**, a następnie wybrać opcję **Zaktualizuj aplikację**.
   
     ![Przycisk aktualizowania aplikacji](media/service-create-distribute-apps/power-bi-app-update-complete.png)

Osoby, którym udostępniono aplikację, automatycznie zobaczą zaktualizowaną wersję aplikacji. 

# <a name="automatically-install-apps-for-end-users"></a>Automatyczne instalowanie aplikacji dla użytkowników końcowych
Aplikacje można instalować automatycznie dla użytkowników końcowych, co ułatwia dystrybucję odpowiednich aplikacji do właściwych osób lub grup.

Aplikacje dostarczają dane, których użytkownicy końcowi potrzebują do pracy. Teraz możesz automatycznie instalować te aplikacje z listy zawartości Aplikacje zamiast wyszukiwania ich w usłudze Microsoft AppSource lub używania linku instalacji. Ułatwia to dystrybucję standardowej zawartości usługi Power BI do użytkowników.

## <a name="how-to-install-an-app-automatically-for-end-users"></a>Jak automatycznie instalować aplikacje dla użytkowników końcowych
Włączenie tej funkcji przez administratora udostępnia wydawcom aplikacji nową opcję **automatycznego instalowania aplikacji**. Jeśli pole jest ***zaznaczone*** i wydawca aplikacji wybierze pozycję **Zakończ** (lub **Aktualizuj aplikację** w przypadku istniejących aplikacji), aplikacja zostanie wypchnięta do wszystkich użytkowników lub grup zdefiniowanych w sekcji **Uprawnienia** aplikacji na karcie **Dostęp**.

![Włączanie wypychania aplikacji](media/service-create-distribute-apps/power-bi-apps-access.png)

## <a name="how-users-get-the-apps-that-were-pushed-to-them"></a>Jak użytkownicy odbierają wypchnięte do nich aplikacje
Po wypchnięciu aplikacji jest ona automatycznie wyświetlana na liście Aplikacje. Możesz dobrać aplikacje, które użytkownicy lub stanowiska w organizacji muszą mieć „w zasięgu ręki”.

![Włączanie wypychania aplikacji](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

### <a name="considerations-for-automatically-installing-apps"></a>Zagadnienia dotyczące automatycznego instalowania aplikacji
Poniżej przedstawiono niektóre kwestie, o których należy pamiętać podczas wypychania aplikacji do użytkowników końcowych:

* Automatyczne instalowanie aplikacji dla użytkowników może trwać pewien czas. Większość aplikacji jest instalowana natychmiast, lecz wypychanie aplikacji może trwać pewien czas.  To zależy od liczby elementów w aplikacji i liczby osób, którym udzielono dostępu. Zalecamy wypychanie aplikacji poza godzinami pracy, na długo przed tym, zanim użytkownicy będą ich potrzebować. Zweryfikuj kilku użytkowników przed wysłaniem wiadomości o dostępności aplikacji do szerokiego kręgu użytkowników.

* Odśwież przeglądarkę. Zanim wypchnięta aplikacja będzie widoczna na liście Aplikacje, może być konieczne odświeżenie lub zamknięcie i ponowne otwarcie przeglądarki przez użytkownika.

* Jeśli użytkownik nie widzi natychmiast aplikacji na liście Aplikacje, powinien odświeżyć lub zamknąć i otworzyć ponownie przeglądarkę.

* Nie przeciążaj użytkowników. Nie należy wypychać zbyt wielu aplikacji — dzięki temu użytkownicy będą odbierać wstępnie zainstalowane aplikacje jako przydatne. Dobra praktyka to kontrolowanie, kto może wypychać aplikacje do użytkowników końcowych, w celu koordynowania wypychania. Możesz ustanowić w organizacji punkt kontaktowy na potrzeby pobierania aplikacji wypchniętych do użytkowników końcowych.

* Użytkownicy-goście, którzy nie zaakceptowali zaproszenia, nie otrzymają automatycznie zainstalowanych dla nich aplikacji.  

## <a name="unpublish-an-app"></a>Cofanie publikacji aplikacji
Każdy członek grupy roboczej aplikacji może cofnąć publikację aplikacji.

* W obszarze roboczym aplikacji wybierz przycisk wielokropka (**...**) w prawym górnym rogu, a następnie wybierz opcję **Cofnij publikację aplikacji**.
  
     ![Cofnięcie publikacji aplikacji](media/service-create-distribute-apps/power-bi-app-unpublish.png)

Ta czynność spowoduje odinstalowanie aplikację u wszystkich osób, którym ją udostępniono, i nikt nie będzie miał już do niej dostępu. Nie usuwa jednak obszaru roboczego aplikacji ani jego zawartości.

## <a name="power-bi-apps-faq"></a>Często zadawane pytania dotyczące aplikacji usługi Power BI
### <a name="how-are-app-workspaces-different-from-group-workspaces"></a>Czym obszary robocze aplikacji różnią się od obszarów roboczych grupy?
W tej wersji zmieniono nazwy wszystkich obszarów roboczych grupy na obszary robocze aplikacji. Możesz opublikować aplikację z dowolnego z obszarów roboczych. Ta funkcja pozostanie w większości zgodna z obszarami roboczymi grupy. W ciągu kilku najbliższych miesięcy planujemy wprowadzić następujące ulepszenia do obszarów roboczych aplikacji: 

* Tworzenie obszarów roboczych aplikacji nie będzie oznaczało tworzenia odpowiadających im elementów w usłudze Office 365, tak jak ma to miejsce w przypadku obszarów roboczych grupy. Możesz więc utworzyć dowolną liczbę obszarów aplikacji, nie martwiąc się, że w tle tworzone są również różne grupy usługi Office 365 (możesz nadal korzystać z usługi OneDrive dla Firm w usłudze Office 365 do przechowywania plików). 
* Obecnie możesz dodawać do list członków i administratorów tylko pojedyncze osoby. Wkrótce możliwe będzie dodawanie wielu grup zabezpieczeń usługi AD lub nowoczesnych grup do tych list w celu ułatwienia zarządzania.  

### <a name="how-are-apps-different-from-organizational-content-packs"></a>W jaki sposób aplikacje różnią się od pakietów zawartości organizacji?
Aplikacje są kolejnym etapem ewolucji i uproszczeniem pakietów zawartości. Istnieje jednak między nimi kilka różnic. 

* Po zainstalowaniu przez użytkowników biznesowych pakiety zawartości tracą swoją tożsamość grupową: stają się tylko listami pulpitów nawigacyjnych i raportów obok innych pulpitów nawigacyjnych i raportów. Natomiast aplikacje utrzymują grupowanie i tożsamość nawet po instalacji. To ułatwia użytkownikom biznesowym dalsze przechodzenie do nich w późniejszym czasie.
* Możesz tworzyć wiele pakietów zawartości w obszarze roboczym, ale aplikacja ma bezpośrednią relację ze swoim obszarem roboczym. Sądzimy, że dzięki temu aplikacje będą łatwiejsze do zrozumienia i utrzymania w dłuższym okresie. Zapoznaj się z sekcją dotyczącą planów rozwoju na blogu usługi Power BI, aby poznać szczegółowe informacje na temat planów rozwoju tego obszaru. 
* Z czasem planujemy wycofać pakiety zawartości organizacji, więc zalecamy od teraz tworzenie aplikacji.  

### <a name="what-about-read-only-members-in-groups"></a>Co z członkami grup z prawami tylko do odczytu?
W grupach można dodać członków z prawami tylko do odczytu, którzy mogą jedynie wyświetlać zawartość. Głównym problemem w tym podejściu jest to, że nie można dodawać grup zabezpieczeń jako członków. 

Dzięki aplikacjom możesz opublikować wersję obszaru roboczego aplikacji tylko do odczytu dla większych grup odbiorców, w tym dla grup zabezpieczeń. Możesz wypróbować zmiany w pulpitach nawigacyjnych i raportach w aplikacji, nie wpływając na użytkowników końcowych. Zalecamy używanie aplikacji w ten sposób w przyszłości. W dłuższej perspektywie planujemy wycofanie członkostwa z uprawnieniami tylko do odczytu z obszarów roboczych.  

## <a name="next-steps"></a>Następne kroki
* [Instalowanie i używanie aplikacji w usłudze Power BI](service-install-use-apps.md)
* [Aplikacje usługi Power BI dla usług zewnętrznych](service-connect-to-services.md)
* [Portal administracyjny usługi Power BI](https://docs.microsoft.com/en-us/power-bi/service-admin-portal)
* Masz pytania? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)
