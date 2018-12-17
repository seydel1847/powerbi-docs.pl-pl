---
title: Dodawanie hiperlinków do tabeli
description: Użyj programu Power BI Desktop do tworzenia hiperlinków. Następnie użyj programu Power BI Desktop lub usługi Power BI, aby dodać je do macierzy i tabel raportu.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 92224e00da95714125a8e15c27432e8d305ae0f7
ms.sourcegitcommit: f25464d5cae46691130eb7b02c33f42404011357
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2018
ms.locfileid: "53180558"
---
# <a name="add-hyperlinks-to-a-table"></a>Dodawanie hiperlinków do tabeli
W tym temacie opisano, jak tworzyć hiperlinki, używając programu Power BI Desktop. Następnie użyj programu Power BI Desktop lub usługi Power BI, aby dodać je do macierzy i tabel raportu. 

![Tabela z hiperlinkami](media/power-bi-hyperlinks-in-tables/hyperlinkedtable.png)

> [!NOTE]
> Hiperlinki w [kafelkach na pulpitach nawigacyjnym](service-dashboard-edit-tile.md) i [polach tekstowych na pulpitach nawigacyjnych](service-dashboard-add-widget.md) mogą być tworzone na bieżąco przy użyciu usługi Power BI. Hiperlinki w [polach tekstowych w raportach](service-add-hyperlink-to-text-box.md) mogą być tworzone na bieżąco przy użyciu usługi Power BI i programu Power BI Desktop.
> 
> 

## <a name="to-create-a-hyperlink-in-a-table-or-matrix-using-power-bi-desktop"></a>Tworzenie hiperlinku w tabeli lub macierzy przy użyciu programu Power BI Desktop
Hiperlinki w tabelach i macierzach mogą być tworzone w programie Power BI Desktop, ale nie z poziomu usługi Power BI. Hiperlinki mogą być również tworzone przy użyciu dodatku Power Pivot dla programu Excel przed zaimportowaniem skoroszytu do usługi Power BI. Obie metody zostały opisane poniżej.

## <a name="create-a-table-or-matrix-hyperlink-in-power-bi-desktop"></a>Tworzenie hiperlinku macierzy lub tabeli w programie Power BI Desktop
Procedura dodawania hiperlinku zależy od tego, czy dane zostały zaimportowane, czy też połączenie z nimi odbywa się przy użyciu zapytania bezpośredniego. Poniżej opisano oba scenariusze.

### <a name="for-data-imported-into-power-bi"></a>W przypadku danych zaimportowanych do usługi Power BI
1. Jeśli hiperlink nie został jeszcze utworzony jako pole w zestawie danych, użyj programu Desktop, aby dodać go jako [kolumnę niestandardową](desktop-common-query-tasks.md).
2. W widoku danych zaznacz kolumnę, a następnie na karcie **Modelowanie** wybierz listę rozwijaną **Kategoria danych**.
   
    ![Lista rozwijana kategorii danych](media/power-bi-hyperlinks-in-tables/pbi_data_category.png)
3. Wybierz pozycję **Internetowy adres URL**.
4. Przełącz się do widoku raportu i utwórz tabelę lub macierz, korzystając z pola z kategorią Internetowy adres URL. Hiperlinki będą podkreślone i w kolorze niebieskim.

    ![Linki w kolorze niebieskim i podkreślone](media/power-bi-hyperlinks-in-tables/power-bi-table-with-hyperlinks2.png)

    > [!NOTE]
    > Adresy URL muszą zaczynać się od **http://, https://** lub **www**.
    >
   
1. Jeśli nie chcesz wyświetlać długiego adresu URL w tabeli, możesz wyświetlić ikonę hiperlinku  ![Ikona hiperlinku](media/power-bi-hyperlinks-in-tables/power-bi-hyperlink-icon.png) zamiast niego. Należy pamiętać, że nie można wyświetlać ikon w macierzach.
   
   * Wybierz wykres, aby go uaktywnić.
   * Wybierz ikonę wałka do malowania ![Ikona wałka do malowania](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png) w celu otwarcia karty Formatowanie.
   * Rozwiń pozycję **Wartości**, zlokalizuj **adres URL ikony** i zmień ustawienie na **Włączony**.
