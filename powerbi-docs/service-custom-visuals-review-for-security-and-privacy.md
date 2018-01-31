---
title: "Przegląd wizualizacji niestandardowych pod kątem zabezpieczeń i prywatności"
description: "Przed włączeniem wizualizacji niestandardowej należy sprawdzić ją pod kątem zabezpieczeń i prywatności, aby była zgodna ze standardami obowiązującymi w danej organizacji."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 09/05/2017
ms.author: maghan
ms.openlocfilehash: 15f8d9090736a62fdaa53aa3f19e7e0fff127337
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2018
---
# <a name="review-custom-visuals-for-security-and-privacy"></a>Przegląd wizualizacji niestandardowych pod kątem zabezpieczeń i prywatności
Przed włączeniem wizualizacji niestandardowej należy sprawdzić ją pod kątem zabezpieczeń i prywatności, aby była zgodna ze standardami obowiązującymi w danej organizacji.

## <a name="enable-a-custom-visual"></a>Włączanie wizualizacji niestandardowej
<a name="enable"></a>Wizualizacja niestandardowa w raporcie jest wyłączona do momentu wybrania pozycji **Włącz niestandardowe wizualizacje** w sposób pokazany poniżej.  

![](media/service-custom-visuals-review-for-security-and-privacy/emptyvisual.png)

## <a name="considerations-before-you-enable-a-custom-visual"></a>Zagadnienia do rozważenia przed włączeniem wizualizacji niestandardowej
<a name="considerations"></a>

> [!WARNING]
> Wizualizacja niestandardowa może zawierać kod, który stanowi zagrożenie pod kątem zabezpieczeń lub prywatności. Dlatego wizualizacja niestandardowa w raporcie jest wyłączona do momentu wybrania pozycji Włącz niestandardowe wizualizacje. Poniżej przedstawiono kilka kwestii, które warto rozważyć przed podjęciem decyzji o włączeniu wizualizacji niestandardowej:
> 
> 

1. Autor i źródło wizualizacji niestandardowej użytej w raporcie muszą być zaufane.
2. Jeśli nie masz pewności, co zrobić, skonsultuj się z zespołem informatycznym, aby podjąć świadomą decyzję dotyczącą ewentualnego włączenia wizualizacji niestandardowych w wyświetlanych raportach.
3. Jeśli ktoś udostępnia Ci raport, który zawiera wizualizację niestandardową, nie czuj się w obowiązku włączyć tę wizualizację, nawet jeśli pochodzi od Twego współpracownika. Warto się chwilę zastanowić, czy wizualizacja ta jest niezbędna do wykonania danego zadania. Jeśli wolisz nie ryzykować, zawsze możesz poprosić o dostarczenie raportu bez wizualizacji niestandardowej.

## <a name="security-best-practices-for-it-professionals-to-enable-a-custom-visual"></a>Najlepsze rozwiązania dla informatyków dotyczące włączania wizualizacji niestandardowej
<a name="security"></a>

> [!WARNING]
> Wizualizacja niestandardowa może zawierać kod, który stanowi zagrożenie pod kątem zabezpieczeń lub prywatności. Dlatego wizualizacja niestandardowa w raporcie jest wyłączona do momentu wybrania pozycji Włącz niestandardowe wizualizacje. Istnieje kilka najlepszych rozwiązań, które można wykorzystać, aby ocenić wizualizację niestandardową pod kątem zabezpieczeń i prywatności.
> 
> 

1. Przeprowadź proces weryfikacyjny dotyczący wizualizacji niestandardowych w organizacji. Zweryfikowane wizualizacje niestandardowe mogłyby być udostępniane użytkownikom wewnętrznym za pośrednictwem wewnętrznej witryny internetowej, takiej jak biblioteka dokumentów programu SharePoint lub dokumentu programu OneNote.
2. Zapewnij wskazówki dla użytkowników biznesowych dotyczące prawidłowego korzystania z wizualizacji niestandardowych i utwórz grupę e-mail dla użytkowników biznesowych umożliwiającą im wysyłanie pytań dotyczących zabezpieczeń i prywatności.
3. Przeprowadź ocenę kodu JavaScript w pliku pbiviz wizualizacji niestandardowej.

**Aby przeprowadzić ocenę kodu JavaScript w wizualizacji niestandardowej**

Wizualizacja niestandardowa używa języka JavaScript, przez co może zagrażać bezpieczeństwu lub prywatności. Jeśli otrzymasz wizualizację niestandardową lub plik pbix z wizualizacją niestandardową pochodzącą z nieznanego źródła, sprawdź dokładnie, czy kod JavaScript jest bezpieczny.

Aby przeprowadzić ocenę kodu JavaScript w wizualizacji niestandardowej, wyodrębnij kod wizualizacji niestandardowej. Poniżej przedstawiono sposób wyodrębniania kodu:  

1. Zapisz plik pbiviz w folderze.
2. Zmień nazwę pliku na plik zip.
3. Wyodrębnij plik zip do folderu lokalnego.

## <a name="custom-visual-file-contents"></a>Zawartość pliku wizualizacji niestandardowej
Poniżej przedstawiono zawartość pliku pbiviz:

