---
title: "Zarządzanie magazynem danych"
description: "Dowiedz się, jak można zarządzać magazynem własnego obszaru roboczego lub magazynem danych obszaru roboczego aplikacji, aby móc publikować raporty i zestawy danych."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 06/28/2017
ms.author: asaxton
ms.openlocfilehash: b10e95d9f5817ba989360b3a30c3efd55f30faec
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="manage-your-data-storage"></a>Zarządzanie magazynem danych
Dowiedz się, jak można zarządzać magazynem własnego obszaru roboczego lub magazynem danych obszaru roboczego aplikacji, aby móc publikować raporty i zestawy danych.

Obszary robocze użytkowników i aplikacji mają własne pojemności danych.

* Użytkownicy wersji bezpłatnej i Pro mają magazyn danych o maksymalnej pojemności 10 GB.
* Użytkownicy wersji Pro mogą tworzyć obszary robocze aplikacji z magazynami danych o maksymalnym rozmiarze 10 GB każdy.

Na poziomie dzierżawy łączne użycie nie może przekroczyć 10 GB na użytkownika wersji Pro dla wszystkich użytkowników wersji Pro oraz obszarów roboczych aplikacji w dzierżawie.

Więcej informacji o innych funkcjach [modelu cen usługi Power BI](https://powerbi.microsoft.com/pricing).

Magazyn danych zawiera Twoje zestawy danych i raporty programu Excel oraz elementy, które udostępniły Ci inne osoby. Zestawy danych są dowolnymi źródłami danych, które zostały przekazane lub z którymi nawiązano połączenie, w tym plikami programu Power BI Desktop oraz używanymi skoroszytami programu Excel. Pojemność danych uwzględnia również następujące elementy.

* Zakresy programu Excel przypięte do pulpitu nawigacyjnego.
* Lokalne wizualizacje usług Reporting Services przypięte do pulpitu nawigacyjnego usługi Power BI.
* Przekazane obrazy.

Rozmiar udostępnianego pulpitu nawigacyjnego będzie różnić się zależnie od elementów, które są do niego przypięte. Na przykład w przypadku przypięcia elementów z dwóch raportów należących do dwóch różnych zestawów danych rozmiar będzie obejmować oba zestawy danych.

<a name="manage"/>

## <a name="manage-items-owned-by-you"></a>Zarządzanie elementami będącymi własnością użytkownika
Zobacz, ile miejsca w magazynie danych jest używane w ramach Twojego konta usługi Power BI, i zarządzaj kontem.

1. Aby zarządzać własnym magazynem, przejdź do obszaru **Mój obszar roboczy** w lewym okienku nawigacji.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)
2. Wybierz ikonę koła zębatego ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) w prawym górnym rogu, a następnie wybierz pozycję \> **Zarządzaj magazynem osobistym**.
   
    Na górnym pasku jest wyświetlane wykorzystanie limitu miejsca.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    Zestawy danych i raporty są podzielone na dwie karty:
   
    **Należące do mnie:** Są to raporty i zestawy danych przekazane przez Ciebie do konta usługi Power BI, w tym zestawy danych usługi, takie jak Salesforce i Dynamics CRM.  
    **Należące do innych:** Te raporty i zestawy danych zostały udostępnione Tobie przez inne osoby.
3. Aby usunąć zestaw danych lub raport, wybierz ikonę kosza na śmieci ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).

Należy pamiętać, że Ty lub inna osoba może mieć raporty i pulpity nawigacyjne oparte na zestawie danych. Jeśli usuniesz zestaw danych, te raporty i pulpity nawigacyjne nie będą już działać.

## <a name="manage-your-app-workspace"></a>Zarządzanie obszarem roboczym aplikacji
1. Wybierz strzałkę obok pozycji **Obszary robocze** \> wybierz nazwę obszaru roboczego aplikacji.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. Wybierz ikonę koła zębatego ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) w prawym górnym rogu, a następnie wybierz pozycję \> **Zarządzaj miejscem grupy**.
   
    Na górnym pasku jest wyświetlane wykorzystanie limitu miejsca w magazynie grupy.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    Zestawy danych i raporty są podzielone na dwie karty:
   
    **Należące do nas:** Są to raporty i zestawy danych przekazane przez Ciebie lub inną osobę do konta usługi Power BI grupy, w tym zestawy danych usługi, takie jak Salesforce i Dynamics CRM.
    **Należące do innych:** Te raporty i zestawy danych zostały udostępnione Twojej grupie przez inne osoby.
3. Aby usunąć zestaw danych lub raport, wybierz ikonę kosza na śmieci ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).
   
   > [!NOTE]
   > Każdy członek mający uprawnienia do edycji obszaru roboczego aplikacji ma uprawnienia do usuwania zestawów danych i raportów z obszaru roboczego aplikacji.
   > 
   > 

Należy pamiętać, że Ty lub inna osoba w grupie może mieć raporty i pulpity nawigacyjne oparte na zestawie danych. Jeśli usuniesz zestaw danych, te raporty i pulpity nawigacyjne nie będą już działać.

## <a name="dataset-limits"></a>Limity zestawu danych
Istnieje limit rozmiaru wynoszący 1 GB na zestaw danych importowany do usługi Power BI. Jeśli wybrano, aby zachować środowisko programu Excel zamiast importować dane, będzie występować ograniczenie do 250 MB na zestaw danych.

## <a name="what-happens-when-you-hit-a-limit"></a>Co się stanie po osiągnięciu limitu
Po osiągnięciu limitu pojemności danych w usłudze zostaną wyświetlone monity. 

Wybranie ikony koła zębatego ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) spowoduje wyświetlenie czerwonego paska wskazującego, że przekroczono limit pojemności danych.

![](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

Ta informacja będzie wyświetlana również w obszarze **Zarządzaj magazynem osobistym**.

 ![](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 W przypadku próby wykonania działania, które spowoduje osiągnięcie jednego z limitów, zostanie wyświetlony monit informujący, że przekroczono limit. Możliwe będzie [zarządzanie](#manage) magazynem w celu zmniejszenia ilości danych w magazynie i pozostania w ramach limitu.

 ![](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

