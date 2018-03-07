---
title: "Używanie tabel obliczeniowych w programie Power BI Desktop"
description: Tabele obliczeniowe w programie Power BI Desktop
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
LocalizationGroup: Model your data
ms.openlocfilehash: 8bf8d2629d6a0bd88a85fa468547586e93502721
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="using-calculated-tables-in-power-bi-desktop"></a>Używanie tabel obliczeniowych w programie Power BI Desktop
Przy użyciu tabel obliczeniowych można dodać nową tabelę do modelu. Jednak zamiast wykonywania zapytań i ładowania wartości do nowych kolumn tabeli ze źródła danych, tworzona jest formuła języka DAX (Data Analysis Expressions) definiująca wartości w tabeli. W programie Power BI Desktop tabele obliczeniowe są tworzone za pomocą funkcji Nowa tabela w widoku raportu lub widoku danych.

W większości przypadków importowanie danych do modelu odbywa się z zewnętrznego źródła danych. Tabele obliczeniowe zapewniają jednak pewne korzyści. Tabele obliczeniowe są zazwyczaj najlepszym rozwiązaniem dla obliczeń pośrednich oraz danych przechowywanych jako część modelu, a nie obliczanych na bieżąco lub jako część zapytania.

W przeciwieństwie do tabel utworzonych jako część zapytania, tabele obliczeniowe utworzone w widoku raportu lub widoku danych są oparte na danych, które zostały już załadowane do modelu danych. Na przykład można połączyć lub skrzyżować dwie tabele.

Podobnie jak w przypadku normalnych tabel, tabele obliczeniowe mogą mieć relacje z innymi tabelami. Kolumny w tabeli obliczeniowej zawierają typy danych i formatowanie oraz mogą należeć do kategorii danych. Kolumny można dowolnie nazywać i dodawać do wizualizacji w raporcie tak samo jak inne pola. Tabele obliczeniowe są ponownie obliczane, jeśli którakolwiek z tabel, z której są ściągane dane, zostanie odświeżona lub w dowolny sposób zaktualizowana.

Do obliczania tabel obliczeniowych używany jest język DAX ([Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx)) — język formuł przeznaczony do pracy z danymi relacyjnymi, takimi jak używane w programie Power BI Desktop. Język DAX zawiera bibliotekę ponad 200 funkcji, operatorów i konstrukcji, które zapewniają ogromną elastyczność w tworzeniu formuł do obliczania wyników na potrzeby praktycznie dowolnej analizy danych.

## <a name="lets-look-at-an-example"></a>Spójrzmy na przykład
Jeff, menedżer projektu w firmie Contoso, ma jedną tabelę z pracownikami z regionów północno-zachodnich, a drugą z pracownikami z regionów południowo-zachodnich. Jeff chce połączyć obie tabele w jedną.

**NorthwestEmployees** (Pracownicy — północny zachód)

 ![](media/desktop-calculated-tables/calctables_nwempl.png)

**SoutwestEmployees** (Pracownicy — południowy zachód)

 ![](media/desktop-calculated-tables/calctables_swempl.png)

Połączenie tych dwóch tabel przy użyciu tabeli obliczeniowej jest dość proste. Mimo że można utworzyć tabelę obliczeniową zarówno w widoku raportu, jak i widoku danych, wykonanie tej czynności w widoku danych jest nieco prostsze, ponieważ można natychmiast zobaczyć nową tabelę obliczeniową.

W **widoku danych** na karcie **Modelowanie** kliknij pozycję **Nowa tabela**. Zostanie wyświetlony pasek formuły.

 ![](media/desktop-calculated-tables/calctables_formulabarempty.png)

Następnie wprowadź następującą formułę:

 ![](media/desktop-calculated-tables/calctables_formulabarformula.png)

Została utworzona nowa tabela o nazwie Pracownicy z regionów zachodnich.

 ![](media/desktop-calculated-tables/calctables_westregionempl.png)

Nowa tabela z pracownikami z regionów zachodnich wyświetlana jest podobnie jak wszystkie inne tabele na liście Pola. Można utworzyć relacje z innymi tabelami, dodać miary i kolumny obliczeniowe i dodać dowolne jej pola do raportów, jak w przypadku innych tabel.

 ![](media/desktop-calculated-tables/calctables_fieldlist.png)

## <a name="functions-for-calculated-tables"></a>Funkcje dla tabel obliczeniowych
Tabele obliczeniowe mogą być definiowane przez dowolne wyrażenie DAX zwracające tabelę, w tym proste odwołanie do innej tabeli. Na przykład:

 ![](media/desktop-calculated-tables/calctables_formulabarsimpleformula.png)

Tabele obliczeniowe z językiem DAX mogą służyć do rozwiązywania wielu problemów analitycznych. To, co tu przedstawiliśmy, to tylko krótkie wprowadzenie do tabel obliczeniowych. Po rozpoczęciu pracy z tabelami obliczeniowymi zapoznaj się z niektórymi najczęściej stosowanymi i przydatnymi funkcjami tabeli języka DAX:

&lt;TABLE&gt; DISTINCT VALUES CROSSJOIN UNION NATURALINNERJOIN NATURALLEFTOUTERJOIN INTERSECT CALENDAR CALENDARAUTO

Zobacz [dokumentację funkcji języka DAX](https://msdn.microsoft.com/ee634396.aspx) dla tych i innych tabel zwracających funkcje języka DAX.

