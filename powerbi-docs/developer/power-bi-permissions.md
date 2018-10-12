---
title: Uprawnienia usługi Power BI
description: Uprawnienia usługi Power BI
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 10/01/2018
ms.openlocfilehash: 2ca9711ecfdc205fafe7210f99f2de26a8f6d6d6
ms.sourcegitcommit: f391b645062f64ac3adc2ce7877318583b14b941
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2018
ms.locfileid: "48016128"
---
# <a name="power-bi-permissions"></a>Uprawnienia usługi Power BI

## <a name="permission-scopes"></a>Zakresy uprawnień

Uprawnienia usługi Power BI zapewniają aplikacji możliwość wykonywania pewnych akcji w imieniu użytkownika. Aby uprawnienia były ważne, muszą zostać zatwierdzone przez użytkownika.

| Nazwa wyświetlana | Opis | Wartość zakresu |
| --- | --- | --- |
| Wyświetlanie wszystkich zestawów danych |Aplikacja może wyświetlać wszystkie zestawy danych dla zalogowanego użytkownika oraz zestawy danych, do których użytkownik ma dostęp. |Dataset.Read.All |
| Odczytywanie i zapisywanie wszystkich zestawów danych |Aplikacja może wyświetlać i zapisywać wszystkie zestawy danych dla zalogowanego użytkownika oraz zestawy danych, do których użytkownik ma dostęp. |Dataset.ReadWrite.All |
| Dodawanie danych do zestawu danych użytkownika |Daje aplikacji dostęp do dodawania i usuwania wierszy zestawu danych użytkownika. To uprawnienie nie zapewnia aplikacji dostępu do danych użytkownika. |Data.Alter_Any |
| Tworzenie zawartości |Aplikacja może automatycznie tworzyć zawartość i zestawy danych dla użytkownika. |Content.Create |
| Wyświetlanie grup użytkowników |Aplikacja może wyświetlać wszystkie grupy, do których należy zalogowany użytkownik. |Group.Read |
| Wyświetlanie wszystkich grup |Aplikacja może wyświetlać wszystkie grupy, do których należy zalogowany użytkownik. |Group.Read.All |
| Odczytywanie i zapisywanie wszystkich grup |Aplikacja może wyświetlać i zapisywać wszystkie grupy dla zalogowanego użytkownika oraz dowolne grupy, do których użytkownik ma dostęp. |Group.ReadWrite.All |
| Wyświetlanie wszystkich pulpitów nawigacyjnych |Aplikacja może wyświetlać wszystkie pulpity nawigacyjne dla zalogowanego użytkownika oraz pulpity nawigacyjne, do których użytkownik ma dostęp. |Dashboard.Read.All |
| Wyświetlanie wszystkich raportów |Aplikacja może wyświetlać wszystkie raporty dla zalogowanego użytkownika oraz raporty, do których użytkownik ma dostęp. Aplikacja może także wyświetlać dane zawarte w raportach oraz ich strukturę. |Report.Read.All |
| Odczytywanie i zapisywanie wszystkich raportów |Aplikacja może wyświetlać i zapisywać wszystkie raporty dla zalogowanego użytkownika oraz raporty, do których użytkownik ma dostęp. Nie daje to uprawnień do utworzenia nowego raportu. |Report.ReadWrite.All |
| Odczytywanie i zapisywanie wszystkich pojemności |Aplikacja może wyświetlać i zapisywać wszystkie pojemności dla zalogowanego użytkownika oraz wszelkie pojemności, do których użytkownik ma dostęp. Nie daje to uprawnień do tworzenia nowej pojemności. |Capacities.ReadWrite.All |
| Odczytywanie wszystkich pojemności |Aplikacja może wyświetlać i zapisywać wszystkie pojemności dla zalogowanego użytkownika oraz wszelkie pojemności, do których użytkownik ma dostęp. Nie daje to uprawnień do tworzenia nowej pojemności. |Capacities.Read.All |
| Odczytywanie i zapisywanie całej zawartości w dzierżawie |Aplikacja może wyświetlać i zapisywać w usłudze Power BI wszystkie artefakty, takie jak grupy, raporty, pulpity nawigacyjne i zestawy danych. Zakładając, że zalogowany użytkownik jest administratorem usługi Power BI. |Tenant.ReadWrite.All |
| Wyświetlanie całej zawartości w dzierżawie |Aplikacja może wyświetlać w usłudze Power BI wszystkie artefakty, takie jak grupy, raporty, pulpity nawigacyjne i zestawy danych. Zakładając, że zalogowany użytkownik jest administratorem usługi Power BI. |Tenant.Read.All |

Aplikacja może zażądać uprawnień, gdy próbuje zalogować się do strony użytkownika przez przekazanie żądanych uprawnień w parametrze zakresu wywołania. Jeśli uprawnienia zostaną przydzielone, token dostępu zostanie zwrócony do aplikacji, z której będzie można korzystać w przyszłych wywołaniach interfejsu API. Z dostępu może korzystać tylko określona aplikacja.

> [!NOTE]
> Interfejsy API usługi Power BI nadal odwołują się do obszarów roboczych aplikacji jako grup. Wszystkie odwołania do grup oznaczają, że pracujesz z obszarami roboczymi aplikacji.

## <a name="requesting-permissions"></a>Żądanie uprawnień

Można wywołać interfejs API do uwierzytelniania za pomocą nazwy użytkownika i hasła, jednak aby podejmować czynności w imieniu innych użytkowników, będzie to wymagało żądania uprawnień, które użytkownik następnie potwierdza i wysyła wynikowy token dostępu do wszystkich przyszłych wywołań. Na potrzeby tego procesu będziemy postępować zgodnie ze standardowym protokołem [OAuth 2.0](http://oauth.net/2/). Rzeczywiste wdrożenie może się różnić, jednak przepływ OAuth dla usługi Power BI zawiera następujące elementy:

* **Interfejs użytkownika logowania** — jest to interfejs użytkownika, który może być wywoływany przez dewelopera w celu żądania uprawnień. Będzie to wymagać zalogowania, jeśli użytkownik jeszcze nie jest zalogowany. Użytkownik musi również zatwierdzić uprawnienia, których żąda aplikacja. Okno logowania odeśle z powrotem kod dostępu lub komunikat o błędzie do dostarczonego adresu URL przekierowania.
  * Standardowy adres URL przekierowania powinien być dostarczony przez usługę Power BI do użytku przez natywne aplikacje.
* **Kod autoryzacji** — kody autoryzacji są zwracane do aplikacji internetowej po zalogowaniu za pomocą parametrów adresu URL w adresie URL przekierowania. Ponieważ znajdują się one w parametrach, istnieje pewne zagrożenie bezpieczeństwa. Aplikacje internetowe muszą wymienić kod autoryzacji na token autoryzacji
* **Tokeny autoryzacji** — używa się ich do uwierzytelniania wywołań interfejsu API w imieniu innego użytkownika. Zostaną przystosowane do zakresu określonej aplikacji. Tokeny mają ustawiony cykl życia i gdy wygasają, należy je odświeżyć.
* **Token odświeżania** — po wygaśnięciu tokenów następuje proces ich odświeżania.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)