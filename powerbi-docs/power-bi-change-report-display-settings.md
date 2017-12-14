---
title: Zmiana rozmiaru strony raportu (samouczek)
description: "Samouczek: zmienianie ustawień wyświetlania strony w raporcie usługi Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/25/2017
ms.author: mihart
ms.openlocfilehash: a5cc05e26012f88e889612788d4479a370063d4f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="change-the-size-of-a-report-page-tutorial"></a>Zmiana rozmiaru strony raportu (samouczek)
W [poprzednim artykule i filmie wideo](power-bi-report-display-settings.md) omówiliśmy dwa różne sposoby kontrolowania wyświetlania strony w raportach usługi Power BI: **Widok** i **Rozmiar strony**. Teraz je wypróbujemy.

## <a name="first-lets-change-the-page-view-setting"></a>Po pierwsze zmienimy ustawienie Widok strony
1. Otwórz raport w widoku odczytu lub edycji. W tym przykładzie użyto strony „Nowe sklepy” [próbnych danych dotyczących analizy handlu detalicznego](sample-retail-analysis.md).  Strona ta jest wyświetlana przy użyciu ustawienia **Dopasuj do strony**.  W tym przypadku opcja Dopasuj do strony wyświetla stronę raportu bez pasków przewijania, ale niektóre szczegóły i tytuły są zbyt małe, żeby dało się je odczytać.
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_page.png)
2. Upewnij się, że na kanwie nie wybrano żadnych wizualizacji. Wybierz opcję **Widok** i przejrzyj opcje wyświetlania.

* Widok odczytu będzie następujący.
  
     ![](media/power-bi-change-report-display-settings/power-bi-page-view-menu-new.png)
* Widok edycji będzie następujący.
  
    ![](media/power-bi-change-report-display-settings/power-bi-view-editing-view.png)

1. Zobaczmy, jak wygląda strona przy użyciu ustawienia **Rozmiar rzeczywisty**.
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)
   
   Niezbyt dobrze. Pulpit nawigacyjny ma teraz podwójne paski przewijania.
2. Przełącz się na opcję **Dopasuj do szerokości**.
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_width.png)
   
   Teraz strona wygląda lepiej. Mamy paski przewijania, ale też łatwiej odczytać szczegóły.

## <a name="change-the-default-view-for-a-report-page"></a>Zmiana domyślnego widoku strony raportu
Wszystkie raporty usługi Power BI domyślnie wyświetlane są w widoku **Dopasuj do strony**. Co zrobić, jeśli chcesz, aby ta strona raportu zawsze była otwierana w widoku **Rozmiar rzeczywisty**?

1. Na stronie **Nowe sklepy** raportu przełącz się z powrotem na widok **Rozmiar rzeczywisty**.
   
   ![](media/power-bi-change-report-display-settings/power-bi-actual-size.png)
2. Zapisz raport pod inną nazwą, wybierając opcję **Plik > Zapisz jako**. Masz teraz dwie kopie tego raportu; raport oryginalny, **Nowe sklepy** nadal będzie otwierany w widoku domyślnym, ale w przypadku nowego raportu będzie stosowany widok **Rozmiar rzeczywisty**. Sprawdźmy to.
   
   ![](media/power-bi-change-report-display-settings/power-bi-save-as.png)
3. Wybierz nazwę bieżącego obszaru roboczego z górnego paska nawigacyjnego, aby powrócić do tego obszaru roboczego.  
   
   ![](media/power-bi-change-report-display-settings/power-bi-my-workspace.png)
4. Wybierz kartę **Raporty** i wybierz nowy utworzony raport (będzie oznaczony żółtą gwiazdką).
   
    ![](media/power-bi-change-report-display-settings/power-bi-new-report2.png)
5. Raport zostanie otwarty w widoku **Rozmiar rzeczywisty**.
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)

