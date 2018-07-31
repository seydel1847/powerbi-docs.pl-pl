---
title: Uruchamianie skryptów języka R w programie Power BI Desktop
description: Uruchamianie skryptów języka R w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6796de2b32061629e8f4fbcbc9b3311b5a95042d
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39327297"
---
# <a name="run-r-scripts-in-power-bi-desktop"></a>Uruchamianie skryptów języka R w programie Power BI Desktop
Skrypty języka R można uruchamiać bezpośrednio w programie **Power BI Desktop** i importować wynikowe zestawy danych bezpośrednio do modelu danych w programie Power BI Desktop.

## <a name="install-r"></a>Instalowanie języka R
Aby uruchamiać skrypty języka R w programie Power BI Desktop, musisz zainstalować **język R** na swojej maszynie lokalnej. Język **R** możesz pobrać i zainstalować bezpłatnie z wielu miejsc, w tym ze [strony pobierania Revolution Open](https://mran.revolutionanalytics.com/download/) i [repozytorium CRAN](https://cran.r-project.org/bin/windows/base/). Bieżąca wersja mechanizmu obsługi skryptów języka R w programie Power BI Desktop obsługuje znaki Unicode, a także spacje (puste znaki) w ścieżce instalacji.

## <a name="run-r-scripts"></a>Uruchamianie skryptów języka R
Wykonując kilka prostych kroków w programie Power BI Desktop, można uruchomić skrypty języka R i utworzyć model danych, na podstawie którego można z kolei tworzyć raporty i udostępniać je w usłudze Power BI. Mechanizm obsługi skryptów języka R w programie Power BI Desktop obsługuje teraz formaty liczb z separatorami dziesiętnymi (.) i przecinkami (,).

### <a name="prepare-an-r-script"></a>Przygotowywanie skryptu języka R
Aby uruchomić skrypt języka R w programie Power BI Desktop, utwórz skrypt w lokalnym środowisku programistycznym języka R i upewnij się, że działa on prawidłowo.

Aby uruchomić skrypt w programie Power BI Desktop, upewnij się, że działa on prawidłowo w niezmodyfikowanym obszarze roboczym. Oznacza to, że wszystkie pakiety i zależności muszą zostać jawnie załadowane i uruchomione. Do uruchamiania skryptów zależnych można używać polecenia *source()*.

Istnieje kilka ograniczeń dotyczących przygotowywania i uruchamiania skryptów języka R w programie Power BI Desktop:

* Importowane są tylko ramki danych, dlatego upewnij się, że dane, które chcesz zaimportować do usługi Power BI, są reprezentowane w ramce danych.
* Kolumny o typach Complex i Vector nie są importowane i są zastępowane wartościami błędów w utworzonej tabeli.
* Wartości równe N/A są przekształcane w programie Power BI Desktop na wartości NULL.
* Limit czasu działania każdego skryptu języka R to 30 minut.
* Interakcyjne wywołania w skrypcie języka R, takie jak oczekiwanie na wprowadzenie danych przez użytkownika, wstrzymują wykonywanie skryptu.
* Ustawiając katalog roboczy w skrypcie języka R, *musisz* zdefiniować pełną ścieżkę do katalogu roboczego, a nie ścieżkę względną.

### <a name="run-your-r-script-and-import-data"></a>Uruchamianie skryptu języka R i importowanie danych
1. W programie Power BI Desktop łącznik danych skryptu języka R znajduje się w obszarze **Pobierz dane**. Aby uruchomić skrypt języka R, wybierz pozycje **Pobierz dane &gt; Więcej...**, a następnie wybierz pozycje **Inne &gt; Skrypt języka R**, jak pokazano na poniższej ilustracji:
   
   ![](media/desktop-r-scripts/r-scripts-1.png)
2. Jeśli na maszynie lokalnej masz zainstalowany język R, jako aparat języka jest wybierana jego najnowsza zainstalowana wersja. Po prostu skopiuj skrypt do okna skryptu i wybierz przycisk **OK**.
   
   ![](media/desktop-r-scripts/r-scripts-2.png)
3. Jeśli język R nie jest zainstalowany, nie zostanie zidentyfikowany albo jeśli na maszynie lokalnej masz wiele jego instalacji, rozwiń pozycję **Ustawienia instalacji języka R** w celu wyświetlenia opcji instalacji lub wybrania instalacji, która ma uruchomić skrypt języka R.
   
   ![](media/desktop-r-scripts/r-scripts-3.png)
   
   Jeśli język R jest zainstalowany i nie zostanie zidentyfikowany, możesz jawnie określić jego lokalizację w polu tekstowym dostępnym po rozwinięciu pozycji **Ustawienia instalacji języka R**. Na ilustracji powyżej ścieżka *C:\Program Files\R\R-3.2.0* została jawnie podana w polu tekstowym.
   
   Ustawienia instalacji języka R znajdują się w środku sekcji Obsługa skryptów języka R okna dialogowego Opcje. Aby określić własne ustawienia instalacji języka R, wybierz pozycje **Plik > Opcje i ustawienia**, a następnie pozycje **Opcje > Obsługa skryptów języka R**. Jeśli dostępnych jest wiele instalacji języka R, zostanie wyświetlone menu rozwijane pozwalające wybrać instalację do użycia.
   
   ![](media/desktop-r-scripts/r-scripts-4.png)
4. Wybierz przycisk **OK**, aby uruchomić skrypt języka R. Gdy skrypt zostanie uruchomiony pomyślnie, można wybrać wynikowe ramki danych do dodania do modelu usługi Power BI.

### <a name="refresh"></a>Odświeżanie
Skrypt języka R w programie Power BI Desktop można odświeżyć. Odświeżenie skryptu języka R powoduje, że program Power BI Desktop uruchamia go ponownie w swoim środowisku.

## <a name="next-steps"></a>Następne kroki
Spójrz na następujące informacje dodatkowe na temat języka R w usłudze Power BI.

* [Tworzenie wizualizacji języka R w programie Power BI Desktop](desktop-r-visuals.md)
* [Używanie zewnętrznego środowiska IDE języka R z usługą Power BI](desktop-r-ide.md)

