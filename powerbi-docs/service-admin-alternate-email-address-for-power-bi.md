---
title: Korzystanie z alternatywnego adresu e-mail
description: Korzystanie z alternatywnego adresu e-mail
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/01/2018
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 5998f4b63a168c3056a5464844d008bd657ef7c9
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54294279"
---
# <a name="using-an-alternate-email-address"></a>Korzystanie z alternatywnego adresu e-mail

Podczas tworzenia konta usługi Power BI podajesz adres e-mail. Domyślnie usługa Power BI używa tego adresu do wysyłania aktualizacji dotyczących działań w usłudze. Na przykład gdy inny użytkownik wysyła do Ciebie zaproszenie do udostępniania, jest ono przekazywane na ten adres.

W niektórych przypadkach możesz wybrać opcję dostarczania tych wiadomości e-mail na adres e-mail inny niż użyty podczas tworzenia konta. W tym artykule wyjaśniono, jak określić adres alternatywny w usłudze Office 365 i w programie PowerShell. Przedstawiono również sposób rozpoznawania adresu e-mail w usłudze Azure Active Directory (Azure AD).

> [!NOTE]
> Określanie adresu alternatywnego nie wpływa na to, którego adresu e-mail usługa Power BI używa na potrzeby aktualizacji usług, biuletynów i innych informacji promocyjnych.  Wiadomości tego typu są zawsze wysyłane na adres e-mail, którego użyto podczas tworzenia konta usługi Power BI.

## <a name="use-office-365"></a>Korzystanie z usługi Office 365

Aby określić adres alternatywny w usłudze Office 365, wykonaj poniższe kroki.

1. Otwórz [stronę informacji osobistych w usłudze Office 365](https://portal.office.com/account/#personalinfo). Jeśli zostanie wyświetlony monit, zaloguj się przy użyciu adresu e-mail i hasła używanego w usłudze Power BI.

1. W menu po lewej stronie wybierz pozycję **Dane osobowe**.

1. W sekcji **Szczegóły kontaktu** wybierz pozycję **Edytuj**.

    Jeśli nie możesz edytować swoich danych, oznacza to, że Twój adres e-mail jest zarządzany przez administratora usługi Office 365. Skontaktuj się z administratorem, aby zaktualizować adres e-mail.

    ![Szczegóły kontaktu](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)

1. W polu **Alternatywny adres e-mail** wprowadź adres, na który mają być wysyłane aktualizacje dotyczące usługi Power BI.

## <a name="use-powershell"></a>Korzystanie z programu PowerShell

Aby określić adres alternatywny w programie PowerShell, użyj polecenia [Set-AzureADUser](/powershell/module/azuread/set-azureaduser/).

```powershell
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

## <a name="email-address-resolution-in-azure-ad"></a>Rozpoznawanie adresów e-mail w usłudze Azure AD

Podczas przechwytywania tokenu osadzania usługi Azure AD na potrzeby usługi Power BI można korzystać z trzech różnych typów adresów e-mail:

* Główny adres e-mail skojarzony z kontem usługi Azure AD użytkownika

* Adres e-mail UserPrincipalName (UPN)

* *Adres e-mail typu „other”* (atrybut tablicy)

Usługa Power BI wybiera adres e-mail do użycia na podstawie następującej sekwencji:

1. Jeśli w obiekcie użytkownika usługi Azure AD znajduje się atrybut poczty, usługa Power BI skorzysta z tego atrybutu poczty na potrzeby adresu e-mail.

1. Jeśli adres e-mail UPN *nie* jest adresem e-mail należącym do domeny **\*.onmicrosoft.com** (informacja po symbolu „@”), usługa Power BI użyje tego atrybutu poczty na potrzeby adresu e-mail.

1. Jeśli w obiekcie użytkownika usługi AAD znajduje się atrybut tablicy *„other” dla adresu e-mail*, jest używany pierwszy adres e-mail z tej listy (ponieważ w tym atrybucie może znajdować się lista adresów e-mail).

1. Jeśli żaden z powyższych warunków nie został spełniony, jest używany adres UPN.

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

