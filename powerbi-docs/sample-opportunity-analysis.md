---
title: "Próbka danych do analizy szans biznesowych dla usługi Power BI: krótki przewodnik"
description: "Próbka danych do analizy szans biznesowych dla usługi Power BI: krótki przewodnik"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/04/2017
ms.author: mihart
ms.openlocfilehash: 878738eb3f588c461b687451062a1641479e77ed
ms.sourcegitcommit: 54da95f184dd0f7bb59bb0bc8775a1d93129b195
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2017
---
# <a name="opportunity-analysis-sample-for-power-bi-take-a-tour"></a>Próbka danych do analizy szans biznesowych dla usługi Power BI: krótki przewodnik
**Próbka danych do śledzenia szans biznesowych** zawiera pulpit nawigacyjny (oraz skojarzony raport) dotyczący firmy zajmującej się oprogramowaniem, która posiada 2 kanały sprzedaży: *bezpośredni* i *partnerski*. Kierownik ds. sprzedaży utworzył ten pulpit nawigacyjny, aby śledzić szanse biznesowe i przychody z podziałem na region, rozmiar transakcji i kanał.

Kierownik ds. sprzedaży bazuje na dwóch wskaźnikach przychodów:

* **Przychód** — jest to oszacowanie sprzedawcy w zakresie spodziewanego w jego ocenie przychodu.
* **Przychód uwzględniany** — obliczany jako procentowe prawdopodobieństwo przychodu X i powszechnie uznawany za dokładniejszy wskaźnik rzeczywistego przychodu ze sprzedaży. Prawdopodobieństwo jest określane na podstawie bieżącego ***etapu sprzedaży*** dla transakcji.
  * Potencjalny klient — 10%  
  * Kwalifikacja — 20%  
  * Rozwiązanie — 40%  
  * Oferta — 60%  
  * Finalizacja — 80%

