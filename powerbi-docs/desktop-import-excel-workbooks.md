---
title: Importowanie skoroszytów programu Excel do programu Power BI Desktop
description: Importowanie skoroszytów programu Excel do programu Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 073301b1fe204d66eb91c4ea50216afc5464df64
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="import-excel-workbooks-into-power-bi-desktop"></a>Importowanie skoroszytów programu Excel do programu Power BI Desktop
Do programu **Power BI Desktop** można łatwo importować skoroszyty programu Excel zawierające zapytania dodatku Power Query, modele dodatku Power Pivot i arkusze programu Power View. Na podstawie skoroszytu programu Excel są automatycznie tworzone raporty i wizualizacje, a po zaimportowaniu zawartości można ulepszać i dostosowywać te raporty za pomocą programu Power BI Desktop, korzystając z istniejących funkcji i nowych funkcji publikowanych w każdej comiesięcznej aktualizacji programu Power BI Desktop.

W przyszłości planowane jest zapewnienie dodatkowej komunikacji między programami Excel i Power BI Desktop (na przykład funkcji importu/eksportu). Ta bieżąca możliwość importowania skoroszytów do programu Power BI Desktop pozwala obecnym użytkownikom programu Excel na rozpoczęcie korzystania z programu Power BI Desktop.

## <a name="how-do-i-import-an-excel-workbook"></a>Jak zaimportować skoroszyt programu Excel?
Aby zaimportować skoroszyt, w programie Power BI Desktop wybierz pozycję **Plik -\> Importuj -\> Zawartość skoroszytu programu Excel**.

![](media/desktop-import-excel-workbooks/importexceltopbi_1.png)

Zostanie wyświetlone okno umożliwiające wybranie skoroszytu do zaimportowania. Nie ma obecnie żadnych ograniczeń dotyczących rozmiaru ani liczby obiektów w skoroszycie, ale analizowanie większych skoroszytów i importowanie ich do programu Power BI Desktop trwa dłużej.

> [!NOTE]
> W celu załadowania lub zaimportowania plików programu Excel z **folderów udostępnionych usługi OneDrive dla Firm** lub **folderów grupy usługi Office 365** wprowadź adres URL pliku programu Excel jako **internetowe** źródło danych w programie Power BI Desktop. Aby poprawnie sformatować adres URL usługi **OneDrive dla Firm**, należy wykonać kilka kroków — więcej informacji i poprawną sekwencję kroków podano w temacie [Używanie linków usługi OneDrive dla Firm w programie Power BI Desktop](desktop-use-onedrive-business-links.md).
> 
> 

Po wybraniu skoroszytu program Power BI Desktop przeanalizuje go i przekonwertuje na plik programu Power BI Desktop (pbix). Jest to operacja jednorazowa. Po utworzeniu pliku programu Power BI Desktop w ten sposób ten plik nie jest już zależny od oryginalnego skoroszytu programu Excel i można go modyfikować lub zmieniać (a także zapisywać i udostępniać) bez wpływu na oryginalny skoroszyt.

![](media/desktop-import-excel-workbooks/importexceltopbi_2.png)

Po zakończeniu operacji importu zostaje wyświetlona strona **Podsumowanie** z opisem elementów, które zostały przekonwertowane, a także listą wszystkich elementów, których nie udało się zaimportować.

![](media/desktop-import-excel-workbooks/importexceltopbi_3.png)

Po wybraniu pozycji **Zamknij** raport zostaje załadowany w programie Power BI Desktop. Na poniższej ilustracji przedstawiono program Power BI Desktop po zaimportowaniu skoroszytu programu Excel. Program Power BI Desktop automatycznie załadował raport na podstawie zawartości skoroszytu.

![](media/desktop-import-excel-workbooks/importexceltopbi_4.png)

Po zaimportowaniu skoroszytu można kontynuować pracę w raporcie, na przykład tworzyć nowe wizualizacje, dodawać dane lub tworzyć nowe strony raportu, za pomocą funkcji i możliwości dostępnych w programie Power BI Desktop.

## <a name="which-workbook-elements-are-imported"></a>Które elementy skoroszytu są importowane?
Program Power BI Desktop może importować następujące elementy z programu Excel, zwane zwykle *obiektami*.

