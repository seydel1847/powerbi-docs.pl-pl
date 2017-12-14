---
title: "Przechodzenie do szczegółów w wizualizacji w usłudze Power BI"
description: "Ten dokument przedstawia sposób przechodzenia do szczegółów w wizualizacji w usłudze Microsoft Power BI i programie Power BI Desktop."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: MNAaHw4PxzE
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/18/2017
ms.author: mihart
ms.openlocfilehash: 83c63ee2bed5ae7674223cf2fc3f9241308926e9
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="drill-down-in-a-visualization-in-power-bi"></a>Przechodzenie do szczegółów w wizualizacji w usłudze Power BI
## <a name="drill-down-requires-a-hierarchy"></a>Przechodzenie do szczegółów wymaga hierarchii
Jeśli wizualizacja ma hierarchię, przejście do szczegółów pozwala ujawnić dodatkowe szczegóły. Wizualizacja może na przykład dotyczyć liczby medali olimpijskich z uwzględnieniem hierarchii składającej się ze sportu, dyscypliny i rodzaju konkurencji. Domyślnie wizualizacja będzie wyświetlać medale według rodzaju sportu — gimnastyka, narciarstwo, sporty wodne itp. Ponieważ ma ona jednak hierarchię, po wybraniu jednego z elementów wizualizacji (np. słupka, linii lub bąbelka) zostanie wyświetlony bardziej szczegółowy obraz. Wybierz element **sporty wodne**, aby wyświetlić dane dotyczące pływania, skoków do wody oraz piłki wodnej.  Wybierz element **skoki do wody**, aby wyświetlić szczegóły dla konkurencji skoków z trampoliny, wieży oraz synchronicznych.

Możesz dodawać hierarchie do raportów, których jesteś właścicielem, ale nie do tych, które zostały Ci udostępnione.
Nie masz pewności, które wizualizacje usługi Power BI zawierają hierarchię?  Umieść kursor na wizualizacji i jeśli w rogach na górze wyświetlone zostaną poniższe kontrolki przechodzenia do szczegółów, oznacza to, że wizualizacja ma hierarchię.

![](media/power-bi-visualization-drill-down/power-bi-drill-icon4.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon3.png)
![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) ![](media/power-bi-visualization-drill-down/power-bi-drill-icon6.png)  

Daty są wyjątkowym typem hierarchii. Po dodaniu pola daty do wizualizacji usługa Power BI automatycznie dodaje hierarchię czasu, która zawiera rok, kwartał, miesiąc i dzień. Aby uzyskać więcej informacji, zobacz [Hierarchie wizualizacji i zachowanie przechodzenia do szczegółów](guided-learning/visualizations.yml#step-18) lub obejrzyj poniższy klip wideo.

  <iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Aby dowiedzieć się, jak tworzyć hierarchie przy użyciu programu Power BI Desktop, obejrzyj klip wideo [Sposób tworzenia i dodawania hierarchii](https://youtu.be/q8WDUAiTGeU)
> 
> 

## <a name="two-methods-to-drill-down"></a>Dwie metody przechodzenia do szczegółów
Istnieją dwa różne sposoby przechodzenia do szczegółów (lub zwijania szczegółów) w wizualizacji.  Oba zostały opisane w tym artykule. Obie metody dają taki sam rezultat, można więc wybrać wygodniejszą.

> [!NOTE]
> Aby to sprawdzić, [otwórz przykładową analizę Retail Analysis](sample-datasets.md) w usłudze Power BI i utwórz mapę drzewa wyświetlającą pozycję **Total Units This Year**  (Wartości) według pozycji **Territory** (terytorium), **City** (miasto), **PostalCode** (kod pocztowy) i **Name** (nazwa) (Grupa).  
> 
> 

## <a name="method-1-for-drill-down"></a>Przechodzenie do szczegółów — metoda 1
Ta metoda wykorzystuje ikony przechodzenia do szczegółów wyświetlane w rogach na górze wizualizacji.

1. W usłudze Power BI otwórz raport w [widoku do czytania](service-report-open-in-reading-view.md) lub [widoku do edycji](service-reading-view-and-editing-view.md). Przechodzenie do szczegółów wymaga wizualizacji z hierarchią. 
   
   Hierarchia została pokazana w animacji poniżej.  Wizualizacja zawiera hierarchię, w skład której wchodzi terytorium, miasto, kod pocztowy i nazwa miejscowości. Każde terytorium posiada co najmniej jedno miasto, każde miasto co najmniej jeden kod pocztowy itd. Domyślnie wizualizacja wyświetla tylko dane terytorium, ponieważ pozycja *Territory* wyświetlana jest na początku listy.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Aby włączyć przechodzenie do szczegółów, wybierz ikonę strzałki w prawym górnym rogu wizualizacji. Ciemna ikona oznacza, że przechodzenie do szczegółów jest włączone. Jeśli przechodzenie do szczegółów nie zostanie włączone, wybranie elementu wizualizacji (np. słupka lub bąbelka) spowoduje przefiltrowanie krzyżowe innych wykresów na stronie raportu.    
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon.png)
3. Aby przejść do szczegółów ***pojedynczego pola***, kliknij jeden z elementów wizualizacji, na wykresie słupkowym oznacza to kliknięcie jednego ze słupków, a na mapie drzewa kliknięcie jednego z *liści*. Zwróć uwagę, że tytuł zmienia się podczas przechodzenia do szczegółów i z powrotem. Na tej animacji zmienia się on z „Total Units This Year by Territory” (Całkowita liczba jednostek w tym roku według terytorium) na „Total Units This Year by Territory and City” (Całkowita liczba jednostek w tym roku według terytorium i miasta), a następnie na „Total Units This Year by Territory, City and PostalCode” (Całkowita liczba jednostek w tym roku według terytorium, miasta i kodu pocztowego) i na „Total Units This Year by Territory, City, PostalCode, and Name" (Całkowita liczba jednostek w tym roku według terytorium, miasta, kodu pocztowego i nazwy). Aby zwinąć szczegóły, wybierz ikonę **Zwiń szczegóły** ![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) w lewym górnym rogu wizualizacji, jak pokazano poniżej.
   
   ![](media/power-bi-visualization-drill-down/drill.gif)
4. Aby przejść do szczegółów ***wszystkich pól jednocześnie***, wybierz podwójną strzałkę w lewym górnym rogu wizualizacji.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillall.png)
5. Aby zwinąć szczegóły, wybierz strzałkę w górę w lewym górnym rogu wizualizacji.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillup2.png)

