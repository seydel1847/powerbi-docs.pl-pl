---
title: 'Project Online: łączenie się z danymi za pomocą programu Power BI Desktop'
description: 'Project Online: łączenie się z danymi za pomocą programu Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6cae9bdfbb89e8c3a11e8ee3fec45327296319b3
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34288917"
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

Pamiętaj, że konto, którego używasz do nawiązania połączenia ze źródłem danych OData, musi mieć co najmniej dostęp na poziomie Przeglądarka portfeli do witryny Project Web App. 

Tutaj możesz wybrać tabele, z którymi chcesz utworzyć połączenie i dla których chcesz utworzyć zapytanie.  Potrzebujesz informacji o tym, jak rozpocząć pracę?  W następującym wpisie w blogu przedstawiono sposób tworzenia wykresu postępu realizacji na podstawie danych usługi Project Online.  Wpis w blogu dotyczy łączenia się z usługą Project Online za pomocą dodatku Power Query, ale ma również zastosowanie w przypadku programu Power BI Desktop.

[Creating burndown charts for Project using Power Pivot and Power Query (Tworzenie wykresów postępu realizacji dla programu Project przy użyciu dodatków Power Pivot i Power Query)](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

