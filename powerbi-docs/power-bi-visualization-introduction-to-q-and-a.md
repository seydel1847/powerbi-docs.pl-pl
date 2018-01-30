---
title: "Szybki start — wprowadzenie do funkcji pytań i odpowiedzi w usłudze Power BI"
description: "Szybki start: wprowadzenie do funkcji pytań i odpowiedzi w usłudze Power BI przy użyciu przykładu Retail Analysis"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/16/2018
ms.author: mihart
ms.openlocfilehash: d63c6479ed5f0bb9e882900fc5a653f08ad6a823
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="get-started-with-power-bi-qa-quickstart"></a>Wprowadzenie do funkcji pytań i odpowiedzi w usłudze Power BI (szybki start)
## <a name="use-power-bi-qa-with-the-retail-analysis-sample"></a>Używanie funkcji pytań i odpowiedzi usługi Power BI z przykładem Retail Analysis
Czasem najszybszym sposobem uzyskania odpowiedzi na podstawie danych jest zadanie pytania przy użyciu języka naturalnego.  W ramach tego podręcznika Szybki start rozpatrzymy 2 różne sposoby tworzenia tej samej wizualizacji: po pierwsze, wbudowanie jej do raportu i, po drugie, zadanie pytania za pomocą funkcji pytań i odpowiedzi. Użyjemy usługi Power BI, ale proces jest niemal identyczny w przypadku używania programu Power BI Desktop.

Aby z niego skorzystać, musisz użyć raportu, który możesz edytować, dlatego użyjemy jednego z przykładów dostępnych w usłudze Power BI.

## <a name="method-1-using-the-report-editor"></a>Metoda 1: przy użyciu edytora raportu
1. W obszarze roboczym usługi Power BI wybierz pozycję **Pobierz dane** \> **Przykłady** \> **Przykład analizy detalicznej** > **Połącz**.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)
2. Pulpit nawigacyjny zawiera obszar kafelka wykresu „Sprzedaż zeszłoroczna i sprzedaż tegoroczna”.  Wybierz ten kafelek. 
   
   * Jeśli ten kafelek został utworzony za pomocą funkcji pytań i odpowiedzi, wybranie kafelka otworzy funkcję pytań i odpowiedzi. 
   * Ale ten Kafelek został utworzony w raporcie, więc raport zostanie otwarty na stronie zawierającej tę wizualizację.
3. Otwórz raport w widoku do edycji, wybierając pozycję **Edytuj raport**.  Jeśli nie jesteś właścicielem raportu, nie będziesz mieć możliwości otwarcia raportu w widoku do edycji.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Wybierz obszar wykresu i przejrzyj ustawienia w okienku **Pola**.  Twórca raportu zbudował ten wykres, wybierając te 3 wartości (**Czas > Miesiąc obrachunkowy**, **Sprzedaż > Sprzedaż tegoroczna**, **Sprzedaż > Sprzedaż zeszłoroczna > Wartość**) i porządkując je w źródłach **Oś** i **Wartości**.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="method-2-using-qa"></a>Metoda 2: za pomocą funkcji pytań i odpowiedzi
A może spróbujemy utworzyć ten sam wykres liniowy za pomocą funkcji pytań i odpowiedzi?

![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. Przejdź z powrotem do pulpitu nawigacyjnego przykładu analizy detalicznej.
2. Używając języka naturalnego, wpisz coś podobnego do poniższego w pole pytania:
   
   **jaka była tegoroczna sprzedaż i zeszłoroczna sprzedaż według miesięcy jako wykres warstwowy**
   
   W miarę pisania pytania funkcja pytań i odpowiedzi wybiera najlepszą wizualizację do wyświetlania odpowiedzi, przy czym wizualizacja zmienia się dynamicznie w miarę modyfikowania pytania. Funkcja pytań i odpowiedzi pomaga również sformatować pytanie za pomocą sugestii, funkcji automatycznego uzupełniania i korekty pisowni.
   
   Po zakończeniu wpisywania pytania wynikiem jest dokładnie ten sam wykres, który widzieliśmy w raporcie.  Ale jego tworzenie w ten sposób było znacznie szybsze!
   
   ![](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. Podobnie jak podczas pracy z raportami, w ramach funkcji pytań i odpowiedzi masz dostęp do okienek wizualizacji, filtrów i pól.  Otwórz te okienka, aby dalej eksplorować i modyfikować element wizualny.
4. Aby przypiąć wykres do swojego pulpitu nawigacyjnego, wybierz ikonę pinezki ![](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png).

## <a name="next-steps"></a>Następne kroki
[Pytania i odpowiedzi w usłudze Power BI](power-bi-q-and-a.md)

[Dbanie o poprawne współdziałanie danych z funkcją pytań i odpowiedzi w usłudze Power BI](service-prepare-data-for-q-and-a.md)

Więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

