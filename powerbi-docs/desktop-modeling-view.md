---
title: Używanie widoku modelowania w programie Power BI Desktop (wersja zapoznawcza)
description: Użyj widoku modelowania, aby zobaczyć złożone zestawy danych w formacie wizualnym w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/13/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 84e2bc663a4e3912608279c7315bc494b3c9844a
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296529"
---
# <a name="modeling-view-in-power-bi-desktop-preview"></a>Widok modelowania w programie Power BI Desktop (wersja zapoznawcza)

Za pomocą **widoku modelowania** w programie **Power BI Desktop**, można przeglądać złożone zestawy danych, które zawierają wiele tabel, oraz pracować nad nimi. W widoku modelowania można wykonać następujące czynności:


## <a name="enabling-the-modeling-view-preview-feature"></a>Włączanie funkcji widoku modelowania (wersja zapoznawcza)

Funkcja widoku modelowania jest dostępna w wersji zapoznawczej i trzeba ją włączyć w programie **Power BI Desktop**. Aby włączyć widok modelowania, wybierz **Plik > Opcje i Ustawienia > Opcje > Funkcje wersji zapoznawczej**, a następnie zaznacz pole wyboru **Widok modelowania**, jak pokazano na poniższej ilustracji.

![Włączanie funkcji widoku modelowania (wersja zapoznawcza) w programie Power BI Desktop](media/desktop-modeling-view/modeling-view_01.png)

Pojawi się monit, że należy ponownie uruchomić program **Power BI Desktop**, aby funkcja w wersji zapoznawczej została włączona. 

![Ponownie uruchamianie programu Power BI Desktop, aby włączyć funkcje w wersji zapoznawczej](media/desktop-modeling-view/modeling-view_01b.png)

## <a name="using-modeling-view"></a>Używanie widoku modelowania

Aby uzyskać dostęp do widoku modelowania, wybierz ikonę widoku modelowania w lewej części programu **Power BI Desktop**, jak pokazano na poniższej ilustracji.

![Ikona widoku modelowania w programie Power BI Desktop](media/desktop-modeling-view/modeling-view_02.png)

## <a name="creating-separate-diagrams"></a>Tworzenie oddzielnych diagramów

Przy użyciu widoku modelowania można utworzyć diagramy modelu, które zawierają tylko podzbiór tabel w modelu. Może to ułatwić dostarczanie bardziej czytelnego widoku tabel, nad którymi chcesz pracować, a także uprościć pracę nad złożonymi zestawami danych. Aby utworzyć nowy diagram dotyczący tylko podzbioru tabel, kliknij znak **+** obok karty **Wszystkie tabele** u dołu okna programu Power BI Desktop.

![Aby utworzyć nowy diagram, kliknij znak + w sekcji kart](media/desktop-modeling-view/modeling-view_03.png)

Następnie możesz przeciągnąć tabelę z listy **Pola** na powierzchnię diagramu. Kliknij prawym przyciskiem myszy tabelę, a następnie wybierz pozycję **Dodaj powiązane tabele** z wyświetlonego menu.

![Kliknij prawym przyciskiem myszy tabelę i wybierz opcję Dodaj powiązane tabele](media/desktop-modeling-view/modeling-view_04.png)

Kiedy to zrobisz, tabele powiązane z oryginalną tabelą zostaną wyświetlone na nowym diagramie. Na poniższej ilustracji przedstawiono sposób wyświetlania powiązanych tabel po wybraniu opcji menu **Dodaj powiązane tabele**.

![Pokazywanie powiązanych tabel](media/desktop-modeling-view/modeling-view_05.png)

## <a name="setting-common-properties"></a>Ustawianie typowych właściwości

Można jednocześnie wybrać wiele obiektów w widoku modelowania, przytrzymując naciśnięty klawisz **CTRL** i klikając wiele tabel. Po wybraniu wielu tabel stają się one wyróżnione w widoku modelowania. W przypadku wyróżnienia wielu tabel zmiany zastosowane w okienku **Właściwości** są stosowane do wszystkich wybranych tabel.

Na przykład, aby zmienić [tryb przechowywania](desktop-storage-mode.md) wielu tabel w widoku diagramu, można przytrzymać naciśnięty klawisz **CTRL**, wybrać tabele, a następnie zmienić ustawienie trybu przechowywania w okienku **Właściwości**.

![Wybieranie wielu tabel z przytrzymanym naciśniętym klawiszem CTRL, a następnie ustawianie wspólnych właściwości dla wszystkich wybranych tabel](media/desktop-modeling-view/modeling-view_06.png)


## <a name="next-steps"></a>Następne kroki

W poniższych artykułach opisano dokładniej modele danych oraz szczegóły trybu DirectQuery.

* [Agregacje w programie Power BI Desktop (wersja zapoznawcza)](desktop-aggregations.md)
* [Modele złożone w programie Power BI Desktop (wersja zapoznawcza)](desktop-composite-models.md)
* [Tryb przechowywania w programie Power BI Desktop (wersja zapoznawcza)](desktop-storage-mode.md)
* [Relacje wiele-do-wielu w programie Power BI Desktop (wersja zapoznawcza)](desktop-many-to-many-relationships.md)


Artykuły dotyczące trybu DirectQuery:

* [Używanie trybu DirectQuery w usłudze Power BI](desktop-directquery-about.md)
* [Źródła danych obsługiwane przez tryb DirectQuery w usłudze Power BI](desktop-directquery-data-sources.md)
