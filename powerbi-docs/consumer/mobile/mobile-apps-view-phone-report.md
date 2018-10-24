---
title: Wyświetlanie raportów usługi Power BI zoptymalizowanych pod kątem telefonu
description: Dowiedz się więcej na temat korzystania ze stron raportów zoptymalizowanych pod kątem wyświetlania w aplikacjach usługi Power BI na telefonach.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 09/14/2018
ms.author: maggies
ms.openlocfilehash: 06a8d15ca894b877199f22fc6c00d4c34827d76b
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2018
ms.locfileid: "46547803"
---
# <a name="view-power-bi-reports-optimized-for-your-phone"></a>Wyświetlanie raportów usługi Power BI zoptymalizowanych pod kątem telefonu

Dotyczy:

| ![Telefon iPhone](./media/mobile-apps-view-phone-report/ios-logo-40-px.png) | ![Telefon z systemem Android](./media/mobile-apps-view-phone-report/android-logo-40-px.png) |
|:--- |:--- |
| Telefony iPhone |Telefony z systemem Android |

Podczas tworzenia raportu usługi Power BI w programie Power BI Desktop lub w usłudze możesz również [utworzyć wersję tego raportu zoptymalizowaną pod kątem wyświetlania](../../desktop-create-phone-report.md) w aplikacji Power BI na telefonie.

W takim przypadku po otwarciu raportu usługi Power BI na telefonie usługa wykrywa, czy raport został zoptymalizowany pod kątem korzystania z niego na telefonie, i automatycznie otwiera zoptymalizowany raport w widoku pionowym.

![Raport w trybie widoku pionowego](./media/mobile-apps-view-phone-report/07-power-bi-phone-report-portrait.png)

Jeśli nie jest dostępny raport zoptymalizowany pod kątem telefonu, raporty będą mimo wszystko otwierane, ale w niezoptymalizowanym widoku poziomym. Nawet jeśli raport został zoptymalizowany pod kątem telefonu, po obróceniu telefonu na bok raport zostanie otwarty w niezoptymalizowanym widoku i w oryginalnym układzie. Jeśli zoptymalizowane są tylko niektóre strony, w widoku pionowym wyświetlony zostanie komunikat informujący, że raport jest dostępny w widoku poziomym.

