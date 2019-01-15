---
title: Aktywowanie Cortany dla usługi Power BI
description: Uzyskuj odpowiedzi na podstawie swoich danych dzięki Cortanie i usłudze Power BI. Uaktywnij Cortanę dla każdego zestawu danych usługi Power BI, a następnie włącz Cortanę, aby uzyskać dostęp do swoich zestawów danych z urządzeń z systemem Windows.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/20/2017
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 130c18bb51c99813999f87c69c465dc59783e638
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54276726"
---
# <a name="enable-cortana-to-access-power-bi-reports-and-their-underlying-datasets"></a>Włączanie Cortany, aby uzyskać dostęp do raportów usługi Power BI (i ich źródłowych zestawów danych)
Znasz już [Wprowadzenie do Cortany i usługi Power BI](service-cortana-intro.md) (jeśli jeszcze tego nie znasz, może warto w pierwszej kolejności to przeczytać, a dopiero potem wrócić). A teraz chcesz wypróbować jej możliwości samodzielnie.  Zanim będzie można zadawać Cortanie pytania języka naturalnego i znajdować odpowiedzi w danych przechowywanych w ***raportach*** usługi Power BI, trzeba będzie spełnić kilka wymagań. W szczególności należy wykonać następujące czynności.

> [!NOTE]
> Jeśli sprawdzasz wersję zapoznawczą Cortany i ***pulpitu nawigacyjnego*** usługi Power BI, możesz pominąć resztę tego artykułu. Nie ma wymagań dotyczących instalacji dla Cortany, aby mogła wyszukiwać pulpity nawigacyjne usługi Power BI.
> 
> 

W usłudze Power BI

* włącz co najmniej jeden zestaw danych dla Cortany (raporty są tworzone na bazie zestawów danych, więc Cortana musi mieć dostęp do tych zestawów danych)

W systemie Microsoft Windows

* Sprawdź, czy korzystasz z systemu Windows 10 w wersji 1511 lub nowszej
* Upewnij się, że usługa Power BI i system Windows mogą „rozmawiać” ze sobą. Oznacza to połączenie Twojego konta z systemem Windows.

## <a name="use-power-bi-service-to-enable-cortana-to-access-report-pages-in-power-bi"></a>Używanie usługi Power BI, aby umożliwić Cortanie dostęp do stron raportu w usłudze Power BI
Umożliwienie Cortanie dostępu do raportów w usłudze Power BI jest prostym procesem.  Rzeczywiście, wszystkim, co należy zrobić, jest włączenie źródłowego zestawu danych raportu, wybierając opcję „Zezwól Cortanie na dostęp do tego zestawu danych”. Następnie każdy użytkownik mający dostęp do zestawu danych w usłudze Power BI za pomocą normalnego udostępniania usługi Power BI, aplikacji i funkcji pakietu zawartości, będzie mógł uzyskać odpowiedzi z raportu w Cortanie w systemie Windows 10.

Musisz zalogować się do usługi Power BI (nie do programu Power BI Desktop) i powtórzyć te kroki dla każdego zestawu danych, do którego chcesz Cortanie umożliwić dostęp.

1. Określ, które zestawy danych udostępnić. Z listy zawartości raportu wybierz raport, do którego Cortana ma mieć dostęp, i wybierz ikonę **Wyświetl powiązane** ![](media/service-cortana-enable/power-bi-cortana-view-related-icon.png) .
   
    ![Wyświetlanie powiązanej zawartości](media/service-cortana-enable/power-bi-view-related.png)
2. Zestawem danych skojarzonym z tym raportem jest **Sprzedaż firmy Contoso**.
   
    ![Zestaw danych sprzedaży firmy Contoso](media/service-cortana-enable/power-bi-identify-dataset.png)
3. Po prawej stronie nazwy zestawu danych wybierz pozycję **wielokropek (...) > Ustawienia**.  
   
    ![Wybierz Ustawienia](media/service-cortana-enable/power-bi-settings-cortana.png)
4. Wybierz pozycję **Pytania i odpowiedzi i Cortana** > **Zezwalaj Cortanie na dostęp do tego zestawu danych** > **Zastosuj**.
   
   ![Cortana uzyskuje dostęp do zestawu danych](media/service-cortana-enable/power-bi-cortana-enable-new.png)
   
   W tym przykładzie udostępniamy Cortanie zestaw danych o sprzedaży firmy Contoso.
   
   > [!NOTE]
   > Gdy nowy zestaw danych lub karta odpowiedzi Cortany zostaną dodane do usługi Power BI i udostępnione Cortanie, oczekiwanie na pojawienie się wyników może potrwać do 30 minut. Wylogowanie się i ponowne zalogowanie w systemie Windows 10 lub ponowne uruchomienie procesu Cortany w systemie Windows 10 w inny sposób spowoduje natychmiastowe wyświetlenie nowej zawartości.
   > 
   > Jeśli udostępnisz zestaw danych Cortanie i ten zestaw danych jest częścią należącego do Ciebie pakietu zawartości lub aplikacji, trzeba będzie ponownie go opublikować dla współpracowników, aby również oni mogli korzystać z niego za pomocą Cortany.
   > 
   > 

## <a name="add-your-power-bi-credentials-to-windows"></a>Dodawanie poświadczeń usługi Power BI do systemu Windows
Musisz mieć uruchomiony system Windows 10 w wersji 1511 lub nowszej.

1. Określ, która wersja systemu Windows 10 jest uruchomiona. Otwórz pozycję **Ustawienia**.
    ![Otwieranie ustawień systemu Windows](media/service-cortana-enable/power-bi-cortana-windows.png)

    Następnie wybierz pozycję **System > Informacje**. W dolnej części ekranu zobaczysz pozycje **Specyfikacja systemu Windows > Wersja**

   * Jeśli masz system Windows 10 w wersji od 1511 (aktualizacja systemu Windows z 10 listopada 2015 r.) do 1607, dodaj swoje konto służbowe i konto Microsoft (wykonaj kroki 2 i 3 poniżej).
   * Jeśli masz system Windows 10 w wersji 1607 (aktualizacja systemu Windows z 10 lipca 2016 r.) lub nowszej, dodaj konto służbowe (wykonaj tylko krok 2 poniżej).
1. Dodaj swoje konto służbowe dla Cortany.
   
   * Otwórz pozycje **Ustawienia** > **Konta**.
     
       ![Ustawienia — Konta](media/service-cortana-enable/power-bi-windows-accounts.png)
   * Przewiń do dołu i wybierz pozycję **Dodaj konto służbowe**. Lub na stronie **Konta** wybierz pozycję **Uzyskaj dostęp do miejsca pracy lub nauki > Połącz**.
     
     ![Dodawanie konta służbowego](media/service-cortana-enable/power-bi-add-work-account2.png)

Cortana będzie używać tego konta służbowego do sprawdzania usługi Power BI pod kątem potencjalnych odpowiedzi na pytania w Cortanie.

## <a name="next-steps"></a>Następne kroki
[Tworzenie *kart odpowiedzi* Cortany w usłudze Power BI](service-cortana-answer-cards.md)

[Rozwiązywanie problemów integracji Cortany i usługi Power BI](service-cortana-troubleshoot.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

