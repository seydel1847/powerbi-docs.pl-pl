---
title: Zdalne konfigurowanie dostępu aplikacji mobilnej dla systemu iOS do serwera raportów
description: Dowiedz się, jak zdalnie skonfigurować aplikacje mobilne dla systemu iOS na potrzeby serwera raportów.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 11/15/2018
ms.author: maggies
ms.openlocfilehash: 740c012d83f9ca70f6e909b8cf62714f67c123d4
ms.sourcegitcommit: 6c6aa214dc36c26a01b29e823598d217a3e2b8a1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2018
ms.locfileid: "53451380"
---
# <a name="configure-power-bi-ios-mobile-app-access-to-a-report-server-remotely"></a>Zdalne konfigurowanie dostępu aplikacji mobilnej Power BI dla systemu iOS do serwera raportów

W tym artykule dowiesz się, jak za pomocą narzędzia do zarządzania urządzeniami przenośnymi (MDM, Mobile Device Management) używanego organizacji skonfigurować dostęp aplikacji mobilnej Power BI dla systemu iOS do serwera raportów. Aby przeprowadzić konfigurację, administratorzy IT tworzą zasady konfiguracji aplikacji zawierające wymagane informacje, które mają być wypychane do aplikacji. 

 Ponieważ połączenie z serwerem raportów jest już skonfigurowane, użytkownicy aplikacji mobilnej Power BI dla systemu iOS mogą łatwiej łączyć się z serwerem raportów organizacji. 

## <a name="create-the-app-configuration-policy-in-mdm-tool"></a>Tworzenie zasad konfiguracji aplikacji w narzędziu MDM 

Jako administrator musisz wykonać następujące kroki w usłudze Microsoft Intune, aby utworzyć zasady konfiguracji aplikacji. Kroki i środowisko tworzenia zasad konfiguracji aplikacji mogą być inne w innych narzędziach MDM. 

1. Połącz się ze swoim narzędziem MDM. 
2. Utwórz nowe zasady konfiguracji aplikacji i nadaj im nazwę. 
3. Wybierz użytkowników, do których mają zostać wysłane te zasady konfiguracji aplikacji. 
4. Utwórz pary klucz-wartość. 

Pary zostały wymienione w poniższej tabeli.

|Klucz  |Typ  |Opis  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ServerURL | String (ciąg) | Adres URL serwera raportów </br> Powinien zaczynać się od ciągu http/https |
| com.microsoft.powerbi.mobile.ServerUsername | String (ciąg) | [opcjonalnie] </br> Nazwa użytkownika do używania podczas łączenia z serwerem. </br> Jeśli klucz nie istnieje, aplikacja wyświetla użytkownikowi monit, aby wpisał nazwę użytkownika na potrzeby połączenia.| 
| com.microsoft.powerbi.mobile.ServerDisplayName | String (ciąg) | [opcjonalnie] </br> Wartość domyślna to „Serwer raportów” </br> Przyjazna nazwa używana w aplikacji w celu reprezentowania serwera | 
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boolean (wartość logiczna) | Wartość domyślna to True </br>Ustawienie wartości „True” powoduje zastąpienie dowolnej definicji serwera raportów, która już znajduje się na urządzeniu przenośnym. Istniejące serwery, które zostały już skonfigurowane, są usuwane. </br> Włączenie zastępowania uniemożliwia również użytkownikowi usunięcie tej konfiguracji. </br> Ustawienie wartości „False” powoduje dodanie wypchniętych wartości bez zmian istniejących ustawień. </br> Jeśli w aplikacji mobilnej jest już skonfigurowany ten sam adres URL serwera, aplikacja pozostawia konfigurację bez zmian. Aplikacja nie monituje użytkownika o ponowne uwierzytelnienie dla tego samego serwera. |

Oto przykład ustawienia zasad konfiguracji przy użyciu usługi Intune.

![Ustawienia konfiguracji usługi Intune](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configuration-settings.png)

## <a name="end-users-connecting-to-a-report-server"></a>Łączenie użytkowników końcowych z serwerem raportów

 Załóżmy, że opublikowano zasady konfiguracji aplikacji dla listy dystrybucyjnej. Po uruchomieniu aplikacji mobilnej dla systemu iOS przez użytkowników i na urządzeniach znajdujących się na tej liście dystrybucyjnej zostanie uruchomione następujące środowisko. 

1. Widzą komunikat z informacją o tym, że aplikacja mobilna została skonfigurowana przy użyciu serwera raportów i naciskają przycisk **Zaloguj się**.

    ![Logowanie się do serwera raportów](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-sign-in.png)

2.  Na stronie **Łączenie z serwerem** będą już wypełnione szczegóły serwera raportów. Naciskają przycisk **Połącz**.

    ![Wypełnione szczegóły serwera raportów](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configure-connect-server.png)

3. Wpisują hasło, aby się uwierzytelnić, a następnie naciskają przycisk **Zaloguj się**. 

    ![Wypełnione szczegóły serwera raportów](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-address.png)

Teraz mogą wyświetlać i stosować wskaźniki KPI oraz raporty usługi Power BI przechowywane na serwerze raportów.

## <a name="next-steps"></a>Następne kroki
[Omówienie dla administratorów](admin-handbook-overview.md)  
[Instalacja serwera raportów usługi Power BI](install-report-server.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

