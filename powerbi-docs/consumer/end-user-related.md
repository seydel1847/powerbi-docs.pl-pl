---
title: Wyświetlanie powiązanej zawartości w usłudze Power BI
description: Jeszcze łatwiejsza nawigacja — wyświetlanie powiązanej zawartości w pulpitach nawigacyjnych, raportach i zestawach danych
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: 7bb46bbed79be32b45fe4e5dbd2ecb07acc5d673
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46566400"
---
# <a name="view-related-content-in-power-bi-service"></a>Wyświetlanie powiązanej zawartości w usłudze Power BI
Okienko **Powiązana zawartość** wyświetla sposób połączenia między różnymi zawartościami usługi Power BI — pulpitami nawigacyjnymi, raportami i zestawami danych.  Co więcej z tego okienka możesz wykonywać typowe zadania, np. odświeżanie, zmienianie nazw, generowanie szczegółowych informacji i wiele innych. Wybierz powiązany raport lub pulpit nawigacyjny, a zostanie on otworzony w obszarze roboczym usługi Power BI.   

Prawdopodobnie już wiesz, że raporty są tworzone w oparciu o zestawy danych, następnie wizualizacje raportów są przypinane do pulpitów nawigacyjnych, po czym elementy wizualne pulpitów nawigacyjnych prowadzą z powrotem do raportów. Niemniej jak można dowiedzieć się, które pulpity nawigacyjne hostują wizualizacje z raportu Marketing? Jak zlokalizować te pulpity nawigacyjne? Czy pulpit nawigacyjny Zakupy używa wizualizacji z więcej niż jednego zestawu danych? Jeśli tak, jak się nazywają oraz jak można je otworzyć i edytować? Czy zestaw danych HR jest używany w jakichkolwiek raportach lub pulpitach nawigacyjnych? Można go przenieść bez powstawania niedziałających połączeń? Na pytania tego typu można znaleźć odpowiedzi w okienku **Powiązana zawartość**.  Okienko nie tylko wyświetla powiązaną zawartość, ale też umożliwia podejmowanie działań wobec zawartości i łatwe nawigowanie wśród powiązanych zawartości.

![powiązana zawartość](./media/end-user-related/power-bi-view-related-dashboard-new.png)

> [!NOTE]
> Funkcja powiązanej zawartości nie działa w przypadku strumieniowych zestawów danych.
> 
> 

## <a name="view-related-content-for-a-dashboard"></a>Wyświetlanie powiązanej zawartości pulpitu nawigacyjnego
Zobacz, jak Will wyświetla powiązaną zawartość pulpitu nawigacyjnego. Następnie wykonaj szczegółowe instrukcje poniżej filmu, aby spróbować samodzielnie wykonać tę procedurę, korzystając z przykładowego zestawu danych Procurement Analysis.

<iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M#t=3m05s" frameborder="0" allowfullscreen></iframe>


Musisz mieć co najmniej uprawnienia do *wyświetlania* pulpitu nawigacyjnego, aby otworzyć okienko **Powiązana zawartość**. W tym przykładzie używamy [próbki Procurement Analysis](../sample-procurement.md).

**Metoda 1**

W obszarze roboczym wybierz kartę **Pulpity nawigacyjne**, a następnie wybierz ikonę **Wyświetl powiązane** ![ikona Wyświetl powiązane](./media/end-user-related/power-bi-view-related-icon-new.png).

![Karta pulpitu nawigacyjnego](./media/end-user-related/power-bi-view-related-dash-newer.png)

<br>

**Metoda 2**

Po otwarciu pulpitu nawigacyjnego wybierz   ![ikonę Wyświetl powiązane](./media/end-user-related/power-bi-view-related-new.png) z górnego menu.

Zostanie otwarte okienko **Powiązana zawartość**. Przedstawia ono wszystkie raporty zawierające wizualizacje przypięte do pulpitu nawigacyjnego oraz skojarzone zestawy danych. W przypadku tego pulpitu nawigacyjnego istnieją wizualizacje przypięte z trzech różnych raportów, a te raporty są oparte na trzech różnych zestawach danych.

![Okienko powiązanej zawartości](./media/end-user-related/power-bi-view-related-dashboard-new.png)

W tym miejscu możesz podjąć bezpośrednie działanie wobec powiązanej zawartości.  Na przykład wybierz nazwę raportu, aby go otworzyć.  W przypadku raportu na liście wybierz ikonę [analizy w programie Excel](../service-analyze-in-excel.md), [zmiany nazwy](../service-rename.md) lub [pobrania informacji szczegółowych](end-user-insights.md). W przypadku zestawu danych wybierz ikonę [tworzenia nowego raportu](../service-report-create-new.md), [odświeżenia](../refresh-data.md), zmiany nazwy, [analizy w programie Excel](../service-analyze-in-excel.md), [pobrania informacji szczegółowych](end-user-insights.md) lub otwórz okno **Ustawienia** dla zestawu danych.  

