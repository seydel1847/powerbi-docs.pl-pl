---
title: Publikowanie raportu podzielonego na strony w usłudze Power BI (wersja zapoznawcza)
description: Z tego samouczka dowiesz się, jak opublikować raport podzielony na strony w usłudze Power BI przez przekazanie go z komputera lokalnego.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 11/05/2018
ms.author: maggies
ms.openlocfilehash: 76ec5c140fc90dcf71a76bc6ca13a860e3474c37
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280952"
---
# <a name="publish-a-paginated-report-to-the-power-bi-service-preview"></a>Publikowanie raportu podzielonego na strony w usłudze Power BI (wersja zapoznawcza)

Z tego artykułu dowiesz się więcej na temat publikowania raportu podzielonego na strony w usłudze Power BI przez przekazanie go z komputera lokalnego. Raporty podzielone na strony można załadować do obszaru Mój obszar roboczy lub innego obszaru roboczego, jeśli obszar roboczy znajduje się w pojemności Premium. Poszukaj ikony diamentu ![Ikona diamentu — pojemność usługi Power BI Premium](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) obok nazwy obszaru roboczego. 

Jeśli źródło danych raportu znajduje się w środowisku lokalnym, należy [utworzyć bramę](#create-a-gateway-to-an-on-premises-data-source) po przekazaniu raportu.

## <a name="add-a-workspace-to-a-premium-capacity"></a>Dodawanie obszaru roboczego do pojemności Premium

Jeśli obszar roboczy nie ma ikony diamentu ![Ikona diamentu — pojemność usługi Power BI Premium](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) obok nazwy, należy dodać obszar roboczy do pojemności Premium. 

1. Wybierz pozycję **Obszary robocze**, wybierz symbol wielokropka (**...**) znajdujący się obok nazwy obszaru roboczego, a następnie wybierz pozycję **Edytuj obszar roboczy**.

    ![Wybieranie pozycji Edytuj obszar roboczy](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace.png)

1. W oknie dialogowym **Edytowanie obszaru roboczego** rozwiń węzeł **Zaawansowane**, a następnie przesuń suwak **Pojemność dedykowana** do pozycji **Wł.**

    ![Wybieranie pojemności dedykowanej](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace-dialog.png)

   Zmiana tego ustawienia może okazać się niemożliwa. W takiej sytuacji skontaktuj się z administratorem pojemności usługi Power BI Premium i poproś go o nadanie Ci praw do przypisywania, dzięki którym zyskasz możliwość dodawania obszaru roboczego do pojemności Premium.


## <a name="upload-a-paginated-report"></a>Przekazywanie raportu podzielonego na strony

1. Utwórz raport podzielony na strony w programie Report Builder i zapisz go na komputerze lokalnym.

1. Otwórz usługę Power BI w przeglądarce i przejdź do obszaru roboczego w wersja Premium, w którym chcesz opublikować raport. Zwróć uwagę na ikonę diamentu ![Ikona diamentu — pojemność usługi Power BI Premium](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) obok nazwy. 

1. Wybierz pozycję **Pobierz dane**.

    ![Power BI — pobieranie danych](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-get-data.png)

1. W polu **Pliki** wybierz opcję **Pobierz**.

    ![Power BI — pobieranie plików](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-files-get.png)

1. Wybierz pozycję **Plik lokalny** > przejdź do raportu podzielonego na strony > **Otwórz**.

    ![Wybieranie pozycji Plik lokalny](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-local-file.png)

1. Wybierz kolejno pozycje **Kontynuuj** > **Edytuj poświadczenia**.

    ![Wybieranie pozycji Edytuj poświadczenia](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-edit-credentials.png)

1. Skonfiguruj poświadczenia i wybierz pozycję **Zaloguj się**.

    ![Edytuj poświadczenia](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-credentials.png)

   Raport zostanie wyświetlony na liście raportów.

    ![Raport podzielony na strony na liście Raporty](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

1. Wybierz raport, aby otworzyć go w usłudze Power BI. Jeśli raport ma parametry, musisz je wybrać, aby można było wyświetlić raport.
 
    ![Wybieranie parametrów](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

## <a name="create-a-gateway"></a>Tworzenie bramy

Podobnie jak w przypadku każdego innego raportu usługi Power BI, jeśli źródło danych raportu jest lokalne, w celu uzyskania dostępu do danych należy utworzyć bramę lub połączyć się z nią.

1. Obok nazwy raportu wybierz pozycję **Zarządzaj**.

   ![Zarządzanie raportem podzielonym na strony](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-manage.png)

1. Zapoznaj się z artykułem [Instalowanie bramy](service-gateway-install.md) dotyczącym usługi Power BI, aby uzyskać szczegółowe informacje i poznać następne kroki.

### <a name="gateway-limitations"></a>Ograniczenia dotyczące bramy

Obecnie bramy nie obsługują parametrów z wieloma wartościami.


## <a name="next-steps"></a>Następne kroki

- [Wyświetlanie raportu podzielonego na strony w usłudze Power BI](paginated-reports-view-power-bi-service.md)
- [Czym są raporty podzielone na strony w usłudze Power BI Premium? (wersja zapoznawcza)](paginated-reports-report-builder-power-bi.md)

