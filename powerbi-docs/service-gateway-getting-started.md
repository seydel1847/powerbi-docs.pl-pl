---
title: "Wprowadzenie do bram usługi Power BI"
description: "Poznaj podstawowe informacje dotyczące bram danych dla usługi Power BI."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: e56af5ae1c59afc7d7aef01450bb1c778eb70b14
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="getting-started-with-power-bi-gateways"></a>Wprowadzenie do bram usługi Power BI
Witamy w przewodniku **Wprowadzenie do bram usługi Power BI**. Ten krótki przewodnik opisuje funkcje bramy, jej działanie oraz sposób jej instalowania, konfigurowania i uruchamiania.  

![](media/service-gateway-getting-started/gw_gettingstarted_0a.png)

Bramy stanowią zagadnienie techniczne, a ponieważ każda sieć i każde przedsiębiorstwo jest inne, złożoność bram może mieć tutaj istotne znaczenie. Aby nie zagłębiać się w bardziej skomplikowane kwestie, zaczniemy od podstaw.

## <a name="how-power-bi-gateways-work"></a>Jak działają bramy w usłudze Power BI
**Brama** to oprogramowanie, które ułatwia dostęp do danych znajdujących się w prywatnej sieci lokalnej na potrzeby ich użycia w usłudze w chmurze, takiej jak Power BI. Przypomina strażnika, który wyłapuje żądania dotyczące połączeń i pozwala na ich wykonanie tylko w przypadku, gdy żądania użytkowników spełniają określone kryteria (na przykład mają zezwolenie na korzystanie z bramy). To pozwala organizacjom umieszczać bazy danych i magazyny w sieciach lokalnych i jednocześnie bezpiecznie korzystać z podzbiorów tych danych w celu tworzenia atrakcyjnych raportów i pulpitów nawigacyjnych w usłudze Power BI.

Brama zabezpiecza również dostęp i dane za pomocą szyfrowania i kompresowania wszystkich danych, które przez nią przechodzą, w tym także wszelkiego rodzaju hasła używane do łączenia ze źródłami danych. Choć wydaje się to nieskomplikowane, to jest wiele szczegółowych kwestii, które należy rozważyć.

Czasami brama będzie potrzebna tylko Tobie. Być może masz duży skoroszyt programu Excel, trzy bazy danych SQL z danymi dotyczącymi bieżącej sprzedaży oraz działań marketingowych i chcesz utworzyć pulpit nawigacyjny usługi Power BI, który będzie przedstawiał różne aspekty związane ze sprzedażą. Jesteś jedyną osobą, która tworzy raporty w formie skoroszytu programu Excel i tylko Ty używasz tych baz danych podczas tworzenia raportów usługi Power BI. Potrzebujesz bramy przeznaczonej wyłącznie do użytku osobistego, ponieważ nie ma potrzeby udostępniania tych źródeł danych innym osobom.

A może Twoja organizacja korzysta z wielu baz danych różnych dostawców, w tym Analysis Services, SAP, Oracle oraz IBM i musisz udostępniać je wielu osobom, które tworzą liczne raporty. W takim przypadku potrzebujesz bramy, która pozwala skonfigurować dostęp do wszystkich tych źródeł i udostępnić ją wielu osobom w organizacji. To jest jednak zupełnie inny rodzaj bramy.

Na szczęście usługa Power BI dysponuje dwiema bramami, które dobrze pasują do każdego z tych scenariuszy. Usługa Power BI oferuje dwa typy bram:

* **Lokalna brama danych (tryb osobisty)** — umożliwia jednemu użytkownikowi łączenie się ze źródłami, ale nie może być udostępniania innym. Można z niej korzystać tylko w ramach usługi Power BI.
* **Lokalna brama danych** — umożliwia wielu użytkownikom łączenie się z wieloma lokalnymi źródłami danych i może być używana przez aplikacje Power BI, PowerApps, Flow i Azure Logic po przeprowadzeniu zaledwie jednego procesu instalacji.

