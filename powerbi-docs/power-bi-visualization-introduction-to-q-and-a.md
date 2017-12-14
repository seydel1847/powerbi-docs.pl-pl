---
title: "Wprowadzenie do funkcji pytań i odpowiedzi w usłudze Power BI (samouczek)"
description: "Samouczek: wprowadzenie do funkcji pytań i odpowiedzi w usłudze Power BI przy użyciu przykładu analizy detalicznej"
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
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 2038fb5bd4a21235c3026c8506ae30b8c3e287e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="get-started-with-power-bi-qa-tutorial"></a>Wprowadzenie do funkcji pytań i odpowiedzi w usłudze Power BI (samouczek)
## <a name="tutorial-use-power-bi-qa-with-the-retail-analysis-sample"></a>Samouczek: używanie funkcji pytań i odpowiedzi usługi Power BI na przykładzie analizy detalicznej
Czasem najszybszym sposobem uzyskania odpowiedzi na podstawie danych jest zadanie pytania przy użyciu języka naturalnego.  W ramach tego samouczka rozpatrzymy 2 różne sposoby tworzenia tej samej wizualizacji: wbudowanie jej do raportu i zadanie pytania za pomocą funkcji pytań i odpowiedzi.  

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
[Jakiego rodzaju pytania mogę zadawać funkcji pytań i odpowiedzi?](service-q-and-a.md)

[Pytania i odpowiedzi w usłudze Power BI](service-q-and-a.md)

[Dbanie o poprawne współdziałanie danych z funkcją pytań i odpowiedzi w usłudze Power BI](service-prepare-data-for-q-and-a.md)

[Przygotowanie skoroszytu dla funkcji pytań i odpowiedzi](service-prepare-data-for-q-and-a.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

