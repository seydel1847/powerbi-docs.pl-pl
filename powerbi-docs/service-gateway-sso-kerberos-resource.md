---
title: Używanie protokołu Kerberos (opartego na zasobach) na potrzeby logowania jednokrotnego z usługi Power BI do lokalnych źródeł danych
description: Konfigurowanie bramy przy użyciu protokołu Kerberos w celu włączenia logowania jednokrotnego z usługi Power BI do lokalnych źródeł danych
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 01/08/2018
LocalizationGroup: Gateways
ms.openlocfilehash: f13074c2123808e7b26d40f9c5a7e20cbf0da6e4
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54291808"
---
# <a name="use-resource-based-kerberos-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Używanie opartego na zasobach protokołu Kerberos na potrzeby logowania jednokrotnego z usługi Power BI do lokalnych źródeł danych

[Ograniczone delegowanie Kerberos oparte na zasobach](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) umożliwia włączanie łączności logowania jednokrotnego dla systemu Windows Server 2012 i nowszych wersji, dzięki czemu usługi frontonu i zaplecza mogą znajdować się w różnych domenach. Aby ta funkcja działa, domena usługi zaplecza musi ufać domenie usługi frontonu.

## <a name="preparing-for-resource-based-kerberos-constrained-delegation"></a>Przygotowywanie do ograniczonego delegowania protokołu Kerberos opartego na zasobach

Aby ograniczone delegowanie protokołu Kerberos działało poprawnie, należy skonfigurować kilka elementów, między innymi _główne nazwy usług_ (nazwy SPN) oraz ustawienia delegowania na kontach usług.

### <a name="prerequisite-1-operating-system-requirements"></a>Wymaganie wstępne 1: wymagania dotyczące systemu operacyjnego

Oparte na zasobach ograniczone delegowanie można skonfigurować tylko w obrębie kontrolera domeny z systemem Windows Server 2012 R2 lub Windows Server 2012 albo nowszym.

### <a name="prerequisite-2-install-and-configure-the-on-premises-data-gateway"></a>Wymaganie wstępne 2: zainstalowanie i skonfigurowanie lokalnej bramy danych

Ta wersja lokalnej bramy danych obsługuje uaktualnienie w miejscu i _przejmowanie ustawień_ istniejących bram.

### <a name="prerequisite-3-run-the-gateway-windows-service-as-a-domain-account"></a>Wymaganie wstępne 3: uruchomienie usługi bramy systemu Windows jako konta domeny

W standardowej instalacji brama działa jako konto usługi maszyny lokalnej (dokładnie: _NT Service\PBIEgwService_), jak pokazano na poniższej ilustracji:

![Konto domeny](media/service-gateway-sso-kerberos-resource/domain-account.png)

