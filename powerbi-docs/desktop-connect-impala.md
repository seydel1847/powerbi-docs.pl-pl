---
title: Łączenie się z bazą danych Impala w programie Power BI Desktop
description: Łatwe nawiązywanie połączenia z bazą danych Impala i korzystanie z niej w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 9b00120a0c4c22ba8f031663ab19d94d2c482d3b
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34287698"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Łączenie się z bazą danych Impala w programie Power BI Desktop
W programie Power BI Desktop możesz nawiązać połączenie z bazą danych **Impala** i korzystać z danych źródłowych w taki sam sposób jak w przypadku dowolnego innego źródła danych w programie Power BI Desktop.

## <a name="connect-to-an-impala-database"></a>Łączenie się z bazą danych Impala
Aby nawiązać połączenie z bazą danych **Impala**, wybierz pozycję **Pobierz dane** z poziomu wstążki **Narzędzia główne** w programie Power BI Desktop. Wybierz pozycję **Baza danych** z kategorii po lewej stronie. Zostanie wyświetlona pozycja **Impala**.

![](media/desktop-connect-impala/connect_impala_2.png)

W wyświetlonym oknie **Impala** wpisz lub wklej nazwę serwera Impala w polu i wybierz przycisk **OK**. Pamiętaj, że możesz **zaimportować** dane bezpośrednio do usługi Power BI lub możesz użyć **zapytania bezpośredniego**. Tutaj możesz dowiedzieć się więcej o [używaniu zapytania bezpośredniego](desktop-use-directquery.md).

![](media/desktop-connect-impala/connect_impala_3a.png)

Po wyświetleniu monitu wprowadź poświadczenia lub nawiąż połączenie anonimowo. Łącznik Impala obsługuje uwierzytelnianie anonimowe, podstawowe (nazwa użytkownika i hasło) oraz systemu Windows.

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> Po wprowadzeniu nazwy użytkownika i hasła dla określonego serwera **Impala** program Power BI Desktop będzie używać tych samych poświadczeń przy kolejnych próbach połączenia. Te poświadczenia można zmodyfikować, wybierając pozycję **Plik > Opcje i ustawienia > Ustawienia źródła danych**.
> 
> 

Po pomyślnym nawiązaniu połączenia zostanie wyświetlone okno **Nawigator** z wyświetlonymi danymi dostępnymi na serwerze, z których możesz wybrać jeden lub więcej elementów do zaimportowania i używania w programie **Power BI Desktop**.

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia
Istnieje kilka ograniczeń i zagadnień, które należy wziąć pod uwagę w przypadku łącznika **Impala**:

* Łącznik Impala jest obsługiwany w lokalnej bramie danych przy użyciu dowolnego z trzech obsługiwanych mechanizmów uwierzytelniania.

## <a name="next-steps"></a>Następne kroki
Z poziomu programu Power BI Desktop możesz łączyć się z danymi różnego rodzaju. Więcej informacji na temat źródeł danych znajdziesz w następujących zasobach:

* [Wprowadzenie do programu Power BI Desktop](desktop-getting-started.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)
* [Łączenie się ze skoroszytami programu Excel w programie Power BI Desktop](desktop-connect-excel.md)   
* [Wprowadzanie danych bezpośrednio w programie Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

