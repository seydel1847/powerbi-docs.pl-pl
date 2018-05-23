---
title: Formatowanie warunkowe tabel w programie Power BI Desktop
description: Zastosuj formatowanie dostosowane do tabel
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 9599b40940c9d9cca254bb2ed2e87c161cce371f
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="conditional-formatting-in-tables"></a>Formatowanie warunkowe w tabelach
Za pomocą formatowania warunkowego dla tabel można określić niestandardowe kolory tła komórek na podstawie wartości komórek lub na podstawie innych wartości bądź pól. Można też używać gradientów kolorów. Aby uzyskać dostęp do formatowania warunkowego, w obszarze **Pola** w okienku **Wizualizacje** programu Power BI Desktop w obszarze **Wartości** wybierz strzałkę w dół obok wartości, którą chcesz sformatować (lub kliknij to pole prawym przyciskiem myszy). Można zarządzać tylko formatowaniem warunkowym pól w obszarze **Wartości** w obszarze **Pola**.

![warunkowe formatowanie tabeli](media/desktop-conditional-table-formatting/table-formatting_1.png)

W wyświetlonym oknie dialogowym można skonfigurować kolor, a także wartości *Minimum* i *Maksimum*. W przypadku wybrania pola **Rozbieżność** można skonfigurować też wartość opcjonalną *Środek*.

![rozbieżność kolorów](media/desktop-conditional-table-formatting/table-formatting_2.png)

Gradient koloru można też utworzyć na podstawie pola z modelu danych. Ponadto można określić typ agregacji dla wybranego pola (wybrane pole jest określane w polu **Zastosuj kolor do**, można więc je śledzić).

![podstawowe kolory poza polem](media/desktop-conditional-table-formatting/table-formatting_2b.png)

Niestandardowe formatowanie zastosowane do tabeli przy użyciu opisanych powyżej kroków zastępuje wszystkie niestandardowe style tabeli zastosowane do sformatowanych warunkowo komórek.

![formatowanie tabeli](media/desktop-conditional-table-formatting/table-formatting_3.png)

Formatowanie warunkowe można również zastosować do pól tekstowych i pól daty, pod warunkiem, że jako podstawę formatowania wybierzesz wartość liczbową. 

Aby usunąć formatowanie warunkowe z wizualizacji, wystarczy ponownie kliknąć pole prawym przyciskiem myszy i wybrać pozycję **Usuń formatowanie warunkowe**.

![usuwanie formatowania tabeli](media/desktop-conditional-table-formatting/table-formatting_4.png)

