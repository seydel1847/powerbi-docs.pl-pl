---
title: Zarchiwizowany obszar roboczy usługi Power BI
description: Zarchiwizowany obszar roboczy usługi Power BI po zarządzaniu dzierżawą usługi Office 365
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: d2eeab8241de06f9a4d0e654696173d076e01ad2
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54292366"
---
# <a name="power-bi-archived-workspace"></a>Zarchiwizowany obszar roboczy usługi Power BI

Za pomocą usługi Power BI każdy może zarejestrować się i rozpocząć korzystanie z usługi w ciągu kilku minut.  Później dział IT Twojej organizacji może postanowić przejąć zarządzanie usługą Power BI dla użytkowników w organizacji.  Jeśli nastąpi takie przejęcie, będziesz korzystać z zalet centralnego zarządzania użytkownikami i uprawnieniami w organizacji. Będzie również możliwe korzystanie z zalet udoskonalonego logowania przy użyciu tej samej nazwy użytkownika i hasła, które są stosowane w przypadku innych usług w Twojej organizacji.

Cała zawartość utworzona, zanim dział IT zaczął zarządzać usługą Power BI, jest umieszczana w zarchiwizowanym obszarze roboczym usługi Power BI, który jest dostępny z lewego paska nawigacji usługi [Power BI](https://app.powerbi.com). Należy rozpocząć tworzenie nowej zawartości usługi Power BI w obszarze Mój obszar roboczy, który jest zabezpieczony i zarządzany przez dział IT Twojej organizacji.  Zarchiwizowany obszar roboczy będzie nadal istniał, ale istnieją ograniczenia dotyczące działań, które można wykonać na zawartości w Twoim zarchiwizowanym obszarze roboczym.  Aby usunąć te ograniczenia, musisz migrować zawartość ze zarchiwizowanego obszaru roboczego do obszaru Mój obszar roboczy zarządzanego przez dział IT.

## <a name="restrictions-in-your-archived-workspace"></a>Ograniczenia w zarchiwizowanym obszarze roboczym

Usługa Power BI nie będzie usuwać zawartości ze zarchiwizowanego obszaru roboczego. Możesz nadal pobierać dane, tworzyć raporty i pulpity nawigacyjne oraz odświeżać zestawy danych. Istniejący użytkownicy, którym udostępniono zawartość, nadal mogą wyświetlać zawartość w swoich zarchiwizowanych obszarach roboczych. Istnieją jednak pewne ograniczenia dotyczące zawartości w zarchiwizowanym obszarze roboczym:

* **OneDrive dla Firm**: dla zestawów danych w zarchiwizowanym obszarze roboczym nie można pobierać ani odświeżać danych z poziomu usługi OneDrive dla Firm.  Jeśli spróbujesz nawiązać połączenie z tym źródłem, zostanie wyświetlone ostrzeżenie.

* **Udostępnianie pulpitów nawigacyjnych**: nie możesz udostępniać pulpitów nawigacyjnych innym użytkownikom ze zarchiwizowanego obszaru roboczego.  Wszyscy użytkownicy, którzy mają już dostęp, nadal mogą wyświetlać udostępnione pulpity nawigacyjne, uzyskując dostęp do swojego zarchiwizowanego obszaru roboczego.

* **Tworzenie grup**: nie możesz tworzyć grup w zarchiwizowanym obszarze roboczym.

* **Dostęp do aplikacji mobilnych usługi Power BI**: chociaż nadal możesz wyświetlać zawartość w Internecie w swoim zarchiwizowanym obszarze roboczym, ta zawartość nie jest już widoczna w aplikacjach mobilnych usługi Power BI.

## <a name="migrating-content-in-your-archived-workspace"></a>Migrowanie zawartości w zarchiwizowanym obszarze roboczym

Aby nadal korzystać z usługi Power BI, musisz utworzyć nową zawartość w obszarze Mój obszar roboczy. Musisz też zaplanować migrację całej zawartości zarchiwizowanego obszaru roboczego do obszaru Mój obszar roboczy.  Sposób migrowania zawartości zależy od rodzaju zawartości:

* **Zestawy danych programu Excel lub Power BI Desktop**: te zestawy danych należy migrować, przełączając się ze zarchiwizowanego obszaru roboczego do obszaru Mój obszar roboczy i ponownie przekazując plik programu Excel lub Power BI Desktop, wybierając przycisk **Moje dane**.  W przypadku skonfigurowania zaplanowanego odświeżania musisz ponownie skonfigurować te ustawienia dla nowego zestawu danych w obszarze Mój obszar roboczy.

* **Inne zestawy danych**: Przełącz się do obszaru Mój obszar roboczy, a następnie kliknij przycisk **Pobierz dane**, aby ponownie połączyć się z wszelkimi innymi zestawami danych utworzonymi w Twoim zarchiwizowanym obszarze roboczym.  Może być konieczne ponowne wprowadzenie zabezpieczeń lub informacji o połączeniu.

* **Raporty**: raporty zawarte w plikach programu Excel lub Power BI Desktop są automatycznie tworzone ponownie po ponownym przekazaniu odpowiedniego pliku programu Excel lub Power BI Desktop. Raporty zainstalowane jako część pakietu zawartości są również tworzone ponownie po ponownym nawiązaniu połączenia z pakietem zawartości. Jeśli masz własne raporty utworzone za pomocą usługi Power BI, utwórz je ponownie w obszarze Mój obszar roboczy.

* **Pulpity nawigacyjne**: pulpity nawigacyjne zainstalowane jako część pakietów zawartości są automatycznie tworzone ponownie po ponownym połączeniu z pakietem zawartości w obszarze Mój obszar roboczy. Jeśli masz własne pulpity nawigacyjne utworzone za pomocą usługi Power BI, utwórz je ponownie w obszarze Mój obszar roboczy.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

