---
title: Dystrybucja zawartości usługi Power BI do zewnętrznych użytkowników (gości) przy użyciu usługi Azure AD B2B
description: Usługa Power BI integruje się z usługą Azure Active Directory Business-to-business (Azure AD B2B), aby zapewnić bezpieczny sposób dystrybucji zawartości usługi Power BI do użytkowników (gości) spoza organizacji.
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 16820050ad879b128482af5754bc53973449f982
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/08/2018
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Dystrybucja zawartości usługi Power BI do zewnętrznych użytkowników (gości) przy użyciu usługi Azure AD B2B

Usługa Power BI integruje się z usługą Azure Active Directory Business-to-business (Azure AD B2B), aby zapewnić bezpieczny sposób dystrybucji zawartości usługi Power BI do użytkowników (gości) spoza organizacji, przy jednoczesnym zachowaniu kontroli nad danymi wewnętrznymi.

> [!VIDEO https://www.youtube.com/embed/xxQWEQ1NnlY]

> [!NOTE]
> Zanim zaprosisz użytkowników-gości, musisz **włączyć** funkcję [Ustawienia eksportowania i udostępniania](service-admin-portal.md#export-and-sharing-settings) w ustawieniach dzierżawy portalu administracyjnego usługi Power BI.

> [!NOTE]
> Ta funkcja nie jest obecnie dostępna w aplikacjach mobilnych Power BI. Na urządzeniu przenośnym zawartość usługi Power BI udostępnianą za pośrednictwem usługi Azure AD B2B można wyświetlać w przeglądarce. 

## <a name="who-can-you-invite"></a>Kogo można zaprosić?

Możesz zaprosić użytkowników-gości korzystających z dowolnego adresu e-mail, w tym kont osobistych, takich jak gmail.com, outlook.com lub hotmail.com. W usłudze Azure B2B są one nazywane „identyfikatorami społecznościowymi”. Aby uzyskać więcej informacji, zobacz [Azure B2B](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).

## <a name="invite-guest-users"></a>Zapraszanie gości

Istnieją dwa sposoby na zaproszenie gości do dzierżawy usługi Power BI: zaproszenia planowane i zaproszenia ad hoc. Zaproszenia są wymagane tylko podczas pierwszego zapraszania użytkownika zewnętrznego do organizacji.

### <a name="planned-invites"></a>Zaproszenia planowane

Zaproszenie planowane jest wykonywane w witrynie Microsoft Azure Portal w usłudze Azure AD lub przy użyciu programu PowerShell. Tej opcji należy użyć, jeśli wiesz, których użytkowników należy zaprosić. 

**Tworzenie użytkowników gości w portalu usługi Azure AD wymaga pozycji administratora dzierżawy.**

1. Przejdź do witryny [Azure Portal](https://portal.azure.com) i wybierz opcję **Azure Active Directory**.

2. Przejdź do pozycji **Użytkownicy i grupy** > **Wszyscy użytkownicy** > **Nowy użytkownik gość**.

    ![Portal Azure AD — nowy użytkownik gość](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

3. Wprowadź **adres e-mail** oraz **osobistą wiadomość**.

    ![Portal Azure AD — wiadomość z zaproszeniem nowego użytkownika gościa](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

4. Wybierz opcję **Zaproś**.

Aby zaprosić więcej niż jednego użytkownika gościa, użyj programu PowerShell. Aby uzyskać więcej informacji, zobacz [Funkcja współpracy między firmami przy użyciu usługi Azure Active Directory oraz przykłady programu PowerShell](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-code-samples).

Użytkownik gość musi wybrać opcję **Rozpoczynanie pracy** w odebranej wiadomości e-mail z zaproszeniem. Następnie gość zostanie dodany do dzierżawy.

![Wiadomość e-mail z zaproszeniem użytkownika gościa](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Zaproszenia ad hoc

Aby wykonać to zaproszenie w dowolnym momencie, dodaj zewnętrznego użytkownika do pulpitu nawigacyjnego lub raportu za pomocą udziału interfejsu użytkownika lub aplikacji poprzez stronę dostępu.

Oto przykład tego, co można zrobić podczas zapraszania użytkownika zewnętrznego do korzystania z aplikacji.
![Użytkownik zewnętrzny dodany do listy dostępu aplikacji](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Gość otrzyma wiadomość e-mail z informacją o udostępnieniu aplikacji.

![Wiadomość e-mail z informacjami o aplikacji udostępnionej gościowi](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

Gość musi zalogować się przy użyciu firmowego adresu e-mail. Po zalogowaniu zostanie wyświetlony monit o zaakceptowanie zaproszenia. Po zalogowaniu gość zostanie przekierowany do zawartości aplikacji. Aby powrócić do aplikacji, należy dodać link do zakładek lub zapisać wiadomość e-mail.

## <a name="licensing"></a>Licencjonowanie

Gość musi mieć odpowiednie licencje, aby wyświetlić udostępnioną aplikację. Istnieją trzy opcje realizacji tego kroku.

### <a name="use-power-bi-premium"></a>Użycie usługi Power BI Premium

Przypisanie obszaru roboczego aplikacji do usługi Power BI Premium umożliwi gościom używanie aplikacji bez potrzeby posiadania licencji Power BI Pro. Ponadto licencja Power BI Premium zapewnia aplikacjom inne możliwości, takie jak zwiększona częstotliwość odświeżania, dedykowana pojemność i modele o dużych rozmiarach.

![Użycie usługi Power BI Premium](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-power-bi-pro-license-to-guest-user"></a>Przypisanie licencji Power BI Pro do użytkownika gościa

Przypisanie licencji Power BI Pro do użytkownika gościa w ramach dzierżawy umożliwi mu wyświetlenie zawartości.

> [!NOTE]
> Licencja Power BI Pro z dzierżawy ma zastosowanie do użytkowników gości tylko wtedy, gdy uzyskują oni dostęp do zawartości w dzierżawie.

![Przypisanie licencji Pro z dzierżawy](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Użytkownik gość używa własnej licencji Power BI Pro

Gość ma już licencję Power BI Pro przypisaną w ramach swojej dzierżawy.

![Użytkownik gość używa własnej licencji](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia

* W przypadku zaproszenia użytkowników-gości korzystających z osobistych kont e-mail, takich jak gmail.com, outlook.com lub hotmail.com, można wykonać to [osadzone wideo](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-b2b-redemption-experience), aby zobaczyć przykład sposobu, w jaki użytkownik może się zarejestrować.
* Zewnętrzni goście B2B są ograniczeni tylko do korzystania z zawartości. Zewnętrzni goście B2B mogą wyświetlać aplikacje, pulpity nawigacyjne i raporty, eksportować dane oraz tworzyć subskrypcje e-mail dla pulpitów nawigacyjnych i raportów. Nie mogą uzyskiwać dostępu do obszarów roboczych ani publikować własnej zawartości.
* Ta funkcja nie jest obecnie dostępna w aplikacjach mobilnych Power BI. Na urządzeniu przenośnym zawartość usługi Power BI udostępnianą za pośrednictwem usługi Azure AD B2B można wyświetlać w przeglądarce.
* Stosowanie użytkowników-gości z usługą Power BI nie jest obsługiwane w suwerennych chmurach (dla instytucji rządowych).

## <a name="next-steps"></a>Następne kroki

Aby uzyskać bardziej szczegółowe informacje, w tym dotyczące działania zabezpieczeń na poziomie wiersza, zapoznaj się z [oficjalnym dokumentem](https://aka.ms/powerbi-b2b-whitepaper).

Aby uzyskać informacje dotyczące usługi Azure Active Directory B2B, zobacz [Co to jest współpraca w usłudze Azure AD B2B?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)
