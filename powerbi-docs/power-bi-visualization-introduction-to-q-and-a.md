---
title: Wprowadzenie do pytań i odpowiedzi usługi Power BI
description: Wprowadzenie do funkcji pytań i odpowiedzi w usłudze Power BI z użyciem przykładu Retail Analysis
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 87783b928fdec1cadf5318ae184858c37daa4acc
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279256"
---
# <a name="get-started-with-power-bi-qa"></a>Wprowadzenie do pytań i odpowiedzi usługi Power BI

Czasem najszybszym sposobem uzyskania odpowiedzi na podstawie danych jest zadanie pytania przy użyciu języka naturalnego.  W ramach tego podręcznika Szybki start rozpatrzymy dwa różne sposoby tworzenia tej samej wizualizacji: po pierwsze, wbudowanie jej do raportu i, po drugie, zadanie pytania za pomocą funkcji pytań i odpowiedzi. Użyjemy usługi Power BI, ale proces jest niemal identyczny w przypadku używania programu Power BI Desktop.

Aby z niego skorzystać, musisz użyć raportu, który możesz edytować, dlatego użyjemy jednego z przykładów dostępnych w usłudze Power BI.

## <a name="create-a-visual-in-the-report-editor"></a>Tworzenie wizualizacji w edytorze raportów

1. W obszarze roboczym usługi Power BI wybierz pozycję **Pobierz dane** \> **Przykłady** \> **Przykład analizy detalicznej** > **Połącz**.
   
2. Pulpit nawigacyjny zawiera obszar kafelka wykresu „Sprzedaż zeszłoroczna i sprzedaż tegoroczna”.  Wybierz ten kafelek. Jeśli ten kafelek został utworzony za pomocą funkcji pytań i odpowiedzi, wybranie kafelka otworzy funkcję pytań i odpowiedzi. Ale ten Kafelek został utworzony w raporcie, więc raport zostanie otwarty na stronie zawierającej tę wizualizację.

    ![Przykład Retail Analysis — pulpit nawigacyjny](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)

1. Otwórz raport w widoku do edycji, wybierając pozycję **Edytuj raport**.  Jeśli nie jesteś właścicielem raportu, nie masz możliwości otwarcia raportu w widoku do edycji.
   
    ![Przycisk Edytuj raport](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Wybierz obszar wykresu i przejrzyj ustawienia w okienku **Pola**.  Twórca raportu zbudował ten wykres, wybierając te trzy wartości (**Czas > Miesiąc obrachunkowy**, **Sprzedaż > Sprzedaż tegoroczna**, **Sprzedaż > Sprzedaż zeszłoroczna > Wartość**) i porządkując je w źródłach **Oś** i **Wartości**.
   
    ![Okienko Wizualizacje](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="create-the-same-visual-with-qa"></a>Tworzenie takiej samej wizualizacji za pomocą funkcji pytań i odpowiedzi

A może spróbujemy utworzyć ten sam wykres liniowy za pomocą funkcji pytań i odpowiedzi?

![Pole Zadaj pytanie](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. Przejdź z powrotem do pulpitu nawigacyjnego przykładu analizy detalicznej.
2. Używając języka naturalnego, wpisz coś podobnego do poniższego w polu pytania:
   
   **jaka była tegoroczna sprzedaż i zeszłoroczna sprzedaż według miesięcy jako wykres warstwowy**
   
   W miarę pisania pytania funkcja pytań i odpowiedzi wybiera najlepszą wizualizację do wyświetlania odpowiedzi, przy czym wizualizacja zmienia się dynamicznie w miarę modyfikowania pytania. Funkcja pytań i odpowiedzi pomaga również sformatować pytanie za pomocą sugestii, funkcji automatycznego uzupełniania i korekty pisowni.
   
   Po zakończeniu wpisywania pytania wynikiem jest dokładnie ten sam wykres, który widzieliśmy w raporcie.  Ale jego tworzenie w ten sposób było znacznie szybsze!
   
   ![Przykładowe pytanie](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. Podobnie jak podczas pracy z raportami, w ramach funkcji pytań i odpowiedzi masz dostęp do okienek wizualizacji, filtrów i pól.  Otwórz te okienka, aby dalej eksplorować i modyfikować element wizualny.
4. Aby przypiąć wykres do swojego pulpitu nawigacyjnego, wybierz ikonę pinezki ![Ikona przypinania](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png).

## <a name="next-steps"></a>Następne kroki
[Pytania i odpowiedzi w usłudze Power BI](consumer/end-user-q-and-a.md)

[Dbanie o poprawne współdziałanie danych z funkcją pytań i odpowiedzi w usłudze Power BI](service-prepare-data-for-q-and-a.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