## <a name="method-2-for-drill-down"></a>Przechodzenie do szczegółów — metoda 2
Ta metoda wykorzystuje listę rozwijaną **Eksploruj** w górnym menu usługi Power BI.

1. W usłudze Power BI otwórz raport w [widoku do czytania](service-report-open-in-reading-view.md) lub [widoku do edycji](service-reading-view-and-editing-view.md). Przechodzenie do szczegółów wymaga wizualizacji z hierarchią. 
   
   Hierarchia została pokazana na obrazku poniżej.  Wizualizacja zawiera hierarchię, w skład której wchodzi terytorium, miasto, kod pocztowy i nazwa miejscowości. Każde terytorium posiada co najmniej jedno miasto, każde miasto co najmniej jeden kod pocztowy itd. Domyślnie wizualizacja wyświetla tylko dane terytorium, ponieważ pozycja *Territory* wyświetlana jest na początku listy.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Aby włączyć przechodzenie do szczegółów, uaktywnij wizualizację, wybierając ją, a następnie z górnego menu usługi Power BI wybierz pozycję **Eksploruj** > **Przejdź do szczegółów**. Tło ikony przechodzenia do szczegółów w prawym górnym rogu wizualizacji zmieni się na czarne. ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  
   
   ![](media/power-bi-visualization-drill-down/power-bi-explore2.png)
3. Po włączeniu możesz przechodzić do szczegółów pojedynczego pola, wybierając jeden z liści mapy drzewa. W tym przykładzie po wybraniu terytorium o nazwie **NC** wyświetlona zostaje całkowita liczba sprzedanych jednostek w tym roku w Karolinie Północnej według miast.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drilldown-1.png)
4. Aby przejść do szczegółów wszystkich pól jednocześnie, wybierz pozycję **Eksploruj** > **Pokaż następny poziom**.
   
   ![](media/power-bi-visualization-drill-down/power-bi-show-next-level.png)
5. Aby zwinąć szczegóły, wybierz pozycję **Eksploruj** > **Zwiń szczegóły**.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-up2.png)
6. Aby wyświetlić dane używane do tworzenia wizualizacji, wybierz pozycję **Pokaż dane**. Dane zostaną wyświetlone w okienku poniżej wizualizacji. Okienko będzie wciąż wyświetlane w trakcie dalszego przechodzenia do szczegółów wizualizacji i ich zwijania. Aby uzyskać więcej informacji, zobacz [Wyświetlanie danych użytych do tworzenia wizualizacji](service-reports-show-data.md).

## <a name="considerations-and-limitations"></a>Istotne kwestie i ograniczenia
* Jeśli dodanie pola daty do wizualizacji nie spowoduje utworzenia hierarchii, może to oznaczać, że to pole „data” nie jest w rzeczywistości zapisane jako data. Jeśli jesteś właścicielem zestawu danych, otwórz go w widoku *Dane* w programie Power BI Desktop, wybierz kolumnę zawierającą datę, a następnie w karcie Modelowanie zmień **Typ danych** na **Data** lub **Data/godzina**. Jeśli raport został Ci udostępniony, skontaktuj się z właścicielem i poproś o dokonanie zmiany.  
  
  ![](media/power-bi-visualization-drill-down/power-bi-change-data-type2.png)

## <a name="next-steps"></a>Następne kroki
[Wizualizacje w raportach usługi Power BI](power-bi-report-visualizations.md)

[Raporty usługi Power BI](service-reports.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

