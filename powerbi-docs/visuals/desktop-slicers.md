---
title: Korzystanie z fragmentatorów w programie Power BI Desktop
description: Fragmentatory w programie Power BI Desktop służą do filtrowania, wyróżniania i dostosowywania raportów
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: df4afe91de955eabfba6eeea9022cc5f9475cc33
ms.sourcegitcommit: b8461c1876bfe47bf71c87c7820266993f82c0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2018
ms.locfileid: "49336857"
---
# <a name="using-slicers-power-bi-desktop"></a>Korzystanie z fragmentatorów w programie Power BI Desktop

**Fragmentator** w programie **Power BI Desktop** umożliwia filtrowanie wyników wizualizacji na stronie raportu. Przy użyciu fragmentatorów można łatwo dostosować filtr, który jest stosowany przez interakcję z samym fragmentatorem. Można również określić opcje wyświetlania fragmentatora i interakcji z nim. Na poniższej ilustracji przedstawiono fragmentator z widoczną listą rozwijaną *typu*. 

![fragmentatory w programie Desktop](./media/desktop-slicers/desktop-slicers_01.png)

Fragmentator może być wyświetlany w oparciu o jeden z następujących typów:

* Lista
* Lista rozwijana
* Między
* Mniejsze niż lub równe
* Większe niż lub równe

Możesz dodać fragmentator do raportu, klikając wizualizację **fragmentatora** w okienku **Wizualizacje**.

![typ wizualizacji fragmentatora](./media/desktop-slicers/desktop-slicers_02.png)

Fragmentatory w programie **Power BI Desktop** oraz w **usłudze Power BI** działają w podobny sposób. Aby zapoznać się z artykułem dotyczącym używania fragmentatorów, zobacz [Fragmentatory w usłudze Power BI](power-bi-visualization-slicers.md).

## <a name="synchronize-slicers-across-report-pages"></a>Synchronizowanie fragmentatorów na stronach raportu

W programie **Power BI Desktop** można zsynchronizować fragmentatory na wielu stronach raportu. Aby zsynchronizować fragmentatory, w okienku **Widok** na wstążce wybierz pozycję **Synchronizuj fragmentatory**. W przypadku synchronizacji fragmentatorów zostaje wyświetlone okienko **Synchronizuj fragmentatory**, jak pokazano na poniższej ilustracji.

![pokazuje okienko Synchronizuj fragmentatory](./media/desktop-slicers/desktop-slicers_03.png)

W okienku **Synchronizuj fragmentatory** można określić sposób synchronizacji fragmentatorów na stronach raportu. Można wskazać, czy każdy fragmentator powinien zostać **zastosowany** do każdej strony raportu oraz czy powinien być **widoczny** na każdej stronie raportu.

Na przykład możesz umieścić fragmentator na **stronie 2** raportu, zgodnie z ilustracją poniżej. Następnie możesz określić, czy fragmentator ma być *zastosowany* do każdej wybranej strony i czy powinien być *widoczny* na każdej wybranej stronie raportu. Dla każdego fragmentatora można użyć dowolnej kombinacji opcji. 

![fragmentatory synchronizacji](./media/desktop-slicers/desktop-slicers_04.png)

Użycie linku **Dodaj do wszystkich** w okienku powoduje zastosowanie wybranego fragmentatora do wszystkich stron raportu.


Należy pamiętać, że opcje widoczne w okienku **Synchronizuj fragmentatory** dotyczą tylko *wybranego fragmentatora*. Możesz zastosować wiele fragmentatorów do różnych stron i za pomocą okienka zdefiniować sposób zastosowania poszczególnych fragmentatorów do rozmaitych stron raportu. 

Chociaż wybór fragmentatorów może podlegać synchronizacji, inne wybrane opcje dotyczące np. stylów, edycji i usuwania *nie* są synchronizowane. 

## <a name="advanced-options-for-slicers"></a>Zaawansowane opcje fragmentatorów

Do kolekcji fragmentatorów można także zastosować **nazwę grupy**, korzystając z sekcji **Opcje zaawansowane** okienka **Synchronizuj fragmentatory**. Pozwoli to synchronizować na wszystkich stronach fragmentatory należące do tej samej grupy. 

![nazwa grupy dla fragmentatorów](./media/desktop-slicers/desktop-slicers_05.png)

Ta funkcja umożliwia utworzenie niestandardowej grupy fragmentatorów w celu ich synchronizacji. Podana jest nazwa domyślna, ale można użyć dowolnej nazwy. 

Nazwa grupy zapewnia dodatkową elastyczność podczas pracy z fragmentatorami. Możesz utworzyć oddzielne grupy, aby synchronizować fragmentatory używające tego samego pola, lub umieścić fragmentatory, które używają różnych pól, w tej samej grupie. 

## <a name="how-filtering-affects-selection-in-slicers"></a>Jak filtrowanie wpływa na wybór we fragmentatorach

W przypadku dokonania wyboru we fragmentatorze, a następnie zastosowania filtra, który normalnie spowodowałby usunięcie wybranego elementu, pozostaje on w dolnej części listy elementów we fragmentatorze. Jeśli filtr zostanie usunięty, wybór we fragmentatorze będzie nadal obowiązywać. Należy pamiętać, że jeśli usuniesz wybór elementu we fragmentatorze, zniknie on z listy.

![zachowany wybór we fragmentatorze](./media/desktop-slicers/retained-selection-in-slicers.gif)


## <a name="next-steps"></a>Następne kroki

Może zainteresują Cię również następujące artykuły:

* [Fragmentatory w usłudze Power BI](power-bi-visualization-slicers.md)
* [Używanie fragmentatora zakresu liczbowego w programie Power BI Desktop](../desktop-slicer-numeric-range.md)
* [Używanie fragmentatora i filtru dat względnych w programie Power BI Desktop](desktop-slicer-filter-date-range.md)

