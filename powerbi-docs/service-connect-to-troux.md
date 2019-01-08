---
title: Łączenie się z pakietem zawartości Troux przy użyciu usługi Power BI
description: Pakiet zawartości Troux dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 9152538204089ed9c75b69b79a08dc7496a8cca9
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007711"
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
6. Po zatwierdzeniu proces importowania rozpocznie się automatycznie. Po zakończeniu nowy pulpit nawigacyjny, raport i model zostaną wyświetlone w okienku nawigacji. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.
   
     ![](media/service-connect-to-troux/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

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

