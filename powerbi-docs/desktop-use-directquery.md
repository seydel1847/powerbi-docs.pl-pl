---
title: Używanie zapytania bezpośredniego w programie Power BI Desktop
description: Używanie zapytania bezpośredniego, nazywanego również połączeniem na żywo, w programie Power BI Desktop.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7f938e881e71d241025ddc44aeb1a21daa61dcd9
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39327886"
---
# <a name="use-directquery-in-power-bi-desktop"></a>Używanie zapytania bezpośredniego w programie Power BI Desktop
Program **Power BI Desktop** zawsze umożliwia importowanie kopii danych do programu **Power BI Desktop** po połączeniu ze źródłem danych. W przypadku niektórych źródeł danych dostępne jest inne rozwiązanie: połączenie bezpośrednio ze źródłem danych przy użyciu **zapytania bezpośredniego**.

## <a name="supported-data-sources"></a>Obsługiwane źródła danych
Aby zapoznać się z pełną listą źródeł danych, które obsługują tryb **zapytania bezpośredniego**, zapoznaj się z artykułem [Źródła danych obsługiwane przez zapytanie bezpośrednie](desktop-directquery-data-sources.md).

## <a name="how-to-connect-using-directquery"></a>Jak nawiązać połączenie przy użyciu zapytania bezpośredniego
Jeśli do połączenia ze źródłem danych obsługiwanym przez **zapytanie bezpośrednie** używasz funkcji **Pobierz dane**, w oknie połączenia możesz wybrać, w jaki sposób chcesz nawiązać połączenie.  

![](media/desktop-use-directquery/directquery_2a.png)

Różnice pomiędzy opcjami **Import** a **Zapytanie bezpośrednie** są następujące:

**Import** — wybrane tabele i kolumny są importowane do programu **Power BI Desktop**. Podczas tworzenia lub używania wizualizacji program **Power BI Desktop** wykorzystuje zaimportowane dane. Aby wyświetlić zmiany, które zostały wprowadzone do danych bazowych od momentu początkowego zaimportowania lub ostatniego odświeżenia, należy odświeżyć dane, co spowoduje zaimportowanie całego zestawu danych.

**Zapytanie bezpośrednie** — żadne dane nie są importowane ani kopiowane do programu **Power BI Desktop**. W przypadku źródeł relacyjnych na liście **Pola** są wyświetlane wybrane tabele i kolumny. Dla źródeł wielowymiarowych, takich jak system SAP Business Warehouse, na liście **Pola** są wyświetlane wymiary i miary wybranego modułu. Podczas tworzenia lub używania wizualizacji program **Power BI Desktop** wysyła zapytanie do bazowego źródła danych, co oznacza, że zawsze wyświetlane są aktualne dane.

Podczas używania **zapytania bezpośredniego** dostępnych jest wiele modeli i przekształceń danych, jednak z pewnymi ograniczeniami. Podczas tworzenia lub używania wizualizacji do bazowego źródła danych musi zostać wysłane zapytanie, a czas potrzebny na odświeżenie wizualizacji zależy od wydajności bazowego źródła danych. Jeśli dane potrzebne do obsłużenia żądania były żądane niedawno, program Power BI Desktop korzysta z ostatnich danych, aby skrócić czas potrzebny na wyświetlenie wizualizacji. Wybranie opcji **Odśwież** na karcie wstążki **Narzędzia główne** gwarantuje, że wszystkie wizualizacje zostaną odświeżone przy użyciu aktualnych danych.

Artykuł [Usługa Power BI i zapytanie bezpośrednie](desktop-directquery-about.md) opisuje szczegółowo funkcję **zapytania bezpośredniego**. Możesz również zapoznać się z następującymi sekcjami, aby uzyskać więcej informacji na temat korzyści, ograniczeń i kwestii, które należy wziąć pod uwagę w przypadku korzystania z **zapytania bezpośredniego**.

## <a name="benefits-of-using-directquery"></a>Korzyści wynikające z użycia zapytania bezpośredniego
Używanie **zapytania bezpośredniego** ma kilka zalet:

* **Zapytanie bezpośrednie** umożliwia tworzenie wizualizacji na podstawie bardzo dużych zestawów danych, w przypadku których nie można byłoby od razu zaimportować wszystkich danych przy użyciu wstępnego agregowania.
* Zmiany danych bazowych wymagają odświeżenia danych, a w przypadku niektórych raportów wyświetlenie aktualnych danych może wymagać dużych transferów danych, w związku z czym ponowne importowanie danych staje się niepraktyczne. Z kolei raporty **zapytania bezpośredniego** zawsze korzystają z aktualnych danych.
* Ograniczenie rozmiaru zestawu danych do 1 GB *nie dotyczy* **zapytania bezpośredniego**.