| Obiekt w skoroszycie programu Excel | Wynik końcowy w pliku programu Power BI Desktop |
| --- | --- |
| Zapytania dodatku Power Query |Wszystkie zapytania dodatku Power Query z programu Excel są konwertowane na zapytania w programie Power BI Desktop. Jeśli w skoroszycie programu Excel zdefiniowano grupy zapytań, taka sama organizacja zostanie zreplikowana w programie Power BI Desktop. Ładowane są wszystkie zapytania, chyba że w programie Excel ustawiono dla nich opcję Utwórz tylko połączenie. Zachowanie związane z ładowaniem można dostosować w oknie dialogowym **Właściwości** na karcie **Narzędzia główne** w **Edytorze zapytań** w programie Power BI Desktop. |
| Zewnętrzne połączenia danych dodatku Power Pivot |Wszystkie zewnętrzne połączenia danych dodatku Power Pivot są konwertowane na zapytania w programie Power BI Desktop. |
| Połączone tabele lub tabele bieżącego skoroszytu |Jeśli w pliku programu Excel istnieje tabela arkusza połączona z modelem danych lub z zapytaniem — przy użyciu polecenia *Z tabeli* lub funkcji *Excel.CurrentWorkbook()* w języku M — prezentowane są następujące opcje: 1. Zaimportowanie tabeli do pliku programu Power BI Desktop. Ta tabela to jednorazowa migawka danych. Nie można później edytować danych w tej tabeli w programie Power BI Desktop. W przypadku tabel utworzonych za pomocą tej opcji obowiązuje ograniczenie rozmiaru do miliona znaków (łącznie — obejmuje to wszystkie nagłówki kolumn i komórki). 2. Zachowanie połączenia z oryginalnym skoroszytem. Ewentualnie można zachować połączenie z oryginalnym skoroszytem programu Excel. Program Power BI Desktop będzie pobierać najnowszą zawartość tej tabeli przy każdym odświeżeniu, podobnie jak w przypadku innych zapytań utworzonych w programie Power BI Desktop do badania skoroszytów programu Excel. |
| Kolumny obliczeniowe, miary, wskaźniki KPI, kategorie danych i relacje modelu danych |Te obiekty modelu danych są konwertowane na obiekty równoważne w programie Power BI Desktop. Należy pamiętać, że niektóre kategorie danych nie są dostępne w programie Power BI Desktop, na przykład kategoria **Obraz**. W takim przypadku informacja o kategorii danych zostaje zresetowana dla danej kolumny. |
| Arkusze programu Power View |Dla każdego arkusza programu Power View w pliku programu Excel tworzona jest nowa strona raportu. Nazwy i kolejność tych stron raportu są zgodne z oryginalnym skoroszytem programu Excel. |

## <a name="are-there-any-limitations-to-importing-a-workbook"></a>Czy istnieją jakiekolwiek ograniczenia związane z importowaniem skoroszytu?
Z importowaniem skoroszytu do programu Power BI Desktop związanych jest kilka następujących ograniczeń:

* **Połączenia zewnętrzne z modelami tabelarycznymi usług Analysis Services:** w programie Excel 2013 można utworzyć połączenie z modelami tabelarycznymi usług SQL Server Analysis Services i tworzyć raporty programu Power View na ich podstawie bez potrzeby importowania danych. Ten typ połączenia nie jest obecnie obsługiwany w ramach importowania skoroszytów programu Excel do programu Power BI Desktop. Jako obejście należy ponownie utworzyć te połączenia zewnętrzne w programie Power BI Desktop.
* **Hierarchie:** ten typ obiektu modelu danych nie jest obecnie obsługiwany w programie Power BI Desktop. W związku z tym hierarchie są pomijane w ramach importowania skoroszytu programu Excel do programu Power BI Desktop.
* **Kolumny danych binarnych:** ten typ kolumny modelu danych nie jest obecnie obsługiwany w programie Power BI Desktop. Kolumny danych binarnych są usuwane z tabeli wynikowej w programie Power BI Desktop.
* **Nieobsługiwane elementy programu Power View:** istnieje kilka funkcji w programie Power View, które nie są dostępne w programie Power BI Desktop, na przykład motywy lub niektóre typy wizualizacji (wykres punktowy z osią odtwarzania, zachowania przechodzenia do szczegółów itp.). Te nieobsługiwane wizualizacje skutkują komunikatami *Nieobsługiwana wizualizacja* w odpowiadających im lokalizacjach w raporcie programu Power BI Desktop, które można usunąć lub ponownie skonfigurować — według własnego uznania.
* **Nazwane zakresy używające polecenia** ***Z tabeli*** **w dodatku Power Query lub funkcji** ***Excel.CurrentWorkbook*** **w języku M:** importowanie danych tych nazwanych zakresów do programu Power BI Desktop nie jest obecnie obsługiwane, ale jest planowane dodanie tej funkcji w programie Power BI Desktop. Obecnie te nazwane zakresy są ładowane do programu Power BI Desktop jako połączenie zewnętrzne ze skoroszytem programu Excel.
* **Połączenie dodatku PowerPivot z usługami SSRS:** połączenia zewnętrzne dodatku PowerPivot z usługami SQL Server Reporting Services (SSRS) nie są obecnie obsługiwane, ponieważ to źródło danych nie jest obecnie dostępne w programie Power BI Desktop.

