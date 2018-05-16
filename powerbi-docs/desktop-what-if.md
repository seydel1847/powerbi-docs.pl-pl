---
title: Używanie parametrów analizy warunkowej w celu wizualizacji zmiennych w usłudze Power BI Desktop
description: Tworzenie własnej zmiennej analizy warunkowej w celu wyobrażenia i wizualizacji zmiennych w raportach usługi Power BI
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
ms.openlocfilehash: 6b1289c1764514ce975c24bf6a93c5a66d2cc95a
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="create-and-use-a-what-if-parameter-to-visualize-variables-in-power-bi-desktop"></a>Tworzenie i używanie parametrów analizy warunkowej w celu wizualizacji zmiennych w usłudze Power BI Desktop
Wersja programu **Power BI Desktop** wydana w sierpniu 2017 r. umożliwia tworzenie zmiennych **analizy warunkowej** dla raportów, używanie zmiennych jako fragmentatorów, a co za tym idzie, wizualizowanie i szacowanie różnych wartości kluczowych w raportach.

![](media/desktop-what-if/what-if_01.png)

Parametr **analizy warunkowej** znajduje się na karcie **Modelowanie** w programie **Power BI Desktop**. Po jego wybraniu zostanie wyświetlone okno dialogowe, w którym można skonfigurować parametr.

## <a name="creating-a-what-if-parameter"></a>Tworzenie parametru analizy warunkowej
Aby utworzyć parametr **analizy warunkowej**, wybierz przycisk **Analiza warunkowa** na karcie **Modelowanie** w programie **Power BI Desktop**. Poniższa ilustracja przedstawia utworzony parametr o nazwie *Discount percentage* (Procent rabatu) z typem danych *Decimal number* (Liczba dziesiętna). Wartość *Minimum* jest ustawiona na zero, a wartość *Maximum* na 0,50 (pięćdziesiąt procent). Wartość *Increment* (Przyrost) ustawiono na 0,05 (5 procent). O tyle zostanie dostosowany parametr po użyciu w raporcie.

![](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> W przypadku liczb dziesiętnych upewnij się, że poprzedzasz je cyfrą zero: na przykład 0,50, a nie ,50. W przeciwnym razie liczba będzie nieprawidłowa, a wybranie przycisku **OK** nie będzie możliwe.
> 
> 

Dla wygody pole wyboru **Dodaj fragmentator do tej strony** automatycznie umieszcza fragmentator wraz z parametrem **analizy warunkowej** na bieżącej stronie raportu.

![](media/desktop-what-if/what-if_03.png)

Podczas tworzenia parametru **analizy warunkowej** oprócz parametru tworzona jest także miara, która służy do wizualizacji bieżącej wartości parametru **analizy warunkowej**.

![](media/desktop-what-if/what-if_04.png)

Co istotne, po utworzeniu parametru **analizy warunkowej** zarówno ten parametr, jak i miara stają się częścią modelu. Są więc dostępne w raporcie i można ich użyć na innych stronach raportu. Ponieważ są one częścią modelu, można usunąć fragmentator ze strony raportu. Możesz także później przeciągnąć parametr **analizy warunkowej** z listy **Pola** na kanwę raportu (zamieniając wizualizację na fragmentator), aby łatwo przywrócić parametr do raportu.

## <a name="using-a-what-if-parameter"></a>Korzystanie z parametru analizy warunkowej
Utwórzmy prosty przykład z użyciem parametru **analizy warunkowej**. W poprzedniej sekcji utworzyliśmy parametr **analizy warunkowej**, a teraz użyjemy go do utworzenia nowej miary, której wartość jest dostosowywana przez suwak. W tym celu tworzymy nową miarę.

![](media/desktop-what-if/what-if_05.png)

Nowa miara to po prostu łączna wartość sprzedaży z zastosowanym rabatem. Można oczywiście tworzyć interesujące, złożone miary, umożliwiające użytkownikom raportów wizualizację zmiennej parametru **analizy warunkowej**. Możesz na przykład utworzyć raport, który umożliwia sprzedawcom oszacowanie swojego wynagrodzenia w przypadku zrealizowania określonych celów sprzedażowych lub określenie zależności między większą sprzedażą a większym rabatem.

Po wpisaniu formuły miary na pasku formuły i nadaniu jej nazwy **Sales after discount** (Sprzedaż po rabacie) wyświetlone zostaną wyniki:

![](media/desktop-what-if/what-if_06.png)

Następnie tworzymy wizualizację kolumnową z parametrem *OrderDate* (Data zamówienia) na osi i wartościami *SalesAmount* (Kwota sprzedaży) oraz *Sales after discount* (Sprzedaż po rabacie), czyli nowo utworzoną miarą.

![](media/desktop-what-if/what-if_07.png)

Następnie po przeciągnięciu suwaka widzimy, że kolumna *Sales after discount* odzwierciedla kwotę sprzedaży po rabacie.

![](media/desktop-what-if/what-if_08.png)

I to już wszystko. Można użyć parametrów **analizy warunkowej** w wielu sytuacjach, aby umożliwić użytkownikom raportów zapoznanie się z różnymi scenariuszami, które tworzymy w raportach.

