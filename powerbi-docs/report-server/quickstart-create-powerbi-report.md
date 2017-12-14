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
ms.date: 10/28/2017
ms.author: maggies
ms.openlocfilehash: e492d31a8e1ed57a769c9a36f515d99369f6d6dc
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="quickstart-create-a-power-bi-report-for-power-bi-report-server"></a>Szybki start: tworzenie raportu usługi Power BI dla serwera raportów usługi Power BI
Raporty usługi Power BI można przechowywać i zarządzać nimi lokalnie w portalu internetowym serwera raportów usługi Power BI, podobnie jak w przypadku przechowywania ich w chmurze w usłudze Power BI (https://powerbi.com). Raporty usługi Power BI można tworzyć i edytować w programie Power BI Desktop, a następnie publikować je w portalu internetowym. Odbiorcy raportów w organizacji będą mogli wyświetlać je w przeglądarce lub w aplikacji mobilnej Power BI na urządzeniach przenośnych.

![Raport usługi Power BI w portalu internetowym](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

Jeśli masz już doświadczenie w tworzeniu raportów usługi Power BI w programie Power BI Desktop, możesz przystąpić do tworzenia raportów usługi Power BI dla serwera raportów usługi Power BI. Jeśli nie, oto cztery szybkie kroki ułatwiające rozpoczęcie pracy.

## <a name="step-1-install-power-bi-desktop-report-server"></a>Krok 1. Instalowanie programu Power BI Desktop (serwera raportów)
Być może masz już zainstalowany program Power BI Desktop do tworzenia raportów dla usługi Power BI. Zalecamy zainstalowanie wersji programu Power BI Desktop zoptymalizowanej pod kątem serwera raportów usługi Power BI, aby serwer i aplikacja były zawsze zsynchronizowane. Obie wersje programu Power BI Desktop mogą być zainstalowane na tym samym komputerze.

1. W portalu internetowym serwera raportów usługi Power BI wybierz pozycję **Nowy** > **Raport usługi Power BI**.
   
    ![Nowy raport usługi Power BI](media/quickstart-create-powerbi-report/report-server-web-portal-new-powerbi-report.png)
   
    Jeśli nie masz dostępu do portalu internetowego serwera raportów usługi Power BI, przejdź do witryny Centrum pobierania Microsoft i pobierz program [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=837581) (zoptymalizowany dla programu Power BI Report Server — dostępność ogólna: czerwiec 2017).
2. Na końcu procesu instalacji wybierz pozycję **Uruchom program Power BI Desktop teraz**.
   
    Program zostanie uruchomiony automatycznie i będzie można rozpocząć pracę. Na pasku tytułu będzie widnieć napis „Power BI Desktop (serwer raportów)” — oznacza to, że jest to właściwa wersja.
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