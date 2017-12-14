---
title: "Osadzanie raportu przy użyciu elementu iFrame"
description: "Instalacja serwera raportów usługi Power BI jest niezwykle szybka. Uwzględniając pobieranie, instalowanie i konfigurowanie, jego uruchomienie powinno zająć zaledwie kilka minut."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/09/2017
ms.author: asaxton
ms.openlocfilehash: df22a7ed0772979d164a9afae18f4931310ec4a1
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>Szybki start: osadzanie raportu usługi Power BI przy użyciu elementu iFrame i parametrów adresu URL

Każdy raport można osadzić w aplikacji przy użyciu elementu iFrame. 

## <a name="url-parameter"></a>Parametr adresu URL

Do dowolnego adresu URL do raportu można dodać parametr querystring `?rs:Embed=true`.

Na przykład:

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

Będzie to działać dla wszystkich typów raportów w ramach Serwera raportów usługi Power BI.

## <a name="iframe"></a>Element iFrame

Po utworzeniu adres URL na stronie internetowej można utworzyć element iFrame do obsługi raportu.

Na przykład:

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>Filtr adresu URL

Do adresu URL możesz dodać parametr ciągu zapytania w celu filtrowania danych, które są zwracane w raporcie usługi Power BI.

Składnia jest bardzo prosta: zacznij od adresu URL raportu, dodaj znak zapytania, a następnie filtr o następującej składni.

URL?filter=***Tabela***/***Pole*** eq '***wartość***'

Należy pamiętać o następujących kwestiach:

- W nazwach **tabeli** i **pola** uwzględniana jest wielkość liter, w przypadku **wartości** wielkość liter nie jest uwzględniania.
- Można filtrować raport z polami ukrytymi dla widoku raportu.
- **Wartość** musi być ujęta w apostrofy.
- Typ pola musi być ciągiem.
- Nazwy tabeli i pola nie mogą zawierać spacji.

###  <a name="example-filter-on-a-field"></a>Przykład: filtrowanie według pola

Weźmy na przykład [próbkę danych do analizy handlu detalicznego](../sample-datasets.md). Załóżmy, że to jest adres URL do raportu na serwerze raportów w folderze o nazwie „power bi”:

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

Widzimy, że wizualizacja mapy w próbce danych do analizy handlu detalicznego pokazuje sklepy w Karolinie Północnej i innych stanach.

![Wizualizacja mapy próbki danych do analizy handlu detalicznego](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

*NC* oznacza wartość przypisaną dla Karoliny Północnej przechowywaną w polu **Territory** tabeli **Store**. Aby zastosować filtrowanie raportu w celu uwzględnienia wyłącznie danych dla sklepów w Karolinie Północnej, dołącz następujący ciąg do adresu URL:

?filter=Store/Territory eq 'NC'

Raport jest filtrowany pod kątem Karoliny Północnej; wszystkie wizualizacje na stronie raportu wyświetlają dane dotyczące tylko Karoliny Północnej.

![Odfiltrowane wizualizacje próbki danych do analizy handlu detalicznego](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>Tworzenie formuły języka DAX w celu filtrowania z użyciem wielu wartości

Innym sposobem filtrowania z użyciem wielu pól jest utworzenie kolumny obliczeniowej w programie Power BI Desktop łączącej dwa pola w pojedynczą wartość. Następnie można filtrować według tej wartości.

Na przykład próbka danych do analizy handlu detalicznego ma dwa pola: Terytorium i Sieć. W programie Power BI Desktop możesz [utworzyć kolumnę obliczeniową](../desktop-tutorial-create-calculated-columns.md) (pole) o nazwie Terytorium_Sieć. Należy pamiętać, że nazwa **pola** nie może zawierać spacji. Oto formuła języka DAX dla tej kolumny.

Terytorium_Sieć = [Terytorium] & "-" & [Sieć]

Opublikuj raport na serwerze raportów usługi Power BI, a następnie użyj ciągu zapytania adresu URL, aby przefiltrować dane w celu wyświetlenia wyłącznie sklepów Lindseys w Karolinie Północnej (NC).

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>Następne kroki

[Szybki start: tworzenie raportu usługi Power BI dla serwera raportów usługi Power BI](quickstart-create-powerbi-report.md)  
[Szybki start: tworzenie raportu z podziałem na strony dla serwera raportów usługi Power BI](quickstart-create-paginated-report.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)