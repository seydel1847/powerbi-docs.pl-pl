---
title: Rozwiązywanie problemów z zaplanowanym odświeżaniem na Serwerze raportów usługi Power BI
description: W tym artykule omówiono dostępne zasoby służące do rozwiązywania problemów z zaplanowanym odświeżaniem na Serwerze raportów usługi Power BI.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: a90f22c262a314b50981be94121e2573f9fe525a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34296370"
---
# <a name="troubleshoot-scheduled-refresh-in-power-bi-report-server"></a>Rozwiązywanie problemów z zaplanowanym odświeżaniem na Serwerze raportów usługi Power BI
W tym artykule omówiono dostępne zasoby służące do rozwiązywania problemów z zaplanowanym odświeżaniem na Serwerze raportów usługi Power BI.

Ten artykuł będzie aktualizowany w miarę pojawiania się nowych problemów, aby zapewnić pomoc.

## <a name="common-issues"></a>Typowe problemy
Poniżej przedstawiono najbardziej typowe problemy, które można napotkać podczas próby zaplanowania odświeżenia raportu. 

### <a name="driver-related-problems"></a>Problemy związane z sterownikami
Pomyślne nawiązywanie połączeń z różnymi źródłami danych może wymagać zainstalowania sterowników innych firm. Należy je zainstalować nie tylko na maszynie, na której jest używany program Power BI Desktop, ale także na serwerze raportów.

Dodatkowo sterownik może mieć wersję 32- i 64-bitową. Należy zainstalować sterownik 64-bitowy, ponieważ Serwer raportów usługi Power BI jest 64-bitowy.

Aby uzyskać więcej informacji na temat sposobu instalowania i konfigurowania sterowników innych firm, skontaktuj się z producentem.

### <a name="memory-pressure"></a>Wykorzystanie pamięci
Wykorzystanie pamięci może wystąpić, gdy przetwarzanie i renderowanie raportów wymaga więcej pamięci. Zaplanowane odświeżanie raportów może wymagać dużej ilości pamięci na maszynie. Jest tak zwłaszcza w przypadku większych raportów. Wykorzystanie pamięci może spowodować niepowodzenia raportowania, a nawet awarię serwera raportów.

Jeśli wykorzystanie pamięci występuje często, warto zastanowić się nad skalowanym w poziomie wdrożeniem serwera raportów, aby rozłożyć obciążenie zasobów. Alternatywnie za pomocą ustawienia `IsDataModelRefreshService` w pliku rsreportserver.config można zdefiniować, że dany serwer raportów ma być używany na potrzeby odświeżania danych. Korzystając z tego ustawienia, możesz zdefiniować co najmniej jeden serwer jako serwer frontonu, który będzie obsługiwał raporty na żądanie, oraz inny zestaw serwerów używany tylko na potrzeby zaplanowanego odświeżania.

