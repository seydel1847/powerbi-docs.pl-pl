---
title: Łączenie się z bazą danych Impala w programie Power BI Desktop
description: Łatwe nawiązywanie połączenia z bazą danych Impala i korzystanie z niej w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1b512a3e6ef3ead8d93e1b554fbab3aaed8a2a5a
ms.sourcegitcommit: b343e44dbafc0b718c564402593d4b6e3a8ce97c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2018
ms.locfileid: "51027396"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Łączenie się z bazą danych Impala w programie Power BI Desktop
W programie Power BI Desktop możesz nawiązać połączenie z bazą danych **Impala** i korzystać z danych źródłowych w taki sam sposób jak w przypadku dowolnego innego źródła danych w programie Power BI Desktop.

## <a name="connect-to-an-impala-database"></a>Łączenie się z bazą danych Impala
Aby nawiązać połączenie z bazą danych **Impala**, wykonaj następujące kroki: 

1. Wybierz polecenie **Pobierz dane** na karcie **Narzędzia główne** wstążki w programie Power BI Desktop. 

2. Wybierz pozycję **Baza danych** z kategorii po lewej stronie. Zostanie wyświetlona pozycja **Impala**.

    ![Pobierz dane](media/desktop-connect-impala/connect_impala_2.png)

3. W wyświetlonym oknie **Impala** wpisz lub wklej nazwę serwera Impala w polu. Następnie wybierz przycisk **OK**. Dane możesz **zaimportować** bezpośrednio do usługi Power BI lub możesz użyć trybu **DirectQuery**. Dowiedz się więcej o [używaniu trybu DirectQuery](desktop-use-directquery.md).

    ![Okno Impala](media/desktop-connect-impala/connect_impala_3a.png)

4. Po wyświetleniu monitu wprowadź poświadczenia lub nawiąż połączenie anonimowo. Łącznik Impala obsługuje uwierzytelnianie anonimowe, podstawowe (nazwa użytkownika i hasło) oraz systemu Windows.

    ![Łącznik Impala](media/desktop-connect-impala/connect_impala_4.png)

    > [!NOTE]
    > Po wprowadzeniu nazwy użytkownika i hasła dla określonego serwera **Impala** program Power BI Desktop będzie używać tych samych poświadczeń przy kolejnych próbach połączenia. Te poświadczenia można zmodyfikować, wybierając pozycję **Plik > Opcje i ustawienia > Ustawienia źródła danych**.


5. Po nawiązaniu połączenia zostanie wyświetlone okno **nawigatora** zawierające dane dostępne na serwerze. Wybierz elementy tych danych do zaimportowania i używania w programie **Power BI Desktop**.

    ![Okno Nawigator](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia
Istnieje kilka ograniczeń i zagadnień, które należy wziąć pod uwagę w przypadku łącznika **Impala**:

* Łącznik Impala jest obsługiwany w lokalnej bramie danych przy użyciu dowolnego z trzech obsługiwanych mechanizmów uwierzytelniania.

## <a name="next-steps"></a>Następne kroki
Z poziomu programu Power BI Desktop możesz łączyć się ze źródłami danych różnego rodzaju. Więcej informacji na temat źródeł danych znajdziesz w następujących zasobach:

* [Co to jest Power BI Desktop?](desktop-what-is-desktop.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)
* [Łączenie się ze skoroszytami programu Excel w programie Power BI Desktop](desktop-connect-excel.md)   
* [Wprowadzanie danych bezpośrednio w programie Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

