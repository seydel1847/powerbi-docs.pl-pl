---
title: "Instalowanie programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI"
description: "Dowiedz się, jak zainstalować program Power BI Desktop zoptymalizowany pod kątem serwera raportów usługi Power BI"
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 12/15/2017
ms.author: maggies
ms.openlocfilehash: c1c38d9d98c92963534081049cdcc6a557313639
ms.sourcegitcommit: ea247cb3cfc1cac076d4b076c1ad8e2fc37e15a1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2017
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Instalowanie programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI
Dowiedz się, jak zainstalować program Power BI Desktop zoptymalizowany pod kątem serwera raportów usługi Power BI.

Aby utworzyć raporty usługi Power BI dla serwera raportów usługi Power BI, musisz pobrać i zainstalować program Power BI Desktop zoptymalizowany pod kątem serwera raportów usługi Power BI. Ta wersja jest inna niż wersja programu Power BI Desktop używana z usługą Power BI. Na przykład wersja programu Power BI Desktop dla usługi Power BI zawiera funkcje wersji zapoznawczej, które nie są dostępne na serwerze raportów usługi Power BI przed ich premierą. Użycie tej wersji zapewnia, że serwer raportów może współdziałać ze znaną wersją raportów i modelu. 

> [!NOTE]
> Programy Power BI Desktop i Power BI Desktop zoptymalizowany pod kątem serwera raportów usługi Power BI można zainstalować obok siebie na tym samym komputerze.

## <a name="download-and-install-power-bi-desktop"></a>Pobieranie i instalowanie programu Power BI Desktop

Najprostszym sposobem sprawdzenia, czy masz najnowszą wersję programu Power BI Desktop zoptymalizowaną pod kątem serwera raportów usługi Power BI jest uruchomienie go z portalu internetowego serwera raportów.

1. W portalu internetowym serwera raportów wybierz strzałkę **Pobierz** > **Power BI Desktop**.

    ![Pobieranie programu Power BI Desktop z portalu internetowego](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Możesz też przejść bezpośrednio do programu [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=861076) (zoptymalizowanego pod kątem serwera raportów usługi Power BI — październik 2017) w Centrum pobierania Microsoft.

2. Na stronie Centrum pobierania wybierz pozycję **Pobierz**.

3. W zależności od komputera wybierz: 

    - **PBIDesktopRS.msi** (wersja 32-bitowa) lub

    - **PBIDesktopRS_x64.msi** (wersja 64-bitowa).

1. Po pobraniu instalatora uruchom kreatora instalacji programu Power BI Desktop (październik 2017).
2. Na koniec instalacji zaznacz pozycję **Uruchom program Power BI Desktop teraz**.
   
    Program zostanie uruchomiony automatycznie i będzie można rozpocząć pracę.

## <a name="verify-you-are-using-the-correct-version"></a>Sprawdzanie, czy jest używana właściwa wersja
Możesz sprawdzić, czy używasz właściwej wersji programu Power BI Desktop, spoglądając na ekran powitalny lub pasek tytułu tego programu. Na pasku tytułu są podane miesiąc i rok wydania.

![Pasek tytułu programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI](media/quickstart-create-powerbi-report/report-server-desktop-october-2017-version.png)

Na pasku tytułu wersji programu Power BI Desktop związanej z usługą Power BI nie ma miesiąca ani roku.

## <a name="file-extension-association"></a>Skojarzenie rozszerzenia nazwy pliku
Jeśli na tym samym komputerze zainstalowano zarówno program Power BI Desktop, jak i program Power BI Desktop zoptymalizowany pod kątem serwera raportów usługi Power BI, ostatnia z tych instalacji będzie skojarzona z plikami pbix. Oznacza to, że kliknięcie dwukrotne pliku pbix spowoduje uruchomienie programu Power BI Desktop, który zainstalowano jako ostatni.

Jeśli na komputerze z już istniejącym programem Power BI Desktop zainstalowano program Power BI Desktop zoptymalizowany pod kątem serwera raportów usługi Power BI, wszystkie pliki pbix będą domyślnie otwierane w programie Power BI Desktop zoptymalizowanym pod kątem serwera raportów usługi Power BI. Jeśli więc pliki pbix powinny być domyślnie otwierane w programie Power BI Desktop, ponownie zainstaluj program Power BI Desktop z usługi Power BI.

Zawsze możesz najpierw otworzyć wersję programu Power BI Desktop, której chcesz używać. Następnie możesz za pomocą tego programu Power BI Desktop otworzyć właściwy plik.

Edytowanie raportu usługi Power BI z poziomu serwera raportów usługi Power BI lub utworzenie nowego raportu usługi Power BI z poziomu portalu internetowego zawsze spowoduje otwarcie właściwej wersji programu Power BI Desktop.

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia
Raporty na serwerze raportów usługi Power BI oraz w usłudze Power BI (http://powerbi.com) działają prawie dokładnie tak samo, ale różnią się pod względem kilku funkcji.

### <a name="in-a-browser"></a>W przeglądarce
W raportach na serwerze raportów usługi Power BI obsługiwane są wszystkie wizualizacje, w tym:

* Wizualizacje niestandardowe

W raportach na serwerze raportów usługi Power BI nie są obsługiwane:

* Wizualizacje języka R
* Mapy ArcGIS
* Linki do stron nadrzędnych
* Funkcje programu Power BI Desktop w wersji zapoznawczej

### <a name="in-the-power-bi-mobile-apps"></a>W aplikacjach mobilnych Power BI
W raportach na serwerze raportów usługi Power BI obsługiwane są wszystkie funkcje podstawowe w [aplikacjach mobilnych Power BI](../mobile-apps-for-mobile-devices.md), w tym:

* [Układ raportu na telefonie](../desktop-create-phone-report.md): można zoptymalizować raport dla aplikacji mobilnych Power BI. Na telefonie komórkowym zoptymalizowane raporty mają specjalną ikonę, ![ikonę układu raportu na telefonie](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-icon.png), i układ.
  
    ![Raport zoptymalizowany pod kątem telefonów](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-report.png)

Następujące funkcje w aplikacjach mobilnych Power BI nie są obsługiwane w raportach na serwerze raportów usługi Power BI:

* Wizualizacje języka R
* Mapy ArcGIS
* Wizualizacje niestandardowe
* Linki do stron nadrzędnych
* Filtrowanie geograficzne ani kody kreskowe

## <a name="next-steps"></a>Następne kroki
Program Power BI Desktop został już zainstalowany, więc możesz przystąpić do tworzenia raportów usługi Power BI.

[Szybki start: tworzenie raportu usługi Power BI dla serwera raportów usługi Power BI](quickstart-create-powerbi-report.md)  
[Wprowadzenie do programu Power BI Desktop](../desktop-getting-started.md)  
Uczenie z przewodnikiem: [Wprowadzenie do programu Power BI Desktop](../guided-learning/gettingdata.yml#step-2)  
[Omówienie podręcznika użytkownika — serwer raportów usługi Power BI](user-handbook-overview.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

