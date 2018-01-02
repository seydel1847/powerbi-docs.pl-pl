---
title: "Używanie przeglądania szczegółowego w programie Power BI Desktop"
description: "Dowiedz się, jak przechodzić do szczegółowych danych na nowej stronie raportu w programie Power BI Desktop"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: c4482b8a8b7510b54b317ef9731057a52501d47c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Używanie przeglądania szczegółowego w programie Power BI Desktop
**Przeglądanie szczegółowe** w programie **Power BI Desktop** umożliwia utworzenie strony w raporcie, która koncentruje się na określonej jednostce — takiej jak dostawca, klient lub producent. Dzięki tej skoncentrowanej stronie użytkownicy mogą kliknąć prawym przyciskiem myszy punkt danych na innej stronie raportu i użyć przeglądania szczegółowego, aby przejść do tej skoncentrowanej strony w celu uzyskania szczegółów przefiltrowanych do danego kontekstu.

![](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Korzystanie z przeglądania szczegółowego
Aby używać **przeglądania szczegółowego**, utwórz stronę raportu zawierającą wizualizacje, które chcesz zobaczyć, dotyczące typu jednostki, dla którego zapewnisz przeglądanie szczegółowe. Jeśli na przykład chcesz dostarczyć przeglądanie szczegółowe dla producentów, możesz utworzyć stronę przeglądania szczegółowego z wizualizacjami przedstawiającymi sprzedaż całkowitą, sumę wysłanych jednostek, sprzedaż według kategorii, sprzedaż według regionu i tak dalej. W ten sposób, gdy przejdziesz do szczegółów znajdujących się na tej stronie, wizualizacje będą dotyczyć producenta, który został kliknięty i dla którego wybrano przeglądanie szczegółowe.

Następnie na tej stronie przeglądania szczegółowego w sekcji **Pola** okienka **Wizualizacje** przeciągnij pole, którego szczegóły chcesz przeglądać, do obszaru **Filtry przeglądania szczegółowego**.

![](media/desktop-drillthrough/drillthrough_02.png)

Po dodaniu pola do obszaru **Filtry przeglądania szczegółowego** program **Power BI Desktop** automatycznie utworzy wizualizację przycisku *wstecz*. Ta wizualizacja stanie się przyciskiem w opublikowanych raportach i umożliwi użytkownikom korzystającym z raportu w **usłudze Power BI** łatwy powrót do strony raportu, z której przyszli (jest to strona, na której została wybrana opcja przeglądania szczegółowego).

![](media/desktop-drillthrough/drillthrough_03.png)

Przycisk *wstecz* jest obrazem, dlatego możesz zamienić obraz tej wizualizacji na inny dowolny obraz, i nadal będzie on działać poprawnie jako przycisk umożliwiający użytkownikom raportu powrót do ich oryginalnej strony. Aby użyć własnego obrazu dla przycisku wstecz, umieść wizualizację obrazu na stronie przeglądania szczegółowego, a następnie wybierz tę wizualizację i umieść suwak *Przycisk wstecz* na pozycji Włączone. Dzięki temu Twój obraz będzie działać jako przycisk *wstecz*.

![](media/desktop-drillthrough/drillthrough_05.png)

Gdy strona **przeglądania szczegółowego** będzie gotowa, kiedy użytkownik kliknie prawym przyciskiem myszy punkt danych w raporcie, który używa pola umieszczonego w obszarze **Filtry przeglądania szczegółowego** na stronie przeglądania szczegółowego, zostanie wyświetlone menu kontekstowe umożliwiające użytkownikowi przejście do szczegółów znajdujących się na tej stronie.

![](media/desktop-drillthrough/drillthrough_04.png)

Po wybraniu opcji przeglądania szczegółowego strona jest filtrowana w celu wyświetlenia informacji na temat punktu danych, który kliknięto prawym przyciskiem myszy. Jeśli na przykład użytkownik kliknie prawym przyciskiem myszy punkt danych firmy Contoso (producent) i wybierze przeglądanie szczegółowe, strona przeglądania szczegółowego, do której przejdzie użytkownik, będzie filtrowana w celu wyświetlenia informacji o firmie Contoso.

> [!NOTE]
> Tylko pole uwzględnione w obszarze **Filtry przeglądania szczegółowego** zostanie przekazane do strony raportu szczegółowego. Żadne inne informacje kontekstowe nie są przekazywane.
> 
> 

To wszystko na temat używania **przeglądania szczegółowego** w raportach. Jest to doskonały sposób wyświetlania rozszerzonych informacji na temat jednostki wybranej dla filtru przeglądania szczegółowego.

