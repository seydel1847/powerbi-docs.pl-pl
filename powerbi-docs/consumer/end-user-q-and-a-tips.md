---
title: Porady i wskazówki dotyczące zadawania pytań za pomocą funkcji Pytania i odpowiedzi
description: Porady i wskazówki dotyczące zadawania pytań za pomocą funkcji Pytania i odpowiedzi w usłudze Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 52ce1d0eaf9b99c2717b733592c46d65d2209083
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2018
ms.locfileid: "53280448"
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>Porady dotyczące zadawania pytań w funkcji Pytania i odpowiedzi usługi Power BI
## <a name="words-and-terminology-that-qa-recognizes"></a>Wyrazy i terminologia rozpoznawane przez funkcję Pytania i odpowiedzi
Lista słów kluczowych na tej stronie nie jest wyczerpująca.  Najlepszym sposobem na sprawdzenie, czy usługa Power BI rozpoznaje słowo kluczowe, jest wpisanie tego słowa w polu pytania.  Jeśli słowa lub terminy są wyszarzone, usługa Power BI nie rozpoznaje ich.

Poniższa lista używa czasu teraźniejszego, ale w większości przypadków rozpoznawane są wszystkie czasy. Na przykład rozpoznawane są następujące formy czasownika „is”: **are**, **was**, **were**, **will be**, **have**, **has**, **had**, **will have**, **has got**, **do**, **does**, **did**.  Podobnie czasownik „sort” (sortować) obejmuje formy **sorted** i **sorting**.  Usługa Power BI rozpoznaje i uwzględnia również liczbę pojedynczą i mnogą słowa. 

> [!NOTE]
> Funkcja Pytania i odpowiedzi jest również dostępna w [aplikacji Microsoft Power BI dla systemu iOS na urządzeniach iPad, iPhone i iPod Touch](mobile/mobile-apps-ios-qna.md).
>  


|Kategoria  |Słowa kluczowe  |Kolumna 3  |
|---------|---------|---------|
|**Agregacje**     | total, sum, amount, number, quantity, count, average, most, least, fewest, largest, smallest, highest, biggest, maximum, max, greatest, lowest, littlest, minimum, min          |
|     |         |         
**Przedimki**     |  a, an, the              |
|     |         |         
|**Wartości puste i logiczne**     |   blank, empty, null, z prefiksem „non” lub „non-”, empty string, empty text, true, t, false, f          |
|     |         |         |
|**Porównania**     |   vs, versus, compared to, compared with            |
|     |         |         |
|**Spójniki**     |  and, or, each of, with, versus, &, and, but, nor, along with, in addition to       |         
|          |         |
|**Skróty**     |  Funkcja Pytania i odpowiedzi rozpoznaje niemal wszystkie skróty — spróbuj, aby się przekonać.  Oto kilka przykładów: didn’t, haven’t, he’d, he’s, isn’t, it’s, she’ll, they’d, weren’t, where’ll, who’s, won’t, wouldn’t          |
|        |         |
|**Daty**     |       Usługa Power BI rozpoznaje większość terminów opisujących daty (day, week, month, year, quarter, decade,...) oraz daty zapisane w różnych formatach (zobacz poniżej). Usługa Power BI rozpoznaje również następujące słowa kluczowe: MonthName, Days 1-31, decade. Przykłady: January 3rd of 1995, January 3rd 1995, jan 03 1995, 3 Jan 1995, the 3rd of January, January 1995, 1995 January, 1995-01, 01/1995, nazwy miesięcy         |
|        |         |
|**Daty względne**     |   today, right now, current time, yesterday, tomorrow, the current, next, the coming, last, previous, ago, before now, sooner than, after, later than, from, at, on, from now, after now, in the future, past, last, previous, within, in, over, N days ago, N days from now, next, once, twice.|
|    |  Przykład: count of orders in the past 6 days (liczba zamówień w ciągu ostatnich 6 dni).  |            |
|        |         |
|**Równość (zakres)**     |   in, equal to, =, after, is more than, in, between, before  |
|  |Przykłady: Order year is before 2012? (Rok zamówienia przed rokiem 2012?) Price equals between 10 and 20? (Cena wynosi od 10 do 20?) Is the age of John greater than 40? (Wiek Johna to ponad 40 lat?) Total sales in 200-300? (Łączna sprzedaż w zakresie 200–300?)              |
|        |         |
|**Równość (wartość)**     |   is, equal, equal to, in, of, for, within, is in, is on |
|   | Przykłady: Which products are green? (Które produkty są zielone?) Order date equals 2012. (Data zamówienia równa 2012). Is the age of John 40? (Czy wiek Johna to 40 lat?) Total sales that is not equal to 200? (Łączna sprzedaż, która nie wynosi 200?) Order date of 1/1/2016. (Data zamówienia to 1/1/2016). 10 in price? (Cena zawiera 10?) Green for color? (Zielony w przypadku koloru?) 10 in price? (Cena zawiera 10?)              |
|        |         |
|**Nazwy**     |       Jeśli kolumna w zestawie danych zawiera frazę „name” (np. EmployeeName), funkcja pytań i odpowiedzi rozumie, że wartości w tej kolumnie są nazwami. Możesz zadawać pytania, takie jak „which employees are named robert” (którzy pracownicy nazywają się Robert).          |
|        |         |
**Zaimki**  | he, him, himself, his, she, herself, her, hers, it, itself, its, they, their, them, themselves, theirs, this, these, that, those
|**Polecenia zapytań**     |    sorted, sort by, direction, group, group by, by, show, list, display, give me, name, just, only, arrange, rank, compare, to, with, against, alphabetically, ascending, descending, order             |
|        |         |
|**Zakres**     |      greater, more, larger, above, over, >, less, smaller, fewer, below, under, <, at least, no less than, >=, at most, no more than, <=, in, between, in the range of, from, later, earlier, sooner, after, on, at, later than, after, since, starting with, starting from, ending with           |
|        |         |
**Godziny**  |am, pm, o'clock, noon, midnight, hour, minute, second, hh:mm:ss  |
|  |  Przykłady: 10 pm (22:00), 10:35 pm (22:35), 10:35:15 pm (22:35:15), 10 oclock (dziesiąta), noon (południe), midnight (północ), hour (godzina), minute (minuta), second (sekunda).  |
|  |  |
|**Pierwsze N**     |     (kolejność, klasyfikacja): top, bottom, highest, lowest, first, last, next, earliest, newest, oldest, latest, most recent, next            |
|        |         |
|**Typy wizualizacji**     |  Wszystkie typy wizualizacji natywne dla usługi Power BI.  Jeśli jest to opcja w okienku Wizualizacje, możesz dołączyć ją do pytania.  Wyjątkiem są [niestandardowe wizualizacje](../power-bi-custom-visuals.md) dodane ręcznie do okienka Wizualizacje.  |
|  |  Przykład: show districts by month and sales total as bar chart (pokaż regiony według miesiąca oraz łącznej sprzedaży jako wykres słupkowy)               |
|        |         |
|**Pytania „wh” (relacja, kwalifikowana)**  | when, where, which, who, whom, how many, how much, how many times, how often, how frequently, amount, number, quantity, how long, what                |

