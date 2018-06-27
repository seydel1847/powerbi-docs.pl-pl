---
title: Uprawnienia usługi Power BI
description: Uprawnienia usługi Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 09/05/2017
ms.author: maghan
ms.openlocfilehash: 4ba0e62dd8c9ba537f56c97489541591ec0bf2bc
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34289423"
---
# <a name="power-bi-permissions"></a>Uprawnienia usługi Power BI
## <a name="permission-scopes"></a>Zakresy uprawnień
Uprawnienia usługi Power BI zapewniają aplikacji możliwość wykonywania pewnych akcji w imieniu użytkownika. Aby uprawnienia były ważne, muszą zostać zatwierdzone przez użytkownika.

| Nazwa wyświetlana | Opis | Wartość zakresu |
| --- | --- | --- |
| Wyświetlanie wszystkich zestawów danych |Aplikacja może wyświetlać wszystkie zestawy danych dla zalogowanego użytkownika oraz zestawy danych, do których użytkownik ma dostęp. |Dataset.Read.All |
| Odczytywanie i zapisywanie wszystkich zestawów danych |Aplikacja może wyświetlać i zapisywać wszystkie zestawy danych dla zalogowanego użytkownika oraz zestawy danych, do których użytkownik ma dostęp. |Dataset.ReadWrite.All |
| Dodawanie danych do zestawu danych użytkownika (podgląd) |Daje aplikacji dostęp do dodawania i usuwania wierszy zestawu danych użytkownika. To uprawnienie nie zapewnia aplikacji dostępu do danych użytkownika. |Data.Alter_Any |
| Tworzenie zawartości (podgląd) |Aplikacja może automatycznie tworzyć zawartość i zestawy danych dla użytkownika. |Content.Create |
| Wyświetlanie grup użytkowników |Aplikacja może wyświetlać wszystkie grupy, do których należy zalogowany użytkownik. |Group.Read |
| Wyświetlanie wszystkich grup |Aplikacja może wyświetlać wszystkie grupy, do których należy zalogowany użytkownik. |Group.Read.All |
| Wyświetlanie wszystkich pulpitów nawigacyjnych (podgląd) |Aplikacja może wyświetlać wszystkie pulpity nawigacyjne dla zalogowanego użytkownika oraz pulpity nawigacyjne, do których użytkownik ma dostęp. |Dashboard.Read.All |
| Wyświetlanie wszystkich raportów (podgląd) |Aplikacja może wyświetlać wszystkie raporty dla zalogowanego użytkownika oraz raporty, do których użytkownik ma dostęp. Aplikacja może także wyświetlać dane zawarte w raportach oraz ich strukturę. |Report.Read.All |
| Odczytywanie i zapisywanie wszystkich raportów |Aplikacja może wyświetlać i zapisywać wszystkie raporty dla zalogowanego użytkownika oraz raporty, do których użytkownik ma dostęp. Nie daje to uprawnień do utworzenia nowego raportu. |Report.ReadWrite.All |

Aplikacja może zażądać uprawnień, gdy próbuje zalogować się do strony użytkownika przez przekazanie żądanych uprawnień w parametrze zakresu wywołania. Jeśli uprawnienia zostaną przydzielone, token dostępu zostanie zwrócony do aplikacji, z której będzie można korzystać w przyszłych wywołaniach interfejsu API. Z dostępu może korzystać tylko określona aplikacja.

> [!NOTE]
> Interfejsy API usługi Power BI nadal odwołują się do obszarów roboczych aplikacji jako grup. Wszystkie odwołania do grup oznaczają, że pracujesz z obszarami roboczymi aplikacji.
> 
> 

## <a name="requesting-permissions"></a>Żądanie uprawnień
Można wywołać interfejs API do uwierzytelniania za pomocą nazwy użytkownika i hasła, jednak aby podejmować czynności w imieniu innych użytkowników, będzie to wymagało żądania uprawnień, które użytkownik następnie potwierdza i wysyła wynikowy token dostępu do wszystkich przyszłych wywołań. Na potrzeby tego procesu będziemy postępować zgodnie ze standardowym protokołem [OAuth 2.0](http://oauth.net/2/). Rzeczywiste wdrożenie może się różnić, jednak przepływ OAuth dla usługi Power BI zawiera następujące elementy:

* **Interfejs użytkownika logowania** — jest to interfejs użytkownika, który może być wywoływany przez dewelopera w celu żądania uprawnień. Będzie to wymagać zalogowania, jeśli użytkownik jeszcze nie jest zalogowany. Użytkownik musi również zatwierdzić uprawnienia, których żąda aplikacja. Okno logowania odeśle z powrotem kod dostępu lub komunikat o błędzie do dostarczonego adresu URL przekierowania.
  * Standardowy adres URL przekierowania powinien być dostarczony przez usługę Power BI do użytku przez natywne aplikacje.
* **Kod autoryzacji** — kody autoryzacji są zwracane do aplikacji internetowej po zalogowaniu za pomocą parametrów adresu URL w adresie URL przekierowania. Ponieważ znajdują się one w parametrach, istnieje pewne zagrożenie bezpieczeństwa. Aplikacje internetowe muszą wymienić kod autoryzacji na token autoryzacji
* **Tokeny autoryzacji** — używa się ich do uwierzytelniania wywołań interfejsu API w imieniu innego użytkownika. Zostaną przystosowane do zakresu określonej aplikacji. Tokeny mają ustawiony cykl życia i gdy wygasają, należy je odświeżyć.
* **Token odświeżania** — po wygaśnięciu tokenów następuje proces ich odświeżania.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

