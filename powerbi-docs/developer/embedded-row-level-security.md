---
title: "Używanie zabezpieczeń na poziomie wiersza w osadzonej zawartości usługi Power BI"
description: "Poznaj więcej informacji na temat kroków, które musisz wykonać, aby osadzić zawartość usługi Power BI w aplikacji."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 12/21/2017
ms.author: asaxton
ms.openlocfilehash: 491be8983967b1a5dce6579411f194117602b00c
ms.sourcegitcommit: 70e9239e375ae03744fb9bc122d5fc029fb83469
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="use-row-level-security-with-power-bi-embedded-content"></a>Używanie zabezpieczeń na poziomie wiersza w osadzonej zawartości usługi Power BI
Zabezpieczenia na poziomie wiersza (kontrola dostępu) mogą służyć do ograniczania dostępu użytkowników do danych w ramach pulpitów nawigacyjnych, kafelków, raportów i zestawów danych. Wielu różnych użytkowników może pracować z tymi samymi artefaktami, widząc różne dane. Funkcja osadzania obsługuje zabezpieczenia na poziomie wiersza.

Jeśli osadzasz zawartość dla użytkowników innych niż użytkownicy usługi Power BI (aplikacja jest właścicielem danych), co jest typowe w przypadku niezależnych dostawców oprogramowania, ten artykuł jest dla Ciebie. Musisz skonfigurować token osadzania do konta dla użytkownika i roli. Czytaj dalej, aby dowiedzieć się, jak to zrobić.

Jeśli osadzasz zawartość dla użytkowników usługi Power BI (użytkownik jest właścicielem danych) w organizacji, zabezpieczenia RLS działają w taki sam sposób jak bezpośrednio w usłudze Power BI. Nie musisz już nic robić w aplikacji. Aby uzyskać więcej informacji, zobacz [Zabezpieczenia na poziomie wiersza w usłudze Power BI](../service-admin-rls.md).

![Elementy związane z zabezpieczeniami na poziomie wiersza.](media/embedded-row-level-security/powerbi-embedded-rls-components.png)

Aby móc korzystać z zabezpieczeń RLS, ważne jest zrozumienie trzech głównych pojęć: użytkowników, ról i reguł. Przyjrzyjmy się im bliżej:

**Użytkownicy** — użytkownicy końcowi wyświetlający artefakt (pulpit nawigacyjny, kafelek, raport lub zestaw danych). W usłudze Power BI Embedded użytkownicy są identyfikowani przy użyciu właściwości nazwy użytkownika w tokenie osadzania.

**Role** — użytkownicy należą do ról. Rola to kontener reguł. Może mieć nazwę podobną do następujących: *Menedżer sprzedaży* lub *Przedstawiciel handlowy*. Możesz utworzyć role w programie Power BI Desktop. Aby uzyskać więcej informacji, zobacz [Zabezpieczenia na poziomie wiersza w programie Power BI Desktop](../desktop-rls.md).

