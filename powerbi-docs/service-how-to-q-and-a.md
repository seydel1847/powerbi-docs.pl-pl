---
title: "Jak używać funkcji pytań i odpowiedzi w usłudze Power BI"
description: "Jak używać funkcji pytań i odpowiedzi w usłudze Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
editor: 
tags: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: a6736916a4bb2e94c1f5e1e3c3c3e5339cf990ec
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-use-power-bi-qa"></a>Jak używać funkcji pytań i odpowiedzi w usłudze Power BI
## <a name="ask-questions-of-your-data-using-natural-language"></a>Zadawanie pytań o dane za pomocą języka naturalnego
Rozpocznij na pulpicie nawigacyjnym. Pole pytanie pytań i odpowiedzi jest miejscem, gdzie wpisujesz swoje pytanie przy użyciu języka naturalnego. Funkcja pytań i odpowiedzi rozpoznaje wpisywane słowa i określa, gdzie (w którym zestawie danych) znaleźć odpowiedzi. Funkcja pytań i odpowiedzi pomaga też uformować Twoje pytanie za pomocą automatycznego uzupełniania, przeredagowania oraz innych pomocy tekstowych i wizualnych.

![](media/service-how-to-q-and-a/powerbi-qna.png)

Odpowiedź na Twoje pytanie jest wyświetlana jako interaktywna wizualizacja aktualizowana w miarę modyfikacji pytania.

Funkcja pytań i odpowiedzi jest interaktywna i nawet przyjemna, a często jedno pytanie będzie prowadziło do wielu innych, ponieważ wizualizacje ujawniają ciekawe ścieżki do tropienia. Obejrzyj Amandę demonstrującą używanie funkcji pytań i odpowiedzi do tworzenia elementów wizualnych, zagłębiania się w nie i przypinania ich do pulpitów nawigacyjnych.

> [!NOTE]
> Funkcja Pytania i odpowiedzi jest również dostępna w [aplikacji Microsoft Power BI dla systemu iOS na urządzeniach iPad, iPhone i iPod Touch](mobile-apps-ios-qna.md).
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="use-natural-language-to-ask-questions-about-your-data"></a>Używanie języka naturalnego do zadawania pytań dotyczących danych
1. Umieść kursor w polu pytania. Jeszcze przed rozpoczęciem wpisywania funkcja pytań i odpowiedzi wyświetla nowy ekran z sugestiami ułatwiającymi sformułowanie pytania.
   
   ![](media/service-how-to-q-and-a/powerbi-qna-cursor.png)  
   
   Ta lista zawiera:  
   a.  pytania użyte do utworzenia [kafelków](service-dashboard-tiles.md), które są już przypięte do pulpitu nawigacyjnego, oraz  
   b.  nazwy tabel w [źródłowych zestawach danych](service-get-data.md).  
   
   Zawsze możesz wybrać jedno z tych pytań jako punkt początkowy i dalej uściślać pytanie, aby znaleźć określoną odpowiedź, której szukasz. Możesz też użyć nazwy tabeli, aby ułatwić sformułowanie nowego pytania.
2. Wybierz z listy rozwijanej lub zacznij pisać własne pytanie.  
   
   ![](media/service-how-to-q-and-a/powerbi-qna-list.png)
3. W miarę pisania pytania funkcja pytań i odpowiedzi usługi Power BI wybiera najlepszą [wizualizację](power-bi-visualization-types-for-reports-and-q-and-a.md) do wyświetlania odpowiedzi, przy czym wizualizacja zmienia się dynamicznie w miarę modyfikowania pytania. Funkcja pytań i odpowiedzi pomaga też sformułować Twoje pytanie za pomocą automatycznego uzupełniania, przeredagowywania pytania oraz innych pomocy tekstowych i wizualnych.  
   ![](media/service-how-to-q-and-a/powerbi-qna-viz.png)
4. Gdy wpisujesz zapytanie, usługa Power BI wyszukuje odpowiedź w dowolnym zestawie danych, który ma kafelek na tym pulpicie nawigacyjnym.  Jeśli wszystkie kafelki pochodzą z *zestawu danych A*,odpowiedź będzie pochodziła z *zestawu danych A*.  Jeśli istnieją kafelki z *zestawu danych A* i *zestawu danych B*, funkcja pytań i odpowiedzi wyszuka najlepszą odpowiedź z tych 2 zestawów danych.
   
   > [!TIP]
   > Dlatego należy zachować ostrożność, jeśli masz tylko jeden kafelek z *zestawu danych A* i usuniesz go z pulpitu nawigacyjnego, funkcja pytań i odpowiedzi nie będzie już miała dostępu do *zestawu danych A*.
   > 
   > 
5. Gdy wynik Cię zadowala, [przypnij wizualizację do pulpitu nawigacyjnego](service-dashboard-pin-tile-from-q-and-a.md), wybierając ikonę pinezki w prawym górnym rogu. Jeśli pulpit nawigacyjny został Ci udostępniony lub jest częścią aplikacji, nie można będzie jej przypiąć.
   
   ![](media/service-how-to-q-and-a/pbi_qna_finish-typing-question.jpg)

