---
title: 'Próbka danych do analizy zakupów: krótki przewodnik'
description: 'Próbka danych do analizy zakupów dla usługi Power BI: krótki przewodnik'
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/23/2018
ms.author: mihart
LocalizationGroup: Samples
ms.openlocfilehash: a43ffab1ff30dd624fadb7dacb3cebc989ba3128
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "36944686"
---
# <a name="procurement-analysis-sample-for-power-bi-take-a-tour"></a>Próbka danych do analizy zakupów dla usługi Power BI: krótki przewodnik

## <a name="overview-of-the-procurement-analysis-sample"></a>Omówienie przykładu Procurement Analysis
Ten pulpit nawigacyjny oparty na próbce branżowej oraz źródłowy raport zapewniają analizę wydatków firmy produkcyjnej na dostawców według kategorii i lokalizacji. W przykładzie zbadamy następujące obszary:

* Kim są najlepsi dostawcy?
* W jakich kategoriach mamy największe wydatki?
* Którzy dostawcy dają nam największe rabaty i kiedy to robią?

Te przykładowe dane stanowią części serii ilustrującej, w jaki sposób można wykorzystać usługę Power BI w pracy z danymi biznesowymi, raportami i pulpitami nawigacyjnymi. Są to prawdziwe dane pochodzące z firmy obviEnce ([www.obvience.com](http://www.obvience.com/)) przedstawione w sposób anonimowy.

![](media/sample-procurement/procurement1.png)

## <a name="prerequisites"></a>Wymagania wstępne

 Zanim będzie można korzystać z przykładu, trzeba go najpierw pobrać jako [pakiet zawartości](https://docs.microsoft.com/power-bi/sample-procurement#get-the-content-pack-for-this-sample), [plik pbix](http://download.microsoft.com/download/D/5/3/D5390069-F723-413B-8D27-5888500516EB/Procurement%20Analysis%20Sample%20PBIX.pbix) lub [skoroszyt programu Excel](http://go.microsoft.com/fwlink/?LinkId=529784).

### <a name="get-the-content-pack-for-this-sample"></a>Pobieranie pakietu zawartości dla tego przykładu

1. Otwórz usługę Power BI (app.powerbi.com) i zaloguj się.
2. W lewym dolnym rogu wybierz opcję **Pobierz dane**.
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. Na wyświetlonej stronie Pobieranie danych wybierz ikonę **Przykłady**.
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. Wybierz pozycję **Przykład Procurement Analysis**, a następnie wybierz polecenie **Połącz**.  
  
   ![Pobierz dane](media/sample-procurement/procurement1a.png)
   
5. Usługa Power BI zaimportuje pakiet zawartości i doda nowy pulpit nawigacyjny, raport oraz zestaw danych do bieżącego obszaru roboczego. Nowa zawartość jest oznaczona żółtą gwiazdką. 
   
   ![Gwiazdka](media/sample-procurement/procurement1b.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Pobieranie pliku pbix dla tego przykładu

Alternatywnie przykład możesz pobrać jako plik pbix, który został zaprojektowany do użycia w programie Power BI Desktop. 

 * [Przykład Procurement Analysis](http://download.microsoft.com/download/D/5/3/D5390069-F723-413B-8D27-5888500516EB/Procurement%20Analysis%20Sample%20PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Pobieranie skoroszytu programu Excel dla tego przykładu
Możesz też [pobrać sam zestaw danych (skoroszyt programu Excel)](http://go.microsoft.com/fwlink/?LinkId=529784) omawiany w tym przykładzie. Skoroszyt zawiera arkusze programu Power View, które można wyświetlać i modyfikować. Aby wyświetlić nieprzetworzone dane, wybierz pozycje **Power Pivot > Zarządzaj**.


## <a name="spending-trends"></a>Trendy wydatków
Najpierw przyjrzyjmy się trendom w zakresie wydatków z podziałem na kategorie i lokalizacje.  

1. W obszarze roboczym otwórz kartę **Pulpity nawigacyjne** i wybierz pulpit nawigacyjny analizy zakupów.
2. Wybierz kafelek pulpitu nawigacyjnego **Faktury łącznie według kraju/regionu**. Ponadto spowoduje to otworzenie strony „Przegląd wydatków” raportu „Przykład analizy zakupów”.

    ![](media/sample-procurement/procurement2.png)

Zwróć uwagę na kilka rzeczy:

* Na wykresie liniowym **Faktury łącznie według miesiąca i kategorii**: kategoria **Bezpośrednie** zawiera całkiem spójne wydatki, **Logistyka** wykazuje szczyt w grudniu, a szczyt kategorii **Inne** przypada w lutym.
* Na mapie **Faktury łącznie według kraju/regionu**: większość naszych wydatków ma miejsce w USA.
* Na wykresie kolumnowym **Faktury łącznie według podkategorii**: największymi kategoriami wydatków jest **Sprzęt** oraz **Towary i usługi pośrednie**.
* Na wykresie Faktury łącznie według warstwy: większość działalności biznesowej jest prowadzona wraz z warstwą 1 (10 pierwszych) dostawców. Ułatwia to lepsze zarządzanie relacjami z dostawcami.

## <a name="spending-in-mexico"></a>Wydatki w Meksyku
Sprawdźmy obszary wydatków w Meksyku.

1. Na wykresie kołowym wybierz bąbelek **Meksyk** na mapie. Zauważ, że na wykresie kolumnowym „Faktury łącznie według podkategorii” większa część przypada w podkategorii **Towary i usługi pośrednie**.

   ![](media/sample-procurement/pbi_procsample_spendmexico.png)
2. Przejdź do szczegółowych informacji w kolumnie **Towary i usługi pośrednie**:

   * Wybierz strzałkę przechodzenia do szczegółów ![](media/sample-procurement/pbi_drilldown_icon.png) w prawym górnym rogu wykresu.
   * Wybierz kolumnę **Towary i usługi pośrednie**.

      Zdecydowanie największą część wydatków w tej kategorii pochłania Sprzedaż i marketing.
   * Wybierz ponownie **Meksyk** na mapie.

      Największą część wydatków w tej kategorii w Meksyku stanowi Konserwacja i naprawa.

      ![](media/sample-procurement/pbi_procsample_drill_mexico.png)
3. Wybierz strzałkę w górę w lewym górnym rogu wykresu, aby powrócić do poprzednich informacji szczegółowych.
4. Wybierz strzałkę ponownie, aby wyłączyć przechodzenie do szczegółów.  
5. Wybierz opcję **Power BI** w górnym pasku nawigacyjnym, aby powrócić do obszaru roboczego.

## <a name="evaluate-different-cities"></a>Ocena różnych miast
Możemy użyć wyróżnienia, aby ocenić różne miasta.

1. Wybierz kafelek pulpitu nawigacyjnego **Faktury łącznie, % rabatu według miesiąca**. Raport zostanie otwarty na stronie „Analiza rabatów”.
2. Wybierz różne miasta na mapie drzewa **Faktury łącznie według miasta**, aby zobaczyć ich porównanie. Prawie wszystkie faktury w Miami pochodzą od dostawców warstwy 1.

   ![](media/sample-procurement/pbi_procsample_miamitreemap2.png)

## <a name="vendor-discounts"></a>Rabaty dostawcy
Przyjrzyjmy się również rabatom dostępnym u dostawców oraz okresom, w których uzyskujemy największe rabaty.

![](media/sample-procurement/procurement4.png)

W szczególności szukamy odpowiedzi na poniższe pytania:

* Czy rabaty różnią się w poszczególnych miesiącach, czy też są takie same w każdym miesiącu?
* Czy niektóre miasta uzyskują wyższe rabaty od innych?

### <a name="discount-by-month"></a>Rabaty według miesięcy
Sprawdzając wykres złożony **Faktury łącznie i % rabatu według miesiąca**, zobaczymy, że **luty** jest najgorętszym miesiącem, a **wrzesień** najspokojniejszym. Teraz sprawdźmy procent rabatu w tych miesiącach.
Zauważ, że wzrost zapotrzebowania oznacza spadek rabatu, a spadek zapotrzebowania to z kolei wzrost rabatu. Im bardziej potrzebujemy rabatu, tym gorszą ofertę otrzymujemy.

![](media/sample-procurement/procurement5.png)

### <a name="discount-by-city"></a>Rabaty według miast
Innym obszarem do zbadania jest rabat według miast. Wybierz każde miasto na mapie drzewa i zobacz, jak zmienia się wykres.

* W St. Louis (MO) odnotowano najwyższy szczyt w liczbie faktur w lutym oraz największy spadek oszczędności związany z rabatami w kwietniu.
* W Meksyku (Meksyk) odnotowano najwyższy procent rabatów (11,05%), a w Atlancie (GA) najniższy (0,08%).

![](media/sample-procurement/procurement6.png)

### <a name="edit-the-report"></a>Edytowanie raportu
Wybierz opcję **Edytuj raport** w lewym górnym rogu i sprawdź widok edycji.

* Zobacz, jak tworzone są strony
* Dodawanie stron i wykresów w oparciu o te same dane
* Zmiana typu wizualizacji dla wykresu — na przykład zmiana mapy drzewa na wykres pierścieniowy
* Przypinanie elementów do pulpitu nawigacyjnego

Pracując na danych w tym środowisku, nie musisz się niczego obawiać. Zawsze możesz zrezygnować z zapisania wprowadzonych zmian. Jeśli jednak je zapiszesz, możesz przejść do obszaru **Pobieranie danych** i pobrać nową kopię zestawu danych użytego w tym przykładzie.

## <a name="next-steps-connect-to-your-data"></a>Następne kroki: łączenie z danymi
Mamy nadzieję, że dzięki temu przewodnikowi wiesz już, że pulpity nawigacyjne usługi Power BI oraz raporty mogą okazać się niezastąpione w uzyskiwaniu informacji o danych dotyczących zakupów. Teraz Twoja kolej. Połącz się ze swoimi danymi. Usługa Power BI umożliwia nawiązanie połączenia z różnymi źródłami danych. Dowiedz się więcej o [rozpoczynaniu pracy z usługą Power BI](service-get-started.md).
