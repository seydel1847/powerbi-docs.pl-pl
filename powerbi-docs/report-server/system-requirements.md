---
title: Wymagania sprzętowe i programowe dotyczące instalowania serwera raportów usługi Power BI
description: Ten artykuł zawiera minimalne wymagania dotyczące sprzętu i oprogramowania, które trzeba spełnić, aby zainstalować i uruchomić serwer raportów usługi Power BI.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: maghan
ms.openlocfilehash: 3b0e9c148b86d8bf762a31cca5c3421df454502d
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34481751"
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Wymagania sprzętowe i programowe dotyczące instalowania serwera raportów usługi Power BI
Ten artykuł zawiera minimalne wymagania dotyczące sprzętu i oprogramowania, które trzeba spełnić, aby zainstalować i uruchomić serwer raportów usługi Power BI.

## <a name="processor-memory-and-operating-system-requirements"></a>Wymagania dotyczące procesora, pamięci i systemu operacyjnego
| Składnik | Wymaganie |
| --- | --- |
| .NET Framework |4.6<br><br>Oprogramowanie .NET Framework można zainstalować ręcznie ze strony programu [Microsoft .NET Framework 4.6 (Instalator internetowy) dla systemu Windows](http://support.microsoft.com/kb/3045560).<br/><br/> Aby uzyskać więcej informacji, zaleceń i wskazówek dotyczących programu .NET Framework 4.6, zobacz [.NET Framework — Przewodnik wdrażania dla deweloperów](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).<br/><br/>Systemy Windows 8.1 i Windows Server 2012 R2 przed zainstalowaniem programu .NET Framework 4.6 wymagają aktualizacji [KB2919355](http://support.microsoft.com/kb/2919355). |
| Dysk twardy |Serwer raportów usługi Power BI wymaga co najmniej 1 GB wolnego miejsca na dysku twardym.<br><br>Dodatkowe miejsce będzie wymagane na serwerze bazy danych, który jest hostem bazy danych serwera raportów. |
| Pamięć |**Minimalna:** 1 GB<br/><br/> **Zalecana:** co najmniej 4 GB |
| Szybkość procesora |**Minimalna:** procesor x64: 1,4 GHz<br/><br/> **Zalecana:** 2,0 GHz lub szybszy |
| Typ procesora |Procesor x64: AMD Opteron, AMD Athlon 64, Intel Xeon z obsługą technologii Intel EM64T, Intel Pentium IV z obsługą technologii EM64T |
| System operacyjny |Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br><br>Windows 8.1<br><br>Windows 8.1 Pro<br><br>Windows 8.1 Enterprise<br><br>Windows 8<br><br>Windows 8 Pro<br><br>Windows 8 Enterprise |

> [!NOTE]
> Instalacja serwera raportów usługi Power BI jest obsługiwana tylko dla procesorów x64.
> 
> 

## <a name="database-server-version-requirements"></a>Wymagania dotyczące wersji serwera bazy danych
Do hostowania baz danych serwera raportów jest używany program SQL Server. Wystąpienie aparatu bazy danych programu SQL Server może być lokalne lub zdalne. Poniżej wymieniono obsługiwane wersje aparatu bazy danych programu SQL Server, których można używać do hostowania baz danych serwera raportów:

* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012
* SQL Server 2008 R2
* SQL Server 2008

Utworzenie bazy danych serwera raportów na komputerze zdalnym wymaga skonfigurowania połączenia, które korzysta z konta użytkownika domeny lub konta usługi z dostępem sieciowym. Jeśli zdecydujesz się na korzystanie ze zdalnego wystąpienia programu SQL Server, rozważ dokładnie, których poświadczeń powinien używać serwer raportów w celu łączenia się z wystąpieniem programu SQL Server. Aby uzyskać więcej informacji, zobacz [Konfigurowanie połączenia z bazą danych serwera raportów](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager).

## <a name="considerations"></a>Istotne zagadnienia
Serwer raportów usługi Power BI zainstaluje wartości domyślne w celu skonfigurowania podstawowych ustawień wymaganych do uruchomienia serwera raportów. Wymagania są następujące:

* Aparat bazy danych programu SQL Server musi być dostępny po zakończeniu instalacji i przed rozpoczęciem konfigurowania bazy danych dla serwera raportów. Wystąpienie aparatu bazy danych hostuje bazę danych serwera raportów utworzoną przez Menedżera konfiguracji usług Reporting Services. Aparat bazy danych nie jest wymagany do obsługi instalacji.
* Konto użytkownika służące do uruchomienia Instalatora musi należeć do lokalnej grupy administratorów.
* Konto użytkownika używane na potrzeby Menedżera konfiguracji usług Reporting Services musi mieć uprawnienia dostępu i tworzenia do baz danych w wystąpieniu aparatu bazy danych, które hostuje bazy danych serwera raportów.
* Instalator musi mieć możliwość użycia wartości domyślnych w celu zarezerwowania adresów URL, które zapewniają dostęp do serwera raportów i portalu internetowego. Te wartości to port 80, silny symbol wieloznaczny i nazwy katalogów wirtualnych w formacie **SerwerRaportów** i **Raporty**.

## <a name="read-only-domain-controller-rodc"></a>Kontroler domeny tylko do odczytu (RODC)
 Serwer raportów można zainstalować w środowisku z kontrolerem domeny tylko do odczytu (RODC), jednak aby usługi Reporting Services działały prawidłowo, wymagany jest dostęp do kontrolera domeny do odczytu i zapisu. Jeśli usługi Reporting Services będą miały dostęp tylko do kontrolera RODC, podczas wykonywania zadań administracyjnych mogą wystąpić błędy.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Połączenia na żywo usług Analysis Services i raportów usługi Power BI
W przypadku wystąpień tabelarycznych lub wielowymiarowych można używać połączenia na żywo. Serwer usług Analysis Services musi mieć odpowiednią wersję i wydanie, aby działać prawidłowo.

| **Wersja serwera** | **Wymagana jednostka SKU** |
| --- | --- |
| 2012 SP1 CU4 lub nowsza |Jednostka SKU w wersji Business Intelligence i Enterprise |
| 2014 |Jednostka SKU w wersji Business Intelligence i Enterprise |
| 2016 lub nowszy |Jednostka SKU w wersji Standard lub nowsza |

## <a name="next-steps"></a>Następne kroki
[Co to jest serwer raportów usługi Power BI?](get-started.md)  
[Omówienie dla administratorów](admin-handbook-overview.md)  
[Instalacja serwera raportów usługi Power BI](install-report-server.md)  
[Instalowanie programu Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

