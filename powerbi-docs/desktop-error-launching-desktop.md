---
title: Rozwiązywanie problemów podczas uruchamiania programu Power BI Desktop
description: Rozwiązywanie problemów podczas uruchamiania programu Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: f527fa17ab242f6835ca99a3ff3ef3e2525a001f
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277140"
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Co zrobić, jeśli nie można uruchomić programu Power BI Desktop
Może się zdarzyć, że użytkownicy programu **Power BI Desktop**, którzy zainstalowali starszą wersję **lokalnej bramy danych usługi Power BI**, nie mogą uruchomić programu Power BI Desktop ze względu na ograniczenia zasad administracyjnych zastosowane przez lokalną bramę danych usługi Power BI do potoków nazwanych na maszynie lokalnej. 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Rozwiązywanie problemów z lokalną bramą danych i programem Power BI Desktop
Aby rozwiązać problem związany z lokalną bramą danych i włączyć program Power BI Desktop, można użyć trzech sposobów:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Rozwiązanie 1. Zainstalowanie najnowszej wersji lokalnej bramy danych usługi Power BI
Najnowsza wersja lokalnej bramy danych usługi Power BI nie stosuje ograniczeń do potoków nazwanych na maszynie lokalnej i umożliwia prawidłowe uruchomienie programu Power BI Desktop. Jest to zalecane rozwiązanie, jeśli nadal musisz korzystać z lokalnej bramy danych usługi Power BI. Możesz pobrać najnowszą wersję lokalnej bramy danych usługi Power BI z [tej lokalizacji](https://go.microsoft.com/fwlink/?LinkId=698863). Pamiętaj, że jest to bezpośredni link pobierania do pliku wykonywalnego instalacji.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>Rozwiązanie 2. Odinstalowanie lub zatrzymanie usługi lokalnej bramy danych usługi Power BI w systemie Windows
Jeśli nie potrzebujesz już lokalnej bramy danych usługi Power BI, możesz odinstalować ją lub zatrzymać usługę lokalnej bramy danych usługi Power BI w systemie Windows, co spowoduje usunięcie zasad ograniczeń i umożliwi uruchomienie programu Power BI Desktop.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Rozwiązanie 3. Uruchomienie programu Power BI Desktop z uprawnieniami administratora
Możesz również uruchomić program Power BI Desktop jako administrator, aby umożliwić programowi Power BI Desktop pomyślne uruchomienie. Nadal zaleca się zainstalowanie najnowszej wersji lokalnej bramy danych usługi Power BI, jak opisano wcześniej w tym artykule.

Zauważ, że program Power BI Desktop został zaprojektowany jako architektura obsługująca wiele procesów i niektóre z tych procesów komunikują się przy użyciu nazwanych potoków systemu Windows. Mogą istnieć inne procesy, które zakłócają działanie tych nazwanych potoków. Najczęstszym powodem takich zakłóceń są zabezpieczenia, w tym sytuacje, gdy oprogramowanie antywirusowe lub zapory mogą blokować potoki lub przekierowywać ruch do określonego portu. Uruchamianie programu Power BI Desktop z uprawnieniami administratora może rozwiązać ten problem. Jeśli uruchamianie z uprawnieniami administratora jest niemożliwe, skontaktuj się z administratorem, aby ustalić, które stosowane reguły zabezpieczeń uniemożliwiają potokom nazwanym prawidłową komunikację, i umieścić program Power BI Desktop oraz jego odpowiednie procesy podrzędne na liście dozwolonych.

## <a name="resolve-issues-when-connecting-to-sql-server"></a>Rozwiązywanie problemów podczas nawiązywania połączenia z programem SQL Server
Jeśli podczas nawiązywania połączenia z bazą danych programu SQL Server wystąpi komunikat o błędzie podobny do poniższego, często można rozwiązać problem, uruchamiając program **Power BI Desktop** jako administrator, a następnie sprawdzając połączenia programu SQL Server:

    "An error happened while reading data from the provider: 'Could not load file or assembly 'System.EnterpriseServices, Version=4.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxx' or one of its dependencies. Either a required impersonation level was not provided, or the provided impersonation level is invalid. (Exception from HRESULT: 0x80070542)'"

Po uruchomieniu jako administrator i nawiązaniu połączenia wymagane biblioteki DLL będą zarejestrowane prawidłowo. Po wykonaniu tych czynności uruchamianie programu Power BI Desktop jako administrator nie będzie konieczne.

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Pomoc dotycząca innych kwestii podczas uruchamiania programu Power BI Desktop
Dokładamy wszelkich starań, aby zapewnić rozwiązania możliwie jak największej liczby problemów, które występują w związku z programem **Power BI Desktop**. Regularnie badamy problemy, które mogą dotyczyć wielu klientów, i uwzględniamy je w naszych artykułach.

Jeśli problem z uruchomieniem programu **Power BI Desktop** nie jest związany z lokalną bramą danych lub jeśli powyższe rozwiązania nie działają, możesz przesłać zgłoszenie zdarzenia do [pomocy technicznej usługi Power BI](https://support.powerbi.com) (https://support.powerbi.com)) w celu uzyskania pomocy w zidentyfikowaniu i rozwiązaniu problemu.

W przypadku innych problemów, które mogą występować w przyszłości w związku z używaniem programu **Power BI Desktop** (mamy nadzieję, że ich nie będzie wcale lub że będzie ich niewiele), warto włączyć śledzenie i zbierać pliki dziennika, aby umożliwić lepsze identyfikowanie problemów. Aby włączyć śledzenie, wybierz kolejno pozycje **Plik > Opcje i ustawienia > Opcje**, a następnie wybierz opcję **Diagnostyka** i zaznacz pole **Włącz śledzenie** w obszarze *Opcje diagnostyczne*. Zdajemy sobie sprawę, że aby włączenie tej opcji było możliwe, program **Power BI Desktop** musi być uruchomiony, a więc może się to przydać raczej w przypadku ewentualnych problemów związanych z uruchomieniem programu **Power BI Desktop** w przyszłości.

