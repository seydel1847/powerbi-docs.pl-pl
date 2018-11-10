---
title: Eksportowanie raportów z usługi Power BI do programu PowerPoint
description: Dowiedz się, jak wyeksportować raport usługi Power BI do programu PowerPoint.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Share your work
ms.openlocfilehash: 661d615ed33b12ae0557fd8feaa0bc47b3a6638f
ms.sourcegitcommit: ac63e6a082ca8397909217837e8d98c9389b23ac
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2018
ms.locfileid: "50736946"
---
# <a name="export-reports-from-power-bi-to-powerpoint"></a>Eksportowanie raportów z usługi Power BI do programu PowerPoint
Usługa Power BI umożliwia teraz publikowanie raportów w programie **Microsoft PowerPoint** oraz łatwe tworzenie pokazu slajdów na podstawie raportu usługi Power BI. Podczas **eksportowania do programu PowerPoint** zachodzą następujące zmiany:

* Każda strona w raporcie usługi Power BI staje się pojedynczym slajdem w programie PowerPoint
* Każda strona w raporcie usługi Power BI jest eksportowana jako jeden obraz o wysokiej rozdzielczości w programie PowerPoint
* Pola tekstowe w raporcie usługi Power BI stają się edytowalnymi polami tekstowymi w programie PowerPoint
* W programie PowerPoint jest tworzony link prowadzący do raportu usługi Power BI

Eksportowanie **raportu usługi Power BI** do programu **PowerPoint** jest łatwe. Wystarczy wykonać kroki opisane w następnej sekcji.

## <a name="how-to-export-your-power-bi-report-to-powerpoint"></a>Jak wyeksportować raport usługi Power BI do programu PowerPoint
W usłudze Power BI wybierz sekcję **Raporty** w okienku nawigacji po lewej stronie, aby ją rozwinąć, a następnie wybierz odpowiedni raport, aby wyświetlić go na kanwie. Raport możesz także wybrać w sekcji **Mój obszar roboczy** lub **Ulubione**, jeśli znajduje się on w którejś z tych lokalizacji.

![](media/end-user-powerpoint/powerbi_to_powerpoint_0.png)

Gdy raport, który chcesz wyeksportować do programu PowerPoint, zostanie wyświetlany na kanwie, wybierz pozycję **Plik > Eksportuj do programu PowerPoint (wersja zapoznawcza)** na pasku menu w usłudze Power BI, jak pokazano na poniższej ilustracji.

![](media/end-user-powerpoint/powerbi_to_powerpoint_1.png)

W prawym górnym rogu okna przeglądarki usługi Power BI zostanie wyświetlony transparent powiadomienia z informacją, że raport jest eksportowany do programu PowerPoint. Może to potrwać kilka minut. Podczas eksportowania raportu możesz kontynuować pracę w usłudze Power BI.

![](media/end-user-powerpoint/powerbi_to_powerpoint_2.png)

Po zakończeniu na transparencie powiadomienia zostanie wyświetlona informacja, że usługa Power BI zakończyła proces eksportowania.

![](media/end-user-powerpoint/powerbi_to_powerpoint_3.png)

Plik będzie dostępny w miejscu, gdzie przeglądarka wyświetla pobrane pliki. Na poniższej ilustracji widać transparent pobierania wzdłuż dolnej części okna przeglądarki.

![](media/end-user-powerpoint/powerbi_to_powerpoint_4.png)

To wszystko. Teraz możesz pobrać ten plik, otworzyć go za pomocą programu PowerPoint, a następnie modyfikować go i ulepszać, tak jak każdą inną prezentację programu PowerPoint.

## <a name="checking-out-your-exported-powerpoint-file"></a>Sprawdzanie wyeksportowanego pliku programu PowerPoint
Po otworzeniu pliku programu PowerPoint wyeksportowanego przez usługę Power BI znajdziesz w nim kilka fajnych i przydatnych elementów. Przyjrzyj się poniższej ilustracji, a następnie zapoznaj się z ponumerowanymi elementami poniżej, opisującymi niektóre z tych użytecznych funkcji.

![](media/end-user-powerpoint/powerbi_to_powerpoint_5.png)

1. Pierwsza strona pokazu slajdów zawiera nazwę raportu oraz link umożliwiający **wyświetlenie w usłudze Power BI** raportu, na którym oparto ten pokaz slajdów.
2. Widoczne są także pewne przydatne informacje dotyczące raportu, takie jak *ostatnie odświeżanie danych*, na których oparty jest wyeksportowany raport, oraz data i godzina *pobrania*, czyli data i godzina wyeksportowania raportu usługi Power BI do pliku programu PowerPoint.
3. Każda strona raportu jest osobnym slajdem, jak pokazano w okienku nawigacji po lewej stronie.
4. Opublikowany raport jest renderowany w języku zgodnym z ustawieniami usługi Power BI lub ustawieniami regionalnymi przeglądarki. Aby zobaczyć preferencję języka, wybierz ikonę z kołem zębatym ![](./media/end-user-powerpoint/power-bi-settings-icon.png) **> Ustawienia > Ogólne > Język**. Informacje dotyczące ustawień regionalnych znajdują się w temacie [Języki i kraje/regiony obsługiwane w usłudze Power BI](../supported-languages-countries-regions.md).
5. Prezentacja programu PowerPoint zawiera slajd tytułowy z wyeksportowaną godziną w prawidłowej strefie czasowej.

