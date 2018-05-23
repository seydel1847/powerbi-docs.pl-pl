---
title: Używanie zewnętrznego środowiska IDE języka R z usługą Power BI
description: W usłudze Power BI możesz uruchomić zewnętrzne środowisko IDE i korzystać z niego
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c51d89979ccf6791e69a7cdd457004b065b9d537
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="use-an-external-r-ide-with-power-bi"></a>Używanie zewnętrznego środowiska IDE języka R z usługą Power BI
W programie **Power BI Desktop** możesz za pomocą zewnętrznego środowiska IDE (zintegrowanego środowiska programistycznego) języka R tworzyć i dostosowywać skrypty języka R, a następnie używać tych skryptów w usłudze Power BI.

![](media/desktop-r-ide/r-ide_1a.png)

## <a name="enable-an-external-r-ide"></a>Włączanie zewnętrznego środowiska IDE języka R
Wcześniej do tworzenia i uruchamiania skryptów języka R trzeba było używać edytora skryptów języka R w programie **Power BI Desktop**. W tym wydaniu możesz uruchomić zewnętrzne środowisko IDE języka R z poziomu programu **Power BI Desktop**, aby automatycznie zaimportować i wyświetlić dane w środowisku IDE języka R. W zewnętrznym środowisku IDE języka R możesz zmodyfikować skrypt, a następnie wkleić go z powrotem do programu **Power BI Desktop** w celu utworzenia wizualizacji i raportów usługi Power BI.

Począwszy od wydania programu **Power BI Desktop** z września 2016 r. (wersja 2.39.4526.362), można określić, jakie środowisko IDE języka R ma być używane, a także spowodować jego automatyczne uruchamianie z poziomu programu **Power BI Desktop**.

### <a name="requirements"></a>Wymagania
Aby używać tej funkcji, musisz zainstalować **środowisko IDE języka R** na komputerze lokalnym. Program **Power BI Desktop** nie zawiera, nie wdraża ani nie instaluje aparatu R, dlatego musisz oddzielnie zainstalować język **R** na komputerze lokalnym. Korzystając z następujących opcji, możesz wybrać, które środowisko IDE języka R ma być używane:

