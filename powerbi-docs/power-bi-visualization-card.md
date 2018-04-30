---
title: Wizualizacje w postaci kart (kafelki z dużą liczbą)
description: Tworzenie wizualizacji w postaci karty w usłudze Power BI
services: powerbi
documentationcenter: ''
author: mihart
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
ms.date: 03/26/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3e30e0f742d97817583ecdfd72df65a8658ec977
ms.sourcegitcommit: 312390f18b99de1123bf7a7674c6dffa8088529f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="card-visualizations"></a>Wizualizacje w postaci kart
Czasami jedna liczba jest najważniejsza i chcesz ją śledzić na swoim pulpicie nawigacyjnym lub w raporcie usługi Power BI, np. łączna sprzedaż, udział w rynku rok do roku lub łączna liczba szans sprzedaży. Ten typ wizualizacji jest nazywany *kartą*. Podobnie jak w przypadku niemal wszystkich natywnych wizualizacji usługi Power BI, karty można tworzyć przy użyciu edytora raportu lub funkcji Pytania i odpowiedzi.

![Wizualizacja w postaci karty](media/power-bi-visualization-card/pbi_opptuntiescard.png)

## <a name="create-a-card-using-the-report-editor"></a>Tworzenie karty za pomocą edytora raportu
W poniższych instrukcjach używane są przykładowe dane dotyczące analizy handlu detalicznego. Aby je wykonać, [pobierz przykład](sample-datasets.md) dla usługi Power BI (app.powerbi.com) lub dla programu Power BI Desktop.   

1. Rozpocznij od [pustej strony raportu](power-bi-report-add-page.md) i wybierz pole **Store** \> **Open store count**. Jeśli używasz usługi Power BI, należy otworzyć raport w [widoku do edycji](service-interact-with-a-report-in-editing-view.md).

    Usługa Power BI tworzy wykres kolumnowy dla jednej liczby.

   ![](media/power-bi-visualization-card/pbi_rptnumbertilechart.png)
2. W okienku Wizualizacje wybierz ikonę karty.

   ![](media/power-bi-visualization-card/pbi_changechartcard.png)
6. Umieść kursor nad kartą i wybierz ikonę pinezki ![](media/power-bi-visualization-card/pbi_pintile.png), aby dodać wizualizację do pulpitu nawigacyjnego.

   ![](media/power-bi-visualization-card/power-bi-pin-icon.png)
7. Przypnij kafelek do istniejącego lub nowego pulpitu nawigacyjnego.

   * Istniejący pulpit nawigacyjny: z listy rozwijanej wybierz nazwę pulpitu nawigacyjnego.
   * Nowy pulpit nawigacyjny: wpisz nazwę nowego pulpitu nawigacyjnego.
8. Wybierz pozycję **Przypnij**.

   Komunikat o powodzeniu (w prawym górnym rogu) informuje o tym, że wizualizacja została dodana do pulpitu nawigacyjnego jako kafelek.

   ![](media/power-bi-visualization-card/power-bi-pin-success-message.png)
9. Wybierz pozycję **Przejdź do pulpitu nawigacyjnego**. Tam możesz [edytować i przenieść](service-dashboard-edit-tile.md) przypiętą wizualizację.


