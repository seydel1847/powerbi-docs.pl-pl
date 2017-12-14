---
title: "Używanie tego samego konta w usłudze Power BI i na platformie Azure"
description: "Jak używać tego samego konta logowania w usłudze Power BI i na platformie Azure"
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
ms.date: 06/28/2017
ms.author: asaxton
ms.openlocfilehash: a601e4252e8c2b3bc130b61139ffb528742ea7ea
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
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

