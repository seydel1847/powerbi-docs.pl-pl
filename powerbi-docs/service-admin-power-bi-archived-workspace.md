---
title: Zarchiwizowany obszar roboczy usługi Power BI
description: Zarchiwizowany obszar roboczy usługi Power BI po zarządzaniu dzierżawą usługi Office 365
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 8b9fcf1c6121c4aeecfdf948b77493f1f2a7f825
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="power-bi-archived-workspace"></a>Zarchiwizowany obszar roboczy usługi Power BI
Za pomocą usługi Power BI każdy może zarejestrować się i rozpocząć korzystanie z usługi w ciągu kilku minut.  Później dział IT Twojej organizacji może postanowić przejąć zarządzanie usługą Power BI dla użytkowników w organizacji.  Jeśli wystąpi takie przejęcie, skorzystasz z centralnego zarządzania użytkownikami i uprawnieniami w Twojej organizacji oraz możesz wykorzystać zalety prostszego logowania się przy użyciu tej samej nazwy użytkownika i hasła używanych w przypadku innych usług w Twojej organizacji. 

Wszelka zawartość utworzona zanim dział IT zaczął zarządzać usługą Power BI zostanie umieszczona w zarchiwizowanym obszarze roboczym usługi Power BI, który jest dostępny z lewego paska nawigacji [usługi Power BI](https://app.powerbi.com).  Należy rozpocząć tworzenie nowej zawartości usługi Power BI w obszarze Mój obszar roboczy, który jest zabezpieczony i zarządzany przez dział IT Twojej organizacji.  Zarchiwizowany obszar roboczy będzie nadal istniał, ale istnieją ograniczenia dotyczące działań, które można wykonać na zawartości w Twoim zarchiwizowanym obszarze roboczym.  Aby usunąć te ograniczenia, musisz zmigrować zawartość ze swojego zarchiwizowanego obszaru roboczego do swojego obszaru roboczego zarządzanego przez dział IT.

## <a name="restrictions-in-your-archived-workspace"></a>Ograniczenia w zarchiwizowanym obszarze roboczym
Żadna zawartość nie zostanie usunięta ze zarchiwizowanego obszaru roboczego.  Możesz nadal pobierać dane, tworzyć raporty i pulpity nawigacyjne oraz odświeżać zestawy danych.  Istniejący użytkownicy, którym udostępniono zawartość, nadal będą mogli wyświetlać zawartość w swoich zarchiwizowanych obszarach roboczych.

Istnieją jednak pewne ograniczenia dotyczące zawartości w zarchiwizowanym obszarze roboczym:

* **OneDrive dla Firm.  ** Nie będzie można pobrać danych ani ich odświeżyć z poziomu usługi OneDrive dla Firm dla zestawów danych w zarchiwizowanym obszarze roboczym.  Jeśli spróbujesz nawiązać połączenie z tym źródłem, zostanie wyświetlone ostrzeżenie.
* **Udostępnianie pulpitów nawigacyjnych.  ** Nie możesz udostępniać pulpitów nawigacyjnych innym użytkownikom ze zarchiwizowanego obszaru roboczego.  Dowolni użytkownicy, którzy mają już dostęp, nadal będą mogli wyświetlać udostępnione pulpity nawigacyjne, uzyskując dostęp do swojego zarchiwizowanego obszaru roboczego.
* **Tworzenie grup.  ** Grup nie można tworzyć w zarchiwizowanym obszarze roboczym.
* **Dostęp do aplikacji mobilnych usługi Power BI.  **Chociaż nadal możesz wyświetlać zawartość w Internecie w swoim zarchiwizowanym obszarze roboczym, ta zawartość nie będzie już widoczna w aplikacjach mobilnych usługi Power BI.

## <a name="migrating-content-in-your-archived-workspace"></a>Migrowanie zawartości w zarchiwizowanym obszarze roboczym
Aby nadal korzystać z usługi Power BI, musisz utworzyć nową zawartość w swoim obszarze Mój obszar roboczy zarządzanym przez dział IT.   Musisz też zaplanować migrację wszelkiej zawartości w zarchiwizowanym obszarze roboczym do obszaru Mój obszar roboczy.  Sposób migrowania zawartości zależy od rodzaju zawartości:

* **Zestawy danych programu Excel lub Power BI Desktop.  ** Te zestawy danych należy migrować, przełączając się ze zarchiwizowanego obszaru roboczego do obszaru Mój obszar roboczy i ponownie przekazując plik programu Excel lub Power BI Desktop, klikając przycisk „Moje dane”.  W przypadku skonfigurowania zaplanowanego odświeżania, musisz ponownie skonfigurować te ustawienia dla nowego zestawu danych w obszarze Mój obszar roboczy.
* **Inne zestawy danych.  ** Przełącz się do obszaru Mój obszar roboczy, a następnie kliknij przycisk Pobierz dane, aby ponownie połączyć się z wszelkimi innymi zestawami danych utworzonymi w Twoim zarchiwizowanym obszarze roboczym.  Może być konieczne ponowne wprowadzenie zabezpieczeń lub informacji o połączeniu.
* **Raporty.  ** Raporty, które były zawarte w plikach programu Excel lub Power BI Desktop, lub raporty zainstalowane jako część pakietów zawartości zostaną automatycznie odtworzone po ponownym przekazaniu odpowiedniego pliku programu Excel lub Power BI Desktop, lub ponownym połączeniu się z pakietem zawartości.  Jeśli za pomocą usługi Power BI utworzono własne raporty, musisz ponownie odtworzyć te raporty w obszarze Mój obszar roboczy.
* **Pulpity nawigacyjne.  ** Pulpity nawigacyjne zainstalowane jako część pakietów zawartości zostaną automatycznie odtworzone po ponownym połączeniu z pakietem zawartości w obszarze Mój obszar roboczy.  Jeśli za pomocą usługi Power BI zostały utworzone własne pulpity nawigacyjne, musisz odtworzyć te pulpity nawigacyjne w obszarze Mój obszar roboczy.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

