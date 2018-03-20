---
title: "Używanie danych tabelarycznych usług Analysis Services w programie Power BI Desktop"
description: "Dane tabelaryczne usług Analysis Services w programie Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 02ce801db4eb6f5040c1d0e31ee0746a475c0bbb
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2018
---
# <a name="using-analysis-services-tabular-data-in-power-bi-desktop"></a>Używanie danych tabelarycznych usług Analysis Services w programie Power BI Desktop
Program Power BI Desktop zapewnia dwa sposoby nawiązywania połączenia i pobierania danych z modeli tabelarycznych usług programu SQL Server Analysis Services: eksplorowanie przy użyciu połączenia na żywo lub wybranie elementów i zaimportowanie ich do programu Power BI Desktop.

Przyjrzyjmy się temu bliżej.

**Eksploruj przy użyciu połączenia na żywo** — w przypadku użycia połączenia na żywo elementy w modelu tabelarycznym lub perspektywie, np. tabele, kolumny i miary, pojawiają się na liście pól w programie Power BI Desktop. Możesz użyć zaawansowanych narzędzi do obsługi wizualizacji i raportów programu Power BI Desktop, aby zbadać model tabelaryczny przy użyciu nowych, wysoce interaktywnych sposobów.

Podczas nawiązywania połączenia na żywo żadne dane z modelu tabelarycznego nie są importowane do programu Power BI Desktop. Za każdym razem, gdy wchodzisz w interakcję z wizualizacją, program Power BI Desktop wysyła zapytanie do modelu tabelarycznego i oblicza wyświetlane wyniki. Zawsze patrzysz na najnowsze dane. Pamiętaj, że modele tabelaryczne są bardzo bezpieczne. Elementy pojawiające się w programie Power BI Desktop zależą od uprawnień modelu, z którym nawiązano połączenie.

Po utworzeniu dynamicznych raportów w programie Power BI Desktop możesz udostępnić je poprzez opublikowanie w witrynie usługi Power BI. W przypadku publikowania pliku programu Power BI Desktop z połączeniem na żywo z modelem tabelarycznym i witryną usługi Power BI lokalna brama danych musi być zainstalowana i skonfigurowana przez administratora. Aby dowiedzieć się więcej, zobacz temat [Lokalna brama danych](service-gateway-onprem.md).

**Wybierz elementy i zaimportuj je do programu Power BI Desktop** — w przypadku tej opcji połączenia możesz wybrać elementy, np. tabele, kolumny i miary, w modelu tabelarycznym lub perspektywie i załadować je do modelu programu Power BI Desktop. Możesz użyć zaawansowanego edytora zapytań programu Power BI Desktop, aby jeszcze dokładniej zmodyfikować żądane wyniki. Możesz użyć funkcji modelowania programu Power BI Desktop, aby jeszcze dokładniej modelować dane. Nie utrzymuje się połączenia na żywo między programem Power BI Desktop i modelem tabelarycznym. Następnie możesz zbadać model programu Power BI Desktop w trybie offline lub opublikować go w witrynie usługi Power BI.

## <a name="to-connect-to-a-tabular-model"></a>Jak nawiązać połączenie z modelem tabelarycznym
1. W programie Power BI Desktop na karcie **Narzędzia główne** kliknij pozycję **Pobierz dane**.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata.png)
2. Kliknij opcję **Baza danych usług SQL Server Analysis Services**, a następnie kliknij pozycję **Połącz**.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as.png)
3. Wprowadź nazwę serwera i wybierz tryb połączenia. 
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as_server.png)
4. Ten krok zależy od wybranego trybu połączenia:

* Jeśli łączysz się na żywo, w nawigatorze wybierz model tabelaryczny lub perspektywę.
  
  ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as_live.png)
* Jeśli używasz opcji Wybierz elementy i pobierz dane, w nawigatorze wybierz model tabelaryczny lub perspektywę. Możesz dodatkowo wybrać tylko konkretne tabele lub kolumny do załadowania. Aby ukształtować dane przed załadowaniem, kliknij opcję Edytuj, aby otworzyć edytor zapytań. Gdy wszystko będzie gotowe, kliknij opcję Załaduj, aby zaimportować dane do programu Power BI Desktop.

![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as_select.png)

## <a name="frequently-asked-questions"></a>Często zadawane pytania
**Pytanie:** Czy potrzebuję lokalnej bramy danych?

