---
title: Pobieranie danych z plików dla usługi Power BI
description: Dowiedz się, jak pobierać dane z plików programów Excel i Power BI Desktop oraz z plików CSV do usługi Power BI
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: cbf0550c12fad37af528622b35584898b3a697f4
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282338"
---
# <a name="get-data-from-files-for-power-bi"></a>Pobieranie danych z plików dla usługi Power BI
![](media/service-get-data-from-files/file_icons.png)

W usłudze Power BI można tworzyć połączenia z trzema typami plików lub importować z nich dane i raporty.

* Microsoft Excel (xlsx lub xlsm)
* Power BI Desktop (pbix)
* Wartości rozdzielane przecinkami (csv)

## <a name="what-does-get-data-from-a-file-really-mean"></a>Co tak naprawdę oznacza „pobieranie danych z pliku”?
Dane eksplorowane w usłudze Power BI pochodzą z zestawu danych. Jednak aby mieć zestaw danych, najpierw trzeba pobrać trochę danych. W tym artykule skoncentrujemy się na pobieraniu danych z plików.

Aby lepiej zrozumieć znaczenie zestawów danych i to, jak pobieramy do nich dane, przyjrzyjmy się samochodowi. Usiądź w swoim samochodzie i przyjrzyj się desce rozdzielczej. Bardzo przypomina to siedzenie przed komputerem i patrzenie na pulpit nawigacyjny usługi Power BI. Deska rozdzielcza pokazuje wszystko, co robi samochód: jakie są obroty silnika i temperatura, jaki masz włączony bieg, jaka jest prędkość itd.

W usłudze Power BI zestaw danych jest jak silnik w samochodzie. Zestaw danych dostarcza dane, metryki i informacje wyświetlane na pulpicie nawigacyjnym usługi Power BI. Oczywiście silnik, czyli zestaw danych, potrzebuje paliwa, a w usłudze Power BI paliwem są dane. Samochód jest wyposażony w zbiornik, z którego paliwo jest dostarczane do silnika. Podobnie w usłudze Power BI potrzebny jest zbiornik zawierający dane, które można dostarczyć do zestawu danych. W naszym przypadku ten zbiornik jest plikiem programu Power BI Desktop, skoroszytem programu Excel lub plikiem CSV.

Możemy pójść nawet o krok dalej. Zbiornik w samochodzie trzeba napełniać paliwem. Paliwem dla naszego pliku programu Power BI Desktop, programu Excel lub pliku CSV są dane z innego źródła danych. Pobieramy dane z innego źródła danych i umieszczamy je w pliku programu Excel, programu Power BI Desktop lub w pliku CSV. Jeśli jest to skoroszyt programu Excel lub plik CSV, można ręcznie wprowadzić dane w wierszach. Możemy też utworzyć połączenie z zewnętrznym źródłem danych, aby wysyłać zapytania i ładować dane do naszego pliku. Gdy będziemy mieć plik z danymi, możemy pobrać je do usługi Power BI jako zestaw danych.

> [!NOTE]
> Aby można było importować dane ze skoroszytu programu Excel do usługi Power BI, muszą one znajdować się w tabeli lub w modelu danych.
> 
> 

## <a name="where-your-file-is-saved-makes-a-difference"></a>Miejsce zapisu pliku jest istotne
**Lokalnie** — jeśli zapiszesz plik na dysku lokalnym na komputerze lub w innej lokalizacji w organizacji, będzie można *zaimportować* plik do usługi Power BI z jej poziomu. Plik pozostanie na dysku lokalnym, więc tak naprawdę nie jest w całości importowany do usługi Power BI. Właściwie nowy zestaw danych jest tworzony w witrynie usługi Power BI, a dane oraz, w niektórych przypadkach, model danych, są ładowane do zestawu danych. Jeśli plik zawiera jakiekolwiek raporty, zostaną one wyświetlone w witrynie usługi Power BI w sekcji Raporty.

**OneDrive — dla firm** — jeśli masz usługę OneDrive dla Firm i zalogujesz się do niej przy użyciu tego samego konta, z którego korzystasz do logowania się w usłudze Power BI, zapewnisz najwydajniejszy sposób na utrzymanie synchronizacji pracy w pliku programu Excel, Power BI Desktop lub w pliku CSV z zestawem danych, raportami oraz pulpitami nawigacyjnymi w usłudze Power BI. Ponieważ usługi Power BI i OneDrive działają w chmurze, usługa Power BI łączy się z plikiem w usłudze OneDrive mniej więcej co godzinę. W przypadku wykrycia jakichkolwiek zmian zestaw danych, raporty i pulpity nawigacyjne zostaną automatycznie zaktualizowane w usłudze Power BI.

**OneDrive — dla osób prywatnych** — w przypadku zapisu plików na własnym koncie w usłudze OneDrive zapewnisz sobie wiele takich samych korzyści, jak w przypadku usługi OneDrive dla Firm. Największa różnica dotyczy pierwszego połączenia z plikiem (przy użyciu opcji Pobierz dane > Pliki > OneDrive — dla osób prywatnych), ponieważ trzeba zalogować się do usługi OneDrive przy użyciu konta Microsoft, które zazwyczaj różni się od konta używanego do logowania w usłudze Power BI. Podczas logowania do usługi OneDrive przy użyciu konta Microsoft należy wybrać opcję Nie wylogowuj mnie. Dzięki temu usługa Power BI będzie w stanie nawiązać połączenie z plikiem co godzinę i zapewnić synchronizację zestawu danych w usłudze Power BI.

**Witryny zespołu programu SharePoint** — zapisywanie plików programu Power BI Desktop w witrynach zespołu programu SharePoint jest bardzo podobne do zapisywania plików w usłudze OneDrive dla Firm. Największa różnica polega na sposobie nawiązywania połączenia z plikiem z poziomu usługi Power BI. Możesz określić adres URL lub połączyć się z folderem głównym.

## <a name="ready-to-get-started"></a>Możemy zaczynać?
Zobacz następujące artykuły, aby dowiedzieć się więcej o pobieraniu pliku do usługi Power BI.

* [Pobieranie danych z plików skoroszytów programu Excel](service-excel-workbook-files.md)
* [Pobieranie danych z plików programu Power BI Desktop](service-desktop-files.md)
* [Pobieranie danych z plików z wartościami rozdzielanymi przecinkami (csv)](service-comma-separated-value-files.md)

