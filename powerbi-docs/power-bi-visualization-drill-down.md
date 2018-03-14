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
ms.date: 02/26/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: fb834c92953c2cafcbca77bc1b3828b385755bca
ms.sourcegitcommit: 743e44fc8730fea0f7149916080b0c6d7eb6359d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2018
---
# <a name="drill-down-in-a-visualization-in-power-bi"></a>Przechodzenie do szczegółów w wizualizacji w usłudze Power BI
## <a name="drill-down-requires-a-hierarchy"></a>Przechodzenie do szczegółów wymaga hierarchii
Jeśli wizualizacja ma hierarchię, przejście do szczegółów pozwala ujawnić dodatkowe szczegóły. Wizualizacja może na przykład dotyczyć liczby medali olimpijskich z uwzględnieniem hierarchii składającej się ze sportu, dyscypliny i rodzaju konkurencji. Domyślnie wizualizacja będzie wyświetlać liczbę medali według rodzaju sportu — gimnastyka, narciarstwo, sporty wodne itp. Ponieważ ma ona jednak hierarchię, po wybraniu jednego z elementów wizualizacji (np. słupka, linii lub bąbelka) zostanie wyświetlony bardziej szczegółowy obraz. Wybierz element **sporty wodne**, aby wyświetlić dane dotyczące pływania, skoków do wody oraz piłki wodnej.  Wybierz element **skoki do wody**, aby wyświetlić szczegóły dla konkurencji skoków z trampoliny, wieży oraz synchronicznych.

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
Istnieją dwie metody przechodzenia do szczegółów (lub w drugą stronę) w wizualizacji.  Oba zostały opisane w tym artykule. Obie metody dają taki sam rezultat, można więc wybrać wygodniejszą.

> [!NOTE]
> Aby to sprawdzić, [otwórz przykładową analizę Retail Analysis](sample-datasets.md) w usłudze Power BI i utwórz mapę drzewa wyświetlającą pozycję **Total Units This Year**  (Wartości) według pozycji **Territory** (terytorium), **City** (miasto), **PostalCode** (kod pocztowy) i **Name** (nazwa) (Grupa).  
> 
> 

## <a name="method-one-for-drill-down"></a>Pierwsza metoda przechodzenia do szczegółów
Ta metoda wykorzystuje ikony przechodzenia do szczegółów wyświetlane w rogach na górze wizualizacji.

1. W usłudze Power BI otwórz raport w [widoku do czytania lub widoku do edycji](service-reading-view-and-editing-view.md). Przechodzenie do szczegółów wymaga wizualizacji z hierarchią. 
   
   Hierarchia została pokazana w animacji poniżej.  Wizualizacja zawiera hierarchię, w skład której wchodzi terytorium, miasto, kod pocztowy i nazwa miejscowości. Każde terytorium posiada co najmniej jedno miasto, każde miasto co najmniej jeden kod pocztowy itd. Domyślnie wizualizacja wyświetla tylko dane terytorium, ponieważ pozycja *Territory* wyświetlana jest na początku listy.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Aby włączyć przechodzenie do szczegółów, wybierz ikonę strzałki w prawym górnym rogu wizualizacji. Ciemna ikona oznacza, że przechodzenie do szczegółów jest włączone. Jeśli przechodzenie do szczegółów nie zostanie włączone, wybranie elementu wizualizacji (np. słupka lub bąbelka) spowoduje przefiltrowanie krzyżowe innych wykresów na stronie raportu.    
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon.png)
3. Aby przejść do szczegółów **jednego pola w danym momencie**, wybierz jeden z elementów w wizualizacji. Na wykresie słupkowym oznacza to kliknięcie jednego słupka. Na wykresie mapy drzewa oznacza to kliknięcie jednego **liścia**. Zwróć uwagę, że tytuł zmienia się podczas przechodzenia do szczegółów i z powrotem. Na tej animacji zmienia się on z „Total Units This Year by Territory” (Całkowita liczba jednostek w tym roku według terytorium) na „Total Units This Year by Territory and City” (Całkowita liczba jednostek w tym roku według terytorium i miasta), a następnie na „Total Units This Year by Territory, City and PostalCode” (Całkowita liczba jednostek w tym roku według terytorium, miasta i kodu pocztowego) i na „Total Units This Year by Territory, City, PostalCode, and Name" (Całkowita liczba jednostek w tym roku według terytorium, miasta, kodu pocztowego i nazwy). Aby zwinąć szczegóły, wybierz ikonę **Zwiń szczegóły** ![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) w lewym górnym rogu wizualizacji, jak pokazano poniżej.
   
   ![](media/power-bi-visualization-drill-down/drill.gif)
