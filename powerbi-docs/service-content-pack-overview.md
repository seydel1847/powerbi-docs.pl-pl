---
title: Omówienie programu pakietu zawartości usługi Power BI
description: Program certyfikacji pakietu zawartości
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/20/2018
ms.author: maggies
ms.openlocfilehash: c5c69bab7fb0a47e5e546dfe1b3143a13428d4bc
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54285236"
---
# <a name="overview-of-the-power-bi-service-content-pack-program"></a>Omówienie programu pakietu zawartości usługi Power BI
Pakiet zawartości to zbiór gotowej do użycia zawartości, która umożliwia użytkownikom natychmiastowy wgląd w szczegółowe informacje na podstawie źródła. Pakiet zawartości zazwyczaj skupia się na konkretnym scenariuszu biznesowym, zapewniając szczegółowe informacje o roli, domenie lub przepływie pracy.

Niezależni dostawcy oprogramowania mogą tworzyć szablonowe pakiety zawartości, dzięki którym klienci będą w stanie łączyć się i tworzyć wystąpienia przy użyciu własnych kont. Jako eksperci w danej dziedzinie mogą udostępniać dane w sposób umożliwiający ich łatwe wykorzystanie przez użytkowników biznesowych. Pakiety zawartości oferują klientom monitorowanie i analizowanie ad hoc, bez potrzeby realizowania znacznych inwestycji w infrastrukturę raportowania.

Te szablonowe pakiety zawartości tworzone przez niezależnych dostawców oprogramowania mogą być przesyłane do zespołu usługi Power BI w celu publicznego udostępnienia w galerii pakietów zawartości usługi Power BI (app.powerbi.com/getdata/services) oraz w witrynie Microsoft AppSource (appsource.microsoft.com). Przykład środowiska użytkownika publicznego pakietu zawartości można znaleźć [tutaj](template-content-pack-experience.md).

## <a name="overview"></a>Omówienie
Ogólny proces tworzenia i przesyłania szablonu pakietu zawartości obejmuje szereg kroków.

 ![Proces](media/service-content-pack-overview/developer-content-pack-overview.png)

1. [Zapoznaj się z wymaganiami](#requirements) i upewnij się, że zostały spełnione
2. [Utworzenie zawartości](template-content-pack-authoring.md#queries) w programie Power BI Desktop
3. [Utworzenie pulpitu nawigacyjnego](template-content-pack-authoring.md#dashboard) w usłudze PowerBI.com
4. [Przetestowanie pakietu zawartości](template-content-pack-testing.md) w organizacji
5. [Przesłanie](template-content-pack-testing.md#submission) zawartości do usługi Power BI w celu opublikowania

<a name="requirements"></a>

## <a name="requirements"></a>Wymagania
Aby utworzyć i przesłać pakiet zawartości do publikacji w usłudze Power BI i AppSource, musisz spełnić następujące wymagania:

* Masz aplikację SaaS używaną przez użytkowników biznesowych.
* Twoja aplikacja SaaS ma dane użytkowników, które można wizualizować w usłudze Power BI.
* Twoja aplikacja SaaS ma interfejs API, który jest dostępny za pośrednictwem publicznej sieci Internet. Optymalnie interfejs API powinien być interfejsem REST API lub źródłem danych OData. Pakiety zawartości usługi Power BI obsługują wiele typów uwierzytelniania, takich jak uwierzytelnianie podstawowe, OAuth 2.0 i klucz interfejsu API. 
* Twoja aplikacja SaaS została zatwierdzona do publikowania pakietu zawartości. Prześlij żądanie na adres pbiservicesapps@microsoft.com. Przeanalizujemy każde z nich pod kątem istotności i oczekiwanego użycia. 
* Podpisana umowa z partnerem. Tę czynność wykonuje się w [kroku przesyłania](template-content-pack-testing.md#submission).

Sprawdź sekcję dotyczącą [tworzenia](template-content-pack-authoring.md), aby uzyskać więcej szczegółowych informacji o wymaganiach technicznych.

## <a name="business-scenario"></a>Scenariusz biznesowy
Pakiety zawartości zapewniają szczegółowe informacje i metryki koncentrujące się na danym scenariuszu biznesowym. Zrozumienie odbiorców i korzyści, jakie mogą ze sobą nieść pakiety zawartości, pomoże w zagwarantowaniu, że dostarczona zawartość umożliwi użytkownikom osiągnięcie sukcesu.

### <a name="tips"></a>Porady
* Określ odbiorców i zadanie, które starają się wykonać.  
* Skup się na konkretnym okresie (ostatnie 90 dni) lub danej liczbie ostatnich wyników.  
* Importuj tylko tabele/kolumny powiązane z danym scenariuszem.  
* Weź pod uwagę zaoferowanie większej liczby pakietów zawartości w przypadku oddzielnych, unikatowych scenariuszy.  

## <a name="frequently-asked-questions"></a>Często zadawane pytania
**Czy mogę, jako inna firma, utworzyć pakiet zawartości usługi Power BI dla aplikacji SaaS, która nie jest moją własnością?**

Wymagamy podpisania umowy partnerskiej z właścicielem aplikacji SaaS przed opublikowaniem pakietu zawartości w usłudze. Jako inna firma ponosisz odpowiedzialność za zorganizowanie podpisania umowy partnerskiej z właścicielem aplikacji SaaS.

**Nie mam publicznego interfejsu API dewelopera dla mojej usługi. Czy nadal mogę utworzyć pakiet zawartości usługi Power BI, który pobiera dane bezpośrednio z magazynu danych?**

Nie, pakiety zawartości usługi Power BI wymagają interfejsu API dewelopera dostępnego za pośrednictwem publicznej sieci Internet.

**Jakiego rodzaju interfejsy API są obsługiwane przez pakiety zawartości usługi oraz z jakimi typami uwierzytelniania mogą współpracować?**

Pakiety zawartości usługi Power BI obsługują dowolne interfejsy API REST lub źródła danych OData. Usługa Power BI może współpracować z wieloma typami uwierzytelniania, w tym uwierzytelnianiem podstawowym, OAuth 2.0 i internetowym kluczem API. Więcej szczegółów dotyczących wymagań technicznych znajdziesz w artykule [Tworzenie](template-content-pack-authoring.md#dashboard).

**Mój pakiet zawartości został opublikowany w usłudze Power BI. Jak mogę go zaktualizować?**

Opublikowane pakiety zawartości można aktualizować raz w miesiącu. Żądania aktualizacji przesłane na adres [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com) przed ostatnim dniem bieżącego miesiąca zostaną opublikowane w pierwszym tygodniu następnego miesiąca.

**Mam więcej pytań dotyczących pakietów zawartości usługi. Jak mogę się skontaktować?**

Możesz napisać do nas wiadomość e-mail z pytaniami i wysłać ją pod adres [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com)

## <a name="support"></a>Pomoc techniczna
Pomoc podczas programowania można uzyskać pod adresem [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support). Incydenty klientów szybko znajdą swoją drogę do odpowiedniego zespołu.

## <a name="next-step"></a>Następny krok
[Tworzenie](template-content-pack-authoring.md)