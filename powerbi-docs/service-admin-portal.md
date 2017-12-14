---
title: "Portal administracyjny usługi Power BI"
description: "Portal administracyjny umożliwia zarządzanie dzierżawą usługi Power BI w organizacji. Zawiera on kluczowe elementy, takie jak metryki użycia, dostęp do centrum administracyjnego usługi Office 365 oraz ustawienia."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 09/05/2017
ms.author: asaxton
ms.openlocfilehash: 339e3bc6f5a8acda20313e2f99e1b9b041bc2225
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-admin-portal"></a>Portal administracyjny usługi Power BI
Portal administracyjny umożliwia zarządzanie dzierżawą usługi Power BI w organizacji. Zawiera on kluczowe elementy, takie jak metryki użycia, dostęp do centrum administracyjnego usługi Office 365 oraz ustawienia.

Zarządzanie dzierżawą usługi Power BI w firmie odbywa się za pośrednictwem portalu administracyjnego usługi Power BI. Portal administracyjny jest dostępny dla wszystkich użytkowników, którzy są administratorami globalnymi w usłudze Office 365 lub którym przydzielono rolę administratora usługi Power BI. Aby uzyskać więcej informacji o roli administratora usługi Power BI, zobacz [Opis roli administratora usługi Power BI](service-admin-role.md).

Wszyscy użytkownicy będą widzieli **Portal administracyjny** pod ikoną koła zębatego. Jeśli użytkownik nie jest administratorem, zobaczy tylko sekcję **Ustawienia — wersja Premium** oraz wyłącznie te ustawienia, którymi może zarządzać.

## <a name="how-to-get-to-the-admin-portal"></a>Jak uzyskać dostęp do portalu administracyjnego
Twoje konto musi być oznaczone jako **Administrator globalny**, w usłudze Office 365 lub Azure Active Directory, albo musisz uzyskać przydział do roli administratora usługi Power BI, aby uzyskać dostęp do portalu administracyjnego usługi Power BI. Aby uzyskać więcej informacji o roli administratora usługi Power BI, zobacz [Opis roli administratora usługi Power BI](service-admin-role.md). Aby uzyskać dostęp do portalu administracyjnego usługi Power BI, wykonaj następujące czynności.

1. Wybierz koło zębate ustawień w prawym górnym rogu usługi Power BI.
2. Wybierz polecenie **Portal administracyjny**.

![](media/service-admin-portal/powerbi-admin-settings.png)

W portalu znajduje się pięć kart. Zostały one opisane poniżej.

