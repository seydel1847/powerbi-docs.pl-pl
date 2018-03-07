---
title: "Łączenie plików binarnych w programie Power BI Desktop"
description: "Łatwe łączenie binarnych źródeł danych w programie Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 395562dfecba4657ffa906494f81532febb6a11f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="combine-binaries-in-power-bi-desktop"></a>Łączenie plików binarnych w programie Power BI Desktop
Jednym z zaawansowanych sposobów importowania danych do programu **Power BI Desktop** jest łączenie wielu plików, które mają ten sam schemat, w jedną tabelę logiczną. W wydaniu programu **Power BI Desktop** z listopada 2016 r. (oraz w kolejnych wersjach) ta wygodna i popularna metoda została udogodniona i rozszerzona, jak opisano w tym artykule.

Aby rozpocząć proces łączenia plików binarnych z tego samego folderu, wybierz pozycję **Pobierz dane > Plik > Folder**.

![](media/desktop-combine-binaries/combine-binaries_1.png)

## <a name="previous-combine-binaries-behavior"></a>Poprzednie zachowanie łączenia plików binarnych
W wersjach programu **Power BI Desktop** sprzed listopada 2016 r. można było łączyć niektóre typy plików za pomocą przekształcenia **Połącz pliki binarne**, ale obowiązywały pewne ograniczenia:

* Przekształcenia nie były uwzględniane dla poszczególnych plików przed połączeniem tych plików w jedną tabelę. W efekcie w ramach procesu edycji często trzeba było łączyć pliki, a następnie odfiltrowywać *wartości nagłówków* przez filtrowanie wierszy.
* Przekształcenie **Połącz pliki binarne** działało tylko w przypadku plików *tekstowych* i plików *CSV*, a nie działało w przypadku innych obsługiwanych formatów plików, takich jak skoroszyty programu Excel, pliki JSON i inne.

Klienci prosili o bardziej intuicyjne działanie operacji **łączenia plików binarnych**, więc przekształcenie zostało ulepszone.

## <a name="current-combine-binaries-behavior"></a>Obecne zachowanie łączenia plików binarnych
Obecnie program **Power BI Desktop** bardziej efektywnie obsługuje **łączenie plików binarnych**. Zaczynasz od wybrania pozycji **Połącz pliki binarne** na karcie **Narzędzia główne** wstążki w **Edytorze zapytań** lub z poziomu samej kolumny.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

Przekształcenie **Połącz pliki binarne** działa teraz w następujący sposób:

* Przekształcenie **Połącz pliki binarne** analizuje każdy plik wejściowy i określa odpowiedni format pliku do użycia, taki jak *tekst* lub *skoroszyt programu Excel* lub plik *JSON*.
* Przekształcanie pozwala wybrać konkretny obiekt z pierwszego pliku, na przykład ze *skoroszytu programu Excel*, do wyodrębnienia.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* Następnie przekształcenie **Połącz pliki binarne** automatycznie wykonuje następujące czynności:
  
  * Tworzy przykładowe zapytanie, które wykonuje wszystkie wymagane kroki wyodrębniania w jednym pliku.
  * Tworzy *zapytanie funkcji*, które parametryzuje dane wejściowe plik/dane binarne do *zapytania przykładowego*. Zapytanie przykładowe i zapytanie funkcji są połączone, zatem zmiany w zapytaniu przykładowym są uwzględniane w zapytaniu funkcji.
  * Stosuje *zapytanie funkcji* do oryginalnego zapytania z wejściowymi plikami binarnymi (na przykład zapytanie *Folder*) tak, aby zapytanie funkcji było stosowane do binarnych danych wejściowych w każdym wierszu, a następnie rozwija wynikowe wyodrębnianie danych jako kolumny najwyższego poziomu.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

Nowe zachowanie przekształcenia **Połącz pliki binarne** umożliwia łatwe łączenie wszystkich plików binarnych w danym folderze, o ile mają ten sam typ pliku i strukturę (np. te same kolumny).

Ponadto można z łatwością zastosować dodatkowe kroki przekształcenia lub wyodrębniania, modyfikując utworzone automatycznie *zapytanie przykładowe* bez konieczności martwienia się o modyfikowanie lub tworzenie dodatkowych kroków *zapytania funkcji*. Wszystkie zmiany w *zapytaniu przykładowym* są automatycznie generowane w połączonym *zapytaniu funkcji*.

## <a name="next-steps"></a>Następne kroki
Z poziomu programu Power BI Desktop możesz łączyć się z danymi różnego rodzaju. Więcej informacji na temat źródeł danych znajdziesz w następujących zasobach:

* [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)
* [Łączenie się z plikami CSV w programie Power BI Desktop](desktop-connect-csv.md)   
* [Wprowadzanie danych bezpośrednio w programie Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

