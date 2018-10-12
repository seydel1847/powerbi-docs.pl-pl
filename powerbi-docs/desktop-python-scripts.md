---
title: Uruchamianie skryptów języka Python w programie Power BI Desktop
description: Uruchamianie skryptów języka Python w programie Power BI Desktop
author: otarb
manager: rajatt
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/18/2018
ms.author: otarb
LocalizationGroup: Connect to data
ms.openlocfilehash: c7214d67cba58cdcd2e63b194e6c648e614943af
ms.sourcegitcommit: 698b788720282b67d3e22ae5de572b54056f1b6c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2018
ms.locfileid: "45975017"
---
# <a name="run-python-scripts-in-power-bi-desktop"></a>Uruchamianie skryptów języka Python w programie Power BI Desktop
Skrypty języka Python można uruchamiać bezpośrednio w programie **Power BI Desktop** i importować wynikowe zestawy danych bezpośrednio do modelu danych w programie Power BI Desktop.

## <a name="install-python"></a>Instalowanie języka Python
Aby uruchamiać skrypty języka Python w programie Power BI Desktop, musisz zainstalować **język Python** na swojej maszynie lokalnej. Język **Python** możesz pobrać i zainstalować bezpłatnie z wielu miejsc, w tym z [oficjalnej strony pobierania języka Python](https://www.python.org/) i witryny [Anaconda](https://anaconda.org/anaconda/python/). Bieżąca wersja mechanizmu obsługi skryptów języka Python w programie Power BI Desktop obsługuje znaki Unicode, a także spacje (puste znaki) w ścieżce instalacji.

## <a name="run-python-scripts"></a>Uruchamianie skryptów języka Python
Wykonując kilka prostych kroków w programie Power BI Desktop, można uruchomić skrypty języka Python i utworzyć model danych, na podstawie którego można z kolei tworzyć raporty i udostępniać je w usłudze Power BI.

### <a name="prepare-a-python-script"></a>Przygotowywanie skryptu języka Python
Aby uruchomić skrypt języka Python w programie Power BI Desktop, utwórz skrypt w lokalnym środowisku programistycznym języka Python i upewnij się, że działa on prawidłowo.

Aby uruchomić skrypt w programie Power BI Desktop, upewnij się, że działa on prawidłowo w niezmodyfikowanym obszarze roboczym. Oznacza to, że wszystkie pakiety i zależności muszą zostać jawnie załadowane i uruchomione.

Istnieje kilka ograniczeń dotyczących przygotowywania i uruchamiania skryptów języka Python w programie Power BI Desktop:

* Importowane są tylko ramki danych Pandas, dlatego upewnij się, że dane, które chcesz zaimportować do usługi Power BI, są reprezentowane w ramce danych.
* Limit czasu działania każdego skryptu języka Python to 30 minut.
* Interakcyjne wywołania w skrypcie języka Python, takie jak oczekiwanie na wprowadzenie danych przez użytkownika, wstrzymują wykonywanie skryptu.
* Ustawiając katalog roboczy w skrypcie języka Python, *musisz* zdefiniować pełną ścieżkę do katalogu roboczego, a nie ścieżkę względną.
* Zagnieżdżone tabele (tabele w tabelach) nie są obecnie obsługiwane. 

### <a name="run-your-python-script-and-import-data"></a>Uruchamianie skryptu języka Python i importowanie danych
1. W programie Power BI Desktop łącznik danych skryptu języka Python znajduje się w obszarze **Pobierz dane**. Aby uruchomić skrypt języka Python, wybierz pozycje **Pobierz dane &gt; Więcej**, a następnie wybierz pozycje **Inne &gt; Skrypt języka Python**, jak pokazano na poniższej ilustracji:
   
   ![](media/desktop-python-scripts/python-scripts-1.png)
2. Jeśli na maszynie lokalnej masz zainstalowany język Python, jako aparat języka jest wybierana jego najnowsza zainstalowana wersja. Po prostu skopiuj skrypt do okna skryptu i wybierz przycisk **OK**.
   
   ![](media/desktop-python-scripts/python-scripts-2.png)
3. Jeśli język Python nie jest zainstalowany, nie zostanie zidentyfikowany lub na maszynie lokalnej masz jego wiele instalacji, pojawi się ostrzeżenie.
   
   ![](media/desktop-python-scripts/python-scripts-3.png)
   
   Ustawienia instalacji języka Python znajdują się w środku sekcji Obsługa skryptów języka Python okna dialogowego Opcje. Aby określić własne ustawienia instalacji języka Python, wybierz pozycje **Plik > Opcje i ustawienia**, a następnie pozycje **Opcje > Obsługa skryptów języka Python**. Jeśli dostępnych jest wiele instalacji języka Python, zostanie wyświetlone menu rozwijane pozwalające wybrać instalację do użycia. Możesz również wybrać pozycję **Inne** i podać ścieżkę niestandardową.
   
   ![](media/desktop-python-scripts/python-scripts-4.png)
4. Wybierz przycisk **OK**, aby uruchomić skrypt języka Python. Gdy skrypt zostanie uruchomiony pomyślnie, można wybrać wynikowe ramki danych do dodania do modelu usługi Power BI.

### <a name="refresh"></a>Odśwież
Skrypt języka Python w programie Power BI Desktop można odświeżyć. Odświeżenie skryptu języka Python powoduje, że program Power BI Desktop uruchamia go ponownie w swoim środowisku.

## <a name="next-steps"></a>Następne kroki
Zapoznaj się z następującymi informacjami dodatkowymi na temat języka Python w usłudze Power BI.

* [Tworzenie wizualizacji języka Python w programie Power BI Desktop](desktop-python-visuals.md)
* [Używanie zewnętrznego środowiska IDE języka Python z usługą Power BI](desktop-python-ide.md)