**Odpowiedź:** To zależy. Jeśli używasz programu Power BI Desktop do nawiązywania połączenia na żywo z modelem tabelarycznym, ale nie zamierzasz publikować danych w witrynie usługi Power BI, nie potrzebujesz bramy. Z drugiej strony, jeśli zamierzasz publikować dane w witrynie usługi Power BI, brama danych jest niezbędna, aby zabezpieczyć komunikację między usługą Power BI i lokalnym serwerem usług Analysis Services. Pamiętaj, aby skontaktować się z administratorem serwera usług Analysis Services przed zainstalowaniem bramy danych.

Jeśli wybierasz elementy i pobierasz dane, importujesz dane modelu tabelarycznego bezpośrednio do pliku programu Power BI Desktop, więc brama nie jest potrzebna.

**Pytanie:** Jaka jest różnica między połączeniem na żywo z modelem tabelarycznym z poziomu usługi Power BI a połączeniem na żywo z poziomu programu Power BI Desktop?

**Odpowiedź:** W przypadku nawiązywania połączenia na żywo z modelem tabelarycznym z poziomu witryny w usłudze Power BI z lokalną bazą danych usług Analysis Services w organizacji lokalna brama danych jest wymagana do zabezpieczania komunikacji między tymi elementami. W przypadku nawiązywania połączenia na żywo z modelem tabelarycznym z programu Power BI Desktop brama nie jest wymagana, ponieważ program Power BI Desktop oraz serwer usług Analysis Services, z którym nawiązujesz połączenie, są uruchomione lokalnie w organizacji. Jeśli jednak chcesz opublikować plik programu Power BI Desktop w witrynie usługi Power BI, brama jest wymagana.

**Pytanie:** Jeśli utworzono połączenie na żywo, czy można nawiązać połączenie z innym źródłem danych w tym samym pliku programu Power BI Desktop?

**Odpowiedź:** Nie. Nie możesz eksplorować danych na żywo i nawiązywać połączenia z innym źródłem danych w tym samym pliku. Jeśli już zaimportowano dane lub nawiązano połączenie z innym źródłem danych w pliku programu Power BI Desktop, musisz utworzyć nowy plik, aby eksplorować dane na żywo.

**Pytanie:** Jeśli utworzono połączenie na żywo, czy można edytować model lub zapytanie w programie Power BI Desktop?

**Odpowiedź:** Możesz utworzyć miary na poziomie raportu w programie Power BI Desktop, ale wszystkie inne funkcje zapytań i modelowania są wyłączone podczas eksplorowania danych na żywo.

**Pytanie:** Jeśli utworzono połączenie na żywo, czy jest ono bezpieczne?

**Odpowiedź:** Tak. Twoje bieżące poświadczenia systemu Windows są używane do nawiązywania połączenia z serwerem usług Analysis Services. Nie możesz użyć podstawowych lub przechowywanych poświadczeń w usłudze Power BI lub programie Power BI Desktop w przypadku eksplorowania danych na żywo.

**Pytanie:** W nawigatorze widzę model i perspektywę. Jaka jest różnica?

**Odpowiedź:** Perspektywa jest określonym widokiem modelu tabelarycznego. Może zawierać tylko konkretne tabele, kolumny lub miary w zależności od unikatowych potrzeb analizy danych. Model tabelaryczny zawsze zawiera co najmniej jedną perspektywę, która może obejmować wszystkie elementy w modelu. Jeśli nie wiesz, którą opcję wybrać, skontaktuj się z administratorem.

## <a name="to-change-the-server-name-after-initial-connection"></a>Aby zmienić nazwę serwera po zainicjowaniu połączenia
Po utworzeniu pliku programu Power BI Desktop w przypadku eksplorowania danych w połączeniu na żywo mogą zaistnieć sytuacje, w których zechcesz przełączyć połączenia na inny serwer. Jeśli na przykład utworzono plik programu Power BI Desktop podczas nawiązywania połączenia z serwerem programowania i przed opublikowaniem w usłudze Power BI, zajdzie potrzeba przełączenia połączenia na serwer produkcyjny.

1. Wybierz pozycję **Edytuj zapytania** na wstążce.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_chname_editquery.png)
2. Wprowadź nazwę nowego serwera.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_chname_dialog.png)

