---
title: Używanie tabel obliczeniowych w programie Power BI Desktop
description: Tabele obliczeniowe w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 10264540a1ec0b8eb79e446590b86df855505d76
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54275185"
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

* DISTINCT
* WARTOŚCI
* CROSSJOIN
* UNION
* NATURALINNERJOIN
* NATURALLEFTOUTERJOIN
* INTERSECT
* CALENDAR
* CALENDARAUTO

Zobacz [dokumentację funkcji języka DAX](https://msdn.microsoft.com/ee634396.aspx) dla tych i innych tabel zwracających funkcje języka DAX.

