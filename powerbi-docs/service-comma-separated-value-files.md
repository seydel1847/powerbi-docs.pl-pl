---
title: Pobieranie danych z plików z wartościami rozdzielanymi przecinkami (csv)
description: Dowiedz się, jak pobierać dane z plików CSV do usługi Power BI
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 194993f1cd27e173b831850639b8e88a43b3f5aa
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34243387"
---
# <a name="get-data-from-comma-separated-value-csv-files"></a>Pobieranie danych z plików z wartościami rozdzielanymi przecinkami (csv)
![](media/service-comma-separated-value-files/csv_icon.png)

Pliki z wartościami rozdzielanymi przecinkami, często nazywane plikami CSV, to proste pliki tekstowe z wierszami danych, w których każda wartość jest oddzielona przecinkiem. Te typy plików mogą zawierać bardzo duże ilości danych zgromadzonych w pliku o względnie niewielkim rozmiarze, co sprawia, że są idealnym źródłem danych dla usługi Power BI. Przykładowy plik CSV można pobrać [tutaj](http://go.microsoft.com/fwlink/?LinkID=619356).

Jeśli masz plik CSV, nadszedł czas na przesłanie go jako zestawu danych do witryny usługi Power BI, w której będzie można rozpocząć eksplorowanie danych, tworzenie pulpitów nawigacyjnych i udostępnianie szczegółowych danych innym osobom.

>[!TIP]
>Wiele organizacji codziennie wydaje pliki CSV ze zaktualizowanymi danymi. Aby upewnić się, że zestaw danych w usłudze Power BI jest zsynchronizowany ze zaktualizowanym plikiem, należy zapisać plik w usłudze OneDrive, korzystając z tej samej nazwy.

## <a name="where-your-file-is-saved-makes-a-difference"></a>Miejsce zapisu pliku jest istotne
**Lokalne** — jeśli zapiszesz plik CSV na dysku lokalnym na komputerze lub w innej lokalizacji w organizacji, będziesz w stanie *zaimportować* plik do usługi Power BI z jej poziomu. Plik pozostanie na dysku lokalnym, więc tak naprawdę nie jest w całości importowany do usługi Power BI. Zamiast tego w usłudze Power BI zostaje utworzony nowy zestaw danych, a dane z pliku CSV są do niego ładowane.

**OneDrive — firmowe** — jeśli masz usługę OneDrive dla Firm i zalogujesz się do niej przy użyciu tego samego konta, z którego korzystasz do logowania się w usłudze Power BI, zapewnisz najwydajniejszy sposób na utrzymanie synchronizacji pliku CSV i zestawu danych, raportów oraz pulpitów nawigacyjnych w usłudze Power BI. Ponieważ usługi Power BI i OneDrive działają w chmurze, usługa Power BI *łączy się* z plikiem w usłudze OneDrive mniej więcej co godzinę. W przypadku wykrycia jakichkolwiek zmian zestaw danych, raporty i pulpity nawigacyjne zostaną automatycznie zaktualizowane w usłudze Power BI.

**OneDrive — dla osób prywatnych** — w przypadku zapisu plików na własnym koncie w usłudze OneDrive zapewnisz sobie wiele takich samych korzyści, jak w przypadku usługi OneDrive dla Firm. Największa różnica dotyczy pierwszego połączenia z plikiem (przy użyciu opcji Pobierz dane > Pliki > OneDrive — dla osób prywatnych), ponieważ trzeba zalogować się do usługi OneDrive przy użyciu konta Microsoft, które zazwyczaj różni się od konta używanego do logowania w usłudze Power BI. Podczas logowania do usługi OneDrive przy użyciu konta Microsoft należy wybrać opcję Nie wylogowuj mnie. Dzięki temu usługa Power BI będzie w stanie nawiązać połączenie z plikiem co godzinę i zapewnić synchronizację zestawu danych w usłudze Power BI.

**Witryny zespołu programu SharePoint** — zapisywanie plików programu Power BI Desktop w witrynach zespołu programu SharePoint jest bardzo podobne do zapisywania plików w usłudze OneDrive dla Firm. Największa różnica polega na sposobie nawiązywania połączenia z plikiem z poziomu usługi Power BI. Możesz określić adres URL lub połączyć się z folderem głównym.

## <a name="import-or-connect-to-a-csv-file"></a>Importowanie pliku CSV lub nawiązywanie z nim połączenia
>[!IMPORTANT]
>Maksymalny rozmiar pliku, który można zaimportować do usługi Power BI, to 1 GB.

1. W usłudze Power BI w okienku nawigatora kliknij polecenie **Pobierz dane**.
   
   ![](media/service-comma-separated-value-files/csv_get_data_button.png)
2. W sekcji **Pliki** kliknij polecenie **Pobierz**.
   
   ![](media/service-comma-separated-value-files/csv_files_get.png)
3. Znajdź plik.
   
   ![](media/service-comma-separated-value-files/csv_find_your_file.png)

## <a name="next-steps"></a>Następne kroki
**Eksploruj dane** — po pobraniu danych z pliku do usługi Power BI nadszedł czas na ich eksplorowanie. Po prostu kliknij nowy zestaw danych prawym przyciskiem myszy, a następnie kliknij polecenie **Eksploruj**.

**Zaplanuj odświeżanie** — jeśli plik jest zapisany na dysku lokalnym, możesz skonfigurować zaplanowane odświeżanie, aby zestaw danych i raporty w usłudze Power BI pozostały aktualne. Aby dowiedzieć się więcej, zobacz [Data refresh in Power BI (Odświeżanie danych w usłudze Power BI)](refresh-data.md). Jeżeli plik jest zapisany w usłudze OneDrive, usługa Power BI będzie automatycznie synchronizować się z plikiem mniej więcej co godzinę.

