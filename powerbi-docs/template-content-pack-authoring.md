---
title: Tworzenie szablonowych pakietów zawartości w usłudze Power BI
description: Tworzenie szablonowych pakietów zawartości
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maggies
ms.openlocfilehash: 8b7c46ad1e9ea9c4c79a8f5a1b48c73ab3336306
ms.sourcegitcommit: 3a287ae4ab16d1e76caed651bd8ae1a1738831cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39157574"
---
# <a name="author-template-content-packs-in-power-bi"></a>Tworzenie szablonowych pakietów zawartości w usłudze Power BI
Tworzenie szablonowego pakietu zawartości używa programu Power BI Desktop oraz witryny PowerBI.com. Dostępne są cztery składniki pakietu zawartości:

* Zapytania umożliwiają [łączenie](desktop-connect-to-data.md) z danymi i [przekształcanie](desktop-query-overview.md) ich, jak również definiowanie [parametrów](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/)  
* Model danych do tworzenia [relacji](desktop-create-and-manage-relationships.md), [miar](desktop-measures.md) i ulepszeń funkcji pytań i odpowiedzi  
* [Strony](desktop-report-view.md) raportu obejmują wizualizacje i filtry zapewniające wgląd w dane  
* [Pulpit nawigacyjny](service-dashboards.md) i [kafelki](service-dashboard-create.md) oferują przegląd uwzględnionych szczegółowych danych  

Możesz znać każdy element jako istniejące funkcje usługi Power BI. Podczas tworzenia pakietu zawartości istnieją dodatkowe kwestie, które należy wziąć pod uwagę dla każdego aspektu (zobacz poszczególne sekcje poniżej, aby uzyskać więcej szczegółowych informacji).

<a name="queries"></a>

## <a name="queries"></a>Zapytania
Dla szablonowych pakietów zawartości zapytania opracowane w programie Power BI Desktop są używane do połączenia ze źródłem danych i importowania danych. Te zapytania są wymagane do zwrócenia spójnego schematu i są obsługiwane w przypadku zaplanowanego odświeżania danych (zapytania bezpośrednie nie są obsługiwane).

Szablonowe pakiety zawartości obsługują tylko jedno źródło danych na pakiet zawartości, więc musisz ostrożnie definiować swoje zapytania. Pojedyncze źródło danych jest zdefiniowane jako źródło, które wymaga tego samego uwierzytelniania. Możesz wykonać wiele wywołań interfejsu API w różnych zapytaniach, jeśli wszystkie wywołania dotyczą tego samego punktu końcowego interfejsu API i używają tego samego uwierzytelniania. Pakiety zawartości usługi Power BI nie obsługują wielu źródeł, jeśli wymagają różnego uwierzytelniania.

### <a name="connect-to-your-api"></a>Łączenie z interfejsem API
Aby rozpocząć pracę, musisz nawiązać połączenie z interfejsem API z programu Power BI Desktop, aby rozpocząć tworzenie zapytań.

W celu nawiązania połączenia z interfejsem API Możesz użyć łączników danych dostępnych fabrycznie w programie Power BI Desktop. Możesz użyć internetowego łącznika danych (Pobierz dane -> Internet) do nawiązania połączenia z interfejsem API Rest lub łącznika usługi OData (Pobierz dane -> Źródło danych OData), aby nawiązać połączenie ze źródłem danych OData. Należy pamiętać, że te łączniki będą fabrycznie działać tylko wtedy, gdy interfejs API obsługuje uwierzytelnianie podstawowe.

