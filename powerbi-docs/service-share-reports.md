---
title: Udostępnianie filtrowanego raportu usługi Power BI współpracownikom
description: Dowiedz się, jak filtrować raport usługi Power BI i udostępniać go współpracownikom w Twojej organizacji.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 05bdb9ccca7715b74cb18462f215f7d1bf640526
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279770"
---
# <a name="share-a-filtered-power-bi-report-with-your-coworkers"></a>Udostępnij filtrowane raportu usługi Power BI współpracownikom
*Udostępnianie* to świetna metoda na zapewnienie kilku osobom dostępu do Twojego pulpitu nawigacyjnego i raportów. Usługa Power BI oferuje również [kilka innych sposobów współpracy i rozpowszechniania raportów](service-how-to-collaborate-distribute-dashboards-reports.md).

Zarówno osoba udostępniająca, jak i adresaci zawartości muszą mieć [licencję na usługę Power BI Pro](service-features-license-type.md) lub zawartość musi być uwzględniona w [pojemności Premium](service-premium.md). 

Raport w usłudze Power BI można udostępniać współpracownikom w tej samej domenie poczty e-mail z większości miejsc: Ulubione, Ostatnie, Udostępnione mi (jeśli właściciel to umożliwia), Mój obszar roboczy lub z innych obszarów roboczych. Współpracownicy, którym udostępniasz raport, mogą go wyświetlać i korzystać z niego, ale nie mogą go edytować. O ile nie zastosowano [zabezpieczeń na poziomie wiersza](service-admin-rls.md), osoby te widzą w raporcie te same dane co Ty. 

Czasami zachodzi potrzeba udostępnienia filtrowanej wersji raportu. Może to być raport zawierający tylko dane dotyczące określonego miasta, sprzedawcy lub roku. Spróbuj utworzyć niestandardowy adres URL. Raport zostanie przefiltrowany, gdy odbiorcy otworzą go po raz pierwszy. Mogą oni usunąć filtr, modyfikując adres URL.

## <a name="filter-and-share-a-report"></a>Filtrowanie i udostępnianie raportu

1. Otwórz raport w [widoku do edycji](consumer/end-user-reading-view.md), zastosuj filtr i zapisz raport.
   
   W tym przykładzie przefiltrujemy dane z [przykładu Retail Analysis](sample-tutorial-connect-to-the-samples.md), aby wyświetlić tylko wartości, w których pole **Territory** ma wartość **NC**.
   
   ![Okienko filtru raportu](media/service-share-reports/power-bi-filter-report2.png)
2. Dodaj następujący ciąg na końcu adresu URL strony z raportem:
   
   ?filter=*nazwatabeli*/*nazwapola* eq *wartość*
   
    Pole musi być typu **ciąg**. Wartość *tablename* ani *fieldname* nie może zawierać spacji.
   
   W naszym przykładzie nazwa tabeli to **Store**, nazwa pola to **Territory**, a wartość, według której chcemy filtrować, to **NC**:
   
    ?filter=Store/Territory eq 'NC'
   
   ![Adres URL przefiltrowanego raportu](media/service-share-reports/power-bi-filter-url3.png)
   
   Przeglądarka dodaje znaki specjalne reprezentujące ukośniki, spacje i apostrofy. Końcowy ciąg wygląda następująco:
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

3. [Udostępnij raport](service-share-dashboards.md), ale wyczyść pole wyboru **Wyślij powiadomienie e-mail do adresatów**. 

    ![Okno dialogowe Udostępnij raport](media/service-share-reports/power-bi-share-report-dialog.png)

4. Wyślij łącze z utworzonym wcześniej filtrem.

## <a name="next-steps"></a>Następne kroki
* Chcesz przesłać opinię? Jeśli masz sugestie, przejdź do [witryny społeczności usługi Power BI](https://community.powerbi.com/).
* [Jak współpracować nad pulpitami nawigacyjnymi i raportami oraz je udostępniać?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Udostępnianie pulpitu nawigacyjnego](service-share-dashboards.md)
* Masz więcej pytań? [Odwiedź Społeczność usługi Power BI](http://community.powerbi.com/).