* Możesz zainstalować ulubione środowisko IDE języka R. Wiele z nich jest dostępnych bezpłatnie, na przykład [strona pobierania Revolution Open](https://mran.revolutionanalytics.com/download/) i repozytorium [CRAN Repository](https://cran.r-project.org/bin/windows/base/).
* Program **Power BI Desktop** obsługuje również program [R Studio](https://www.rstudio.com/) i program **Visual Studio 2015** z edytorami [*R Tools for Visual Studio*](https://beta.visualstudio.com/vs/rtvs/).
* Wykonując jedną z następujących czynności, możesz również zainstalować inne środowisko IDE języka R i spowodować, że program **Power BI Desktop** będzie uruchamiał to **środowisko IDE języka R**:
  
  * Możesz skojarzyć pliki **.R** z zewnętrznym środowiskiem IDE, które ma być uruchamiane przez program **Power BI Desktop**.
  * Możesz określić plik .exe, który powinien być uruchamiany przez program **Power BI Desktop**, wybierając pozycję *Inne* w sekcji **Opcje skryptu języka R** okna dialogowego **Opcje**. Okno dialogowe **Opcje** możesz wyświetlić, wybierając pozycję **Plik > Opcje i ustawienia > Opcje**.
    
    ![](media/desktop-r-ide/r-ide_1b.png)

Jeśli masz zainstalowanych wiele środowisk IDE języka R, możesz określić, które z nich będzie uruchamiane, wybierając je z listy rozwijanej *Wykryte środowiska IDE języka R* w oknie dialogowym **Opcje**.

Domyślnie program **Power BI Desktop** uruchamia program **R Studio** jako zewnętrzne środowisko IDE języka R, jeśli jest on zainstalowany na komputerze lokalnym. Jeśli program **R Studio** nie jest zainstalowany, a masz program **Visual Studio 2015** z edytorami **R Tools for Visual Studio**, będzie on uruchamiany zamiast R Studio. Jeśli żadne z tych środowisk IDE języka R nie jest zainstalowane, będzie uruchamiana aplikacja skojarzona z plikami **.R**.

Natomiast jeśli nie istnieje żadne skojarzenie plików **.R**, w sekcji *Przejdź do preferowanego środowiska IDE języka R* okna dialogowego **Opcje** możesz określić ścieżkę do niestandardowego środowiska IDE. Inne środowisko IDE języka R możesz również uruchomić, wybierając ikonę koła zębatego **Ustawienia** obok ikony strzałki **Uruchom środowisko IDE języka R** w programie **Power BI Desktop**.

## <a name="launch-an-r-ide-from-power-bi-desktop"></a>Uruchamianie środowiska IDE języka R z poziomu programu Power BI Desktop
Aby uruchomić środowisko IDE języka R z poziomu programu **Power BI Desktop**, wykonaj następujące kroki:

1. Załaduj dane do programu **Power BI Desktop**.
2. W okienku **Pola** wybierz niektóre pola, z którymi chcesz pracować. Jeśli nie zostały jeszcze włączone wizualizacje skryptów, zostanie wyświetlony monit, aby to zrobić.
   
   ![](media/desktop-r-ide/r-ide_3.png)
3. Gdy wizualizacje skryptów są włączone, w okienku **Wizualizacje** możesz wybrać wizualizację języka R, co spowoduje utworzenie pustej wizualizacji języka R gotowej do wyświetlenia wyników działania skryptu. Zostanie również wyświetlone okienko **Edytor skryptów języka R**.
   
   ![](media/desktop-r-ide/r-ide_4.png)
4. Teraz możesz wybrać pola, których chcesz użyć w skrypcie języka R. Gdy wybierzesz pola, **Edytor skryptów języka R** automatycznie utworzy kod skryptu na podstawie wybranych pól. Możesz utworzyć (lub wkleić) skrypt języka R bezpośrednio w okienku **Edytor skryptów języka R** lub pozostawić je puste.
   
   ![](media/desktop-r-ide/r-ide_5.png)
   
   > [!NOTE]
   > Domyślny typ agregacji ustawiony dla wizualizacji języka R to *Nie sumuj*.
   > 
   > 
5. Teraz możesz uruchamiać środowisko IDE języka R bezpośrednio z poziomu programu **Power BI Desktop**. Naciśnij przycisk **Uruchom środowisko IDE języka R** znajdujący się z prawej strony paska tytułu **Edytora skryptów języka R**, jak pokazano poniżej.
   
   ![](media/desktop-r-ide/r-ide_6.png)
6. Określone przez Ciebie środowisko IDE języka R zostanie uruchomione przez program Power BI Desktop, jak pokazano na poniższej ilustracji (na tej ilustracji domyślnym środowiskiem IDE języka R jest **RStudio**).
   
   ![](media/desktop-r-ide/r-ide_7.png)
   
   > [!NOTE]
   > Program **Power BI Desktop** dodaje pierwsze trzy wiersze skryptu, aby po uruchomieniu skryptu można było zaimportować dane z programu **Power BI Desktop**.
   > 
   > 
7. Dowolny skrypt utworzony w **okienku edytora skryptów języka R** programu **Power BI Desktop** zaczyna się od wiersza 4 w środowisku IDE języka R. W tym momencie możesz utworzyć skrypt języka R w środowisku IDE języka R. Po ukończeniu skryptu języka R w środowisku IDE języka R musisz go skopiować i wkleić z powrotem do okienka **Edytor skryptów języka R** w programie **Power BI Desktop**, *z wyłączeniem* pierwszych trzech wierszy skryptu, które zostały wygenerowane automatycznie przez program **Power BI Desktop**. Nie kopiuj pierwszych trzech wierszy skryptu z powrotem do programu **Power BI Desktop**. Służą one wyłącznie do zaimportowania danych z programu **Power BI Desktop** do środowiska IDE języka R.

### <a name="known-limitations"></a>Znane ograniczenia
Uruchamianie środowiska IDE języka R bezpośrednio z poziomu programu Power BI Desktop ma kilka ograniczeń:

* Automatyczne eksportowanie skryptu ze środowiska IDE języka R do programu **Power BI Desktop** nie jest obsługiwane.
* Edytor **R Client** (RGui.exe) nie jest obsługiwany, ponieważ nie obsługuje on otwierania plików.

## <a name="next-steps"></a>Następne kroki
Spójrz na następujące informacje dodatkowe na temat języka R w usłudze Power BI.

* [Uruchamianie skryptów języka R w programie Power BI Desktop](desktop-r-scripts.md)
* [Tworzenie wizualizacji usługi Power BI przy użyciu języka R](desktop-r-visuals.md)

