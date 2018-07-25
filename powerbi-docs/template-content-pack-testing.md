---
title: Testowanie szablonowych pakietów zawartości dla usługi Power BI
description: Testowanie szablonowych pakietów zawartości
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maggies
ms.openlocfilehash: 4f461029ab3f698992128fa4f3f53714ee962b1e
ms.sourcegitcommit: 3a287ae4ab16d1e76caed651bd8ae1a1738831cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39157552"
---
# <a name="testing-template-content-packs-for-power-bi"></a>Testowanie szablonowych pakietów zawartości dla usługi Power BI
Istnieje wiele sposobów, aby przetestować pakiet zawartości przed przesłaniem go do opublikowania.  

> [!NOTE]
> Jeśli pakiet zawartości używa niestandardowego, opracowanego przez Ciebie [łącznika danych](https://aka.ms/DataConnectors), nie możesz przetestować odświeżania danych ani szablonowego pakietu zawartości w opisany poniżej sposób. W takim przypadku przejdź do [przesyłania](#submission) pakietu zawartości, a zespół usługi Power BI przetestuje go razem z Tobą.
> 
> 

## <a name="testing-scheduled-data-refresh"></a>Testowanie zaplanowanego odświeżania danych
Szablonowe pakiety zawartości używają funkcji Odśwież w witrynie PowerBI.com, aby utworzyć wystąpienie pakietu zawartości z danymi klienta podczas nawiązywania połączenia. Zanim pakiet zawartości stanie się publicznie dostępny, możesz przetestować ten przepływ przy użyciu utworzonego przez siebie pliku programu Desktop.

Po przekazaniu pliku wybierz pozycję „...” obok zestawu danych oraz pozycję Zaplanuj odświeżanie. Skonfiguruj poświadczenia dla źródła. Upewnij się, że operacja odświeżania zestawu danych przebiega pomyślnie. Wypróbuj zarówno pozycję „Odśwież teraz”, jak i „Zaplanowane odświeżanie”. Jeśli odświeżanie powoduje jakiekolwiek błędy, sprawdź komunikat o błędzie, a następnie sprawdź zapytania i system końcowy.

### <a name="additional-refresh-tips"></a>Dodatkowe porady dotyczące odświeżania
* Podczas próby zaplanowania odświeżania powinno być wykrywane tylko jedno źródło danych.  
* Połączenie testowe powinno wskazywać, że Twój użytkownik będzie mógł załadować pakiet zawartości. W przeciwnym razie upewnij się, że Twoje zapytania obsługują dodatkowe przypadki błędów.  
* Odświeżanie powinno zakończyć się w rozsądnym czasie. Zalecany czas to ok. 5 minut.  

![ustawienia](media/template-content-pack-testing/scheduledrefresh.png)

<a name="templates"></a>

## <a name="testing-templates"></a>Testowanie szablonów
Szablonowy pakiet zawartości przypomina istniejące rozwiązania, ale nie zawiera rzeczywistych danych w zestawie danych. Zamiast tego, gdy użytkownik korzysta z szablonu lub tworzy jego wystąpienie, jest wyświetlany monit o podanie parametrów i poświadczeń w celu nawiązania połączenia. Po nawiązaniu połączenia użytkownik zobaczy własne dane na pulpicie nawigacyjnym, w raporcie i w zestawie danych. 

Użytkownik, który utworzy wystąpienie pakietu zawartości, ma dostęp do ustawień zestawu danych, takich jak zaplanowane odświeżanie. Żadne ustawienia zabezpieczeń na poziomie wiersza w zestawie danych **nie** są publikowane w pakiecie zawartości.  

> [!NOTE]
> Szablonowe pakiety zawartości mogą zawierać tylko 1 pulpit nawigacyjny, 1 raport i 1 zestaw danych. Zobacz listę ograniczeń na stronie [tworzenia](template-content-pack-authoring.md#restrictions). 
> 
> 

Aby umożliwić tworzenie szablonów dla swojej dzierżawy, skontaktuj się z administratorem usługi Power BI w celu włączenia poniższego przełącznika funkcji. 

![przełącznik funkcji](media/template-content-pack-testing/featureswitch.png)

Po jego włączeniu w dolnej części okna [„Tworzenie pakietu zawartości”](https://app.powerbi.com/groups/me/publish-content/) zostanie wyświetlone pole wyboru umożliwiające opublikowanie szablonowego pakietu zawartości w organizacji. 

![pole wyboru](media/template-content-pack-testing/checkbox.png)

### <a name="naming"></a>Nazewnictwo
Zalecamy stosowanie spójnego nazewnictwa pulpitu nawigacyjnego, raportu i zestawu danych w pakiecie zawartości. Te nazwy są zapisane na stałe i są takie same dla wszystkich użytkowników, dlatego stosowanie Twojej nazwy produktu/scenariusza może ułatwić klientom ich zlokalizowanie.

### <a name="additional-template-tips"></a>Dodatkowe porady dotyczące szablonów
* Upewnij się, że parametry określone w zapytaniach są zrozumiałe dla użytkowników końcowych.
* Weź pod uwagę, jak długo użytkownik końcowy będzie czekał na zakończenie zaplanowanego odświeżania.

![tworzenie](media/template-content-pack-testing/createtemplate.png)

<a name="submission"></a>

## <a name="submission"></a>Przesyłanie
Proces przesyłania za pośrednictwem usługi [Microsoft AppSource](https://appsource.microsoft.com/en-us/partners/list-an-app) umożliwia opublikowanie szablonowego pakietu zawartości w galerii pakietów zawartości usługi w witrynie PowerBI.com, jak również umieszczenie go na liście w usłudze [Microsoft AppSource](http://appsource.microsoft.com).

### <a name="before-submission"></a>Przed przesłaniem
* Przejrzyj porady dotyczące tworzenia dla każdego z artefaktów w pakiecie zawartości.
* Przetestuj różne konta i warunki dotyczące danych oraz nawiąż z nimi połączenie. (Pomiń ten krok, jeśli masz opracowany własny, niestandardowy [łącznik danych](https://aka.ms/DataConnectors)).
* Przejrzyj wszystkie wizualizacje. Starannie wyszukaj błędnie napisane elementy.
* Upewnij się, że pakiet zawartości dobrze współpracuje z funkcją Pytania i odpowiedzi. Zalecamy przetestowanie co najmniej 30 różnych pytań w modelu danych. (Pomiń ten krok, jeśli masz opracowany własny, niestandardowy [łącznik danych](https://aka.ms/DataConnectors)).

### <a name="submission"></a>Przesyłanie
Po uzyskaniu gotowości do przesyłania odwiedź [stronę przesyłania aplikacji](https://appsource.microsoft.com/en-us/partners/list-an-app) w usłudze AppSource i prześlij informacje. Z listy dostępnych produktów wybierz usługę Power BI.

Zespół usługi Power BI przejrzy zgłoszenie i skontaktuje się z Tobą, aby zapewnić zgodność wszystkich artefaktów z wymaganiami przesyłania. Oprócz sprawdzenia kompletności zweryfikujemy także jakość dostarczonego pulpitu nawigacyjnego i raportów, aby upewnić się, że spełniają one wymagania scenariusza biznesowego opisanego w aplikacji.

### <a name="updates"></a>Aktualizacje
Aktualizacja pakietu zawartości odbywa się zgodnie z przepływem podobnym do oryginalnej wysyłki. 

