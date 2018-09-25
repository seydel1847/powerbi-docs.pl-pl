---
title: Wprowadzenie do usługi Power BI (usługa Power BI w trybie online)
description: Wprowadzenie do usługi Power BI w trybie online (app.powerbi.com)
author: adamw
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/22/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: c64a5e487725bdfedf03b496322a52e7664f5455
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2018
ms.locfileid: "46545094"
---
# <a name="tutorial-get-started-with-power-bi-service-apppowerbicom"></a>Samouczek: wprowadzenie do usługi Power BI (app.powerbi.com)
Ten samouczek ułatwia rozpoczęcie pracy z ***usługą Power BI***. Jeśli chcesz dowiedzieć się, jakie miejsce zajmuje usługa Power BI w ofercie innych produktów Power BI, zdecydowanie zalecamy zapoznanie się z tematem [Co to jest Power BI](power-bi-overview.md).

![grafika przedstawiająca relację między programem Desktop, usługą i aplikacją mobilną](media/service-get-started/power-bi-components.png)

Ten samouczek obejmuje następujące kroki:

> [!div class="checklist"]
> * Wyszukiwanie innej zawartości dotyczącej wprowadzenia do usługi Power BI
> * Logowanie do konta usługi Power BI w trybie online lub tworzenie konta, jeśli jeszcze go nie masz
> * Otwieranie usługi Power BI
> * Pobieranie danych i otwieranie ich w widoku raportu
> * Używanie tych danych do tworzenia wizualizacji i zapisywanie jej jako raportu
> * Tworzenie pulpitu nawigacyjnego przez przypinanie kafelków z raportu
> * Dodawanie kolejnej wizualizacji do pulpitu nawigacyjnego za pomocą narzędzia języka naturalnym dla pytań i odpowiedzi
> * Oczyszczanie zasobów przez usuwanie zestawu danych, raportu i pulpitu nawigacyjnego