**Reguły** — role mają reguły, czyli faktyczne filtry, które zostaną zastosowane wobec danych. Mogą być bardzo proste, np. „Kraj = USA”, lub dużo bardziej dynamiczne.
W pozostałej części tego artykułu przedstawimy przykład tworzenia zabezpieczeń RLS, a następnie wykorzystywania ich w osadzonej aplikacji. Przedstawiony przykład korzysta z pliku PBIX [Retail Analysis Sample](http://go.microsoft.com/fwlink/?LinkID=780547).

![Przykład raportu](media/embedded-row-level-security/powerbi-embedded-report-example.png)

## <a name="adding-roles-with-power-bi-desktop"></a>Dodawanie ról przy użyciu programu Power BI Desktop
Przykładowe dane dotyczące analizy handlu detalicznego przedstawiają sprzedaż dla wszystkich sklepów w łańcuchu dostaw. Bez zabezpieczeń na poziomie wiersza każdy menedżer regionalny po zalogowaniu i wyświetleniu raportu zobaczy takie same dane. Na wyższym szczeblu kierowniczym zdecydowano, że każdy menedżer regionalny powinien widzieć tylko sprzedaż dotyczącą sklepów, którymi zarządza. Aby to osiągnąć, możemy użyć zabezpieczeń na poziomie wiersza.

Zabezpieczenia na poziomie wiersza są tworzone w programie Power BI Desktop. Po otwarciu zestawu danych i raportu możemy przełączyć się na widok diagramu, aby wyświetlić schemat:

![Widok diagramu w programie Power BI Desktop](media/embedded-row-level-security/powerbi-embedded-schema.png)

Poniżej przedstawiono kilka istotnych kwestii dotyczących tego schematu:

* Wszystkie miary, takie jak **Total Sales** (sprzedaż łącznie), są przechowywane w tabeli faktów **Sales** (sprzedaż).
* Istnieją cztery dodatkowe powiązane tabele wymiarów: **Item** (element), **Time** (czas), **Store** (sklep) i **District** (region).
* Strzałki w liniach relacji wskazują, w którą stronę filtry mogą przepływać z jednej tabeli do innej. Jeśli na przykład filtr zostanie umieszczony w pozycji **Time[Date]** w bieżącym schemacie będzie filtrować wyłącznie wartości w tabeli **Sales**. Ten filtr nie będzie mieć wpływu na żadne inne tabele, ponieważ wszystkie strzałki w liniach relacji są skierowane do tabeli sprzedaży, a nie od niej.
* Tabela **District** wskazuje menedżera każdego regionu:
  
    ![Wiersze w tabeli District](media/embedded-row-level-security/powerbi-embedded-district-table.png)

Jeśli zastosujemy filtr, na podstawie tego schematu, do kolumny **District Manager** w tabeli **District** oraz jeśli ten filtr będzie zgodny z użytkownikiem wyświetlającym raport, będzie również odfiltrowywać tabele **Store** i **Sales** tak, aby pokazywać dane tylko dla tego menedżera regionalnego.

Oto kroki tej procedury:

1. Na karcie **Modelowanie** wybierz pozycję **Zarządzaj rolami**.
   
    ![Karta Modelowanie w programie Power BI Desktop](media/embedded-row-level-security/powerbi-embedded-manage-roles.png)
2. Utwórz nową rolę o nazwie **Menedżer**.
   
    ![Tworzenie nowej roli](media/embedded-row-level-security/powerbi-embedded-new-role.png)
3. W tabeli **District** wprowadź następujące wyrażenie DAX: **[District Manager] = USERNAME()**.
   
    ![Instrukcje języka DAX na potrzeby reguły zabezpieczeń RLS](media/embedded-row-level-security/powerbi-embedded-new-role-dax.png)
4. Aby upewnić się, że reguły działają, na karcie **Modelowanie** wybierz opcję **Wyświetl jako role**, a następnie wybierz utworzoną rolę **Menedżer** oraz rolę **Inny użytkownik**. Wprowadź **Andrew Ma** w polu użytkownika.
   
    ![Okno dialogowe wyświetlania jako roli](media/embedded-row-level-security/powerbi-embedded-new-role-view.png)
   
    Raporty będą teraz pokazywać dane tak, jak w przypadku zalogowania użytkownika **Andrew Ma**.

Takie zastosowanie filtru spowoduje odfiltrowanie wszystkich rekordów w tabelach **District**, **Store** i **Sales**. Jednak ze względu na kierunek filtrowania w relacjach między tabelami **Sales** i **Time** oraz **Sales** i **Item** tabele **Item** i **Time** nie zostaną odfiltrowane. Aby dowiedzieć się więcej o dwukierunkowym filtrowaniu krzyżowym, pobierz oficjalny dokument [Bidirectional cross-filtering in SQL Server Analysis Services 2016 and Power BI Desktop (Dwukierunkowe filtrowanie krzyżowe w usługach SQL Server Analysis Services 2016 oraz programie Power BI Desktop)](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx).

## <a name="applying-user-and-role-to-an-embed-token"></a>Stosowanie użytkownika i roli do tokenu osadzania
Teraz po skonfigurowaniu ról programu Power BI Desktop należy wykonać pewne operacje w aplikacji, aby skorzystać z ról.

Użytkownicy są uwierzytelniani i autoryzowani przez aplikację, a tokeny osadzania są używane do udzielania użytkownikom dostępu do konkretnego raportu usługi Power BI Embedded. Usługa Power BI Embedded nie ma żadnych konkretnych informacji o tym, kim jest użytkownik. Aby zabezpieczenia na poziomie wiersza mogły zadziałać, musisz przekazać dodatkowy kontekst w ramach tokenu osadzania w formie tożsamości. Wykonuje się to przy użyciu interfejsu API [GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx).

Interfejs API [GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx) akceptuje listę tożsamości ze wskazaniem odpowiednich zestawów danych. Aby zabezpieczenia na poziomie wiersza mogły zadziałać, musisz przekazać następujące informacje jako część tożsamości.

* **Nazwa użytkownika (obowiązkowe)** — jest to ciąg, którego można użyć do zidentyfikowania użytkownika podczas stosowania reguł zabezpieczeń na poziomie wiersza. Można wymienić na liście tylko jednego użytkownika.
* **Role (obowiązkowe)** — ciąg zawierający role do wybrania podczas stosowania reguł zabezpieczeń na poziomie wiersza. W przypadku przekazywania więcej niż jednej roli należy je przekazywać jako tablicę ciągów.
* **Zestaw danych (obowiązkowe)** — zestaw danych, który ma zastosowanie do osadzanego artefaktu. 

Możesz utworzyć token osadzania przy użyciu metody **GenerateTokenInGroup** w obszarze **PowerBIClient.Reports**. Obecnie obsługiwane są wyłącznie raporty.

Przykładowo możesz zmienić przykład [PowerBIEmbedded_AppOwnsData](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data). *Wiersz 76 i 77 pliku Home\HomeController.cs* można zaktualizować z:

```
// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync(GroupId, report.Id, generateTokenRequestParameters);
```

do

```
var generateTokenRequestParameters = new GenerateTokenRequest("View", null, identities: new List<EffectiveIdentity> { new EffectiveIdentity(username: "username", roles: new List<string> { "roleA", "roleB" }, datasets: new List<string> { "datasetId" }) });

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync("groupId", "reportId", generateTokenRequestParameters);
```

W przypadku wywoływania interfejsu API REST zaktualizowany interfejs API będzie teraz akceptować dodatkową tablicę JSON o nazwie **identities**, która zawiera nazwę użytkownika, listę ról w postaci ciągu oraz listę zestawów danych w postaci ciągu, np.:

```
{
    "accessLevel": "View",
    "identities": [
        {
            "username": "EffectiveIdentity",
            "roles": [ "Role1", "Role2" ],
            "datasets": [ "fe0a1aeb-f6a4-4b27-a2d3-b5df3bb28bdc" ]
        }
    ]
}
```

Teraz po zebraniu wszystkich elementów, gdy ktoś zaloguje się do aplikacji w celu wyświetlenia tego artefaktu, będzie w stanie zobaczyć tylko te dane, do których ma dostęp — zgodnie z ustawieniami zabezpieczeń na poziomie wiersza.

## <a name="working-with-analysis-services-live-connections"></a>Praca z połączeniami na żywo usług Analysis Services
Zabezpieczeń na poziomie wiersza można użyć z połączeniami na żywo usług Analysis Services w przypadku serwerów lokalnych. Istnieje kilka podstawowych koncepcji, które należy zrozumieć w przypadku stosowania tego typu połączenia.

Efektywną tożsamością zapewnioną dla właściwości nazwy użytkownika musi być użytkownik systemu Windows z uprawnieniami na serwerze usług Analysis Services.

**Konfiguracja lokalnej bramy danych**

[Lokalnej bramy danych](../service-gateway-onprem.md) używa się podczas pracy z połączeniami na żywo usług Analysis Services. Podczas generowania tokenu osadzania z tożsamością na liście konto główne musi być wymienione na liście jako administrator bramy. Jeśli konto główne nie jest wymienione na liście, zabezpieczenia na poziomie wiersza nie będą właściwością stosowaną wobec danych. Użytkownik inny niż administrator bramy może zapewnić role, ale musi określić własną nazwę użytkownika na potrzeby efektywnej tożsamości.

**Używanie ról**

Role można przekazać wraz z tożsamością w tokenie osadzania. Jeśli żadna rola nie zostanie wybrana, podana nazwa użytkownika będzie używana do rozpoznawania skojarzonych ról.

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia
* Przypisywanie użytkowników do ról w usłudze Power BI nie wpływa na zabezpieczenia na poziomie wiersza podczas używania tokenu osadzania.
* Usługa Power nie będzie stosować ustawień zabezpieczeń na poziomie wiersza do administratorów lub członków z uprawnieniami do edycji podczas podawania tożsamości wraz z tokenem osadzania, ale będzie stosować je wobec danych.
* Połączenia na żywo usług Analysis Services są obsługiwane w przypadku serwerów lokalnych.
* Połączenia na żywo usług Azure Analysis Services obsługują filtrowanie według ról, ale nie dynamicznie według nazwy użytkownika.
* Jeśli źródłowy zestaw danych nie wymaga zabezpieczeń RLS, żądanie GenerateToken **nie** może zawierać efektywnej tożsamości.
* Jeśli źródłowy zestaw danych jest modelem w chmurze (modelem w pamięci podręcznej lub zapytaniem bezpośrednim), efektywna tożsamość musi zawierać co najmniej jedną rolę. W przeciwnym razie rola nie zostanie przypisana.
* Lista tożsamości może zawierać wiele tokenów tożsamości na potrzeby osadzania pulpitu nawigacyjnego. Dla wszystkich innych artefaktów lista zawiera jedną tożsamość.

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

