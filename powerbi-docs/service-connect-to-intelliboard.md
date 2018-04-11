---
title: Nawiązywanie połączenia z IntelliBoard przy użyciu usługi Power BI
description: IntelliBoard dla usługi Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: d73a02e754615263a155d3a7e31e47af4b740fd8
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-intelliboard-with-power-bi"></a>Nawiązywanie połączenia z IntelliBoard przy użyciu usługi Power BI
IntelliBoard oferuje uproszczony dostęp do danych systemu zarządzania nauczaniem Moodle za pośrednictwem usług raportowania. Pakiet zawartości IntelliBoard dla usługi Power BI oferuje dodatkowe narzędzia analityczne, w tym metryki dotyczące kursów, zarejestrowanych użytkowników, ogólnej wydajności i aktywności systemu LMS.

Połącz się z [pakietem zawartości IntelliBoard](https://app.powerbi.com/getdata/services/intelliboard) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.  
   
    ![](media/service-connect-to-intelliboard/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.  
   
    ![](media/service-connect-to-intelliboard/services.png)
3. Wybierz pozycję **IntelliBoard**, a następnie opcję **Pobierz**.  
   
    ![](media/service-connect-to-intelliboard/intelliboard.png)
4. Wybierz pozycję **OAuth 2**, a następnie pozycję **Zaloguj**. Po wyświetleniu monitu podaj poświadczenia IntelliBoard.
   
    ![](media/service-connect-to-intelliboard/creds.png)
   
    ![](media/service-connect-to-intelliboard/creds2.png)
5. Po nawiązaniu połączenia automatycznie zostanie załadowany pulpit nawigacyjny, raport i zestaw danych. Po zakończeniu kafelki zostaną zaktualizowane o dane pochodzące z konta IntelliBoard.
   
    ![](media/service-connect-to-intelliboard/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Pakiet zawartości obejmuje dane z następujących tabel:  

    - Działanie  
    - Agenci  
    - Autoryzacja  
    - Kraje  
    - Postępy kursów  
    - Rejestracje
    - Język  
    - Platforma  
    - Sumy  
    - Postępy użytkowników    

## <a name="system-requirements"></a>Wymagania systemowe
Aby utworzyć wystąpienia tego pakietu zawartości, wymagane jest konto IntelliBoard z uprawnieniami do powyższych tabel.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

