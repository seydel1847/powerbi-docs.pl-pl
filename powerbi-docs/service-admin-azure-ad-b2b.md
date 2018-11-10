---
title: Dystrybucja zawartości usługi Power BI do zewnętrznych użytkowników (gości) przy użyciu usługi Azure AD B2B
description: Usługa Power BI integruje się z usługą Azure Active Directory Business-to-business (Azure AD B2B), aby zapewnić bezpieczny sposób dystrybucji zawartości usługi Power BI do użytkowników (gości) spoza organizacji.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: dded0f38ccc4c871bf402240aba25b11106bac09
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973217"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Dystrybucja zawartości usługi Power BI do zewnętrznych użytkowników (gości) przy użyciu usługi Azure AD B2B

Usługa Power BI integruje się z usługą Azure Active Directory business-to-business (Azure AD B2B), aby zapewnić bezpieczny sposób dystrybucji zawartości usługi Power BI do użytkowników (gości) spoza organizacji, przy jednoczesnym zachowaniu kontroli nad danymi wewnętrznymi.

## <a name="enable-access"></a>Włączanie dostępu

Upewnij się, że funkcja [ustawień eksportowania i udostępniania](service-admin-portal.md#export-and-sharing-settings) została włączona w portalu administracyjnym usługi Power BI, zanim zaprosisz użytkowników-gości.

## <a name="who-can-you-invite"></a>Kogo można zaprosić?

Możesz zaprosić użytkowników-gości korzystających z dowolnego adresu e-mail, w tym kont osobistych, takich jak gmail.com, outlook.com i hotmail.com. W usłudze Azure AD B2B te adresy są nazywane *tożsamościami społecznościowymi*.

## <a name="invite-guest-users"></a>Zapraszanie gości

Zaproszenia są wymagane tylko w sytuacji, gdy zewnętrzny użytkownik-gość jest zapraszany do organizacji po raz pierwszy. Istnieją dwa sposoby zapraszania użytkowników: zaproszenia planowane i zaproszenia ad hoc.

### <a name="planned-invites"></a>Zaproszenia planowane

Użyj zaproszenia planowanego, jeśli wiesz, których użytkowników chcesz zaprosić. Zaproszenie możesz wysłać przy użyciu witryny Azure Portal lub programu PowerShell. Aby zapraszać inne osoby, musisz być administratorem dzierżawy.

Wykonaj poniższe kroki, aby wysłać zaproszenie w witrynie Azure Portal.

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Azure Active Directory**.

1. W obszarze **Zarządzanie** przejdź kolejno do pozycji **Użytkownicy** > **Wszyscy użytkownicy** > **Nowy użytkownik-gość**.

    ![Portal Azure AD — nowy użytkownik gość](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

1. Wprowadź **adres e-mail** oraz **osobistą wiadomość**.

    ![Portal Azure AD — wiadomość z zaproszeniem nowego użytkownika gościa](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

1. Wybierz opcję **Zaproś**.

Aby zaprosić więcej niż jednego użytkownika gościa, użyj programu PowerShell. Więcej informacji można znaleźć w temacie [Przykłady kodu i programu PowerShell na potrzeby współpracy B2B w usłudze Azure AD](/azure/active-directory/b2b/code-samples/).

Użytkownik gość musi wybrać opcję **Rozpoczynanie pracy** w odebranej wiadomości e-mail z zaproszeniem. Następnie gość zostanie dodany do dzierżawy.

![Wiadomość e-mail z zaproszeniem użytkownika gościa](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Zaproszenia ad hoc

Aby wykonać to zaproszenie w dowolnym momencie, dodaj zewnętrznego użytkownika do pulpitu nawigacyjnego lub raportu za pomocą udziału interfejsu użytkownika lub aplikacji poprzez stronę dostępu. Oto przykład tego, co można zrobić podczas zapraszania użytkownika zewnętrznego do korzystania z aplikacji.

![Użytkownik zewnętrzny dodany do listy dostępu aplikacji](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Użytkownik-gość otrzyma wiadomość e-mail z informacją o udostępnieniu aplikacji.

![Wiadomość e-mail z informacjami o aplikacji udostępnionej gościowi](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

Gość musi zalogować się przy użyciu firmowego adresu e-mail. Po zalogowaniu zostanie wyświetlony monit o zaakceptowanie zaproszenia. Po zalogowaniu gość zostanie przekierowany do zawartości aplikacji. Aby wrócić do aplikacji, może on dodać link do zakładek lub zapisać wiadomość e-mail.

## <a name="licensing"></a>Licencjonowanie

Użytkownik-gość musi mieć odpowiednie licencje, aby wyświetlić udostępnioną aplikację. W tym celu można skorzystać z jednej z trzech metod: użycie usługi Power BI Premium, przypisanie licencji usługi Power BI Pro lub użycie licencji usługi Power BI Pro gościa.

### <a name="use-power-bi-premium"></a>Użycie usługi Power BI Premium

Przypisanie obszaru roboczego aplikacji do [pojemności usługi Power BI Premium](service-premium.md) umożliwia gościom używanie aplikacji bez potrzeby posiadania licencji Power BI Pro. Ponadto licencja usługi Power BI Premium zapewnia aplikacjom inne możliwości, takie jak zwiększona częstotliwość odświeżania, dedykowana pojemność i modele o dużych rozmiarach.

![Użycie usługi Power BI Premium](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-a-power-bi-pro-license-to-guest-user"></a>Przypisanie licencji usługi Power BI Pro do użytkownika-gościa

Przypisanie licencji usługi Power BI Pro do użytkownika-gościa w ramach dzierżawy umożliwia mu wyświetlanie zawartości w tej dzierżawie.

![Przypisanie licencji Pro z dzierżawy](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Użytkownik gość używa własnej licencji Power BI Pro

Gość ma już licencję Power BI Pro przypisaną w ramach swojej dzierżawy.

![Użytkownik gość używa własnej licencji](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia

* Zewnętrzni goście B2B są ograniczeni tylko do korzystania z zawartości. Zewnętrzni goście B2B mogą wyświetlać aplikacje, pulpity nawigacyjne i raporty, eksportować dane oraz tworzyć subskrypcje e-mail dla pulpitów nawigacyjnych i raportów. Nie mogą uzyskiwać dostępu do obszarów roboczych ani publikować własnej zawartości.

* Ta funkcja nie jest obecnie dostępna w aplikacjach mobilnych Power BI. Na urządzeniu przenośnym zawartość usługi Power BI udostępnianą za pośrednictwem usługi Azure AD B2B można wyświetlać w przeglądarce.

* Ta funkcja nie jest obecnie dostępna w składniku Web Part raportu usługi SharePoint Online w usłudze Power BI.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać szczegółowe informacje, w tym opis sposobu działania zabezpieczeń na poziomie wiersza, zapoznaj się z oficjalnym dokumentem: [Dystrybucja zawartości usługi Power BI do zewnętrznych użytkowników (gości) przy użyciu usługi Azure AD B2B](https://aka.ms/powerbi-b2b-whitepaper).

Informacje dotyczące usługi Azure AD B2B można znaleźć w temacie [Co to jest współpraca w usłudze Azure AD B2B?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b/)