* [Metryki użycia](#usage-metrics)
* [Użytkownicy](#users)
* [Dzienniki inspekcji](#audit-logs)
* [Ustawienia dzierżawy](#tenant-settings)
* [Ustawienia — wersja Premium](#premium-settings)

![](media/service-admin-portal/powerbi-admin-landing-page.png)

## <a name="usage-metrics"></a>Metryki użycia
Pierwsza karta w portalu administracyjnym to **Metryki użycia**. Raport metryk użycia daje możliwość monitorowania użycia w usłudze Power BI w ramach organizacji. Ponadto zapewnia możliwość wyświetlania najbardziej aktywnych użytkowników i grup w usłudze Power BI w ramach organizacji.

> [!NOTE]
> Przy pierwszym uzyskaniu dostępu do pulpitu nawigacyjnego lub po powrocie do pulpitu nawigacyjnego po długim czasie najprawdopodobniej zobaczysz ekran ładowania, gdy będziemy ładować pulpit nawigacyjny.
> 
> 

Po załadowaniu pulpitu nawigacyjnego zobaczysz dwie sekcje kafelków. Pierwsza sekcja obejmuje dane użycia dla poszczególnych użytkowników, a druga sekcja zawiera podobne informacje dotyczące grup w organizacji.

Oto podział elementów, które zobaczysz w każdym kafelków:

* Unikatowy licznik dla wszystkich pulpitów nawigacyjnych, raportów i zestawów danych w obszarze roboczym użytkownika
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)
* Najczęściej używany pulpit nawigacyjny według liczby użytkowników, którzy mogą do niego uzyskać dostęp. Jeśli na przykład masz pulpit nawigacyjny, który został udostępniony trzem użytkownikom oraz został dodany do pakietu zawartości, z którym łączy się dwóch różnych użytkowników, licznik będzie wskazywać 6 (1 + 3 +2)
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)
* Najpopularniejsza zawartość, z którą łączą się użytkownicy. Będzie to wszystko to, z czym użytkownicy mogą się połączyć za pośrednictwem procesu Pobierz dane, a więc pakiety zawartości SaaS, pakiety zawartości organizacji, pliki lub bazy danych.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)
* Widok użytkowników oparty na liczbie posiadanych przez nich pulpitów nawigacyjnych, zarówno utworzonych przez użytkowników, jak i tych udostępnionych.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)
* Widok użytkowników oparty na liczbie posiadanych raportów
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

Druga sekcja wyświetla informacje tego samego typu, ale w oparciu o grupy. Dzięki temu możesz zobaczyć, które grupy w organizacji są najbardziej aktywne oraz których informacji używają.

Przy użyciu tych informacji możesz zyskać prawdziwy wgląd w sposób użytkowania usługi Power BI w organizacji oraz rozpoznać bardzo aktywnych użytkowników i grupy w organizacji.

## <a name="users"></a>Użytkownicy
Druga karta w portalu administracyjnym to **Zarządzanie użytkownikami**. Zarządzanie użytkownikami, w przypadku usługi Power BI, odbywa się w centrum administracyjnym usługi Office 365, więc ta sekcja umożliwia szybkie przejście do obszaru, w którym można zarządzać użytkownikami, administratorami i grupami w usłudze Office 365.

![](media/service-admin-portal/powerbi-admin-manage-users.png)

Po kliknięciu pozycji **Przejdź do centrum administracyjnego usługi Office 365** użytkownik zostanie przeniesiony bezpośrednio do strony początkowej centrum administracyjnego usługi Office 365, aby zarządzać użytkownikami dzierżawy.

![](media/service-admin-portal/powerbi-admin-o365-admin-center.png)

## <a name="audit-logs"></a>Dzienniki inspekcji
Trzeci karta w portalu administracyjnym to **Dzienniki inspekcji**. Dzienniki znajdują się w centrum zabezpieczeń i zgodności usługi Office 365. Ta sekcja umożliwia szybki dostęp do tego obszaru w usłudze Office 365. 

Aby uzyskać więcej informacji o dziennikach inspekcji, zobacz [Inspekcja usługi Power BI w organizacji](service-admin-auditing.md)

## <a name="tenant-settings"></a>Ustawienia dzierżawy
Trzeci karta w portalu administracyjnym to **Ustawienia dzierżawy**. Ustawienia dzierżawy zapewniają więcej kontroli nad funkcjami, które są dostępne w organizacji. Jeśli masz obawy związane z poufnymi danymi, niektóre z funkcji mogą nie być odpowiednie dla Twojej organizacji. Możesz też zdecydować, że dana funkcja będzie dostępna tylko dla wybranej grupy. Jeśli tak jest, możesz ją wyłączyć w dzierżawie.

![](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> Zastosowanie ustawienia dla wszystkich użytkowników w dzierżawie może zająć do 10 minut.
> 
> 

Ustawienia mogą mieć trzy stany w oparciu o podane ustawienia.

### <a name="disabled-for-the-entire-organization"></a>Wyłączone dla całej organizacji
Możesz wyłączyć funkcję i uniemożliwić użytkownikom korzystanie z niej.

![](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

### <a name="enabled-for-the-entire-organization"></a>Włączone dla całej organizacji
Możesz włączyć funkcję dla całej organizacji — wszyscy użytkownicy będą mieć dostęp do tej funkcji.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

### <a name="enabled-for-a-subset-of-the-organization"></a>Włączone dla podzbioru organizacji
Możesz też włączyć funkcję dla części organizacji. Można to zrobić na kilka różnych sposobów. Funkcję możesz włączyć dla całej organizacji poza wybraną grupą użytkowników.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

Ponadto możesz włączyć funkcję tylko dla wybranej grupy użytkowników, jednocześnie wyłączając ją dla innej grupy użytkowników. Dzięki temu upewnisz się, że wybrani użytkownicy nie będą mieć dostępu do funkcji, nawet kiedy znajdą się w grupie dozwolonych użytkowników.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

## <a name="export-and-sharing-settings"></a>Ustawienia eksportowania i udostępniania
### <a name="share-content-to-external-users"></a>Udostępnianie zawartości użytkownikom zewnętrznym
Użytkownicy w organizacji mogą udostępniać pulpity nawigacyjne użytkownikom spoza organizacji.

![](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Publikowanie w Internecie
Użytkownicy w organizacji mogą publikować raporty w Internecie. [Dowiedz się więcej](service-publish-to-web.md)

![](media/service-admin-portal/powerbi-admin-publish-to-web.png)

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do konkretnych grup.
> 
> 

### <a name="export-data"></a>Eksportowanie danych
Użytkownicy w organizacji mogą eksportować dane z kafelka lub wizualizacji. [Dowiedz się więcej](power-bi-visualization-export-data.md)

![](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> Wyłączenie opcji **Eksportowanie danych** ponadto uniemożliwi użytkownikom korzystanie z funkcji **Analizuj w programie Excel** oraz połączenia na żywo usługi Power BI.
> 
> 

### <a name="export-reports-as-powerpoint-presentations"></a>Eksportowanie raportów jako prezentacji programu PowerPoint
Użytkownicy w organizacji mogą eksportować raporty usługi Power BI jako pliki programu PowerPoint. [Dowiedz się więcej](service-publish-to-powerpoint.md)

![](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Drukowanie pulpitów nawigacyjnych i raportów
Użytkownicy w organizacji mogą drukować pulpity nawigacyjne i raporty. [Dowiedz się więcej](service-print.md)

![](media/service-admin-portal/powerbi-admin-print-dashboard.png)

![](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-settings"></a>Ustawienia pakietu zawartości
### <a name="publish-content-packs-to-the-entire-organization"></a>Publikowanie pakietów zawartości w całej organizacji
Użytkownicy w organizacji mogą publikować pakiety zawartości w całej organizacji.

![](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs"></a>Tworzenie szablonów pakietów zawartości w organizacji
Użytkownicy w organizacji mogą tworzyć szablony pakietów zawartości, które używają zestawów danych wbudowanych w jednym źródle danych w aplikacji Power BI Desktop.

## <a name="integration-settings"></a>Ustawienia integracji
### <a name="ask-questions-about-data-using-cortana"></a>Zadawanie pytań o dane przy użyciu Cortany
Użytkownicy w organizacji mogą zadawać pytania dotyczące danych przy użyciu Cortany.

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do konkretnych grup.
> 
> 

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Używanie funkcji Analizuj w programie Excel z lokalnymi zestawami danych
Użytkownicy w organizacji mogą używać programu Excel, aby wyświetlać lokalne zestawy danych usługi Power BI i wchodzić z nimi w interakcje. [Dowiedz się więcej](service-analyze-in-excel.md)

> [!NOTE]
> Wyłączenie funkcji **Eksportowanie danych** również uniemożliwi użytkownikom korzystanie z funkcji **Analizuj w programie Excel**.
> 
> 

### <a name="user-arcgis-maps-for-power-bi-preview"></a>Używanie dodatku ArcGIS Maps for Power BI (wersja zapoznawcza)
Użytkownicy w organizacji mogą używać wizualizacji ArcGIS Maps for Power BI (wersja zapoznawcza) dostarczanej przez firmę Esri. [Dowiedz się więcej](power-bi-visualization-arcgis.md)

## <a name="r-visuals-settings"></a>Ustawienia elementów wizualnych języka R
### <a name="interact-with-an-dshare-r-visuals"></a>Wchodzenie w interakcje z elementami wizualnymi języka R oraz ich udostępnianie
Użytkownicy w organizacji mogą wchodzić w interakcje z elementami wizualnymi utworzonymi przy użyciu skryptów języka R oraz je udostępniać. [Dowiedz się więcej](service-r-visuals.md)

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do konkretnych grup.
> 
> 

## <a name="audit-settings"></a>Ustawienia inspekcji
### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>Twórz dzienniki inspekcji na potrzeby wewnętrznych inspekcji działań i sprawdzania zgodności
Użytkownicy w organizacji mogą używać inspekcji, aby monitorować działania podejmowane w usłudze Power BI przez innych użytkowników w organizacji. [Dowiedz się więcej](service-admin-auditing.md)

To ustawienie musi być włączone, aby można było rejestrować wpisy dziennika inspekcji.

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do konkretnych grup.
> 
> 

## <a name="dashboard-settings"></a>Ustawienia pulpitu nawigacyjnego
### <a name="data-classification-for-dashboards"></a>Klasyfikacja danych dla pulpitów nawigacyjnych
Użytkownicy w organizacji mogą tagować pulpity nawigacyjne przy użyciu klasyfikacji, aby wskazywać poziomy zabezpieczeń pulpitów nawigacyjnych. [Dowiedz się więcej](service-data-classification.md)

> [!NOTE]
> To ustawienie ma zastosowanie do całej organizacji i nie może być ograniczone do konkretnych grup.
> 
> 

## <a name="developer-settings"></a>Ustawienia dewelopera
### <a name="embed-content-in-apps"></a>Osadzanie zawartości w aplikacjach
Użytkownicy w organizacji mogą osadzać pulpity nawigacyjne i raporty usługi Power BI w aplikacjach oprogramowania jako usługi (SaaS). Wyłączenie tego ustawienia sprawi, że użytkownicy nie będą w stanie używać interfejsów API REST do osadzania zawartości usługi Power BI w swoich aplikacjach.

## <a name="premium-settings"></a>Ustawienia — wersja Premium
Karta Ustawienia — wersja Premium umożliwia zarządzanie pojemnością Power BI Premium zakupioną dla organizacji. Wszyscy użytkownicy w organizacji będą widzieć kartę ustawień wersji Premium, ale zobaczą zawartość na karcie tylko wtedy, jeśli przydzielono im rolę **administratora pojemności** lub użytkownika z uprawnieniami do przypisywania. Jeśli użytkownik nie ma żadnych uprawnień, zobaczy następujący komunikat.

![](media/service-admin-portal/premium-settings-no-access.png "Brak dostępu do ustawień wersji Premium")

Aby uzyskać więcej informacji o zarządzaniu ustawieniami wersji Premium, zobacz [Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md).

## <a name="next-steps"></a>Następne kroki
[Opis roli administratora usługi Power BI](service-admin-role.md)  
[Inspekcja usługi Power BI w organizacji](service-admin-auditing.md)  
[Zarządzanie usługą Power BI Premium](service-admin-premium-manage.md)  
[Administrowanie usługą Power BI w organizacji](service-admin-administering-power-bi-in-your-organization.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

