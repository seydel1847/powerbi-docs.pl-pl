---
title: Używanie motywów pulpitu nawigacyjnego w usłudze Power BI
description: Dowiedz się, jak używać niestandardowej palety kolorów i stosować ją do całego pulpitu nawigacyjnego w usłudze Power BI
author: mihart
manager: annbe
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/22/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 25bd28db7b31921d5f1a02ae72cee47207134f2a
ms.sourcegitcommit: aed348a2d0025f7f40f2196254993f6aba5db7d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43241481"
---
# <a name="use-dashboard-themes-in-power-bi-service"></a>Używanie motywów pulpitu nawigacyjnego w usłudze Power BI
**Motywy pulpitu nawigacyjnego** umożliwiają zastosowanie motywu kolorystycznego — kolorów firmowych, okolicznościowych lub innego dowolnego motywu kolorystycznego — do całego pulpitu nawigacyjnego. Zastosowanie **motywu pulpitu nawigacyjnego** spowoduje, że kolory tego motywu będą używane we wszystkich wizualizacjach na pulpicie nawigacyjnym (z kilkoma wyjątkami opisanymi w dalszej części tego artykułu).

![przykładowy pulpit nawigacyjny z motywem](media/service-dashboard-themes/power-bi-full-dashboard-theme.png)

Zmienianie kolorów wizualizacji raportu na pulpicie nawigacyjnym nie będzie wpływać na wizualizacje w raporcie. Ponadto jeśli przypinasz kafelki z raportu, który ma już [zastosowany motyw raportu](desktop-report-themes.md), możesz zachować bieżący motyw lub użyć motywu pulpitu nawigacyjnego.


## <a name="prerequisites"></a>Wymagania wstępne
* Aby z tego skorzystać, otwórz [pulpit nawigacyjny przykładu Sales and Marketing](sample-datasets.md).


## <a name="how-dashboard-themes-work"></a>Jak działają motywy pulpitu nawigacyjnego
Aby rozpocząć pracę, otwórz utworzony pulpit nawigacyjny (lub pulpit, w przypadku którego masz uprawnienia do edycji), który chcesz dostosować. Wybierz wielokropek (...), a następnie wybierz pozycję **Motyw pulpitu nawigacyjnego**. 

![opcja motywu pulpitu nawigacyjnego](media/service-dashboard-themes/power-bi-dashboard-theme.png)

W wyświetlonym okienku nawigacyjnym wybierz jeden ze wstępnie utworzonych motywów.  W poniższym przykładzie wybraliśmy motyw **Ciemny**.

![Wybrana opcja Jasny](media/service-dashboard-themes/power-bi-theme-menu.png)

![Zastosowana opcja Ciemny](media/service-dashboard-themes/power-bi-theme-dark.png)

## <a name="create-a-custom-theme"></a>Tworzenie motywu niestandardowego

Domyślny motyw pulpitów nawigacyjnych usługi Power BI to **Jasny**. Aby dostosować kolory lub utworzyć własny motyw, wybierz pozycję **Niestandardowy** z listy rozwijanej. 

![Wybieranie pozycji Niestandardowy z listy rozwijanej](media/service-dashboard-themes/power-bi-theme-custom.png)

Do tworzenia własnych motywów pulpitu nawigacyjnego należy użyć opcji niestandardowych. Przy dodawaniu obrazu tła zaleca się użycie obrazu o rozdzielczości co najmniej 1920 x 1080 pikseli. Aby użyć obrazu jako tła, przekaż obraz do publicznej witryny internetowej, skopiuj adres URL i wklej go w polu **Adres URL obrazu**. 

### <a name="using-json-themes"></a>Korzystanie z motywów JSON
Motyw niestandardowy można także utworzyć, przekazując plik JSON zawierający ustawienia wszystkich kolorów do użycia na pulpicie nawigacyjnym. W programie Power BI Desktop twórcy raportu używają plików JSON do [tworzenia motywów dla raportów](desktop-report-themes.md). Te same pliki JSON można przekazywać do pulpitów nawigacyjnych. Można też znaleźć i przekazać pliki JSON ze [strony galerii motywów](https://community.powerbi.com/t5/Themes-Gallery/bd-p/ThemesGallery) dostępnej w społeczności usługi Power BI 

![Witryna galerii motywów](media/service-dashboard-themes/power-bi-theme-gallery.png)

Można również zapisać motyw niestandardowy jako plik JSON, a następnie udostępnić go innym twórcom pulpitów nawigacyjnych. 

### <a name="use-a-theme-from-the-theme-gallery"></a>Używanie motywu z galerii motywów

Podobnie jak w przypadku opcji wbudowanych i niestandardowych, po przekazaniu motywu kolory zostaną automatycznie zastosowane do wszystkich kafelków na pulpicie nawigacyjnym. 

1. Najedź kursorem na motyw i wybierz pozycję **Wyświetl raport**.

    ![Wyświetlanie raportu](media/service-dashboard-themes/power-bi-choose-theme.png)

2. Przewiń w dół i znajdź link do pliku JSON.  Wybierz ikonę pobierania i zapisz plik.

    ![Plik JSON o nazwie Spring Day](media/service-dashboard-themes/power-bi-theme-json.png)

3. Po powrocie do usługi Power BI w oknie niestandardowego motywu pulpitu nawigacyjnego wybierz pozycję **Przekaż motyw JSON**.

    ![Przekazywanie pliku JSON](media/service-dashboard-themes/power-bi-upload-theme.png)

4. Przejdź do lokalizacji, w której zapisano motyw pliku JSON, i wybierz pozycję **Otwórz**.

5. Na stronie motywu pulpitu nawigacyjnego wybierz pozycję **Zapisz**. Nowy motyw zostanie zastosowany do pulpitu nawigacyjnego.

    ![zastosowany nowy motyw](media/service-dashboard-themes/power-bi-json.png)

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia

* Jeśli raport używa innego motywu niż pulpit nawigacyjny, możesz kontrolować, czy wizualizacja zachowuje bieżący motyw, czy też używa motywu pulpitu nawigacyjnego w celu ujednolicenia wyglądu wizualizacji pochodzących z różnych źródeł. Aby podczas przypinania kafelka do pulpitu nawigacyjnego zachować motyw raportu, wybierz pozycję **Zachowaj bieżący motyw**. W wizualizacji na pulpicie nawigacyjnym zostanie zachowany motyw raportu, w tym ustawienia przezroczystości. 

    Opcje obszaru **Motyw kafelków** są widoczne tylko w przypadku utworzenia raportu w programie Power BI Desktop, [dodania motywu raportu](desktop-report-themes.md) i opublikowania raportu w usłudze Power BI. 

    ![Wybrana pozycja Zachowaj bieżący motyw](media/service-dashboard-themes/power-bi-keep-current.png)

    Spróbuj ponownie przypiąć kafelek i wybrać pozycję **Użyj motywu pulpitu nawigacyjnego**.

    ![Użyj motywu docelowego](media/service-dashboard-themes/power-bi-use-destination.png)

* Motywów pulpitu nawigacyjnego nie można stosować do przypiętych stron dynamicznych raportu, kafelków elementów iframe, kafelków usługi SSRS, kafelków skoroszytów ani obrazów.
* Motywy pulpitu nawigacyjnego mogą być wyświetlane na urządzeniach przenośnych, ale tworzenie motywu pulpitu nawigacyjnego jest możliwe tylko w usłudze Power BI. 
* Motywy niestandardowe pulpitu nawigacyjnego działają jedynie w przypadku kafelków przypiętych z raportów. 