Obie bramy pełnią podobną funkcję — ułatwiają dostęp do danych znajdujących się w prywatnej sieci lokalnej, dzięki czemu dane mogą być wykorzystywane w usługach w chmurze, takich jak Power BI. Bramy osobistej może używać tylko jedna osoba i tylko w ramach usługi Power BI, natomiast **lokalna brama danych** może być używana przez wielu użytkowników i w ramach wielu usług.

Aby brama zaczęła działać, należy wykonać trzy poniższe kroki:

* Zainstalować bramę
* Dodać użytkowników do bramy (zezwolić im na korzystanie z bramy)
* Połączyć się ze źródłami danych

Zastosowanie bramy pozwala również wykonywać inne ważne czynności:

* Odświeżanie danych lokalnych w celu aktualizowania raportów usługi Power BI za pomocą najnowszych danych

Dzięki procesowi odświeżania danych pulpity nawigacyjne i raporty usługi Power BI wyglądają świeżo i odzwierciedlają najnowsze dane. Gdy ktoś wyświetli raport utworzony za pomocą danych lokalnych, uzyska wgląd w najnowsze informacje, nawet jeśli raport został utworzony jakiś czas temu.

Pierwsza część, polegająca na instalowaniu bramy, jest łatwa. Udzielanie użytkownikom dostępu do bramy również nie jest niczym skomplikowanym, wystarczy dodać ich w oknie dialogowym usługi Power BI. Łączenie ze źródłami danych może okazać się skomplikowane, ponieważ źródeł danych jest naprawdę wiele, a każde z nich ma własne wymagania i niuanse dotyczące połączenia. W tym artykule skupimy się na bramie, dlatego odświeżanie zostanie omówione w innym przewodniku.

Na początek zajmiemy się najłatwiejszym procesem, czyli instalacją bramy.

## <a name="install-the-gateway"></a>Instalowanie bramy
Aby zainstalować bramę, otwórz usługę Power BI i zaloguj się przy użyciu konta usługi Power BI. Możesz też użyć tego linku, aby uruchomić usługę Power BI w przeglądarce i zalogować się. W usłudze Power BI wybierz **ikonę pobierania** w prawym górnym rogu, jak pokazano na poniższej ilustracji, a następnie wybierz pozycję **Brama danych**.

![](media/service-gateway-getting-started/gw_gettingstarted_01.png)

Spowoduje to przejście do strony pobierania, gdzie należy kliknąć przycisk **Pobierz bramę**, aby rozpocząć pobieranie.

![](media/service-gateway-getting-started/gw_gettingstarted_02.png)

Ten ekran w bardzo zwięzły sposób wyjaśnia działanie bramy. Zawiera także kilka ważnych **ostrzeżeń**. Pierwsze z nich mówi o tym, że po zainstalowaniu bramy jest ona uruchamiana na komputerze, na którym była wykonywana instalacja. Jeśli ten komputer jest wyłączony, brama również pozostaje wyłączona, a tym samym nie będzie działać. Ponadto instalowanie bramy na komputerze korzystającym z sieci bezprzewodowej nie jest najlepszym rozwiązaniem, więc zaleca się użycie komputera podłączonego do sieci przewodowej.

Jeśli wszystko jest gotowe, wybierz pozycję **Dalej**, aby kontynuować instalację.

![](media/service-gateway-getting-started/gw_gettingstarted_03.png)

Tutaj możesz wybrać, którą bramę zainstalować — lokalną czy osobistą. W tym przewodniku zainstalujesz **lokalną bramę danych**.

Oto kilka kwestii, na które należy zwrócić uwagę przy podejmowaniu decyzji:

