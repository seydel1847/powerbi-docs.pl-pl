---
title: Rozwiązywanie problemów ze scenariuszami odświeżania
description: Rozwiązywanie problemów ze scenariuszami odświeżania
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: d94e25b78edef2aefaa5e63c788e5f11dc948791
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="troubleshooting-refresh-scenarios"></a>Rozwiązywanie problemów ze scenariuszami odświeżania
W tym miejscu możesz znaleźć informacje dotyczące różnych scenariuszy związanych z odświeżaniem danych w usłudze Power BI.

> [!NOTE]
> Jeśli napotkasz sytuację, której nie wymieniono poniżej, możesz uzyskać dodatkową pomoc w [witrynie społeczności](http://community.powerbi.com/) albo utworzyć [bilet pomocy technicznej](https://powerbi.microsoft.com/support/).
> 
> 

## <a name="refresh-using-web-connector-doesnt-work-properly"></a>Odświeżanie przy użyciu łącznika internetowego nie działa prawidłowo
Jeśli masz skrypt łącznika internetowego korzystający z funkcji [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx) oraz zestaw danych lub raport zaktualizowany po 18 listopada 2016 r., musisz użyć bramy, aby odświeżanie działało prawidłowo.

## <a name="unsupported-data-source-for-refresh"></a>Źródło danych, którego odświeżanie nie jest obsługiwane
Podczas konfigurowania zestawu danych możesz zobaczyć błąd wskazujący na to, że zestaw danych korzysta ze źródła danych, którego odświeżanie nie jest obsługiwane. Aby uzyskać więcej informacji, zobacz [Rozwiązywanie problemów ze źródłem danych, którego odświeżanie nie jest obsługiwane](service-admin-troubleshoot-unsupported-data-source-for-refresh.md)

## <a name="dashboard-doesnt-reflect-changes-after-refresh"></a>Pulpit nawigacyjny nie odzwierciedla zmian po odświeżeniu
Poczekaj około 10–15 minut na odzwierciedlenie odświeżenia w kafelkach pulpitu nawigacyjnego.  Jeśli nadal nie widać efektów, ponownie przypnij wizualizację do pulpitu nawigacyjnego.

## <a name="gatewaynotreachable-when-setting-credentials"></a>Błąd GatewayNotReachable podczas ustawiania poświadczeń
Możesz napotkać błąd GatewayNotReachable podczas próby ustawienia poświadczeń dla źródła danych. Może to być spowodowane przestarzałą bramą.  Zainstaluj najnowszą bramę i spróbuj ponownie.

## <a name="processing-error-the-following-system-error-occurred-type-mismatch"></a>Błąd przetwarzania: Wystąpił następujący błąd systemu: niezgodność typów
Ten problem może dotyczyć skryptu M w pliku programu Power BI Desktop lub skoroszycie programu Excel.  Może być również spowodowany przestarzałą wersją programu Power BI Desktop.

## <a name="tile-refresh-errors"></a>Błędy dotyczące odświeżania kafelka
Aby uzyskać informacje o liście błędów, które można napotkać w związku z kafelkami pulpitu nawigacyjnego, wraz z ich wyjaśnieniami, zobacz [Rozwiązywanie problemów z błędami kafelków](refresh-troubleshooting-tile-errors.md).

## <a name="refresh-fails-when-updating-data-from-sources-that-use-aad-oauth"></a>Odświeżanie kończy się niepowodzeniem w przypadku aktualizowania danych ze źródeł korzystających z autoryzacji AAD OAuth
Token OAuth usługi Azure Active Directory (**AAD**), używany przez wiele różnych źródeł danych, wygasa po upływie około godziny. Możesz napotkać sytuacje, w których ładowanie danych zajmuje więcej czasu niż trwa wygaśnięcie tokenu (więcej niż jedna godzina), ponieważ usługa Power BI czeka do dwóch godzin podczas ładowania danych. W takiej sytuacji proces ładowania danych może zakończyć się niepowodzeniem z błędem dotyczącym poświadczeń.

Źródła danych używające tokenu AAD OAuth obejmują usługę **Microsoft Dynamics CRM Online**, **SharePoint Online** (SPO) i inne. Jeśli łączysz się ze źródłami danych tego typu i otrzymujesz błąd dotyczący poświadczeń, gdy ładowanie zajmuje więcej niż godzinę, przyczyna może być właśnie taka.

Firma Microsoft szuka rozwiązania, które umożliwi procesowi ładowania danych odświeżanie tokenu i kontynuowanie pracy. Jeśli jednak wystąpienie usługi Dynamics CRM Online lub SharePoint Online (lub innego źródła danych AAD OAuth) jest takie duże, że może osiągnąć 2-godzinny próg ładowania danych, może również dojść do przekroczenia limitu czasu ładowania danych w usłudze Power BI.

Ponadto należy pamiętać, że prawidłowe odświeżanie w przypadku nawiązywania połączenia ze źródłem danych **SharePoint Online** przy użyciu tokenu AAD OAuth wymaga użycia tego samego konta podczas logowania w usłudze **Power BI**.

## <a name="uncompressed-data-limits-for-refresh"></a>Limity nieskompresowanych danych w przypadku odświeżania
Maksymalny rozmiar zestawów danych zaimportowanych do **usługi Power BI** to 1 GB. Te zestawy danych są mocno skompresowane, aby zapewniać wysoką wydajność. Ponadto w przypadku pojemności udostępnionej usługa stosuje limit dla ilości nieskompresowanych danych przetwarzanych podczas odświeżenia, który wynosi 10 GB. Ten limit bierze kompresję pod uwagę, dlatego wynosi znacznie więcej niż 1 GB. Zestawy danych w usłudze Power BI Premium nie podlegają temu limitowi. Jeśli odświeżenie w usłudze Power BI nie powiedzie się z tego powodu, zredukuj ilość danych importowanych do usługi Power BI i spróbuj ponownie.

## <a name="scheduled-refresh-timeout"></a>Limit czasu zaplanowanego odświeżania
Zaplanowane odświeżanie w przypadku zaimportowanych zestawów danych przekracza limit czasu po dwóch godzinach. W przypadku zestawów danych w obszarach roboczych w warstwie **Premium** limit czasu jest zwiększony do pięciu godzin. Jeśli zostanie osiągnięty ten limit, możesz zredukować rozmiar lub złożoność zestawu danych albo podzielić zestaw danych na mniejsze części.

## <a name="next-steps"></a>Następne kroki
[Odświeżanie danych](refresh-data.md)  
[Rozwiązywanie problemów z lokalną bramą danych](service-gateway-onprem-tshoot.md)  
[Rozwiązywanie problemów z bramą Power BI Gateway — Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

