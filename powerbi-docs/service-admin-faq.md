---
title: Administrowanie usługą Power BI — często zadawane pytania
description: Zapoznaj się z odpowiedziami na często zadawane pytania dotyczące rejestracji, zarządzania dzierżawą i innych zadań administracyjnych usługi Power BI.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 60ac0a944b1eb54ab998fbf25cb5fb79d6dddbe6
ms.sourcegitcommit: 833cf1252807721fb1b3000487bd032bfd6c8c98
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/04/2018
ms.locfileid: "48271905"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>Administrowanie usługą Power BI — często zadawane pytania

W tym artykule przedstawiono często zadawane pytania dotyczące administrowania usługi Power BI. Omówienie administracji usługi Power BI można znaleźć w temacie [Co to jest administracja usługi Power BI?](service-admin-administering-power-bi-in-your-organization.md).

## <a name="whats-in-this-article"></a>Zawartość artykułu
**Tworzenie konta w usłudze Power BI**

* [Jak użytkownicy tworzą konta w usłudze Power BI?](#how-do-users-sign-up-for-power-bi)
* [Jak poszczególni użytkownicy w organizacji tworzą konta?](#how-do-individual-users-in-my-organization-sign-up)
* [Jak mogę uniemożliwić użytkownikom dołączanie do istniejącej dzierżawy usługi Office 365?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [Jak można zezwolić użytkownikom na dołączanie do istniejącej dzierżawy usługi Office 365?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [Jak sprawdzić, czy dzierżawa ma blokadę?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)
* [Jak uniemożliwić istniejącym użytkownikom rozpoczynanie korzystania z usługi Power BI?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [Jak można zezwolić istniejącym użytkownikom na tworzenie kont w usłudze Power BI?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Administrowanie usługi Power BI**

* [Jak zmieni się obecny sposób zarządzania tożsamością użytkowników w mojej organizacji?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Jak zarządzać usługą Power BI?](#how-do-we-manage-power-bi)
* [Jaka jest procedura przejęcia zarządzania dzierżawą utworzoną przez firmę Microsoft dla moich użytkowników?](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
* [Jeśli mam wiele domen, czy mogę kontrolować to, do której dzierżawy usługi Office 365 dodawani są użytkownicy?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)
* [Jak usunąć usługę Power BI dla użytkowników, którzy są już zarejestrowani?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [Jak sprawdzić, kiedy nowi użytkownicy dołączają do mojej dzierżawy?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [Czy istnieją dodatkowe rzeczy, na które należy się przygotować?](#are-there-any-additional-things-i-should-be-prepared-for)
* [Gdzie znajduje się moja dzierżawa usługi Power BI?](#where-is-my-power-bi-tenant-located)
* [Co to jest umowa SLA (umowa dotycząca poziomu usług) usługi Power BI?](#what-is-the-power-bi-sla)

**Zabezpieczenia w usłudze Power BI**

* [Czy usługa Power BI spełnia krajowe, regionalne i branżowe wymagania dotyczące zgodności?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Jak działają zabezpieczenia w usłudze Power BI?](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>Tworzenie konta w usłudze Power BI
### <a name="how-do-users-sign-up-for-power-bi"></a>Jak użytkownicy tworzą konta w usłudze Power BI?
Możesz utworzyć konto w usłudze Power BI za pośrednictwem [witryny internetowej usługi Power BI](https://powerbi.microsoft.com). Możesz też zarejestrować się za pośrednictwem strony zakupu usług w centrum administracyjnym usługi Office 365. Jeśli administrator zarejestruje się w usłudze Power BI, będzie mógł przydzielać licencje użytkownikom, którzy powinni otrzymać dostęp.

Ponadto poszczególni użytkownicy w organizacji mogą być w stanie zarejestrować się w usłudze Power BI za pośrednictwem [witryny internetowej usługi Power BI](https://powerbi.microsoft.com). Po zarejestrowaniu się użytkownika organizacji w usłudze Power BI zostanie do niego automatycznie przypisana bezpłatna licencja usługi Power BI. [Dowiedz się więcej](service-self-service-signup-for-power-bi.md)

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>Jak poszczególni użytkownicy w organizacji tworzą konta?
Istnieją trzy scenariusze, które mogą mieć zastosowanie do użytkowników w Twojej organizacji:

Scenariusz 1. Organizacja ma już istniejące środowisko usługi Office 365, a użytkownik rejestrujący się w usłudze Power BI ma już konto usługi Office 365.
Jeśli w tym scenariuszu użytkownik ma konto służbowe w dzierżawie (np. contoso.com), ale nie ma jeszcze konta Power BI, firma Microsoft po prostu aktywuje plan dla tego konta, a użytkownik otrzyma automatyczne powiadomienie o sposobie korzystania z usługi Power BI.

Scenariusz 2. Organizacja ma istniejące środowisko usługi Office 365, a użytkownik rejestrujący się w usłudze Power BI nie ma jeszcze konta usługi Office 365.
W tym scenariuszu użytkownik ma adres e-mail w domenie organizacji (np. contoso.com), ale nie ma jeszcze konta usługi Office 365. W takim przypadku użytkownik może zarejestrować się w usłudze Power BI i automatycznie otrzyma konto. Dzięki temu użytkownik może uzyskać dostęp do usługi Power BI. Jeśli na przykład pracownica o imieniu Nancy użycie swojego adresu e-mail (np. Nancy@contoso.com) do zarejestrowania się w usłudze, firma Microsoft automatycznie doda użytkownika Nancy w środowisku usługi Office 365 firmy Contoso i aktywuje usługę Power BI dla tego konta.

Scenariusz 3. Organizacja nie ma środowiska usługi Office 365 połączonego z domeną poczty e-mail.
Nie ma żadnych administracyjnych działań, które organizacja musi podjąć, aby skorzystać z usługi Power BI. Użytkownicy będą dodawani do nowego katalogu użytkowników działającego tylko w chmurze, a Ty będziesz mieć możliwość dobrowolnego wyboru i przejęcia tych użytkowników jako administrator dzierżawy i zarządzania nimi.

> [!IMPORTANT]
> Jeśli organizacja ma wiele domen poczty e-mail i chcesz, aby wszystkie rozszerzenia adresu e-mail znalazły się w tej samej dzierżawie, dodaj wszystkie domeny adresów e-mail do dzierżawy usługi Azure Active Directory przed zarejestrowaniem jakichkolwiek użytkowników. Nie istnieje automatyczny mechanizm przenoszenia użytkowników między dzierżawami po ich utworzeniu. Aby uzyskać więcej informacji o tym procesie, zobacz sekcję [Jeśli mam wiele domen, czy mogę kontrolować to, do której dzierżawy usługi Office 365 dodawani są użytkownicy?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) później w tym artykule oraz [Dodawanie domeny do usługi Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) w Internecie.
> 
> 

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>Jak mogę uniemożliwić użytkownikom dołączanie do istniejącej dzierżawy usługi Office 365?
Istnieją kroki, które możesz podjąć jako administrator, aby uniemożliwić użytkownikom dołączanie do istniejącej dzierżawy usługi Office 365. W przypadku zastosowania blokady próby rejestracji podejmowane przez użytkowników zakończą się niepowodzeniem, a użytkownicy zostaną przekierowani do kontaktu z administratorem w organizacji. Nie musisz powtarzać tego procesu, jeśli już wyłączono automatyczną dystrybucję licencji (np. usługa Office 365 dla instytucji edukacyjnych dla uczniów i studentów, nauczycieli i wykładowców oraz personelu).

Te kroki wymagają użycia programu Windows PowerShell. Aby rozpocząć korzystanie z programu Windows PowerShell, zobacz [Rozpoczynanie pracy z programem PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=286814).

Aby wykonać następujące kroki, musisz zainstalować najnowszą 64-bitową wersję [modułu Azure Active Directory Module dla programu Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

Po wybraniu linku wybierz opcję **Uruchom**, aby uruchomić pakiet instalatora.

**Wyłącz automatyczne dołączanie do dzierżawy**: użyj tego polecenia programu Windows PowerShell, aby uniemożliwić nowym użytkownikom dołączanie do zarządzanej dzierżawy:

* Aby wyłączyć automatyczne dołączanie do dzierżawy dla nowych użytkowników:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
* Aby włączyć automatyczne dołączanie do dzierżawy dla nowych użytkowników:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

> [!NOTE]
> Blokada uniemożliwia rejestrowanie się w usłudze Power BI nowym użytkownikom w organizacji. Użytkownicy, którzy zarejestrują się w usłudze Power BI przed wyłączeniem nowych rejestracji dla organizacji, zachowają swoje licencje. Zobacz sekcję [Jak mogę usunąć licencje?], aby uzyskać instrukcje dotyczące usuwania dostępu do usługi Power BI dla użytkowników, którzy już wcześniej zarejestrowali się w usłudze.
> 
> 

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>Jak można zezwolić użytkownikom na dołączanie do istniejącej dzierżawy usługi Office 365?
Aby umożliwić użytkownikom dołączanie do dzierżawy, uruchom przeciwne polecenie do opisanego w pytaniu powyżej.

Aby wykonać następujące kroki, musisz zainstalować najnowszą 64-bitową wersję [modułu Azure Active Directory Module dla programu Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Jak sprawdzić, czy dzierżawa ma blokadę?
Użyj następującego skryptu programu PowerShell.

Aby wykonać następujące kroki, musisz zainstalować najnowszą 64-bitową wersję [modułu Azure Active Directory Module dla programu Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Get-MsolCompanyInformation | fl allow*

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Jak uniemożliwić istniejącym użytkownikom rozpoczynanie korzystania z usługi Power BI?
Istnieją kroki, które możesz podjąć jako administrator, aby uniemożliwić użytkownikom rejestrowanie się w usłudze Power BI. W przypadku zastosowania blokady próby rejestracji podejmowane przez użytkowników zakończą się niepowodzeniem, a użytkownicy zostaną przekierowani do kontaktu z administratorem w organizacji. Nie musisz powtarzać tego procesu, jeśli już wyłączono automatyczną dystrybucję licencji (np. usługa Office 365 dla instytucji edukacyjnych dla uczniów i studentów, nauczycieli i wykładowców oraz personelu). [Dowiedz się więcej](service-admin-licensing-organization.md#enable-or-disable-individual-user-sign-up-in-azure-active-directory)

Ustawienie usługi AAD, które kontroluje tę opcję, to **AllowAdHocSubscriptions**. W przypadku większości dzierżaw dla tego ustawienia określona jest wartość true, co oznacza, że jest ono włączone. Jeśli klient nabył usługę Power BI za pośrednictwem partnera, domyślnie dla tego ustawienia może być ustawiona wartość false, co oznacza, że jest ono wyłączone.

Aby wykonać następujące kroki, musisz zainstalować najnowszą 64-bitową wersję [modułu Azure Active Directory Module dla programu Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

1. Najpierw musisz zalogować się do usługi Azure Active Directory przy użyciu poświadczeń usługi Office 365. Pierwszy wiersz spowoduje wyświetlenie monitu o podanie poświadczeń. Drugi wiersz spowoduje nawiązanie połączenia z usługą Azure Active Directory.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Po zalogowaniu się można wydać następujące polecenie, aby wyświetlić bieżącą konfigurację dzierżawy.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Przy użyciu tego polecenia można włączyć ($true) lub wyłączyć ($false) opcję AllowAdHocSubscriptions.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> Flaga AllowAdHocSubscriptions jest używana do kontrolowania kilku możliwości użytkownika w organizacji, w tym możliwości rejestrowania się w usłudze Azure Rights Management. Zmiana tej flagi wpłynie na wszystkie te możliwości.
> 
> 

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Jak można zezwolić istniejącym użytkownikom na tworzenie kont w usłudze Power BI?
Aby umożliwić istniejącym użytkownikom rejestrowanie się w usłudze Power BI, uruchom polecenie opisane w powyższym pytaniu, ale przekaż wartość true zamiast wartości false.

Aby wykonać następujące kroki, musisz zainstalować najnowszą 64-bitową wersję [modułu Azure Active Directory Module dla programu Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

1. Najpierw musisz zalogować się do usługi Azure Active Directory przy użyciu poświadczeń usługi Office 365. Pierwszy wiersz spowoduje wyświetlenie monitu o podanie poświadczeń. Drugi wiersz spowoduje nawiązanie połączenia z usługą Azure Active Directory.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Po zalogowaniu się można wydać następujące polecenie, aby wyświetlić bieżącą konfigurację dzierżawy.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Przy użyciu tego polecenia można włączyć ($true) lub wyłączyć ($false) opcję AllowAdHocSubscriptions.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> Flaga AllowAdHocSubscriptions jest używana do kontrolowania kilku możliwości użytkownika w organizacji, w tym możliwości rejestrowania się w usłudze Azure Rights Management. Zmiana tej flagi wpłynie na wszystkie te możliwości.
> 
> 

## <a name="administration-of-power-bi"></a>Administrowanie usługi Power BI
### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Jak zmieni się obecny sposób zarządzania tożsamością użytkowników w mojej organizacji?
Jeśli Twoja organizacja ma już istniejące środowisko usługi Office 365 i wszyscy użytkownicy w organizacji mają konta usługi Office 365, zarządzanie tożsamościami nie ulegnie zmianie.

Jeśli organizacja ma już istniejące środowisko usługi Office 365, ale nie wszyscy użytkownicy w organizacji mają konta usługi Office 365, utworzymy użytkownika w ramach dzierżawy i przypiszemy licencje na podstawie służbowego adresu e-mail danego użytkownika. Oznacza to, że liczba użytkowników, którymi zarządzasz w danym momencie, będzie się zwiększać w miarę tworzenia kont usługi przez użytkowników w organizacji.

Jeśli organizacja nie ma środowiska usługi Office 365 połączonego z domeną poczty e-mail, Twój sposób zarządzania tożsamościami nie zmieni się. Użytkownicy będą dodawani do nowego katalogu użytkowników działającego tylko w chmurze, a Ty będziesz mieć możliwość dobrowolnego wyboru i przejęcia tych użytkowników jako administrator dzierżawy i zarządzania nimi.

### <a name="how-do-we-manage-power-bi"></a>Jak zarządzać usługą Power BI?
Usługa Power BI zapewnia portal administracyjny, który umożliwia wyświetlanie statystyk użycia, link do centrum administracyjnego usługi Office 365 umożliwiającego zarządzanie użytkownikami i grupami oraz możliwość kontrolowania ustawień obejmujących całą dzierżawę. 

> [!NOTE]
> Twoje konto musi być oznaczone jako **Administrator globalny**, w usłudze Office 365 lub Azure Active Directory, albo musisz uzyskać przydział do roli administratora usługi Power BI, aby uzyskać dostęp do portalu administracyjnego usługi Power BI. Aby uzyskać więcej informacji o roli administratora usługi Power BI, zobacz [Opis roli administratora usługi Power BI](service-admin-role.md).
> 
> 

Aby uzyskać więcej informacji, zobacz [Portal administracyjny usługi Power BI](service-admin-portal.md).

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Jaka jest procedura przejęcia zarządzania dzierżawą utworzoną przez firmę Microsoft dla moich użytkowników?
Jeśli dzierżawa została utworzona przez firmę Microsoft, możesz przejąć dzierżawę i zarządzać nią w następujący sposób:

1. Dołącz do dzierżawy, tworząc konto w usłudze Power BI za pomocą adresu e-mail w domenie odpowiadającej domenie dzierżawy, którą chcesz zarządzać. Na przykład jeśli firma Microsoft utworzyła dzierżawę contoso.com, należy dołączyć do dzierżawy za pomocą adresu e-mail kończącego się na @contoso.com.
2. Przejmij kontrolę administracyjną, weryfikując własność domeny: po dołączeniu do dzierżawy możesz nadać sobie rolę *administratora globalnego*, weryfikując własność domeny. Aby to zrobić, wykonaj następujące kroki:
   
   1. Przejdź do [https://portal.office.com](https://portal.office.com).
   2. Wybierz ikonę Uruchamianie aplikacji w lewym górnym rogu, a następnie wybierz pozycję **Administrator**.
   3. Zapoznaj się z instrukcjami na stronie **Zostań administratorem**, a następnie wybierz pozycję **Tak, chcę być administratorem**.
      
      > [!NOTE]
      > Jeśli ta opcja nie jest widoczna, oznacza to, że ktoś już został administratorem usługi Office 365.
      > 
      > 

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Jeśli mam wiele domen, czy mogę kontrolować to, do której dzierżawy usługi Office 365 dodawani są użytkownicy?
Jeśli nic nie zrobisz, dzierżawy będą tworzone dla każdej domeny i poddomeny poczty e-mail dla użytkowników.

Jeśli chcesz, aby wszyscy użytkownicy należeli do tej samej dzierżawy niezależnie od rozszerzenia adresu e-mail:

* Utwórz docelową dzierżawę wcześniej lub użyj istniejącej dzierżawy, a następnie dodaj wszystkie istniejące domeny i poddomeny, które chcesz połączyć z dzierżawą. Wtedy wszyscy użytkownicy mający adresy e-mail w tych domenach i poddomenach automatycznie dołączą do dzierżawy docelowej po utworzeniu konta.

> [!IMPORTANT]
> Nie jest obsługiwany żaden automatyczny mechanizm przenoszenia już utworzonych użytkowników do innej dzierżawy. Aby uzyskać więcej informacji na temat dodawania domen do dzierżawy usługi Office 365, zobacz [Dodawanie domeny i użytkowników do usługi Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
> 
> 

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Jak usunąć usługę Power BI dla użytkowników, którzy są już zarejestrowani?
Jeśli użytkownik zarejestrował się już w usłudze Power BI, ale nie chcesz, aby miał dostęp do usługi Power BI, możesz usunąć licencję usługi Power BI dla tego użytkownika.

1. Przejdź do centrum administracyjnego usługi Office 365.
2. Na lewym pasku nawigacyjnym wybierz pozycję **Użytkownicy** > **Aktywni użytkownicy**.
3. Znajdź użytkownika, którego licencję chcesz usunąć, a następnie wybierz jego nazwę > **Edytuj**.
4. Na stronie szczegółów użytkownika wybierz opcję **Licencje** w lewym pasku nawigacyjnym.
5. Usuń zaznaczenie pola wyboru **Power BI (wersja bezpłatna)** lub **Power BI Pro**, w zależności od licencji zastosowanej do konta użytkownika.
6. Wybierz pozycję **Zapisz**.

> [!NOTE]
> Możesz też przeprowadzać zbiorcze zarządzanie licencjami użytkowników. Aby to zrobić, wybierz wielu użytkowników i wybierz opcję **Edytuj**.
> 
> 

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Jak sprawdzić, kiedy nowi użytkownicy dołączają do mojej dzierżawy?
Użytkownicy, którzy dołączyli do dzierżawy w ramach tego programu, otrzymują unikatową licencję, którą można odfiltrować w okienku aktywnego użytkownika na pulpicie nawigacyjnym administratora.

Aby utworzyć ten nowy widok, w centrum administracyjnym usługi Office 365 przejdź do pozycji **Użytkownicy** > **Aktywni użytkownicy** oraz w menu **Wybierz widok** wybierz opcję **Nowy widok**. Nazwij nowy widok i w pozycji **Przypisana licencja** wybierz opcję **Power BI (wersja bezpłatna)** lub **Power BI Pro**. Możesz mieć wybraną tylko jedną licencję na widok. Jeśli masz w organizacji obie licencje, **Power BI (wersja bezpłatna)** i **Power BI Pro**, musisz utworzyć dwa widoki. Po utworzeniu nowego widoku możesz zobaczyć wszystkich użytkowników w dzierżawie, którzy zarejestrowali się w tym programie.

### <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Czy istnieją dodatkowe rzeczy, na które należy się przygotować?
Może wzrosnąć liczba żądań o resetowanie haseł. Aby uzyskać informacje o tym procesie, zobacz [Resetowanie hasła użytkownika](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c).

Możesz usunąć użytkownika z dzierżawy za pośrednictwem standardowego procesu w centrum administracyjnym usługi Office 365. Jeśli jednak użytkownik nadal ma aktywny adres e-mail od organizacji, będzie w stanie ponownie dołączyć, chyba że zablokujesz wszystkim użytkownikom możliwość dołączania.

### <a name="where-is-my-power-bi-tenant-located"></a>Gdzie znajduje się moja dzierżawa usługi Power BI?
Aby dowiedzieć się, gdzie znajduje się dzierżawa usługi Power BI, czyli gdzie mieści się tak zwany region danych, zobacz [Gdzie znajduje się moja dzierżawa usługi Power BI?](service-admin-where-is-my-tenant-located.md)

### <a name="what-is-the-power-bi-sla"></a>Co to jest umowa SLA usługi Power BI?
Aby uzyskać informacje na temat umowy SLA (umowy dotyczącej poziomu usług) usługi Power BI, zapoznaj się z artykułem dotyczącym [postanowień licencyjnych i dokumentacji](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) w sekcji **Licencjonowanie** witryny internetowej licencjonowania firmy Microsoft.

## <a name="security-in-power-bi"></a>Zabezpieczenia w usłudze Power BI
### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Czy usługa Power BI spełnia krajowe, regionalne i branżowe wymagania dotyczące zgodności?
Dowiedz się więcej na temat zgodności usługi Power BI na stronie [Centrum zaufania firmy Microsoft](http://go.microsoft.com/fwlink/?LinkId=785324).

### <a name="how-does-security-work-in-power-bi"></a>Jak działają zabezpieczenia w usłudze Power BI?
Usługa Power BI jest oparta na usłudze Office 365, która z kolei jest oparta na usługach platformy Azure, takich jak usługa Azure Active Directory. Aby uzyskać omówienie architektury usługi Power BI, zobacz [Zabezpieczenia usługi Power BI](service-admin-power-bi-security.md). 

## <a name="next-steps"></a>Następne kroki
[Portal administracyjny usługi Power BI](service-admin-portal.md)  
[Opis roli administratora usługi Power BI](service-admin-role.md)  
[Rejestracja samoobsługowa w usłudze Power BI](service-self-service-signup-for-power-bi.md)  
[Zakup usługi Power BI Pro](service-admin-purchasing-power-bi-pro.md)  
[Power BI Premium — co to jest?](service-premium.md)  
[Jak kupić usługę Power BI Premium](service-admin-premium-purchase.md)  
[Zarządzanie kontami użytkowników usługi Office 365](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Zarządzanie grupami usługi Office 365](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  
[Zarządzanie grupą w usługach Power BI i Office 365](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Oficjalny dokument na temat usługi Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)