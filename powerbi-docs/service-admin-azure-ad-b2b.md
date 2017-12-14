---
title: "Dystrybucja zawartości usługi Power BI do zewnętrznych użytkowników (gości) przy użyciu usługi Azure AD B2B"
description: "Usługa Power BI integruje się z usługą Azure Active Directory Business-to-business (Azure AD B2B), aby zapewnić bezpieczny sposób dystrybucji zawartości usługi Power BI do użytkowników (gości) spoza organizacji."
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
ms.date: 11/14/2017
ms.author: asaxton
ms.openlocfilehash: 5dabaa09923203c31572b413f8674b76028b7483
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Dystrybucja zawartości usługi Power BI do zewnętrznych użytkowników (gości) przy użyciu usługi Azure AD B2B

Usługa Power BI integruje się z usługą Azure Active Directory Business-to-business (Azure AD B2B), aby zapewnić bezpieczny sposób dystrybucji zawartości usługi Power BI do użytkowników (gości) spoza organizacji, przy jednoczesnym zachowaniu kontroli nad danymi wewnętrznymi.

> [!VIDEO https://www.youtube.com/embed/xxQWEQ1NnlY]

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

Aby wykonać zaproszenie w dowolnym momencie, dodaj zewnętrznego użytkownika do listy dostępu aplikacji podczas jej publikowania.

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

## <a name="next-steps"></a>Następne kroki

Aby uzyskać bardziej szczegółowe informacje, w tym dotyczące działania zabezpieczeń na poziomie wiersza, zapoznaj się z [oficjalnym dokumentem](https://aka.ms/powerbi-b2b-whitepaper).

Aby uzyskać informacje dotyczące usługi Azure Active Directory B2B, zobacz [Co to jest współpraca w usłudze Azure AD B2B?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)