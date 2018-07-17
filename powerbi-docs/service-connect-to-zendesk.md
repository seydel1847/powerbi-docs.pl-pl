---
title: Nawiązywanie połączenia z systemem Zendesk przy użyciu usługi Power BI
description: System Zendesk dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: afcaae9499aa1c7e1461030cfa6b5d7b35a47188
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37136024"
---
# <a name="connect-to-zendesk-with-power-bi"></a>Nawiązywanie połączenia z systemem Zendesk przy użyciu usługi Power BI
Pakiet zawartości Zendesk oferuje pulpit nawigacyjny usługi Power BI oraz zestaw raportów usługi Power BI zapewniających wgląd w informacje dotyczące liczby biletów i wydajności agentów. Możesz użyć dostarczonego pulpitu nawigacyjnego i raportów lub dostosować je, aby podkreślić najważniejsze informacje.  Dane będą odświeżane automatycznie raz dziennie. 

Połącz się z [pakietem zawartości Zendesk](https://app.powerbi.com/getdata/services/zendesk) lub dowiedz się więcej na temat [integracji systemu Zendesk](https://powerbi.microsoft.com/integrations/zendesk) z usługą Power BI.

>[!NOTE]
>Aby nawiązać połączenie, wymagane jest konto administratora systemu Zendesk. Więcej szczegółowych informacji na temat [wymagań](#Requirements) znajduje się poniżej.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.
   
   ![](media/service-connect-to-zendesk/pbi_getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.
   
   ![](media/service-connect-to-zendesk/pbi_getservices.png) 
3. Wybierz pozycję **Zendesk** \> **Pobierz**.
   
   ![](media/service-connect-to-zendesk/zendesk.png)
4. Podaj adres URL skojarzony z kontem. Ma on postać **https://company.zendesk.com**. Szczegółowe informacje dotyczące [znajdowania tych parametrów](#FindingParams) zostały podane poniżej.
   
   ![](media/service-connect-to-zendesk/pbi_zendeskconnect.png)
5. Po wyświetleniu monitu wprowadź poświadczenia systemu Zendesk.  Wybierz opcję **oAuth 2** jako mechanizm uwierzytelniania i kliknij przycisk **Zaloguj**. Postępuj zgodnie z przepływem uwierzytelniania systemu Zendesk. (Jeśli już wcześniej zalogowano się w systemie Zendesk w przeglądarce, monit o poświadczenia może nie zostać wyświetlony).
   
   > [!NOTE]
   > Ten pakiet zawartości wymaga połączenia z kontem administratora systemu Zendesk. 
   > 
   > 
   
   ![](media/service-connect-to-zendesk/pbi_zendesksignin.png)
6. Kliknij opcję **Zezwalaj**, aby umożliwić usłudze Power BI uzyskiwanie dostępu do danych z systemu Zendesk.
   
   ![](media/service-connect-to-zendesk/zendesk2.jpg)
7. Kliknij przycisk **Połącz**, aby rozpocząć proces importowania. Po zaimportowaniu danych przez usługę Power BI zobaczysz nowy pulpit nawigacyjny, raport i zestaw danych w okienku nawigacji po lewej stronie. Nowe elementy są oznaczone żółtą gwiazdką \*.
   
   ![](media/service-connect-to-zendesk/pbi_zendeskdash.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](power-bi-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](service-dashboard-tiles.md), aby otworzyć raport źródłowy.
* Zestaw danych zostanie ustawiony na codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub spróbować odświeżyć go na żądanie przy użyciu opcji **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Pakiet zawartości Power BI obejmuje dane dotyczące następujących elementów:  

* Użytkownicy (użytkownicy końcowi i agenci)  
* Organizacje  
* Grupy  
* Bilety  

Istnieje również zestaw miar, które zostały obliczone, np. Średni czas oczekiwania oraz Bilety rozwiązane w ciągu ostatnich 7 dni. Pełna lista jest dołączona do pakietu zawartości.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Wymagania systemowe
W celu uzyskania dostępu do pakietu zawartości Zendesk wymagane jest konto administratora systemu Zendesk. Jeśli jesteś agentem lub użytkownikiem końcowym zainteresowanym wyświetleniem danych systemu Zendesk, dodaj sugestię i sprawdź łącznik Zendesk w programie [Power BI Desktop](desktop-connect-to-data.md).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Adres URL systemu Zendesk będzie taki sam, jak adres URL, którego używasz do logowania się do konta Zendesk. Jeśli nie masz pewności co do adresu URL systemu Zendesk, możesz skorzystać z [pomocy logowania](https://www.zendesk.com/login/) w systemie Zendesk.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Jeśli masz problemy z nawiązaniem połączenia, sprawdź adres URL systemu Zendesk i upewnij się, że korzystasz z konta administratora systemu Zendesk.

## <a name="next-steps"></a>Następne kroki
* [Co to jest usługa Power BI?](power-bi-overview.md)
* [Pobieranie danych](service-get-data.md)

