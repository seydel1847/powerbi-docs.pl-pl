---
title: 'Błąd: Nie można odnaleźć żadnych danych w skoroszycie programu Excel'
description: 'Błąd: Nie można odnaleźć żadnych danych w skoroszycie programu Excel'
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: ea5312178d33986ebc3f4b9e8610012c87d54216
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2018
ms.locfileid: "53026036"
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>Błąd: Nie można odnaleźć żadnych danych w skoroszycie programu Excel

>[!NOTE]
>Ten artykuł dotyczy programu Excel 2007 lub nowszego.

Podczas importowania skoroszytu programu Excel do usługi Power BI może zostać wyświetlony następujący błąd:

*Błąd: Nie można odnaleźć żadnych danych w skoroszycie programu Excel. Dane mogą być niepoprawnie sformatowane. Edytuj skoroszyt w programie Excel i zaimportuj go ponownie.*

![Nie można odnaleźć danych w skoroszycie](media/service-admin-troubleshoot-excel-workbook-data/pbi_wecouldntfindanydata.png)

## <a name="quick-solution"></a>Szybkie rozwiązanie
1. Edytuj skoroszyt w programie Excel.
2. Zaznacz zakres komórek zawierających dane. Pierwszy wiersz powinien zawierać nagłówki kolumn (nazwy kolumn).
3. Naciśnij klawisze **Ctrl+T**, aby utworzyć tabelę.
4. Zapisz skoroszyt.
5. Wróć do usługi Power BI i zaimportuj skoroszyt ponownie lub jeśli pracujesz w programie Excel 2016, a skoroszyt został wcześniej zapisany w usłudze OneDrive dla Firm, w programie Excel kliknij pozycję Plik > Publikuj.

## <a name="details"></a>Szczegóły
### <a name="cause"></a>Przyczyna
W programie Excel można utworzyć **tabelę** obejmującą zakres komórek, co pozwala łatwiej sortować, filtrować i formatować dane.

Podczas importowania skoroszytu programu Excel usługa Power BI wyszukuje te tabele i importuje je do zestawu danych; jeśli nie znajdzie żadnej tabeli, zostanie wyświetlony ten komunikat o błędzie.

### <a name="solution"></a>Rozwiązanie
1. Otwórz skoroszyt w programie Excel. 
    >[!NOTE]
    >Ilustracje w tym temacie pochodzą z programu Excel 2013. Jeśli używasz innej wersji, elementy mogą wyglądać inaczej, jednak kroki są takie same.
    
    ![Otwieranie skoroszytu](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht1.png)
2. Zaznacz zakres komórek zawierających dane. Pierwszy wiersz powinien zawierać nagłówki kolumn (nazwy kolumn):
   
    ![Zaznaczanie zakresu komórek](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht2.png)
3. Na wstążce na karcie **WSTAW** kliknij pozycję **Tabela** (lub naciśnij skrót **Ctrl+T**).
   
    ![Wstawianie tabeli](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht3.png)
4. Zostanie wyświetlone następujące okno dialogowe. Upewnij się, że pole **Moja tabela ma nagłówki** zostało zaznaczone i wybierz przycisk **OK**:
   
    ![Tworzenie tabeli](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlcreatetbl.png)
5. Dane zostaną sformatowane jako tabela:
   
    ![Dane sformatowane jako tabela](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xltbl.png)
6. Zapisz skoroszyt.
7. Wróć do usługi Power BI. Wybierz pozycję Pobierz dane w dolnej części okienka nawigacji po lewej stronie.
   
    ![Pobierz dane](media/service-admin-troubleshoot-excel-workbook-data/pbi_getdata.png)
8. W polu **Pliki** wybierz opcję **Pobierz**.
   
    ![Pobieranie plików](media/service-admin-troubleshoot-excel-workbook-data/pbi_getfiles.png)
9. Zaimportuj ponownie skoroszyt programu Excel. Tym razem proces importu powinien znaleźć tabelę i zakończyć się powodzeniem.
   
    W przypadku dalszych problemów z importem skontaktuj się z nami, klikając pozycję **Społeczność ** w menu pomocy:
   
    ![Link do społeczności](media/service-admin-troubleshoot-excel-workbook-data/pbi_questionmenucommunity.png)
