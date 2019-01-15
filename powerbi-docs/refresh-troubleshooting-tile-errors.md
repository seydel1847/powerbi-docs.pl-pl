---
title: Rozwiązywanie problemów z błędami kafelków
description: Typowe błędy występujące podczas odświeżania kafelka w usłudze Power BI
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: bc53bdf6c0fd013d446c6d74cf2a422a84302f6a
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54289790"
---
# <a name="troubleshooting-tile-errors"></a>Rozwiązywanie problemów z błędami kafelków
Poniżej przedstawiono typowe błędy kafelków wraz z wyjaśnieniem.

> [!NOTE]
> Jeśli wystąpi błąd powodujący problemy, którego nie wymieniono poniżej, możesz uzyskać dodatkową pomoc w [witrynie społeczności](http://community.powerbi.com/) albo utworzyć [bilet pomocy technicznej](https://powerbi.microsoft.com/support/).
> 
> 

## <a name="errors"></a>Błędy
**Usługa Power BI napotkała nieoczekiwany błąd podczas ładowania modelu. Spróbuj ponownie później.**
lub **Nie można pobrać modelu danych. Skontaktuj się z właścicielem pulpitu nawigacyjnego, aby upewnić się, że źródła danych oraz model istnieją i są dostępne.**

Nie udało się uzyskać dostępu do danych, ponieważ źródło danych nie jest dostępne. Być może źródło danych zostało usunięte lub przeniesione albo zmieniono jego nazwę. Ten błąd może również wystąpić, jeśli źródło danych jest w trybie offline lub zostały zmienione uprawnienia. Sprawdź, czy źródło nadal znajduje się we wskazanej lokalizacji oraz czy wciąż masz uprawnienia dostępu do niego. Inną przyczyną tego problemu może być opóźnienie źródła. Spróbuj ponownie później, gdy obciążenie źródła zmniejszy się. Jeśli jest to źródło lokalne, być może jego właściciel udzieli dodatkowych informacji.

**Nie masz uprawnień do wyświetlania tego kafelka lub otwierania skoroszytu.**

Skontaktuj się z właścicielem pulpitu nawigacyjnego, aby upewnić się, że źródła danych oraz model istnieją i są dostępne dla Twojego konta.

**Kształty danych muszą zawierać co najmniej jedną grupę lub co najmniej jedno obliczenie z danymi wyjściowymi. Skontaktuj się z właścicielem pulpitu nawigacyjnego.**

Nie ma żadnych danych do wyświetlenia, ponieważ zapytanie jest puste. Dodaj wybrane pola z listy pól do wizualizacji i przypnij ją ponownie.

**Nie można wyświetlić danych, ponieważ usługa Power BI nie może określić relacji między co najmniej dwoma polami.**

Próbujesz użyć co najmniej dwóch niepowiązanych pól z tabel. Musisz usunąć niepowiązane pola z wizualizacji, a następnie utworzyć relację między tabelami. Gdy to zrobisz, możesz ponownie dodać pola do wizualizacji. Możesz to zrobić za pomocą programu Power BI Desktop lub dodatku PowerPivot dla programu Excel. [Dowiedz się więcej](desktop-create-and-manage-relationships.md)

**Grupy na osi podstawowej i osi dodatkowej nakładają się na siebie. Grupy na osi podstawowej nie mogą mieć tych samych kluczy co grupy na osi dodatkowej.**

Zazwyczaj jest to problem przejściowy. Najczęściej występuje podczas przenoszenia grup z wierszy do kolumn. W takim przypadku błąd powinien zniknąć po zakończeniu przenoszenia wszystkich grup. Jeśli komunikat będzie się powtarzać, spróbuj zamienić pola między wierszami i kolumnami lub zmienić legendę osi albo usunąć pola z wizualizacji.  

**Wizualizacja przekroczyła dostępną ilość zasobów. Spróbuj użyć filtru, aby zmniejszyć ilość wyświetlanych danych.**

Wizualizacja próbuje wykonać zapytanie względem zbyt dużej ilości danych, co uniemożliwia przedstawienie wyników za pomocą dostępnych zasobów. Spróbuj przefiltrować wizualizację, aby zmniejszyć ilość wynikowych danych.

**Nie można rozpoznać następujących pól: {0}. Zaktualizuj wizualizację przy użyciu pól, które istnieją w zestawie danych.**

Prawdopodobnie pole zostało usunięte lub zmieniono jego nazwę. Możesz usunąć uszkodzone pole z wizualizacji, dodać inne pole i przypiąć je ponownie.

**Nie można pobrać danych tej wizualizacji. Spróbuj ponownie później.**

Zazwyczaj jest to problem przejściowy. Jeśli komunikat będzie się powtarzać, skontaktuj się z pomocą techniczną.

## <a name="contact-support"></a>Kontakt z pomocą techniczną
W przypadku uporczywych problemów [skontaktuj się z pomocą techniczną](https://support.powerbi.com), aby umożliwić wnikliwe zbadanie ich przyczyn.

## <a name="next-steps"></a>Następne kroki
[Rozwiązywanie problemów z lokalną bramą danych](service-gateway-onprem-tshoot.md)  
[Rozwiązywanie problemów z bramą Power BI Gateway – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