## <a name="limitations-of-directquery"></a>Ograniczenia dotyczące zapytania bezpośredniego
Obecnie istnieje kilka ograniczeń związanych z korzystaniem z **zapytania bezpośredniego**:

* Wszystkie tabele muszą pochodzić z jednej bazy danych.
* Jeśli zapytanie **Edytora zapytań** jest zbyt skomplikowane, wystąpi błąd. Aby naprawić ten błąd, należy usunąć problematyczny krok w **Edytorze zapytań** lub *zaimportować* dane zamiast korzystać z **zapytania bezpośredniego**. W przypadku wielowymiarowych źródeł, takich jak system SAP Business Warehouse, nie ma **Edytora zapytań**.
* Filtrowanie relacji działa tylko w jedną stronę, a nie w obie (ale jest możliwe włączenie filtrowania krzyżowego w obu kierunkach w przypadku **zapytania bezpośredniego** w wersji zapoznawczej). W przypadku wielowymiarowych źródeł, takich jak system SAP Business Warehouse, relacje nie są zdefiniowane w modelu.
* W **zapytaniu bezpośrednim** nie są dostępne funkcje analizy czasu. Na przykład szczególne traktowanie kolumn z datą (rok, kwartał, miesiąc, dzień itd.) nie jest obsługiwane w **zapytaniu bezpośrednim**.
* Domyślnie wyrażenia języka DAX dozwolone w miarach są ograniczone. Zapoznaj się z akapitem po liście wypunktowanej, aby uzyskać więcej informacji.
* W przypadku korzystania z **zapytania bezpośredniego** liczba zwracanych wierszy danych jest ograniczona do 1 miliona. Nie ma to wpływu na agregacje lub obliczenia używane do tworzenia zestawów danych zwracanych przy użyciu **zapytania bezpośredniego** — dotyczy tylko zwracanych wierszy. Możesz na przykład zagregować 10 milionów wierszy przy użyciu zapytania korzystającego ze źródła danych i dokładnie zwrócić wyniki agregacji do usługi Power BI przy użyciu **zapytania bezpośredniego**, o ile dane zwrócone do usługi Power BI obejmują mniej niż 1 milion wierszy. Jeśli liczba wierszy do zwrócenia przez **zapytanie bezpośrednie** przekracza 1 milion, usługa Power BI zwróci błąd.

Aby zagwarantować, że zapytania wysyłane do bazowego źródła danych mają akceptowalną wydajność, na miary domyślnie nałożone są ograniczenia. Użytkownicy zaawansowani mogą zdecydować się na obejście tego ograniczenia, wybierając pozycje **Plik > Opcje i ustawienia > Opcje** i **Zapytanie bezpośrednie**, a następnie wybierając pozycję *Zezwalaj na nieograniczone miary w trybie zapytania bezpośredniego*. Gdy ta opcja jest zaznaczona, można użyć dowolnego wyrażenia języka DAX prawidłowego dla miary. Użytkownicy muszą być jednak świadomi, że niektóre wyrażenia, które dobrze działają po zaimportowaniu danych, mogą znacznie spowalniać zapytania do źródła danych zaplecza w trybie zapytania bezpośredniego.

## <a name="important-considerations-when-using-directquery"></a>Istotne zagadnienia dotyczące korzystania z zapytania bezpośredniego
Podczas używania **zapytania bezpośredniego** należy wziąć pod uwagę trzy następujące kwestie:

* **Wydajność i obciążenie** — wszystkie żądania **zapytania bezpośredniego** są wysyłane do źródłowej bazy danych, a więc czas wymagany do odświeżenia wizualizacji zależy od tego, jak szybko źródło danych zaplecza zwróci wyniki zapytania (lub zapytań). Zalecany czas odpowiedzi (zwrócenia żądanych danych) podczas używania **zapytania bezpośredniego** w przypadku wizualizacji wynosi pięć sekund lub mniej. Maksymalny zalecany czas zwracania wyników to 30 sekund. Dłuższy czas wiąże się z nieakceptowalnym pogorszeniem jakości korzystania z tej funkcji przez użytkownika. Ponadto gdy raport zostanie opublikowany w usłudze Power BI, każde zapytanie obsługiwane dłużej niż przez kilka minut przekroczy limit czasu, a użytkownik otrzyma komunikat o błędzie.
  
  Należy również wziąć pod uwagę obciążenie źródłowej bazy danych w zależności od liczby użytkowników usługi Power BI, którzy będą korzystać z opublikowanego raportu. Korzystanie z *zabezpieczeń na poziomie wiersza* może również mieć istotne znaczenie. Jeśli kafelek pulpitu nawigacyjnego bez zabezpieczeń na poziomie wiersza jest współużytkowany przez wielu użytkowników, do bazy danych jest wysyłane jedno zapytanie. Zastosowanie zabezpieczeń na poziomie wiersza do kafelka pulpitu nawigacyjnego zwykle oznacza, że odświeżenie kafelka wymaga wysłania jednego zapytania *na użytkownika*, a więc znacząco zwiększa obciążenie źródłowej bazy danych, co może wpłynąć na wydajność.
  
  Usługa Power BI tworzy możliwie jak najefektywniejsze zapytania. Jednak w pewnych okolicznościach wygenerowane zapytanie może nie być dostatecznie efektywne, aby uniknąć odświeżenia, które może zakończyć się niepowodzeniem. Może się tak zdarzyć, jeśli wygenerowane zapytanie pobiera zbyt dużą liczbę wierszy (ponad 1 milion) ze źródła danych zaplecza. W takim przypadku występuje następujący błąd:
  
      The resultset of a query to external data source has exceeded
      the maximum allowed size of '1000000' rows.
  
  Taka sytuacja może się zdarzyć w przypadku prostego wykresu zawierającego kolumnę o bardzo wysokiej kardynalności z wybraną opcją agregacji *Nie sumuj*. Wizualizacja musi zawierać wyłącznie kolumny z kardynalnością poniżej 1 miliona lub mieć zastosowane odpowiednie filtry.
