---
title: Konfigurowanie i korzystanie z tabel dat w programie Power BI Desktop
description: Dowiedz się, jak skonfigurować tabelę jako tabelę dat i co to oznacza w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 4e4c5c9362283678679ad9791d9d4c333d4dd308
ms.sourcegitcommit: 2ae660a7b70fce23eb58b159d049eca44a664f2c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/30/2018
ms.locfileid: "52670560"
---
# <a name="set-and-use-date-tables-in-power-bi-desktop"></a>Konfigurowanie i korzystanie z tabel dat w programie Power BI Desktop

Program **Power BI Desktop** działa w tle, automatycznie identyfikując tabele jako **tabele dat**. Następnie tworzy hierarchie dat oraz inne metadane dla modelu w Twoim imieniu. Możesz używać tych wbudowanych hierarchii podczas tworzenia funkcji raportu, takich jak wizualizacje, tabele, szybkie miary, fragmentatory itd. W tym celu program Power BI Desktop tworzy w Twoim imieniu ukryte tabele, których możesz używać w raportach i wyrażeniach DAX.

Wielu analityków danych woli tworzyć własne tabele danych, co jest dobrym rozwiązaniem. W programie **Power BI Desktop** można określić tabelę używaną przez model jako **tabela dat**, a następnie utworzyć związane z datami wizualizacje, tabele, szybkie miary itd. w oparciu o dane czasowe z tej tabeli. Określenie własnej tabeli dat pozwala kontrolować hierarchie dat utworzone w modelu i używać ich w **szybkich miarach** oraz innych operacjach korzystających z tabeli dat modelu. 

![](media/desktop-date-tables/date-tables_01.png)

## <a name="setting-your-own-date-table"></a>Konfigurowanie własnej tabeli dat

Aby skonfigurować **tabelę dat**, wybierz tabelę do użycia jako tabela dat w okienku **Pola**, po czym kliknij tabelę prawym przyciskiem myszy i wybierz pozycje **Oznacz jako tabelę dat > Oznacz jako tabelę dat** w wyświetlonym menu, zgodnie z rysunkiem poniżej.

![](media/desktop-date-tables/date-tables_02.png)

Można również wybrać tabelę, a następnie wybrać pozycję **Oznacz jako tabelę dat** na wstążce **Modelowanie**, pokazanej tutaj.

![](media/desktop-date-tables/date-tables_02b.png)

Po określeniu własnej **tabeli dat** program Power BI Desktop wykonuje następujące operacje sprawdzania poprawności tej kolumny i zawartej w niej danych, aby potwierdzić, że dane:

* zawierają unikatowe wartości
* nie zawierają wartości zerowych
* zawierają ciągłe wartości dat (od początku do końca)
* Jeśli dane są typu **Data/Godzina**, zawierają tą samą sygnaturę czasową w każdej wartości.

Istnieją dwa prawdopodobne scenariusze tworzenia własnej tabeli dat i obie metody są uzasadnione:

* Pierwszy scenariusz polega na użyciu kanonicznej lub podstawowej tabeli dat i hierarchii. Jest to tabela w Twoich danych, która spełnia wcześniej opisane kryteria weryfikacji poprawności tabeli dat. 

* Drugi scenariusz obejmuje wykorzystanie tabeli z usług Analysis Services, na przykład z polem *przyciemnionej daty*, która ma być użyta jako tabela dat. 

Po określeniu tabeli dat można wybrać, która kolumna w tej tabeli jest kolumną dat. Można określić kolumnę, która ma być użyta, wybierając tabelę w okienku **Pola**, a następnie klikając tabelę prawym przyciskiem myszy i wybierając pozycje **Oznacz jako tabelę dat > Ustawienia tabeli dat**. Zostanie wyświetlone następujące okno, w którym z listy rozwijanej można wybrać kolumny używane jako tabela dat.

![](media/desktop-date-tables/date-tables_03.png)

Należy pamiętać, że po określeniu własnej tabeli dat program **Power BI Desktop** nie tworzy automatycznie hierarchii, które normalnie zostałyby wbudowane w modelu w Twoim imieniu. Jeśli później usuniesz zaznaczenie tabeli dat (rezygnując z ręcznej konfiguracji tabeli dat), program Power BI Desktop odtworzy automatycznie utworzone wbudowane tabele dat dla kolumn dat w tabeli.

Warto również zauważyć, że po oznaczeniu tabeli jako tabeli dat wbudowana tabela dat utworzona (automatycznie) przez program Power BI Desktop zostanie usunięta i żadne wizualizacje ani wyrażenia DAX utworzone wcześniej na podstawie tej wbudowanej tabeli nie będą działać poprawnie. 

## <a name="marking-your-date-table-as-the-appropriate-data-type"></a>Oznaczanie tabeli dat jako odpowiedniego typu danych

Po określeniu własnej **tabeli dat** należy się upewnić, że typ danych został ustawiony prawidłowo. Należy ustawić opcję **Typ danych** na wartość **Data/Godzina** lub **Data**. W tym celu wykonaj następujące czynności:

1. Wybierz **tabelę dat** w okienku **Pola**, rozwiń ją w razie potrzeby, a następnie wybierz kolumnę, która ma służyć jako data.
   
    ![](media/desktop-date-tables/date-tables_04.png) 

2. Na karcie **Modelowanie** wybierz pozycję **Typ danych** i kliknij strzałkę listy rozwijanej, aby wyświetlić dostępne typy danych.

    ![](media/desktop-date-tables/date-tables_05.png)

3. Określ typ danych kolumny. 


## <a name="next-steps"></a>Następne kroki

Może zainteresują Cię również następujące artykuły:

* [Typy danych w programie Power BI Desktop](desktop-data-types.md)

 