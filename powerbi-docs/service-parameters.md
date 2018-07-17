---
title: Wyświetlanie i edytowanie ustawień parametrów zestawu danych w usłudze Power BI
description: Parametry zapytania są tworzone w programie Power BI Desktop, ale można je przeglądać i aktualizować w usłudze Power BI
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/26/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: ac271e8013bce5824931153351a651644a716a2f
ms.sourcegitcommit: 5eb8632f653b9ea4f33a780fd360e75bbdf53b13
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965164"
---
# <a name="what-is-a-query-parameter"></a>Co to jest parametr zapytania?
Parametry zapytania są dodawane w programie Power BI Desktop przez twórców raportu. Parametry pozwalają na tworzenie części raportów w zależności od co najmniej jednej *wartości* parametru. Na przykład twórca raportu może utworzyć parametr, który ogranicza możliwość użycia danych do pojedynczego regionu kraju, lub parametr, który definiuje dopuszczalne formaty pól, takie jak daty, godzina i tekst.

![Karta Strona główna przedstawiająca opcję Zarządzaj parametrami w programie Desktop](media/service-parameters/power-bi-manage-parameters.png)


## <a name="review-and-edit-parameters-in-power-bi-service"></a>Przeglądanie i edytowanie parametrów w usłudze Power BI

Po zdefiniowaniu parametrów w programie Desktop podczas [publikowania raportu w usłudze Power BI](desktop-upload-desktop-files.md) wybrane opcje i ustawienia parametrów są przenoszone wraz z raportem. Niektóre ustawienia parametrów można przeglądać i edytować w usłudze Power BI — nie parametry, które ograniczają dostępne dane, ale parametry, które zdefiniują i opisują dopuszczalne wartości.

1. W usłudze Power BI wybierz ikonę koła zębatego ![ikona koła zębatego](media/service-parameters/power-bi-cog.png), aby otworzyć obszar **Ustawienia**.

2. Wybierz kartę **Zestawy danych** i wyróżnij zestaw danych na liście. 
    
    ![Okno Ustawienia z wybraną kartą Zestawy danych](media/service-parameters/power-bi-select-dataset2.png)

3. Rozwiń pozycję **Parametry**.  Jeśli wybrany zestaw danych nie ma parametrów, zobaczysz komunikat z linkiem do sekcji Dowiedz się więcej dotyczącej parametrów zapytania. Ale jeśli zestaw danych ma parametry, rozwinięcie nagłówka **Parametry** spowoduje wyświetlenie tych parametrów. 

    ![Okno Ustawienia z rozwiniętą pozycją Parametry](media/service-parameters/power-bi-settings.png)

    Przejrzyj ustawienia parametrów i w razie potrzeby wprowadź zmiany. Szarych pól nie można edytować. 


## <a name="next-steps"></a>Następne kroki
Doraźnym sposobem dodawania prostych parametrów jest [modyfikowanie adresu URL](service-url-filters.md).