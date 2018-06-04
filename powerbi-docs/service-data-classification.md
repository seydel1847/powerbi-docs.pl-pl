---
title: Klasyfikacja danych pulpitu nawigacyjnego
description: Poznaj więcej informacji o klasyfikacji danych pulpitu nawigacyjnego, w tym o sposobie konfigurowania klasyfikacji przez administratora oraz możliwości zmiany klasyfikacji przez właścicieli pulpitu nawigacyjnego.
author: amandacofsky
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: amac
LocalizationGroup: Dashboards
ms.openlocfilehash: f08e4199af06a4a7fd74cb525e918a67a27165a8
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34251327"
---
# <a name="dashboard-data-classification"></a>Klasyfikacja danych pulpitu nawigacyjnego
Każdy pulpit nawigacyjny jest inny. W zależności od źródła danych, z którym nawiązywane jest połączenie, prawdopodobnie zauważysz, że Twoi współpracownicy, którym udostępniasz pulpit nawigacyjny, będą musieli podjąć inne kroki niż Ty, w zależności od poufności danych. Niektóre pulpity nawigacyjne nigdy nie powinny być udostępniane osobom spoza firmy lub drukowane, podczas gdy inne można udostępniać swobodnie. Korzystając z klasyfikacji danych pulpitu nawigacyjnego, możesz zwiększyć świadomość osób przeglądających pulpity nawigacyjne w zakresie poziomu zabezpieczeń, który należy zastosować. Możesz oznaczyć pulpity nawigacyjne przy użyciu klasyfikacji zdefiniowanych przez dział IT w firmie, aby każda osoba wyświetlająca zawartość mogła uzyskać te same informacje o poufności danych.

![](media/service-data-classification/dashboard_tagged_as_hbi.png)

## <a name="data-classification-tags"></a>Tagi klasyfikacji danych
Tagi klasyfikacji danych są wyświetlane obok nazwy pulpitu nawigacyjnego, dzięki czemu każda osoba wyświetlająca pulpit uzyska informacje o poziomie zabezpieczeń, które należy zastosować wobec pulpitu nawigacyjnego i danych w nim zawartych.

![](media/service-data-classification/tag_next_to_title.png)

Tag będzie również wyświetlany obok tytułu pulpitu nawigacyjnego na liście Ulubione.

![](media/service-data-classification/tag_on_dashboard_tile.png)

Po najechaniu kursorem na tag zobaczysz pełną nazwę klasyfikacji.

![](media/service-data-classification/tag_tooltip.png)

Administratorzy mogą też ustawić adres URL dla tagu, aby zapewnić dodatkowe informacje.

> [!NOTE]
> W zależności od ustawień klasyfikacji wprowadzonych przez administratora niektóre typy klasyfikacji mogą nie być wyświetlane jako tag na pulpicie nawigacyjnym. Jeśli jesteś właścicielem pulpitu nawigacyjnego, zawsze możesz sprawdzić typ klasyfikacji pulpitu nawigacyjnego w ustawieniach pulpitu nawigacyjnego.
> 
> 

## <a name="setting-a-dashboards-classification"></a>Ustawianie klasyfikacji pulpitu nawigacyjnego
Jeśli klasyfikacja danych jest włączona w firmie, wszystkie pulpity nawigacyjne zaczynają z domyślnym typem klasyfikacji, ale właściciel pulpitu nawigacyjnego może zmienić klasyfikację, aby dopasować poziom zabezpieczeń.

Aby zmienić klasyfikację, wykonaj następujące czynności.

1. Przejdź do ustawień pulpitu nawigacyjnego, wybierając **wielokropek** obok nazwy pulpitu nawigacyjnego, a następnie wybierz opcję **Ustawienia**.
   
    ![](media/service-data-classification/dashboard_settings.png)
2. W obszarze Ustawienia pulpitu nawigacyjnego możesz zobaczyć bieżącą klasyfikację pulpitu nawigacyjnego i użyć menu rozwijanego, aby zmienić typ klasyfikacji.
   
    ![](media/service-data-classification/classification_setting_dropdown.png)
3. Po zakończeniu wybierz opcję **Zastosuj**.

Po zastosowaniu zmiany każda osoba, której udostępniono pulpit nawigacyjny, zobaczy aktualizację podczas kolejnego ponownego załadowania pulpitu.

## <a name="working-with-data-classification-tags-as-an-admin"></a>Praca z tagami klasyfikacji danych na poziomie administratora
Klasyfikacja danych jest ustawiana przez administratora globalnego w organizacji. Aby włączyć klasyfikację danych, wykonaj następujące czynności.

1. Wybierz koło zębate Ustawienia i wybierz opcję **Portal administracyjny**.
   
    ![](media/service-data-classification/admin_portal_in_settings.png)
2. Przełącz opcję **Klasyfikacja danych dla pulpitów nawigacyjnych i raportów** na wartość *Wł.* na karcie **Ustawienia dzierżawy**.
   
    ![](media/service-data-classification/data_classification_switch_location.png)

Po włączeniu opcji zobaczysz formularz umożliwiający utworzenie różnych klasyfikacji w organizacji.

![](media/service-data-classification/blank_classification_form.png)

Każda klasyfikacja ma **nazwę** i **nazwę skróconą**, która będzie wyświetlana na pulpicie nawigacyjnym. Dla każdej klasyfikacji możesz zdecydować, czy tag z nazwą skróconą będzie wyświetlany na pulpicie nawigacyjnym, wybierając opcję **Pokaż tag**. Jeśli zdecydujesz, żeby nie pokazywać typu klasyfikacji na pulpicie nawigacyjnym, właściciel nadal będzie w stanie wyświetlić typ, sprawdzając ustawienia pulpitu nawigacyjnego. Ponadto możesz opcjonalnie dodać **adres URL**, który zawiera więcej informacji o wytycznych dotyczących klasyfikacji oraz wymaganiach użytkowania w organizacji.  

Ostatni krok to podjęcie decyzji o tym, która klasyfikacja będzie klasyfikacją domyślną.  

Po wypełnieniu formularza z typami klasyfikacji wybierz opcję **Zastosuj**, aby zapisać ustawienia.

![](media/service-data-classification/filled_in_classification_form.png)

W tym momencie wszystkie pulpity nawigacyjne otrzymają klasyfikację domyślną, a właściciele pulpitów nawigacyjnych będą w stanie zaktualizować typ klasyfikacji do typu odpowiedniego dla zawartości. Możesz wrócić tutaj później, aby dodać lub usunąć typy klasyfikacji bądź zmienić domyślny typ klasyfikacji.  

> [!NOTE]
> Jest kilka ważnych rzeczy do zapamiętania na wypadek powrotu w celu wprowadzenia zmian:
> 
> * Jeśli wyłączysz klasyfikację danych, żadne tagi nie zostaną zapamiętane. Ponowne włączenie opcji będzie wymagało rozpoczęcia całej procedury od początku.  
> * Jeśli usuniesz typ klasyfikacji, wszystkie pulpity nawigacyjne przypisane do usuniętego typu klasyfikacji powrócą do domyślnego typu klasyfikacji do momentu ponownego ustawienia typu przez właściciela.  
> * Jeśli zmienisz domyślny typ klasyfikacji, wszystkie pulpity nawigacyjne, które nie miały jeszcze przypisanego typu klasyfikacji przez właściciela zostaną przypisane do nowego typu domyślnego.
> 
> 

