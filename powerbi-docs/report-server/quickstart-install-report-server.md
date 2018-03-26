---
title: 'Szybki start: instalowanie serwera raportów usługi Power BI'
description: Instalacja serwera raportów usługi Power BI jest niezwykle szybka. Uwzględniając pobieranie, instalowanie i konfigurowanie, jego uruchomienie powinno zająć zaledwie kilka minut.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
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
ms.date: 03/19/2018
ms.author: maggies
ms.openlocfilehash: 625864384f73260ec0f62b74ff9a95e966289da0
ms.sourcegitcommit: 93e7362fc47319959b6992dfd037effdf831d010
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/21/2018
---
# <a name="quickstart-install-power-bi-report-server"></a>Szybki start: instalowanie serwera raportów usługi Power BI
Instalacja serwera raportów usługi Power BI jest niezwykle szybka. Uwzględniając pobieranie, instalowanie i konfigurowanie, jego uruchomienie powinno zająć zaledwie kilka minut.

To jest krótkie omówienie sposobu instalacji serwera raportów, jeśli użytkownik chce uruchomić nowy serwer. Aby uzyskać bardziej szczegółowe informacje na temat instalowania serwera raportów, zobacz temat [Instalowanie serwera raportów usługi Power BI](install-report-server.md).

## <a name="video-install-power-bi-report-server"></a>Wideo: Instalacja serwera raportów usługi Power BI

<iframe width="640" height="360" src="https://www.youtube.com/embed/zacaEb9A4F0?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="before-you-begin"></a>Zanim rozpoczniesz
Przed zainstalowaniem serwera raportów usługi Power BI zalecane jest przejrzenie tematu [Wymagania sprzętowe i programowe dotyczące instalowania serwera raportów usługi Power BI](system-requirements.md).

## <a name="step-1-download"></a>Krok 1. Pobieranie

Aby pobrać serwer raportów usługi Power BI i program Power BI Desktop zoptymalizowany pod kątem serwera raportów usługi Power BI, przejdź do artykułu [Lokalne raportowanie za pomocą serwera raportów usługi Power BI](https://powerbi.microsoft.com/report-server/) i wybierz pozycję **Pobierz bezpłatną wersję próbną**.

Postępuj zgodnie z instrukcjami, aby pobrać lokalnie pliki dla serwera raportów usługi Power BI. 

![Pobieranie serwera raportów usługi Power BI](media/quickstart-install-report-server/download-pbireportserver.png)

## <a name="step-2-run-installer"></a>Krok 2. Uruchamianie instalatora
Uruchom pobrany plik PowerBIReportServer.exe i wykonaj czynności opisane na ekranach instalacji. Można będzie wybrać ścieżkę instalacji oraz wersję do zainstalowania. Możesz wybrać wersję próbną, która wygaśnie po upływie 180 dni, wersję dla deweloperów lub wprowadzić klucz produktu.

![Instalowanie serwera raportów usługi Power BI](media/quickstart-install-report-server/pbireportserver-install.png)

## <a name="step-3-configure-the-server"></a>Krok 3. Konfigurowanie serwera
Po zakończeniu instalacji należy uruchomić menedżera konfiguracji, aby zakończyć konfigurowanie serwera. Należy utworzyć bazę danych katalogu ReportServer oraz zweryfikować adresy URL portalu internetowym i usługi internetowej.

![Konfigurowanie serwera raportów usługi Power BI](media/quickstart-install-report-server/pbireportserver-configure.png)

## <a name="step-4-browse-to-web-portal"></a>Krok 4. Przechodzenie do portalu internetowego
Po zakończeniu konfiguracji można otworzyć w przeglądarce portal internetowy. Domyślny adres to `http://localhost/reports`. Można również przeglądać przy użyciu nazwy maszyny zamiast domyślnej nazwy localhost, jeśli nie jest ona blokowana przez zaporę.

![Portal internetowy Serwera raportów usługi Power BI](media/quickstart-install-report-server/web-portal.png)

## <a name="next-steps"></a>Następne kroki
[Podręcznik administratora](admin-handbook-overview.md)  
[Jak znaleźć klucz produktu serwera raportów](find-product-key.md)  
[Instalacja serwera raportów usługi Power BI](install-report-server.md)  
[Instalowanie programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI](install-powerbi-desktop.md)  
[Obsługa przeglądarek dla serwera raportów usługi Power BI](browser-support.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

