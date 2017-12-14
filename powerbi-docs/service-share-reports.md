---
title: "Udostępnianie raportów usługi Power BI współpracownikom"
description: "Dowiedz się, jak udostępniać raporty usługi Power BI oraz filtrowane raporty współpracownikom w Twojej organizacji."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: complete
qualitydate: 06/22/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/14/2017
ms.author: maggies
ms.openlocfilehash: 022f085d12d7dc872052ca9205deca264b1c0418
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="share-power-bi-reports-with-your-coworkers"></a>Udostępnianie raportów usługi Power BI współpracownikom
*Udostępnianie* to świetna metoda na zapewnienie kilku osobom dostępu do Twojego pulpitu nawigacyjnego i raportów. Usługa Power BI oferuje [kilka sposobów współpracy i rozpowszechniania raportów](service-how-to-collaborate-distribute-dashboards-reports.md). Udostępnianie to jedna z tych metod.

Zarówno osoba udostępniająca, jak i adresaci zawartości muszą mieć [licencję na usługę Power BI Pro](service-free-vs-pro.md) lub zawartość musi być uwzględniona w [pojemności Premium](service-premium.md). Masz jakieś sugestie? Zespół zajmujący się usługą Power BI chętnie zapozna się z Twoją opinią. Aby ją przekazać, przejdź do [witryny społeczności usługi Power BI](https://community.powerbi.com/).

Raport możesz udostępnić w obszarze Mój obszar roboczy lub obszarze roboczym aplikacji współpracownikom znajdującym się w tej samej domenie poczty e-mail co Ty. Osoby, którym udostępniasz raport, mogą go wyświetlać i korzystać z niego, ale nie mogą go edytować. O ile nie zastosowano [zabezpieczeń na poziomie wiersza](service-admin-rls.md), osoby te widzą w raporcie te same dane co Ty. 

## <a name="share-a-power-bi-report"></a>Udostępnianie raportu usługi Power BI
1. W usłudze Power BI [utwórz pulpit nawigacyjny](service-dashboard-create.md) z co najmniej jednym kafelkiem połączonym z raportem, który chcesz udostępnić. 
   
    Nawet jeśli chcesz udostępnić tylko raport, musisz najpierw utworzyć pulpit nawigacyjny połączony z tym raportem i go udostępnić. 

1. W prawym górnym rogu pulpitu nawigacyjnego wybierz pozycję **Udostępnij**.

     ![Wybieranie pozycji Udostępnij](media/service-share-reports/power-bi-share-upper-right.png)
  
2. Wpisz adresy odbiorców. Jeśli nie chcesz wysyłać tym osobom wiadomości e-mail o pulpicie nawigacyjnym, wyczyść pole wyboru **Wyślij powiadomienie e-mail do adresatów**.

     ![Czyszczenie pola wyboru Wyślij powiadomienie e-mail](media/service-share-reports/power-bi-share-dont-send-mail.png)

4. Wybierz pozycję **Udostępnij**.

      Osoby, którym udostępniono pulpit nawigacyjny, mogą teraz wyświetlać raport źródłowy. 

1. Otwórz raport w usłudze Power BI, skopiuj adres URL strony z raportem i wyślij go do współpracowników. 
   
    Po wybraniu linku przez inną osobę usługa Power BI otworzy raport w wersji tylko do odczytu.

## <a name="share-a-filtered-version-of-a-report"></a>Udostępnianie filtrowanej wersji raportu
Czasami zachodzi potrzeba udostępnienia filtrowanej wersji raportu. Może to być raport zawierający tylko dane dotyczące określonego miasta, sprzedawcy lub roku. Można to zrobić, tworząc niestandardowy adres URL.

1. Otwórz raport w [widoku do edycji](service-reading-view-and-editing-view.md), zastosuj filtr i zapisz raport.
   
   W tym przykładzie przefiltrujemy dane z zestawu [Retail Analysis](sample-tutorial-connect-to-the-samples.md), wyświetlając tylko wartości, w których pole **Territory** ma wartość **NC**.
   
   ![Okienko filtru raportu](media/service-share-reports/power-bi-filter-report2.png)
2. Dodaj następujący ciąg na końcu adresu URL strony z raportem:
   
   ?filter=*nazwatabeli*/*nazwapola* eq *wartość*
   
    Pole musi być **ciągiem**, a parametry *nazwatabeli* i *nazwapola* nie mogą zawierać spacji.
   
   W naszym przykładzie nazwa tabeli to **Store**, nazwa pola to **Territory**, a wartość, według której chcemy filtrować, to **NC**:
   
    ?filter=Store/Territory eq NC
   
   ![Adres URL przefiltrowanego raportu](media/service-share-reports/power-bi-filter-url3.png)
   
   Przeglądarka dodaje znaki specjalne reprezentujące ukośniki i spacje. Końcowy ciąg wygląda następująco:
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-10a61f70f2f5/ReportSection2?filter=Store%252FTerritory%20eq%20NC
3. Wyślij ten adres URL do współpracowników. 
   
   Po wybraniu linku przez inną osobę usługa Power BI otworzy przefiltrowany raport w wersji tylko do odczytu.

## <a name="next-steps"></a>Następne kroki
* Chcesz przesłać opinię? Jeśli masz sugestie, przejdź do [witryny społeczności usługi Power BI](https://community.powerbi.com/).
* [Jak współpracować nad pulpitami nawigacyjnymi i raportami oraz je udostępniać?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Udostępnianie pulpitu nawigacyjnego](service-share-dashboards.md)
* Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/).

