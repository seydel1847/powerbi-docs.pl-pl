---
title: "Łączenie się z pakietem zawartości Troux przy użyciu usługi Power BI"
description: "Pakiet zawartości Troux dla usługi Power BI"
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
ms.openlocfilehash: ec225639ed23f57735081d556c1ac3283dc4d691
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-troux-for-power-bi"></a>Łączenie się z pakietem zawartości Troux dla usługi Power BI
Pakiet zawartości Troux pozwala w całkowicie nowy sposób wizualizować repozytorium architektury przedsiębiorstwa bezpośrednio w usłudze Power BI. Ten pakiet zawartości oferuje zestaw szczegółowych danych dotyczących możliwości biznesowych, aplikacji zapewniających te możliwości oraz technologii obsługujących te aplikacje, które mogą być w pełni dostosowywane przy użyciu usługi Power BI.

Połącz się z [pakietem zawartości Troux](https://app.powerbi.com/getdata/services/troux) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-troux/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-troux/services.png)
3. Wybierz pozycję **Troux** \>  **Pobierz**.
   
   ![](media/service-connect-to-troux/troux.png)
4. Określ adres URL Troux OData. Poniżej znajdują się szczegółowe informacje dotyczące [wyszukiwania tych parametrów](#FindingParams).
   
   ![](media/service-connect-to-troux/params.png)
5. W polu **Metoda uwierzytelniania** wybierz opcję **Podstawowa**, podaj nazwę użytkownika i hasło (z rozróżnianiem wielkości liter), a następnie wybierz pozycję **Zaloguj**.
   
    ![](media/service-connect-to-troux/creds.png)
6. Po zatwierdzeniu proces importowania rozpocznie się automatycznie. Po zakończeniu tego procesu w okienku nawigacji zostaną wyświetlone nowy pulpit nawigacyjny, raport i model. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
     ![](media/service-connect-to-troux/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu Pytania i odpowiedzi](service-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="system-requirements"></a>Wymagania systemowe
Wymagany jest dostęp do źródła danych Troux OData i programu Troux w wersji 9.5.1 lub nowszej.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Zespół obsługi klienta może dostarczyć użytkownikowi unikatowy adres URL źródła danych Troux OData

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Jeśli po podaniu poświadczeń wystąpi błąd upływu limitu czasu, spróbuj ponownie nawiązać połączenie.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)
