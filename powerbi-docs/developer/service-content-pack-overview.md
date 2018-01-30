---
title: "Omówienie programu pakietu zawartości usługi Power BI"
description: "Program certyfikacji pakietu zawartości"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/04/2018
ms.author: maghan
ms.openlocfilehash: 1eaa549bf42c17cd2bd857efd4d50b991e862ea0
ms.sourcegitcommit: 25489cf87c31fc107a5337fa1dd36506897c4bbb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/05/2018
---
# <a name="overview-of-the-power-bi-service-content-pack-program"></a>Omówienie programu pakietu zawartości usługi Power BI
Pakiet zawartości to zbiór gotowej do użycia zawartości, która umożliwia użytkownikom natychmiastowy wgląd w szczegółowe informacje na podstawie źródła. Pakiet zawartości zazwyczaj skupia się na konkretnym scenariuszu biznesowym, zapewniając szczegółowe informacje o roli, domenie lub przepływie pracy.

Niezależni dostawcy oprogramowania mogą tworzyć szablonowe pakiety zawartości, dzięki którym klienci będą w stanie łączyć się i tworzyć wystąpienia przy użyciu własnych kont. Jako eksperci domeny mogą odblokować dane w sposób, który będzie łatwy do wykorzystania przez użytkowników biznesowych. Pakiety zawartości oferują klientom monitorowanie i analizowanie ad hoc, bez potrzeby realizowania znacznych inwestycji w infrastrukturę raportowania. 

Te szablonowe pakiety zawartości tworzone przez niezależnych dostawców oprogramowania mogą być przesyłane do zespołu usługi Power BI w celu publicznego udostępnienia w galerii pakietów zawartości usługi Power BI (app.powerbi.com/getdata/services) oraz w witrynie Microsoft AppSource (appsource.microsoft.com). Przykład środowiska użytkownika publicznego pakietu zawartości można znaleźć [tutaj](template-content-pack-experience.md).

## <a name="overview"></a>Omówienie
Ogólny proces rozwoju i przesyłania szablonowego pakietu zawartości obejmuje wiele kroków.

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
* Twoja aplikacja SaaS ma interfejs API, który jest dostępny za pośrednictwem publicznej sieci Internet. Idealnie interfejs API jest interfejsem REST API lub źródłem danych OData. Pakiety zawartości usługi Power BI obsługują wiele typów uwierzytelniania, takich jak uwierzytelnianie podstawowe, OAuth 2.0 i klucz interfejsu API. 
* Twoja aplikacja SaaS została zatwierdzona do publikowania pakietu zawartości. Prześlij żądanie na adres pbiservicesapps@microsoft.com. Przeanalizujemy każde z nich pod kątem istotności i oczekiwanego użycia. 
* Podpisana umowa z partnerem. Tę czynność wykonuje się w [kroku przesyłania](template-content-pack-testing.md#submission).

Sprawdź sekcję [tworzenia](template-content-pack-authoring.md), aby uzyskać więcej szczegółów o wymaganiach technicznych.

## <a name="business-scenario"></a>Scenariusz biznesowy
Pakiety zawartości zapewniają szczegółowe informacje i metryki koncentrujące się na danym scenariuszu biznesowym. Zrozumienie odbiorców i korzyści, jakie mogą ze sobą nieść pakiety zawartości, pomoże w zagwarantowaniu, że dostarczona zawartość umożliwi użytkownikom osiągnięcie sukcesu.

### <a name="tips"></a>Porady
* Określ odbiorców i zadanie, które starają się wykonać.  
* Skup się na konkretnym okresie (ostatnie 90 dni) lub danej liczbie ostatnich wyników.  
* Importuj tylko tabele/kolumny powiązane z danym scenariuszem.  
* Weź pod uwagę zaoferowanie większej liczby pakietów zawartości w przypadku oddzielnych, unikatowych scenariuszy.  

## <a name="frequently-asked-questions"></a>Często zadawane pytania
**Czy mogę utworzyć pakiet zawartości usługi Power BI dla aplikacji SaaS innej firmy, która nie jest moją własnością?**

Nie, obecnie wymagamy podpisania umowy partnerskiej z właścicielem aplikacji SaaS przed opublikowaniem pakietu zawartości w usłudze.

**Nie mam publicznego interfejsu API dewelopera dla mojej usługi. Czy nadal mogę utworzyć pakiet zawartości usługi Power BI, który pobiera dane bezpośrednio z magazynu danych?**

Nie, pakiety zawartości usługi Power BI wymagają interfejsu API dewelopera dostępnego za pośrednictwem publicznej sieci Internet.

**Jakiego rodzaju interfejsy API są obsługiwane przez pakiety zawartości usługi oraz z jakimi typami uwierzytelniania mogą współpracować?**

Pakiety zawartości usługi Power BI obsługują dowolne interfejsy API REST lub źródła danych OData. Usługa Power BI może współpracować z wieloma typami uwierzytelniania, w tym uwierzytelnianiem podstawowym, OAuth 2.0 i internetowym kluczem API. Więcej szczegółów dotyczących wymagań technicznych znajdziesz w artykule [Tworzenie](template-content-pack-authoring.md#dashboard).

**Mam więcej pytań dotyczących pakietów zawartości usługi. Jak mogę się skontaktować?**

Możesz napisać do nas wiadomość e-mail z pytaniami i wysłać ją pod adres pbiservicesapps@microsoft.com

## <a name="support"></a>Pomoc techniczna
Aby uzyskać pomoc techniczną podczas tworzenia, skorzystaj ze strony [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support). Jest ona aktywnie monitorowana i zarządzana. Incydenty klientów szybko znajdą swoją drogę do odpowiedniego zespołu.

## <a name="next-step"></a>Następny krok
[Tworzenie](template-content-pack-authoring.md)
