---
title: Organizowanie pracy w nowych obszarach roboczych (wersja zapoznawcza) — Power BI
description: Dowiedz się, jak tworzyć nowe obszary robocze, czyli kolekcje pulpitów nawigacyjnych i raportów utworzone w celu udostępnienia najważniejszych metryk dla organizacji.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/11/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: dd4ee055501974345c819f7604ff30174cd4c5ba
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279018"
---
# <a name="organize-work-in-the-new-workspaces-preview-in-power-bi"></a>Organizowanie pracy w nowych obszarach roboczych (wersja zapoznawcza) w usłudze Power BI

Obszary robocze to miejsca, w których można we współpracy z innymi osobami tworzyć kolekcje pulpitów nawigacyjnych i raportów. Takie kolekcje możesz następnie pakować w *aplikacje* i rozpowszechniać je w całej organizacji albo wśród konkretnych osób lub grup. W usłudze Power BI wprowadzono nowe środowisko obszarów roboczych w wersji zapoznawczej. 

![Nowe obszary robocze w usłudze Power BI w wersji zapoznawczej](media/service-new-workspaces/power-bi-new-workspaces-preview.png)

Nowe obszary robocze w wersji zapoznawczej umożliwiają:

- Przypisywanie ról obszarów roboczych do grup użytkowników: grup zabezpieczeń, list dystrybucyjnych, grup usługi Office 365 i pojedynczych użytkowników.
- Tworzenie grupy roboczej w usłudze Power BI bez konieczności tworzenia grupy usługi Office 365.
- Korzystanie z bardziej wyspecjalizowanych ról obszarów roboczych, co umożliwia bardziej elastyczne zarządzanie uprawnieniami w obszarze roboczym.

Przeczytaj informacje o sposobie [tworzenia nowych obszarów roboczych](service-create-the-new-workspaces.md).
 
Tworząc jeden z nowych obszarów roboczych, nie tworzysz skojarzonej bazowej grupy usługi Office 365. Administracja obszarem roboczym odbywa się w usłudze Power BI, a nie Office 365. Nadal możesz dodać grupę usługi Office 365 do obszaru roboczego, aby dalej zarządzać dostępem użytkowników do zawartości za pośrednictwem grup usługi Office 365. Możesz jednak dodatkowo korzystać z grup zabezpieczeń i list dystrybucyjnych oraz dodawać pojedynczych użytkowników bezpośrednio w usłudze Power BI, co daje więcej możliwości zarządzania dostępem do obszarów roboczych. Ponieważ administrowanie obszarem roboczym jest teraz dostępne w usłudze Power BI, administratorzy usługi Power BI decydują, kto w organizacji może tworzyć obszary robocze. W obszarze **Ustawienia obszaru roboczego** portalu administracyjnego administratorzy mogą nadać lub odebrać uprawnienia do tworzenia obszarów roboczych wszystkim osobom w organizacji. Ponadto mogą zezwolić na tworzenie wyłącznie członkom konkretnych grup zabezpieczeń.

![Ustawienia obszaru roboczego w portalu administracyjnym](media/service-new-workspaces/power-bi-workspace-admin-settings.png)

Przeczytaj więcej na temat [portalu administracyjnego usługi Power BI](service-admin-portal.md).

## <a name="roll-out-new-workspaces"></a>Wprowadzanie nowych obszarów roboczych

W okresie obowiązywania wersji zapoznawczej można tworzyć zarówno stare, jak i nowe obszary robocze, a oba typy obszarów roboczych mogą istnieć równolegle. Po zakończeniu okresu obowiązywania wersji zapoznawczej nowych obszarów roboczych i ich ogólnym udostępnieniu stare obszary robocze będą mogły istnieć jeszcze przez jakiś czas. Nie będzie możliwości tworzenia ich i należy się przygotować do przeprowadzenia migracji istniejących obszarów roboczych do infrastruktury nowych obszarów roboczych. Nie martw się, będziesz mieć kilka miesięcy na przeprowadzenie migracji.

## <a name="roles-in-the-new-workspaces"></a>Role w nowych obszarach roboczych

Możesz dodawać grupy użytkowników lub pojedynczych użytkowników do nowych obszarów roboczych jako członków, współautorów lub administratorów. Wszyscy użytkownicy w grupie otrzymują zdefiniowaną przez Ciebie rolę. Jeśli dany użytkownik należy do wielu grup użytkowników, otrzyma najwyższy poziom uprawnień zapewnianych przez rolę.