> [!NOTE]
> Jeśli Twój interfejs API korzysta z innych typów uwierzytelniania, takich jak OAuth 2.0 lub klucz internetowego interfejsu API, wówczas należy opracować własny łącznik danych umożliwiający programowi Power BI Desktop pomyślne łączenie się i uwierzytelnianie w interfejsie API. Aby uzyskać szczegółowe informacje na temat tworzenia własnego łącznika danych dla swojego pakietu zawartości, zapoznaj się z dokumentacją łączników danych [tutaj](https://aka.ms/DataConnectors). 
>
>

### <a name="consider-the-source"></a>Uwzględnianie źródła
Zapytania definiują dane, które zostaną uwzględnione w modelu danych. W zależności od rozmiaru systemu te zapytania powinny również obejmować filtry, aby upewnić się, że klienci mają do czynienia z rozmiarem, którym można zarządzać i który pasuje do danego scenariusza biznesowego.

Pakiety zawartości usługi Power BI mogą wykonywać wiele zapytań równolegle i jednocześnie dla wielu użytkowników.  Planuj z wyprzedzeniem strategię ograniczania przepustowości i współbieżności oraz zapytaj nas, jak spowodować, żeby pakiet zawartości był odporny na błędy.

### <a name="schema-enforcement"></a>Egzekwowanie schematu
Upewnij się, że Twoje zapytania są odporne na zmiany w systemie, zmiany w schemacie podczas odświeżania mogą uszkodzić model. Jeśli źródło może zwrócić wynik null/brak wyniku schematu dla niektórych zapytań, należy wziąć pod uwagę zwracanie pustej tabeli lub zgłaszanie błędu niestandardowego, który jest zrozumiały dla użytkownika.

### <a name="parameters"></a>Parametry
[Parametry](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) w programie Power BI Desktop umożliwiają użytkownikom podawanie wartości wejściowych, które dostosowują dane pobrane przez użytkownika. Zawczasu pomyśl o parametrach, aby uniknąć przeróbek po zainwestowaniu czasu w kompilowanie szczegółowych zapytań lub raportów.

> [!NOTE]
> Szablonowe pakiety zawartości obecnie obsługują tylko parametry tekstowe. Innych typów parametrów można używać podczas tworzenia, ale podczas [testowania](template-content-pack-testing.md#templates) wszystkie wartości podane przez użytkowników będą literałami.
>
>

### <a name="additional-query-tips"></a>Dodatkowe porady dotyczące zapytań

* Upewnij się, że wszystkie kolumny są odpowiednio wpisywane
* Kolumny mają nazwy informacyjne (zobacz sekcję pytań i odpowiedzi)  
* W przypadku logiki udostępnionej należy rozważyć użycie funkcji lub zapytań  
* Poziomy prywatności nie są obecnie obsługiwane w usłudze — jeśli zostanie wyświetlony monit o poziomy prywatności, konieczne może być ponownie napisanie zapytania, aby użyć ścieżek względnych  

## <a name="data-model"></a>Model danych

Dobrze zdefiniowany model danych gwarantuje, że klienci mogą łatwo i intuicyjnie wchodzić w interakcje z pakietem zawartości. Utwórz model danych w programie Power BI Desktop.

> [!NOTE]
> Większość podstawowego modelowania (pisownia, nazwy kolumn) ma się odbywać w [zapytaniach](#queries).
>
>

### <a name="qa"></a>Pytania i odpowiedzi
Modelowanie wpłynie również na to, jak dobrze funkcja pytań i odpowiedzi zapewnia wyniki klientom. Upewnij się, że dodano synonimy do często używanych kolumn i że kolumny mają poprawne nazwy w [zapytaniach](#queries).

### <a name="additional-data-model-tips"></a>Dodatkowe porady dotyczące modelu danych
* Wszystkie kolumny wartości zostały sformatowane
    >[!NOTE]
    >W zapytaniu powinny być stosowane typy.  
* Wszystkie miary zostały sformatowane  
* Ustawiono domyślne podsumowanie. Szczególnie opcja „Nie sumuj”, jeśli jest to wymagane (na przykład dla unikatowych wartości)  
* Kategoria danych została ustawiona, jeśli ma to zastosowanie  
* Relacje zostały ustawione (w razie potrzeby)  

## <a name="reports"></a>Raporty
Strony raportu zapewniają dodatkowy wgląd w dane zawarte w pakiecie zawartości. Użyj stron raportów, aby odpowiedzieć na kluczowe pytania biznesowe, które próbuje rozwiązać pakiet zawartości. Utwórz raport za pomocą programu Power BI Desktop.

> [!NOTE]
> Tylko jeden raport może zostać dołączony do pakietu zawartości, wykorzystaj zalety różnych stron w celu wyróżnienia określonych sekcji scenariusza.
>
>

### <a name="additional-report-tips"></a>Dodatkowe porady dotyczące raportów
* Do filtrowania krzyżowego użyj więcej niż jednej wizualizacji na stronie  
* Dokładnie dopasuj wizualizacje (bez nakładania się)  
* Układ strony jest ustawiony w trybie układu „4:3” lub „16:9”  
* Wszystkie przedstawione agregacje mają sens liczbowy (średnie, unikatowe wartości)  
* Fragmentowanie daje wymierne wyniki  
* Logo znajduje się co najmniej na górze raportu  
* Elementy są na schemacie kolorów klienta w najszerszym możliwym zakresie  

<a name="dashboard"></a>

## <a name="dashboard"></a>Pulpit nawigacyjny
Pulpit nawigacyjny jest głównym punktem interakcji z pakietem zawartości dla klientów. Powinien on zawierać przegląd dołączonej zawartości, szczególnie ważnych metryk dla danego scenariusza biznesowego.

Aby utworzyć pulpit nawigacyjny dla szablonowego pakietu zawartości, wystarczy przekazać swój plik PBIX za pośrednictwem pozycji Pobierz dane > Pliki lub opublikować bezpośrednio z programu Power BI Desktop.

> [!NOTE]
> Szablonowe pakiety zawartości aktualnie wymagają jednego raportu i zestawu danych na pakiet zawartości. Nie należy przypinać zawartości z wielu raportów/zestawów danych na pulpicie nawigacyjnym używanym w pakiecie zawartości.
>
>

### <a name="additional-dashboard-tips"></a>Dodatkowe porady dotyczące pulpitu nawigacyjnego
* Utrzymuj ten sam motyw podczas przypinania tak, aby kafelki na pulpicie nawigacyjnym były spójne  
* Przypnij logo do motywu, aby konsumenci wiedzieli, skąd pochodzi pakiet  
* Sugerowany układ do pracy z większością rozdzielczości ekranu ma szerokość 5–6-małych kafelków  
* Wszystkie kafelki pulpitu nawigacyjnego powinny mieć odpowiednie tytuły/podtytuły  
* Rozważ grupowania na pulpicie nawigacyjnym dla różnych scenariuszy w pionie albo poziomie  

<a name="restrictions"></a>

## <a name="summary-of-restrictions"></a>Podsumowanie ograniczeń
Zgodnie z tym, co zostało wymienione w powyższej sekcjach, obecnie szablonowe pakiety zawartości mają zestaw ograniczeń:  

| Obsługiwane | *Nieobsługiwane* |
| --- | --- |
| Zestawy danych wbudowane w pulpit usługi PBI |*Zestawy danych z innych pakietów zawartości lub danych wejściowych, takich jak pliki programu Excel* |
| Źródło danych obsługiwane w chmurze dla zaplanowanego odświeżania danych |*Bezpośrednie zapytanie lub lokalna łączność nie są obsługiwane.* |
| Zapytania zwracające spójne schematy lub błędy, gdzie jest to odpowiednie |*Schematy dynamiczne lub niestandardowe* |
| Jedno źródło danych dla zestawu danych |*Wiele źródeł danych, takich jak zestawy połączone lub adresy URL, które zostały wykryte jako wiele źródeł danych* |
| Parametry typu tekst |*Inne typy parametrów (takie jak data) lub „Lista dozwolonych wartości”* |
| Jeden pulpit nawigacyjny, raport i zestaw danych |*Wiele pulpitów nawigacyjnych, raportów i zestawów danych* |

## <a name="next-step"></a>Następny krok
[Testowanie i przesyłanie pakietu zawartości](template-content-pack-testing.md)