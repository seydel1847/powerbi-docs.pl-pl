---
title: Konfigurowanie ustawień serwera proxy dla lokalnej bramy danych
description: Informacje dotyczące konfiguracji ustawień serwera proxy dla lokalnej bramy danych.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 11/21/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: ef554d7190709565610336169b4883d71970f822
ms.sourcegitcommit: b25ae650643b0a62f33d7c1741307137b9cec316
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/05/2018
ms.locfileid: "34799561"
---
# <a name="configuring-proxy-settings-for-the-on-premises-data-gateway"></a>Konfigurowanie ustawień serwera proxy dla lokalnej bramy danych
Środowisko pracy może wymagać, aby dostęp do Internetu odbywał się za pośrednictwem serwera proxy. Może to uniemożliwiać lokalnej bramie danych nawiązanie połączenia z usługą.

## <a name="does-your-network-use-a-proxy"></a>Czy w Twojej sieci jest używany serwer proxy?
W następującym wpisie w witrynie superuser.com opisano, jak można ustalić, czy w sieci znajduje się serwer proxy.

[How do I know what proxy server I'm using? (Jak sprawdzić, jakiego serwera proxy używam?) (SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## <a name="configuration-file-location-and-default-configuration"></a>Lokalizacja pliku konfiguracji i konfiguracja domyślna
Informacje o konfiguracji serwera proxy znajdują się w pliku konfiguracji platformy .NET. Lokalizacja i nazwy plików zależą od używanej bramy.

### <a name="on-premises-data-gateway"></a>Lokalna brama danych
Lokalna brama danych używa dwóch głównych plików konfiguracji.

**Konfiguracja**

Pierwszy plik jest używany przez ekrany, które umożliwiają faktyczne skonfigurowanie bramy. W przypadku problemów z konfigurowaniem bramy należy przyjrzeć się zawartości tego pliku.

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Usługa systemu Windows**

Drugi plik jest używany przez usługę systemu Windows, która współdziała z usługą Power BI i obsługuje żądania.

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

## <a name="configuring-proxy-settings"></a>Konfigurowanie ustawień serwera proxy
Poniżej przedstawiono domyślną konfigurację serwera proxy.

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

Konfiguracja domyślna korzysta z uwierzytelniania systemu Windows. Jeśli Twój serwer proxy korzysta z innej formy uwierzytelniania, musisz zmienić ustawienia. Jeśli masz wątpliwości, skontaktuj się z administratorem sieci. Uwierzytelnianie podstawowe serwera proxy nie jest zalecane, dlatego próba użycia uwierzytelniania podstawowego serwera proxy może spowodować błędy uwierzytelniania, co w konsekwencji powoduje nieprawidłowe skonfigurowanie bramy. Aby rozwiązać ten problem, użyj silniejszego mechanizmu uwierzytelniania serwera proxy.

Oprócz używania poświadczeń domyślnych, można dodać element <proxy>, aby bardziej szczegółowo zdefiniować ustawienia serwera proxy. Na przykład można określić, że lokalna brama danych powinna zawsze używać serwera proxy, nawet w przypadku zasobów lokalnych, przez ustawienie wartości false dla parametru bypassonlocal. Może to pomóc w rozwiązywaniu problemów w sytuacjach, gdy chcesz śledzić wszystkie żądania https pochodzące z lokalnej bramy danych w plikach dziennika serwera proxy. Poniższa przykładowa konfiguracja określa, że wszystkie żądania muszą przejść przez określony serwer proxy o adresie IP 192.168.1.10.

    <system.net>
        <defaultProxy useDefaultCredentials="true">
            <proxy  
                autoDetect="false"  
                proxyaddress="http://192.168.1.10:3128"  
                bypassonlocal="false"  
                usesystemdefault="true"
            />  
        </defaultProxy>
    </system.net>

Aby dowiedzieć się więcej o konfiguracji elementów serwera proxy w plikach konfiguracji .NET, zobacz [defaultProxy Element (Network Settings) (Element defaultProxy — ustawienia sieci)](https://msdn.microsoft.com/library/kd3cf2ex.aspx).

## <a name="changing-the-gateway-service-account-to-a-domain-user"></a>Zmiana konta usługi bramy na użytkownika domeny
Podczas konfigurowania ustawień serwera proxy pod kątem używania domyślnych poświadczeń zgodnie z powyższymi wskazówkami mogą wystąpić problemy z uwierzytelnianiem na serwerze proxy. Jest to spowodowane tym, że domyślnym kontem usługi jest identyfikator SID usługi, a nie uwierzytelniony użytkownik domeny. Aby umożliwić poprawne uwierzytelnianie na serwerze proxy, można zmienić konto usługi bramy.

> [!NOTE]
> Zaleca się korzystanie z zarządzanego konta usługi, co pozwala uniknąć resetowania haseł. Dowiedz się, jak utworzyć [zarządzane konto usługi](https://technet.microsoft.com/library/dd548356.aspx) w usłudze Active Directory.
> 
> 

### <a name="change-the-on-premises-data-gateway-service-account"></a>Zmienianie konta usługi lokalnej bramy danych
1. Zmień konto usługi systemu Windows dla **usługi lokalnej bramy danych**.
   
    Domyślne konto dla tej usługi to *NT SERVICE\PBIEgwService*. Musisz je zmienić na konto użytkownika domeny usługi Active Directory. Możesz też użyć zarządzanego konta usługi, aby uniknąć konieczności zmiany hasła.
   
    Musisz zmienić konto na karcie **Logowanie** we właściwościach usługi systemu Windows.
2. Uruchom ponownie **usługę lokalnej bramy danych**.
   
    W wierszu polecenia z uprawnieniami administratora uruchom następujące polecenia.
   
        net stop PBIEgwService
   
        net start PBIEgwService
3. Uruchom **konfiguratora lokalnej bramy danych**. Możesz wybrać przycisk Start systemu Windows i wyszukać *lokalną bramę danych*.
4. Zaloguj się do usługi Power BI.
5. Przywróć bramę przy użyciu klucza odzyskiwania.
   
    Pozwoli to nowemu kontu usługi odszyfrować przechowywane poświadczenia dla źródeł danych.
    
> [!NOTE]
> Bezpośrednia zmiana konta usługi za pomocą panelu sterowania usług nie powoduje automatycznej aktualizacji listy ACL. Należy się upewnić, że nowe konto usługi ma dostęp do plików i folderu instalacji. Folder instalacji bramy można znaleźć w ścieżce C:\Program Files\On-premises data gateway. 
> 

## <a name="next-steps"></a>Następne kroki
[Lokalna brama danych (tryb osobisty)](service-gateway-personal-mode.md)
[Informacje dotyczące zapory](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

