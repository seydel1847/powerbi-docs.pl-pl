---
title: Dodawanie parametrów raportu usługi Power BI przy użyciu adresu URL
description: Filtrowanie raportu przy użyciu parametrów ciągu zapytania adresu URL oraz możliwość filtrowania według więcej niż jednego pola.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/11/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 071f7ea0c324ec8fe0160766f65cf929f811362a
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="filter-a-report-using-query-string-parameters-in-the-url"></a>Filtrowanie raportu za pomocą parametrów ciągu zapytania w adresie URL
Po otwarciu raportu w usłudze Power BI każda strona raportu ma własny unikatowy adres URL. Aby wykonać filtrowanie takiej strony raportu, możesz użyć okienka Filtr na kanwie raportów.  Możesz też dodać parametry ciągu zapytania do adresu URL. Być może masz raport, który chcesz pokazać współpracownikom, ale najpierw planujesz go wstępnie przefiltrować. Jeden ze sposobów polega na tym, aby rozpocząć od domyślnego adresu URL raportu, dodać do niego parametry filtru, a następnie po prostu wysłać cały adres URL swoim współpracownikom za pośrednictwem poczty e-mail.

![Raport usługi Power BI w usłudze](media/service-url-filters/power-bi-report2.png)

<iframe width="640" height="360" src="https://www.youtube.com/embed/WQFtN8nvM4A?list=PLv2BtOtLblH3YE_Ycas5B1GtcoFfJXavO&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="query-string-parameter-syntax-for-filtering"></a>Składnia parametru ciągu zapytania dotycząca filtrowania
Składnia jest dość prosta: zacznij od adresu URL raportu, dodaj znak zapytania, a następnie filtr o wybranej składni.

URL?filter=***Tabela***/***Pole*** eq '***wartość***'

![Adres URL z filtrem](media/service-url-filters/power-bi-filter-urls7b.png)

* W nazwach **tabeli** i **pola** wielkość liter jest uwzględniana, w przypadku **wartości** wielkość liter nie jest istotna.
* Pola ukryte w widoku raportu mogą być nadal filtrowane.
* **Wartość** musi być ujęta w apostrofy.
* Typ pola musi być liczbą lub ciągiem
* Nazwy tabeli i pola nie mogą zawierać spacji.

Jeśli nadal masz jakieś wątpliwości, czytaj dalej, aby uzyskać bardziej szczegółowe informacje.  

## <a name="filter-on-a-field"></a>Filtrowanie według pola
Załóżmy, że adres URL raportu wygląda następująco.

![początkowy adres URL](media/service-url-filters/power-bi-filter-urls6.png)

Na przedstawionej wizualizacji mapy (patrz powyżej) widać, że w Karolinie Północnej są zlokalizowane sklepy.

>[!NOTE]
>Ten przykład jest oparty na [próbce analizy handlu detalicznego](sample-datasets.md).
> 

Aby zastosować filtrowanie raportu w celu uwzględnienia wyłącznie danych dla sklepów w Karolinie Północnej („NC”), dołącz następujący ciąg do adresu URL:

?filter=Store/Territory eq 'NC'

![Adres URL z filtrem](media/service-url-filters/power-bi-filter-urls7.png)

>[!NOTE]
>*NC* oznacza wartość przechowywaną w polu **Territory** tabeli **Store**.
> 
> 

Raport jest filtrowany pod kątem Karoliny Północnej; wszystkie wizualizacje na stronie raportu wyświetlają wyłącznie dane dotyczące Karoliny Północnej.

![](media/service-url-filters/power-bi-report4.png)

## <a name="filter-on-multiple-fields"></a>Filtrowanie według wielu pól
Można również filtrować według wielu pól, dodając dodatkowe parametry do adresu URL. W tym celu należy przejść do pierwotnego parametru filtru.

```
?filter=Store/Territory eq 'NC'
```

Aby filtrować dodatkowe pola, dodaj `and` i inne pole w tym samym formacie jak powyżej. Oto przykład:

```
?filter=Store/Territory eq 'NC' and Store/Chain eq 'Fashions Direct'
```

<iframe width="640" height="360" src="https://www.youtube.com/embed/0sDGKxOaC8w?showinfo=0" frameborder="0" allowfullscreen></iframe>


### <a name="using-dax-to-filter-on-multiple-values"></a>Korzystanie z języka DAX w celu filtrowania według wielu pól
Innym sposobem filtrowania z użyciem wielu pól jest utworzenie kolumny obliczeniowej łączącej dwa pola w pojedynczą wartość. Następnie można filtrować według tej wartości.

Istnieją dwa pola: Territory i Chain. W programie Power BI Desktop [utwórz nową kolumnę obliczeniową](desktop-tutorial-create-calculated-columns.md) (pole) o nazwie TerritoryChain. Należy pamiętać, że nazwa **pola** nie może zawierać spacji. Oto formuła języka DAX dla tej kolumny.

TerritoryChain = [Territory] & " - " & [Chain]

Opublikuj raport w usłudze Power BI, a następnie użyj ciągu zapytania adresu URL, aby przefiltrować dane w celu wyświetlenia wyłącznie sklepów Lindseys w Karolinie Północnej (NC).

    https://app.powerbi.com/groups/me/reports/8d6e300b-696f-498e-b611-41ae03366851/ReportSection3?filter=Store/TerritoryChain eq 'NC–Lindseys'

## <a name="pin-a-tile-from-a-filtered-report"></a>Przypinanie kafelka z filtrowanego raportu
Po przefiltrowaniu raportu za pomocą parametrów ciągu zapytania możesz przypiąć wizualizację z tego raportu do pulpitu nawigacyjnego. Kafelek na pulpicie nawigacyjnym wyświetli odfiltrowane dane, a wybranie tego kafelka pulpitu nawigacyjnego spowoduje otwarcie raportu, który został użyty do jego utworzenia.  Filtrowanie wykonane za pomocą adresu URL nie jest zapisywane wraz z raportem, a po wybraniu kafelka pulpitu nawigacyjnego raport otworzy się w stanie sprzed filtrowania.  Oznacza to, że dane wyświetlane na kafelku pulpitu nawigacyjnego nie będą odpowiadały danym wyświetlanym w wizualizacji raportu.

W niektórych przypadkach może okazać się to przydatne. Na przykład, gdy chcesz wyświetlić różne wyniki: filtrowane na pulpicie nawigacyjnym i niefiltrowane w raporcie.

## <a name="limitations-and-troubleshooting"></a>Ograniczenia i rozwiązywanie problemów
Używając parametrów ciągu zapytania, należy pamiętać o kilku rzeczach.

* Filtrowanie ciągu zapytania nie działa z adresami URL [publikowania w Internecie](service-publish-to-web.md) ani usługą Power BI Embedded.   
* Typ pola musi być liczbą lub ciągiem.
* Nazwy tabeli i pola nie mogą zawierać spacji.

## <a name="next-steps"></a>Następne kroki
[Przypinanie wizualizacji do pulpitu nawigacyjnego](service-dashboard-pin-tile-from-report.md)  
[Wypróbuj bezpłatnie!](https://powerbi.com/)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