![Niezoptymalizowana strona raportu](./media/mobile-apps-view-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Wszystkie pozostałe funkcje raportów usługi Power BI działają w raportach zoptymalizowanych pod kątem telefonu. Dowiedz się, jakie funkcje są dostępne w:

* [Raportach na telefonach iPhone](mobile-reports-in-the-mobile-apps.md). 
* [Raportach na telefonach z systemem Android](mobile-reports-in-the-mobile-apps.md).

## <a name="filter-the-report-page-on-a-phone"></a>Filtrowanie strony raportu w telefonie
Jeśli raport zoptymalizowany pod kątem telefonu ma zdefiniowane filtry, możesz użyć tych filtrów podczas wyświetlania raportu w telefonie. W telefonie zostanie otwarty raport odfiltrowany do wartości filtrowanych w raporcie w Internecie z komunikatem informującym o aktywnych filtrach na stronie. Filtry można zmienić w telefonie.

1. Naciśnij ikonę filtru ![Ikona filtru na telefonie iPhone](./media/mobile-apps-view-phone-report/power-bi-phone-filter-icon.png) w dolnej części strony. 
2. Użyj filtrowania podstawowego lub zaawansowanego, aby wyświetlić interesujące Cię wyniki.
   
    ![Zaawansowane filtrowanie raportów usługi Power BI na telefonie](./media/mobile-apps-view-phone-report/power-bi-iphone-advanced-filter-toronto.gif)

## <a name="cross-highlight-visuals"></a>Krzyżowe wyróżnianie wizualizacji
Krzyżowe wyróżnianie wizualizacji w raportach na telefonach działa podobnie jak w usłudze Power BI i w raportach wyświetlanych na telefonach w widoku poziomym: po wybraniu danych w jednej wizualizacji wyróżniane są powiązane dane w pozostałych wizualizacjach na tej stronie.

Dowiedz się więcej na temat [filtrowania i wyróżniania w usłudze Power BI](../../power-bi-reports-filters-and-highlighting.md).

## <a name="select-visuals"></a>Wybieranie wizualizacji
W raportach na telefonach po wybraniu wizualizacji zostaje ona wyróżniona i zostaje na niej umieszczony fokus, co neutralizuje gesty wykonywane na kanwie.

Po wybraniu wizualizacji możesz na przykład przewijać wizualizację. Aby cofnąć zaznaczenie wizualizacji, po prostu dotknij dowolny obszar poza wizualizacją.

## <a name="open-visuals-in-focus-mode"></a>Otwieranie wizualizacji w trybie koncentracji uwagi
Raporty na telefonach mają także tryb koncentracji uwagi, który umożliwia powiększenie wizualizacji w celu zapoznania się z nią oraz z raportem.

* W raporcie na telefonie naciśnij ikonę wielokropka (**...**) w prawym górnym rogu wizualizacji i wybierz polecenie **Rozwiń do trybu koncentracji uwagi**.
  
    ![Rozwijanie do trybu koncentracji uwagi](././media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)

Czynności wykonane w trybie koncentracji uwagi są stosowane do kanwy raportu i odwrotnie, co umożliwia bezproblemowe korzystanie z raportu. Jeśli na przykład w wizualizacji wyróżnisz wartość, a następnie wrócisz do całego raportu, cały raport będzie filtrowany pod kątem wartości wyróżnionej w wizualizacji.

Niektóre czynności można wykonać wyłącznie w trybie koncentracji uwagi z powodu ograniczeń związanych z rozmiarem ekranu:

* **Przechodzenie do szczegółów** informacji wyświetlanych w wizualizacji. Więcej informacji na temat [przechodzenia do szczegółów i uogólniania](mobile-apps-view-phone-report.md#drill-down-in-a-visual)w raporcie na telefon znajduje się poniżej.
* **Sortowanie** wartości w wizualizacji.
* **Cofanie**: usuwanie czynności wykonanych w wizualizacji i przywracanie definicji skonfigurowanej podczas tworzenia raportu.
  
    Aby wyczyścić wszystkie czynności wykonane na wizualizacji, naciśnij ikonę wielokropka (**...**), a następnie wybierz polecenie **Cofnij**.
  
    ![Cofanie](././media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)
  
    Funkcja Cofanie jest dostępna na poziomie raportu — wówczas usuwa wszystkie czynności wykonane na wszystkich wizualizacjach — lub na poziomie wizualizacji, gdzie usuwa wszystkie czynności z wybranej wizualizacji.   

## <a name="drill-down-in-a-visual"></a>Przechodzenie do szczegółów w wizualizacji
Jeśli w wizualizacji zdefiniowano poziomy hierarchii, możesz przejść do informacji szczegółowych wyświetlonych w wizualizacji, a następnie wrócić do informacji ogólnych. Możesz dodać [możliwość przejścia do szczegółów wizualizacji](../end-user-drill.md) w usłudze Power BI lub programie Power BI Desktop. Przechodzenie do szczegółów działa w raportach usługi Power BI zoptymalizowanych pod kątem korzystania z telefonu tylko podczas wyświetlania ich na telefonie. 

1. W raporcie wyświetlonym na telefonie naciśnij ikonę wielokropka (**...**) w prawym górnym rogu, a następnie wybierz opcję **Rozwiń do trybu koncentracji uwagi**.
   
    ![Rozwijanie do trybu koncentracji uwagi](././media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)
   
    W tym przykładzie słupki pokazują wartości dla stanów.
2. Naciśnij ikonę Eksploruj ![Ikona Eksploruj](./media/mobile-apps-view-phone-report/power-bi-phone-report-explore-icon.png) w lewym dolnym rogu.
   
    ![Tryb eksplorowania](./media/mobile-apps-view-phone-report/power-bi-phone-report-explore-mode.png)
3. Naciśnij opcję **Pokaż następny poziom** lub **Rozwiń do następnego poziomu**.
   
    ![Rozwijanie do następnego poziomu](./media/mobile-apps-view-phone-report/power-bi-phone-report-expand-levels.png)
   
    Teraz słupki pokazują wartości dla miast.
   
    ![Rozwinięte poziomy](./media/mobile-apps-view-phone-report/power-bi-phone-report-expanded-levels.png)
4. Naciśnięcie strzałki w lewym górnym rogu spowoduje powrót do raportu na telefonie, w którym wartości niższego poziomu nadal będą rozwinięte.
   
    ![Nadal rozwinięte wartości niższego poziomu](./media/mobile-apps-view-phone-report/power-bi-back-to-phone-report-expanded-levels.png)
5. Aby wrócić do oryginalnego poziomu, naciśnij ponownie ikonę wielokropka (**...** ), a następnie wybierz opcję **Cofnij**.
   
    ![Cofanie](././media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)

## <a name="next-steps"></a>Następne kroki
* [Tworzenie raportów zoptymalizowanych pod kątem aplikacji Power BI na telefony](../../desktop-create-phone-report.md)
* [Tworzenie widoku pulpitu nawigacyjnego dla telefonu w usłudze Power BI](../../service-create-dashboard-mobile-phone-view.md)
* [Tworzenie elastycznych wizualizacji zoptymalizowanych pod kątem dowolnego rozmiaru](../../visuals/desktop-create-responsive-visuals.md)
* Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

