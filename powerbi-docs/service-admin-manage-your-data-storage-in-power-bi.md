---
title: Zarządzanie magazynem danych w obszarach roboczych
description: Dowiedz się, jak można zarządzać magazynem danych we własnym obszarze roboczym lub obszarze roboczym aplikacji, aby móc nadal publikować raporty i zestawy danych.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2018
ms.author: maggies
LocalizationGroup: Administration
ms.openlocfilehash: a46fbb0679de30e554003d858e01756b9b242b1b
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280728"
---
# <a name="manage-data-storage-in-power-bi-workspaces"></a>Zarządzanie magazynem danych w obszarach roboczych usługi Power BI

Dowiedz się, jak można zarządzać magazynem danych we własnym obszarze roboczym lub obszarze roboczym aplikacji, aby móc nadal publikować raporty i zestawy danych.

Obszary robocze użytkowników i aplikacji mają własne pojemności danych:

* Wszyscy użytkownicy mają magazyn danych o maksymalnej pojemności 10 GB.
* Użytkownicy z licencją usługi Power BI Pro mogą tworzyć obszary robocze aplikacji z magazynami danych o maksymalnym rozmiarze 10 GB każdy.
* Obszar roboczy aplikacji w pojemności Premium nie wlicza się do magazynu użytkownika usługi Power BI Pro.

Na poziomie dzierżawy łączne użycie nie może przekroczyć 10 GB na użytkownika wersji Pro dla wszystkich użytkowników wersji Pro oraz obszarów roboczych aplikacji w dzierżawie.

Więcej informacji o innych funkcjach [modelu cen usługi Power BI](https://powerbi.microsoft.com/pricing).

Magazyn danych obejmuje Twoje zestawy danych i raporty programu Excel oraz elementy, które udostępniły Ci inne osoby. Zestawy danych to dowolne źródła danych, które zostały przekazane lub z którymi nawiązano połączenie. Te źródła danych obejmują używane pliki programu Power BI Desktop oraz skoroszyty programu Excel. Pojemność danych uwzględnia również następujące elementy.

* Zakresy programu Excel przypięte do pulpitu nawigacyjnego.
* Lokalne wizualizacje usług Reporting Services przypięte do pulpitu nawigacyjnego usługi Power BI.
* Przekazane obrazy.

Rozmiar udostępnianego pulpitu nawigacyjnego różni się zależnie od elementów, które są do niego przypięte. Na przykład w przypadku przypięcia elementów z dwóch raportów należących do dwóch różnych zestawów danych rozmiar obejmuje oba zestawy danych.

<a name="manage"/>

## <a name="manage-items-you-own"></a>Zarządzanie elementami, które należą do Ciebie

Zobacz, ile miejsca w magazynie danych jest używane w ramach Twojego konta usługi Power BI, i zarządzaj kontem.

1. Aby zarządzać własnym magazynem, przejdź do obszaru **Mój obszar roboczy** w lewym okienku nawigacji.
   
    ![Mój obszar roboczy](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)
2. Wybierz ikonę koła zębatego ![Ikona koła zębatego](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) w prawym górnym rogu \> **Zarządzaj magazynem osobistym**.
   
    Na górnym pasku jest wyświetlane wykorzystanie limitu miejsca.
   
    ![Zarządzanie limitem magazynu](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    Zestawy danych i raporty są podzielone na dwie karty:
   
    **Należące do mnie:** Raporty i zestawy danych przekazane przez Ciebie do konta usługi Power BI, w tym zestawy danych usług, takich jak Salesforce i Dynamics CRM.  
    **Należące do innych:** Te raporty i zestawy danych zostały udostępnione Tobie przez inne osoby.
1. Aby usunąć zestaw danych lub raport, wybierz ikonę kosza na śmieci ![ikona kosza na śmieci](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).

Należy pamiętać, że Ty lub inna osoba może mieć raporty i pulpity nawigacyjne oparte na zestawie danych. Jeśli usuniesz zestaw danych, te raporty i pulpity nawigacyjne nie będą już działać.

## <a name="manage-your-app-workspace"></a>Zarządzanie obszarem roboczym aplikacji
1. Wybierz strzałkę obok pozycji **Obszary robocze** \> wybierz nazwę obszaru roboczego aplikacji.
   
    ![Tworzenie obszaru roboczego aplikacji](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. Wybierz ikonę koła zębatego ![Ikona koła zębatego](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) w prawym górnym rogu \> **Zarządzaj magazynem grupy**.
   
    Na górnym pasku jest wyświetlane wykorzystanie limitu miejsca w magazynie grupy.
   
    ![Zarządzanie magazynem obszaru roboczego aplikacji](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    Zestawy danych i raporty są podzielone na dwie karty:
   
    **Należące do nas:** Raporty i zestawy danych przekazane przez Ciebie lub inną osobę do konta usługi Power BI grupy, w tym zestawy danych usług, takich jak Salesforce i Dynamics CRM.
    **Należące do innych:** Te raporty i zestawy danych zostały udostępnione Twojej grupie przez inne osoby.
3. Aby usunąć zestaw danych lub raport, wybierz ikonę kosza na śmieci ![ikona kosza na śmieci](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).
   
   > [!NOTE]
   > Każdy członek mający uprawnienia do edycji obszaru roboczego aplikacji ma uprawnienia do usuwania zestawów danych i raportów z obszaru roboczego aplikacji.
   > 
   > 

Należy pamiętać, że Ty lub inna osoba w grupie może mieć raporty i pulpity nawigacyjne oparte na zestawie danych. Jeśli usuniesz zestaw danych, te raporty i pulpity nawigacyjne nie będą już działać.

## <a name="dataset-limits"></a>Limity zestawu danych
Istnieje limit rozmiaru wynoszący 1 GB na zestaw danych importowany do usługi Power BI. Jeśli wybrano, aby zachować środowisko programu Excel zamiast importować dane, będzie występować ograniczenie do 250 MB na zestaw danych.

## <a name="what-happens-when-you-reach-a-limit"></a>Co się stanie po osiągnięciu limitu
Po osiągnięciu limitu pojemności danych w usłudze będą wyświetlane monity. 

Wybieranie ikony koła zębatego ![ikona koła zębatego](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png)spowoduje wyświetlenie czerwonego paska wskazującego, że przekroczono limit pojemności danych.

![Osiągnięto limit magazynu](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

Ten limit będzie również wyświetlany w obszarze **Zarządzanie magazynem osobistym**.

 ![Zarządzaj magazynem osobistym, osiągnięto limit magazynu](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 W przypadku próby wykonania akcji, która spowoduje osiągnięcie jednego z limitów, zostanie wyświetlony komunikat informujący, że przekroczono limit. Możesz [zarządzać](#manage) magazynem w celu zmniejszenia ilości danych w magazynie i pozostania w ramach limitu.

 ![Przekroczono limit przestrzeni dyskowej](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

