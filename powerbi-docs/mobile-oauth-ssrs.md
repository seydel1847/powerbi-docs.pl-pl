---
title: Korzystanie z uwierzytelniania OAuth w celu łączenia się z serwerem raportów usługi Power BI i serwerem SSRS
description: Informacje o sposobie konfigurowania środowiska w celu zapewnienia obsługi uwierzytelniania OAuth za pomocą aplikacji mobilnej Power BI, aby umożliwić połączenie z usługami SQL Server Reporting Services 2016 lub ich nowszą wersją.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 06/07/2018
ms.author: maghan
ms.openlocfilehash: ba8a0c6868e84cf9d675fff8f69a34b4befc9b61
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34852215"
---
# <a name="using-oauth-to-connect-to-power-bi-report-server-and-ssrs"></a>Korzystanie z uwierzytelniania OAuth w celu łączenia się z serwerem raportów usługi Power BI i serwerem SSRS
Informacje o sposobie konfigurowania środowiska w celu zapewnienia obsługi uwierzytelniania OAuth za pomocą aplikacji mobilnej Power BI, aby umożliwić połączenie z serwerem raportów usługi Power BI i usługami SQL Server Reporting Services 2016 lub ich nowszą wersją.

![](media/mobile-oauth-ssrs/powerbi-mobile-oauth.png)

Uwierzytelniania OAuth możesz używać do łączenia się z serwerem raportów usługi Power BI i usługami Reporting Services w celu wyświetlania raportów i kluczowych wskaźników wydajności dla urządzeń przenośnych. Program Windows Server 2016 zapewnia pewne ulepszenia roli serwera proxy aplikacji internetowych (WAP) w zakresie tego typu uwierzytelniania. Należy pamiętać, że ta konfiguracja nie obsługuje wyświetlania raportów usługi Power BI w aplikacjach mobilnych usługi Power BI. Można je jednak wyświetlić w przeglądarce na urządzeniu przenośnym. Aby wyświetlić raporty usługi Power BI w aplikacji mobilnej należy używać uwierzytelniania systemu Windows.

## <a name="requirements"></a>Wymagania
W przypadku serwerów proxy aplikacji internetowych (Web Application Proxy — WAP) i serwerów usług Active Directory Federation Services (ADFS) jest wymagany program Windows Server 2016. Nie jest konieczne posiadanie domeny na poziomie funkcjonalności programu Windows Server 2016.

## <a name="domain-name-services-dns-configuration"></a>Konfigurowanie usług nazw domen (DNS)
Należy określić publiczny adres URL, z którym będzie się łączyć aplikacja mobilna Power BI. Może on na przykład wyglądać podobnie do poniższego adresu.

```
https://reports.contoso.com
```

Rekord DNS dla **raportów** należy ustawić na publiczny adres IP serwera proxy aplikacji internetowych (WAP). Należy również skonfigurować publiczny rekord DNS dla serwera usług AD FS. Serwer usług AD FS można na przykład skonfigurować za pomocą poniższego adresu URL.

```
https://fs.contoso.com
```

Rekord DNS dla usług **fs** należy ustawić na publiczny adres IP serwera proxy aplikacji internetowych (WAP), ponieważ zostanie on opublikowany jako część aplikacji WAP.

## <a name="certificates"></a>Certyfikaty
Certyfikaty należy skonfigurować zarówno dla aplikacji WAP, jak i dla serwera usług AD FS. Oba te certyfikaty muszą być częścią ważnego urzędu certyfikacji rozpoznawanego na urządzeniach przenośnych.

## <a name="reporting-services-configuration"></a>Konfigurowanie usług Reporting Services
W zakresie usług Reporting Services nie trzeba wykonywać wielu działań konfiguracyjnych. Wystarczy tylko upewnić się, że istnieje główna nazwa usługi umożliwiająca zapewnienie odpowiedniego uwierzytelniania Kerberos oraz że jest włączony serwer usług Reporting Services obsługujący uwierzytelnianie negocjowane.

### <a name="service-principal-name-spn"></a>Główna nazwa usługi
Główna nazwa usługi jest unikatowym identyfikatorem usługi, która korzysta z uwierzytelniania Kerberos. Upewnij się, że masz odpowiednią główną nazwę usługi w standardzie HTTP dla serwera raportów.

