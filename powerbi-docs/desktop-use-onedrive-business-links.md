---
title: Używanie linków usługi OneDrive dla Firm w programie Power BI Desktop
description: Używanie linków usługi OneDrive dla Firm w programie Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 006a2d6b64bfbaf1284759f176f379320dfae3b6
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="use-onedrive-for-business-links-in-power-bi-desktop"></a>Używanie linków usługi OneDrive dla Firm w programie Power BI Desktop
Wiele osób przechowuje na dysku usługi OneDrive dla Firm skoroszyty programu Excel, które by się świetnie nadawały do użytku w programie Power BI Desktop. W programie **Power BI Desktop** można używać linków online do plików programu **Excel** przechowywanych w usłudze **OneDrive dla Firm**, aby tworzyć raporty i wizualizacje. Możesz użyć konta grupy usługi **OneDrive dla Firm** lub swojego osobistego konta usługi **OneDrive dla Firm**.

Uzyskiwanie linku online z usługi **OneDrive dla Firm** wymaga wykonania kilku określonych kroków. W poniższych sekcjach opisano te kroki, które umożliwiają udostępnianie linku w grupach, na różnych komputerach oraz wśród współpracowników.

## <a name="get-a-link-from-excel-starting-in-the-browser"></a>Uzyskiwanie linku z programu Excel, zaczynając od przeglądarki
1. Przejdź do swojej lokalizacji usługi OneDrive dla Firm za pomocą przeglądarki. Kliknij prawym przyciskiem myszy plik, którego chcesz użyć, a następnie wybierz polecenie **Otwórz w programie Excel**.
   
   > [!NOTE]
> Interfejs użytkownika Twojej przeglądarki może nie wyglądać dokładnie tak samo, jak na poniższej ilustracji. Istnieje wiele sposobów wybrania polecenia **Otwórz w programie Excel** dla plików w interfejsie przeglądarki usługi **OneDrive dla Firm**. Możesz użyć każdej opcji, która pozwala na otworzenie pliku w programie Excel.
   > 
   > 
   
   ![](media/desktop-use-onedrive-business-links/odb-links_02.png)
2. W programie **Excel** wybierz pozycję **Plik > Informacje** i wybierz link powyżej przycisku **Chroń skoroszyt**. Wybierz pozycję **Kopiuj link do schowka** (w Twojej wersji pozycja może mieć nazwę **Kopiuj ścieżkę do schowka**).
   
   ![](media/desktop-use-onedrive-business-links/odb-links_03.png)

## <a name="use-the-link-in-power-bi-desktop"></a>Używanie linku w programie Power BI Desktop
W programie Power BI Desktop możesz użyć linku, który właśnie został skopiowany do schowka. Wykonaj następujące czynności:

1. W programie Power BI Desktop wybierz pozycję **Pobierz dane > Internet**.
   
   ![](media/desktop-use-onedrive-business-links/odb-links_04.png)
2. Wklej link do okna dialogowego **Z Internetu** (**nie** wybieraj jeszcze przycisku OK).
   
    ![](media/desktop-use-onedrive-business-links/odb-links_05.png)
3. Zwróć uwagę na ciąg *?web=1* na końcu linku — musisz *usunąć ten fragment ciągu internetowego adresu URL* **przed** wybraniem przycisku **OK**, aby program **Power BI Desktop** prawidłowo przeszedł do pliku.
4. Jeśli w programie **Power BI Desktop** zostanie wyświetlony monit o podanie poświadczeń, wybierz pozycję **Windows** (w przypadku lokalnych witryn programu SharePoint) lub pozycję **Konto organizacji** (w przypadku witryn usług Office 365 i OneDrive dla Firm).
   
   ![](media/desktop-use-onedrive-business-links/odb-links_06.png)

Zostanie wyświetlone okno **Nawigator** umożliwiające wybór z listy tabel, arkuszy i zakresów znajdujących się w skoroszycie programu Excel. Od tego momentu możesz korzystać z pliku usługi OneDrive dla Firm, tak jak z każdego innego pliku programu Excel, i tworzyć raporty oraz używać go w zestawach danych, tak jak każdego innego źródła danych.

> [!NOTE]
> Aby użyć pliku usługi **OneDrive dla Firm** jako źródła danych w usłudze Power BI, po włączeniu opcji **Odświeżanie usługi** dla tego pliku upewnij się, że podczas konfigurowania ustawień odświeżania wybrano standard **OAuth2** w obszarze **Metoda uwierzytelniania**. W przeciwnym razie podczas próby nawiązania połączenia lub odświeżenia może wystąpić błąd (taki jak *Nie można zaktualizować poświadczeń źródła danych*). Wybranie standardu **OAuth2** jako metody uwierzytelniania zapobiega temu błędowi poświadczeń.
> 
> 

