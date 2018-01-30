---
title: "Informacje o wersji serwera raportów usługi Power BI"
description: "Interfejs API REST zapewnia programowy dostęp do obiektów w katalogu serwera raportów usługi Power BI."
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: ede77374fab911ed77a993cc705b8caa00e48bf0
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/06/2018
---
# <a name="develop-with-the-rest-apis-for-power-bi-report-server"></a>Tworzenie dla serwera raportów usługi Power BI przy użyciu interfejsów API REST
Serwer raportów usługi Power BI obsługuje interfejsy API REST (Representational State Transfer). Interfejsy API REST to punkty końcowe usług obsługujące zestaw operacji HTTP (metod), które umożliwiają tworzenie, pobieranie, aktualizowanie i usuwanie zasobów na serwerze raportów.

Interfejs API REST zapewnia programowy dostęp do obiektów w katalogu serwera raportów usługi Power BI. Przykładami takich obiektów są foldery, raporty, wskaźniki KPI, źródła danych, zestawy danych, plany odświeżania lub subskrypcje. Przy użyciu interfejsu API REST można na przykład nawigować po hierarchii folderów, odnajdywać zawartość folderu lub pobierać definicje raportów. Można również tworzyć, aktualizować i usuwać obiekty. Przykładowe zadania obsługi obiektów obejmują przekazanie raportu, wykonanie planu odświeżania, usunięcie folderu itp.

## <a name="components-of-a-rest-api-requestresponse"></a>Składniki żądania/odpowiedzi interfejsu API REST
W parze żądanie/odpowiedź interfejsu API REST można wyróżnić pięć składników:

* **Identyfikator URI żądania**, który składa się z następujących elementów: `{URI-scheme} :// {URI-host} / {resource-path} ? {query-string}`. Mimo że identyfikator URI żądania jest zawarty w nagłówku komunikatu żądania, wymieniamy go oddzielnie, ponieważ większość języków i struktur wymaga jego przekazania poza komunikatem żądania.
  
  * Schemat identyfikatora URI: określa protokół używany do przesyłania żądania, na przykład `http` lub `https`.
  * Host identyfikatora URI: określa nazwę domeny lub adres IP serwera, na którym jest hostowany punkt końcowy usługi REST, na przykład `myserver.contoso.com`.
  * Ścieżka zasobu: określa zasób lub kolekcję zasobów, która może obejmować wiele segmentów używanych przez usługę podczas wybierania tych zasobów. Na przykład do pobrania określonych właściwości klasy CatalogItem można użyć elementu `CatalogItems(01234567-89ab-cdef-0123-456789abcdef)/Properties`.
  * Ciąg zapytania (opcjonalnie): udostępnia dodatkowe proste parametry, takie jak wersja interfejsu API lub kryteria wybierania zasobów.
* Pola nagłówka komunikatu żądania HTTP:
  
  * Wymagana [metoda HTTP](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) (znana także jako operacja lub polecenie), która informuje usługę o żądanym typie operacji. Interfejsy API REST usług Reporting Services obsługują metody DELETE, GET, HEAD, PUT, POST i PATCH.
  * Opcjonalne dodatkowe pola nagłówka wymagane przez określony identyfikator URI i metodę HTTP.
* Opcjonalne pola **treści komunikatu żądania** HTTP umożliwiające obsługę identyfikatora URI i działania protokołu HTTP. Na przykład operacje POST zawierają obiekty zakodowane w formacie MIME, które są przekazywane jako parametry złożone. W przypadku operacji POST lub PUT typ treści z kodowaniem MIME należy również określić w nagłówku żądania `Content-type`. Niektóre usługi wymagają użycia konkretnego typu MIME, takiego jak `application/json`.
* Pola **nagłówka komunikatu odpowiedzi** HTTP:
  
  * [Kod stanu HTTP](http://www.w3.org/Protocols/HTTP/HTRESP.html) — od kodów 2xx oznaczających powodzenie do kodów błędów 4xx lub 5xx. Można także zwracać kod stanu zdefiniowany przez usługę zgodnie z informacjami podanymi w dokumentacji interfejsu API.
  * Opcjonalne dodatkowe pola nagłówka, wymagane do obsługi odpowiedzi na żądanie, takie jak nagłówek odpowiedzi `Content-type`.
* Opcjonalne pola **treści komunikatu odpowiedzi** HTTP:
  
  * Obiekty odpowiedzi zakodowane w formacie MIME są zwracane w treści odpowiedzi HTTP, np. odpowiedzi metody GET zwracającej dane. Zazwyczaj te obiekty są zwracane w formacie strukturalnym, takim jak JSON lub XML, zgodnie z nagłówkiem odpowiedzi `Content-type`.

## <a name="api-documentation"></a>Dokumentacja interfejsu API
Nowoczesny interfejs API REST wymaga nowoczesnej dokumentacji interfejsu API. Interfejs API REST jest oparty na specyfikacji OpenAPI (nazywanej też specyfikacją struktury Swagger), a dokumentacja jest dostępna w witrynie [SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0). Witryna SwaggerHub pomaga również wygenerować bibliotekę klienta w wybranym języku — JavaScript, TypeScript, C#, Java, Python, Ruby i innych.

## <a name="testing-api-calls"></a>Testowanie wywołań interfejsu API
Narzędzie do testowania komunikatów żądań/odpowiedzi HTTP nosi nazwę [Fiddler](http://www.telerik.com/fiddler). Jest to bezpłatny internetowy serwer proxy debugowania, który pozwala przechwytywać żądania REST, co ułatwia diagnozowanie komunikatów żądania/odpowiedzi HTTP.

## <a name="next-steps"></a>Następne kroki
Zapoznaj się z dostępnymi interfejsami API w witrynie [SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0).

Przykłady są dostępne w witrynie [GitHub](https://github.com/Microsoft/Reporting-Services). Przykład obejmuje aplikację HTML 5 opartą na technologiach TypeScript i React oraz pakiet internetowy zawierający demonstrację użycia programu PowerShell.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)