* **Zabezpieczenia** — wszyscy użytkownicy, którzy korzystają z opublikowanego raportu, łączą się ze źródłem danych zaplecza, korzystając z poświadczeń wprowadzonych po publikacji w usłudze Power BI. Jest to taka sama sytuacja, jak w przypadku zaimportowanych danych: wszyscy użytkownicy zobaczą takie same dane, bez względu na reguły zabezpieczeń zdefiniowane w źródle zaplecza. Klienci, którzy chcą zaimplementować zabezpieczenia na poziomie użytkownika ze źródłami zapytania bezpośredniego, powinni korzystać z zabezpieczeń na poziomie wiersza. [Dowiedz się więcej na temat zabezpieczeń na poziomie wiersza](service-admin-rls.md).
* **Obsługiwane funkcje** — niektóre funkcje programu **Power BI Desktop** nie są obsługiwane w trybie **zapytania bezpośredniego** lub mają pewne ograniczenia. Ponadto istnieją pewne funkcje usługi Power BI (takie jak *szybki wgląd*), które nie są dostępne dla zestawów danych korzystających z **zapytania bezpośredniego**. Dlatego podczas decydowania, czy korzystać z **zapytania bezpośredniego**, należy wziąć pod uwagę ograniczenia funkcji związane z korzystaniem z **zapytania bezpośredniego**.   

## <a name="publish-to-the-power-bi-service"></a>Publikowanie w usłudze Power BI
Raporty utworzone przy użyciu **zapytania bezpośredniego** można publikować w usłudze Power BI.

Jeśli użyte źródło danych nie wymaga **lokalnej bramy danych** (**Azure SQL Database**, **Azure SQL Data Warehouse** lub **Redshift**), należy wprowadzić poświadczenia przed wyświetleniem raportu w usłudze Power BI.

Możesz wprowadzić poświadczenia, wybierając ikonę koła zębatego **Ustawienia** w usłudze Power BI, a następnie wybierając pozycję **Ustawienia**.

![](media/desktop-use-directquery/directquery_3.png)

W usłudze Power BI zostanie wyświetlone okno **Ustawienia**. W tym oknie wybierz kartę **Zestawy danych**, a następnie wybierz zestaw danych, który korzysta z **zapytania bezpośredniego**, i wybierz pozycję **Edytuj poświadczenia**.

![](media/desktop-use-directquery/directquery_4.png)

Dopóki poświadczenia nie zostaną wprowadzone, otwarcie opublikowanego raportu lub eksplorowanie zestawu danych utworzonego za pomocą połączenia **zapytania bezpośredniego** z takimi źródłami danych będzie skutkowało błędem.

W przypadku źródeł danych innych niż **Azure SQL Database**, **Azure SQL Data Warehouse** oraz **Redshift**, które korzystają z zapytania bezpośredniego, należy zainstalować **lokalną bramę danych** w celu nawiązania połączenia danych. Możesz [dowiedzieć się więcej na temat lokalnej bramy danych](http://go.microsoft.com/fwlink/p/?LinkID=627094).

## <a name="next-steps"></a>Następne kroki
Aby uzyskać więcej informacji na temat **zapytania bezpośredniego**, zapoznaj się z następującymi zasobami:

* [Zapytanie bezpośrednie w usłudze Power BI](desktop-directquery-about.md)
* [Źródła danych obsługiwane przez zapytanie bezpośrednie](desktop-directquery-data-sources.md)
* [Zapytanie bezpośrednie i system SAP BW](desktop-directquery-sap-bw.md)
* [Zapytanie bezpośrednie i platforma SAP HANA](desktop-directquery-sap-hana.md)
* [Lokalna brama danych](service-gateway-onprem.md)