## <a name="create-a-card-from-the-qa-question-box"></a>Tworzenie karty za pomocą pola pytania funkcji Pytania i odpowiedzi
Skorzystanie z pola pytania funkcji Pytania i odpowiedzi jest najprostszym sposobem utworzenia karty. Pole pytania funkcji Pytania i odpowiedzi jest dostępne w usłudze Power BI (app.powerbi.com) z poziomu pulpitu nawigacyjnego lub raportu. Poniższe kroki przedstawiają tworzenie karty z poziomu pulpitu nawigacyjnego usługi Power BI. Jeśli chcesz utworzyć kartę za pomocą funkcji Pytania i odpowiedzi w programie Power BI Desktop, [wykonaj te instrukcje](https://powerbi.microsoft.com/en-us/blog/power-bi-desktop-december-feature-summary/#QandA), aby uzyskać wersję zapoznawczą funkcji Pytania i odpowiedzi dla raportów w programie Power BI Desktop.

1. Utwórz [pulpit nawigacyjny](service-dashboards.md) i [pobierz dane](service-get-data.md). W tym przypadku jest używany [przykład Opportunity Analysis](sample-opportunity-analysis.md).

1. W polu pytania w górnej części pulpitu nawigacyjnego rozpocznij wpisywanie tego, co chcesz wiedzieć o danych. 

   ![](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

>**PORADA**: Z poziomu raportu usługi Power BI, w [widoku do edycji](service-reading-view-and-editing-view.md), wybierz pozycję **Zadaj pytanie** z górnego paska menu. W przypadku raportu programu Power BI Desktop znajdź jakieś wolne miejsce w raporcie i kliknij je dwukrotnie, aby otworzyć pole pytania.

3. Na przykład wpisz w polu pytania „number of opportunities” (liczba możliwości).

   ![](media/power-bi-visualization-card/power-bi-q-and-a.png)

   Pole pytania pomaga zadać pytanie, pokazując sugestie i inne sformułowania, a na koniec wyświetla łączną liczbę.  
4. Wybierz ikonę pinezki ![](media/power-bi-visualization-card/pbi_pintile.png) w prawym górnym rogu, aby dodać kartę do pulpitu nawigacyjnego.

   ![](media/power-bi-visualization-card/power-bi-pin.png)
5. Przypnij kartę jako kafelek do istniejącego lub nowego pulpitu nawigacyjnego.

   * Istniejący pulpit nawigacyjny: z listy rozwijanej wybierz nazwę pulpitu nawigacyjnego. Twój wybór będzie ograniczony tylko do tych pulpitów nawigacyjnych wewnątrz bieżącego obszaru roboczego.
   * Nowy pulpit nawigacyjny: wpisz nazwę nowego pulpitu nawigacyjnego a zostanie ona dodana do Twojego bieżącego obszaru roboczego.
6. Wybierz pozycję **Przypnij**.

   Komunikat o powodzeniu (w prawym górnym rogu) informuje o tym, że wizualizacja została dodana do pulpitu nawigacyjnego jako kafelek.  

   ![](media/power-bi-visualization-card/power-bi-success.png)
7. Wybierz pozycję **Przejdź do pulpitu nawigacyjnego**, aby wyświetlić nowy kafelek. Tam możesz [zmienić nazwę, rozmiar, dodać hiperlink i zmienić położenia kafelka i inne](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.

   ![](media/power-bi-visualization-card/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów
- Jeśli pole pytania nie jest w ogóle widoczne, skontaktuj się z administratorem systemu lub dzierżawy.    
- Jeśli używasz programu Power BI Desktop i dwukrotne kliknięcie pustego miejsca w raporcie nie otwiera pola funkcji Pytania i odpowiedzi, konieczne może być jej włączenie.  Wybierz pozycję **Plik > Opcje i ustawienia > Opcje > Funkcje w wersji zapoznawczej > Pytania i odpowiedzi**, a następnie ponownie uruchom program Power BI Desktop.

## <a name="format-a-card"></a>Formatowanie karty
Istnieje wiele opcji zmieniania etykiet, tekstu, koloru i innych elementów. Najlepszym sposobem zapoznania się z nimi jest utworzenie karty, a następnie eksplorowanie okienka Formatowanie. Oto tylko kilka spośród dostępnych opcji formatowania. 

1. Rozpocznij, wybierając ikonę pędzla, aby otworzyć okienko formatowania. 

    ![](media/power-bi-visualization-card/power-bi-format-card.png)
2. Rozwiń węzeł **Etykieta danych**, a następnie zmień kolor, rozmiar i rodzinę czcionek. Jeśli masz tysiące sklepów, możesz użyć opcji **Jednostki wyświetlania**, aby pokazać liczbę w tysiącach i kontrolować liczbę miejsc dziesiętnych. Na przykład można użyć wersji 125,8K zamiast 125 832,00.

3.  Rozwiń węzeł **Etykieta kategorii**, a następnie zmień rozmiar i kolor.

    ![](media/power-bi-visualization-card/power-bi-card-format.png)

4. Rozwiń węzeł **Tło** i przesuń suwak do położenia oznaczającego włączenie.  Teraz możesz zmienić kolor tła i przezroczystość.

    ![](media/power-bi-visualization-card/power-bi-format-color.png)

5. Zmieniaj ustawienia opcji formatowania do momentu uzyskania wybranego wyglądu karty. 

    ![](media/power-bi-visualization-card/power-bi-formatted.png)

## <a name="next-steps"></a>Następne kroki
[Kafelki pulpitu nawigacyjnego w usłudze Power BI](service-dashboard-tiles.md)

[Pulpity nawigacyjne w usłudze Power BI](service-dashboards.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)
