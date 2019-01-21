---
title: Tworzenie raportu usługi Power BI dla serwera raportów usługi Power BI
description: Dowiedz się, jak utworzyć raport usługi Power BI dla serwera raportów usługi Power BI w kilku prostych krokach.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 09/19/2018
ms.author: maggies
ms.openlocfilehash: dd3da287d976b9fe84ab56b425a5f08fba31d224
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54288364"
---
# <a name="create-a-power-bi-report-for-power-bi-report-server"></a>Tworzenie raportu usługi Power BI dla serwera raportów usługi Power BI
Raporty usługi Power BI można przechowywać i zarządzać nimi lokalnie w portalu internetowym serwera raportów usługi Power BI, podobnie jak w przypadku przechowywania ich w chmurze w usłudze Power BI (https://powerbi.com). Raporty usługi Power BI można tworzyć i edytować w programie Power BI Desktop, a następnie publikować je w portalu internetowym. Odbiorcy raportów w organizacji będą mogli wyświetlać je w przeglądarce lub w aplikacji mobilnej Power BI na urządzeniach przenośnych.

![Raport usługi Power BI w portalu internetowym](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

Oto cztery szybkie kroki ułatwiające rozpoczęcie pracy.

## <a name="step-1-install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Krok 1. Instalowanie programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI

Jeśli masz już doświadczenie w tworzeniu raportów usługi Power BI w programie Power BI Desktop, jesteś blisko rozpoczęcia tworzenia raportów usługi Power BI dla serwera raportów usługi Power BI. Zalecamy zainstalowanie wersji programu Power BI Desktop zoptymalizowanej pod kątem serwera raportów usługi Power BI, aby serwer i aplikacja były zawsze zsynchronizowane. Obie wersje programu Power BI Desktop mogą być zainstalowane na tym samym komputerze.

1. W portalu internetowym serwera raportów wybierz strzałkę **Pobierz** > **Power BI Desktop**.

    ![Pobieranie programu Power BI Desktop z portalu internetowego](media/quickstart-create-powerbi-report/report-server-download-web-portal.png)

    Możesz też przejść bezpośrednio do programu [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=57271) (zoptymalizowanego pod kątem serwera raportów usługi Power BI — sierpień 2018) w Centrum pobierania Microsoft.

2. Na stronie Centrum pobierania wybierz pozycję **Pobierz**.

3. W zależności od komputera wybierz:

    - **PBIDesktopRS.msi** (wersja 32-bitowa) lub

    - **PBIDesktopRS_x64.msi** (wersja 64-bitowa).

4. Po pobraniu instalatora uruchom kreatora instalacji programu Power BI Desktop (sierpień 2018).

2. Na koniec instalacji zaznacz pozycję **Uruchom program Power BI Desktop teraz**.
   
    Program zostanie uruchomiony automatycznie i będzie można rozpocząć pracę. Na pasku tytułu będzie widnieć napis „Power BI Desktop (sierpień 2018)” — oznacza to, że jest to właściwa wersja.

    ![Power BI Desktop (wersja z sierpnia 2018)](media/quickstart-create-powerbi-report/power-bi-report-server-desktop-august-2018.png)

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

## <a name="next-steps"></a>Następne kroki
### <a name="power-bi-desktop"></a>Power BI Desktop
Dostępnych jest wiele wspaniałych zasobów dotyczących tworzenia raportów w programie Power BI Desktop. Ten link to dobry punkt startowy.

* [Wprowadzenie do programu Power BI Desktop](../desktop-getting-started.md)
* Nauka z przewodnikiem: [Wprowadzenie do programu Power BI Desktop](../guided-learning/gettingdata.yml?tutorial-step=2)

### <a name="power-bi-report-server"></a>serwerze raportów usługi Power BI
* [Instalowanie programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI](install-powerbi-desktop.md)  
* [Co to jest serwer raportów usługi Power BI?](get-started.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)