## <a name="now-lets-explore-the-page-size-setting"></a>Teraz przyjrzymy się ustawieniom *rozmiaru strony*
Ustawienia rozmiaru strony są dostępne tylko w [Widoku edycji](service-interact-with-a-report-in-editing-view.md). Aby otworzyć raport w widoku edycji, musisz mieć uprawnienia właściciela raportu. W przypadku połączenia z dowolnym z naszych [przykładów](sample-datasets.md) będziesz mieć uprawnienia właściciela do tych raportów.

1. Otwórz stronę „Sprzedaż miesięczna regionu” [próbnych danych dotyczących analizy handlu detalicznego](sample-retail-analysis.md) w widoku edycji.
2. Upewnij się, że na kanwie nie wybrano żadnych wizualizacji.  W okienku **Wizualizacje** wybierz ikonę wałka do malowania ![](media/power-bi-change-report-display-settings/power-bi-paintroller.png).
3. Wybierz opcję **Rozmiar strony** &gt; **Typ**, aby wyświetlić opcje rozmiaru strony.
   
   ![](media/power-bi-change-report-display-settings/power-bi-page-size-menu-new.png)
4. Wybierz opcję **Letter**.  Na białej części kanwy pozostanie tylko zawartość mieszcząca się w obszarze 816 × 1056 pikseli (rozmiar Letter).
   
   ![](media/power-bi-change-report-display-settings/power-bi-letter-new.png)
5. Jeśli zmienimy **Widok** na opcję „Dopasuj do szerokości”, nasza kanwa będzie wyświetlać tylko zawartość strony mieszczącą się w rozmiarze Letter.
   
   ![](media/power-bi-change-report-display-settings/power-bi-fit-to-width-new.png)
6. Wybierz współczynnik **Rozmiar strony** **16:9**.
   
   ![](media/power-bi-change-report-display-settings/power-bi-16-to-9-new.png)
   
   Strona raportu będzie wyświetlana przy użyciu współczynnika 16 (szerokość) do 9 (wysokość). Aby wyświetlić faktyczny rozmiar w pikselach, przyjrzyj się wyszarzonym polom Szerokość i Wysokość (1280 × 720). Jest dużo wolnego miejsca wokół kanwy raportu, ponieważ wcześniej ustawiliśmy **Widok** na opcję „Dopasuj do szerokości”.
7. Kontynuuj eksplorowanie opcji **Rozmiar strony**.

## <a name="using-page-view-and-page-size-together"></a>Używanie połączonych opcji Widok i Rozmiar strony
Użyj opcji Widok i Rozmiar strony w połączeniu, aby utworzyć raport, który będzie wyglądał doskonale po osadzeniu w innej aplikacji.

W tym ćwiczeniu utworzysz stronę raportu, która będzie wyświetlana w aplikacji z dostępnym miejscem 500 pikseli (szerokość) na 750 pikseli (wysokość).

W poprzednim kroku zobaczyliśmy, że nasza strona raportu była wyświetlana w polu o rozmiarze 1280 pikseli (szerokość) na 720 pikseli (wysokość). Wiemy więc, że musimy wykonać wiele działań związanych ze zmianą rozmiaru i organizacją, jeśli chcemy, żeby wszystkie nasze elementy wizualne się zmieściły.

1. Zmień rozmiar i przesuń elementy wizualne tak, aby mieściły się w części mniejszej od połowy obecnego obszaru kanwy.
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-view.gif)
2. Wybierz opcję **Rozmiar strony** &gt; **Niestandardowy**.
3. Ustaw Szerokość na wartość 500, a Wysokość na wartość 750.
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-new.png)
4. Dopasuj stronę raportu, aby wyglądała możliwie najlepiej. Przełącz się między opcjami **Widok > Rozmiar rzeczywisty** i **Widok > Dopasuj do strony**, aby wprowadzać usprawnienia.
   
    ![](media/power-bi-change-report-display-settings/power-bi-final-new.png)

## <a name="next-steps"></a>Następne kroki
[Tworzenie raportów dla Cortany](service-cortana-answer-cards.md)

Powrót do [Ustawienia wyświetlania strony w raporcie usługi Power BI](power-bi-report-display-settings.md)

Przeczytaj więcej na temat [raportów w usłudze Power BI](service-reports.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