Aby włączyć **ograniczone delegowanie protokołu Kerberos, brama musi działać jako konto domeny, chyba że usługa Azure AD została już zsynchronizowana z lokalną usługą Active Directory (przy użyciu narzędzia Azure AD DirSync/Connect). Jeśli zachodzi potrzeba przełączenia konta na konto domeny, zapoznaj się z sekcją [Przełączanie bramy na konto domeny](service-gateway-sso-kerberos.md#switching-the-gateway-to-a-domain-account) w dalszej części tego artykułu.

Jeśli narzędzie Azure AD DirSync/Connect zostało skonfigurowane, a konta użytkowników są synchronizowane, usługa bramy nie musi wykonywać wyszukiwania w lokalnej usłudze AD w czasie wykonywania. W usłudze bramy można używać lokalnego identyfikatora SID (zamiast wymagać konta domeny). Czynności konfiguracji ograniczonego delegowania protokołu Kerberos opisane w tym artykule są takie same, jak w przypadku tej konfiguracji (z tą różnicą, że są stosowane względem obiektu komputera bramy w usłudze Active Directory, a nie w ramach konta domeny).

### <a name="prerequisite-4-have-domain-admin-rights-to-configure-spns-setspn-and-kerberos-constrained-delegation-settings"></a>Wymaganie wstępne 4: uprawnienia administratora domeny do konfigurowania ustawień ograniczonego delegowania protokołu Kerberos i nazw SPN (SetSPN)

Mimo że jest technicznie możliwe, aby administrator domeny tymczasowo lub trwale przypisał innej osobie uprawnienia do konfigurowania nazw SPN i delegowania protokołu Kerberos bez konieczności uzyskania przez tę osobę uprawnień administratora domeny, nie jest to zalecane rozwiązanie. W poniższej sekcji opisano czynności konfiguracyjne niezbędne do spełnienia **wymagania wstępnego 3**.

## <a name="configuring-kerberos-constrained-delegation-for-the-gateway-and-data-source"></a>Konfigurowanie ograniczonego delegowania protokołu Kerberos dla bramy i źródła danych

Aby poprawnie skonfigurować system, należy skonfigurować lub zweryfikować następujące dwa elementy:

1. W razie potrzeby skonfiguruj nazwę SPN w ramach konta domeny usługi bramy.

1. Skonfiguruj ustawienia delegowania na koncie domeny usługi bramy.

Należy pamiętać, że użytkownik musi być administratorem domeny, aby wykonać te dwie czynności konfiguracji.

W poniższych sekcjach opisano kolejno te kroki.

### <a name="configure-an-spn-for-the-gateway-service-account"></a>Konfigurowanie nazwy SPN dla konta usługi bramy

Po pierwsze należy ustalić, czy nazwa SPN została już utworzona dla konta domeny używanego jako konto usługi bramy, wykonując następujące kroki:

1. Jako administrator domeny uruchom narzędzie **Użytkownicy i komputery usługi Active Directory**.

1. Kliknij prawym przyciskiem myszy domenę, wybierz pozycję **Znajdź** i wpisz nazwę konta usługi bramy

1. W wynikach wyszukiwania kliknij prawym przyciskiem myszy konto usługi bramy, a następnie wybierz pozycję **Właściwości**.

1. Jeśli karta **Delegowanie** jest widoczna w oknie dialogowym **Właściwości**, oznacza to, że nazwa SPN została już utworzona i można przejść do kolejnej podsekcji dotyczącej konfigurowania ustawień delegowania.

    Jeśli karta **Delegowanie** nie jest widoczna w oknie dialogowym **Właściwości**, można ręcznie utworzyć nazwę SPN dla tego konta, co spowoduje dodanie karty **Delegowanie** (jest to najprostszy sposób konfigurowania ustawień delegowania). Nazwę SPN można utworzyć przy użyciu [narzędzia setspn](https://technet.microsoft.com/library/cc731241.aspx) w systemie Windows (aby utworzyć nazwę SPN, są wymagane uprawnienia administratora domeny).

    Załóżmy na przykład, że konto usługi bramy to „PBIEgwTest\GatewaySvc”, a nazwa maszyny, na której działa usługa bramy, to **Machine1**. Aby ustawić nazwę SPN konta usługi bramy dla maszyny w tym przykładzie, należy uruchomić następujące polecenie:

      ![Ustawianie nazwy SPN](media/service-gateway-sso-kerberos-resource/set-spn.png)

    Po wykonaniu tej czynności można przystąpić do konfigurowania ustawień delegowania.

### <a name="configure-delegation-settings"></a>Konfigurowanie ustawień delegowania

W poniższych krokach założono, że istnieje środowisko lokalne z dwoma maszynami w różnych domenach: maszyną bramy i serwerem bazy danych opartym na programie SQL Server. Na potrzeby tego przykładu przyjmujemy również następujące ustawienia i nazwy:

- Nazwa maszyny bramy: **PBIEgwTestGW**
- Konto usługi bramy: **PBIEgwTestFrontEnd\GatewaySvc** (wyświetlana nazwa konta: Łącznik bramy)
- Nazwa maszyny źródła danych programu SQL Server: **PBIEgwTestSQL**
- Konto usługi źródła danych programu SQL Server: **PBIEgwTestBackEnd\SQLService**

Biorąc pod uwagę te przykładowe nazwy i ustawienia, wykonaj następujące kroki konfiguracji:

1. Używając elementu **Użytkownicy i komputery usługi Active Directory**, czyli przystawki konsoli Microsoft Management Console (MMC), w obrębie kontrolera domeny **PBIEgwTestFront-end**, upewnij się, że na koncie usługi bramy nie zastosowano żadnych ustawień delegowania.

    ![Właściwości: Łącznik bramy](media/service-gateway-sso-kerberos-resource/gateway-connector-properties.png)

1. Używając elementu **Użytkownicy i komputery usługi Active Directory** w obrębie kontrolera domeny **PBIEgwTestBack-end**, upewnij się, że na koncie usługi zaplecza nie zastosowano żadnych ustawień delegowania. Ponadto upewnij się, że atrybut „msDS-AllowedToActOnBehalfOfOtherIdentity” nie został ustawiony. Ten atrybut można znaleźć w „Edytorze atrybutów”, jak pokazano na poniższej ilustracji:

    ![Właściwości usługi SQL](media/service-gateway-sso-kerberos-resource/sql-service-properties.png)

1. Utwórz grupę w przystawce **Użytkownicy i komputery usługi Active Directory** w obrębie kontrolera domeny **PBIEgwTestBack-end**. Dodaj konto usługi bramy do tej grupy, jak pokazano na poniższej ilustracji. Na ilustracji przedstawiono nową grupę o nazwie _ResourceDelGroup_ i konto usługi bramy **GatewaySvc** dodane do tej grupy.

    ![Właściwości grupy](media/service-gateway-sso-kerberos-resource/group-properties.png)

1. Otwórz wiersz polecenia i uruchom następujące polecenia kontrolera domeny **PBIEgwTestBack-end**, aby zaktualizować atrybut msDS-AllowedToActOnBehalfOfOtherIdentity konta usługi zaplecza:

    ```powershell
    $c=get-adgroupResourceDelGroup
    set-aduser **SQLService** -principalsAllowedToDelegateToAccount$c
    ```

1. Możesz sprawdzić, czy aktualizacja jest widoczna na karcie „Edytor atrybutów” we właściwościach konta usługi zaplecza w przystawce **Użytkownicy i komputery usługi Active Directory**.

Na koniec na maszynie z uruchomioną usługą bramy (**PBIEgwTestGW** w naszym przykładzie) należy przydzielić zasady lokalne „Personifikuj klienta po uwierzytelnieniu” do konta usługi bramy. Można to zrobić lub sprawdzić za pomocą Edytora lokalnych zasad grupy (**gpedit**).

1. Na maszynie bramy uruchom polecenie _gpedit.msc_.

1. Wybierz kolejno pozycje **Lokalne zasady komputera > Konfiguracja komputera > Ustawienia systemu Windows > Ustawienia zabezpieczeń > Zasady lokalne > Przypisywanie praw użytkownika**, jak pokazano na poniższej ilustracji.

    ![Przypisywanie praw użytkownika](media/service-gateway-sso-kerberos-resource/user-rights-assignment.png)

1. Na liście zasad w obszarze **Przypisywanie praw użytkownika** wybierz pozycję **Personifikuj klienta po uwierzytelnieniu**.

    ![Personifikowanie klienta](media/service-gateway-sso-kerberos-resource/impersonate-client.png)

1. Kliknij prawym przyciskiem myszy pozycję **Personifikuj klienta po uwierzytelnieniu**, otwórz okno **Właściwości** i sprawdź listę kont. Musi ona zawierać konto usługi bramy (**PBIEgwTestFront-end** **\GatewaySvc**).

1. Na liście zasad w obszarze **Przypisywanie praw użytkownika** wybierz pozycję **Działanie jako część systemu operacyjnego (SeTcbPrivilege)**. Upewnij się, że konto usługi bramy również znajduje się na liście kont.

1. Uruchom ponownie proces usługi **lokalnej bramy danych**.

## <a name="running-a-power-bi-report"></a>Uruchamianie raportu usługi Power BI

Po zakończeniu wszystkich czynności konfiguracyjnych opisanych w tym artykule możesz skonfigurować źródło danych na stronie **Zarządzanie bramą** w usłudze Power BI. Następnie w obszarze **Ustawienia zaawansowane** włącz logowanie jednokrotne i publikuj raporty oraz zestawy danych powiązane z tym źródłem danych.

![Ustawienia źródeł danych](media/service-gateway-sso-kerberos-resource/data-source-settings.png)

Ta konfiguracja będzie działać w większości przypadków. Jednak w przypadku użycia protokołu Kerberos możliwe są inne konfiguracje w zależności od środowiska. Jeśli nadal nie można załadować raportu, należy skontaktować się z administratorem domeny, aby dokładniej zbadał problem.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat **lokalnej bramy danych** i **zapytania bezpośredniego**, zapoznaj się z następującymi zasobami:

- [Lokalna brama danych](service-gateway-onprem.md)
- [Zapytanie bezpośrednie w usłudze Power BI](desktop-directquery-about.md)
- [Źródła danych obsługiwane przez zapytanie bezpośrednie](desktop-directquery-data-sources.md)
- [Zapytanie bezpośrednie i system SAP BW](desktop-directquery-sap-bw.md)
- [Zapytanie bezpośrednie i platforma SAP HANA](desktop-directquery-sap-hana.md)