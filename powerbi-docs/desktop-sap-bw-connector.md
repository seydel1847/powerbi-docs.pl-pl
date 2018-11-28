---
title: Używanie łącznika systemu SAP BW w programie Power BI Desktop
description: Używanie łącznika systemu SAP BW w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 10/15/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f4825e8d8d47f755b01748c847b0fcf110db030a
ms.sourcegitcommit: fdb54145f9bc93b312409c15c603749f3a4a876e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/28/2018
ms.locfileid: "52452872"
---
# <a name="use-the-sap-bw-connector-in-power-bi-desktop"></a>Używanie łącznika systemu SAP BW w programie Power BI Desktop
Program Power BI Desktop umożliwia dostęp do danych systemu **SAP Business Warehouse (BW)**.

Aby dowiedzieć się, jak klienci systemu SAP mogą korzystać z zalet połączenia usługi Power BI z istniejącymi systemami SAP Business Warehouse (BW), zapoznaj się z [oficjalnym dokumentem dotyczącym usługi Power BI i systemu SAP BW](https://aka.ms/powerbiandsapbw). Aby uzyskać szczegółowe informacje o używaniu trybu DirectQuery z systemem SAP BW, zobacz artykuł [Zapytanie bezpośrednie i system SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md).

Począwszy od wersji programu **Power BI Desktop** wydanej w czerwcu 2018 roku (ogólnodostępnej od października 2018 r.), można używać łącznika SAP BW Connector w implementacji oferującej znaczącą poprawę wydajności i dostępności. Ta zaktualizowana wersja łącznika SAP BW Connector została opracowana przez firmę Microsoft i jest nazywana wersją **Implementation 2.0**. Możesz wybrać wersję 1 (v1) łącznika **SAP BW Connector** lub łącznik **Implementation 2.0 SAP Connector**. W poniższych sekcjach opisano instalację każdej z wersji. Możesz wybrać jeden lub drugi łącznik podczas nawiązywania połączenia z systemem SAP BW z poziomu programu Power BI Desktop.

Sugerujemy używanie łącznika **Implementation 2.0 SAP Connector** zawsze, gdy jest to możliwe.

## <a name="installation-of-version-1-of-the-sap-bw-connector"></a>Instalacja wersji 1 łącznika SAP BW Connector
Zalecamy używanie łącznika Implementation 2.0 SAP Connector zawsze, gdy jest to możliwe (patrz instrukcje w następnej sekcji). W tej sekcji opisano instalację wersji 1 łącznika **SAP BW Connector**, który można zainstalować, wykonując następujące kroki instalacji:

1. Zainstaluj bibliotekę **SAP NetWeaver** na komputerze lokalnym. Bibliotekę **SAP NetWeaver** możesz uzyskać od administratora SAP lub bezpośrednio z witryny [SAP Software Download Center](https://support.sap.com/swdc) (Centrum pobierania oprogramowania SAP). Ponieważ struktura witryny **SAP Software Download Center** (Centrum pobierania oprogramowania SAP) jest często zmieniana, dokładniejsze wskazówki dotyczące nawigowania w tej witrynie są niedostępne. Biblioteka **SAP NetWeaver** zwykle jest również składnikiem instalacji narzędzi klienckich SAP.
   
   Aby uzyskać informacje na temat lokalizacji pobierania najnowszej wersji, możesz wyszukać dokument *SAP Note #1025361*. Upewnij się, że architektura biblioteki **SAP NetWeaver** (32-bitowa lub 64-bitowa) jest zgodna z architekturą zainstalowanego programu **Power BI Desktop**, a następnie zainstaluj wszystkie pliki zawarte w **zestawie SDK SAP NetWeaver RFC** zgodnie z dokumentem SAP Note.
2. W oknie dialogowym **Pobieranie danych** znajdują się wpisy **SAP Business Warehouse Application Server** i **SAP Business Warehouse Message Server** w kategorii **Baza danych**.
   
   ![Opcje pobierania danych dla systemu SAP](media/desktop-sap-bw-connector/sap_bw_2a.png)

## <a name="installation-of-implementation-20-sap-connector"></a>Instalacja łącznika Implementation 2.0 SAP Connector

Wersja **Implementation 2.0** łącznika SAP Connector wymaga łącznika SAP .NET Connector 3.0. Możesz [pobrać łącznik SAP .NET Connector 3.0](https://support.sap.com/en/product/connectors/msnet.html) z witryny internetowej SAP, korzystając z następującego linku:

* [SAP .NET Connector 3.0](https://support.sap.com/en/product/connectors/msnet.html)

Dostęp do pobierania wymaga prawidłowego użytkownika S-user. Zachęcamy klientów, aby skontaktowali się ze swoim zespołem SAP Basis w celu uzyskania łącznika SAP .NET Connector 3.0. 

Łącznik jest dostarczany w wersji 32-bitowej i 64-bitowej, a użytkownicy *muszą* wybrać wersję, która odpowiada ich instalacji programu Power BI Desktop. W momencie pisania tego dokumentu witryna internetowa udostępnia dwie wersje (dla platformy .NET 4.0):

* Łącznik SAP Connector w wersji 3.0.20.0 dla platformy Microsoft .NET i systemu Windows w wersji 32-bitowej (x86) jako plik zip (6896 KB), 16 stycznia 2018 r.
* Łącznik SAP Connector w wersji 3.0.20.0 dla platformy Microsoft .NET i systemu Windows w wersji 64-bitowej (x64) jako plik zip (7180 KB), 16 stycznia 2018 r.

Podczas instalacji upewnij się, że w oknie **Optional setup steps** (Opcjonalne kroki instalacji) została wybrana opcja *Install assemblies to GAC* (Zainstaluj zestawy w pamięci podręcznej GAC), jak pokazano na poniższej ilustracji.

![Opcjonalne kroki instalacji SAP](media/desktop-sap-bw-connector/sap_bw_2b.png)

> [!NOTE]
> Pierwsza wersja implementacji systemu SAP BW wymagała bibliotek DLL NetWeaver. Jeśli używasz łącznika Implementation 2.0 SAP Connector i nie używasz pierwszej wersji, biblioteki DLL NetWeaver nie są wymagane.


## <a name="version-1-sap-bw-connector-features"></a>Funkcje łącznika systemu SAP BW Connector w wersji 1
Łącznik **SAP BW Connector** w wersji 1 w programie Power BI Desktop umożliwia importowanie danych z modułów **SAP Business Warehouse Server** oraz korzystanie z trybu DirectQuery. 

Aby dowiedzieć się więcej o **łączniku systemu SAP BW** oraz sposobu jego używania z zapytaniem bezpośrednim, zobacz artykuł [Zapytanie bezpośrednie i system SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md).

Aby nawiązać połączenie, musisz określić *Serwer*, *Numer systemu* i *Identyfikator klienta*.

![Ustawienia połączenia serwera SAP](media/desktop-sap-bw-connector/sap_bw_3a.png)

Możesz również określić dwie dodatkowe **Opcje zaawansowane**: kod języka i niestandardową instrukcję MDX do uruchamiania na określonym serwerze.

![Dodatkowe informacje o połączeniu](media/desktop-sap-bw-connector/sap_bw_4a.png)

Jeśli nie została określona żadna instrukcja MDX, jest wyświetlane okno **Nawigator** zawierające listę modułów dostępnych na serwerze z opcją przechodzenia do szczegółów oraz wybierania elementów z dostępnych modułów, w tym wymiarów i miar. Usługa Power BI uwidacznia zapytania i moduły uwidocznione przez [interfejsy BAPI BW Open Analysis Interface OLAP](https://help.sap.com/saphelp_nw70/helpdata/en/d9/ed8c3c59021315e10000000a114084/content.htm).

Gdy wybierzesz co najmniej jeden element z serwera, na podstawie zaznaczenia zostanie utworzony podgląd tabeli wyników.

![Podgląd tabeli SAP](media/desktop-sap-bw-connector/sap_bw_5.png)

Okno **Nawigator** również zawiera kilka **opcji wyświetlania**, które umożliwiają wykonywanie następujących czynności:

* **Wyświetlanie *tylko wybranych elementów* i *wszystkich elementów* (widok domyślny):** Ta opcja przydaje się do weryfikowania ostatecznego zestawu zaznaczonych elementów. Innym sposobem wyświetlenia tych samych danych jest wybranie pozycji *Nazwy kolumn* w obszarze *Podgląd*.
* **Włącz podglądy danych (zachowanie domyślne):** Możesz również decydować o tym, czy w tym oknie dialogowym powinny być wyświetlane podglądy danych. Wyłączenie podglądów danych powoduje zmniejszenie liczby wywołań serwera, ponieważ nie występują więcej żądania danych na potrzeby podglądu.
* **Nazwy techniczne:** System SAP BW obsługuje pojęcie *nazw technicznych* dla obiektów w module. Nazwy techniczne umożliwiają właścicielowi modułu uwidacznianie *przyjaznych dla użytkownika* nazw obiektów modułu, w odróżnieniu od uwidaczniania tylko *nazw fizycznych* tych obiektów w module.

![Okno Nawigatora](media/desktop-sap-bw-connector/sap_bw_6.png)

Po wybraniu wszystkich niezbędnych obiektów w oknie **Nawigator** możesz zdecydować, co robić dalej, wybierając jeden z następujących przycisków w dolnej części okna **Nawigator**:

* Wybranie przycisku **Ładuj** wyzwala załadowanie całego zestawu wierszy tabeli wyników do modelu danych programu Power BI Desktop, a następnie przejście do widoku **Raport**, w którym możesz rozpocząć wizualizowanie danych lub wprowadzanie dalszych modyfikacji przy użyciu widoków **Dane** lub **Relacje**.
* Wybranie przycisku **Edytuj** wywołuje **Edytor zapytań**, w którym możesz wykonać dodatkowe kroki transformacji i filtrowania danych, zanim cały zestaw wierszy zostanie wprowadzony do modelu danych programu Power BI Desktop.

Oprócz importowania danych z modułów systemu **SAP BW** możesz również zaimportować dane z szerokiej gamy innych źródeł danych w programie Power BI Desktop, a następnie połączyć je w jeden raport. Dzięki temu masz możliwość skorzystania ze wszystkich ciekawych scenariuszy raportowania i analizowania w oparciu o dane systemu **SAP BW**.

## <a name="using-implementation-20-sap-bw-connector"></a>Używanie łącznika Implementation 2.0 SAP BW Connector

Aby używać wersji Implementation 2.0 łącznika SAP BW Connector, należy utworzyć nowe połączenie. Aby utworzyć nowe połączenie, wykonaj następujące kroki.

1. W oknie **Pobieranie danych** wybierz pozycję **SAP Business Warehouse Application Server** lub **SAP Business Warehouse Message Server**.

2. Zostanie wyświetlone okno dialogowe nowego połączenia, które umożliwia wybór implementacji. Wybranie wersji **Implementation 2.0**, jak pokazano na poniższej ilustracji, włącza opcje Tryb wykonywania, Rozmiar partii i Włącz struktury cech.

    ![Okno dialogowe połączenia SAP](media/desktop-sap-bw-connector/sap_bw_7.png)

3. Wybierz przycisk **OK**. Zostanie otwarte środowisko **Nawigatora**, takie samo jak opisane we wcześniejszej sekcji dotyczącej łącznika SAP BW Connector w wersji 1. 

### <a name="new-options-for-implementation-20"></a>Nowe opcje dla wersji Implementation 2.0 

Implementacja Implementation 2.0 obsługuje następujące opcje:

1. **ExecutionMode** — określa interfejs MDX używany do wykonywania zapytań na serwerze. Prawidłowe opcje to:

        a. SapBusinessWarehouseExecutionMode.BasXml
        b. SapBusinessWarehouseExecutionMode.BasXmlGzip
        c. SapBusinessWarehouseExecutionMode.DataStream

    Wartość domyślna tej opcji to SapBusinessWarehouseExecutionMode.BasXmlGzip.

    Użycie wartości *SapBusinessWarehouseExecutionMode.BasXmlGzip* może zwiększyć wydajność, gdy występuje duże opóźnienie dla dużych zestawów danych.

2. **BatchSize** — określa maksymalną liczbę wierszy, które zostaną pobrane naraz podczas wykonywania instrukcji MDX. Mniejsza liczba wierszy przełoży się na więcej wywołań do serwera podczas pobierania dużego zestawu danych. Duża liczba wierszy może zwiększyć wydajność, ale może spowodować problemy z pamięcią na serwerze systemu SAP BW. Wartość domyślna to 50000 wierszy.

3. **EnableStructures** — wartość logiczna wskazująca, czy charakterystyczne struktury są rozpoznawane. Wartość domyślna tej opcji to false. Wpływa na listę obiektów dostępnych do wyboru. Nieobsługiwana w trybie zapytania natywnego.

Opcja **ScaleMeasures** jest przestarzała w tej implementacji. Zachowanie teraz jest takie samo jak w przypadku ustawienia *ScaleMeasures = false*, które zawsze wyświetla wartości nieskalowane.

### <a name="additional-improvements-for-implementation-20"></a>Dodatkowe ulepszenia w implementacji Implementation 2.0 

Na poniższej liście punktowanej opisano niektóre dodatkowe ulepszenia towarzyszące nowej implementacji:

* Lepsza wydajność
* Możliwość pobrania kilku milionów wierszy danych i dostrajanie za pomocą parametru rozmiaru partii.
* Możliwość przełączania trybów wykonywania.
* Obsługa trybu skompresowanego. Szczególnie korzystna w przypadku połączeń z dużym opóźnieniem lub dużych zestawów danych.
* Ulepszone wykrywanie zmiennych daty
* [Eksperymentalne] Uwidacznianie wymiarów Data (typ DATS w ABAP) i Czas (typ TIMS w ABAP) odpowiednio jako daty i godziny zamiast wartości tekstowych.
* Lepsza obsługa wyjątków. Błędy występujące w wywołaniach funkcji BAPI są teraz udostępniane.
* Składanie kolumn w trybach BasXml i BasXmlGzip. Na przykład jeśli wygenerowane zapytanie MDX pobiera 40 kolumn, ale bieżące zaznaczenie potrzebuje tylko 10, to żądanie zostanie przekazane na serwer w celu pobrania mniejszego zestawu danych.


### <a name="changing-existing-reports-to-use-implementation-20"></a>Zmiana istniejących raportów w celu używania implementacji 2.0 

Zmiana istniejących raportów w celu używania implementacji **Implementation 2.0** jest możliwa tylko w trybie importu i wymaga ręcznego wykonania następujących czynności.

1. Otwórz istniejący raport, wybierz pozycję **Edytuj zapytania** na wstążce, a następnie wybierz zapytanie systemu SAP Business Warehouse, które chcesz zaktualizować.

2. Kliknij prawym przyciskiem myszy zapytanie i wybierz pozycję **Edytor zaawansowany**.

3. W **Edytorze zaawansowanym** zmień wywołanie funkcji SapBusinessWarehouse.Cubes w następujący sposób: 

    a. Ustal, czy zapytanie już zawiera rekord opcji, taki jak pokazany w poniższym przykładzie:

    ![fragment kodu zapytania](media/desktop-sap-bw-connector/sap_bw_9.png)

    b. Jeśli tak, dodaj opcję implementacji 2.0 i usuń opcję ScaleMeasures, jeśli jest obecna, tak jak pokazano:

    ![fragment kodu zapytania](media/desktop-sap-bw-connector/sap_bw_10.png)

    c. Jeśli zapytanie nie zawiera jeszcze rekordu opcji, po prostu go dodaj. Na przykład jeśli wygląda następująco:

    ![fragment kodu zapytania](media/desktop-sap-bw-connector/sap_bw_11.png)

    d. Zmień je na:

    ![fragment kodu zapytania](media/desktop-sap-bw-connector/sap_bw_12.png)

4. Dołożono wszelkich starań, aby zapewnić zgodność wersji Implementation 2.0 łącznika SAP BW Connector z łącznikiem SAP BW Connector w wersji 1. Jednak mogą istnieć pewne różnice spowodowane używaniem różnych trybów wykonywania kodu języka MDX systemu SAP BW. Aby rozwiązać niezgodności, spróbuj przełączyć się między trybami wykonywania.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
W tej sekcji omówiono sytuacje problemowe (i ich rozwiązania) dotyczące pracy z łącznikiem systemu **SAP BW**.

1. Dane liczbowe z systemu **SAP BW** zwracają kropki dziesiętne zamiast przecinków. Na przykład w angielskim zapisie liczba 1,000,000 jest zwracana jako 1.000.000.
   
   System **SAP BW** zwraca dane dziesiętne z użyciem przecinka (*,*) lub kropki (*.*) jako separatora dziesiętnego. Aby określić, którego z tych separatorów dziesiętnych powinien używać system **SAP BW**, sterownik używany w programie **Power BI Desktop** wywołuje moduł *BAPI_USER_GET_DETAIL*. To wywołanie zwraca strukturę o nazwie **DEFAULTS** zawierającą pole o nazwie *DCPFM*, w którym jest przechowywany *format notacji dziesiętnej*. Przyjmuje on jedną z trzech następujących wartości:
   
       ‘ ‘ (space) = Decimal point is comma: N.NNN,NN
       'X' = Decimal point is period: N,NNN.NN
       'Y' = Decimal point is N NNN NNN,NN
   
   Klienci, którzy zgłaszali ten problem, odkryli, że wywołanie modułu *BAPI_USER_GET_DETAIL* w przypadku niektórych użytkowników (użytkowników, którym są wyświetlane nieprawidłowe dane) kończy się niepowodzeniem i wyświetleniem komunikatu o błędzie podobnego do następującego:
   
       You are not authorized to display users in group TI:
           <item>
               <TYPE>E</TYPE>
               <ID>01</ID>
               <NUMBER>512</NUMBER>
               <MESSAGE>You are not authorized to display users in group TI</MESSAGE>
               <LOG_NO/>
               <LOG_MSG_NO>000000</LOG_MSG_NO>
               <MESSAGE_V1>TI</MESSAGE_V1>
               <MESSAGE_V2/>
               <MESSAGE_V3/>
               <MESSAGE_V4/>
               <PARAMETER/>
               <ROW>0</ROW>
               <FIELD>BNAME</FIELD>
               <SYSTEM>CLNTPW1400</SYSTEM>
           </item>
   
   Aby naprawić ten błąd, użytkownicy muszą poprosić administratora systemu SAP o przyznanie użytkownikowi SAPBW używanemu w usłudze Power BI uprawnień do wykonywania modułu *BAPI_USER_GET_DETAIL*. Warto również sprawdzić, czy użytkownik ma wymaganą wartość *DCPFM*, jak opisano wcześniej w tym rozwiązaniu problemu.
   
2. **Łączność dla zapytań SAP BEx**
   
   W programie Power BI Desktop możesz wykonywać zapytania **BEx**, włączając określoną właściwość, jak pokazano na poniższej ilustracji:
   
   ![](media/desktop-sap-bw-connector/sap_bw_8.png)
   
3. Okno **Nawigator** nie wyświetla podglądu danych i widoczny jest w nim komunikat o błędzie informujący, że *odwołanie do obiektu nie zostało ustawione na wystąpienie obiektu*.
   
   Użytkownicy systemu SAP muszą mieć dostęp do określonych modułów funkcji BAPI, aby uzyskiwać metadane i pobierać dane z obiektów InfoProvider systemu SAP BW. Są to moduły:
   * BAPI_MDPROVIDER_GET_CATALOGS
   * BAPI_MDPROVIDER_GET_CUBES
   * BAPI_MDPROVIDER_GET_DIMENSIONS
   * BAPI_MDPROVIDER_GET_HIERARCHYS
   * BAPI_MDPROVIDER_GET_LEVELS
   * BAPI_MDPROVIDER_GET_MEASURES
   * BAPI_MDPROVIDER_GET_MEMBERS
   * BAPI_MDPROVIDER_GET_VARIABLES
   * BAPI_IOBJ_GETDETAIL

   Aby rozwiązać ten problem, sprawdź, czy użytkownik ma dostęp do różnych modułów *MDPROVIDER*, a także modułu *BAPI_IOBJ_GETDETAIL*. Aby kontynuować rozwiązywanie tego lub podobnych problemów, wybierz opcję *Włącz śledzenie* w oknie *Diagnostyka* w menu *Opcje* programu Power BI Desktop. Spróbuj pobrać dane z systemu SAP BW, gdy śledzenie jest aktywne, i zapoznaj się z plikiem śledzenia, aby uzyskać więcej szczegółów.


## <a name="next-steps"></a>Następne kroki
Aby uzyskać więcej informacji na temat systemu SAP i trybu DirectQuery, zapoznaj się z następującymi zasobami:

* [Zapytanie bezpośrednie i platforma SAP HANA](desktop-directquery-sap-hana.md)
* [Zapytanie bezpośrednie i system SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)
* [Zapytanie bezpośrednie w usłudze Power BI](desktop-directquery-about.md)
* [Źródła danych obsługiwane przez zapytanie bezpośrednie](desktop-directquery-data-sources.md)
* [Oficjalny dokument dotyczący usługi Power BI i systemu SAP BW](https://aka.ms/powerbiandsapbw)
