---
title: Jak wyeksportować raport z usługi Power BI do programu Power BI Desktop (wersja zapoznawcza)
description: Pobieranie raportu z usługi Power BI do pliku programu Power BI Desktop
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 5c42b633b3c8746d2e26656eb5310b1f74cb2500
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282016"
---
# <a name="export-a-report-from-power-bi-service-to-desktop-preview"></a>Eksportowanie raportu z usługi Power BI do wersji Desktop (wersja zapoznawcza)
W programie Power BI Desktop możesz wyeksportować (inaczej mówiąc *pobrać*) raport do usługi Power BI, zapisując raport i wybierając pozycję **Publikuj**. Możesz też wyeksportować w drugim kierunku i pobrać raport z usługi Power BI na pulpit. Rozszerzenie dla plików eksportowanych w dowolnym kierunku to *pbix*.

Istnieje kilka ograniczeń i zagadnień, które należy wziąć pod uwagę i które zostały omówione w dalszej części tego artykułu.

![Lista rozwijana Plik](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix"></a>Pobieranie raportu jako pliku pbix
Aby pobrać plik pbix, wykonaj następujące kroki:

1. W **usłudze Power BI** otwórz raport, który chcesz pobrać, w [widoku do edycji](consumer/end-user-reading-view.md).
2. Na pasku menu wybierz pozycje **Plik > Pobierz raport**.
   
   > [!NOTE]
   > Można pobrać jedynie raporty [utworzone za pomocą programu Power BI Desktop](guided-learning/publishingandsharing.yml?tutorial-step=2) po 23 listopada 2016 r. — i zaktualizowane po tej dacie. Jeśli nie, opcja menu *Pobierz raport* w usłudze Power BI będzie szara.
   > 
   > 
3. Gdy plik pbix jest tworzony, transparent stanu pokazuje postęp operacji. Gdy plik jest gotowy, zostanie wyświetlone pytanie o to, czy otworzyć, czy też zapisać plik pbix. Nazwa pliku odpowiada tytułowi raportu.
   
    ![otwórz, zapisz lub anuluj](media/service-export-to-pbix/power-bi-save-pbix.png)
   
    Masz teraz możliwość otwarcia pliku pbix w usłudze Power BI (app.powerbi.com) albo w programie Power BI Desktop.     
4. Aby natychmiast otworzyć raport na pulpicie, wybierz pozycję **Otwórz**. Aby zapisać plik w określonej lokalizacji, wybierz pozycję **Zapisz > Zapisz jako**. Jeśli jeszcze nie zostało to zrobione, [zainstaluj program Power BI Desktop](desktop-get-the-desktop.md).
   
    Po otwarciu raportu na pulpicie możesz zobaczyć komunikat ostrzegawczy informujący o tym, że niektóre funkcje dostępne w raporcie usługi Power BI mogą nie być dostępne na pulpicie.
   
    ![okno dialogowe ostrzeżenia](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. Edytor raportów w programie Power BI Desktop wygląda bardzo podobnie do edytora raportów w usłudze Power BI.  
   
    ![Edytor raportu w programie Power BI Desktop](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów
Istnieje kilka istotnych kwestii i ograniczeń związanych z pobieraniem (eksportowaniem) pliku *pbix* z usługi Power BI.

* Aby pobrać plik, musisz mieć dostęp do edycji do raportu
* Raport musiał zostać utworzony za pomocą programu **Power BI Desktop** i *opublikowany* w **usłudze Power BI** lub do usługi musiał zostać *przekazany* plik PBIX.
* Raporty muszą być opublikowane lub zaktualizowane po 23 listopada 2016 r. Raportów opublikowanych przed tą datą nie można pobrać.
* Ta funkcja nie będzie działać z raportami początkowo utworzonymi w **usłudze Power BI** łącznie z pakietami zawartości.
* Podczas otwierania pobranych plików należy zawsze używać najnowszej wersji programu **Power BI Desktop**. Pobrane pliki *pbix* mogą nie zostać otwarte w innej niż bieżąca wersji programu **Power BI Desktop**.
* Jeśli administrator wyłączył możliwość eksportowania danych, ta funkcja nie będzie widoczna w **usłudze Power BI**.
* Zestawu danych z odświeżaniem przyrostowym nie można pobrać do pliku *pbix*.

## <a name="next-steps"></a>Następne kroki
Obejrzyj trwający minutę film **Guy in a Cube** na temat tej funkcji:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Ponadto poniżej przedstawiono niektóre dodatkowe artykuły, które mogą pomóc Ci w nauce używania **usługi Power BI**:

* [Raporty w usłudze Power BI](consumer/end-user-reports.md)
* [Power BI — podstawowe pojęcia](consumer/end-user-basic-concepts.md)

Po zainstalowaniu programu **Power BI Desktop** następująca zawartość może pomóc Ci szybko zacząć z niego korzystać:

* [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)   

