---
title: Właściwości zestawu danych usługi Power BI
description: Informacje dotyczące interfejsów API zestawu danych usługi Power BI
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 4654534d9643b9c5cf5911249a0eda33b5cc32af
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277904"
---
# <a name="dataset-properties"></a>Właściwości zestawu danych

Aktualna wersja 1 interfejsu API zestawów danych pozwala tylko na tworzenie zestawu danych z nazwą i kolekcją tabel. Każda tabela może mieć nazwę i kolekcję kolumn. Każda kolumna ma nazwę i typ danych. Rozszerzamy te właściwości w szczególności o obsługę miar i relacji między tabelami. Oto kompletna lista obsługiwanych właściwości w tej wersji:

> [!IMPORTANT]
> Jest ona dostępna na stronie [Datasets Operation Groups (Grupy operacji zestawów danych)](https://docs.microsoft.com/rest/api/power-bi/datasets).

## <a name="dataset"></a>Zestaw danych

Nazwa  |Typ  |Opis  |Tylko do odczytu  |Wymagane
---------|---------|---------|---------|---------
Identyfikator     |  Guid (identyfikator GUID)       | Unikatowy identyfikator zestawu danych w całym systemie.        | Prawda        | Fałsz        
nazwa     | String (ciąg)        | Zdefiniowana przez użytkownika nazwa zestawu danych.        | Fałsz        | Prawda        
tables     | Table[] (tabela[])        | Kolekcja tabel.        |  Fałsz       | Fałsz        
relationships     | Relationship[] (relacja[])        | Kolekcja relacji między tabelami.        | Fałsz        |  Fałsz  
defaultMode     | String (ciąg)        | Określa, czy zestaw danych jest wypychany, przesyłany strumieniowo lub używany w ramach obydwu operacji. Dostępne wartości: „Push”, „Streaming” i „PushStreaming”.         | Fałsz        |  Fałsz

## <a name="table"></a>Tabela

Nazwa  |Typ  |Opis  |Tylko do odczytu  |Wymagane
---------|---------|---------|---------|---------
nazwa     | String (ciąg)        |  Nazwa tabeli zdefiniowana przez użytkownika. Jest ona również używana jako identyfikator tabeli.       | Fałsz        |  Prawda       
columns     |  column[] (kolumna[])       |  Kolekcja kolumn.       | Fałsz        |  Prawda       
measures     | measure[] (miara[])        |  Kolekcja miar.       | Fałsz        |  Fałsz       
isHidden     | Boolean (wartość logiczna)        | W przypadku wartości Prawda tabela zostanie ukryta przed narzędziami klienta.        | Fałsz        | Fałsz        

## <a name="column"></a>strukturalna

Nazwa  |Typ  |Opis  |Tylko do odczytu  |Wymagane
---------|---------|---------|---------|---------
nazwa     |  String (ciąg)        | Nazwa kolumny zdefiniowana przez użytkownika.        |  Fałsz       | Prawda       
dataType     |  String (ciąg)       |  Obsługiwane ograniczenia i [typy danych EDM](https://msdn.microsoft.com/library/ee382832.aspx). Zobacz [Ograniczenia typu danych](#DataTypeRestrictions).      |  Fałsz       | Prawda        
formatString     | String (ciąg)        | Ciąg opisujący, jak powinna być formatowana wyświetlana wartość. Aby dowiedzieć się więcej na temat formatowania ciągów, zobacz [FORMAT_STRING Contents (Zawartość elementu FORMAT_STRING)](https://msdn.microsoft.com/library/ms146084.aspx).      | Fałsz        | Fałsz        
sortByColumn    | String (ciąg)        |   Nazwa ciągu kolumny w tej samej tabeli, która ma być używana do porządkowania bieżącej kolumny.     | Fałsz        | Fałsz       
dataCategory     | String (ciąg)        |  Wartość ciągu do użycia dla kategorii danych opisującej dane w tej kolumnie. Niektóre typowe wartości to: Address, City, Continent, Country, Image, ImageUrl, Latitude, Longitude, Organization, Place, PostalCode, StateOrProvince, WebUrl       |  Fałsz       | Fałsz        
isHidden    |  Boolean (wartość logiczna)       |  Właściwość wskazująca, czy kolumna została ukryta w widoku. Wartość domyślna to fałsz.       | Fałsz        | Fałsz        
summarizeBy     | String (ciąg)        |  Domyślna metoda agregacji kolumny. Wartości to: default, none, sum, min, max, count, average, distinctCount     |  Fałsz       | Fałsz

## <a name="measure"></a>Miara

Nazwa  |Typ  |Opis  |Tylko do odczytu  |Wymagane
---------|---------|---------|---------|---------
nazwa     | String (ciąg)        |  Nazwa miary zdefiniowana przez użytkownika.       |  Fałsz       | Prawda        
expression     | String (ciąg)        | Prawidłowe wyrażenie języka DAX.        | Fałsz        |  Prawda       
formatString     | String (ciąg)        |  Ciąg opisujący, jak powinna być formatowana wyświetlana wartość. Aby dowiedzieć się więcej na temat formatowania ciągów, zobacz [FORMAT_STRING Contents (Zawartość elementu FORMAT_STRING)](https://msdn.microsoft.com/library/ms146084.aspx).       | Fałsz        | Fałsz        
isHidden     | String (ciąg)        |  W przypadku wartości Prawda tabela zostanie ukryta przed narzędziami klienta.       |  Fałsz       | Fałsz       

## <a name="relationship"></a>Relacja

Nazwa  |Typ  |Opis  |Tylko do odczytu  |Wymagane 
---------|---------|---------|---------|---------
nazwa     | String (ciąg)        | Nazwa relacji zdefiniowana przez użytkownika. Jest ona również używana jako identyfikator relacji.        | Fałsz       | Prawda        
crossFilteringBehavior     | String (ciąg)        |    Kierunek filtru relacji: OneDirection (ustawienie domyślne), BothDirections, Automatic       | Fałsz        | Fałsz        
fromTable     | String (ciąg)        | Nazwa tabeli klucza obcego.        | Fałsz        | Prawda         
fromColumn    | String (ciąg)        | Nazwa kolumny klucza obcego.        | Fałsz        | Prawda         
toTable    | String (ciąg)        | Nazwa tabeli klucza podstawowego.        | Fałsz        | Prawda         
toColumn     | String (ciąg)        | Nazwa kolumny klucza podstawowego.        | Fałsz        | Prawda        

<a name="DataTypeRestrictions"/>

## <a name="data-type-restrictions-applies-to-datatype-property"></a>Ograniczenia typu danych (dotyczy właściwości dataType)

Typ danych  |Ograniczenia  
---------|---------
Int64     |   Wartości Int64.MaxValue i Int64.MinValue nie są dozwolone.      
Double (liczba o podwójnej precyzji)     |  Wartości Double.MaxValue i Double.MinValue nie są dozwolone. Wartość NaN nie jest obsługiwana. Wartości +Infinity i -Infinity nie są obsługiwane w niektórych funkcjach (na przykład Min, Max).       
Boolean (wartość logiczna)     |   Prawda lub fałsz.
Datetime (data/godzina)    |   Podczas ładowania danych wartości zawierające ułamki określające dzień są przeliczane na całkowite wielokrotności 1/300 sekundy (3,33 ms).      
String (ciąg)     |  Obecnie umożliwia użycie do 4000 znaków na wartość ciągu.
Decimal (liczba dziesiętna)|precision (dokładność)=28, scale (skala)=4

## <a name="example"></a>Przykład
Poniższy przykład kodu zawiera niektóre z tych właściwości:

```
{

  "name": "PushAdvanced",

  "tables": [

    {

      "name": "Date",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        }

      ]

    },

    {

      "name": "sales",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "Sales",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ],

      "measures": [

        {

          "name": "percent to forecast",

          "expression": "SUM(sales[Sales])/SUM(forecast[forecast])",

          "formatString": "0.00 %;-0.00 %;0.00 %"

        }

      ]

    },

    {

      "name": "forecast",

      "columns": [

        {

          "name": "date",

          "dataType": "dateTime",

          "formatString": "m/d/yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "forecast",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ]

    }

  ],

  "relationships": [

    {

      "name": "2ea345ce-b147-436e-8ac2-9d3c4d82af8d",

      "fromTable": "sales",

      "fromColumn": "Date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    },

    {

      "name": "5d95f419-e589-4345-9581-6e70670b1bba",

      "fromTable": "forecast",

      "fromColumn": "date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    }

  ]

}
```