* Obie bramy wymagają wersji 64-bitowych systemów operacyjnych Windows.
* Bram nie można zainstalować na kontrolerze domeny.
* Na jednym komputerze można zainstalować maksymalnie dwie lokalne bramy danych — jedną w trybie osobistym, a drugą w trybie standardowym. 
* Na jednym komputerze może znajdować się tylko jedna brama uruchomiona w tym samym trybie.
* Na różnych komputerach można zainstalować wiele lokalnych bram danych i zarządzać nimi z tego samego interfejsu zarządzania bramy usługi Power BI (wyjątek stanowi brama osobista, o czym napisano w następnym punkcie).
* Każdy użytkownik usługi Power BI może mieć uruchomioną jedną bramę w trybie osobistym. Zainstalowanie kolejnej bramy w trybie osobistym dla tego samego użytkownika, nawet na innym komputerze, spowoduje zastąpienie poprzedniej instalacji najnowszą.

Po wybraniu pozycji **Dalej** rozpocznie się instalacja bramy. Należy określić, gdzie zostanie ona zainstalowana — najlepszym rozwiązaniem jest zazwyczaj domyślna lokalizacja.

![](media/service-gateway-getting-started/gw_gettingstarted_06.png)

Proces instalacji przebiega szybko, o czym informuje wyświetlany pasek stanu.

![](media/service-gateway-getting-started/gw_gettingstarted_06a.png)

Gdy wszystko jest niemal gotowe, należy przypisać odpowiednie konto do bramy. Powinno to być konto (nazwa użytkownika i hasło) używane podczas logowania się w usłudze Power BI, ponieważ brama jest skojarzona z danym kontem usługi Power BI, a konfigurowanie bram przeprowadza się z poziomu usługi Power BI.

![](media/service-gateway-getting-started/gw_gettingstarted_07.png)

Poniższa ilustracja wskazuje zalogowanego użytkownika.

![](media/service-gateway-getting-started/gw_gettingstarted_08.png)

Po zalogowaniu należy utworzyć **klucz odzyskiwania**. Tę kwestię omówiono bardziej szczegółowo w innym artykule, ale teraz warto zapamiętać, że klucz ten będzie potrzebny do odzyskania lub przeniesienia bramy.

![](media/service-gateway-getting-started/gw_gettingstarted_09.png)

Jeśli wszystko przebiegnie poprawnie, zostanie wyświetlone okno informujące o tym, że brama jest gotowa.

![](media/service-gateway-getting-started/gw_gettingstarted_10.png)

To wszystko w kwestii instalacji bramy lokalnej. Był to rzeczywiście dość łatwy proces. Po wykonaniu konfiguracji początkowej kolejny krok polega na **dodaniu użytkowników** lub **dodaniu źródeł danych** — te czynności można wykonać w dowolnej kolejności.

W następnej sekcji opisano proces dodawania użytkowników do bramy, a następnie omówiono, gdzie należy przejść, aby dodać źródła danych do bramy.

## <a name="add-users-to-a-gateway"></a>Dodawanie użytkowników do bramy
Po zainstalowaniu bramy można przystąpić do zarządzania nią za pomocą **usługi Power BI**. Aby przejść do ekranu zarządzania bramami, w usłudze Power BI wybierz ikonę koła zębatego w prawym górnym rogu, a następnie wybierz pozycję **Zarządzaj bramami**.

![](media/service-gateway-getting-started/gw_gettingstarted_15.png)

Zostanie wyświetlona strona wewnątrz kanwy usługi Power BI, z poziomu której można zarządzać bramami. Strona **Ustawienia bramy** wygląda następująco.

![](media/service-gateway-getting-started/gw_gettingstarted_12.png)

Po naciśnięciu lub kliknięciu pozycji **Administratorzy** zostanie wyświetlona następująca strona zarządzania dla administratorów. Ta strona zawiera jedynie informacje o użytkownikach uprawnionych do *administrowania* oraz listę użytkowników dodanych (lub usuniętych) z poszczególnych źródeł danych przy użyciu innej strony — to zagadnienie omówimy w kilku następnych akapitach.

![](media/service-gateway-getting-started/gw_gettingstarted_13.png)

