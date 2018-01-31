---
title: "Wprowadzenie do serwera raportów usługi Power BI"
description: "Dowiedz się, jak zainstalować serwer raportów usługi Power BI. "
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 61558613b0022f7585b31c3e3d674a64ea009d61
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2018
---
# <a name="get-started-with-power-bi-report-server"></a>Wprowadzenie do serwera raportów usługi Power BI
Tworzenie i wdrażanie raportów dla urządzeń przenośnych i raportów z podziałem na strony usługi Power BI oraz zarządzanie nimi lokalnie przy użyciu wielu gotowych do użycia narzędzi i usług zapewnianych przez Serwer raportów usługi Power BI.

## <a name="create-deploy-and-manage-reports"></a>Tworzenie i wdrażanie raportów oraz zarządzanie nimi
Serwer raportów usługi Power BI to rozwiązanie wdrażane przez klientów w środowiskach lokalnych, które umożliwia tworzenie i publikowanie raportów oraz zarządzanie nimi, a następnie dostarczanie ich różnymi sposobami do różnych użytkowników: wyświetlanie w przeglądarce internetowej, na ich urządzeniach przenośnych lub jako wiadomości e-mail w ich skrzynkach odbiorczych.

Serwer raportów usługi Power BI oferuje pakiet produktów:

* Nowoczesny portal internetowy, który można wyświetlić w dowolnej nowoczesnej przeglądarce. W portalu internetowym można organizować i wyświetlać raporty oraz kluczowe wskaźniki wydajności. W portalu można również przechowywać skoroszyty programu Excel.
* Raporty usługi Power BI utworzone za pomocą programu Power BI Desktop można wyświetlić w portalu internetowym we własnym środowisku.
* Raporty z podziałem na strony umożliwiające tworzenie raportów o nowoczesnym wyglądzie przy użyciu przeznaczonych do tego narzędzi.
* Raporty dla urządzeń przenośnych z układem dynamicznym, który dostosowuje się do różnych urządzeń i sposobów ich trzymania.

Dowiedz się więcej na ten temat.

### <a name="whats-new-in-power-bi-report-server"></a>Co nowego w serwerze raportów usługi Power BI
Poniższe źródła zawierają aktualne informacje o nowych funkcjach Serwera raportów usługi Power BI.

* [Co nowego w serwerze raportów usługi Power BI](whats-new.md)
* [Blog usługi Microsoft Power BI](https://powerbi.microsoft.com/blog/)
* [Blog zespołu usług SQL Server Reporting Services](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [Kanał Guy in a Cube (YouTube)](https://aka.ms/guyinacube)

## <a name="web-portal"></a>Portal internetowy
![](media/get-started/web-portal.png)

Dla użytkowników końcowych Serwera raportów usługi Power BI drzwiami frontowymi jest nowoczesny portal internetowy, który można wyświetlić w dowolnej nowoczesnej przeglądarce. W nowym portalu są dostępne wszystkie raporty i kluczowe wskaźniki wydajności.

Portal internetowy może zawierać Twoje własne, niestandardowe [znakowanie](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal). W portalu internetowym można również tworzyć kluczowe wskaźniki wydajności. Kluczowe wskaźniki wydajności umożliwiają szybkie uzyskiwanie informacji o kluczowych metrykach biznesowych w przeglądarce, bez konieczności otwierania raportu.

Zawartość portalu internetowego jest zorganizowana według typu: raporty usługi Power BI, raporty dla urządzeń przenośnych, raporty z podziałem na strony i kluczowe wskaźniki wydajności oraz skoroszyty programu Excel, udostępnione zestawy danych i udostępnione źródła danych służące jako bloki konstrukcyjne raportów. W tym miejscu można bezpiecznie je przechowywać i zarządzać nimi, w tradycyjnej hierarchii folderów. Można oznaczać ulubione i zarządzać zawartością, jeśli użytkownik ma odpowiednią rolę.

W nowym portalu internetowym można planować przetwarzanie raportów, uzyskiwać dostęp do raportów na żądanie i subskrybować opublikowane raporty.

Więcej informacji o [portalu internetowym](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).

## <a name="power-bi-reports"></a>Raporty usługi Power BI
![](media/get-started/powerbi-reports.png)

Raport usługi Power BI to widok zestawu danych z wielu perspektyw z wizualizacjami przedstawiającymi różne wyniki, wnioski i szczegółowe informacje wynikające z tego zestawu danych.  Raport może zawierać jedną wizualizację lub kilka stron wypełnionych wizualizacjami. W zależności od Twojego stanowiska możesz być osobą, która tworzy raporty, lub osobą, która korzysta z raportów.

Raporty są oparte na jednym zestawie danych. Każda wizualizacja w raporcie reprezentuje część informacji. Wizualizacje nie są statyczne — możesz dodawać i usuwać dane, zmieniać typy wizualizacji oraz stosować filtry i fragmentatory, analizując dane w celu wyciągania wniosków i szukania odpowiedzi. Podobnie jak pulpit nawigacyjny — ale jeszcze bardziej — raport jest wysoce interakcyjny i można go dostosowywać, a wizualizacje są aktualizowane, gdy ich bazowe dane zmieniają się.

## <a name="paginated-reports"></a>Raporty z podziałem na strony
![](media/get-started/paginated-reports.png)

Raporty z podziałem na strony są raportami w postaci dokumentów wielostronicowych, w których wraz z ilością danych zwiększa się liczba wierszy w tabelach oraz liczba stron raportu. To doskonałe rozwiązanie do tworzenia dokumentów o stałym układzie z idealnie rozmieszczoną treścią, zoptymalizowanych pod kątem wydruku, takich jak pliki PDF i pliki programu Word.

Raporty o nowoczesnym wyglądzie można tworzyć przy użyciu programów [Report Builder](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016) i Report Designer w narzędziach [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt).

## <a name="report-server-programming-features"></a>Funkcje programowania serwera raportów
Korzystaj z zalet funkcji programowania Serwera raportów usługi Power BI, aby móc rozszerzać i dostosowywać funkcje raportowania dzięki interfejsom API do integracji i rozszerzania możliwości przetwarzania danych i raportów w aplikacjach niestandardowych.

Więcej [dokumentacji dla deweloperów serwera raportów](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation).

## <a name="next-steps"></a>Następne kroki
[Podręcznik użytkownika](user-handbook-overview.md)  
[Podręcznik administratora](admin-handbook-overview.md)  
[Szybki start: instalowanie serwera raportów usługi Power BI](quickstart-install-report-server.md)  
[Instalowanie programu Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

