---
title: Błyskawiczne doskonałe raporty na podstawie skoroszytów programu Excel
description: Błyskawiczne doskonałe raporty na podstawie skoroszytów programu Excel
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/28/2018
ms.author: mihart
LocalizationGroup: Data from files
ms.openlocfilehash: f24d4055bd5fcf5fdee058112c268a1a0e197012
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34247177"
---
# <a name="from-excel-workbook-to-stunning-report-in-no-time"></a>Błyskawiczne doskonałe raporty na podstawie skoroszytów programu Excel
Twój kierownik chce zobaczyć raport o najnowszych wynikach sprzedaży połączony z wrażeniami z ostatniej kampanii do końca dnia. Ale najnowsze dane znajdują się w różnych systemach innych firm i w plikach na Twoim laptopie. W przeszłości trzeba było poświęcić godziny na tworzenie elementów wizualnych i formatowanie raportu. Zaczynasz się niepokoić.

Bez obaw. Usługa Power BI pozwala od ręki utworzyć doskonały raport.

W tym przykładzie przekażemy plik programu Excel z systemu lokalnego, utworzymy nowy raport i udostępnimy go współpracownikom — wszystko z poziomu usługi Power BI.

## <a name="prepare-your-data"></a>Przygotowywanie danych
Jako przykład weźmy prosty plik programu Excel. Przed załadowaniem pliku programu Excel do usługi Power BI musisz uporządkować dane w postaci płaskiej tabeli. Oznacza to, że każda kolumna zawiera ten sam typ danych — na przykład tekst, datę, liczbę lub walutę. Musisz mieć wiersz nagłówka, ale nie powinno być żadnej kolumny ani wiersza, które zawierają sumy.

![dane zorganizowane w programie Excel](media/service-from-excel-to-stunning-report/pbi_excel_file.png)

Następnie sformatuj swoje dane jako tabelę. W programie Excel na karcie Narzędzia główne w grupie Style wybierz pozycję **Formatuj jako tabelę**. Wybierz styl tabeli, który ma być zastosowany do arkusza. Arkuszu programu Excel jest teraz gotowy do załadowania do usługi Power BI.

![dane sformatowane jako tabela](media/service-from-excel-to-stunning-report/pbi_excel_table.png)