Wszyscy użytkownicy, których dodasz do obszaru roboczego, muszą mieć licencję usługi Power BI Pro. W obszarze roboczym ci użytkownicy mogą współpracować nad pulpitami nawigacyjnymi i raportami, które mają zostać opublikowane wśród większej liczby osób lub nawet w całej organizacji. Jeśli chcesz rozpowszechniać zawartość wśród innych użytkowników w Twojej organizacji, możesz przypisać im licencje usługi Power BI Pro lub umieścić obszar roboczy w pojemności usługi Power BI Premium.

Role umożliwiają zarządzenie uprawnieniami w obszarze roboczym, dzięki czemu zespoły mogą ze sobą współpracować. Nowe obszary robocze umożliwiają przypisywanie ról do pojedynczych użytkowników i do grup: grup zabezpieczeń, grup usługi Office 365 i list dystrybucyjnych. 

Po przypisaniu roli do grupy użytkowników członkowie tej grupy otrzymają dostęp do zawartości. W przypadku zagnieżdżonych grup użytkowników wszyscy użytkownicy w grupie otrzymają uprawnienia. Użytkownik, który znajduje się w kilku grupach użytkowników z różnymi rolami, otrzyma najwyższy poziom uprawnień przypisany do tych grup. 

Nowe obszary robocze oferują trzy role: administratorów, członków i współautorów.

**Administratorzy mogą:**

- Aktualizować i usuwać obszary robocze. 
- Dodawać i usuwać użytkowników, w tym innych administratorów.
- Wykonywać wszystkie czynności, do których są uprawnieni członkowie.

**Członkowie mogą:** 

- Dodawać członków lub innych użytkowników o niższych uprawnieniach.
- Publikować i aktualizować aplikację.
- Udostępniać element lub aplikację.
- Zezwalać innym osobom na dalsze udostępnianie elementów.
- Wykonywać wszystkie czynności, do których są uprawnieni współautorzy.


**Współautorzy mogą:** 

- Tworzyć, edytować i usuwać zawartość w obszarze roboczym. 
- Publikować raporty w obszarze roboczym i usuwać zawartość.
- Nie mogą przyznawać nowym osobom dostępu do zawartości. Nie mogą udostępniać nowej zawartości, ale mogą udostępniać zawartość osobom, którym już wcześniej udostępniono obszar roboczy, element lub aplikację. 
- Nie mogą modyfikować członków grupy.
 
Tworzymy przepływy pracy dla żądań dostępu w usłudze, tak aby użytkownicy, którzy nie mają dostępu, mogli go zażądać. Istnieją już przepływy pracy dla żądań dostępu do pulpitów nawigacyjnych, raportów i aplikacji.

## <a name="convert-old-workspaces-to-new-workspaces"></a>Konwertowanie starych obszarów roboczych na nowe obszary robocze

W trakcie obowiązywania wersji zapoznawczej nie można automatycznie konwertować starych obszarów roboczych na nowe. Można jednak utworzyć nowy obszar roboczy i opublikować zawartość w nowej lokalizacji. 

Gdy nowe obszary robocze staną się ogólnie dostępne, można będzie włączyć opcję automatycznego migrowania starych obszarów roboczych. W pewnym momencie po opublikowaniu wersji ogólnodostępnej przeprowadzenie migracji stanie się konieczne.

## <a name="how-are-the-new-workspaces-different-from-current-workspaces"></a>Czym różnią się nowe obszary robocze od bieżącej wersji obszarów roboczych?

Wraz z wprowadzeniem nowych obszarów roboczych modyfikujemy niektóre funkcje. Oto zmiany, które prawdopodobnie zostaną wprowadzone na stałe wraz z wersją zapoznawczą. 