Te przykładowe dane stanowią części serii ilustrującej, w jaki sposób można wykorzystać usługę Power BI w pracy z danymi biznesowymi, raportami i pulpitami nawigacyjnymi. Są to prawdziwe dane pochodzące z firmy obviEnce ([www.obvience.com](http://www.obvience.com/)) przedstawione w sposób anonimowy.

>[!Note] 
Możesz również [pobrać sam zestaw danych (skoroszyt programu Excel) omawiany w tym przykładzie](http://go.microsoft.com/fwlink/?LinkId=529782). Skoroszyt zawiera arkusze programu Power View, które można wyświetlać i modyfikować.  Aby wyświetlić nieprzetworzone dane, wybierz pozycje **Power Pivot > Zarządzaj**. 

![](media/sample-opportunity-analysis/opportunity1.png)

## <a name="what-is-our-dashboard-telling-us"></a>O czym informuje nas pulpit nawigacyjny?
Nasz kierownik ds. sprzedaży utworzył pulpit nawigacyjny, aby śledzić najważniejsze metryki. W przypadku zauważenia czegoś interesującego może wybrać kafelek, aby bliżej przyjrzeć się tym danym.

1. Przychód firmy wynosi 2 mld USD, zaś przychód uwzględniany 461 mln USD.
2. Liczba szans biznesowych i przychód układają się w podobny wzorzec lejka, z malejącymi wartościami całkowitymi na każdym kolejnym etapie.
3. Większość szans biznesowych jest dostępnych w regionie wschodnim. 
4. Duże szanse biznesowe generują większy przychód niż szanse średnie i małe.
5. Duże transakcje partnerskie generują wyższe przychody: średnio 8 mln USD w porównaniu do 6 mln USD dla sprzedaży bezpośredniej. 

Ponieważ nakład pracy związany z zawarciem transakcji jest taki sam, niezależnie od tego, czy transakcja jest uznawana za dużą, średnią, czy małą, firma powinna bliżej przyjrzeć się danym, aby dowiedzieć się więcej na temat dużych szans biznesowych. 

Wybierz kafelek **Liczba szans biznesowych według kryterium partnerskiego i etapu sprzedaży**, aby otworzyć stronę 1 raportu.  
![](media/sample-opportunity-analysis/opportunity2.png)

## <a name="explore-the-pages-in-the-report"></a>Przeglądanie stron w raporcie
### <a name="page-1-of-our-report-is-titled-opportunity-count-overview"></a>Strona 1 naszego raportu nosi tytuł „Przegląd liczby szans biznesowych”.
![](media/sample-opportunity-analysis/opportunity3.png)

* Wschód jest najważniejszym regionem pod względem liczby szans biznesowych.  
* Na wykresie kołowym wybierz kolejno każdy region, aby filtrować strony. W każdym z regionów partnerzy odpowiadają za znacznie większą liczbę dużych szans biznesowych.   
* Wykres kolumnowy liczby szans biznesowych według kryterium partnerskiego i rozmiaru szansy jasno pokazuje, że większość dużych szans biznesowych jest generowanych przez partnerów, a więcej małych i średnich szans biznesowych to szanse niegenerowane przez partnerów. 
* Wybierz poszczególne etapy sprzedaży na wykresie słupkowym w lewym dolnym rogu, aby wyświetlić różnice w liczbach dla poszczególnych regionów i zwróć uwagę, że choć region wschodni jest największym regionem pod względem liczb, to w etapach Rozwiązanie, Oferta oraz Finalizacja wszystkie 3 regiony mają porównywalne wartości liczbowe. Oznacza to, że procentowo więcej transakcji dochodzi do skutku w regionie centralnym i zachodnim. 

### <a name="page-2-of-our-report-is-titled-revenue-overview"></a>Strona 2 naszego raportu ma tytuł „Omówienie przychodów”.
Na stronie tej zastosowano podobne spojrzenie na dane jednak z perspektywy przychodów zamiast liczby szans.  
![](media/sample-opportunity-analysis/opportunity4.png)

* Region wschodni jest nie tylko największym regionem pod względem liczby szans, lecz także pod względem przychodów.  
* Filtrowanie według kryterium partnerskiego (wybierz pozycję **Tak** w legendzie w prawym górnym rogu) pokazuje przychody na poziomie 1,5 mld USD i 294 mln USD. Dla porównania przychody niegenerowane przez partnerów wynosiły odpowiednio 644 mld USD i 166 mln USD.  
* Średni przychód w przypadku dużych klientów jest wyższy (8 mln) dla szans generowanych przez partnerów w porównaniu do 6 mln dla szans biznesowych niegenerowanych przez partnerów.  
* W odniesieniu do szans biznesowych generowanych przez partnerów przeciętny przychód w przypadku dużych szans biznesowych jest niemal dwukrotnie wyższy niż w przypadku średnich szans biznesowych (4 mln).  
* Średni przychód z tytułu małych i średnich transakcji jest porównywalny dla szans generowanych przez partnerów i pozostałych.   

Nasi partnerzy wyraźnie lepiej radzą sobie ze sprzedażą produktów klientom.  Może się okazać sensowne realizowanie większej liczby transakcji za pośrednictwem partnerów.

### <a name="page-3-of-our-report-is-titled-region-stage-counts"></a>Strona 3 raportu nosi tytuł „Liczby według etapów i regionów”
Ta strona analizuje podobne dane, ale z podziałem na region i etap.  
![](media/sample-opportunity-analysis/opportunity5.png)

* Filtrowanie według regionu wschodniego (wybierz pozycję **Wschód** na wykresie kołowym) pokazuje, że szanse biznesowe we wschodnim regionie dzielą się niemal równo na te generowane przez partnerów i bezpośrednio. 
* Duże szanse biznesowe występują najczęściej w regionie centralnym, małe w regionie wschodnim, a średnie najczęściej w regionie zachodnim. 

### <a name="page-4-of-our-report-is-titled-upcoming-opportunities"></a>Strona 4 raportu nosi nazwę „Nadchodzące szanse biznesowe”
Ponownie spoglądamy na podobne czynniki, jednak tym razem z perspektywy daty/czasu.  
![](media/sample-opportunity-analysis/opportunity6.png)

Dyrektor finansowy używa tej strony do zarządzania obciążeniami. Przyglądając się możliwościom uzyskiwania przychodów w podziale na miesiące i etapy sprzedaży, może odpowiednio planować.

* Średni przychód dla etapu finalizacji jest najwyższy. Realizacja tych transakcji ma najwyższy priorytet.
* Filtrując według miesięcy (przez wybranie nazwy miesiąca w lewym fragmentatorze), widzimy, że na styczeń przypada znaczna część dużych transakcji na etapie finalizacji o uwzględnianym przychodzie na poziomie 75 mln USD. Dla porównania, w lutym mamy przede wszystkim średnie transakcje na etapie rozwiązania i oferty.
* Ogólnie wysokość uwzględnianego przychodu waha się w zależności od etapu sprzedaży, liczby szans biznesowych i rozmiaru transakcji. Dodaj filtry (za pomocą okienka filtrowania po prawej stronie) dla tych czynników, aby poznać dodatkowe szczegółowe informacje.

Pracując na danych w tym środowisku, nie musisz się niczego obawiać. Zawsze możesz zrezygnować z zapisania wprowadzonych zmian. Jeśli jednak je zapiszesz, możesz przejść do obszaru **Pobieranie danych** i pobrać nową kopię zestawu danych użytego w tym przykładzie.

## <a name="next-steps-connect-to-your-data"></a>Następne kroki: łączenie z danymi
Mamy nadzieję, że dzięki temu przewodnikowi wiesz już, że pytania i odpowiedzi, raporty oraz pulpity nawigacyjne usługi Power BI mogą okazać się niezastąpione w uzyskiwaniu szczegółowych informacji pod kątem śledzenia szans biznesowych. Teraz Twoja kolej. Połącz się ze swoimi danymi. Usługa Power BI umożliwia nawiązanie połączenia z różnymi źródłami danych. Dowiedz się więcej o [rozpoczynaniu pracy z usługą Power BI](service-get-started.md).

[Pobierz przykłady](sample-datasets.md)  