## <a name="view-related-content-for-a-report"></a>Wyświetlanie powiązanej zawartości raportu
Musisz mieć co najmniej uprawnienia do *wyświetlania* raportu, aby otworzyć okienko **Powiązana zawartość**. W tym przykładzie używamy [próbki Procurement Analysis](../sample-procurement.md).

**Metoda 1**

W obszarze roboczym wybierz kartę **Raporty**, a następnie wybierz ikonę **Wyświetl powiązane** ![ikona Wyświetl powiązane](./media/end-user-related/power-bi-view-related-icon-new.png).

![Karta Raporty](./media/end-user-related/power-bi-view-related-report-newer.png)

<br>

**Metoda 2**

Otwórz raport w [Widoku do czytania](end-user-reading-view.md) i wybierz ikonę ![ikona Wyświetl powiązane](./media/end-user-related/power-bi-view-related-new.png) z górnego menu.

Zostanie otwarte okienko **Powiązana zawartość**. Przedstawia ono skojarzony zestaw danych oraz wszystkie pulpity nawigacyjne, które mają przypięty co najmniej jeden kafelek z tego raportu. W przypadku tego raportu istnieją wizualizacje przypięte do dwóch różnych pulpitów nawigacyjnych.

![Okienko powiązanej zawartości](./media/end-user-related/power-bi-view-related-report.png)

W tym miejscu możesz podjąć bezpośrednie działanie wobec powiązanej zawartości.  Na przykład wybierz nazwę pulpitu nawigacyjnego, aby go otworzyć.  W przypadku dowolnego pulpitu nawigacyjnego na liście wybierz ikonę, aby [udostępnić pulpit nawigacyjny innym osobom](../service-share-dashboards.md) lub otwórz okno **Ustawienia** dla pulpitu nawigacyjnego. W przypadku zestawu danych wybierz ikonę [tworzenia nowego raportu](../service-report-create-new.md), [odświeżenia](../refresh-data.md), zmiany nazwy, [analizy w programie Excel](../service-analyze-in-excel.md), [pobrania informacji szczegółowych](end-user-insights.md) lub otwórz okno **Ustawienia** dla zestawu danych.  

## <a name="view-related-content-for-a-dataset"></a>Wyświetlanie powiązanej zawartości zestawu danych
Musisz mieć co najmniej uprawnienia do *wyświetlania* zestawu danych, aby otworzyć okienko **Powiązana zawartość**. W tym przykładzie używamy [próbki Procurement Analysis](../sample-procurement.md).

W obszarze roboczym wybierz kartę **Zestawy danych**, a następnie znajdź ikonę **Wyświetl powiązane** ![ikona Wyświetl powiązane](./media/end-user-related/power-bi-view-related-icon-new.png).

![Karta Zbiory danych](./media/end-user-related/power-bi-view-related-dataset-newer.png)

Wybierz ikonę, aby otworzyć okienko **Powiązana zawartość**.

![](media/end-user-related/power-bi-datasets.png)

W tym miejscu możesz podjąć bezpośrednie działanie wobec powiązanej zawartości.  Na przykład wybierz nazwę pulpitu nawigacyjnego lub raportu, aby go otworzyć.  W przypadku dowolnego pulpitu nawigacyjnego na liście wybierz ikonę, aby [udostępnić pulpit nawigacyjny innym osobom](../service-share-dashboards.md) lub otwórz okno **Ustawienia** dla pulpitu nawigacyjnego. W przypadku raportu wybierz ikonę [analizy w programie Excel](../service-analyze-in-excel.md), [zmiany nazwy](../service-rename.md) lub [pobrania informacji szczegółowych](end-user-insights.md).  

## <a name="limitations-and-troubleshooting"></a>Ograniczenia i rozwiązywanie problemów
* Jeśli Twoja przeglądarka nie ma wystarczającej ilości miejsca, nie zobaczysz opcji **Wyświetl powiązane**, ale nadal będzie wyświetlana ikona ![ikona Wyświetl powiązane](./media/end-user-related/power-bi-view-related-icon-new.png). Wybierz ikonę, aby otworzyć okienko **Powiązana zawartość**.
* Aby otworzyć okienko Powiązana zawartość dla raportu, musisz pracować w [Widoku odczytu](end-user-reading-view.md).
* Zawartość powiązana nie jest dostępna w aplikacji Power BI Desktop.
* Funkcja powiązanej zawartości nie działa w przypadku strumieniowych zestawów danych.

## <a name="next-steps"></a>Następne kroki
* [Wprowadzenie do usługi Power BI](../service-get-started.md)
* Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

