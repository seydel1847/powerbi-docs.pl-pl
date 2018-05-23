---
title: Nawiązywanie połączenia z systemem Acumatica przy użyciu usługi Power BI
description: Acumatica dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: ea5ce2e1e635149c91fbcf38d84e3093af7915c9
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="connect-to-acumatica-with-power-bi"></a>Nawiązywanie połączenia z systemem Acumatica przy użyciu usługi Power BI
Pakiet zawartości Acumatica dla usługi Power BI umożliwia zyskanie szybkiego wglądu w dane zapewniające możliwości. Usługa Power BI pobiera dane, w tym możliwości, konta i klientów, a następnie tworzy domyślny pulpit nawigacyjny i powiązane raporty w oparciu o te dane.

Połącz się z [pakietem zawartości Acumatica](https://app.powerbi.com/getdata/services/acumatica) lub przeczytaj więcej na temat [integracji systemu Acumatica](https://powerbi.microsoft.com/integrations/acumatica) z usługą Power BI.

>[!NOTE]
>Ten pakiet zawartości wymaga systemu Acumatica w wersji 5.2 lub nowszej.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-acumatica/getdata3.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-acumatica/getdata2.png)
3. Wybierz pozycję **Acumatica** \> **Pobierz**.
   
   ![](media/service-connect-to-acumatica/acumatica.png)
4. Wprowadź punkt końcowy Acumatica OData. Punkt końcowy OData pozwala zewnętrznemu systemowi na wysyłanie żądań dotyczących danych z systemu Acumatica. Punkt końcowy Acumatica OData jest sformatowany w następujący sposób i powinien używać protokołu HTTPS:
   
     https://[domena_witryny]/odata/[nazwa_firmy]
   
   Nazwa firmy jest wymagana tylko wtedy, gdy korzystasz z wdrożenia obejmującego wiele firm. Więcej informacji na temat odnajdywania tego parametru na koncie Acumatica znajduje się poniżej.
   
   ![](media/service-connect-to-acumatica/parameters.png)
5. Jako metodę uwierzytelniania wybierz opcję **Podstawowa**. Wprowadź nazwę użytkownika i hasło konta Acumatica, a następnie kliknij opcję **Zaloguj**.
   
    ![](media/service-connect-to-acumatica/creds2.png)
6. Po zaimportowaniu danych przez usługę Power BI zobaczysz nowy pulpit nawigacyjny, raport i zestaw danych w okienku nawigacji po lewej stronie. Nowe elementy są oznaczone żółtą gwiazdką \*, która zniknie po wybraniu. Wybranie pulpitu nawigacyjnego spowoduje wyświetlenie układu podobnego do przedstawionego poniżej:
   
    ![](media/service-connect-to-acumatica/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="system-requirements"></a>Wymagania systemowe
Ten pakiet zawartości wymaga systemu Acumatica w wersji 5.2 lub nowszej. Potwierdź wersję u administratora systemu Acumatica.

## <a name="finding-parameters"></a>Znajdowanie parametrów
**Punkt końcowy Acumatica OData**

Punkt końcowy Acumatica OData jest sformatowany w następujący sposób i powinien używać protokołu HTTPS:

    https://[sitedomain]/odata/[companyname]

Domenę witryny aplikacji można znaleźć na pasku adresu przeglądarki po zalogowaniu się do systemu Acumatica. W poniższym przykładzie domeną witryny jest „https://pbi.acumatica.com”, więc punkt końcowy OData, który należy podać, wygląda następująco: „https://pbi.acumatica.com/odata”.

 ![](media/service-connect-to-acumatica/url.png)

Nazwa firmy jest wymagana tylko wtedy, gdy korzystasz z wdrożenia obejmującego wiele firm. Możesz znaleźć te informacje na stronie logowania w systemie Acumatica.

![](media/service-connect-to-acumatica/signin2.png)

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Jeśli nie możesz się zalogować, upewnij się, że podany punkt końcowy Acumatica OData jest prawidłowo sformatowany.

    https://<application site domain>/odata/<company name>

Jeśli masz problemy z nawiązaniem połączenia, skontaktuj się z administratorem, aby sprawdzić wersję systemu Acumatica. Ten pakiet zawartości wymaga wersji 5.2 lub nowszej.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)