* Tworzenie obszarów roboczych nie będzie oznaczało tworzenia odpowiadających im elementów w usłudze Office 365, tak jak ma to miejsce w bieżącej wersji obszarów roboczych. (Możesz nadal dodać grupę usługi Office 365 do obszaru roboczego, przypisując jej rolę). 
* W bieżącej wersji obszarów roboczych możesz dodawać tylko pojedyncze osoby jako członków i administratorów. W nowych obszarach roboczych możesz dodawać wiele grup zabezpieczeń usługi AD, list dystrybucyjnych lub grup usługi Office 365, aby umożliwić łatwiejsze zarządzanie użytkownikami. 
- Na podstawie obszarów roboczych w bieżącej wersji możesz tworzyć organizacyjne pakiety zawartości. Nie można ich tworzyć w ramach nowych obszarów roboczych.
- W obszarach roboczych w bieżącej wersji można używać organizacyjnych pakietów zawartości. Nie możesz z nich korzystać w ramach nowych obszarów roboczych.
- W trakcie obowiązywania wersji zapoznawczej niektóre funkcje nowych obszarów roboczych nie są jeszcze włączone. Zobacz następną sekcję [Planowane funkcje nowych obszarów roboczych](service-new-workspaces.md#planned-new-workspace-preview-features), aby uzyskać szczegółowe informacje.

## <a name="limitations-and-considerations"></a>Ograniczenia i istotne zagadnienia

Ograniczenia, o których trzeba wiedzieć:

- Obszary robocze mogą zawierać maksymalnie 1000 zestawów danych lub 1000 raportów na zestaw danych. 
- Osoba z licencją usługi Power BI Pro może być członkiem maksymalnie 250 obszarów roboczych.

## <a name="planned-new-workspace-preview-features"></a>Planowane funkcje nowych obszarów roboczych w wersji zapoznawczej

W czasie udostępnienia wersji zapoznawczej niektóre inne funkcje nowych obszarów roboczych w wersji zapoznawczej nadal są w fazie opracowywania i nie są jeszcze dostępne:

- Brak przycisku **Opuść obszar roboczy**.
- Metryki użycia nie są jeszcze obsługiwane.
- Jak działa wersja Premium: Obszary robocze możesz przypisywać i tworzyć w pojemności Premium, ale aby przenieść obszar roboczy pomiędzy pojemnościami, należy przejść do ustawień obszaru roboczego.
- Osadzanie składników Web Part programu SharePoint nie jest jeszcze obsługiwane.
- Brak przycisku **OneDrive** dla grup usługi Office 365 w obszarze Pobierz dane/pliki.

## <a name="workspace-features-that-work-differently"></a>Funkcje obszarów roboczych, które działają inaczej

Działanie niektórych funkcji różni się w bieżącej wersji obszarów roboczych i w nowych obszarach roboczych. Te różnice są zamierzone. Zostały wprowadzone na podstawie opinii klientów i umożliwiają bardziej elastyczną współpracę w obszarach roboczych:

- Ustawienie uprawnień do ponownego udostępniania elementów: zastąpione przez rolę współautora
- Obszary robocze tylko do odczytu: Zamiast udzielać użytkownikom dostępu tylko do odczytu do obszaru roboczego, przypiszesz ich do nadchodzącej roli Przeglądający, która zapewnia podobny dostęp tylko do odczytu do zawartości w obszarze roboczym.

## <a name="known-issues"></a>Znane problemy

Ponieważ ta funkcja jest obecnie dostępna w wersji zapoznawczej, ma kilka ograniczeń, o których warto wiedzieć. Następujące problemy są znane, a poprawki do nich są w fazie projektowania:

- Użytkownicy lub grupy użytkowników w wersji bezpłatnej dodani jako adresaci subskrypcji wiadomości e-mail mogą nie może otrzymywać wiadomości e-mail zgodnie z oczekiwaniami. Ten problem występuje, gdy jeden z nowych obszarów roboczych znajduje się w pojemności Premium, ale obszar Mój obszar roboczy użytkownika tworzącego subskrypcję nie znajduje się w pojemności Premium. Jeśli obszar Mój obszar roboczy znajduje się w pojemności Premium, użytkownicy i grupy użytkowników w wersji bezpłatnej będą otrzymywać wiadomości e-mail.
- Po przeniesieniu obszaru roboczego z pojemności Premium do udostępnionej pojemności (w niektórych przypadkach) użytkownicy i grupy użytkowników w wersji bezpłatnej nadal będą otrzymywać wiadomości e-mail, chociaż nie powinno to mieć miejsca. Ten problem występuje, gdy obszar Mój obszar roboczy użytkownika tworzącego subskrypcję znajduje się w pojemności Premium.

## <a name="next-steps"></a>Następne kroki
* [Tworzenie nowych obszarów roboczych (wersja zapoznawcza) w usłudze Power BI](service-create-the-new-workspaces.md)
* [Tworzenie obszarów roboczych w bieżącej wersji](service-create-workspaces.md)
* [Instalowanie i używanie aplikacji w usłudze Power BI](service-create-distribute-apps.md)
* Masz pytania? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)
