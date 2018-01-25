---
title: "Używanie przykładów usługi Power BI, samouczek."
description: "Samouczek: używanie przykładów usługi Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 03/08/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: d92edce9ae1332c4a0c73be5db93201c9b87dc86
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="the-power-bi-samples-a-tutorial"></a>Przykłady usługi Power BI, samouczek
<!-- Shared newnav Include -->
[!INCLUDE [newnavbydefault](./includes/newnavbydefault.md)]

Zalecamy rozpoczęcie od artykułu [Przykładowe zestawy danych dla usługi Power BI](sample-datasets.md). W tym artykule dowiesz się wszystkiego o przykładach; jak je pobrać, gdzie je zapisać, jak ich używać, a także poznasz niektóre z historii, które mogą opowiedzieć przykłady. Następnie, kiedy już opanujesz podstawy, wróć do tego samouczka.   

## <a name="about-this-tutorial"></a>Informacje o tym samouczku
Ten samouczek omawia sposób importowania przykładowych pakietów zawartości, dodawania ich do usługi Power BI oraz otwierania zawartości. *Pakiet zawartości* jest typem przykładu, w którym zestaw danych jest powiązany z pulpitem nawigacyjnym i raportem. Przykładowe pakiety zawartości są dostępne z poziomu usługi Power BI, przy użyciu funkcji **Pobierz dane**.

> [!NOTE]
> Ten samouczek dotyczy usługi Power BI, a nie programu Power BI Desktop.
> 
> 

Przykładowy pakiet zawartości *Retail Analysis* używany w tym samouczku składa się z pulpitu nawigacyjnego, raportu i zestawu danych.
Aby zapoznać się z tym pakietem zawartości i scenariuszem, możesz przed rozpoczęciem [zobaczyć przewodnik po przykładzie Retail Analysis](sample-retail-analysis.md).

## <a name="get-data-in-this-case-get-a-sample-content-pack"></a>Pobieranie danych (w tym przypadku pobieranie przykładowego pakietu zawartości)
1. Otwórz usługę Power BI i zaloguj się w niej (app.powerbi.com).
2. Wybierz obszar roboczy i utwórz nowy pulpit nawigacyjny.  
   
    ![](media/sample-tutorial-connect-to-the-samples/power-bi-create-dashboard2.png)
3. Nadaj mu nazwę **Retail Analysis sample**.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-name-dashboard.png)
4. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie. Jeśli nie widzisz opcji **Pobierz dane**, rozwiń w okienko nawigacji, wybierając pozycję ![](media/sample-tutorial-connect-to-the-samples/expand-nav.png).
   
   ![](media/sample-tutorial-connect-to-the-samples/pbi_getdata.png)
5. Wybierz opcję **Przykłady**.  
   
   ![](media/sample-tutorial-connect-to-the-samples/pbi_samplesdownload.png)
6. Wybierz pozycję *Retail Analysis Sample* i wybierz polecenie **Połącz**.   
   
   ![](media/sample-tutorial-connect-to-the-samples/pbi_retailanalysissampleconnect.png)

## <a name="what-exactly-was-imported"></a>Co dokładnie zostało zaimportowane?
W przypadku przykładowych pakietów zawartości po wybraniu opcji **Połącz** usługa Power BI tworzy kopię pakietu zawartości i zapisuje ją w chmurze. Ponieważ osoba, która utworzyła pakiet zawartości, dołączyła zestaw danych, raport i pulpit nawigacyjny, to właśnie te elementy otrzymasz po kliknięciu opcji **Połącz**.

1. Usługa Power BI tworzy nowy pulpit nawigacyjny i umieszcza go na liście na karcie **Pulpity nawigacyjne**. Żółta gwiazdka informuje użytkownika o tym, że jest to nowy element.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-new-dashboard.png)
2. Otwórz kartę **Raporty**.  W tym miejscu zobaczysz nowy raport o nazwie *Retail Analysis Sample*.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-new-report.png)
   
   Sprawdź też kartę **Zestawy danych**.  Znajdziesz tu nowy zestaw danych.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-new-dataset.png)

## <a name="explore-your-new-content"></a>Eksplorowanie nowej zawartości
Teraz możesz samodzielnie eksplorować pulpit nawigacyjny, zestaw danych i raport. Istnieje wiele różnych sposobów przechodzenia do pulpitów nawigacyjnych, raportów i zestawów danych. Poniżej opisano jeden z tych sposobów.  

> [!TIP]
> Potrzebujesz małego wsparcia na początek?  Sprawdź [Przewodnik po przykładzie Retail Analysis](sample-retail-analysis.md), aby uzyskać instrukcje krok po kroku dotyczące tego przykładu.
> 
> 

1. Przejdź z powrotem do karty **Pulpity nawigacyjne** i wybierz pulpit nawigacyjny *Retail Analysis Sample*, aby go otworzyć.    
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-dashboards.png)
2. Zostanie otwarty pulpit nawigacyjny.  Zawiera on różne kafelki wizualizacji.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-dashboards2new.png)
3. Wybierz jeden z kafelków, aby otworzyć raport źródłowy.  W tym przykładzie wybierzemy wykres warstwowy (ujęty w różową ramkę na poprzedniej ilustracji). Raport zostanie otwarty na stronie zawierającej ten wykres warstwowy.
   
    ![](media/sample-tutorial-connect-to-the-samples/power-bi-report.png)
   
   > [!NOTE]
   > Jeżeli kafelek zostanie utworzony przy użyciu [funkcji pytań i odpowiedzi usługi Power BI](power-bi-q-and-a.md), zamiast tego zostanie otwarta strona funkcji pytań i odpowiedzi.
   > 
   > 
4. Z powrotem na karcie **Zestawy danych** masz kilka opcji umożliwiających eksplorowanie zestawu danych.  Nie możesz otworzyć go i zobaczyć wszystkich wierszy oraz kolumn (jak w przypadku programu Power BI Desktop lub Excel).  Jeżeli ktoś udostępnia współpracownikom pakiet zawartości, zazwyczaj chce podzielić się szczegółowymi informacjami, a nie dawać współpracownikom bezpośredni dostęp do danych. Nie oznacza to jednak, że nie możesz eksplorować zestawu danych.  
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-chart-icon2.png)
   
   * Jednym ze sposobów eksploracji zestawu danych jest utworzenie własnych wizualizacji i raportów od początku.  Wybierz ikonę wykresu ![](media/sample-tutorial-connect-to-the-samples/power-bi-chart-icon4.png), aby otworzyć zestaw danych w trybie edycji raportu.
     
       ![](media/sample-tutorial-connect-to-the-samples/power-bi-report-editing.png)
   * Innym sposobem eksploracji zestawu danych jest uruchomienie funkcji [Szybki wgląd](service-insights.md). Wybierz wielokropek (...) i wybierz opcję **Uzyskaj szczegółowe dane**. Gdy szczegółowe informacje będą gotowe, wybierz opcję **Wyświetl szczegółowe dane**.
     
       ![](media/sample-tutorial-connect-to-the-samples/power-bi-insights.png)

## <a name="next-steps"></a>Następne kroki
[Power BI — podstawowe pojęcia](service-basic-concepts.md)

[Przykłady dla usługi Power BI](sample-datasets.md)

[Źródła danych dla usługi Power BI](service-get-data.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

