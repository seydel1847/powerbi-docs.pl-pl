---
title: Środowiska szablonowych pakietów zawartości w usłudze Power BI
description: Środowiska szablonowych pakietów zawartości
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maggies
ms.openlocfilehash: f1010557bdd781fac9542c2636424e7e2bef2c26
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54288272"
---
# <a name="template-content-pack-experiences-in-power-bi"></a>Środowiska szablonowych pakietów zawartości w usłudze Power BI
W tej sekcji opisano typowe środowisko użytkownika nawiązującego połączenie z [pakietem zawartości](service-connect-to-services.md) niezależnego dostawcy oprogramowania.

Wypróbuj samodzielnie środowisko połączenia, nawiązując połączenie z wydanym pakietem zawartości pod adresem https://app.powerbi.com/getdata/services (takim jak [pakiet zawartości GitHub](https://app.powerbi.com/getdata/services/github) opisany poniżej).

## <a name="connect"></a>Połącz
Aby rozpocząć, użytkownik przegląda galerię pakietów zawartości i wybiera pakiet zawartości, z którym chce nawiązać połączenie. Wpis pakietu zawartości zawiera nazwę, ikonę i tekst opisowy z dodatkowymi informacjami dla użytkownika.

![połącz](media/template-content-pack-experience/github_data.png)

![połącz](media/template-content-pack-experience/github_connect.png)

## <a name="parameters"></a>Parametry
Po dokonaniu wyboru użytkownik zostanie poproszony o podanie parametrów (jeśli są wymagane). Okno dialogowe parametrów jest udostępniane deklaratywnie przez autora podczas tworzenia pakietu zawartości.

Obecnie interfejs użytkownika parametrów jest bardzo podstawowy — nie ma sposobu na wyliczenie list rozwijanych, a sprawdzanie poprawności danych wejściowych jest ograniczone do wyrażenia regularnego.

![parametry](media/template-content-pack-experience/github_params.png)

## <a name="credentials"></a>Poświadczenia
Po podaniu parametrów użytkownik będzie monitowany o zalogowanie się.  Jeśli źródło obsługuje wiele typów uwierzytelniania, użytkownik wybierze odpowiednią opcję. Jeśli źródło wymaga uwierzytelniania OAuth, interfejs użytkownika logowania do usługi będzie się pojawiać, gdy użytkownik naciśnie pozycję Zaloguj się.  W przeciwnym razie użytkownik może wprowadzić swoje poświadczenia w podanym oknie dialogowym.

![Poświadczenia](media/template-content-pack-experience/github_login.png)

![połącz](media/template-content-pack-experience/github_creds2.png)

## <a name="instantiation"></a>Tworzenie wystąpienia
Gdy logowanie powiedzie się, artefakty zawarte w pakiecie zawartości — model, raporty i pulpit nawigacyjny — zostaną wyświetlone na pasku nawigacyjnym.  Te artefakty są dodawane do kont poszczególnych użytkowników.  Dane są ładowane asynchronicznie w celu wypełnienia zestawu danych (modelu).  Następnie użytkownik będzie mógł korzystać z pulpitu nawigacyjnego, raportów i modelu.

Domyślnie dla użytkownika jest konfigurowany dzienny harmonogram odświeżania, który ponownie oszacuje zapytania w modelu.  Poświadczenia podane użytkownikowi muszą umożliwiać mu odświeżanie danych, gdy jest on nieobecny.

![Tworzenie wystąpienia](media/template-content-pack-experience/github_dashboard.png)

## <a name="exploration-and-monitoring"></a>Eksploracja i monitorowanie
Gdy pakiet zawartości wypełni konta użytkowników, będą oni mogli eksplorować i monitorować dane/szczegółowe informacje.

Zwykle obejmuje to:

* Wyświetlanie i dostosowywanie pulpitu nawigacyjnego
* Wyświetlanie i dostosowywanie raportu
* Zadawanie pytań dotyczących danych przy użyciu języka naturalnego
* Eksplorowanie danych w modelu danych przy użyciu kanwy eksploracji

Należy rozważyć zapewnienie modelowania języka naturalnego (synonimy) oraz zrozumiałego schematu modelu w celu zapewnienia lepszych środowisk eksploracji.

