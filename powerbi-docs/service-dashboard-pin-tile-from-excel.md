---
title: Przypinanie kafelka do pulpitu nawigacyjnego usługi Power BI z programu Excel
description: Przypnij kafelek do pulpitu nawigacyjnego usługi Power BI z programu Excel w usłudze OneDrive dla Firm. Przypinanie zakresów, wykresów, tabel
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: l8JoB7w0zJA
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 3bb151de24a984406aa6fd40a70977f2e9eaf1be
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2018
ms.locfileid: "46548056"
---
# <a name="pin-a-tile-to-a-power-bi-dashboard-from-excel"></a>Przypinanie kafelka do pulpitu nawigacyjnego usługi Power BI z programu Excel
Zanim będzie możliwe przypięcie kafelka ze skoroszytu programu Excel połącz ten skoroszyt z usługą Power BI (app.powerbi.com). Zasadniczo łączenie skoroszytu powoduje przeniesienie połączonej wersji tylko do odczytu tego skoroszytu do usługi Power BI i pozwala przypiąć zakresy do pulpitów nawigacyjnych. Możesz nawet przypiąć cały arkusz do pulpitu nawigacyjnego.  
Jeśli skoroszyt został Ci udostępniony, będziesz mieć możliwość wyświetlania kafelków przypiętych przez właściciela, ale nie samodzielnego tworzenia jakichkolwiek kafelków pulpitu nawigacyjnego. 

