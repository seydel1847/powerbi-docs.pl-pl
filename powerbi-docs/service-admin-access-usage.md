---
title: Znajdowanie zalogowanych użytkowników usługi Power BI
description: Jeśli administrator dzierżawy chce dowiedzieć się, kto jest zalogowany do usługi Power BI, może uzyskać wgląd za pomocą raportów dostępu i użycia usługi Azure Active Directory.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/31/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: f685a900465cc0f1b635aad7609aaae4356da6b3
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284638"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Znajdowanie zalogowanych użytkowników usługi Power BI

Jeśli administrator dzierżawy chce dowiedzieć się, kto jest zalogowany do usługi Power BI, powinien [użyć raportów dostępu i użycia usługi Azure Active Directory](/azure/active-directory/reports-monitoring/concept-sign-ins), aby uzyskać wgląd w te informacje.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Raport aktywności zawiera użyteczne informacje, ale nie identyfikuje typu licencji poszczególnych użytkowników. Licencje można wyświetlać w centrum administracyjnym usługi Office 365.

## <a name="requirements"></a>Wymagania

Każdy użytkownik (w tym użytkownik niebędący administratorem) może wyświetlić raport własnych logowań, ale jeśli chcesz wyświetlić raport dotyczący wszystkich użytkowników, musisz spełniać poniższe wymagania.

* Twoja dzierżawa musi mieć skojarzoną licencję usługi Azure AD Premium.

* Musisz pełnić jedną z następujących ról: administrator globalny, administrator zabezpieczeń lub czytelnik zabezpieczeń.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Wyświetlanie informacji o logowaniach w witrynie Azure Portal

Aby wyświetlić działania związane z logowaniem, wykonaj poniższe kroki.

1. W witrynie **Azure Portal** wybierz pozycję **Azure Active Directory**.

1. W obszarze **Monitorowanie** wybierz pozycję **Logowania**.
   
    ![Operacje logowania do usługi Azure AD](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Przefiltruj aplikacje, wybierając pozycję **Microsoft Power BI** lub **Power BI Gateway**, i wybierz pozycję **Zastosuj**.

    Pozycja **Microsoft Power BI** powoduje odfiltrowanie działań logowania związanych z usługą, a pozycja **Power BI Gateway** — działań logowania do lokalnej bramy danych.
   
    ![Filtrowanie operacji logowania](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Eksportowanie danych

Dostępne są dwie opcje eksportowania danych logowania: pobranie pliku CSV lub użycie programu PowerShell. W górnej części raportu logowania wybierz jedną z następujących opcji:

* **Pobierz** — aby pobrać plik CSV zawierający bieżące, odfiltrowane dane.

* **Skrypt** — aby pobrać skrypt programu PowerShell umożliwiający uzyskanie bieżących, odfiltrowanych danych. W razie potrzeby można zaktualizować filtr w skrypcie.

![Pobieranie pliku CSV lub skryptu](media/service-admin-access-usage/download-sign-in-data-csv.png)

## <a name="data-retention"></a>Przechowywanie danych

Dane logowania są dostępne przez maksymalnie 30 dni. Aby uzyskać więcej informacji, zobacz [Zasady przechowywania raportów usługi Azure Active Directory](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Następne kroki

[Korzystanie z inspekcji w ramach organizacji](service-admin-auditing.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