4. Aby przejść do szczegółów ***wszystkich pól jednocześnie***, wybierz podwójną strzałkę w lewym górnym rogu wizualizacji.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillall.png)
5. Aby zwinąć szczegóły, wybierz strzałkę w górę w lewym górnym rogu wizualizacji.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillup2.png)

## <a name="method-two-for-drill-down"></a>Druga metoda przechodzenia do szczegółów
Ta metoda wykorzystuje listę rozwijaną **Eksploruj** w górnym menu usługi Power BI.

1. W usłudze Power BI otwórz raport w [widoku do czytania lub widoku do edycji](service-reading-view-and-editing-view.md). Przechodzenie do szczegółów wymaga wizualizacji z hierarchią. 
   
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

6. Aby wyświetlić dane używane do tworzenia wizualizacji, wybierz pozycję **Pokaż dane**. Dane są wyświetlane w okienku poniżej elementu wizualnego. Okienko będzie wciąż wyświetlane w trakcie dalszego przechodzenia do szczegółów wizualizacji i ich zwijania. Aby uzyskać więcej informacji, zobacz [Wyświetlanie danych użytych do tworzenia wizualizacji](service-reports-show-data.md).

## <a name="understanding-the-hierarchy-axis-and-hierarchy-group"></a>Opis osi hierarchii i grupy hierarchii
Oś hierarchii i grupa hierarchii to mechanizmy, których można użyć do zwiększenia lub zmniejszenia poziomu szczegółowości danych, które chcesz wyświetlić. Wszelkie dane, które można podzielić na kategorie i podkategorie, kwalifikują się jako dane zawierające hierarchię. W tym oczywiście dane dotyczące daty i godziny.

Możesz utworzyć wizualizację w usłudze Power BI, aby użyć hierarchii, wybierając jedno lub więcej pól danych do dodania do listy **Oś** lub listy **Grupa** wraz z danymi, które chcesz zbadać jako pola danych na liście **Wartości**. Użytkownik wie, czy jego dane są hierarchiczne, jeśli ikony trybu szczegółów pojawiają się w lewym lub prawym górnym rogu wizualizacji. 

Zasadniczo dobrze jest myśleć o dwóch typach danych hierarchicznych:
- Dane daty i godziny — jeśli masz pole danych z typem danych DateTime, masz już dane hierarchiczne. Usługa Power BI automatycznie tworzy hierarchię dla dowolnego pola danych, którego wartości można przeanalizować w ramach struktury [DateTime](https://msdn.microsoft.com/library/system.datetime.aspx). Należy dodać tylko jedno pole DateTime do listy **Oś** lub **Grupa**.
- Dane podzielone na kategorie — jeśli dane pochodzą z kolekcji zawierających podkolekcje lub w innym wypadku zawierają wiersze danych współużytkujące wspólne wartości, masz dane hierarchiczne.

Usługa Power BI umożliwia rozszerzenie o jeden lub wszystkie podzbiory. Możesz przejść do szczegółów w danych, aby zobaczyć jeden podzbiór na każdym poziome lub aby zobaczyć wszystkie podzbiory jednocześnie na każdym poziomie. Na przykład możesz przejść do szczegółów dla konkretnego roku lub wyświetlić wszystkie wyniki dla każdego roku, przechodząc w dół hierarchii. Ponadto nadal możesz działać w ten sam sposób w drugą stronę.

W poniższych sekcjach opisano przechodzenie do szczegółów od najwyższego widoku, średniego widoku i najniższego widoku.

### <a name="hierarchical-data-and-time-data"></a>Dane hierarchiczne oraz dane czasu
W tym przykładzie postępuj zgodnie z sekcją [Próbka analizy handlu detalicznego](sample-datasets.md) i utwórz wizualizację skumulowanego wykresu kolumnowego korzystającą z wartości **Month** (oś) względem wartości **TotalSales** (wartości).  

Chociaż pole danych osi to **Month** (miesiąc), nadal tworzy kategorię **Year** (rok) na liście **Oś**. Dzieje się tak, ponieważ usługa Power BI zapewnia pełną strukturę danych DateTime dla wszystkich odczytywanych wartości. Na początku hierarchii znajdują się dane dotyczące roku.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-1.png)

