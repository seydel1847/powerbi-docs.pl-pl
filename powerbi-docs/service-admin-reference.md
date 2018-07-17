---
title: Polecenia cmdlet programu PowerShell, interfejsy API REST i zestaw SDK platformy .NET na potrzeby administracji usługi Power BI
description: Dowiedz się więcej na temat sposobów administrowania usługą Power BI za pomocą skryptów i interfejsów API programowania.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: overview
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: ffb2ae077add5756af63f07d8f3da830e075e0b4
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "36945287"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>Polecenia cmdlet programu PowerShell, interfejsy API REST i zestaw SDK platformy .NET na potrzeby administracji usługi Power BI
Usługa Power BI umożliwia administratorom tworzenie skryptów na potrzeby typowych zadań za pomocą poleceń cmdlet programu PowerShell. Udostępnia ona również interfejsy API REST i oferuje zestaw SDK platformy .NET służący do opracowywania rozwiązań administracyjnych. W tym temacie przedstawiono listę poleceń cmdlet i odpowiadającą im metodę zestawu SDK oraz punkt końcowy interfejsu API REST. Aby uzyskać więcej informacji, zobacz:

  - [Pobieranie](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) programu PowerShell i jego [dokumentacja](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
  - [Dokumentacja](https://docs.microsoft.com/rest/api/power-bi/admin) interfejsu API REST
  - [Pobieranie](https://www.nuget.org/packages/Microsoft.PowerBI.Api/) zestawu SDK platformy .NET 


| **Nazwa polecenia cmdlet** | **Metoda zestawu SDK** | **Punkt końcowy interfejsu API REST** | **Opis** |
| --- | --- | --- | --- |
| **Get-PowerBIDatasource** | Datasets\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Pobiera źródła danych dla danego zestawu danych. |
| **Get-PowerBIDataset** | Datasets\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | Pobiera pełną listę zestawów danych w dzierżawie usługi Power BI. |
| **Get-PowerBIWorkspace** | Groups\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | Pobiera pełną listę obszarów roboczych w dzierżawie usługi Power BI. |
| **Add-PowerBIWorkspaceUser** | Groups\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | Dodaje użytkownika jako członka do danego obszaru roboczego. |
| **Remove-PowerBIWorkspaceUser** | Groups\_DeleteUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Usuwa użytkownika z listy członkostwa danego obszaru roboczego. |
| **Restore-PowerBIWorkspace** | Groups\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | Przywraca usunięty obszar roboczy. |
| **Set-PowerBIWorkspace** | Groups\_UpdateGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId} | Aktualizuje właściwości danego obszaru roboczego. |
| **Get-PowerBIDataset -WorkspaceId** | Groups\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/datasets | Pobiera zestawy danych w ramach danego obszaru roboczego. |
| **Export-PowerBIReport** | Reports\_ExportReportAsAdmin | Nie dotyczy | Eksportuje dany raport do pliku lokalnego. |
| **Get-PowerBIReport** | Reports\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | Pobiera pełną listę raportów w dzierżawie usługi Power BI. |
| **Get-PowerBIDashboard** | Dashboards\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | Pobiera pełną listę pulpitów nawigacyjnych w dzierżawie usługi Power BI. |
| **Get-PowerBIDashboard -WorkspaceId** | Grupy\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Pobiera pulpity nawigacyjne w ramach danego obszaru roboczego. |
| **Get-PowerBITile -DashboardId** | Dashboards\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Pobiera kafelki danego pulpitu nawigacyjnego. |
| **Get-PowerBIReport -WorkspaceId** | Groups\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/reports | Pobiera raporty w ramach danego obszaru roboczego. |
| **Get-PowerBIImport** | Imports\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | Pobiera pełną listę operacji importu w dzierżawie usługi Power BI. |
| **Connect-PowerBIServiceAccount** | Nie dotyczy | Nie dotyczy | Loguje do usługi Power BI i rozpoczyna sesję. |
| **Disconnect-PowerBIServiceAccount** | Nie dotyczy | Nie dotyczy | Wylogowuje z usługi Power BI i zamyka istniejącą sesję. |
| **Invoke-PowerBIRestMethod** | Nie dotyczy | Nie dotyczy | Wysyła dowolne wywołania interfejsu API REST do usługi Power BI. |
| **Get-PowerBIAccessToken** | Nie dotyczy | Nie dotyczy | Uzyskuje token dostępu usługi Power BI w ramach sesji. |
| **Resolve-PowerBIError** | Nie dotyczy | Nie dotyczy | Uzyskuje szczegółowe informacje o błędach dla nieudanych wywołań poleceń cmdlet. |