## <a name="upload-your-excel-file-into-power-bi"></a>Przekazywanie pliku programu Excel do usługi Power BI
Usługa Power BI łączy wiele źródeł danych, w tym pliki programu Excel znajdujące się na Twoim komputerze. Aby rozpocząć, zaloguj się do usługi Power BI. Jeżeli jeszcze nie została przeprowadzona rejestracja, [możesz to zrobić za darmo](https://powerbi.com).

Chcesz utworzyć nowy pulpit nawigacyjny. Otwórz pozycję **Mój obszar roboczy** i wybierz ikonę **+ Utwórz**.

![Ikona tworzenia](media/service-from-excel-to-stunning-report/power-bi-new-dash.png)

Wybierz pozycję **Pulpit nawigacyjny**, wprowadź nazwę i wybierz pozycję **Utwórz**. Zostanie wyświetlony nowy pulpit nawigacyjny — bez danych.

![Lista rozwijana tworzenia](media/service-from-excel-to-stunning-report/power-bi-create-dash.png)

Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie. Na stronie Pobierz dane w obszarze Import lub Połącz z danymi w polu Pliki wybierz **Pobierz**.

![Pobieranie danych z plików](media/service-from-excel-to-stunning-report/pbi_get_files.png)

Na stronie Pliki wybierz **plik lokalny**. Przejdź do pliku skoroszytu programu Excel na swoim komputerze i zaznacz go do załadowania do usługi Power BI. Wybierz pozycję **Import**.

> **UWAGA**: Aby skorzystać z pozostałej części tego samouczka, należy użyć [Przykładowego skoroszytu finansowego](sample-financial-download.md).
> 
> 

![Okno Pobierz dane > Pliki](media/service-from-excel-to-stunning-report/pbi_local_file.png)

## <a name="build-your-report"></a>Tworzenie raportu
Gdy usługa Power BI zaimportuje plik programu Excel, zacznij tworzyć raport. Gdy pojawi się komunikat **Zestaw danych jest gotowy**, wybierz pozycję **Widok zestawu danych**.  Usługa Power BI otworzy się w widoku do edycji i wyświetl kanwę raportu. Po prawej stronie znajdują się okienka Wizualizacje, Filtry i Pola.

Należy zauważyć, że Twoje dane tabeli skoroszytu programu Excel zostaną wyświetlone w okienku Pola. W obszarze nazwy tabeli usługa Power BI wyświetla nagłówki kolumn jako oddzielne pola.

![jak wyglądają dane programu Excel w okienku Pola](media/service-from-excel-to-stunning-report/pbi_report_fields.png)

Teraz możesz rozpocząć tworzenie wizualizacji. Twój kierownik chce zobaczyć zysk w funkcji czasu. W okienku Pola przeciągnij pozycję **Zysk** na kanwę raportu. Domyślnie usługa Power BI wyświetla wykres słupkowy. Następnie przeciągnij pozycję **Data** na kanwę raportu. Usługa Power BI aktualizuje wykres słupkowy, aby pokazać zysk według daty.

![wykres kolumnowy w edytorze raportów](media/service-from-excel-to-stunning-report/pbi_report_pin-new.png)

> **PORADA**: Jeśli wykres nie wygląda jak oczekiwano, sprawdź swoje agregacje. Na przykład w źródle **Wartość** kliknij prawym przyciskiem myszy właśnie dodane pole i upewnij się, że dane są agregowane w należyty sposób.  W tym przykładzie używamy pozycji **Suma**.
> 
> 

Twój kierownik chce wiedzieć, które kraje są najbardziej dochodowe. Zrób na nim wrażenie wizualizacją mapy. Wybierz pusty obszar na kanwie, a następnie z okienka Pola przeciągnij pola **Kraj**, a następnie **Zysk**. Usługa Power BI tworzy element wizualny mapy z dymkami reprezentującymi względny zysk w każdej lokalizacji.

![element wizualny mapy w edytorze raportów](media/service-from-excel-to-stunning-report/pbi_report_map-new.png)

A co z wyświetlaniem elementu wizualnego pokazującego sprzedaż według produktu i segmentu rynku? Łatwe. W okienku Pola zaznacz pola wyboru obok pól Sprzedaż, Produkt i Segment. Usługa Power BI natychmiast utworzy wykres słupkowy. Zmień typ wykresu, wybierając jedną z ikon w menu Wizualizacje. Na przykład zmień go na skumulowany wykres słupkowy.  Aby posortować wykres, wybierz wielokropek (...) > **Sortuj według**.

![skumulowany wykres kolumnowy w edytorze raportów](media/service-from-excel-to-stunning-report/pbi_barchart-new.png)

Przypnij wszystkie swoje elementy wizualne do pulpitu nawigacyjnego. Możesz już udostępnić go współpracownikom.

![pulpit nawigacyjny z przypiętymi trzema elementami wizualnymi](media/service-from-excel-to-stunning-report/pbi_report.png)

## <a name="share-your-dashboard"></a>Udostępnianie pulpitu nawigacyjnego
Chcesz udostępnić pulpit nawigacyjny swojej kierowniczce Pauli. Możesz udostępnić pulpit nawigacyjny i źródłowy raport wszelkim współpracownikom, którzy mają konto usługi Power BI. Mogą oni wchodzić w interakcje z Twoim raportem, ale nie mogą zapisać zmian.

Aby udostępnić raport, w górnej części pulpitu nawigacyjnego wybierz pozycję **Udostępnij**.

![Ikona udostępniania](media/service-from-excel-to-stunning-report/power-bi-share.png)

Usługa Power BI wyświetli stronę Udostępnianie pulpitu nawigacyjnego. W górnym obszarze wprowadź adresy e-mail adresatów. Dodaj komunikat w polu poniżej. Aby umożliwić odbiorcom udostępnianie Twojego pulpitu nawigacyjnego innym osobom, wybierz pozycję **Zezwalaj adresatom na udostępnianie pulpitu nawigacyjnego**. Wybierz pozycję **Udostępnij**.

![Okno Udostępnij pulpit nawigacyjny](media/service-from-excel-to-stunning-report/power-bi-share-dash-new.png)

Następne kroki

* [Wprowadzenie do usługi Power BI](service-get-started.md)
* [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md)
* [Power BI — podstawowe pojęcia](service-basic-concepts.md)
* Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

