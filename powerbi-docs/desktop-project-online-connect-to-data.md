---
title: "Project Online: łączenie się z danymi za pomocą programu Power BI Desktop"
description: "Project Online: łączenie się z danymi za pomocą programu Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: c85262d14101900443eff276ce0471ba5c08322f
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2017
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online: łączenie się z danymi za pomocą programu Power BI Desktop
Możesz łączyć się z danymi w usłudze Project Online za pomocą programu Power BI Desktop.

### <a name="step-1-download-power-bi-desktop"></a>Krok 1. Pobieranie programu Power BI Desktop
1. [Pobierz program Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521662), a następnie uruchom instalatora, aby pobrać program **Power BI Desktop** na komputer.

### <a name="step-2-connect-to-project-online-with-odata"></a>Krok 2. Łączenie z usługą Project Online za pomocą usługi OData
1. Otwórz program **Power BI Desktop**.
2. Na ekranie *Zapraszamy* wybierz pozycję **Pobierz dane**.
3. Wybierz pozycję **Źródło danych OData** i wybierz pozycję **Połącz**.
4. Wprowadź adres źródła danych OData w polu adresu URL, a następnie kliknij przycisk OK.
   
   Jeśli adres witryny aplikacji Project Web App przypomina https://\<nazwa_dzierżawy\>.sharepoint.com/sites/pwa, adres do wprowadzenia dla źródła danych OData to https://\<nazwa_dzierżawy\>.sharepoint.com/sites/pwa/\_api/Projectdata.
   
   W naszym przykładzie używamy adresu https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Program Power BI Desktop wyświetli monit o uwierzytelnienie za pomocą konta usługi Office 365. Wybierz konto organizacyjne, a następnie wprowadź swoje poświadczenia.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

Tutaj możesz wybrać tabele, z którymi chcesz utworzyć połączenie i dla których chcesz utworzyć zapytanie.  Potrzebujesz informacji o tym, jak rozpocząć pracę?  W następującym wpisie w blogu przedstawiono sposób tworzenia wykresu postępu realizacji na podstawie danych usługi Project Online.  Wpis w blogu dotyczy łączenia się z usługą Project Online za pomocą dodatku Power Query, ale ma również zastosowanie w przypadku programu Power BI Desktop.

[Creating burndown charts for Project using Power Pivot and Power Query (Tworzenie wykresów postępu realizacji dla programu Project przy użyciu dodatków Power Pivot i Power Query)](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)
