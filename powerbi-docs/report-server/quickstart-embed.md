---
title: Osadzanie raportu przy użyciu elementu iFrame
description: Osadzanie raportu serwera raportów usługi Power BI w elemencie iFrame w programie SharePoint Server
author: markingmyname
ms.author: maghan
ms.date: 05/04/2018
ms.topic: quickstart
ms.service: powerbi
ms.component: powerbi-report-server
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 8d7653e6f390959df745fa2b19076ee89b26b1bc
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34293702"
---
# <a name="quickstart-embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>Szybki start: osadzanie raportu serwera raportów usługi Power BI w elemencie iFrame w programie SharePoint Server

Z tego przewodnika Szybki start dowiesz się, jak osadzać raport serwera raportów usługi Power BI przy użyciu elementu iFrame na stronie programu SharePoint. W przypadku pracy z usługą SharePoint Online serwer raportów usługi Power BI musi być publicznie dostępny. W usłudze SharePoint Online składnik Web Part usługi Power BI, który współpracuje z usługą Power BI, nie działa na serwerze raportów usługi Power BI. 

![Przykład elementu iFrame](media/quickstart-embed/quickstart_embed_01.png)
## <a name="prerequisites"></a>Wymagania wstępne
* Musisz mieć zainstalowany i skonfigurowany [serwer raportów usługi Power BI](https://powerbi.microsoft.com/en-us/report-server/).
* Konieczne będzie zainstalowanie programu [Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI](install-powerbi-desktop.md).
* Musisz mieć zainstalowane i skonfigurowane środowisko programu [SharePoint](https://docs.microsoft.com/en-us/sharepoint/install/install).

## <a name="creating-the-power-bi-report-server-report-url"></a>Tworzenie adresu URL raportu serwera raportów usługi Power BI

1. Pobierz przykład [Blog Demo](https://github.com/Microsoft/powerbi-desktop-samples) (Pokaz bloga) z usługi GitHub.

    ![pobieranie przykładowego pliku PBIX](media/quickstart-embed/quickstart_embed_14.png)

2. Otwórz przykładowy plik PBIX z serwisu GitHub w programie **Power BI Desktop zoptymalizowanym pod kątem serwera raportów usługi Power BI**.

    ![narzędzie PBI RS Desktop](media/quickstart-embed/quickstart_embed_02.png)

3. Zapisz raport na **serwerze raportów usługi Power BI**. 

    ![zapisywanie na serwerze PBI RS](media/quickstart-embed/quickstart_embed_03.png)

4. Wyświetl raport w **portalu internetowym**.

    ![Portal internetowy](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capturing-the-url-parameter"></a>Przechwytywanie parametru adresu URL

Po utworzeniu adresu URL można utworzyć element iFrame w ramach strony programu SharePoint do hostowania raportu. W przypadku dowolnego adresu URL raportu serwera raportów usługi Power BI można dodać parametr querystring elementu `?rs:embed=true` w celu osadzenia raportu w elemencie iFrame. 

   Na przykład:
    ``` 
    http://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embedding-a-power-bi-report-server-report-in-a-sharepoint-iframe"></a>Osadzanie raportu serwera raportów usługi Power BI w elemencie iFrame programu SharePoint

1. Przejdź do strony **Zawartość witryny** programu SharePoint.

    ![Strona zawartości witryny](media/quickstart-embed/quickstart_embed_05.png)

2. Wybierz stronę, na której chcesz dodać raport.

    ![Aplikacja strony zawartości witryny](media/quickstart-embed/quickstart_embed_06.png)

3. Wybierz ikonę koła zębatego w prawym górnym rogu i wybierz pozycję **Edytuj stronę**.

    ![Opcja Edytuj stronę](media/quickstart-embed/quickstart_embed_07.png)

4. Wybierz pozycję **Dodaj składnik Web Part**.

    ![Dodawanie składnika Web Part](media/quickstart-embed/quickstart_embed_08.png)

5. W obszarze **Kategorie** wybierz pozycję **Nośniki i zawartość**, w obszarze **Składniki** wybierz pozycję **Edytor zawartości**, a następnie wybierz pozycję **Dodaj**.

    ![Wybieranie składnika Web Part Edytor zawartości](media/quickstart-embed/quickstart_embed_09.png) ![Wybieranie pozycji Dodaj](media/quickstart-embed/quickstart_embed_091.png)

6. Wybierz pozycję **Kliknij tutaj, aby dodać nową zawartość**.

    ![Dodawanie nowej zawartości](media/quickstart-embed/quickstart_embed_10.png)

7. Na wstążce wybierz kartę **Formatowanie tekstu**, a następnie wybierz pozycję **Edytuj źródło**.

     ![Edytowanie źródła](media/quickstart-embed/quickstart_embed_11.png)

8. W oknie Edytowanie źródła wklej kod elementu iFrame, a następnie wybierz przycisk OK.

    ![Kod elementu iFrame](media/quickstart-embed/quickstart_embed_12.png)

     Na przykład:
     ```
     <iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. Na wstążce wybierz kartę **Strona** i wybierz pozycję **Zatrzymaj edytowanie**.

    ![Zatrzymywanie edytowania](media/quickstart-embed/quickstart_embed_13.png)

10. Teraz raport powinien być widoczny na stronie.

    ![Przykład elementu iFrame](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>Następne kroki

[Szybki start: tworzenie raportu usługi Power BI dla serwera raportów usługi Power BI](quickstart-create-powerbi-report.md)  
[Szybki start: tworzenie raportu z podziałem na strony dla serwera raportów usługi Power BI](quickstart-create-paginated-report.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/) 