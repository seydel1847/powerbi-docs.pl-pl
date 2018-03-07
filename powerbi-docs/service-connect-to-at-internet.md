---
title: "Łączenie się z pakietem zawartości AT Internet Bridge za pomocą usługi Power BI"
description: "Pakiet zawartości AT Internet Bridge dla usługi Power BI"
services: powerbi
documentationcenter: 
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: fdbf43c5a0f6b031f8a3ef71363cb6db33bc63af
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
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

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Ten pakiet zawartości zawiera dane z ostatnich 45 dni w następujących tabelach:  

    - Conversion  
    - Devices  
    - Localization  
    - Sources  
    - Global Visits  

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Power BI — podstawowe pojęcia](service-basic-concepts.md)

