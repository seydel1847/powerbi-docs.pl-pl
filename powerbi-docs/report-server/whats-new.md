---
title: "Co nowego w serwerze raportów usługi Power BI"
description: "Dowiedz się, co nowego w serwerze raportów usługi Power BI. Obejmuje to obszary najważniejszych funkcji i jest aktualizowane w miarę, jak są wydawane nowe elementy."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 10/31/2017
ms.author: maghan
ms.openlocfilehash: 2ac4efa4e1eff5099fa3732b0fa753b04941979e
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2018
---
# <a name="whats-new-in-power-bi-report-server"></a>Co nowego w serwerze raportów usługi Power BI
Dowiedz się, co nowego w serwerze raportów usługi Power BI. Obejmuje to obszary najważniejszych funkcji i jest aktualizowane w miarę, jak są wydawane nowe elementy.

Aby pobrać serwer raportów usługi Power BI i program Power BI Desktop zoptymalizowany pod kątem serwera raportów usługi Power BI, przejdź do [Lokalne raportowanie za pomocą serwera raportów usługi Power BI](https://powerbi.microsoft.com/report-server/).

![Porada](media/whats-new/fyi-tip.png "Porada") Aby uzyskać bieżące informacje o wersji, zobacz [Informacje o wersji serwera raportów usługi Power BI](release-notes.md).

Powiązane nowości są dostępne w następujących artykułach:

* [Co nowego w usłudze Power BI](../service-whats-new.md)
* [Co nowego w programie Power BI Desktop](../desktop-latest-update.md)
* [Co nowego w aplikacjach mobilnych dla usługi Power BI](../mobile-whats-new-in-the-mobile-apps.md)
* [Blog zespołu usługi Power BI](https://powerbi.microsoft.com/blog/)

## <a name="october-2017-release"></a>Wersja z października 2017 r.
### <a name="power-bi-report-data-sources"></a>Źródła danych raportu usługi Power BI
Raporty usługi Power BI na serwerze raportów usługi Power BI można połączyć z różnymi źródłami danych. Możesz importować dane i planować odświeżanie danych lub bezpośrednio wysłać do nich zapytanie przy użyciu zapytania bezpośredniego lub połączenia na żywo usług SQL Server Analysis Services. Zobacz listę źródeł danych, które obsługują zaplanowane odświeżanie, i tych, które obsługują zapytanie bezpośrednie w „Źródła danych raportu usługi Power BI na serwerze raportów usługi Power BI”.

### <a name="scheduled-data-refresh-for-imported-data"></a>Zaplanowane odświeżanie danych dla importowanych danych
Na serwerze raportów usługi Power BI możesz ustawić zaplanowane odświeżanie danych, aby zapewnić aktualność danych w raportach usługi Power BI z osadzonym modelem, zamiast połączenia na żywo lub zapytania bezpośredniego. W przypadku importowania danych w modelu zagnieżdżonym zostanie on odłączony od oryginalnego źródła danych. Musi ono zostać zaktualizowane, aby dane były aktualne, a zaplanowane odświeżanie jest sposobem, aby to zrobić. Przeczytaj więcej na temat „zaplanowanego odświeżania raportów usługi Power BI na serwerze raportów usługi Power BI”.

### <a name="editing-power-bi-reports-from-the-server"></a>Edytowanie raportów usługi Power BI z serwera
Możesz otwierać i edytować pliki raportu usługi Power BI (pbix) z serwera, ale wrócisz do oryginalnego pliku, który został przekazany.  Oznacza to, że **jeśli dane zostały odświeżone przez serwer, nie zostaną one odświeżone przy pierwszym otwarciu pliku**. Musisz ręcznie odświeżyć je lokalnie, aby zobaczyć zmianę.

### <a name="large-file-uploaddownload"></a>Pobieranie/przekazywanie dużego pliku
Możesz przekazać pliki do 2 GB, chociaż domyślnie ten limit jest ustawiony na 1 GB w ustawieniach serwera raportów w programie SQL Server Management Studio (SSMS).  Te pliki są przechowywane w bazie danych, tak samo, jak w programie SharePoint i nie jest wymagana żadna specjalna konfiguracja katalogu programu SQL Server.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Uzyskiwanie dostępu do udostępnionych zestawów danych jako źródeł danych usługi OData
Możesz uzyskać dostęp do udostępnionych zestawów danych z programu Power BI Desktop ze źródłem danych usługi OData. Aby uzyskać więcej informacji, zobacz [Uzyskiwanie dostępu do udostępnionych zestawów danych jako źródeł danych usługi OData na serwerze raportów usługi Power BI](access-dataset-odata.md).

### <a name="scale-out"></a>Skalowanie w poziomie
Ta wersja obsługuje skalowanie w poziomie. Użyj modułu równoważenia obciążenia i ustaw koligację serwera w celu uzyskania najlepszych wyników. Należy pamiętać, że scenariusz nie jest jeszcze zoptymalizowany dla skalowania w poziomie, więc zobaczysz modele potencjalnie replikowane w wielu węzłach. Scenariusz będzie działać bez modułu równoważenia obciążenia sieciowego i trwałych sesji. Jednak zobaczysz nie tylko nadmierne wykorzystanie pamięci między węzłami, gdy model będzie ładowany N razy, ale wydajność spadnie między połączeniami, ponieważ model jest przesyłany strumieniowo, gdy trafia do nowego węzła między żądaniami.  

### <a name="administrator-settings"></a>Ustawienia administratora
Administratorzy mogą ustawić następujące właściwości w zaawansowanych właściwościach programu SSMS dla farmy serwerów:

* EnableCustomVisuals: Prawda/Fałsz
* EnablePowerBIReportEmbeddedModels: Prawda/Fałsz
* EnablePowerBIReportExportData: Prawda/Fałsz
* MaxFileSizeMb: Domyślnie teraz wynosi 1000
* ModelCleanupCycleMinutes: Jak często sprawdza, czy wykluczyć modele z pamięci
* ModelExpirationMinutes: Jak długo trwa aż model wygaśnie i zostanie usunięty na podstawie czasu ostatniego użycia
* ScheduleRefreshTimeoutMinutes: Jak długo może trwać odświeżanie długich danych dla modelu. Domyślnie są to dwie godziny.  Nie ma żadnego sztywnego, górnego limitu.

**Plik konfiguracji rsreportserver.config**

```
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>Interfejs API dewelopera
Interfejs API dewelopera (API REST) wprowadzony w wersji SSRS 2017 został rozszerzony dla serwera raportów usługi Power BI do pracy z zarówno z plikami programu Excel, jak i plikami pbix. Jednym potencjalnym przypadkiem użycia jest programowe pobieranie plików z serwera, odświeżanie ich i ponownie ich opublikowanie. Na przykład jest to jedyny sposób odświeżania skoroszytów programu Excel z modelami programu PowerPivot.

Należy pamiętać, że istnieje nowy, oddzielny interfejs API dla dużych plików, które zostaną zaktualizowane w wersji serwera raportów usługi Power BI struktury Swagger. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>Usługi SQL Server Analysis Services (SSAS) i zużycie pamięci serwera raportów usługi Power BI
Serwer raportów usługi Power BI hostuje teraz wewnętrznie usługi SQL Server Analysis Services (SSAS). To nie jest specyficzne dla zaplanowanego odświeżania. Hosting usług SSAS może znacznie rozszerzyć zużycie pamięci serwera raportów. Plik konfiguracji AS.ini jest dostępny w węzłach serwerów, więc jeśli znasz usługi SSAS, możesz chcieć zaktualizować ustawienia, a w tym maksymalny limit pamięci i buforowania dysku itp. Aby uzyskać szczegółowe informacje, zobacz [Właściwości serwera w usługach Analysis Services](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services).

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Wyświetlanie i interakcje ze skoroszytami programu Excel
Program Excel i usługa Power BI zawierają ofertę narzędzi, która jest unikatowa w branży. Razem umożliwiają one analitykom biznesowym łatwiejsze zbieranie, kształtowanie, analizowanie i wizualne eksplorowanie ich danych. Oprócz wyświetlania raportów usługi Power BI w portalu internetowym, użytkownicy biznesowi mogą teraz wykonywać te same operacje ze skoroszytami programu Excel na serwerze raportów usługi Power BI, zapewniając im jedną lokalizację do publikowania i wyświetlania zawartości ich samoobsługowej analizy biznesowej firmy Microsoft.

Opublikowaliśmy [przewodnik, jak dodać serwer programu Office Online Server (OOS) do środowiska serwera raportów usługi Power BI w wersji zapoznawczej](excel-oos.md). Klienci z kontem licencji zbiorczej mogą pobrać program OOS z Centrum obsługi licencji zbiorczej bez ponoszenia kosztów i będą mieć tylko funkcje wyświetlania. Po skonfigurowaniu użytkownicy mogą wyświetlać i wchodzić w interakcje ze skoroszytami programu Excel które:

* Nie mają zależności od zewnętrznych źródeł danych
* Mają aktywne połączenie z zewnętrznym źródłem danych usług SQL Server Analysis Services
* Mają model danych programu PowerPivot

### <a name="support-for-new-table-and-matrix-visuals"></a>Obsługiwanie nowych elementów wizualnych tabeli i macierzy
Serwer raportów usługi Power BI obsługuje obecnie nowe elementy wizualne tabeli i macierzy usługi Power BI. Aby utworzyć raporty z tymi elementami wizualnymi, konieczne będzie zaktualizowanie programu Power BI Desktop do wersji z października 2017 r. Nie można jej zainstalować obok wersji programu Power BI Desktop z czerwca 2017 r. Dla najnowszej wersji programu Power BI Desktop na [stronie pobierania serwera raportów usługi Power BI](https://powerbi.microsoft.com/report-server/) wybierz pozycję **Zaawansowane opcje pobierania**.

## <a name="june-2017"></a>Czerwiec 2017
* Ogólnodostępna wersja serwera raportów usługi Power BI (GA).

## <a name="may-2017"></a>Maj 2017 r.
* Udostępniono wersję zapoznawczą serwera raportów usługi Power BI
* Możliwość lokalnego publikowania raportów usługi Power BI
  * Obsługa niestandardowych elementów wizualnych
  * Obsługa połączeń na żywo usług Analysis Services tylko z większą liczbą źródeł danych w przyszłości.
  * Aplikacja mobilna usługi Power BI zaktualizowana w celu wyświetlania raportów usługi Power BI hostowanych na serwerze raportów usługi Power BI
* Rozszerzona współpraca przy raportach z komentarzami

## <a name="next-steps"></a>Następne kroki
[Informacje o wersji serwera raportów usługi Power BI](release-notes.md)  
[Podręcznik użytkownika](user-handbook-overview.md)  
[Podręcznik administratora](admin-handbook-overview.md)  
[Szybki start: instalowanie serwera raportów usługi Power BI](quickstart-install-report-server.md)  
[Instalowanie programu Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