## <a name="qa-helps-you-phrase-the-question"></a>Funkcja Pytania i odpowiedzi pomaga w sformułowaniu pytania
Funkcja Pytania i odpowiedzi stara się jak najlepiej zrozumieć zadawane pytania i odpowiadać na nie. Robi to na kilka sposobów. We wszystkich przypadkach możesz zaakceptować działanie w całości, w części lub w ogóle go nie akceptować. Podczas wpisywania pytania funkcja Pytania i odpowiedzi wykonuje następujące działania:

* Automatyczne uzupełnianie słów i pytań. Funkcja używa różnych strategii, w tym automatycznego uzupełniania rozpoznawalnych słów oraz poprzednio używanych pytań, które zwróciły prawidłowe odpowiedzi. Jeśli dostępnych jest kilka opcji automatycznego uzupełniania, są one prezentowane na liście rozwijanej.
* Poprawianie pisowni.
* Wyświetlanie podglądu odpowiedzi w formie wizualizacji. Wizualizacja jest aktualizowana podczas wpisywania i edytowania pytania (funkcja nie czeka na naciśnięcie klawisza Enter).
* Sugerowanie terminów zastępczych ze źródłowych zestawów danych, gdy z powrotem przeniesiesz kursor do pola pytania.
* Ponowne formułowanie pytania w oparciu o dane w źródłowych zestawach danych. Funkcja Pytania i odpowiedzi zastępuje użyte słowa synonimami ze źródłowych zestawów danych. Po przeczytaniu przekształcenia będziesz wiedzieć, czy funkcja Pytania i odpowiedzi zrozumiała Twoje pytanie. 
* Wygasza słowa, których nie rozumie.

## <a name="dont-stop-now"></a>Nie przerywaj
Po wyświetleniu wyników przez funkcję Pytania i odpowiedzi możesz nadal prowadzić konwersację! Skorzystaj z interaktywnych funkcji wizualizacji oraz aparatu Pytania i odpowiedzi, aby odkryć jeszcze więcej szczegółowych informacji.

## <a name="next-steps"></a>Następne kroki
Powrót do [pytań i odpowiedzi w usłudze Power BI](end-user-q-and-a.md)  

[Power BI — podstawowe pojęcia](end-user-basic-concepts.md)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