### <a name="tell-qa-which-visualization-to-use"></a>Poinformuj funkcję pytań i odpowiedzi, której wizualizacji użyć.
Za pomocą funkcji pytań i odpowiedzi nie tylko możesz zadawać pytania tak, aby dane same przemówiły, możesz też wskazać sposób ich wyświetlenia. Po prostu dodaj „jako <visualization type>„ na końcu pytania.  Na przykład „Pokaż spis magazynu według roślin jako mapę” i „pokaż cały spis jako kartę”.  Wypróbuj to samodzielnie.

## <a name="how-does-qa-know-how-to-answer-questions"></a>Skąd funkcja pytań i odpowiedzi wie, jak odpowiadać na pytania?
### <a name="which-datasets-does-qa-use"></a>Których zestawów danych używa funkcja pytań i odpowiedzi?
Skąd funkcja pytań i odpowiedzi wie, jak odpowiadać na pytania dotyczące danych? Polega ona na nazwach tabel, kolumn i pól obliczeniowych w źródłowym zestawie danych. Co więc użytkownik (lub właściciel zestawu danych) uważa za ważne! 

Na przykład załóżmy, że masz tabelę programu Excel o nazwie „Sprzedaż” z kolumnami zatytułowanymi „Produkt”, „Miesiąc”, „Sprzedane jednostki”, „Sprzedaż brutto” i „Zysk”. Możesz zadawać pytania dotyczące dowolnej z tych jednostek.  Możesz zapytać „pokaż *sprzedaż*”, „całkowity *zysk* według *miesiąca*”, „sortuj *produkty* według *sprzedanych jednostek*” i inne.

Funkcja pytań i odpowiedzi może odpowiadać na pytania, które są oparte na sposobie organizacji zestawu danych. Jak to będzie działać w usłudze Salesforce? Gdy połączysz się ze swoim kontem witryny salesforce.com, usługa Power BI automatycznie wygeneruje pulpit nawigacyjny.  Zanim zaczniesz zadawać pytania za pomocą funkcji pytań i odpowiedzi, zapoznaj się z danymi wyświetlanymi w wizualizacjach pulpitu nawigacyjnego oraz w danych wyświetlanych na liście rozwijanej pytań i odpowiedzi.

* Jeśli etykiety osi i wartości wizualizacji zawierają terminy „sprzedaż”, „konto”, „miesiąc” i „możliwości”, możesz bezpiecznie zadawać pytania, takie jak: „Które *konto* ma największe *możliwości* lub pokaż *sprzedaż* według miesiąca jako wykres słupkowy”.
* Jeśli lista rozwijana zawiera terminy „sprzedawcy”, „stan” i „rok”, możesz bezpiecznie zadawać pytania, takie jak: „który *sprzedawca* miał najniższą *sprzedaż* na *Florydzie* w *2013*”.

Jeśli masz dane wydajności witryny internetowej w usłudze Google Analytics, możesz zadać pytanie o czas pozostawania na stronie internetowej, liczbę unikatowych odwiedzin strony i stopień zaangażowania użytkownika. Lub, jeśli zadajesz zapytanie do danych demograficznych, możesz zadawać pytania na temat wieku i przychodu gospodarstwa domowego według lokalizacji.

### <a name="which-visualization-does-qa-use"></a>Jakich wizualizacji używa funkcja pytań i odpowiedzi?
Funkcja pytań i odpowiedzi wybiera najlepsze wizualizacje na podstawie wyświetlanych danych. Niekiedy dane w źródłowych zestawach danych są definiowane jako określony typ lub kategoria i pomaga to funkcji pytań i odpowiedzi określić sposób ich wyświetlania. Na przykład, jeśli dane są zdefiniowane jako typ Data, najprawdopodobniej będą wyświetlane jako wykres liniowy. Dane, które należą do kategorii miejscowość, najprawdopodobniej będą wyświetlane jako mapa.

Można określić funkcji pytań i odpowiedzi, której wizualizacji użyć, dodając ją do na swojego pytania. Jednak należy pamiętać, że nie zawsze może być możliwe wyświetlenie w funkcji pytań i odpowiedzi danych w żądanym typie wizualizacji.

Aby uzyskać informacje na temat słów kluczowych, które są rozpoznawane przez funkcję pytań i odpowiedzi, zobacz [Porady dotyczące zadawanie pytań](service-q-and-a-tips.md).

## <a name="next-steps"></a>Następne kroki
Powrót do [pytań i odpowiedzi w usłudze Power BI](service-q-and-a.md)  
[Samouczek: Używanie pytań i odpowiedzi z próbką sprzedaży detalicznej](power-bi-visualization-introduction-to-q-and-a.md)  
[Porady dotyczące zadawania pytań w funkcji pytań i odpowiedzi](service-q-and-a-tips.md)  
[Przygotowanie skoroszytu dla funkcji pytań i odpowiedzi](service-prepare-data-for-q-and-a.md)  
[Przypinanie kafelka do pulpitu nawigacyjnego z funkcji pytań i odpowiedzi](service-dashboard-pin-tile-from-q-and-a.md)  