Po zainstalowaniu i zweryfikowaniu źródła danych (czyli pomyślnym nawiązaniu połączenia) zostanie ono wyświetlone poniżej skojarzonej bramy po lewej stronie ekranu **zarządzania bramami**, jak pokazano na poniższej ilustracji. Zwróć uwagę, że w okienku po prawej stronie znajdują się dwie sekcje, między którymi można się swobodnie poruszać: **Ustawienia źródła danych** i **Użytkownicy**. Poniższy ekran przedstawia sekcję **Ustawienia źródła danych**.

![](media/service-gateway-getting-started/gw_gettingstarted_16.png)

Po wybraniu sekcji **Użytkownicy** wyświetli się pole tekstowe, w którym możesz wpisać nazwy użytkowników organizacji, którym chcesz udzielić dostępu do wybranego źródła danych. Na poniższym ekranie widać, że dodanymi użytkownikami są Maggie i Adam.

Po rozpoczęciu wpisywania adresu e-mail w polu tekstowym usługa Power BI wyświetli listę użytkowników, których adres e-mail jest zgodny z tym wpisywanym przez Ciebie. Wystarczy, że klikniesz odpowiednią nazwę i dodasz go do listy.

Możesz także dodać grupy adresów e-mail (aliasów), aby zezwolić na dostęp grupom użytkowników i pojedynczym osobom.

![](media/service-gateway-getting-started/gw_gettingstarted_17.png)

Po wybraniu polecenia **Dodaj** dodani członkowie pojawią się w polu — w razie potrzeby można dodać kolejnych. Usuwanie użytkowników jest równie proste. Wystarczy zaznaczyć pole wyboru obok nazwy użytkownika, a następnie wybrać przycisk **Usuń** poniżej tego pola.

![](media/service-gateway-getting-started/gw_gettingstarted_18.png)

To wszystko. Pamiętaj, że użytkowników należy dodać do każdego źródła danych, do którego chcesz przyznać dostęp. Każde źródło danych ma osobną listę użytkowników, dlatego należy dodawać ich do poszczególnych źródeł danych oddzielnie.

## <a name="adding-data-sources"></a>Dodawanie źródeł danych
Aby brama spełniała swoją funkcję, należy dodać źródła danych. W tym miejscu można napotkać pewne trudności, ponieważ dostępnych źródeł danych jest naprawdę wiele, a każde z nich ma swoje określone wymagania (oraz często swoje własne sterowniki).

Zanim przejdziesz do kolejnego artykułu, przekonaj się, jak wygląda proces dodawania źródła danych. Na stronie **Zarządzaj bramami** **usługi Power BI** wybierz bramę, do której chcesz dodać źródło danych, a następnie wybierz polecenie **Dodaj źródło danych** w lewym górnym rogu strony powyżej listy bram.

Po wykonaniu tych czynności w okienku po prawej stronie zostanie wyświetlony panel **Ustawienia źródła danych**, jak pokazano na poniższej ilustracji. Z poziomu tego panelu możesz określić nazwę źródła danych, wpisując ją w polu tekstowym **Nazwa źródła danych**, oraz wybrać jego typ z listy rozwijanej **Typ źródła danych**.

![](media/service-gateway-getting-started/gw_gettingstarted_14.png)

Brama jest już zainstalowana, możesz więc przystąpić do dodawania źródeł danych. Świetnie. Zapoznaj się z zasobami w poniższej sekcji, aby uzyskać informacje o źródłach danych, więcej szczegółów na temat korzystania z bram oraz inne przydatne informacje.

## <a name="next-steps"></a>Następne kroki
[Using the on-premises data gateway](service-gateway-onprem.md) (Korzystanie z lokalnej bramy danych)  
[Lokalna brama danych — szczegóły](service-gateway-onprem-indepth.md)  
[Lokalna brama danych (tryb osobisty)](service-gateway-personal-mode.md) 
[Rozwiązywanie problemów z lokalną bramą danych](service-gateway-onprem-tshoot.md)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

