---
title: "Łączenie się z usługą appFigures za pomocą usługi Power BI"
description: "Usługa appFigures w usłudze Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
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
ms.author: yshoukry
ms.openlocfilehash: 950c69282e74b42fca4034aaabb9487bad370219
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-appfigures-with-power-bi"></a>Łączenie się z usługą appFigures za pomocą usługi Power BI
Śledzenie ważnych statystyk dotyczących aplikacji jest bardzo proste dzięki usłudze Power BI i pakietowi zawartości appFigures. Usługa Power BI pobiera dane, w tym informacje o sprzedaży aplikacji, pobraniach i statystykach dotyczących reklam, a następnie tworzy domyślny pulpit nawigacyjny i powiązane raporty w oparciu o te dane.

Połącz się z [pakietem zawartości appFigures](https://app.powerbi.com/getdata/services/appfigures) lub przeczytaj więcej na temat [integracji usługi appFigures](https://powerbi.microsoft.com/integrations/appfigures) z usługą Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-appfigures/pbi_getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-appfigures/pbi_getservices.png)
3. Wybierz pozycję **appFigures** \> **Pobierz**.
   
   ![](media/service-connect-to-appfigures/appfigures.png)
4. Jako **metodę uwierzytelniania** wybierz opcję **oAuth2** \> **Zaloguj**. Po wyświetleniu monitu wprowadź swoje poświadczenia appFigures i postępuj zgodnie z procesem uwierzytelniania appFigures.
   
   Przy pierwszym połączeniu usługa Power BI wyświetla monit o pozwolenie na dostęp tylko do odczytu do Twojego konta. Kliknij przycisk **Zezwalaj**, aby rozpocząć proces importowania. Może to zająć kilka minut w zależności od ilości danych na Twoim koncie.
   
   ![](media/service-connect-to-appfigures/appfiguresdoc_06.png)
5. Po zaimportowaniu danych przez usługę Power BI zobaczysz nowy pulpit nawigacyjny, raport i zestaw danych w okienku nawigacji po lewej stronie. Nowe elementy są oznaczone żółtą gwiazdką \*:
   
    ![](media/service-connect-to-appfigures/pbi_appfigures3.png)
6. Wybierz pulpit nawigacyjny usługi appFigures. Jest to domyślny pulpit nawigacyjny utworzony przez usługę Power BI do wyświetlania Twoich danych. Możesz modyfikować pulpit nawigacyjny, aby wyświetlać dane w dowolny sposób.
   
    ![](media/service-connect-to-appfigures/appfiguresdoc_01.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
W usłudze Power BI są dostępne następujące dane pochodzące z usługi appFigures.

| **Nazwa tabeli** | **Opis** |
| --- | --- |
| Kraje |Ta tabela zawiera informacje o nazwie kraju. |
| Daty |Ta tabela zawiera daty od dzisiejszej do najwcześniejszej daty publikacji aplikacji, które są aktywne i widoczne na Twoim koncie appFigures. |
| Zdarzenia |Ta tabela zawiera codzienne informacje o pobraniach, sprzedaży i reklamach dotyczące każdej aplikacji według kraju. Należy pamiętać, że w jednej tabeli znajdują się zarówno informacje o aplikacji, jak i o zakupach w aplikacji — możesz użyć kolumny <strong>Typ</strong>, aby je rozróżnić. |
| Inapps |Ta tabela zawiera dane o różnych typach zakupów w aplikacji, które są skojarzone z aktywnymi, widocznymi aplikacjami na Twoim koncie appFigures. |
| Produkty |Ta tabela zawiera dane o różnych aplikacjach, które są aktywne i widoczne na Twoim koncie appFigures. |

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Jeśli dane z niektórych aplikacji nie są wyświetlane w usłudze Power BI, upewnij się, że te aplikacje są widoczne i aktywne na karcie **Aplikacje** w witrynie appFigures.

![](media/service-connect-to-appfigures/appfiguresdoc_11.png)

## <a name="next-steps"></a>Następne kroki
* [Wprowadzenie do usługi Power BI](service-get-started.md)
* [Pobieranie danych w usłudze Power BI](service-get-data.md)
