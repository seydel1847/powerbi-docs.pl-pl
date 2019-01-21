---
title: Używanie miar w programie Power BI Desktop
description: Miary w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/08/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 4cdd4cf3f8a21b2e97b936ed4e6d4efe2df9a0e8
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54290595"
---
# <a name="measures-in-power-bi-desktop"></a>Miary w programie Power BI Desktop

Program **Power BI Desktop** pomaga w przygotowywaniu analizy danych za pomocą zaledwie kilku kliknięć. Jednak czasami te dane po prostu nie zawierają wszystkiego, co jest potrzebne do uzyskania odpowiedzi na niektóre najważniejsze pytania. Miary mogą Ci w tym pomóc.

Miary są stosowane w niektórych najczęściej używanych analizach danych. Mogą to być na przykład w sumy, średnie, wartości minimalne i maksymalne oraz zliczenia lub bardziej zaawansowane obliczenia utworzone samodzielnie przy użyciu formuły języka DAX. Obliczone wyniki miar zawsze zmieniają się w odpowiedzi na interakcje z raportami, umożliwiając szybkie i dynamiczne badanie danych ad hoc. Przyjrzyjmy się temu bliżej.

## <a name="understanding-measures"></a>Omówienie miar

W programie **Power BI Desktop** miary są tworzone i używane w **widoku raportu** lub **widoku danych**. Miary utworzone samodzielnie znajdują się na liście pól i są oznaczone ikoną kalkulatora. Miary można dowolnie nazywać i dodawać do nowych lub istniejących wizualizacji tak samo jak inne pola.

![](media/desktop-measures/measuresinpbid_measinfieldlist.png)

> [!NOTE]
> Być może zainteresują Cię również **szybkie miary**, czyli miary gotowe do użycia, które można wybrać w oknach dialogowych. Są one dobrym sposobem na szybkie tworzenie miar i poznanie składni języka DAX, ponieważ ich automatycznie utworzone formuły języka DAX są dostępne do przejrzenia. Zapoznaj się z artykułem: [szybkie miary](desktop-quick-measures.md).
> 
> 

## <a name="data-analysis-expressions"></a>Wyrażenia analizy danych

Miary obliczają wynik na podstawie formuły wyrażenia. Gdy tworzysz własne miary, używasz języka formuł [wyrażeń analizy danych](https://msdn.microsoft.com/library/gg413422.aspx) (DAX, Data Analysis Expressions). Język DAX zawiera bibliotekę ponad 200 funkcji, operatorów i konstrukcji. Zapewniają one ogromną elastyczność w tworzeniu miar do obliczania wyników na potrzeby praktycznie dowolnej analizy danych.

Formuły języka DAX są bardzo podobne do formuł programu Excel. Język DAX zawiera nawet wiele tych samych funkcji co program Excel, takich jak DATA, SUMA i LEWY. Jednak funkcje języka DAX są przeznaczone do pracy z danymi relacyjnymi, jakie występują w programie Power BI Desktop.

## <a name="lets-look-at-an-example"></a>Spójrzmy na przykład
Jen jest kierownikiem sprzedaży w firmie Contoso. Poproszono ją o podanie prognoz sprzedażowych odsprzedawców na przyszły rok obrachunkowy. Postanawia przygotować swoje oszacowania na podstawie kwot sprzedaży z poprzedniego roku z sześcioprocentowym wzrostem rocznym wynikającym z różnych promocji zaplanowanych na kolejne sześć miesięcy.

Aby utworzyć raport dotyczący tych oszacowań, importuje zeszłoroczne dane sprzedaży do programu Power BI Desktop. Odnajduje pole SalesAmount w tabeli Reseller Sales. Zaimportowane dane zawierają tylko kwoty sprzedaży z ostatniego roku, zmienia więc nazwę pola SalesAmount na Last Years Sales. Następnie przeciąga pole Last Years Sales na kanwę raportu. Na wizualizacji wykresu jest ono widoczne jako pojedyncza wartość, która jest sumą sprzedaży wszystkich odsprzedawców w ciągu ostatniego roku.

Zauważa, że mimo nieokreślenia żadnych obliczeń jedno obliczenie zostało podane automatycznie. Program Power BI Desktop utworzył własną miarę, sumując wszystkie wartości w polu Last Years Sales.

Jednak Jen potrzebuje miary do obliczenia prognoz sprzedażowych na nadchodzący rok, które będą oparte na zeszłorocznej sprzedaży pomnożonej przez 1,06 w celu uwzględnienia oczekiwanego 6 procentowego wzrostu w firmie. Na potrzeby tego obliczenia utworzy swoją własną miarę. Używając funkcji Nowa miara, tworzy nową miarę, a następnie wprowadza następującą formułę języka DAX:

    Projected Sales = SUM('Sales'[Last Years Sales])*1.06

Następnie Jen przeciąga swoją nową miarę Projected Sales na wykres.

![](media/desktop-measures/measuresinpbid_lastyearsales.png)

Szybko i przy minimalnym nakładzie pracy Jen ma teraz miarę do obliczania planowanej sprzedaży. Może dalej analizować swoje prognozy, filtrując według określonych odsprzedawców lub dodając inne pola do raportu.

## <a name="data-categories-for-measures"></a>Kategorie danych dla miar

Możesz też wybrać kategorie danych na potrzeby miar. 

Umożliwia to, między innymi, dynamiczne tworzenie adresów URL za pomocą miar i oznaczenie kategorii danych jako internetowego adresu URL. 

Możesz tworzyć tabele, w których miary są wyświetlane jako internetowe adresy URL, i kliknąć adres URL utworzony zgodnie z Twoim wyborem. Jest to szczególnie przydatne, gdy chcesz połączyć inne raporty usługi Power BI przy użyciu [parametrów filtrowania adresów URL](service-url-filters.md).

## <a name="learn-more"></a>Dowiedz się więcej
W tym temacie przedstawiliśmy tylko krótkie wprowadzenie do miar, ale istnieje o wiele więcej zasobów, które pomogą Ci nauczyć się, jak tworzyć własne miary. Pamiętaj, aby zapoznać się z dokumentem [Samouczek: tworzenie własnych miar w programie Power BI Desktop](desktop-tutorial-create-measures.md), skąd możesz pobrać przykładowy plik i wziąć udział w szczegółowych lekcjach na temat tworzenia kolejnych miar.  

Aby bardziej szczegółowo poznać język DAX, zapoznaj się z tematem [Podstawy języka DAX w programie Power BI Desktop](desktop-quickstart-learn-dax-basics.md). [Dokumentacja języka Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) zawiera szczegółowe artykuły na temat każdej funkcji, składni, operatorów i konwencji nazewnictwa. Język DAX od kilku lat jest obecny w dodatku Power Pivot do programu Excel i w usługach SQL Server Analysis Services, istnieje więc wiele innych przydatnych zasobów. Pamiętaj, aby zajrzeć na [stronę wiki DAX Resource Center](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx), gdzie wpływowi członkowie społeczności analizy biznesowej dzielą się swoją wiedzą na temat języka DAX.