## <a name="sign-up-for-power-bi-service"></a>Tworzenie konta w usłudze Power BI
Jeśli nie masz konta usługi Power BI Pro, na początku [utwórz konto bezpłatnej wersji próbnej usługi Power BI](https://app.powerbi.com/signupredirect?pbi_source=web).

Jeśli masz już konto, otwórz przeglądarkę i wpisz adres app.powerbi.com, aby otworzyć usługę Power BI. 

![Zaloguj się lub zarejestruj bezpłatnie](media/service-get-started/power-bi-sign-up.png)

Jeśli potrzebujesz pomocy dotyczącej programu Power BI Desktop, zobacz [Wprowadzenie do programu Desktop](desktop-getting-started.md). Jeśli potrzebujesz pomocy dotyczącej aplikacji Power BI dla urządzeń przenośnych, zobacz [Aplikacje Power BI dla urządzeń przenośnych](consumer/mobile/mobile-apps-for-mobile-devices.md).

> [!TIP]
> Wolisz skorzystać z darmowego kursu szkoleniowego, realizowanego samodzielnie? [Zapisz się na nasz kurs Analizowanie i wizualizowanie danych, dostępny w witrynie EdX](http://aka.ms/edxpbi).

Zapoznaj się z naszą [listą odtwarzania w serwisie YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP). Warto zacząć od obejrzenia klipu wideo Wprowadzenie do usługi Power BI:
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 

## <a name="what-is-power-bi-service"></a>Co to jest usługa Power BI?
Usługa Microsoft Power BI jest czasami nazywana usługą Power BI w trybie online lub app.powerbi.com. Usługa Power BI pomaga na bieżąco śledzić ważne informacje.  ***Pulpity nawigacyjne*** usługi Power BI umożliwiają monitorowanie najważniejszych aspektów działalności biznesowej.  Pulpity nawigacyjne zawierają ***kafelki***, które można kliknąć, aby otworzyć ***raporty*** umożliwiające uzyskiwanie dodatkowych informacji.  Połączenie z wieloma ***zestawami danych*** pozwala wyświetlać wszystkie istotne dane w jednym miejscu. Potrzebujesz pomocy dotyczącej bloków konstrukcyjnych tworzących usługę Power BI?  Zobacz [Power BI — podstawowe pojęcia](consumer/end-user-basic-concepts.md).

Jeśli przechowujesz ważne dane w plikach programu Excel lub plikach CSV, możesz utworzyć pulpit nawigacyjny usługi Power BI, aby mieć dostęp do informacji w dowolnym miejscu i dzielić się spostrzeżeniami z innymi osobami.  Czy masz subskrypcję aplikacji SaaS, takiej jak Salesforce?  Od razu połącz się z usługą Salesforce, aby automatycznie utworzyć pulpit nawigacyjny z tych danych, lub [zapoznaj się z innymi aplikacjami SaaS](service-get-data.md), z którymi możesz nawiązać połączenie. Jeśli należysz do organizacji, sprawdź, czy możesz korzystać z opublikowanych [aplikacji](consumer/end-user-create-apps.md).

Zapoznaj się z wszystkimi innymi sposobami [pobierania danych dla usługi Power BI](service-get-data.md).

## <a name="step-1-get-data"></a>Krok 1. Pobieranie danych
Oto przykład przedstawiający pobieranie danych z pliku CSV. Chcesz kontynuować pracę z tym samouczkiem? [Pobierz przykładowy plik CSV](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Zaloguj się do usługi Power BI](http://www.powerbi.com/). Nie masz konta? Nie martw się — możesz utworzyć konto bezpłatnej wersji próbnej.
2. Usługa Power BI zostanie otwarta w przeglądarce. Wybierz pozycję **Pobierz dane** w dolnej części paska nawigacyjnego po lewej stronie.
   
   ![pobieranie danych](media/service-get-started/getdata3.png)
3. Wybierz pozycję **Pliki**. 
   
   ![pobieranie plików](media/service-get-started/gs1.png)
4. Przejdź do pliku na komputerze i wybierz pozycję **Otwórz**. Jeśli plik został zapisany w usłudze OneDrive dla Firm, wybierz tę opcję. Jeśli plik został zapisany lokalnie, wybierz opcję **Plik lokalny**. 
   
   ![ekran Pobierz dane > Pliki](media/service-get-started/gs2.png)
5. W tym samouczku wybierzemy pozycję **Importuj**, aby dodać plik programu Excel jako zestaw danych, na podstawie którego utworzymy raporty i pulpity nawigacyjne. W przypadku wybrania pozycji **Przekaż** cały skoroszyt programu Excel jest przekazywany do usługi Power BI, gdzie można go otworzyć i edytować w aplikacji Excel Online.
   
   ![wybieranie opcji Importuj](media/service-get-started/power-bi-import.png)
6. Po przygotowaniu zestawu danych wybierz pozycję **Wyświetl zestaw danych**, aby go otworzyć w edytorze raportów. 

    ![okno dialogowe Zestaw danych jest gotowy](media/service-get-started/power-bi-gs.png)

    Ponieważ jeszcze nie utworzyliśmy żadnej wizualizacji, kanwa raportu będzie pusta.

    ![puste kanwy raportów](media/service-get-started/power-bi-report-editor.png)

6. Spójrz na górny pasek menu i zauważ, że jest dostępna opcja **Widok do czytania**. Ponieważ opcja widoku do czytania jest dostępna, oznacza to, że jesteś obecnie w **widoku do edycji**. 

    ![opcja Widok do czytania](media/service-get-started/power-bi-editing-view.png)

    W widoku do edycji możesz tworzyć i modyfikować raporty, ponieważ jesteś *właścicielem* raportu — jesteś *twórcą*. Po udostępnieniu raportu współpracownikom będą oni mogli wchodzić z nim w interakcje jedynie w widoku do czytania — są to *użytkownicy*. Dowiedz się więcej na temat [widoku do czytania oraz widoku do edycji](consumer/end-user-reading-view.md).
    
    Doskonałym sposobem na zapoznanie się z edytorem raportów jest skorzystanie z tego [krótkiego przewodnika](service-the-report-editor-take-a-tour.md).
   > 
 

## <a name="step-2-start-exploring-your-dataset"></a>Krok 2. Rozpoczynanie eksplorowania zestawu danych
Teraz, po nawiązaniu połączenia z danymi, rozpocznij eksplorowanie.  Po znalezieniu interesujących danych możesz utworzyć pulpit nawigacyjny w celu monitorowania ich zmian w czasie. Zobaczmy, jak to działa.
    
1. Aby utworzyć wizualizację, w edytorze raportu użyjemy okienka **Pola** w prawej części strony.  Zaznacz pola wyboru obok pozycji **Gross Sales** i **Date**.
   
   ![lista Pola](media/service-get-started/fields.png)

2. Usługa Power BI przeanalizuje dane i utworzy wizualizację.  Jeśli najpierw wybrano pole **Date**, pojawi się tabela.  Jeśli najpierw wybrano pole **Gross Sales**, pojawi się wykres. Wybierz inny sposób wyświetlania danych. Zobaczmy te dane w postaci wykresu liniowego. Wybierz ikonę wykresu liniowego (znanego także jako szablon) w **okienku Wizualizacje**.
   
   ![edytor raportu z wybraną ikoną](media/service-get-started/gettingstart5new.png)

3. Wykres wygląda ciekawie, więc *przypnijmy* go do pulpitu nawigacyjnego. Umieść kursor na wizualizacji i wybierz ikonę **Przypnij**.  Po przypięciu wizualizacji zostanie ona zapisana na pulpicie nawigacyjnym i będzie na bieżąco aktualizowana. Dzięki temu będzie można błyskawicznie sprawdzić najnowsze wartości.
   
   ![ikona przypinania](media/service-get-started/pinnew.png)

4. Ponieważ to jest nowy raport, zostanie wyświetlony monit o jego zapisanie, zanim będzie można przypiąć wizualizację do pulpitu nawigacyjnego. Nadaj raportowi nazwę (np. *Sales over time* — Sprzedaż w czasie) i wybierz pozycję **Zapisz i kontynuuj**. 
   
   ![okno dialogowe Zapisz raport](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
5. Przypnijmy wykres liniowy do nowego pulpitu nawigacyjnego i nadajmy mu nazwę „Financial sample for tutorial” (Przykład finansowy na potrzeby samouczka). 
   
   ![nazywanie raportu](media/service-get-started/power-bi-pin.png)
   
1. Wybierz pozycję **Przypnij**.
   
    Komunikat o powodzeniu (w prawym górnym rogu) informuje o tym, że wizualizacja została dodana do pulpitu nawigacyjnego jako kafelek.
   
    ![okno dialogowe Przypięto do pulpitu nawigacyjnego](media/service-get-started/power-bi-pin-success.png)

6. Wybierz pozycję **Przejdź do pulpitu nawigacyjnego**, aby wyświetlić wykres liniowy przypięty jako kafelek do całkowicie nowego pulpitu nawigacyjnego. Aby usprawnić pulpit nawigacyjny, możesz dodawać kolejne kafelki wizualizacji, a także [łączyć kafelki oraz zmieniać ich nazwy, rozmiary i położenie](service-dashboard-edit-tile.md).
   
   ![Pulpit nawigacyjny z przypiętą wizualizacją](media/service-get-started/power-bi-new-dashboard.png)
   
   W dowolnym momencie możesz powrócić do raportu, wybierając nowy kafelek na pulpicie nawigacyjnym. Usługa Power BI przeniesie Cię do widoku do czytania w edytorze raportu. Aby powrócić do widoku do edycji, wybierz pozycję **Edytuj raport** z górnego paska menu. Po przejściu do widoku do edycji, kontynuuj eksplorowanie i przypinanie kafelków. 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>Krok 3. Kontynuowanie eksplorowania za pomocą funkcji Pytania i odpowiedzi (zapytania w języku naturalnym)
1. Aby przeprowadzić szybką eksplorację danych, spróbuj zadać pytanie w polu Pytania i odpowiedzi. Pole funkcji Pytania i odpowiedzi znajduje się w górnej części pulpitu nawigacyjnego (**Zadaj pytanie dotyczące Twoich danych**) i w górnym pasku menu raportu (**Zadaj pytanie**). Wpisz na przykład pytanie „what segment had the most revenue” (w jakim segmencie przychody były największe).
   
   ![kanwa funkcji Pytania i odpowiedzi](media/service-get-started/powerbi-qna.png)

2. Funkcja Pytania i odpowiedzi wyszuka odpowiedź, a następnie wyświetli ją w formie wizualizacji. Wybierz ikonę przypinania ![ikona przypinania](media/service-get-started/pbi_pinicon.png) w celu wyświetlenia na pulpicie nawigacyjnym również tej wizualizacji.
3. Przypnij wizualizację do pulpitu nawigacyjnego „Financial Sample for tutorial”.
   
    ![Okno dialogowe opcji Przypnij do pulpitu nawigacyjnego](media/service-get-started/power-bi-pin2.png)

4. Wróć do pulpitu nawigacyjnego, w którym zostanie wyświetlony nowy kafelek.

   ![pulpit nawigacyjny z przypiętym wykresem](media/service-get-started/power-bi-final-dashboard.png)

## <a name="clean-up-resources"></a>Czyszczenie zasobów
Teraz, po zakończeniu tego samouczka, możesz usunąć zestaw danych, raport i pulpit nawigacyjny. 

1. Wybierz pozycję **Mój obszar roboczy** na lewym pasku nawigacyjnym.
2. Wybierz kartę **Zestawy danych** i znajdź zestaw danych zaimportowany na potrzeby tego samouczka.  
3. Wybierz wielokropek (...) > **Usuń**.

    ![Usuwanie zestawu danych](media/service-get-started/power-bi-delete.jpg)

    Usunięcie zestawu danych spowoduje również usunięcie raportu i pulpitu nawigacyjnego. 


## <a name="next-steps"></a>Następne kroki
Chcesz szybko skorzystać z innych samouczków?  Poniżej przedstawiono kilka przydatnych tematów, które pozwalają zapoznać się z usługą Power BI.

> [!div class="nextstepaction"]
> [Łączenie się z używanymi usługami online](consumer/end-user-connect-to-services.md)

