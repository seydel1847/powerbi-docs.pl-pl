---
title: Używanie tego samego konta w usłudze Power BI i na platformie Azure
description: Jak używać tego samego konta logowania w usłudze Power BI i na platformie Azure
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: d9b171052bd095afc918a312ecbadba89a2471cd
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54283580"
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>Używanie tego samego konta w usłudze Power BI i na platformie Azure
Jeśli jesteś użytkownikiem usługi Power BI i platformy Azure, możesz używać tych samych danych logowania dla obu usług, dzięki czemu nie trzeba wpisywać hasła dwa razy.

Usługa Power BI loguje Cię za pomocą konta organizacyjnego skojarzonego z Twoim służbowym adresem e-mail.  Platforma Azure loguje Cię za pomocą konta Microsoft lub Twojego konta organizacyjnego.

Jeśli chcesz używać tych samych danych logowania dla platformy Azure i usługi Power BI, musisz logować się do platformy Azure za pomocą swojego konta organizacyjnego.

**Co zrobić, jeśli już loguję się do platformy Azure za pomocą swojego konta Microsoft?**

Możesz dodać konto organizacyjne jako współadministrator na platformie Azure.  Oto kroki tej procedury:

1. Zaloguj się do [portalu zarządzania platformy Azure](http://manage.windowsazure.com/). Jeśli jesteś użytkownikiem w wielu katalogach platformy Azure, kliknij pozycję **Subskrypcje**, a następnie przeprowadź filtrowanie, aby wyświetlić tylko katalog i subskrypcje, które chcesz edytować.
2. W okienku nawigacji kliknij pozycję **Ustawienia**, kliknij pozycję **Administratorzy**, a następnie kliknij przycisk **Dodaj**.
3. Wprowadź adres e-mail skojarzony z Twoim kontem organizacyjnym.
4. Wybierz subskrypcje, do których chcesz uzyskać dostęp przy użyciu konta organizacyjnego, a następnie kliknij znacznik wyboru.

Przy następnym logowaniu do portalu zarządzania platformy Azure użyj organizacyjnego adresu e-mail.

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

