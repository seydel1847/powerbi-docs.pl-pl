---
title: Optymalizacja wizualizacji usługi Power BI pod kątem dowolnej wielkości
description: Dowiedz się, jak zoptymalizować wizualizacje w istniejących raportach w programie Power BI Desktop i usłudze Power BI na potrzeby aplikacji telefonicznych Power BI.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/13/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 1c50bcf656f967502e8bb01f7ca5184996170bed
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46566331"
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Optymalizacja wizualizacji usługi Power BI pod kątem dowolnej wielkości
Domyślnie podczas tworzenia raportu wizualizacje działają *elastycznie*: zmieniają się dynamicznie i wyświetlają maksymalną ilość danych i szczegółowych informacji niezależnie od rozmiaru ekranu. W starszych raportach można również ustawić wizualizacje tak, aby elastycznie zmieniały rozmiar.

Gdy wizualizacja zmienia rozmiar, usługa Power BI nadaje priorytet widokowi danych, na przykład usuwając dopełnienia i automatycznie przenosząc legendę na górę wizualizacji, tak aby wizualizacja dostarczała odpowiednią ilość informacji, nawet gdy się zmniejszy. Elastyczność jest szczególnie przydatna w przypadku wizualizacji w aplikacji mobilnej Power BI na telefonach.

![Elastyczna zmiana rozmiaru wizualizacji](./media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

Każda wizualizacja zawierająca osie X i Y oraz fragmentatory może elastycznie zmieniać rozmiar.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Włączanie elastyczności w programie Power BI Desktop
1. W starszych raportach programu Power BI Desktop na karcie **Widok** upewnij się, że jesteś w obszarze **Układ pulpitu**.
   
    ![Ikona Układ pulpitu](./media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Wybierz wizualizację, a następnie w okienku **Wizualizacje** wybierz sekcję **Format**.
3. Rozwiń listę **Ogólne** i przesuń suwak **Elastyczna** w położenie **Włącz**.
   
    ![Elastyczna — Włącz](././media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Teraz gdy [utworzysz raport zoptymalizowany na potrzeby telefonu](../desktop-create-phone-report.md) i dodasz tę wizualizację, będzie ona bez problemu zmieniała rozmiar.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Włączanie elastyczności w usłudze Power BI
Elastyczność wizualizacji można włączyć w starszym raporcie usługi Power BI. Musisz mieć możliwość edytowania raportu.

1. W raporcie w usłudze Power BI ([https://powerbi.com](https://powerbi.com)) wybierz pozycję **Edytuj raport**.
2. Wybierz wizualizację, a następnie w okienku **Wizualizacje** wybierz sekcję **Format**.
3. Rozwiń listę **Ogólne** i przesuń suwak **Elastyczna** w położenie **Włącz**.
   
    ![Elastyczna — Włącz](././media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Teraz gdy [utworzysz widok raportu dla telefonu](../desktop-create-phone-report.md) i dodasz tę wizualizację, będzie ona bez problemu zmieniała rozmiar.

## <a name="next-steps"></a>Następne kroki
* [Tworzenie raportów zoptymalizowanych pod kątem aplikacji Power BI na telefony](../desktop-create-phone-report.md)
* [Wyświetlanie raportów usługi Power BI zoptymalizowanych pod kątem telefonu](../consumer/mobile/mobile-apps-view-phone-report.md)
* Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

