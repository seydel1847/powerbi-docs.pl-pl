---
title: "Rozwiązywanie problemów z aplikacją osadzoną"
description: "W tym artykule omówiono niektóre typowe problemy, które można napotkać podczas osadzania zawartości z usługi Power BI."
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
ms.date: 11/27/2017
ms.author: asaxton
ms.openlocfilehash: f6ffc56f524da84e865d17981faddef58534c785
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2017
---
# <a name="troubleshooting-your-embedded-application"></a>Rozwiązywanie problemów z aplikacją osadzoną

W tym artykule omówiono niektóre typowe problemy, które można napotkać podczas osadzania zawartości z usługi Power BI.

## <a name="app-registration"></a>Rejestrowanie aplikacji

**Błąd rejestracji aplikacji**

Komunikaty o błędach otrzymywane w witrynie Azure Portal lub na stronie rejestracji aplikacji Power BI informują o niewystarczających uprawnieniach. Aby zarejestrować aplikację, należy być administratorem w dzierżawie usługi Azure AD lub włączyć opcje rejestrowania aplikacji dla użytkowników bez uprawnień administratora.

**Usługa Power BI nie jest wyświetlana w witrynie Azure Portal podczas rejestrowania nowej aplikacji**

Co najmniej jeden użytkownik musi mieć utworzone konto w usłudze Power BI. Jeśli **usługa Power BI** nie znajduje się na liście interfejsów API, oznacza to, że żaden użytkownik nie jest zarejestrowany w usłudze Power BI.

## <a name="rest-api"></a>Interfejs API REST

**Wywołanie interfejsu API zwraca błąd 401**

W celu głębszego zbadania problemu może być konieczne użycie narzędzia Fiddler. Zarejestrowana aplikacja w ramach usługi Azure AD może nie mieć wymaganego zakresu uprawnień. Należy upewnić się, że wymagany zakres znajduje się w obrębie rejestracji aplikacji dla usługi Azure AD w ramach witryny Azure Portal.

**Wywołanie interfejsu API zwraca błąd 403**

W celu głębszego zbadania problemu może być konieczne użycie narzędzia Fiddler. Powodów wystąpienia błędu 403 może być kilka.

* Ważność tokenu uwierzytelniania usługi Azure AD wygasła.
* Uwierzytelniony użytkownik nie jest członkiem grupy (obszaru roboczego aplikacji).
* Uwierzytelniony użytkownik nie jest administratorem grupy (obszaru roboczego aplikacji).
* Nagłówek autoryzacji jest nieprawidłowo wyświetlony. Należy upewnić się, że nie ma żadnych literówek.

Zaplecze aplikacji może wymagać odświeżenia tokenu uwierzytelniania przed wywołaniem metody GenerateToken.

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

**Generowanie tokenu kończy się niepowodzeniem podczas dostarczania obowiązującej tożsamości**

Przyczyn niepowodzenia metody GenerateToken, po podaniu obowiązującej tożsamości, jest kilka.

* Zestaw danych nie obsługuje obowiązującej tożsamości
* Nie podano nazwy użytkownika
* Nie podano roli
* Nie podano wartości DatasetId
* Użytkownik nie ma odpowiednich uprawnień

Aby sprawdzić, co wywołało ten błąd, należy wykonać następujące czynności.

* Wykonaj polecenie [pobierania zestawu danych](https://msdn.microsoft.com/library/mt784653.aspx). Czy właściwość IsEffectiveIdentityRequired jest prawdziwa?
* Nazwa użytkownika jest wymagana w przypadku każdego elementu EffectiveIdentity.
* Jeśli właściwość IsEffectiveIdentityRolesRequired jest prawdziwa, konieczne jest podanie roli.
* Wartość DatasetId jest wymagana dla każdego elementu EffectiveIdentity.
* W przypadku usług Analysis Services użytkownikiem głównym musi być administrator bramy.

## <a name="data-sources"></a>Źródła danych

**Niezależny dostawca oprogramowania chce mieć inne poświadczenia dla tego samego źródła danych**

Źródło danych może mieć jeden zestaw poświadczeń dla jednego użytkownika głównego. Użycie innych poświadczeń wymaga utworzenia dodatkowych użytkowników głównych. Następnie należy przypisać inne poświadczenia w każdym kontekście użytkownika głównego i wykonać osadzanie przy użyciu tokenu usługi Azure AD tego użytkownika.

## <a name="content-rendering"></a>Renderowanie zawartości

**Renderowanie lub zużycie osadzonej zawartości kończy się niepowodzeniem lub przekracza limit czasu**

Upewnij się, że osadzony token nie wygasł. Sprawdź, czy osadzony token wygasł i odśwież go. Aby uzyskać więcej informacji, zobacz [Odświeżanie tokenu za pomocą zestawu JavaScript SDK](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example).

**Raport lub pulpit nawigacyjny nie ładuje się**

Jeśli użytkownik nie widzi raportu lub pulpitu nawigacyjnego, należy upewnić się, że raport lub pulpit nawigacyjny ładuje się poprawnie w witrynie powerbi.com. Raport lub pulpit nawigacyjny nie będzie działał w aplikacji, jeśli nie zostanie załadowany w witrynie powerbi.com.

**Raport lub pulpit nawigacyjny działa wolno**

Otwórz plik w programie Power BI Desktop lub w witrynie powerbi.com i sprawdź, czy wydajność pozwala wykluczyć problemy z aplikacją lub osadzaniem interfejsów API.

## <a name="tools-for-troubleshooting"></a>Narzędzia do rozwiązywania problemów

### <a name="fiddler-trace"></a>Śledzenie za pomocą narzędzia Fiddler

[Fiddler](http://www.telerik.com/fiddler) to bezpłatne narzędzie firmy Telerik, które monitoruje ruch HTTP.  Dzięki niemu ruch przychodzący i wychodzący można sprawdzać za pomocą interfejsów API usługi Power BI z komputera klienckiego. W ten sposób można ujawnić błędy i inne istotne informacje.

![Śledzenie za pomocą narzędzia Fiddler](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>Narzędzia uruchamiane klawiszem F12 w przeglądarce na potrzeby debugowania na poziomie frontonu

Naciśnięcie klawisza F12 spowoduje uruchomienie okna dewelopera w przeglądarce. Dzięki niemu można zapoznać się z ruchem sieciowym i innymi informacjami.

![Debugowanie przeglądarki po naciśnięciu klawisza F12](media/embedded-troubleshoot/browser-f12.png)

Aby uzyskać odpowiedzi na często zadawane pytania, zobacz [Power BI Embedded — często zadawane pytania](embedded-faq.md).

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)