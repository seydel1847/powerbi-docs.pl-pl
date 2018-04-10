---
title: Łączenie plików (danych binarnych) w programie Power BI Desktop
description: Łatwe łączenie plikowych (binarnych) źródeł danych w programie Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 37aff7aadaf6b514ca3b7329db26bc0228022bdd
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/04/2018
---
# <a name="combine-files-binaries-in-power-bi-desktop"></a>Łączenie plików (danych binarnych) w programie Power BI Desktop
Jednym z zaawansowanych sposobów importowania danych do programu **Power BI Desktop** jest łączenie wielu plików, które mają ten sam schemat, w jedną tabelę logiczną. W wydaniu programu **Power BI Desktop** z listopada 2016 r. (oraz w kolejnych wersjach) ta wygodna i popularna metoda została udogodniona i rozszerzona, jak opisano w tym artykule.

Aby rozpocząć proces łączenia plików z tego samego folderu, wybierz opcję **Pobierz dane > Plik > Folder**.

![](media/desktop-combine-binaries/combine-binaries_1.png)

## <a name="previous-combine-files-binaries-behavior"></a>Poprzednie zachowanie łączenia plików (binarnych)
W wersjach programu **Power BI Desktop** sprzed listopada 2016 r. ta funkcja nosiła nazwę **Połącz dane binarne** i pozwalała na łączenie niektórych typów plików za pomocą przekształcenia **Połącz dane binarne**. Obowiązywały jednak przy tym pewne ograniczenia:

* Przekształcenia nie były uwzględniane dla poszczególnych plików przed połączeniem tych plików w jedną tabelę. W efekcie w ramach procesu edycji często trzeba było łączyć pliki, a następnie odfiltrowywać *wartości nagłówków* przez filtrowanie wierszy.
* Przekształcenie **Połącz pliki binarne** działało tylko w przypadku plików *tekstowych* i plików *CSV*, a nie działało w przypadku innych obsługiwanych formatów plików, takich jak skoroszyty programu Excel, pliki JSON i inne.

Klienci prosili o bardziej intuicyjne działanie operacji **Połącz dane binarne**, dlatego to przekształcenie zostało ulepszone i zmieniło nazwę na **Połącz pliki**.

## <a name="current-combine-files-behavior"></a>Obecne zachowanie łączenia plików
Obecnie program **Power BI Desktop** bardziej efektywnie obsługuje operację **Połącz pliki (dane binarne)**. Zaczynasz od wybrania pozycji **Połącz pliki** na karcie **Narzędzia główne** wstążki w **Edytorze zapytań** lub z poziomu samej kolumny.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

Przekształcenie **Połącz pliki** działa teraz w następujący sposób:

* Przekształcenie **Połącz pliki** analizuje każdy plik wejściowy i określa odpowiedni format pliku do użycia, taki jak *tekst*, *skoroszyt programu Excel* lub plik *JSON*.
* Przekształcanie pozwala wybrać konkretny obiekt z pierwszego pliku, na przykład ze *skoroszytu programu Excel*, do wyodrębnienia.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* Następnie operacja **Połącz pliki** automatycznie wykonuje następujące zapytania:
  
  * Tworzy przykładowe zapytanie, które wykonuje wszystkie wymagane kroki wyodrębniania w jednym pliku.
  * Tworzy *zapytanie funkcji*, które parametryzuje dane wejściowe plik/dane binarne do *zapytania przykładowego*. Zapytanie przykładowe i zapytanie funkcji są połączone, zatem zmiany w zapytaniu przykładowym są uwzględniane w zapytaniu funkcji.
  * Stosuje *zapytanie funkcji* do oryginalnego zapytania z wejściowymi plikami binarnymi (na przykład zapytanie *Folder*) tak, aby zapytanie funkcji było stosowane do binarnych danych wejściowych w każdym wierszu, a następnie rozwija wynikowe wyodrębnianie danych jako kolumny najwyższego poziomu.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

Nowe zachowanie przekształcenia **Połącz pliki** umożliwia łatwe łączenie wszystkich plików w danym folderze, o ile mają one ten sam typ pliku i strukturę (np. te same kolumny).

Ponadto można z łatwością zastosować dodatkowe kroki przekształcania lub wyodrębniania, modyfikując utworzone automatycznie *zapytanie przykładowe* bez konieczności martwienia się o modyfikowanie lub tworzenie dodatkowych kroków *zapytania funkcji*. Wszystkie zmiany w *zapytaniu przykładowym* są automatycznie generowane w połączonym *zapytaniu funkcji*.

## <a name="next-steps"></a>Następne kroki
Z poziomu programu Power BI Desktop możesz łączyć się z danymi różnego rodzaju. Więcej informacji na temat źródeł danych znajdziesz w następujących zasobach:

* [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)
* [Łączenie się z plikami CSV w programie Power BI Desktop](desktop-connect-csv.md)   
* [Wprowadzanie danych bezpośrednio w programie Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

