---
title: Korzystanie z alternatywnego adresu e-mail
description: Korzystanie z alternatywnego adresu e-mail
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 08/09/2017
ms.author: maghan
ms.openlocfilehash: dd9e146b22c95d8c915ea653ee287bb7a51e6b06
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2018
---
# <a name="using-an-alternate-email-address"></a>Korzystanie z alternatywnego adresu e-mail
Domyślnie adres e-mail użyty podczas tworzenia konta w usłudze Power BI służy do wysyłania aktualizacji dotyczących działań w usłudze Power BI.  Na przykład gdy użytkownik wyśle do Ciebie zaproszenie do udostępniania, zostanie ono wysłane na ten adres.

Czasami możesz chcieć, aby te wiadomości e-mail były dostarczane na alternatywny adres e-mail zamiast adresu użytego pierwotnie podczas rejestrowania się w usłudze Power BI.

## <a name="updating-through-office-365-personal-info-page"></a>Aktualizowanie przy użyciu strony informacji osobistych w usłudze Office 365
1. Przejdź do strony [informacji osobistych w usłudze Office 365](https://portal.office.com/account/#personalinfo).  Jeśli zostanie wyświetlony monit, zaloguj się przy użyciu adresu e-mail i hasła używanego w usłudze Power BI.
2. Kliknij link edycji w sekcji Szczegóły kontaktu.  
   
   > [!NOTE]
   > Jeśli link edycji nie jest wyświetlany, oznacza to, że adresem e-mail zarządza administrator usługi Office 365 i musisz skontaktować się z nim, aby zaktualizować swój adres e-mail.
   > 
   > 
   
   ![](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)
3. W polu Alternatywny adres e-mail wprowadź adres, na który mają być wysyłane aktualizacje dotyczące usługi Power BI.

> [!NOTE]
> Zmiana tego ustawienia nie wpłynie na adres e-mail używany do wysyłania aktualizacji dotyczących usług, biuletynów i innych informacji promocyjnych.  Te wiadomości będą zawsze wysyłane na adres e-mail użyty pierwotnie podczas rejestracji w usłudze Power BI.
> 
> 

## <a name="updating-with-powershell"></a>Aktualizowanie za pomocą programu PowerShell
Alternatywnie można zaktualizować adres e-mail przy użyciu programu PowerShell dla usługi Azure Active Directory. Można to zrobić przy użyciu polecenia [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser).

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

Aby uzyskać więcej informacji, zobacz [Program PowerShell usługi Azure Active Directory w wersji 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

