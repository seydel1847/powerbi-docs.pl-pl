---
title: "Szybki start: tworzenie raportu usługi Power BI dla serwera raportów usługi Power BI"
description: "Dowiedz się, jak utworzyć raport usługi Power BI dla serwera raportów usługi Power BI w kilku prostych krokach."
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
ms.date: 3/5/2018
ms.author: maggies
ms.openlocfilehash: 0f0e8422edd2f8c1a34d82be065ffde554c96400
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="quickstart-create-a-power-bi-report-for-power-bi-report-server"></a>Szybki start: tworzenie raportu usługi Power BI dla serwera raportów usługi Power BI
Raporty usługi Power BI można przechowywać i zarządzać nimi lokalnie w portalu internetowym serwera raportów usługi Power BI, podobnie jak w przypadku przechowywania ich w chmurze w usłudze Power BI (https://powerbi.com). Raporty usługi Power BI można tworzyć i edytować w programie Power BI Desktop, a następnie publikować je w portalu internetowym. Odbiorcy raportów w organizacji będą mogli wyświetlać je w przeglądarce lub w aplikacji mobilnej Power BI na urządzeniach przenośnych.

![Raport usługi Power BI w portalu internetowym](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

Oto cztery szybkie kroki ułatwiające rozpoczęcie pracy.

## <a name="step-1-install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Krok 1. Instalowanie programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI

Jeśli masz już doświadczenie w tworzeniu raportów usługi Power BI w programie Power BI Desktop, jesteś blisko rozpoczęcia tworzenia raportów usługi Power BI dla serwera raportów usługi Power BI. Zalecamy zainstalowanie wersji programu Power BI Desktop zoptymalizowanej pod kątem serwera raportów usługi Power BI, aby serwer i aplikacja były zawsze zsynchronizowane. Obie wersje programu Power BI Desktop mogą być zainstalowane na tym samym komputerze.

1. W portalu internetowym serwera raportów wybierz strzałkę **Pobierz** > **Power BI Desktop**.

    ![Pobieranie programu Power BI Desktop z portalu internetowego](media/quickstart-create-powerbi-report/report-server-download-web-portal.png)

    Możesz też przejść bezpośrednio do programu [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=861076) (zoptymalizowanego pod kątem serwera raportów usługi Power BI — październik 2017) w Centrum pobierania Microsoft.

2. Na stronie Centrum pobierania wybierz pozycję **Pobierz**.

3. W zależności od komputera wybierz:

    - **PBIDesktopRS.msi** (wersja 32-bitowa) lub

    - **PBIDesktopRS_x64.msi** (wersja 64-bitowa).

4. Po pobraniu instalatora uruchom kreatora instalacji programu Power BI Desktop (październik 2017).

2. Na koniec instalacji zaznacz pozycję **Uruchom program Power BI Desktop teraz**.
   
    Program zostanie uruchomiony automatycznie i będzie można rozpocząć pracę. Na pasku tytułu będzie widnieć napis „Power BI Desktop (październik 2017)” — oznacza to, że jest to właściwa wersja.

    ![Power BI Desktop w wersji z października 2017 r.](media/quickstart-create-powerbi-report/report-server-desktop-october-2017-version.png)

3. Jeśli nie masz doświadczenia w pracy z programem Power BI Desktop, możesz obejrzeć wideo na ekranie powitalnym.
   
    ![Ekran startowy programu Power BI Desktop](media/quickstart-create-powerbi-report/report-server-powerbi-desktop-start.png)

## <a name="step-2-select-a-data-source"></a>Krok 2. Wybieranie źródła danych
Możliwe jest łączenie się z różnymi źródłami danych. Przeczytaj więcej na temat [łączenia się ze źródłami danych](connect-data-sources.md).

1. Na ekranie powitalnym wybierz pozycję **Pobierz dane**.
   
    Ewentualnie na karcie **Narzędzia główne** wybierz pozycję **Pobierz dane**.
2. Wybierz źródło danych — w tym przykładzie będą to usługi **Analysis Services**.
   
    ![Wybieranie źródła danych](media/quickstart-create-powerbi-report/report-server-get-data-ssas.png)
3. Wypełnij pole **Serwer** i opcjonalnie pole **Baza danych**. Upewnij się, że jest wybrana pozycja **Połącz na żywo**, i wybierz przycisk **OK**.
   
    ![Nazwa serwera](media/quickstart-create-powerbi-report/report-server-ssas-server-name.png)
4. Wybierz serwer raportów, na którym będziesz zapisywać raporty.
   
    ![Wybieranie serwera raportów](media/quickstart-create-powerbi-report/report-server-select-server.png)

## <a name="step-3-design-your-report"></a>Krok 3. Projektowanie raportu
To najbardziej interesująca część: tworzenie wizualizacji ilustrujących dane.

Możesz na przykład utworzyć wykres lejkowy dotyczący klientów i zgrupować wartości według dochodów rocznych.

![Projektowanie raportu](media/quickstart-create-powerbi-report/report-server-create-funnel.png)

1. W obszarze **Wizualizacje** wybierz pozycję **Wykres lejkowy**.
2. Przeciągnij pole, które ma być zliczane, do obszaru **Wartości**. Jeśli nie jest to pole liczbowe, program Power BI Desktop automatycznie utworzy dla niego wartość *Liczba elementów*.
3. Przeciągnij pole do zgrupowania do obszaru **Grupa**.

Przeczytaj znacznie więcej na temat [projektowania raportu usługi Power BI](../desktop-report-view.md).

## <a name="step-4-save-your-report-to-the-report-server"></a>Krok 4. Zapisywanie raportu na serwerze raportów
Gdy raport będzie gotowy, zapisz go na serwerze raportów usługi Power BI wybranym w kroku 2.

1. W menu **Plik** wybierz polecenie **Zapisz jako** > **Serwer raportów usługi Power BI**.
   
    ![Zapisywanie na serwerze raportów](media/quickstart-create-powerbi-report/report-server-save-as-powerbi-report-server.png)
2. Teraz można go wyświetlić w portalu internetowym.
   
    ![Wyświetlanie raportu w portalu internetowym](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

## <a name="considerations-and-limitations"></a>Istotne kwestie i ograniczenia
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
### <a name="power-bi-desktop"></a>Power BI Desktop
Dostępnych jest wiele wspaniałych zasobów dotyczących tworzenia raportów w programie Power BI Desktop. Te linki stanowią dobry punkt wyjścia.

* [Wprowadzenie do programu Power BI Desktop](../desktop-getting-started.md)
* Uczenie z przewodnikiem: [Wprowadzenie do programu Power BI Desktop](../guided-learning/gettingdata.yml#step-2)

### <a name="power-bi-report-server"></a>Serwer raportów usługi Power BI
* [Instalowanie programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI](install-powerbi-desktop.md)  
* [Serwer raportów usługi Power BI — podręcznik użytkownika](user-handbook-overview.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)
