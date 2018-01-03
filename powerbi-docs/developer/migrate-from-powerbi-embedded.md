---
title: "Jak migrować zawartość kolekcji obszarów roboczych usługi Power BI Embedded do usługi Power BI"
description: "Dowiedz się, jak przeprowadzić migrację z usługi Power BI Embedded do usługi Power BI i uzyskać korzyści związane z osadzaniem zawartości w aplikacjach."
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
ms.date: 07/21/2017
ms.author: asaxton
ms.openlocfilehash: 430f1d1a49e510bac66c448b2dceaad1f2537073
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-migrate-power-bi-embedded-workspace-collection-content-to-power-bi"></a>Jak migrować zawartość kolekcji obszarów roboczych usługi Power BI Embedded do usługi Power BI
Dowiedz się, jak przeprowadzić migrację z usługi Power BI Embedded do usługi Power BI i uzyskać korzyści związane z osadzaniem zawartości w aplikacjach.

Firma Microsoft niedawno [ogłosiła udostępnienie usługi Power BI Premium](https://powerbi.microsoft.com/blog/microsoft-accelerates-modern-bi-adoption-with-power-bi-premium/), czyli nowego modelu licencjonowania opartego na pojemnościach, zwiększającego elastyczność uzyskiwania dostępu do zawartości, jej udostępniania i dystrybuowania przez użytkowników. Ta oferta zwiększa również wydajność i skalowalność usługi Power BI.

W związku z wprowadzeniem usługi Power BI Premium usługi Power BI Embedded i Power BI łączą się, oferując bardziej zaawansowany sposób osadzania zawartości usługi Power BI w aplikacjach. Oznacza to wspólne środowisko interfejsów API, spójny zestaw funkcji oraz dostęp do najnowszych elementów usługi Power BI — takich jak pulpity nawigacyjne, bramy i obszary robocze aplikacji — podczas osadzania zawartości. Od teraz będzie można rozpocząć pracę z programem Power BI Desktop, a następnie przejść do wdrożenia przy użyciu usługi Power BI Premium, która zostanie ogólnie udostępniona w drugim kwartale 2017 r.

Usługa Power BI Embedded w bieżącej formie będzie dostępna przez ograniczony czas po ogólnym udostępnieniu oferty połączonej: klienci objęci umową Enterprise Agreement będą mieli do niej dostęp do czasu wygaśnięcia aktualnych umów; klienci, którzy uzyskali usługę Power BI Embedded bezpośrednio lub za pośrednictwem partnera CSP, zachowają dostęp przez rok od daty ogólnej dostępności usługi Power BI Premium.  W tym artykule przedstawiono wskazówki dotyczące migracji z usługi na platformie Azure do usługi Power BI oraz zmian, których można spodziewać się w aplikacji.

> [!IMPORTANT]
> Mimo że podczas migracji używana jest zależność od usługi Power BI, zależność taka nie będzie dotyczyła użytkowników aplikacji osadzonej przy użyciu **tokenu osadzania**. Nie będą oni musieli tworzyć konta w usłudze Power BI w celu wyświetlenia zawartości osadzonej w aplikacji. Tej metody osadzania można użyć w celu obsługi użytkowników niekorzystających z usługi Power BI.
> 
> 

![](media/migrate-from-powerbi-embedded/powerbi-embed-flow.png)

## <a name="prepare-for-the-migration"></a>Przygotowanie do migracji
W ramach przygotowania do migracji z usługi Power BI Embedded na platformie Azure do usługi Power BI należy wykonać kilka czynności. Potrzebna jest dostępna dzierżawa oraz licencja użytkownika usługi Power BI Pro.

1. Upewnij się, że masz dostęp do dzierżawy usługi Azure Active Directory (Azure AD).
   
    Należy określić, jaka konfiguracja dzierżawy będzie używana.
   
   * Istniejąca firmowa dzierżawa usługi Power BI?
   * Oddzielna dzierżawa dla aplikacji?
   * Oddzielna dzierżawa dla każdego klienta?
     
     Jeśli zdecydujesz się na utworzenie nowej dzierżawy dla aplikacji lub dla każdego klienta, zobacz [Tworzenie dzierżawy usługi Azure Active Directory](create-an-azure-active-directory-tenant.md) lub [Jak uzyskać dzierżawę usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant).
2. Utwórz w nowej dzierżawie użytkownika, który będzie pełnił funkcję głównego konta aplikacji. Dla tego użytkownika należy utworzyć konto usługi Power BI i przypisać do niego licencję usługi Power BI Pro.

## <a name="accounts-within-azure-ad"></a>Konta w usłudze Azure AD
W dzierżawie muszą istnieć następujące konta.

> [!NOTE]
> Aby możliwe było korzystanie z obszarów roboczych aplikacji, należy przypisać do tych kont licencje usługi Power BI Pro.
> 
> 

1. Użytkownik będący administratorem dzierżawy.
   
    Zaleca się, aby ten użytkownik był członkiem wszystkich obszarów roboczych aplikacji utworzonych na potrzeby osadzania.
2. Konta analityków tworzących zawartość.
   
    Ci użytkownicy powinni być przypisani do obszarów roboczych aplikacji stosownie do potrzeb.
3. *Główne* konto użytkownika lub konto usługi dla aplikacji.
   
    Poświadczenia tego konta będą przechowywane w zapleczu aplikacji i używane w celu uzyskania tokenu usługi Azure AD do użycia z interfejsami API REST usługi Power BI. To konto będzie używane w celu wygenerowania tokenu osadzania dla aplikacji. To konto musi być też administratorem obszarów roboczych aplikacji tworzonych na potrzeby osadzania.
   
   > [!NOTE]
   > Jest to zwykłe konto użytkownika w organizacji, które będzie używane na potrzeby osadzania.
   > 
   > 

## <a name="app-registration-and-permissions"></a>Rejestrowanie aplikacji i uprawnienia
Konieczne będzie zarejestrowanie aplikacji w usłudze Azure AD i przydzielenie określonych uprawnień.

### <a name="register-an-application"></a>Rejestrowanie aplikacji
Aplikację należy zarejestrować w usłudze Azure AD, aby móc wykonywać wywołania interfejsu API REST. W tym celu należy przejść do witryny Azure Portal i wykonać dodatkowe czynności konfiguracyjne, poza rejestracją na stronie rejestracji aplikacji usługi Power BI. Aby uzyskać więcej informacji, zobacz [Rejestrowanie aplikacji usługi Azure AD, aby osadzić zawartość usługi Power BI](register-app.md).

Należy zarejestrować aplikację przy użyciu **głównego** konta aplikacji.

## <a name="create-app-workspaces-required"></a>Tworzenie obszarów roboczych aplikacji (wymagane)
Możesz użyć obszarów roboczych aplikacji w celu zapewnienia lepszej izolacji, jeśli aplikacja obsługuje wielu klientów. Raporty i pulpity nawigacyjne poszczególnych klientów będą izolowane. Możesz także użyć oddzielnego konta usługi Power BI dla każdego obszaru roboczego aplikacji, aby dodatkowo odizolować środowiska poszczególnych klientów.

> [!IMPORTANT]
> Na potrzeby osadzania dla użytkowników niekorzystających z usługi Power BI nie można używać osobistego obszaru roboczego.
> 
> 

Utworzenie obszaru roboczego aplikacji w usłudze Power BI wymaga użytkownika z licencją Pro. Użytkownik usługi Power BI, który utworzy obszar roboczy aplikacji, będzie domyślnie administratorem tego obszaru roboczego.

> [!NOTE]
> Administratorem obszaru roboczego musi być *główne* konto aplikacji.
> 
> 

## <a name="content-migration"></a>Migracja zawartości
Migrację zawartości z kolekcji obszarów roboczych do usługi Power BI można przeprowadzić równolegle z korzystaniem z bieżącego rozwiązania, bez konieczności przerywania działania.

Możesz użyć **narzędzia do migracji**, ułatwiającego kopiowanie zawartości z usługi Power BI Embedded do usługi Power BI. Jest to przydatne zwłaszcza wówczas, gdy masz dużo zawartości. Aby uzyskać więcej informacji, zobacz [Narzędzie do migracji usługi Power BI Embedded](migrate-tool.md).

Migracja zawartości opiera się przede wszystkim na dwóch interfejsach API.

1. Interfejs API „Download PBIX” pobiera pliki PBIX przekazane do usługi Power BI od października 2016 r.
2. Interfejs API „Import PBIX” przekazuje wszelkie pliki PBIX do usługi Power BI.

Aby skorzystać z fragmentów kodu związanych z tym procesem, zobacz [Fragmenty kodu umożliwiające migrację zawartości z usługi Power BI Embedded](migrate-code-snippets.md).

### <a name="report-types"></a>Typy raportów
Istnieje kilka typów raportów, a każdy wymaga nieco innej procedury migracji.

#### <a name="cached-dataset--report"></a>Buforowany zestaw danych i raport
Buforowane zestawy danych to pliki PBIX zawierające zaimportowane dane, a nie połączenie na żywo czy połączenie zapytania bezpośredniego.

**Procedura**

1. Wywołaj interfejs API pobierania pliku PBIX z obszaru roboczego w usłudze PaaS.
2. Zapisz plik PBIX.
3. Wywołaj importowanie pliku do obszaru roboczego w usłudze SaaS.

#### <a name="directquery-dataset--report"></a>Zestaw danych i raport z zapytaniem bezpośrednim
**Procedura**

1. Wywołaj polecenie GET https://api.powerbi.com/v1.0/collections/{identyfikator_kolekcji}/workspaces/{identyfikator_obszaru_roboczego}/datasets/{identyfikator_zestawu_danych}/Default.GetBoundGatewayDataSources i zapisz otrzymane parametry połączenia.
2. Wywołaj interfejs API pobierania pliku PBIX z obszaru roboczego w usłudze PaaS.
3. Zapisz plik PBIX.
4. Wywołaj importowanie pliku do obszaru roboczego w usłudze SaaS.
5. Zaktualizuj parametry połączenia, wywołując polecenie POST https://api.powerbi.com/v1.0/myorg/datasets/{identyfikator_zestawu_danych}/Default.SetAllConnections
6. Pobierz identyfikator bramy i identyfikator źródła danych, wywołując polecenie GET https://api.powerbi.com/v1.0/myorg/datasets/{identyfikator_zestawu_danych}/Default.GetBoundGatewayDataSources
7. Zaktualizuj poświadczenia użytkownika, wywołując polecenie PATCH https://api.powerbi.com/v1.0/myorg/gateways/{identyfikator_bramy}/datasources/{identyfikator_źródła_danych}

#### <a name="old-dataset--reports"></a>Starsze zestawy danych i raporty
Są to zestawy danych/raporty utworzone przed październikiem 2016 r. Interfejs API „Download PBIX” nie obsługuje plików PBIX przekazanych przed październikiem 2016 r.

**Procedura**

1. Pobierz plik PBI ze środowiska deweloperskiego (wewnętrznej kontroli źródła).
2. Wywołaj importowanie pliku do obszaru roboczego w usłudze SaaS.

#### <a name="push-dataset--report"></a>Zestaw danych i raport interfejsu wypychania
Interfejs API „Download PBIX” nie obsługuje zestawów danych *interfejsu API wypychania*. Nie można przenosić danych zestawu danych interfejsu API wypychania z usługi PaaS do usługi SaaS.

**Procedura**

1. Wywołaj interfejs API „Create dataset” z zestawem danych Json, aby utworzyć zestaw danych w obszarze roboczym usługi SaaS.
2. Skompiluj ponownie raport dla utworzonego zestawu danych.*

Można użyć obejścia w celu przeprowadzenia migracji raportu interfejsu API wypychania z usługi PaaS do usługi SaaS, wykonując następujące czynności.

1. Przekaż dowolny zastępczy plik PBIX do obszaru roboczego usługi PaaS.
2. Sklonuj raport interfejsu API wypychania i powiąż go z zastępczym plikiem PBIX z kroku 1.
3. Pobierz raport interfejsu API wypychania z zastępczym plikiem PBIX.
4. Przekaż zastępczy plik PBIX do obszaru roboczego usługi SaaS.
5. Utwórz zestaw danych wypychania w obszarze roboczym usługi SaaS.
6. Ponownie powiąż raport z zestawem danych interfejsu API wypychania.

## <a name="create-and-upload-new-reports"></a>Tworzenie i przekazywanie nowych raportów
Oprócz zawartości migrowanej z usługi Power BI Embedded platformy Azure można również tworzyć raporty i zestawy danych przy użyciu programu Power BI Desktop, a następnie publikować te raporty w obszarze roboczym aplikacji. Aby móc publikować raporty w obszarze roboczym aplikacji, użytkownik końcowy publikujący je musi mieć licencję usługi Power BI Pro.

## <a name="rebuild-your-application"></a>Ponowne kompilowanie aplikacji
1. Należy zmodyfikować aplikację w celu korzystania z interfejsów API REST usługi Power BI oraz lokalizacji raportu w witrynie powerbi.com.
2. Ponownie skompiluj uwierzytelnianie AuthN/AuthZ przy użyciu *głównego* konta aplikacji. Możesz skorzystać z [tokenu osadzania](https://msdn.microsoft.com/library/mt784614.aspx), aby zezwolić temu użytkownikowi na działanie w imieniu innych użytkowników.
3. Możesz osadzać raporty z witryny powerbi.com w aplikacji.

## <a name="map-your-users-to-a-power-bi-user"></a>Mapowanie użytkowników na użytkownika usługi Power BI
Użytkownicy zarządzani w aplikacji będą mapowani na poświadczenia *głównego* konta usługi Power BI używanego na potrzeby aplikacji. Poświadczenia tego *głównego* konta usługi Power BI dla aplikacji będą w niej przechowywane i używane do tworzenia tokenów osadzania.

## <a name="what-to-do-when-you-are-ready-for-production"></a>Przechodzenie do zastosowania produkcyjnego
Gdy wszystko będzie gotowe do przejścia do zastosowania produkcyjnego, należy wykonać następujące czynności.

* Jeśli korzystasz z oddzielnej dzierżawy na potrzeby programowania, należy upewnić się, że obszary robocze aplikacji oraz pulpity nawigacyjne i raporty są dostępne w środowisku produkcyjnym. Należy także upewnić się, że utworzono aplikację w usłudze Azure AD dla dzierżawy produkcyjnej i przypisano odpowiednie uprawnienia aplikacji, zgodnie z instrukcjami w kroku 1.
* Kup pojemność odpowiednią do potrzeb. Aby łatwiej określić swoje potrzeby, możesz skorzystać z [oficjalnego dokumentu dotyczącego planowania pojemności na potrzeby osadzonej analizy](https://aka.ms/pbiewhitepaper). Gdy wszystko będzie gotowe do zakupu, możesz dokonać zakupu w [centrum administracyjnym usługi Office 365](https://portal.office.com/adminportal/home#/catalog).
  
  > [INFORMACJE DOTYCZĄCE PLATFORMY AZURE] Aby uzyskać informacje o sposobie zakupu usługi Power BI Premium, zobacz [Jak kupić usługę Power BI Premium](../service-admin-premium-purchase.md).
  > 
  > 
* Edytuj obszar roboczy aplikacji i przypisz go do pojemności Premium w obszarze Zaawansowane.
  
    ![](media/migrate-from-powerbi-embedded/powerbi-embedded-premium-capacity.png)
* Wdróż zaktualizowaną aplikację w środowisku produkcyjnym i rozpocznij osadzanie raportów z usługi Power BI.

## <a name="after-migration"></a>Po migracji
Należy wyczyścić odpowiednie zasoby na platformie Azure.

* Usuń wszystkie obszary robocze poza wdrożonym rozwiązaniem z usługi Power BI Embedded na platformie Azure.
* Usuń wszelkie kolekcje obszarów roboczych na platformie Azure.

## <a name="next-steps"></a>Następne kroki
[Osadzanie przy użyciu usługi Power BI](embedding.md)  
[Narzędzie do migracji usługi Power BI Embedded](migrate-tool.md)  
[Fragmenty kodu umożliwiające migrację zawartości z usługi Power BI Embedded](migrate-code-snippets.md)  
[Jak osadzić pulpity nawigacyjne, raporty i kafelki usługi Power BI](embedding-content.md)  
[Power BI Premium — co to jest?](../service-premium.md)  
[Repozytorium Git interfejsu API języka JavaScript](https://github.com/Microsoft/PowerBI-JavaScript)  
[Repozytorium Git języka C# usługi Power BI](https://github.com/Microsoft/PowerBI-CSharp)  
[Przykład osadzania przy użyciu języka JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Oficjalny dokument dotyczący planowania pojemności na potrzeby osadzonej analizy](https://aka.ms/pbiewhitepaper)  
[Oficjalny dokument na temat usługi Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)