Gdy przejdziesz do pojedynczego slajdu, zauważysz, że każda strona raportu jest niezależnym obrazem.

>[!NOTE]
> Zastosowanie jednej wizualizacji dla każdej strony raportu to nowe zachowanie. Poprzednie zachowanie, które udostępniało niezależny obraz dla każdej wizualizacji, nie jest już zaimplementowane. 
 

![](media/end-user-powerpoint/powerbi_to_powerpoint_6.png)

To, co teraz zrobisz z pokazem slajdów programu PowerPoint, lub z dowolnym obrazem o wysokiej rozdzielczości, zależy wyłącznie od Ciebie!

## <a name="limitations"></a>Ograniczenia
Pracując z funkcją **Eksportuj do programu PowerPoint**, należy wziąć pod uwagę kilka zagadnień i ograniczeń.

* **Wizualizacje języka R** nie są obecnie obsługiwane. Każda taka wizualizacja jest eksportowana do programu PowerPoint jako pusty obraz z komunikatem o błędzie informującym, że wizualizacja nie jest obsługiwana.
* **Wizualizacje niestandardowe**, które posiadają **certyfikat**, są obsługiwane. Aby uzyskać więcej informacji na temat certyfikowanych wizualizacji niestandardowych, w tym jak uzyskać certyfikat dla wizualizacji niestandardowej, zobacz [Certyfikowanie wizualizacji niestandardowej](../power-bi-custom-visuals-certified.md). Wizualizacje niestandardowe, które nie mają certyfikatu, nie są obsługiwane i są eksportowane do programu PowerPoint jako puste obrazy z komunikatem o błędzie informującym, że wizualizacja nie jest obsługiwana.
* **Certyfikowane wizualizacje niestandardowe** są obsługiwane. Certyfikowana wizualizacja niestandardowa została zatwierdzona do używania z usługą Power BI, spełnia określone wymagania dotyczące kodu i przeszła restrykcyjne testy bezpieczeństwa. Możesz [dowiedzieć się więcej o **certyfikowanych wizualizacjach niestandardowych**](../power-bi-custom-visuals-certified.md).
* Obecnie nie można eksportować raportów zawierających więcej niż 30 stron.
* Proces eksportowania raportu do programu PowerPoint może potrwać kilka minut, dlatego prosimy o cierpliwość. Czynniki, które mogą mieć wpływ na czas eksportowania, obejmują strukturę raportu oraz bieżące obciążenie usługi Power BI.
* Jeśli element menu **Eksportuj do programu PowerPoint** nie jest dostępny w usłudze Power BI, prawdopodobnie administrator dzierżawy wyłączył tę funkcję. Aby uzyskać więcej informacji, skontaktuj się z administratorem dzierżawy.
* Obrazy tła zostaną przycięte do obszaru ograniczającego wykres. Zdecydowanie zalecamy, aby usunąć obrazy tła przed rozpoczęciem eksportowania do programu PowerPoint.
* **Interakcyjność podczas sesji**, taka jak wyróżnianie i filtrowanie, przechodzenie do szczegółów i inne funkcje, nie jest na razie obsługiwana podczas eksportowania do programu PowerPoint. Wyeksportowany plik programu PowerPoint pokazuje oryginalne wizualizacje tak, jak zostały zapisane w raporcie.
* Strony w programie PowerPoint są zawsze tworzone w standardowym rozmiarze 9:16, niezależnie od oryginalnych wymiarów i rozmiarów stron w raporcie usługi Power BI.
* Raporty, które są własnością użytkownika spoza Twojej domeny dzierżawy usługi Power BI (na przykład raporty należące do osoby spoza organizacji i udostępnione Tobie), nie mogą być publikowane w programie PowerPoint.
* Jeśli udostępniasz pulpit nawigacyjny osobie spoza organizacji (czyli użytkownikowi, który nie należy do Twojej dzierżawy usługi Power BI), ta osoba nie będzie mogła wyeksportować raportów skojarzonych z udostępnionym pulpitem nawigacyjnym do programu PowerPoint. Jeśli na przykład jesteś użytkownikiem aaron@contoso.com, możesz udostępnić pulpit nawigacyjny użytkownikowi david@cohowinery.com. Ale użytkownik david@cohowinery.com nie może wyeksportować skojarzonych raportów do programu PowerPoint.
* Jak wspomniano wcześniej, każda strona raportu jest eksportowana jako jeden obraz w pliku programu PowerPoint.
* Usługa Power BI używa ustawień języka użytkownika usługi Power BI jako języka eksportu do programu PowerPoint. Aby zobaczyć preferencję języka, wybierz ikonę z kołem zębatym ![](./media/end-user-powerpoint/power-bi-settings-icon.png) **> Ustawienia > Ogólne > Język**.
* Czas **Pobrano** na slajdzie okładki wyeksportowanego pliku programu PowerPoint jest ustawiony na strefę czasową komputera obowiązującą w czasie eksportu.

## <a name="next-steps"></a>Następne kroki
[Analizowanie w programie Excel](../service-analyze-in-excel.md)

[Dane programu Excel w usłudze Power BI](../service-excel-workbook-files.md)

[Certyfikowanie wizualizacji niestandardowej](../power-bi-custom-visuals-certified.md)

