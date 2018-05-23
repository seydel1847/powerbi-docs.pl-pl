---
title: Wypychanie danych do zestawu danych
description: Wypychanie danych do zestawu danych usługi Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 01/05/2017
ms.author: maghan
ms.openlocfilehash: 76d07c8384123a303c8801a45ecd05b9e6ed0321
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="push-data-into-a-power-bi-dataset"></a>Wypychanie danych do zestawu danych usługi Power BI
Interfejs API usługi Power BI umożliwia wypychanie danych do zestawu danych usługi Power BI. Załóżmy na przykład, że chcesz rozszerzyć istniejący przepływ pracy firmy, tak aby wypychał kluczowe dane do zestawu danych. W tym konkretnym przypadku chcesz wypchnąć zestaw danych działu sprzedaży i marketingu, w którym znajduje się tabela produktów, do zestawu danych.

Aby rozpocząć wypychanie danych do zestawu danych, musisz mieć konto usługi Azure Active Directory (Azure AD) i [konto usługi Power BI](create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Kroki procesu wypychania danych do zestawu danych
* Krok 1. [Rejestrowanie aplikacji w usłudze Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* Krok 2. [Uzyskiwanie tokenu uwierzytelnienia dostępu](walkthrough-push-data-get-token.md)
* Krok 3. [Tworzenie zestawu danych w usłudze Power BI](walkthrough-push-data-create-dataset.md)
* Krok 4. [Umożliwienie zestawowi danych dodawania wierszy do tabeli usługi Power BI](walkthrough-push-data-get-datasets.md)
* Krok 5. [Dodawanie wierszy do tabeli usługi Power BI](walkthrough-push-data-add-rows.md)

Następna sekcja zawiera ogólne omówienie operacji interfejsu API usługi Power BI wykonywanych w celu wypychania danych.

## <a name="power-bi-api-operations-to-push-data"></a>Operacje interfejsu API usługi Power BI umożliwiające wypychanie danych
Dzięki interfejsowi API REST usługi Power BI możesz wypychać źródła danych do usługi Power BI. Gdy aplikacja doda wiersze do zestawu danych, kafelki na pulpicie nawigacyjnym są automatycznie aktualizowane nowymi danymi. Aby wypchnąć dane, należy wykonać operacje [Utwórz zestaw danych](https://msdn.microsoft.com/library/mt203562.aspx) oraz [Dodaj wiersze](https://msdn.microsoft.com/library/mt203561.aspx). Aby odnaleźć zestaw danych, należy wykonać operację [Pobierz zestawy danych](https://msdn.microsoft.com/library/mt203567.aspx). W przypadku każdej z tych operacji możesz wprowadzić identyfikator grupy, aby pracować z grupą. Użyj operacji [Pobierz grupy](https://msdn.microsoft.com/library/mt243842.aspx), aby wyświetlić listę identyfikatorów grup.

Operacje procesu wypychania danych do zestawu danych:

* [Tworzenie zestawu danych](https://msdn.microsoft.com/library/mt203562.aspx)
* [Pobieranie zestawów danych](https://msdn.microsoft.com/library/mt203567.aspx)
* [Dodawanie wierszy](https://msdn.microsoft.com/library/mt203561.aspx)
* [Pobieranie grup](https://msdn.microsoft.com/library/mt243842.aspx)

Możesz utworzyć zestaw danych w usłudze Power BI, wprowadzając ciąg w formacie JavaScript Object Notation (JSON) do usługi Power BI. Aby dowiedzieć się więcej na temat formatu JSON, zapoznaj się z artykułem [JSON: Wprowadzenie](http://json.org/).

Ciąg JSON dla zestawu danych ma następujący format:

**Obiekt w formacie JSON zestawu danych usługi Power BI**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

W naszym przykładzie zestawu danych działu sprzedaży i marketingu należy wprowadzić ciąg JSON widoczny poniżej. W tym przykładzie **SalesMarketing** to nazwa zestawu danych, a **Product** to nazwa tabeli. Po zdefiniowaniu tabeli należy zdefiniować schemat tabeli. W przypadku zestawu danych **SalesMarketing** schemat tabeli zawiera następujące kolumny: ProductID, Manufacturer, Category, Segment, Product oraz IsCompete.

**Przykładowy zestaw danych obiektu JSON**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

W przypadku schematu tabeli usługi Power BI można użyć następujących typów danych.

## <a name="power-bi-table-data-types"></a>Typy danych tabeli usługi Power BI
| **Typ danych** | **Ograniczenia** |
| --- | --- |
| Int64 |Wartości Int64.MaxValue i Int64.MinValue nie są dozwolone. |
| Double (liczba o podwójnej precyzji) |Wartości Double.MaxValue i Double.MinValue nie są dozwolone. Wartość NaN nie jest obsługiwana. Wartości +Infinity i -Infinity nie są obsługiwane w niektórych funkcjach (na przykład Min, Max). |
| Boolean (wartość logiczna) |Brak |
| Datetime (data/godzina) |Podczas ładowania danych wartości zawierające ułamki określające dzień są przeliczane na całkowite wielokrotności 1/300 sekundy (3,33 ms). |
| String (ciąg) |Obecnie maksymalnie 128 000 znaków. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Dowiedz się więcej na temat wypychania danych do usługi Power BI
Aby rozpocząć wypychanie danych do zestawu danych, zobacz [Krok 1. Rejestrowanie aplikacji w usłudze Azure AD](walkthrough-push-data-register-app-with-azure-ad.md) w lewym okienku nawigacji.

[Następny krok >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Następne kroki
[Tworzenie konta w usłudze Power BI](create-an-azure-active-directory-tenant.md)  
[Tworzenie zestawu danych](https://msdn.microsoft.com/library/mt203562.aspx)  
[Pobieranie zestawów danych](https://msdn.microsoft.com/library/mt203567.aspx)  
[Dodawanie wierszy](https://msdn.microsoft.com/library/mt203561.aspx)  
[Pobieranie grup](https://msdn.microsoft.com/library/mt243842.aspx)  
[JSON: Wprowadzenie](http://json.org/)  
[Omówienie interfejsu API REST usługi Power BI](overview-of-power-bi-rest-api.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

