---
title: Korzystanie z kolumn obliczeniowych w programie Power BI Desktop
description: Kolumny obliczeniowe w programie Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 2a92426061b37753c529b84a1de6b8068cb3bc5f
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="using-calculated-columns-in-power-bi-desktop"></a>Korzystanie z kolumn obliczeniowych w programie Power BI Desktop
Za pomocą kolumn obliczeniowych możesz dodawać nowe dane do tabel już znajdujących się w Twoim modelu. Zamiast jednak wykonywania zapytań i ładowania wartości do nowej kolumny ze źródła danych, tworzona jest formuła języka DAX (Data Analysis Expressions) definiująca wartości w kolumnie. W programie Power BI Desktop kolumny obliczeniowe są tworzone za pomocą funkcji Nowa kolumna w widoku raportu.

W przeciwieństwie do kolumn niestandardowych utworzonych jako część zapytania za pomocą polecenia Dodaj kolumnę niestandardową w edytorze zapytań, kolumny obliczeniowe utworzone w widoku raportu lub widoku danych bazują na danych już załadowanych do modelu. Na przykład można połączyć wartości z dwóch różnych kolumn w dwóch różnych, ale powiązanych tabelach, przeprowadzić dodawanie lub wyodrębnić podciągi.

Tworzone kolumny obliczeniowe pojawiają się na liście Pola tak samo jak wszystkie inne pola, ale będą mieć specjalną ikonę, która wskazuje, że ich wartości są wynikiem formuły. Kolumny można dowolnie nazywać i dodawać do wizualizacji w raporcie tak samo jak inne pola.

![](media/desktop-calculated-columns/calccolinpbid_fields.png)

Do obliczania kolumn obliczeniowych używany jest język DAX ([Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx)) — język formuł przeznaczony do pracy z danymi relacyjnymi, takimi jak używane w programie Power BI Desktop. Język DAX zawiera bibliotekę ponad 200 funkcji, operatorów i konstrukcji, które zapewniają ogromną elastyczność w tworzeniu formuł do obliczania wyników na potrzeby praktycznie dowolnej analizy danych. Aby dowiedzieć się więcej na temat języka DAX, zobacz sekcję Dowiedz się więcej na końcu tego artykułu.

Formuły języka DAX są podobne do formuł programu Excel. W rzeczywistości język DAX zawiera sporo takich samych funkcji jak program Excel. Funkcje języka DAX są jednak przeznaczone do pracy nad danymi interaktywnie dzielonymi lub filtrowanymi w raporcie, tak jak w programie Power BI Desktop. W odróżnieniu od programu Excel, w którym można mieć różne formuły dla każdego wiersza w tabeli, formuła języka DAX tworzona dla nowej kolumny będzie obliczać wyniki dla każdego wiersza w tabeli. Wartości kolumn są ponownie obliczane w miarę konieczności, na przykład po odświeżeniu danych bazowych, gdy wartości zmienią się.

## <a name="lets-look-at-an-example"></a>Spójrzmy na przykład
Jeff kieruje dostawami w firmie Contoso. Chce utworzyć raport pokazujący liczbę dostaw do różnych miast. Ma tabelę Geography (Dane geograficzne) z oddzielnymi polami dla miast i stanów. Ale Jeff chce, aby w jego raporcie wartości City (Miasto) i State (Stan) były pokazywane jako jedna wartość w tym samym wierszu. W tej chwili tabela Geography Jeffa nie ma pola, którego potrzebuje.

![](media/desktop-calculated-columns/calccolinpbid_cityandstatefields.png)

Jednak za pomocą kolumny obliczeniowej Jeff może po prostu złożyć (połączyć) miasta z kolumny City ze stanami z kolumny Stan.

Jeff klika prawym przyciskiem myszy tabelę Geography i klika polecenie Nowa kolumna. Następnie wprowadza następującą formułę języka DAX w pasku formuły:

![](media/desktop-calculated-columns/calccolinpbid_formula.png)

Ta formuła tworzy nową kolumnę o nazwie CityState i dla każdego wiersza w tabeli Geography pobiera wartości z kolumny City, dodaje przecinek i spację, a następnie dołącza wartości z kolumny State.

Teraz Jeff ma potrzebne pole.

![](media/desktop-calculated-columns/calccolinpbid_citystatefield.png)

Może je dodać do swojego raportu wraz z liczbą dostaw. Szybko i przy minimalnym nakładzie pracy Jeff uzyskał pole City, State i może je dodać do wizualizacji w zasadzie dowolnego typu. Jeff widzi, że gdy tworzy wizualizację z mapą, program Power BI Desktop wie, jak odczytać wartości City, State z nowej kolumny.

![](media/desktop-calculated-columns/calccolinpbid_citystatemap.png)

## <a name="learn-more"></a>Dowiedz się więcej
To, co tu przedstawiliśmy, to tylko krótkie wprowadzenie do kolumn obliczeniowych. Pamiętaj, aby zapoznać się z samouczkiem [Tworzenie kolumn obliczeniowych w programie Power BI Desktop](desktop-tutorial-create-calculated-columns.md), skąd możesz pobrać przykładowy plik i wziąć udział w szczegółowych lekcjach na temat tworzenia większej liczby kolumn. 

Aby dowiedzieć się więcej na temat języka DAX, zobacz [Podstawy języka DAX w programie Power BI Desktop](desktop-quickstart-learn-dax-basics.md).

Aby dowiedzieć się więcej na temat kolumn tworzonych jako część zapytania, zobacz sekcję Tworzenie kolumn niestandardowych w temacie [Typowe zadania dotyczące zapytań w programie Power BI Desktop](desktop-common-query-tasks.md).  

