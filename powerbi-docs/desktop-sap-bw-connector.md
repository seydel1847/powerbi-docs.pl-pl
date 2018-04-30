---
title: Używanie łącznika systemu SAP BW w programie Power BI Desktop
description: Używanie łącznika systemu SAP BW w programie Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/09/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: d644f13f6c9b8ada62a0862fdcf92518512828f7
ms.sourcegitcommit: 312390f18b99de1123bf7a7674c6dffa8088529f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="use-the-sap-bw-connector-in-power-bi-desktop"></a>Używanie łącznika systemu SAP BW w programie Power BI Desktop
Program Power BI Desktop umożliwia dostęp do danych systemu **SAP Business Warehouse (BW)**.

Aby dowiedzieć się, jak klienci systemu SAP mogą korzystać z zalet połączenia usługi Power BI z istniejącymi systemami SAP Business Warehouse (BW), zapoznaj się z [oficjalnym dokumentem dotyczącym usługi Power BI i systemu SAP BW](https://aka.ms/powerbiandsapbw).

## <a name="installation-of-sap-bw-connector"></a>Instalacja łącznika systemu SAP BW
Aby używać łącznika systemu **SAP BW**, wykonaj następujące kroki instalacji:

1. Zainstaluj bibliotekę **SAP NetWeaver** na komputerze lokalnym. Bibliotekę **SAP NetWeaver** możesz uzyskać od administratora SAP lub bezpośrednio z witryny [SAP Software Download Center](https://support.sap.com/swdc) (Centrum pobierania oprogramowania SAP). Ponieważ struktura witryny **SAP Software Download Center** (Centrum pobierania oprogramowania SAP) jest często zmieniana, dokładniejsze wskazówki dotyczące nawigowania w tej witrynie są niedostępne. Biblioteka **SAP NetWeaver** zwykle jest również składnikiem instalacji narzędzi klienckich SAP.
   
   Aby uzyskać informacje na temat lokalizacji pobierania najnowszej wersji, możesz wyszukać dokument *SAP Note #1025361*. Upewnij się, że architektura biblioteki **SAP NetWeaver** (32-bitowa lub 64-bitowa) jest zgodna z architekturą zainstalowanego programu **Power BI Desktop**, a następnie zainstaluj wszystkie pliki zawarte w **zestawie SDK SAP NetWeaver RFC** zgodnie z dokumentem SAP Note.
2. W oknie dialogowym **Pobieranie danych** znajdują się wpisy **SAP Business Warehouse Application Server** i **SAP Business Warehouse Message Server** w kategorii **Baza danych**.
   
   ![](media/desktop-sap-bw-connector/sap_bw_2a.png)

## <a name="sap-bw-connector-features"></a>Funkcje łącznika systemu SAP BW
**Łączniki systemu SAP BW** w programie Power BI Desktop umożliwiają importowanie danych z modułów **SAP Business Warehouse Server** oraz korzystanie z zapytań bezpośrednich. 

Aby dowiedzieć się więcej o **łączniku systemu SAP BW** oraz sposobu jego używania z zapytaniem bezpośrednim, zobacz artykuł [Zapytanie bezpośrednie i system SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md).

Aby nawiązać połączenie, musisz określić *Serwer*, *Numer systemu* i *Identyfikator klienta*.

![](media/desktop-sap-bw-connector/sap_bw_3a.png)

Możesz również określić dwie dodatkowe **Opcje zaawansowane**: kod języka i niestandardową instrukcję MDX do uruchamiania na określonym serwerze.

![](media/desktop-sap-bw-connector/sap_bw_4a.png)

Jeśli nie została określona żadna instrukcja MDX, jest wyświetlane okno **Nawigator** zawierające listę modułów dostępnych na serwerze z opcją przechodzenia do szczegółów oraz wybierania elementów z dostępnych modułów, w tym wymiarów i miar. Usługa Power BI uwidacznia zapytania i moduły uwidocznione przez [interfejsy BAPI BW Open Analysis Interface OLAP](https://help.sap.com/saphelp_nw70/helpdata/en/d9/ed8c3c59021315e10000000a114084/content.htm).

Gdy wybierzesz co najmniej jeden element z serwera, na podstawie zaznaczenia zostanie utworzony podgląd tabeli wyników.

![](media/desktop-sap-bw-connector/sap_bw_5.png)

Okno **Nawigator** również zawiera kilka **opcji wyświetlania**, które umożliwiają wykonywanie następujących czynności:

* **Wyświetlanie *tylko wybranych elementów* i *wszystkich elementów* (widok domyślny):** Ta opcja przydaje się do weryfikowania ostatecznego zestawu zaznaczonych elementów. Innym sposobem wyświetlenia tych samych danych jest wybranie pozycji *Nazwy kolumn* w obszarze *Podgląd*.
* **Włącz podglądy danych (zachowanie domyślne):** Możesz również decydować o tym, czy w tym oknie dialogowym powinny być wyświetlane podglądy danych. Wyłączenie podglądów danych powoduje zmniejszenie liczby wywołań serwera, ponieważ nie występują więcej żądania danych na potrzeby podglądu.
* **Nazwy techniczne:** System SAP BW obsługuje pojęcie *nazw technicznych* dla obiektów w module. Nazwy techniczne umożliwiają właścicielowi modułu uwidacznianie *przyjaznych dla użytkownika* nazw obiektów modułu, w odróżnieniu od uwidaczniania tylko *nazw fizycznych* tych obiektów w module.

![](media/desktop-sap-bw-connector/sap_bw_6.png)

Po wybraniu wszystkich niezbędnych obiektów w oknie **Nawigator** możesz zdecydować, co robić dalej, wybierając jeden z następujących przycisków w dolnej części okna **Nawigator**:

* Wybranie przycisku **Ładuj** wyzwala załadowanie całego zestawu wierszy tabeli wyników do modelu danych programu Power BI Desktop, a następnie przejście do widoku **Raport**, w którym możesz rozpocząć wizualizowanie danych lub wprowadzanie dalszych modyfikacji przy użyciu widoków **Dane** lub **Relacje**.
* Wybranie przycisku **Edytuj** wywołuje **Edytor zapytań**, w którym możesz wykonać dodatkowe kroki transformacji i filtrowania danych, zanim cały zestaw wierszy zostanie wprowadzony do modelu danych programu Power BI Desktop.

Oprócz importowania danych z modułów systemu **SAP BW** możesz również zaimportować dane z szerokiej gamy innych źródeł danych w programie Power BI Desktop, a następnie połączyć je w jeden raport. Dzięki temu masz możliwość skorzystania ze wszystkich ciekawych scenariuszy raportowania i analizowania w oparciu o dane systemu **SAP BW**.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
W tej sekcji omówiono sytuacje problemowe (i ich rozwiązania) dotyczące pracy z tą wersją zapoznawczą łącznika systemu **SAP BW**.

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

## <a name="next-steps"></a>Następne kroki
Aby uzyskać więcej informacji na temat platformy SAP HANA i zapytania bezpośredniego, zapoznaj się z następującymi zasobami:

* [Zapytanie bezpośrednie i platforma SAP HANA](desktop-directquery-sap-hana.md)
* [Zapytanie bezpośrednie w usłudze Power BI](desktop-directquery-about.md)
* [Źródła danych obsługiwane przez zapytanie bezpośrednie](desktop-directquery-data-sources.md)
* [Oficjalny dokument dotyczący usługi Power BI i systemu SAP BW](https://aka.ms/powerbiandsapbw)