| **Plik** | **Opis** |
|:--- |:--- |
| ./package.json |Pliku manifestu wskazujący, które pliki należy załadować w przypadku wizualizacji niestandardowej. |
| ./resources |Zawiera kod CSS, TypeScript i JavaScript używany przez wizualizację niestandardową. |
| ./resources/&lt;nazwa&gt; |&lt;nazwa&gt; to nazwa wizualizacji niestandardowej. |
| ./resources/&lt;name&gt;.css |Plik zasobu css wizualizacji niestandardowej. |
| ./resources/&lt;nazwa&gt;.js |Kod, który jest wykonywany, kiedy użytkownik kliknie pozycję Włącz niestandardowe wizualizacje lub zaimportuje wizualizację niestandardową. Ostrzeżenie: kod JavaScript może zawierać elementy zagrażające prywatności i bezpieczeństwu. |
| ./resources/&lt;nazwa&gt;.ts |Kod źródłowy JavaScript wizualizacji w formacie TypeScript. Ostrzeżenie: kod JavaScript lub TypeScript może zawierać elementy zagrażające prywatności i bezpieczeństwu. |
| ./resources/&lt;nazwa&gt;.png |Ikona pokazywana użytkownikowi wizualizacji. |

Po wyodrębnieniu pliku pbiviz możesz przeprowadzić ocenę kodu. Poniżej przedstawiono niektóre najlepsze rozwiązania i zagrożenia, na które warto uważać.

## <a name="best-practices-to-evaluate-the-javascript-or-typescript-code"></a>Najlepsze rozwiązania dotyczące oceny kodu JavaScript i TypeScript
Kod **JavaScript** lub **TypeScript** może zawierać elementy zagrażające prywatności i bezpieczeństwu. Poniżej przedstawiono niektóre najlepsze rozwiązania i zagrożenia, na które warto uważać.

### <a name="best-practices-to-evaluate-javascript-code"></a>Najlepsze rozwiązania dotyczące oceny kodu JavaScript
* Zawsze należy przeprowadzić ocenę zawartości pliku js. Plik ten zawiera kod, który jest wykonywany. Może się tak zdarzyć, że zawartość pliku ts nie będzie kompilowana do pliku js stanowiącego część wizualizacji niestandardowej.
* Zawsze należy przeprowadzić ocenę zawartości pliku ts. Plik ts można załadować do pakietu **Narzędzia deweloperskie**, wyeksportować wizualizację i porównać wynikowy plik js w nowo utworzonym pliku pbiviz z oryginalnym plikiem js zawartym w wizualizacji.
* Sprawdź, czy ikona wizualizacji niestandardowej nie przypomina za bardzo innych wizualizacji, do których użytkownik jest przyzwyczajony.
* Ocenę wizualizację zawsze przeprowadzaj za pomocą konta testowego, które ma minimalne uprawnienia i nie ma dostępu do żadnych poufnych danych. Najlepiej, aby konto testowe było kontem lokalnym, które nie zawiera informacji logowania do usług innych niż Power BI.

### <a name="threats-to-look-for-in-javascript-code"></a>Zagrożenia, na które należy uważać w przypadku kodu JavaScript
* Sprawdź, jakie działania mają miejsce w sieci, kiedy wizualizacja jest używana w trybach edycji i wyświetlania. Sprawdź, czy występujące żądania są akceptowalne. Jeśli autor wizualizacji o tym nie uprzedził, nie powinny występować żadne żądania skierowane do zasobów spoza domeny usługi Power BI.
* Wszelkie dane wychodzące z domeny usługi Power BI powinny być zgodne z oczekiwaniami dotyczącymi normalnego użytkowania. Jeśli na przykład wizualizacja implementuje odtwarzacz wideo, który wyświetla klip wideo z innej witryny, korzystając z elementu iFrame, określone informacje muszą zostać wysłane w żądaniach IFrame, aby zapewnić prawidłowe renderowanie materiału wideo. Jednak jeśli widzisz, że jest wysyłany cały zestaw danych, warto zbadać, czy faktycznie jest to wymagane i potrzebne.
* Sprawdź, czy wizualizacja niestandardowa wysyła lub przechowuje identyfikowalne dane osobowe.
* Sprawdź, czy wizualizacja niestandardowa próbuje uzyskać dostęp do zasobów komputera lokalnego (np. próbuje zapisać pliki na dysku lub uzyskać dostęp do plików cookie).
* Sprawdź, czy wizualizacja niestandardowa ma ukryty kod lub kod bez wyraźnego przeznaczenia.
* Zapisuj kopie poszczególnych wizualizacji sprawdzonych w przeszłości.
* Jeśli oceniasz aktualizację wizualizacji, która została już wcześniej sprawdzona, koniecznie sprawdź, jakie zmiany zostały wprowadzone. Do aktualizacji podchodź równie rygorystycznie jak do pierwszego sprawdzania danej wizualizacji.
* Jeśli zauważysz coś podejrzanego lub niejasnego, skonsultuj się z nami. Chętnie pomożemy.

## <a name="next-steps"></a>Następne kroki
[Wizualizacje w usłudze Power BI](power-bi-report-visualizations.md)  
[Wizualizacje niestandardowe w usłudze Power BI](power-bi-custom-visuals.md)  
[Publikowanie wizualizacji niestandardowych w Sklepie Office](developer/office-store.md)  
[Wprowadzenie do korzystania z narzędzi deweloperskich do tworzenia wizualizacji niestandardowych](service-custom-visuals-getting-started-with-developer-tools.md)  
[Jak certyfikować wizualizację niestandardową](power-bi-custom-visuals-certified.md)    
[Klip wideo: tworzenie wizualizacji niestandardowych dla usługi Power BI — Sachin Patney i Nico Cristache](https://www.youtube.com/watch?v=kULc2VbwjCc)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