Przy włączonym trybie przechodzenia do szczegółów kliknij słupek na wykresie, aby przejść w dół o jeden poziom w hierarchii. Zostaną wyświetlone trzy słupki danych dla dostępnych kwartałów. Następnie z ikon w lewym górnym rogu wybierz opcję **Rozwiń wszystko w dół o jeden poziom w hierarchii**. Następnie wykonaj ten krok ponownie, aby osiągnąć najniższy poziom w hierarchii, który pokazuje wyniki dla każdego miesiąca.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-2.png)

Oprócz wizualizacji możemy zobaczyć hierarchię odzwierciedloną w danych renderowanych dla każdego raportu. W poniższej tabeli przedstawiono wyniki opcji **Pokaż dane** w przechodzeniu do szczegółów w raporcie od jednego miesiąca lub wszystkich miesięcy. 

Zwróć uwagę, że dane są takie same w przypadku raportów kwartalnych i rocznych, ale po przejściu do szczegółów na poziomie określonym dla pozycji **Wartości** możesz zobaczyć, jak jeden raport staje się bardziej szczegółowy, a raport „wszystkie miesiące” zawiera więcej danych.


|Tryb rozwijania|Year|Quarter|Month|Day|
| ---|:---:|:---:|:---:|---|
|Jeden|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-day.png)|
|Wszystkie|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-day.png)|


### <a name="hierarchical-category-data"></a>Dane kategorii hierarchicznej
Dane, które zostały wymodelowane na podstawie kolekcji i podkolekcji, są hierarchiczne. Dobrym przykładem będą dane lokalizacji. Należy wziąć pod uwagę tabelę w źródle danych, której kolumny to Country (kraj), State (stan), City (miasto) oraz Zip (kod pocztowy). Dane współużytkujące te same wartości w kolumnach Country (kraj), State (stan) i City (miasto) są hierarchiczne.

W tym przykładzie postępuj zgodnie z sekcją [Próbka analizy handlu detalicznego](sample-datasets.md). Utwórz wizualizację skumulowanego wykresu kolumnowego sprawdzającego pozycję **Total Units This Year** (całkowita liczba jednostek w bieżącym roku) (wartości) względem pozycji **Territory** (terytorium), **City** (miasto), **PostalCode** (kod pocztowy) oraz **Name** (nazwa) (grupa).  

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-1.png)

Przy włączonym trybie przechodzenia do szczegółów z ikon w lewym górnym rogu wybierz opcję **Rozwiń wszystko w dół o jeden poziom w hierarchii** trzy razy.
Teraz powinien być wyświetlany najniższy poziom hierarchii, w którym znajdują się wyniki dla pozycji Territory (terytorium), City (miasto) oraz Postal Code (kod pocztowy).

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-2.png)

Oprócz wizualizacji możemy zobaczyć hierarchię odzwierciedloną w danych renderowanych dla każdego raportu. W poniższej tabeli przedstawiono wyniki opcji **Pokaż dane** w przechodzeniu do szczegółów w raporcie dla jednego terytorium lub wszystkich terytoriów. Podczas przechodzenia do szczegółów możesz zobaczyć, jak jeden raport staje się bardziej szczegółowy, a raport „wszystkie terytoria” zawiera więcej danych.


| Tryb rozwijania|Terytorium|City|Kod pocztowy|Nazwa|
| ---|:---:|:---:|:---:|---|
|Jeden|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal-name.png)|
|Wszystkie|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal-name.png)|


## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia
* Jeśli dodanie pola daty do wizualizacji nie spowoduje utworzenia hierarchii, może to oznaczać, że to pole „data” nie jest w rzeczywistości zapisane jako data. Jeśli jesteś właścicielem zestawu danych, otwórz go w widoku *Dane* w programie Power BI Desktop, wybierz kolumnę zawierającą datę, a następnie na karcie Modelowanie zmień **Typ danych** na **Data** lub **Data/godzina**. Jeśli raport został Ci udostępniony, skontaktuj się z właścicielem i poproś o dokonanie zmiany.  
  
  ![](media/power-bi-visualization-drill-down/power-bi-change-data-type2.png)

## <a name="next-steps"></a>Następne kroki
[Wizualizacje w raportach usługi Power BI](power-bi-report-visualizations.md)

[Raporty usługi Power BI](service-reports.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

