---
title: Rozwiązywanie problemów z tworzeniem wizualizacji niestandardowych usługi Power BI
description: W tym artykule omówiono niektóre typowe problemy, które można napotkać podczas projektowania lub tworzenia wizualizacji niestandardowej usługi Power BI.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/06/2018
ms.openlocfilehash: d6f3f654574e9cca081ae2f8191fd7b9fc017afd
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223572"
---
# <a name="troubleshoot-power-bi-custom-visuals"></a>Rozwiązywanie problemów z wizualizacjami niestandardowymi usługi Power BI

## <a name="debug"></a>Debugowanie

**Nie znaleziono polecenia Pbiviz (i podobne błędy)**

Po uruchomieniu polecenia `pbiviz` w wierszu polecenia terminalu powinien zostać wyświetlony ekran pomocy. Jeśli tak nie jest, nie zostało ono poprawnie zainstalowane. Upewnij się, że masz zainstalowaną wersję oprogramowania NodeJS 4.0 lub nowszą.

**Nie można znaleźć wizualizacji debugowania na karcie Wizualizacje**

Wizualizacja debugowania wygląda jak ikona wiersza polecenia na karcie **Wizualizacje**.

![Wybór wizualizacji](media/power-bi-custom-visuals-troubleshoot/powerbi-developer-visual-selection.png)

Jeśli jej nie widać, sprawdź, czy została włączona w ustawieniach usługi Power BI.

> [!NOTE]
> Wizualizacja debugowania jest aktualnie dostępna tylko w usłudze Power BI, a nie w programie Power BI Desktop ani aplikacji mobilnej. Natomiast spakowana wizualizacja będzie działała wszędzie.

**Nie można skontaktować się z serwerem wizualizacji**

Uruchom serwer wizualizacji, wprowadzając polecenie `pbiviz start` w wierszu polecenia terminalu na poziomie katalogu głównego projektu wizualizacji. Jeśli serwer jest uruchomiony, prawdopodobnie nie zainstalowano poprawnie certyfikatów SSL.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji i odpowiedzi na pytania, odwiedź stronę [często zadawanych pytań dotyczących wizualizacji niestandardowych usługi Power BI](power-bi-custom-visuals-faq.md#organizational-custom-visuals).