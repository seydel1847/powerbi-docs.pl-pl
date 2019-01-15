---
title: Polecenia cmdlet programu PowerShell, interfejsy API REST i zestaw SDK platformy .NET dla administratorów
description: Dowiedz się więcej na temat sposobów administrowania usługą Power BI za pomocą skryptów i interfejsów API programowania.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: overview
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 86a90396c82a597e8b4f535b71e029bfa21328a4
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280922"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>Polecenia cmdlet programu PowerShell, interfejsy API REST i zestaw SDK platformy .NET na potrzeby administracji usługi Power BI
Usługa Power BI umożliwia administratorom tworzenie skryptów na potrzeby typowych zadań za pomocą poleceń cmdlet programu PowerShell. Udostępnia ona również interfejsy API REST i oferuje zestaw SDK platformy .NET służący do opracowywania rozwiązań administracyjnych. W tym temacie przedstawiono listę poleceń cmdlet i odpowiadającą im metodę zestawu SDK oraz punkt końcowy interfejsu API REST. Aby uzyskać więcej informacji, zobacz:

- [Pobieranie](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) programu PowerShell i jego [dokumentacja](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- [Dokumentacja](https://docs.microsoft.com/rest/api/power-bi/admin) interfejsu API REST
- [Pobieranie](https://www.nuget.org/packages/Microsoft.PowerBI.Api/) zestawu SDK platformy .NET

> Aby poniższe polecenia działały względem dzierżawy na potrzeby administracji, należy wywoływać je przy użyciu elementu `-Scope Organization`.

| **Nazwa polecenia cmdlet** | **Aliasy** | **Metoda zestawu SDK** | **Punkt końcowy interfejsu API REST** | **Opis** |
| --- | --- | --- | --- | --- |
| `Get-PowerBIDatasource` | Nie dotyczy | `Datasets_GetDataSourcesAsAdmin` | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Pobiera źródła danych dla danego zestawu danych. |
| `Get-PowerBIDataset` | Nie dotyczy | `Datasets_GetDatasetsAsAdmin` | /v1.0/myorg/admin/datasets | Pobiera pełną listę zestawów danych w dzierżawie usługi Power BI. |
| `Get-PowerBIWorkspace` | `Get-PowerBIGroup` | `Groups_GetGroupsAsAdmin` | /v1.0/myorg/admin/groups | Pobiera pełną listę obszarów roboczych w dzierżawie usługi Power BI. |
| `Add-PowerBIWorkspaceUser` | `Add-PowerBIGroupUser` | `Groups_AddUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users | Dodaje użytkownika jako członka do danego obszaru roboczego. |
| `Remove-PowerBIWorkspaceUser` | `Remove-PowerBIGroupUser` | `Groups_DeleteUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Usuwa użytkownika z listy członkostwa danego obszaru roboczego. |
| `Restore-PowerBIWorkspace` |`Restore-PowerBIGroup` | `Groups_RestoreDeletedGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/restore | Przywraca usunięty obszar roboczy. |
| `Set-PowerBIWorkspace` |`Set-PowerBIGroup` | `Groups_UpdateGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId} | Aktualizuje właściwości danego obszaru roboczego. |
| `Get-PowerBIDataset -WorkspaceId` | Nie dotyczy | `Groups_GetDatasetsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/datasets | Pobiera zestawy danych w ramach danego obszaru roboczego. |
| `Get-PowerBIReport` | Nie dotyczy | `Reports_GetReportsAsAdmin` | /v1.0/myorg/admin/reports | Pobiera pełną listę raportów w dzierżawie usługi Power BI. |
| `Get-PowerBIDashboard` | Nie dotyczy | `Dashboards_GetDashboardsAsAdmin` | /v1.0/myorg/admin/dashboards | Pobiera pełną listę pulpitów nawigacyjnych w dzierżawie usługi Power BI. |
| `Get-PowerBIDashboard -WorkspaceId` | Nie dotyczy | `Groups_GetDashboardsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Pobiera pulpity nawigacyjne w ramach danego obszaru roboczego. |
| `Get-PowerBITile` | `Get-PowerBIDashboardTile` | `Dashboards_GetTilesAsAdmin` | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Pobiera kafelki danego pulpitu nawigacyjnego. |
| `Get-PowerBIReport` | Nie dotyczy | `Groups_GetReportsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/reports | Pobiera raporty w ramach danego obszaru roboczego. |
| `Get-PowerBIImport` | Nie dotyczy | `Imports_GetImportsAsAdmin` | /v1.0/myorg/admin/imports | Pobiera pełną listę operacji importu w dzierżawie usługi Power BI. |
| `Connect-PowerBIServiceAccount` | `Login-PowerBI` &  `Login-PowerBIServiceAccount` | Nie dotyczy | Nie dotyczy | Loguje do usługi Power BI i rozpoczyna sesję. |
| `Disconnect-PowerBIServiceAccount` | `Logout-PowerBI` & `Logout-PowerBIServiceAccount` | Nie dotyczy | Nie dotyczy | Wylogowuje z usługi Power BI i zamyka istniejącą sesję. |
| `Invoke-PowerBIRestMethod`| Nie dotyczy | NIE DOTYCZY | Nie dotyczy | Wysyła dowolne wywołania interfejsu API REST do usługi Power BI. |
| `Get-PowerBIAccessToken`| Nie dotyczy | NIE DOTYCZY | Nie dotyczy | Uzyskuje token dostępu usługi Power BI w ramach sesji. |
| `Resolve-PowerBIError`| Nie dotyczy | NIE DOTYCZY | Nie dotyczy | Uzyskuje szczegółowe informacje o błędach dla nieudanych wywołań poleceń cmdlet. |
