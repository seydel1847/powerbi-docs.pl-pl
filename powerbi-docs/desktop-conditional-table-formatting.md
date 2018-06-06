---
title: Formatowanie warunkowe tabel w programie Power BI Desktop
description: Zastosuj formatowanie dostosowane do tabel
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 70aa61d6a02bea1b7058a68b20718008ace1b8c8
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34480893"
---
# <a name="conditional-formatting-in-tables"></a>Formatowanie warunkowe w tabelach 
Za pomocą formatowania warunkowego dla tabel można określić niestandardowe kolory komórek, w tym gradienty kolorów, na podstawie wartości komórek lub na podstawie innych wartości bądź pól. Można również wyświetlić wartości komórek ze słupkami danych. 

Aby uzyskać dostęp do formatowania warunkowego, w obszarze **Pola** w okienku **Wizualizacje** programu Power BI Desktop w obszarze **Wartości** wybierz strzałkę w dół obok wartości, którą chcesz sformatować (lub kliknij to pole prawym przyciskiem myszy). Można zarządzać tylko formatowaniem warunkowym pól w obszarze **Wartości** w obszarze **Pola**.

![Polecenie Formatowanie warunkowe w menu](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

W poniższych sekcjach opisano każdą z tych trzech opcji formatowania warunkowego. W jednej kolumnie tabeli można zastosować więcej niż jedną opcję.

> [!NOTE]
> Formatowanie warunkowe zastosowane do tabeli zastępuje wszystkie niestandardowe style tabeli zastosowane do sformatowanych warunkowo komórek.

Aby usunąć formatowanie warunkowe z wizualizacji, wystarczy ponownie kliknąć pole prawym przyciskiem myszy i wybrać pozycję **Usuń formatowanie warunkowe** oraz typ formatowania do usunięcia.

![Polecenie Usuń formatowanie warunkowe w menu](media/desktop-conditional-table-formatting/table-formatting-1-remove.png)

## <a name="background-color-scales"></a>Skale kolorów tła

Wybranie pozycji **Formatowanie warunkowe**, a następnie pozycji **Skale kolorów tła** powoduje wyświetlenie następującego okna dialogowego.

![Okno dialogowe Skale kolorów tła](media/desktop-conditional-table-formatting/table-formatting-1-default-dialog.png)

Aby kolor był oparty na polu wybranym z modelu danych, możesz ustawić wartość **Kolor oparty na** na to pole. Ponadto możesz określić typ agregacji dla wybranego pola za pomocą wartości **Podsumowanie**. Pole do pokolorowania jest podane w polu **Zastosuj kolor do** dla przypomnienia. Formatowanie warunkowe można zastosować do pól tekstowych i pól daty, pod warunkiem, że jako podstawę formatowania wybierzesz wartość liczbową.

![Pole Kolor oparty na](media/desktop-conditional-table-formatting/table-formatting-1-apply-color-to.png)

Aby użyć odrębnych wartości kolorów dla danych zakresów wartości, wybierz pozycję **Kolor według reguł**. Aby zastosować spektrum kolorów, pozostaw pozycję **Kolor według reguł** niezaznaczoną. 

![Okno dialogowe Skale kolorów tła](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-dialog.png)

### <a name="color-by-rules"></a>Kolor według reguł

Po wybraniu pozycji **Kolor według reguł** możesz wprowadzić jeden lub większą liczbę zakresów wartości i dla każdego z nich ustawić kolor.  Każdy zakres wartości rozpoczyna się od warunku *Jeśli wartość*, a także zawiera warunek wartości *i* oraz kolor.

![Zakres wartości Kolor według reguł](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-if-value.png)

Komórki tabeli zawierające wartości z każdego zakresu zostaną wypełnione odpowiednimi kolorami. Na poniższym rysunku przedstawiono trzy reguły.

![Kolor według reguł — przykład](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules.png)

Przykładowa tabela teraz wygląda następująco:

![Przykładowa tabela po zastosowaniu koloru według reguł](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-table.png)


### <a name="color-minimum-to-maximum"></a>Kolor od wartości minimalnej do maksymalnej

Skonfigurować możesz wartości *Minimum* i *Maksimum* oraz ich kolory. W przypadku wybrania pola **Rozbieżność** można skonfigurować też wartość opcjonalną *Środek*.

![Przycisk Rozbieżność](media/desktop-conditional-table-formatting/table-formatting-1-diverging.png)

Przykładowa tabela teraz wygląda następująco:

![Przykładowa tabela z rozbieżnymi kolorami](media/desktop-conditional-table-formatting/table-formatting-1-diverging-table.png)

## <a name="font-color-scales"></a>Skale kolorów czcionki

Wybranie pozycji **Formatowanie warunkowe**, a następnie pozycji **Skale kolorów czcionki** powoduje wyświetlenie następującego okna dialogowego. To okno dialogowe jest podobne do okna dialogowego **Skale kolorów tła**, ale zmienia kolor czcionki zamiast koloru tła komórki.

![Okno dialogowe Skale kolorów czcionki](media/desktop-conditional-table-formatting/table-formatting-2-diverging.png)

Przykładowa tabela teraz wygląda następująco:

![Przykładowa tabela ze skalami kolorów czcionki](media/desktop-conditional-table-formatting/table-formatting-2-table.png)

## <a name="data-bars"></a>Paski danych

Wybranie pozycji **Formatowanie warunkowe**, a następnie pozycji **Paski danych** powoduje wyświetlenie następującego okna dialogowego. 

![Okno dialogowe Paski danych](media/desktop-conditional-table-formatting/table-formatting-3-default.png)

Domyślnie opcja **Pokaż tylko paski** nie jest zaznaczona, więc w komórce tabeli jest wyświetlany zarówno pasek, jak i rzeczywista wartość.

![Przykładowa tabela z paskami danych i wartościami](media/desktop-conditional-table-formatting/table-formatting-3-default-table.png)

Jeśli opcja **Pokaż tylko paski** jest zaznaczona, w komórce tabeli jest wyświetlany tylko pasek.

![Przykładowa tabela jedynie z paskami danych](media/desktop-conditional-table-formatting/table-formatting-3-default-table-bars.png)
