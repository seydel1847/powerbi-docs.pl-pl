---
title: Nawiązywanie połączenia z bazą danych Amazon Redshift w programie Power BI Desktop
description: Łatwe nawiązywanie połączenia z bazą danych Amazon Redshift i korzystanie z niej w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/05/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c90d2ecf5c3722dfa3991d7001f7c5054e48e6a6
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37135127"
---
# <a name="connect-to-amazon-redshift-in-power-bi-desktop"></a>Nawiązywanie połączenia z bazą danych Amazon Redshift w programie Power BI Desktop
W programie **Power BI Desktop** możesz nawiązać połączenie z bazą danych **Amazon Redshift** i korzystać z danych źródłowych w taki sam sposób, jak w przypadku dowolnego innego źródła danych w programie Power BI Desktop.

## <a name="connect-to-an-amazon-redshift-database"></a>Nawiązywanie połączenia z bazą danych Amazon Redshift
Aby nawiązać połączenie z bazą danych **Amazon Redshift**, wybierz pozycję **Pobierz dane** z poziomu wstążki **Narzędzia główne** w programie Power BI Desktop. Wybierz pozycję **Baza danych** z kategorii po lewej stronie. Zostanie wyświetlona pozycja **Amazon Redshift**.

![](media/desktop-connect-redshift/connect_redshift_3.png)

W oknie **Amazon Redshift** wpisz lub wklej w polu nazwę Twojego serwera **Amazon Redshift**. Jako część pola *Serwer* użytkownicy mogą określić port w następującym formacie: *adres_URL_serwera:port*

![](media/desktop-connect-redshift/connect_redshift_4.png)

Po wyświetleniu monitu wprowadź nazwę użytkownika i hasło. Aby uniknąć błędów, należy użyć nazwy serwera, która dokładnie odpowiada certyfikatowi SSL. 

![](media/desktop-connect-redshift/connect_redshift_5.png)

Po pomyślnym nawiązaniu połączenia zostanie wyświetlone okno **Nawigator** z wyświetlonymi danymi dostępnymi na serwerze, z których możesz wybrać jeden lub więcej elementów do zaimportowania i używania w programie **Power BI Desktop**.

![](media/desktop-connect-redshift/connect_redshift_6.png)

Po dokonaniu wyborów w oknie **Nawigator** możesz **załadować** lub**edytować** dane.

* Jeśli zdecydujesz się **załadować** dane, zostanie wyświetlony monit dotyczący wyboru trybu, który ma zostać użyty do załadowania danych: *Import* czy *Zapytanie bezpośrednie*. Aby uzyskać więcej informacji, zapoznaj się z [tym artykułem zawierającym omówienie zapytania bezpośredniego](desktop-use-directquery.md).
* Jeśli wybrano opcję **edytowania** danych, zostanie wyświetlony **Edytor zapytań**, w którym można zastosować szeroką gamę przekształceń i filtrów dotyczących danych, z których wiele ma zastosowanie względem samej bazy danych **Amazon Redshift**  (jeśli jest to obsługiwane).

## <a name="next-steps"></a>Następne kroki
Z poziomu programu Power BI Desktop możesz łączyć się z danymi różnego rodzaju. Więcej informacji na temat źródeł danych znajdziesz w następujących zasobach:

* [Co to jest Power BI Desktop?](desktop-what-is-desktop.md)
* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)
* [Łączenie się ze skoroszytami programu Excel w programie Power BI Desktop](desktop-connect-excel.md)   
* [Wprowadzanie danych bezpośrednio w programie Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

