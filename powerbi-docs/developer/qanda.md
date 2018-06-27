---
title: Funkcja pytań i odpowiedzi w usłudze Power BI Embedded
description: Usługa Power BI Embedded oferuje możliwość zastosowania funkcji pytań i odpowiedzi w aplikacji oraz umożliwia użytkownikom zadawanie pytań przy użyciu języka naturalnego.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/20/2017
ms.author: maghan
ms.openlocfilehash: d1fd42f059f8050662adc80018748d11c1e73e2b
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34813761"
---
# <a name="qa-in-power-bi-embedded"></a>Funkcja pytań i odpowiedzi w usłudze Power BI Embedded
Usługa Power BI Embedded oferuje możliwość zastosowania funkcji pytań i odpowiedzi w aplikacji oraz umożliwia użytkownikom zadawanie pytań przy użyciu języka naturalnego i otrzymywanie natychmiastowych odpowiedzi w formie wizualizacji, np. wykresów lub diagramów.

![Interaktywne pytanie funkcji pytań i odpowiedzi w osadzonej ramce](media/qanda/embedded-qanda.gif)

Istnieją dwa tryby osadzania funkcji pytań i odpowiedzi w aplikacji: **interaktywny** i **obejmujący tylko wyniki**. Tryb **interaktywny** umożliwia wpisywanie pytań i wyświetlanie odpowiedzi w formie wizualizacji. Jeśli masz zapisane lub ustawione pytanie, które chcesz wyświetlić, możesz użyć trybu **samych wyników**, uzupełniając pytanie w osadzonej konfiguracji.

Oto przykład kodu JavaScript.

```
// Embed configuration used to describe the what and how to embed.
// This object is used when calling powerbi.embed within the JavaScript API.
// You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
var config= {
    type: 'qna',
    tokenType:   models.TokenType.Embed | models.TokenType.Aad,
    accessToken: access token value,
    embedUrl:    https://app.powerbi.com/qnaEmbed (groupId to be appended as query parameter if required),
    datasetIds:  array of requested data set ids (at the moment we support only one dataset),
    viewMode:    models.QnAMode.Interactive | models.QnAMode.ResultOnly,
    question:    optional parameter for Explore mode (QnAMode.Interactive) and mandatory for Render Result mode (QnAMode.ResultOnly)
};

// Get a reference to the embedded QNA HTML element
var qnaContainer = $('#qnaContainer')[0];

// Embed the QNA and display it within the div container.
var qna = powerbi.embed(qnaContainer, config);
```

## <a name="set-question"></a>Ustawione pytanie
Jeśli używasz **trybu wyniku** z ustawionym pytaniem, możesz wstawić dodatkowe pytania do ramki i natychmiast uzyskać na nie odpowiedzi zastępujące poprzednie wyniki. Nowa wizualizacja zostanie wyrenderowana zgodnie z nowym pytaniem.

Przykładem takiego użycia będzie lista często zadawanych pytań. Użytkownik może przejść przez pytania i uzyskać na nie odpowiedzi w tej samej osadzonej części.

**Fragment kodu dotyczący użycia zestawu SDK języka JavaScript:**  

```        
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

qna.setQuestion("This year sales")
    .then(function (result) {
        …….
    })
    .catch(function (errors) {
        …….
    });
```

## <a name="visual-rendered-event"></a>Zdarzenie z renderowaniem wizualizacji
W przypadku trybu **interaktywnego** aplikację można powiadomić przy użyciu zdarzenia zmiany danych za każdym razem, gdy renderowana wizualizacja ulega zmianie, aby nakierować ją na zaktualizowane zapytanie wejściowe podczas jego wpisywania.

Nasłuchiwanie zdarzenia *visualRendered* umożliwia zapisywanie pytań do użycia w przyszłości. 

**Fragment kodu dotyczący użycia zestawu SDK języka JavaScript:**  

```
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

// qna.off removes a given event listener if it exists.
qna.off("visualRendered");

// qna.on will add an event listener.
qna.on("visualRendered", function(event) {
     …….
});
```

## <a name="embed-token"></a>Token osadzania
Utwórz token osadzania na podstawie zestawu danych, aby uruchomić część pytań i odpowiedzi. Aby uzyskać więcej informacji, zobacz [Generowanie tokenu](https://docs.microsoft.com/rest/api/power-bi/embedtoken).

## <a name="next-steps"></a>Następne kroki
Aby wypróbować osadzanie funkcji pytań i odpowiedzi, sprawdź [Przykład osadzania przy użyciu języka JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/).

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