Aby uzyskać szczegółowe informacje o współdziałaniu programu Excel i usługi Power BI, zobacz [Pobieranie danych z plików skoroszytów programu Excel](http://go.microsoft.com/fwlink/?LinkID=521962).

Obejrzyj Willa demonstrującego kilka sposobów importowania danych ze skoroszytów programu Excel i łączenia się z nimi.

<iframe width="560" height="315" src="https://www.youtube.com/embed/l8JoB7w0zJA" frameborder="0" allowfullscreen></iframe>

## <a name="connect-your-excel-workbook-from-onedrive-for-business-to-power-bi"></a>Łączenie skoroszytu programu Excel z poziomu usługi OneDrive dla Firm z usługą Power BI
Po wybraniu pozycji **Połącz** skoroszyt pojawi się w usłudze Power BI, podobnie jak w programie Excel Online. Jednak, w przeciwieństwie do programu Excel Online, będziesz mieć dostęp do pewnych doskonałych funkcji ułatwiających przypinanie elementów z arkuszy bezpośrednio do pulpitów nawigacyjnych.

W usłudze Power BI nie możesz edytować swojego skoroszytu. Ale jeśli musisz wprowadzić pewne zmiany, możesz wybrać ikonę ołówka na karcie **Skoroszyty** swojego obszaru roboczego, a następnie wprowadzić zmiany do swojego skoroszytu w programie Excel Online lub otworzyć go w programie Excel na komputerze. Wszelkie wprowadzone zmiany są zapisywane w skoroszycie w usłudze OneDrive.

1. Przekaż swój skoroszyt do usługi OneDrive dla Firm.

2. Z usługi Power BI [połącz się z tym skoroszytem](service-excel-workbook-files.md). W tym celu wybierz opcję **Pobierz dane > Pliki > OneDrive — dla firm** i przejdź do lokalizacji, w której zapisano plik programu Excel. Zaznacz plik i wybierz polecenie **Połącz > Połącz**.

    ![Okno dialogowe usługi OneDrive dla Firm](media/service-dashboard-pin-tile-from-excel/power-bi-connect.png)

3. W usłudze Power BI skoroszyt jest dodawany do karty **Skoroszyty** Twojego obszaru roboczego.  Ikona ![ikona skoroszytu](media/service-dashboard-pin-tile-from-excel/pbi_workbookicon.png) wskazuje, że jest to skoroszyt programu Excel, a żółta gwiazdka wskazuje, że jest on nowy.
    
    ![karta skoroszytów](media/service-dashboard-pin-tile-from-excel/power-bi-workbooks.png)
4. Otwórz skoroszyt w usłudze Power BI, wybierając nazwę skoroszytu.

    Zmiany wprowadzone do skoroszytu w usłudze Power BI nie zostały zapisane i nie mają wpływu na oryginalny skoroszyt w usłudze OneDrive dla Firm. Jeśli sortujesz, filtrujesz lub zmieniasz wartości w usłudze Power BI, tych zmian nie można zapisać ani przypiąć. Jeśli musisz wprowadzić zmiany, które zostaną zapisane, wybierz opcję **Edytuj** w prawym górnym rogu, aby go otworzyć do edycji w programie Excel Online lub Excel. Po wprowadzonych w ten sposób zmianach czas potrzebny do zaktualizowania kafelków na pulpicie nawigacyjnym może potrwać kilka minut.
   
    ![Program Excel Online w usłudze Power BI](media/service-dashboard-pin-tile-from-excel/power-bi-opened.png)

## <a name="pin-a-range-of-cells-to-a-dashboard"></a>Przypinanie zakresu komórek do pulpitu nawigacyjnego
Jednym sposobem dodania nowego [kafelka pulpitu nawigacyjnego](consumer/end-user-tiles.md) jest realizowany z wnętrza skoroszytu programu Excel w usłudze Power BI. Zakresy można przypiąć ze skoroszytów programu Excel, które zostały zapisane w usłudze OneDrive dla Firm lub innej bibliotece dokumentów udostępnionych w grupie. Zakresy mogą zawierać dane, wykresy, tabele, tabele przestawne, wykresy przestawne i inne składniki programu Excel.

1. Wyróżnij komórki, które chcesz przypiąć do pulpitu nawigacyjnego.
   
    ![zaznaczanie komórek w skoroszycie programu Excel](media/service-dashboard-pin-tile-from-excel/pbi_selectrange.png)
2. Wybierz ikonę pinezki ![ikona przypinania](media/service-dashboard-pin-tile-from-excel/pbi_pintile_small.png) . 
3. Przypnij kafelek do istniejącego lub nowego pulpitu nawigacyjnego. 
   
   * Istniejący pulpit nawigacyjny: z listy rozwijanej wybierz nazwę pulpitu nawigacyjnego.
   * Nowy pulpit nawigacyjny: wpisz nazwę nowego pulpitu nawigacyjnego.
   
     ![Okno dialogowe opcji Przypnij do pulpitu nawigacyjnego](media/service-dashboard-pin-tile-from-excel/pbi_dashdialog1.png)
4. Wybierz pozycję **Przypnij**. Komunikat o powodzeniu (w prawym górnym rogu) informuje o tym, że zakres został dodany do pulpitu nawigacyjnego jako kafelek. 
   
    ![okno dialogowe Przypięto do pulpitu nawigacyjnego](media/service-dashboard-pin-tile-from-excel/power-bi-go-to-dashboard.png)
5. Wybierz pozycję **Przejdź do pulpitu nawigacyjnego**. W tym miejscu możesz [zmienić nazwę, rozmiar, link i przenieść](service-dashboard-edit-tile.md) przypiętą wizualizację. Domyślnie wybranie przypiętego kafelka otwiera skoroszyt w usłudze Power BI.

## <a name="pin-an-entire-table-or-pivottable-to-a-dashboard"></a>Przypinanie całej tabeli lub tabeli przestawnej do pulpitu nawigacyjnego
Wykonaj kroki opisane powyżej, z wyjątkiem tego, że zamiast zaznaczania zakresu komórek zaznacz całą tabelę lub tabelę przestawną.

Aby przypiąć tabelę, zaznacz cały zakres tabeli, pamiętając o uwzględnieniu nagłówków.  Aby przypiąć tabelę przestawną, upewnij się, że została uwzględniona każda widoczna część tabeli przestawnej łącznie z filtrami, jeśli były używane.

 ![zaznaczanie komórek](media/service-dashboard-pin-tile-from-excel/pbi_selecttable.png)

Kafelek utworzony na podstawie tabeli lub tabeli przestawnej wyświetli całą tabelę.  Jeśli dodasz/usuniesz/przefiltrujesz wiersze lub kolumny w oryginalnym skoroszycie, zostaną one również dodane/usunięte/przefiltrowane na kafelku.

## <a name="view-the-workbook-linked-to-the-tile"></a>Wyświetlanie skoroszytu połączonego z kafelkiem
Wybranie kafelka skoroszytu otwiera połączony skoroszyt w usłudze Power BI. Ponieważ plik skoroszytu znajduje się w usłudze OneDrive dla Firm właściciela, wyświetlenie skoroszytu wymaga posiadania uprawnienia do odczytu skoroszytu. Jeśli nie masz uprawnienia, otrzymasz komunikat o błędzie.  

 ![wideo](media/service-dashboard-pin-tile-from-excel/pin-from-excel.gif)

## <a name="considerations-and-troubleshooting"></a>Istotne zagadnienia i rozwiązywanie problemów
Nieobsługiwane funkcje: usługa Power BI korzysta z usług programu Excel do pobierania kafelków skoroszytu. W związku z tym, ponieważ niektóre funkcje programu Excel nie są obsługiwane w interfejsie API REST usług programu Excel, nie będą widoczne na kafelkach w usłudze Power BI. Na przykład: wykresy przebiegu w czasie, zestaw ikon formatowania warunkowego i fragmentatory czasu. Aby uzyskać pełną listę nieobsługiwanych funkcji, zobacz [Nieobsługiwane funkcje w interfejsie API REST usług programu Excel](http://msdn.microsoft.com/library/office/ff394477.aspx)

## <a name="next-steps"></a>Następne kroki
[Udostępnianie pulpitu nawigacyjnego, który zawiera linki do skoroszytu programu Excel](service-share-dashboard-that-links-to-excel-onedrive.md)

[Pobieranie danych ze skoroszytów programu Excel](service-excel-workbook-files.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

