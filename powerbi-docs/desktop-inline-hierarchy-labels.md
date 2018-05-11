---
title: Używanie etykiet hierarchii wbudowanych w programie Power BI Desktop
description: Używanie etykiet hierarchii wbudowanych w programie Power BI Desktop
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
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 974194cb04701e2dc21814a0945227ad9c4b770c
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="use-inline-hierarchy-labels-in-power-bi-desktop"></a>Używanie etykiet hierarchii wbudowanych w programie Power BI Desktop
Program **Power BI Desktop** obsługuje **etykiety hierarchii wbudowanych**. Jest to pierwsza z dwóch funkcji mających na celu ulepszenie hierarchicznego przechodzenia do szczegółów. Druga funkcja, która jest aktualnie opracowywana, to możliwość używania etykiet hierarchii zagnieżdżonych (śledź nasze aktualizacje, ponieważ są one częste).   

## <a name="how-inline-hierarchy-labels-work"></a>Jak działają etykiety hierarchii wbudowanych
Etykiety hierarchii wbudowanych pozwalają na wyświetlanie etykiet hierarchii podczas rozwijania wizualizacji przy użyciu funkcji **Rozwiń wszystko**. Jedną z głównych korzyści wyświetlania tych etykiet hierarchii jest możliwość **sortowania** według tych różnych etykiet hierarchii po rozwinięciu danych hierarchicznych.

### <a name="using-the-built-in-expand-all-feature-without-sorting-by-hierarchy-labels"></a>Korzystanie z wbudowanej funkcji Rozwiń wszystko (bez sortowania według etykiet hierarchii)
Zanim sprawdzimy, jak działają etykiety hierarchii wbudowanych, omówimy zachowanie domyślnej funkcji **Rozwiń wszystko**. To pomoże nam zrozumieć (i docenić), jak użyteczne mogą być etykiety hierarchii wbudowanych.

Na poniższej ilustracji przedstawiono wizualizację wykresu słupkowego dla sprzedaży rocznej. Po kliknięciu prawym przyciskiem myszy można wybrać polecenie **Rozwiń wszystko**.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_4.png)

Gdy polecenie **Rozwiń wszystko** zostanie wybrane, wizualizacja rozwija hierarchię dat z poziomu *Year* (Rok) do poziomu *Quarter* (Kwartał), jak pokazano na poniższej ilustracji.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_5.png)

Zwróć uwagę, że etykiety *Year* i *Quarter* są pokazywane w tekście razem... Ten schemat etykietowania jest kontynuowany podczas używania polecenia **Rozwiń wszystko** aż do końca hierarchii.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_6.png)

Tak się zachowuje hierarchia *Date*, skojarzona z polami o typie danych *data/godzina*. Przejdźmy do następnej sekcji i zobaczmy, czym różni się nowa funkcja etykiet hierarchii wbudowanych.

### <a name="using-inline-hierarchy-labels"></a>Używanie etykiet hierarchii wbudowanych
Teraz przyjrzyjmy się innemu wykresowi — z danymi o hierarchii nieformalnej. Poniższa wizualizacja przedstawia wykres słupkowy z danymi kwoty sprzedaży **Sales Amount**, gdzie osią jest *Color*. W tych danych osie *Color* (Kolor) i *Class* (Klasa) tworzą hierarchię nieformalną. W tym miejscu można ponownie wybrać polecenie *Rozwiń wszystko*, aby przejść do szczegółów hierarchii.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_7.png)

Wybranie polecenia **Rozwiń wszystko** powoduje pokazanie następnego poziomu i wyświetlenie w tekście etykiet hierarchii. Domyślnie hierarchie wbudowane są sortowane według wartości miary — w tym przypadku jest to wartość **SalesAmount**. Po włączeniu etykiet hierarchii wbudowanych można posortować te dane także według hierarchii, wybierając wielokropek w prawym górnym rogu (**...**), a następnie wybierając pozycję **Sortuj według > Color Class**, jak pokazano na poniższej ilustracji.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_8.png)

Po wybraniu opcji **Color Class** dane są sortowane według wyboru hierarchii nieformalnej, jak pokazano na poniższej ilustracji.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_9.png)

> [!NOTE]
> Funkcja etykiet hierarchii wbudowanych nie umożliwia jeszcze sortowania wbudowanej hierarchii czasu według wartości — jest ona sortowana tylko według kolejności hierarchii.
> 
> 

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Istnieje możliwość, że wizualizacja zostanie zablokowana w stanie rozwiniętego poziomu hierarchii wbudowanej. Czasami może się zdarzyć, że wizualizacja zostanie zablokowana w trybie, w którym została rozwinięta. W taki przypadku zwijanie szczegółów nie działa. Może się to stać po wykonaniu następujących czynności (rozwiązanie tego problemu znajduje się *poniżej* tych czynności):

Czynności, które mogą spowodować zablokowanie wizualizacji w stanie rozwiniętym:

1. Włączasz funkcję **etykiety hierarchii wbudowanych**
2. Tworzysz wizualizacje z hierarchiami
3. Używasz polecenia **Rozwiń wszystko** i zapisujesz plik
4. Następnie *wyłączasz* funkcję **etykiety hierarchii wbudowanych** i ponownie uruchamiasz program Power BI Desktop
5. Następnie ponownie otwierasz plik

Jeśli wykonasz te czynności i wizualizacje zostaną zablokowane w trybie rozwiniętym, możesz skorzystać z poniższej procedury, aby rozwiązać ten problem:

1. Włącz ponownie funkcję **etykiety hierarchii wbudowanych** i ponownie uruchom program Power BI Desktop
2. Otwórz ponownie plik i zwiń szczegóły zablokowanych wizualizacji
3. Zapisz plik
4. Wyłącz funkcję **etykiety hierarchii wbudowanych** i ponownie uruchom program Power BI Desktop
5. Otwórz ponownie plik

Możesz także usunąć swoją wizualizację i utworzyć ją od nowa.