6. (Opcjonalnie) [Opublikuj raport z programu Power BI Desktop do usługi Power BI](guided-learning/publishingandsharing.yml?tutorial-step=2) i otwórz raport w usłudze Power BI. Hiperlinki będą działać także tam.

### <a name="for-data-connected-with-directquery"></a>W przypadku danych połączonych przy użyciu zapytania bezpośredniego
W trybie zapytania bezpośredniego nie można utworzyć nowej kolumny.  Jeśli jednak dane zawierają już adresy URL, można przekształcić je w hiperlinki.

1. W widoku raportu utwórz tabelę za pomocą pola, które zawiera adresy URL.
2. Zaznacz kolumnę, a następnie na karcie **Modelowanie** wybierz listę rozwijaną **Kategoria danych**.
3. Wybierz pozycję **Internetowy adres URL**. Hiperlinki będą podkreślone i w kolorze niebieskim.
4. (Opcjonalnie) [Opublikuj raport z programu Power BI Desktop do usługi Power BI](guided-learning/publishingandsharing.yml?tutorial-step=2) i otwórz raport w usłudze Power BI. Hiperlinki będą działać także tam.

## <a name="create-a-table-or-matrix-hyperlink-in-excel-power-pivot"></a>Tworzenie hiperlinku macierzy lub tabeli przy użyciu dodatku Power Pivot dla programu Excel
Innym sposobem, aby dodać hiperlinki do tabel i macierzy usługi Power BI, jest utworzenie hiperlinków w zestawie danych przed jego zaimportowaniem/połączeniem się z tym zestawem z usługi Power BI. W tym przykładzie użyto skoroszytu programu Excel.

1. Otwórz skoroszyt w programie Excel.
2. Wybierz kartę **PowerPivot**, a następnie wybierz pozycję **Zarządzaj**.
   
   ![Otwieranie dodatku PowerPivot w programie Excel](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot2.png)
1. Po otwarciu programu PowerPivot wybierz kartę **Zaawansowane**.
   
   ![Karta Zaawansowane programu PowerPivot](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot3.png)
4. Umieść kursor w kolumnie zawierającej adresy URL, które chcesz zamienić na hiperlinki w tabelach usługi Power BI.
   
   > [!NOTE]
   > Adresy URL muszą zaczynać się od **http://, https://** lub **www**.
   > 
5. W grupie **Właściwości raportów** wybierz listę rozwijaną **Kategoria danych** i wybierz pozycję **Internetowy adres URL**. 
   
   ![Lista rozwijana kategorii danych w programie Excel](media/power-bi-hyperlinks-in-tables/createhyperlinksnew.png)

6. Z poziomu usługi Power BI lub programu Power BI Desktop nawiąż połączenie z tym skoroszytem lub zaimportuj go.
7. Utwórz wizualizację tabeli, która zawiera pole adresu URL.
   
   ![Tworzenie tabeli w usłudze Power BI z polem adresu URL](media/power-bi-hyperlinks-in-tables/hyperlinksintables.gif)

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów
Pytanie: Czy można użyć niestandardowego adresu URL jako hiperlinku w tabeli lub macierzy?    
Odpowiedź: Nie. Można użyć ikony łącza. Jeśli potrzebujesz niestandardowego tekstu dla hiperlinków, a Twoja lista adresów URL jest krótka, rozważ użycie pola tekstowego.


## <a name="next-steps"></a>Następne kroki
[Wizualizacje w raportach usługi Power BI](visuals/power-bi-report-visualizations.md)

[Power BI — podstawowe pojęcia](consumer/end-user-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

