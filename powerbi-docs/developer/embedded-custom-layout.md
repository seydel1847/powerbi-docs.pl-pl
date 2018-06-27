---
title: Układy niestandardowe z osadzoną zawartością usługi Power BI
description: Dowiedz się więcej na temat układów niestandardowych używanych w przypadku osadzania zawartości usługi Power BI w aplikacji.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 12/19/2017
ms.author: maghan
ms.openlocfilehash: fc684ebdf6b1ccb53bdd7794b19c1120ece635a3
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34288135"
---
# <a name="custom-layouts"></a>Układy niestandardowe


Układ niestandardowy umożliwia osadzenie raportu z układem innym niż oryginalny raport. Definiowanie nowego układu różni się w przypadku definiowania tylko rozmiaru strony, kontrolowania rozmiarów wizualizacji lub pozycji i widoczności.

Aby zdefiniować układ niestandardowy, zdefiniuj obiekt układu niestandardowego i przekaż go do obiektu ustawień w osadzonej konfiguracji. Ponadto ustaw element LayoutType na Niestandardowy. Aby dowiedzieć się więcej, zobacz [Embed Configuration Details (Szczegóły osadzania konfiguracji)](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details).

```javascript
var embedConfig = {
    ...
    settings: {
            layoutType: models.LayoutType.Custom
    customLayout: {...}
    }
};
```

## <a name="object-definition"></a>Definicja obiektu

```javascript
interface ICustomLayout {
  pageSize?: IPageSize;
  displayOption?: DisplayOption;
  pagesLayout?: PagesLayout;
}

enum PageSizeType {
  Widescreen,
  Standard,
  Cortana,
  Letter,
  Custom
}
interface IPageSize {
  type: PageSizeType;
}
interface ICustomPageSize extends IPageSize {
  width?: number;
  height?: number;
}

enum DisplayOption {
  FitToPage,
  FitToWidth,
  ActualSize
}
```

- `pageSize`: używaj rozmiaru strony do kontrolowania rozmiaru obszaru kanwy (białego obszaru raportu).
- `displayOptions`: możliwe wartości to: FitToWidth, FitToPage lub ActualSize. Ten element kontroluje sposób skalowania kanwy w celu dopasowania jej do elementu iframe.
- `pagesLayout`: kontroluje układ każdej wizualizacji. Aby uzyskać więcej informacji, zobacz PagesLayout.

## <a name="pages-layout"></a>Układ stron

Definiowanie obiektu układu stron to w zasadzie definiowanie układu dla każdej strony oraz definiowanie układu każdej wizualizacji na każdej stronie.
Element PageLayout jest opcjonalny. Jeśli nie zdefiniowano układu dla strony, zostanie zastosowany układ domyślny (zapisany w raporcie).

Element pagesLayout to mapa od nazwy strony do obiektu PageLayout. Definicja:

```javascript
type PagesLayout = { [key: string]: IPageLayout; };
```

Obiekt PageLayout zawiera mapę układu wizualizacji, która mapuje każdą nazwę wizualizacji na obiekt układu wizualizacji:

```javascript
interface IPageLayout {
  visualsLayout: { [key: string]: IVisualLayout; };
}
```

## <a name="visual-layout"></a>Układ wizualizacji

Aby zdefiniować układ wizualizacji, przekaż nową pozycję i rozmiar oraz nowy stan widoczności.

```javascript
interface IVisualLayout {
  x?: number;
  y?: number;
  z?: number;
  width?: number;
  height?: number;
  displayState?: IVisualContainerDisplayState;
}

interface IVisualContainerDisplayState {
  mode: VisualContainerDisplayMode;
}

enum VisualContainerDisplayMode {
  Visible,
  Hidden
}
```

- `x,y,z`: definiuje nową pozycję wizualizacji.
- `width`, wysokość: definiuje nowy rozmiar wizualizacji.
- `displayState`: definiuje widoczność wizualizacji.


## <a name="update-layout"></a>Aktualizowanie układu

Metoda updateSettings umożliwia aktualizowanie układu raportu w dowolnej chwili, gdy raport jest ładowany. Zobacz [Update Settings (Aktualizowanie ustawień)](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Update-Settings).

## <a name="code-example"></a>Przykład kodu

```javascript
// Get models. models contains enums that can be used.
var models = window['powerbi-client'].models;
    
var embedConfiguration = {
    type: 'report',
    id: '5dac7a4a-4452-46b3-99f6-a25915e0fe55',
    embedUrl: 'https://app.powerbi.com/reportEmbed',
    tokenType: models.TokenType.Embed,
    accessToken: 'H4...rf',
    settings: {
            layoutType: models.LayoutType.Custom
        customLayout: {
            pageSize: {
                type: models.PageSizeType.Custom,
                width: 1600,
                height: 1200
            },
            displayOption: models.DisplayOption.ActualSize,
            pagesLayout: {
                "ReportSection1" : {
                    visualsLayout: {
                        "VisualContainer1": {
                            x: 1,
                            y: 1,
                            z: 1,
                            width: 400,
                            height: 300,
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Visible
                            }
                        },
                        "VisualContainer2": {
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Hidden
                            }
                        },
                    }
                }
            }
        }
    }
};
     
// Get a reference to the embedded report HTML element
var embedContainer = document.getElementById('embedContainer');
 
// Embed the report and display it within the div container.
var report = powerbi.embed(embedContainer, embedConfiguration);

```


## <a name="see-also"></a>Zobacz także

[Osadzanie pulpitów nawigacyjnych, raportów i kafelków usługi Power BI](embedding-content.md)   
[Zapytaj społeczność usługi Power BI](https://community.powerbi.com/)

