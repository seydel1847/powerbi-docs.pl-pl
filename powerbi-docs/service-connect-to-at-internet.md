---
title: Łączenie się z pakietem zawartości AT Internet Bridge za pomocą usługi Power BI
description: Pakiet zawartości AT Internet Bridge dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 5afb79f52c4717887ba16d9ca43f913ba3446627
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008378"
---
# <a name="connect-to-at-internet-bridge-with-power-bi"></a>Łączenie się z pakietem zawartości AT Internet Bridge za pomocą usługi Power BI
Usługa AT Internet pozwala uzyskać natychmiastową wartość z danych z wykorzystaniem zunifikowanej cyfrowej platformy analitycznej Analytics Suite. Pakiet zawartości AT Internet Bridge dla usługi Power BI zawiera dane dotyczące wizyt, źródeł, lokalizacji i urządzeń dla witryny.

Połącz się z [pakietem zawartości AT Internet Bridge](https://app.powerbi.com/getdata/services/at-internet-bridge) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-at-internet/pbi_getdata.png) 
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-at-internet/pbi_getservices.png) 
3. Wybierz pozycję **AT Internet Bridge** \> **Pobierz**.
   
   ![](media/service-connect-to-at-internet/atinternet.png)
4. Określ numer witryny internetowej AT, z którą chcesz nawiązać połączenie.
   
   ![](media/service-connect-to-at-internet/params.png)
5. Wybierz opcję **Basic** (podstawowy) jako mechanizm uwierzytelniania, wprowadź nazwę użytkownika i hasło usługi AT Internet, a następnie kliknij przycisk **Zaloguj**.
   
   ![](media/service-connect-to-at-internet/creds.png)
6. Kliknij przycisk **Połącz**, aby rozpocząć proces importowania. Po zakończeniu tego procesu w okienku nawigacji zostaną wyświetlone nowy pulpit nawigacyjny, raport i model. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
    ![](media/service-connect-to-at-internet/atinternet.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Ten pakiet zawartości zawiera dane z ostatnich 45 dni w następujących tabelach:  

    - Conversion  
    - Devices  
    - Localization  
    - Sources  
    - Global Visits  

## <a name="next-steps"></a>Następne kroki
[Co to jest usługa Power BI?](power-bi-overview.md)

[Power BI — podstawowe pojęcia](consumer/end-user-basic-concepts.md)

