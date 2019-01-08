---
title: Nawiązywanie połączenia z IntelliBoard przy użyciu usługi Power BI
description: IntelliBoard dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6f3a335bea711f1785f498caf7fbc828abb01c18
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007895"
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

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

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
[Co to jest usługa Power BI?](power-bi-overview.md)

[Power BI — podstawowe pojęcia](consumer/end-user-basic-concepts.md)