Aby uzyskać informacje na temat sposobu monitorowania wystąpienia usług Analysis Services, zobacz [Monitorowanie wystąpienia usług Analysis Services](https://docs.microsoft.com/sql/analysis-services/instances/monitor-an-analysis-services-instance).

Aby uzyskać informacje o ustawieniach pamięci w ramach usług Analysis Services, zobacz [Właściwości pamięci](https://docs.microsoft.com/sql/analysis-services/server-properties/memory-properties).

### <a name="kerberos-configuration"></a>Konfiguracja protokołu Kerberos
Pomyślne nawiązanie połączenia ze źródłem danych przy użyciu poświadczeń systemu Windows może wymagać skonfigurowania ograniczonego delegowania protokołu Kerberos. Aby uzyskać więcej informacji na temat konfigurowania ograniczonego delegowania protokołu Kerberos, zobacz [Konfigurowanie protokołu Kerberos do używania z raportami usługi Power BI](configure-kerberos-powerbi-reports.md).

## <a name="known-issues"></a>Znane problemy
W tym miejscu będą umieszczane informacje o znanych problemach, gdy staną się dostępne.

## <a name="configuration-settings"></a>Ustawienia konfiguracji
Za pomocą poniższych ustawień możesz skonfigurować sposób wykonywania zaplanowanego odświeżania. Ustawienia w ramach programu SQL Server Management Studio (SSMS) dotyczą wszystkich serwerów raportów w ramach wdrożenia skalowanego w poziomie. Ustawienia skonfigurowane w pliku rsreportserver.config dotyczą konkretnego serwera, na którym je określono.

**Ustawienia w programie SSMS:**

| Ustawienie | Opis |
| --- | --- |
| MaxFileSizeMb |Maksymalny rozmiar pliku przekazywanych raportów. Domyślnie 1000 MB (1 GB). Wartość maksymalna to 2000 MB (2 GB). |
| ModelCleanupCycleMinutes |Określa, jak często model jest sprawdzany, aby wykluczyć go z pamięci. Wartość domyślna to 15 minut. |
| ModelExpirationMinutes |Definiuje czas od ostatniego użycia modelu, po którym model wygaśnie i zostanie wykluczony. Wartość domyślna to 60 minut. |
| ScheduleRefreshTimeoutMinutes |Definiuje, ile może potrwać odświeżanie danych w danym trybie. Wartość domyślna to 120 minut. Nie ma żadnego górnego limitu. |

**Ustawienia w pliku rsreportserver.config:**

```
<Configuration>
    <Service>
        <PollingInterval>10</PollingInterval>
        <IsDataModelRefreshService>false</IsDataModelRefreshService>
        <MaxQueueThreads>0</MaxQueueThreads>
    </Service>
</Configuration>
```

## <a name="tools-for-troubleshooting"></a>Narzędzia do rozwiązywania problemów
### <a name="logs-relevant-for-scheduled-refresh-of-power-bi-reports"></a>Dzienniki zawierające informacje dotyczące zaplanowanego odświeżania raportów usługi Power BI
Pliki dziennika, które zawierają informacje o zaplanowanym odświeżaniu, to dzienniki RSPowerBI_. Znajdują się one w folderze LogFiles lokalizacji instalacji serwera raportów. 

```
C:\Program Files\Microsoft Power BI Report Server\PBIRS\LogFiles\RSPowerBI_*.log
```

**Warunek błędu**

```
2017-10-20 02:00:09.5188|ERROR|744|Error Processing Data Model Refresh: SessionId: e960c25e-ddd4-4763-aa78-0e5dceb53472, Status: Error Model can not be refreshed because not all the data sources are embedded, Exception Microsoft.PowerBI.ReportServer.AsServer.InvalidDataSourceException: Model can not be refreshed because not all the data sources are embedde
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.CanModelRefresh(IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

***Pomyślne odświeżenie***

```
2017-10-25 15:23:41.9370|INFO|6|Handling event with data: TimeEntered: 10/25/2017 8:23:41 PM, Type: Event, SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, EventType: DataModelRefresh
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Data Refresh.
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Retrieving PBIX AsDatabaseInfo.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying all the data sources are embedded.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying connection strings are valid.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Streaming model to Analysis Server.
2017-10-25 15:23:42.7603|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Refreshing the model.
2017-10-25 15:23:51.5258|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Removing credentials from the model.
2017-10-25 15:23:51.6508|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Saving model to the catalog.
```

**Nieprawidłowe poświadczenia**

```
2017-10-20 08:22:01.5595|INFO|302|Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Starting Refreshing the model.
2017-10-20 08:22:02.3758|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed to refresh the model, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.AnalysisServices.Tabular.Model.SaveChanges(SaveOptions saveOptions)
   at Microsoft.PowerBI.ReportServer.AsServer.TOMWrapper.RefreshModel(Database database)
   at Microsoft.PowerBI.ReportServer.AsServer.AnalysisServicesServer.RefreshDatabase(String databaseName, IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshDatabase(AsDatabaseInfo asDatabaseInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
2017-10-20 08:22:02.4588|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed Data Refresh, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.ExecuteActionWithLogging(Action methodToExecute, String description, String localizedDescription, String messageInFailure, RefreshInfo refreshInfo, DataAccessors dataAccessors, ReportEventType operation, Int64 size, Boolean isDataRetrieval, Boolean showInExecutionLog)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshData(RefreshInfo refreshInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

#### <a name="enabling-verbose-logging"></a>Włączanie pełnego rejestrowania
Włączanie pełnego rejestrowania na Serwerze raportów usługi Power BI odbywa się tak samo, jak w przypadku usług SQL Server Reporting Services.

1. Otwórz plik `<install directory>\PBIRS\ReportServer\bin\ReportingServicesService.exe.config`.
2. W obszarze `<system.diagnostics>` zmień wartość właściwości **DefaultTraceSwitch** na **4**.
3. W obszarze `<RStrace>` zmień wartość właściwości **Components** na **all:4**. 

### <a name="executionlog"></a>ExecutionLog
Za każdym razem, gdy raport usługi Power BI zostanie wyrenderowany lub plan zaplanowanego odświeżania zostanie wykonany, do dziennika wykonywania w bazie danych są dodawane nowe wpisy. Te wpisy są dostępne w widoku **ExecutionLog3** w ramach bazy danych katalogu serwera raportów.

Wpisy dziennika wykonywania dotyczące raportów usługi Power BI różnią się od wpisów dotyczących innych typów raportów.

* W kolumnie TimeRendering jest zawsze wartość 0. Renderowanie raportów usługi Power BI odbywa się w przeglądarce, a nie na serwerze.
* Istnieją 2 typy żądań i kolejne akcje elementów:
  * **Interaktywne**: zawsze, gdy raport zostanie wyświetlony.
    * **ASModelStream**: gdy model danych jest przesyłany strumieniowo do usług Analysis Services z katalogu.
    * **ConceptualSchema**: gdy użytkownik kliknie podczas wyświetlania raportu.
    * **QueryData**: zawsze, gdy klient żąda danych.
  * **Odśwież pamięć podręczną**: po każdym wykonaniu planu zaplanowanego odświeżania.
    * **ASModelStream**: zawsze, gdy model danych jest przesyłany strumieniowo do usług Analysis Services z katalogu.
    * **DataRefresh**: zawsze, gdy dane są odświeżane z co najmniej jednego źródła danych.
    * **SaveToCatalog**: zawsze, gdy model danych jest zapisywany z powrotem w katalogu.

## <a name="analysis-services"></a>Analysis Services
Czasem może zajść potrzeba zmodyfikowania usług Analysis Services, aby zdiagnozować problemy lub dostosować limity pamięci.

> [!IMPORTANT]
> Te ustawienia zostaną zresetowane po każdym uaktualnieniu serwera raportów. Zachowaj kopię swoich zmian, aby w razie potrzeby zastosować je ponownie.
> 
> 

### <a name="install-location"></a>Lokalizacja instalacji
Domyślna lokalizacja Serwera raportów usługi Power BI i usług Analysis Services jest następująca.

`C:\Program Files\Microsoft Power BI Report Server\PBIRS\ASEngine`

### <a name="configuring-analysis-services-settings-msmdsrvini"></a>Konfigurowanie ustawień usług Analysis Services (msmdsrv.ini)
W katalogu `<install directory>\PBIRS\ASEngine` znajduje się plik *msmdsrv.ini*, który służy do sterowania różnymi ustawieniami usług Analysis Services. Po otwarciu tego pliku natychmiast zauważysz, że nie zawiera on wszystkich ustawień, których można oczekiwać w pliku msmdsrv.ini. 

Jest to spowodowane tym, że rzeczywisty proces usług Analysis Services jest uruchamiany przez Serwer raportów usługi Power BI w katalogu `<install directory>\PBIRS\ASEngine\workspaces`. W tym folderze można znaleźć pełny plik *msmdsrv.ini*, który jest dobrze znany. Nie należy modyfikować pliku w folderze workspaces, ponieważ jest on nadpisywany przy każdym uruchomieniu procesu usług Analysis Services. Jeśli chcesz zmienić ustawienie, zmodyfikuj plik msmdsrv.ini w katalogu `<install directory>\PBIRS\ASEngine`.

Następujące ustawienia są resetowane przy każdym uruchomieniu procesu usług Analysis Services. Wszelkie wprowadzone w nich zmiany zostaną zignorowane.

* ConfigurationSettings\PrivateProcess
* ConfigurationSettings\DataDir
* ConfigurationSettings\LogDir
* ConfigurationSettings\TempDir
* ConfigurationSettings\BackupDir
* ConfigurationSettings\AllowedBrowsingFolders
* ConfigurationSettings\CrashReportsFolder
* ConfigurationSettings\ExtensionDir
* ConfigurationSettings\Port
* ConfigurationSettings\DeploymentMode
* ConfigurationSettings\ServerLocation
* ConfigurationSettings\TMCompatabilitySKU
* ConfigurationSettings\FlightRecorder\TraceDefinitionFile

### <a name="profiling-the-local-analysis-services-process"></a>Profilowanie lokalnego procesu usług Analysis Services
Dla lokalnego procesu usług Analysis Services można uruchomić śledzenie programu SQL Server Profiler w celach diagnostycznych. Aby połączyć się z lokalnym wystąpieniem usług Analysis Services, wykonaj następujące czynności.

Funkcja śledzenia programu SQL Server Profiler jest częścią [pakietu do pobrania programu SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms).

1. Uruchom program **SQL Server Profiler** jako administrator.
2. Wybierz przycisk **Nowe śledzenie**.
3. W oknie dialogowym **Łączenie z serwerem** wybierz opcję **Analysis Services**, a następnie wprowadź nazwę serwera **localhost:5132**.
4. W oknie dialogowym **Właściwości śledzenia** wybierz zdarzenia do przechwycenia i wybierz pozycję **Uruchom**.

## <a name="lock-pages-in-memory-windows-privilege"></a>Uprawnienie systemu Windows Blokuj strony w pamięci
Jeśli nie można renderować raportu usługi Power BI, może pomóc przypisanie uprawnienia **Blokuj strony w pamięci** do konta usług, w ramach którego jest uruchamiany serwer raportów usługi Power BI. Aby uzyskać więcej informacji o sposobie konfigurowania uprawnienia **Blokuj strony w pamięci**, zobacz [Uprawnienia systemu Windows przypisane do konta usługi Analysis Services](https://docs.microsoft.com/sql/analysis-services/instances/configure-service-accounts-analysis-services#bkmk_winpriv).

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