Aby uzyskać informacje na temat konfigurowania odpowiedniej głównej nazwy usługi dla serwera raportów, zobacz [Rejestrowanie głównej nazwy usługi dla serwera raportów](https://msdn.microsoft.com/library/cc281382.aspx).

### <a name="enabling-negotiate-authentication"></a>Włączanie uwierzytelniania negocjowanego
Aby włączyć uwierzytelnianie Kerberos na serwerze raportów, należy jako typ uwierzytelniania serwera raportów skonfigurować uwierzytelnianie RSWindowsNegotiate. Należy to zrobić w pliku rsreportserver.config.

```
<AuthenticationTypes>  
    <RSWindowsNegotiate />  
    <RSWindowsKerberos />  
    <RSWindowsNTLM />  
</AuthenticationTypes>
```

Aby uzyskać więcej informacji, zobacz [Modyfikowanie pliku konfiguracji usług Reporting Services](https://msdn.microsoft.com/library/bb630448.aspx) i [Konfigurowanie uwierzytelniania systemu Windows na serwerze raportów](https://msdn.microsoft.com/library/cc281253.aspx).

## <a name="active-directory-federation-services-adfs-configuration"></a>Konfigurowanie usług Active Directory Federation Services (AD FS)
Usługi AD FS należy skonfigurować w programie Windows Server 2016 w danym środowisku. Można to zrobić za pomocą Menedżera serwera, wybierając pozycję Dodaj role i funkcje w obszarze Zarządzanie. Aby uzyskać więcej informacji, zobacz [Usługi Active Directory Federation Services](https://technet.microsoft.com/windows-server-docs/identity/active-directory-federation-services).

### <a name="create-an-application-group"></a>Tworzenie grupy aplikacji
Na ekranie zarządzania usługami AD FS należy utworzyć grupę aplikacji dla usług Reporting Services obejmującą informacje dla aplikacji mobilnych Power BI.

Aby utworzyć grupę aplikacji, wykonaj następujące kroki.

1. W aplikacji Zarządzanie usługami AD FS Management kliknij prawym przyciskiem myszy pozycję **Grupy aplikacji** i wybierz pozycję **Dodaj grupę aplikacji**.
   
   ![](media/mobile-oauth-ssrs/adfs-add-application-group.png)
2. W kreatorze dodawania grupy aplikacji wpisz **nazwę** dla grupy aplikacji i wybierz pozycję **Aplikacja natywna uzyskująca dostęp do internetowego interfejsu API**.
   
   ![](media/mobile-oauth-ssrs/adfs-application-group-wizard1.png)
3. Wybierz pozycję **Dalej**.
4. Wpisz **nazwę** dla dodawanej aplikacji. 
5. **Identyfikator klienta** zostanie wygenerowany automatycznie. Dla systemów iOS i Android wpisz wartość *484d54fc-b481-4eee-9505-0258a1913020*.
6. Należy dodać następujące **adresy URL przekierowania**:
   
   **Wpisy dotyczące usługi Power BI dla urządzeń przenośnych — system iOS:**  
   msauth://code/mspbi-adal://com.microsoft.powerbimobile  
   msauth://code/mspbi-adalms://com.microsoft.powerbimobilems  
   mspbi-adal://com.microsoft.powerbimobile  
   mspbi-adalms://com.microsoft.powerbimobilems
   
   **Aplikacje dla systemu Android wymagają tylko następującego wpisu:**  
   urn:ietf:wg:oauth:2.0:oob
   
   ![](media/mobile-oauth-ssrs/adfs-application-group-wizard2.png)
7. Wybierz pozycję **Dalej**.
8. Podaj adres URL serwera raportów. Jest to zewnętrzny adres URL, który będzie wskazywać Twój serwer proxy aplikacji internetowych. Powinien on mieć poniższy format.
   
   > [!NOTE]
   > W tym adresie URL jest uwzględniana wielkość liter.
   > 
   > 
   
   *https://<url to report server>/reports*
   
   ![](media/mobile-oauth-ssrs/adfs-application-group-wizard3.png)
9. Wybierz pozycję **Dalej**.
10. Wybierz **Zasady kontroli dostępu**, które odpowiadają potrzebom Twojej organizacji.
    
    ![](media/mobile-oauth-ssrs/adfs-application-group-wizard4.png)
11. Wybierz pozycję **Dalej**.
12. Wybierz pozycję **Dalej**.
13. Wybierz pozycję **Dalej**.
14. Wybierz pozycję **Zamknij**.

Po zakończeniu tych kroków właściwości grupy aplikacji powinny przypominać poniższe.

![](media/mobile-oauth-ssrs/adfs-application-group.png)

## <a name="web-application-proxy-wap-configuration"></a>Konfigurowanie serwera proxy aplikacji internetowych (WAP)
Na serwerze w danym środowisku należy włączyć rolę serwera proxy aplikacji internetowych systemu Windows. Musi się to odbyć w programie Windows Server 2016. Aby uzyskać więcej informacji, zobacz [Serwer proxy aplikacji internetowych w programie Windows Server 2016](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/web-application-proxy-windows-server) i [Publikowanie aplikacji przy użyciu wstępnego uwierzytelniania usług AD FS](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/publishing-applications-using-ad-fs-preauthentication#a-namebkmk14apublish-an-application-that-uses-oauth2-such-as-a-windows-store-app).

### <a name="constrained-delegation-configuration"></a>Konfigurowanie delegowania ograniczonego
Aby przejść z uwierzytelniania OAuth na uwierzytelnianie systemu Windows, należy wykonać przejście protokołu z delegowaniem ograniczonym. Jest to część konfiguracji protokołu Kerberos. Główna nazwa usług Reporting Services już została zdefiniowana w ramach konfigurowania usług Reporting Services.

Teraz należy skonfigurować delegowanie ograniczone na koncie komputera serwera WAP w ramach usługi Active Directory. Jeśli nie masz praw do usługi Active Directory, może być konieczna pomoc ze strony administratora.

Aby skonfigurować delegowanie ograniczone, należy wykonać poniższe kroki.

1. Na komputerze, na którym zainstalowano narzędzia usługi Active Directory, uruchom narzędzie **Użytkownicy i komputery usługi Active Directory**.
2. Znajdź konto komputera dla serwera WAP. Domyślnie będzie się ono znajdowało w kontenerze komputerów.
3. Kliknij prawym przyciskiem myszy serwer WAP i przejdź do pozycji **Właściwości**.
4. Wybierz kartę **Delegowanie**.
5. Wybierz pozycję **Ufaj temu komputerowi w delegowaniu tylko do określonych usług**, a następnie pozycję **Użyj dowolnego protokołu uwierzytelniania**.
   
   ![](media/mobile-oauth-ssrs/wap-contrained-delegation1.png)
   
   To spowoduje skonfigurowanie delegowania ograniczonego dla tego konta komputera serwera WAP. Następnie należy określić usługi, do których może się odbywać delegowanie z tego komputera.
6. Wybierz pozycję **Dodaj** w obszarze pod polem usług.
   
   ![](media/mobile-oauth-ssrs/wap-contrained-delegation2.png)
7. Wybierz pozycję **Użytkownicy lub komputery**.
8. Wprowadź nazwę konta usług, z którego korzystasz w kontekście usług Reporting Services. Jest to konto, do którego została dodana główna nazwa usługi w ramach konfiguracji usług Reporting Services.
9. Wybierz główną nazwę usługi dla usług Reporting Services, a następnie wybierz pozycję **OK**.
   
   > [!NOTE]
   > Może być widoczna tylko główna nazwa usługi NetBIOS. Jeśli istnieje zarówno główna nazwa usługi NetBIOS, jak i główna nazwa usługi FQDN, obie te nazwy zostaną wybrane.
   > 
   > 
   
   ![](media/mobile-oauth-ssrs/wap-contrained-delegation3.png)
10. Po zaznaczeniu pola wyboru **Rozwinięte** wynik powinien wyglądać podobnie do poniższego.
    
    ![](media/mobile-oauth-ssrs/wap-contrained-delegation4.png)
11. Wybierz przycisk **OK**.

### <a name="add-wap-application"></a>Dodawanie aplikacji WAP
Wprawdzie istnieje możliwość publikowania aplikacji z poziomu konsoli zarządzania dostępem do raportów, ale chcemy umożliwić tworzenie aplikacji za pośrednictwem programu PowerShell. Oto polecenie umożliwiające dodanie aplikacji.

```
Add-WebApplicationProxyApplication -Name "Contoso Reports" -ExternalPreauthentication ADFS -ExternalUrl https://reports.contoso.com/reports/ -ExternalCertificateThumbprint "0ff79c75a725e6f67e3e2db55bdb103efc9acb12" -BackendServerUrl http://ContosoSSRS/reports/ -ADFSRelyingPartyName "Reporting Services - Web API" -BackendServerAuthenticationSPN "http/ContosoSSRS.contoso.com" -UseOAuthAuthentication
```

| Parametr | Komentarze |
| --- | --- |
| **ADFSRelyingPartyName** |Jest to nazwa internetowego interfejsu API, który został utworzony jako część grupy aplikacji w usługach AD FS. |
| **ExternalCertificateThumbprint** |Jest to certyfikat stosowany dla użytkowników zewnętrznych. Należy pamiętać, że ten certyfikat musi być obsługiwany na urządzeniach przenośnych i pochodzić z zaufanego urzędu certyfikacji. |
| **BackendServerUrl** |Jest to adres URL serwera raportów z serwera WAP. Jeśli serwer WAP jest w strefie DMZ, może być konieczne użycie w pełni kwalifikowanej nazwy domeny. Upewnij się, że ten adres URL jest osiągalny w przeglądarce internetowej na serwerze WAP. |
| **BackendServerAuthenticationSPN** |Jest to główna nazwa usługi utworzona w ramach konfigurowania usług Reporting Services. |

### <a name="setting-integrated-authentication-for-the-wap-application"></a>Ustawianie uwierzytelniania zintegrowanego dla aplikacji WAP
Po dodaniu aplikacji WAP należy ustawić parametr BackendServerAuthenticationMode, aby korzystał z opcji IntegratedWindowsAuthentication. Aby to zrobić, potrzebny jest identyfikator aplikacji WAP.

```
Get-WebApplicationProxyApplication “Contoso Reports” | fl
```

![](media/mobile-oauth-ssrs/wap-application-id.png)

Uruchom poniższe polecenie, aby ustawić opcję BackendServerAuthenticationMode przy użyciu identyfikatora aplikacji WAP.

```
Set-WebApplicationProxyApplication -id 30198C7F-DDE4-0D82-E654-D369A47B1EE5 -BackendServerAuthenticationMode IntegratedWindowsAuthentication
```

![](media/mobile-oauth-ssrs/wap-application-backendauth.png)

## <a name="connecting-with-the-power-bi-mobile-app"></a>Nawiązywanie połączenia z aplikacją mobilną Power BI
Z poziomu aplikacji mobilnej Power BI można nawiązać połączenie z wystąpieniem usług Reporting Services. W tym celu należy podać **zewnętrzny adres URL** aplikacji WAP.

![](media/mobile-oauth-ssrs/powerbi-mobile-app1.png)

Po wybraniu pozycji **Połącz** nastąpi przekierowanie do strony logowania w usługach AD FS. Wprowadź prawidłowe poświadczenia domeny.

![](media/mobile-oauth-ssrs/powerbi-mobile-app2.png)

Po wybraniu pozycji **Zaloguj** zobaczysz elementy ze swojego serwera usług Reporting Services.

![](media/mobile-oauth-ssrs/powerbi-mobile-app2.png)

## <a name="multi-factor-authentication"></a>Uwierzytelnianie wieloskładnikowe
W celu zapewnienia dodatkowych zabezpieczeń w danym środowisku można włączyć uwierzytelnianie wieloskładnikowe. Aby dowiedzieć się więcej, zobacz [Konfigurowanie usług AD FS 2016 i usługi Azure MFA](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/configure-ad-fs-2016-and-azure-mfa).

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="you-receive-the-error-failed-to-login-to-ssrs-server-please-verify-server-configuration"></a>Został wyświetlony błąd Nie można zalogować się do serwera usług SSRS. Zweryfikuj konfigurację serwera.

![](media/mobile-oauth-ssrs/powerbi-mobile-error.png)

Aby sprawdzić, jak daleko dotarło żądanie, możesz skonfigurować program [Fiddler](http://www.telerik.com/fiddler) jako serwer proxy dla urządzeń przenośnych. Aby program Fiddler działał jako serwer proxy dla Twojego telefonu, skonfiguruj narzędzie [CertMaker dla systemów iOS i Android](http://www.telerik.com/fiddler/add-ons) na maszynie, na której jest uruchomiony program Fiddler. Jest to dodatek firmy Telerik dla programu Fiddler.

Jeśli logowanie przy użyciu programu Fiddler przebiegnie pomyślnie, możliwe, że występuje problem z certyfikatem aplikacji WAP lub serwera usług AD FS. Korzystając z narzędzia, takiego jak [Microsoft Message Analyzer](https://www.microsoft.com/download/details.aspx?id=44226), sprawdź, czy certyfikaty są prawidłowe.

## <a name="next-steps"></a>Następne kroki
[Rejestrowanie głównej nazwy usługi dla serwera raportów](https://msdn.microsoft.com/library/cc281382.aspx)  
[Modyfikowanie pliku konfiguracji usług Reporting Services](https://msdn.microsoft.com/library/bb630448.aspx)  
[Konfigurowanie uwierzytelniania systemu Windows na serwerze raportów](https://msdn.microsoft.com/library/cc281253.aspx)  
[Usługi Active Directory Federation Services](https://technet.microsoft.com/windows-server-docs/identity/active-directory-federation-services)  
[Serwer proxy aplikacji internetowych w programie Windows Server 2016](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/web-application-proxy-windows-server)  
[Publikowanie aplikacji przy użyciu wstępnego uwierzytelniania usług AD FS](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/publishing-applications-using-ad-fs-preauthentication#a-namebkmk14apublish-an-application-that-uses-oauth2-such-as-a-windows-store-app)  
[Konfigurowanie usług AD FS 2016 i usługi Azure MFA](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/configure-ad-fs-2016-and-azure-mfa)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

