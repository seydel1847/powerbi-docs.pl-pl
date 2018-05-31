---
title: Osadzanie zawartości usługi Power BI w aplikacji dla klientów
description: Dowiedz się, jak integrować lub osadzać raport, pulpit nawigacyjny lub kafelek w aplikacji internetowej przy użyciu interfejsów API usługi Power BI dla klientów.
services: powerbi
author: markingmyname
ms.author: maghan
ms.date: 05/07/2018
ms.topic: tutorial
ms.service: powerbi
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 2d4fdee8d3e4cca60294acd0a9167da1f048afa5
ms.sourcegitcommit: 9fa954608e78dcdb8d8a503c3c9b01c43ca728ab
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2018
ms.locfileid: "34051938"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-customers"></a>Samouczek: osadzanie raportu, pulpitu nawigacyjnego lub kafelka usługi Power BI w aplikacji dla klientów
Usługa **Power BI Embedded na platformie Azure** umożliwia osadzanie raportów, pulpitów nawigacyjnych lub kafelków w aplikacji, aby klienci mogli udostępniać dane. Jest to zazwyczaj scenariusz obejmujący **dewelopera ISV**, w którym jest używana struktura typu **app owns data** (dane należą do aplikacji). Struktura **app owns data** (dane należą do aplikacji) oznacza osadzanie zawartości usługi Power BI dla własnych klientów. Na przykład użytkownik zawartości usługi Power BI może przeglądać raporty, pulpity nawigacyjne lub kafelki bez konieczności logowania się do usługi **Power BI**. W tym samouczku przedstawiono sposób integrowania lub osadzania raportu w aplikacji przy użyciu zestawu .NET SDK usługi **Power BI** z interfejsem API języka JavaScript usługi **Power BI** w przypadku używania usługi **Power BI Embedded na platformie Azure**  dla klientów korzystających ze struktury **app owns data**.

Z tego samouczka dowiesz się, jak wykonywać następujące czynności:
>[!div class="checklist"]
>* Rejestrowanie aplikacji na platformie Azure.
>* Osadzanie raportu, pulpitu nawigacyjnego lub kafelka w aplikacji przy użyciu usługi Power BI Embedded na platformie Azure.

## <a name="prerequisites"></a>Wymagania wstępne
Do rozpoczęcia pracy potrzebne jest konto usługi **Power BI Pro** i konto platformy **Microsoft Azure**.

* Jeśli nie masz konta usługi **Power BI Pro**, na początku [zacznij korzystać z bezpłatnej wersji próbnej](https://powerbi.microsoft.com/en-us/pricing/).
* Jeśli nie masz subskrypcji platformy Azure, przed rozpoczęciem utwórz [bezpłatne konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).
* Musisz mieć własną konfigurację [dzierżawy usługi Azure Active Directory](create-an-azure-active-directory-tenant.md).
* Musisz mieć zainstalowany program [Visual Studio](https://www.visualstudio.com/) (w wersji 2013 lub nowszej).

## <a name="setup-your-embedded-analytics-development-environment"></a>Konfigurowanie środowiska deweloperskiego analizy osadzonej

Przed rozpoczęciem osadzania raportów, pulpitów nawigacyjnych lub kafelków w aplikacji należy upewnić się, że środowisko skonfigurowano w sposób umożliwiający osadzanie. W ramach konfiguracji należy wykonać następujące działania.

### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>Rejestrowanie aplikacji w usłudze Azure Active Directory (Azure AD)

Aplikację można zarejestrować w usłudze Azure Active Directory, aby zapewnić aplikacji dostęp do interfejsów API REST usługi Power BI. Dzięki temu można ustanowić tożsamość aplikacji i określić jej uprawnienia do zasobów REST usługi Power BI.

1. Zaakceptuj [Warunki interfejsu API usługi Microsoft Power BI](https://powerbi.microsoft.com/api-terms).

2. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com).
 
    ![Główna część witryny Azure Portal](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

3. W okienku nawigacji po lewej stronie wybierz kolejno pozycje **Wszystkie usługi** i **Rejestracje aplikacji**, a następnie kliknij przycisk **Rejestrowanie nowej aplikacji**.
   
    ![Wyszukiwanie rejestracji aplikacji](media/embed-sample-for-customers/embed-sample-for-customers-003.png)</br>
    ![Nowa rejestracja aplikacji](media/embed-sample-for-customers/embed-sample-for-customers-004.png)

4. Postępuj zgodnie z monitami i utwórz nową aplikację. W przypadku struktury „app owns data” użyj typu aplikacji **Natywna**. Podaj również **Identyfikator URI przekierowania**, którego usługa **Azure AD** używa do zwracania odpowiedzi tokenu. Wprowadź wartość powiązaną z Twoją aplikacją (np. http://localhost:13526/redirect)).

    ![Tworzenie aplikacji](media/embed-sample-for-customers/embed-sample-for-customers-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>Stosowanie uprawnień do aplikacji w usłudze Azure Active Directory

Konieczne będzie włączenie dodatkowych uprawnień aplikacji oprócz tych, które zostały podane na stronie rejestrowania aplikacji. Musisz zalogować się na konto *główne* używane do osadzania, które musi być kontem administratora globalnego.

### <a name="use-the-azure-active-directory-portal"></a>Korzystanie z portalu usługi Azure Active Directory

1. Przejdź do obszaru [Rejestracje aplikacji](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) w witrynie Azure Portal i wybierz aplikację, której używasz do osadzania.
   
    ![Wybieranie aplikacji](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

2. Wybierz pozycję **Ustawienia**, a następnie w obszarze **Dostęp do interfejsu API** wybierz pozycję **Wymagane uprawnienia**.
   
    ![Wymagane uprawnienia](media/embed-sample-for-customers/embed-sample-for-customers-008.png)

3. Wybierz pozycję **Windows Azure Active Directory**, a następnie upewnij się, że wybrana jest pozycja **Uzyskuj dostęp do katalogu jako zalogowany użytkownik**. Wybierz pozycję **Zapisz**.
   
    ![Uprawnienia usługi Windows Azure AD](media/embed-sample-for-customers/embed-sample-for-customers-011.png)

4. Wybierz pozycję **Dodaj**.

    ![Dodawanie uprawnień](media/embed-sample-for-customers/embed-sample-for-customers-012.png)

5. Wybierz pozycję **Wybierz interfejs API**.

    ![Dodawanie dostępu do interfejsu API](media/embed-sample-for-customers/embed-sample-for-customers-013.png)

6. Wybierz pozycję **Usługa Power BI**, a następnie wybierz pozycję **Wybierz**.

    ![Wybieranie usług PBI](media/embed-sample-for-customers/embed-sample-for-customers-014.png)

7. Wybierz wszystkie uprawnienia w obszarze **Delegowane uprawnienia**. W celu zapisania wyborów musisz je zaznaczać pojedynczo. Po zakończeniu wybierz pozycję **Zapisz**.
   
    ![Wybieranie delegowanych uprawnień](media/embed-sample-for-customers/embed-sample-for-customers-015.png)

8. W obszarze **Wymagane uprawnienia** wybierz pozycję **Udziel uprawnień**.
   
    Wykonanie akcji **Udziel uprawnień** jest konieczne, aby usługa Azure AD nie wysyłała do *konta głównego* monitów o wyrażenie zgody. Jeśli konto, z którego wykonywana jest ta akcja, jest kontem administratora globalnego, udzielisz uprawnień do tej aplikacji wszystkim użytkownikom w swojej organizacji. Jeśli jest to *konto główne*, które nie ma uprawnień administratora globalnego, udzielisz uprawnień do tej aplikacji tylko *kontu głównemu*.
   
    ![Udzielanie uprawnień w oknie dialogowym Wymagane uprawnienia](media/embed-sample-for-customers/embed-sample-for-customers-016.png)

### <a name="create-your-power-bi-embedded-dedicated-capacity-in-azure"></a>Tworzenie dedykowanej pojemności usługi Power BI Embedded na platformie Azure

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com).

    ![Główna część witryny Azure Portal](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

2. W okienku nawigacji po lewej stronie wybierz kolejno pozycje **Wszystkie usługi** i **Power BI Embedded**.

    ![Wyszukiwanie w usłudze PBIE](media/embed-sample-for-customers/embed-sample-for-customers-017.png)

3. Postępuj zgodnie z monitami i wprowadź odpowiednie informacje potrzebne do utworzenia nowej dedykowanej pojemności usługi **Power BI Embedded**, a następnie wybierz pozycję **Utwórz**. Wybierając opcję w polu **Warstwa cenowa**, zapoznaj się z poniższą tabelą, aby zdecydować, która warstwa najlepiej odpowiada Twoim potrzebom. Następnie wybierz pozycję **Utwórz** i poczekaj na ukończenie zasobu.

    ![Konfiguracja usługi PBIE](media/embed-sample-for-customers/embed-sample-for-customers-018.png)

| Węzeł pojemności | Całkowita liczba rdzeni<br/>*(Wewnętrzna baza danych + fronton)* | Rdzenie wewnętrznej bazy danych | Rdzenie frontonu | Limity zapytania bezpośredniego/połączenia na żywo | Maksymalne renderowanie strony w godzinie szczytu |
| --- | --- | --- | --- | --- | --- |
| A1 |1 rdzeń wirtualny |0,5 rdzenia, 3 GB pamięci RAM |0,5 rdzenia | 5 na sekundę |1–300 |
| A2 |2 rdzenie wirtualne |1 rdzeń, 5 GB pamięci RAM |1 rdzeń | 10 na sekundę |301–600 |
| A3 |4 rdzenie wirtualne |2 rdzenie, 10 GB pamięci RAM |2 rdzenie | 15 na sekundę |601–1200 |
| A4 |8 rdzeni wirtualnych |4 rdzenie, 25 GB pamięci RAM |4 rdzenie |30 na sekundę |1201–2400 |
| A5 |16 rdzeni wirtualnych |8 rdzeni, 50 GB pamięci RAM |8 rdzeni |60 na sekundę |2401–4800 |
| A6 |32 rdzenie wirtualne |16 rdzeni, 100 GB pamięci RAM |16 rdzeni |120 na sekundę |4801–9600 |

Teraz możesz wyświetlić nową **dedykowaną pojemność usługi Power BI Embedded**.

   ![Dedykowana pojemność usługi PBIE](media/embed-sample-for-customers/embed-sample-for-customers-019.png)

## <a name="setup-your-power-bi-environment"></a>Konfigurowanie środowiska usługi Power BI

### <a name="create-an-app-workspace"></a>Tworzenie obszaru roboczego aplikacji

W przypadku osadzania raportów, pulpitów nawigacyjnych lub kafelków dla klientów należy umieścić zawartość w obszarze roboczym aplikacji. Konto *główne* musi być kontem administratora obszaru roboczego aplikacji.

1. Rozpocznij od utworzenia obszaru roboczego. Wybierz pozycję **Obszary robocze** > **Utwórz obszar roboczy aplikacji**. W tym miejscu zostanie umieszczona zawartość, do której aplikacja musi uzyskiwać dostęp.

    ![Tworzenie obszaru roboczego](media/embed-sample-for-customers/embed-sample-for-customers-020.png)

2. Nadaj nazwę obszarowi roboczemu. Jeśli odpowiedni **Identyfikator obszaru roboczego** nie jest dostępny, edytuj go, aby skorzystać z unikatowego identyfikatora. Będzie to również nazwa aplikacji.

    ![Nazywanie obszaru roboczego](media/embed-sample-for-customers/embed-sample-for-customers-021.png)

3. Istnieje kilka opcji do ustawienia. Jeśli wybierzesz opcję **Publiczny**, wszystkie osoby w organizacji będą mogły zobaczyć zawartość tego obszaru roboczego. Z drugiej strony opcja **Prywatny** oznacza, że tylko członkowie obszaru roboczego będą mogli wyświetlić jego zawartość.

    ![Prywatny/Publiczny](media/embed-sample-for-customers/embed-sample-for-customers-022.png)

    Nie możesz zmienić ustawienia Publiczny/Prywatny po utworzeniu grupy.

4. Ponadto możesz zdecydować, czy członkowie uzyskają dostęp do **edycji** lub **tylko do wyświetlania**.

    ![Dodawanie członków](media/embed-sample-for-customers/embed-sample-for-customers-023.png)

5. Dodaj adresy e-mail osób, które mają mieć dostęp do obszaru roboczego, a następnie wybierz opcję **Dodaj**. Nie można dodawać aliasów grupy, tylko osoby.

6. Zdecyduj wobec każdej osoby, czy jest członkiem, czy administratorem. Administratorzy mogą edytować obszar roboczy, w tym dodawać innych członków. Członkowie mogą edytować zawartość w obszarze roboczym, chyba że mają dostęp tylko do wyświetlania. Administratorzy i członkowie mogą opublikować aplikację.

7. Rozwiń węzeł **Zaawansowane**, włącz pozycję **Pojemność dedykowana**, a następnie wybierz utworzoną **pojemność dedykowaną usługi Power BI Embedded**. Następnie wybierz pozycję **Zapisz**.

    ![Dodawanie członków](media/embed-sample-for-customers/embed-sample-for-customers-024.png)

Teraz możesz wyświetlić nowy obszar roboczy. Usługa Power BI tworzy obszar roboczy i otwiera go. Zostanie on wyświetlony na liście obszarów roboczych, których członkiem jesteś. Jako że jesteś administratorem, możesz wybrać wielokropek (...), aby powrócić i wprowadzić zmiany, dodając nowych członków lub zmieniając ich uprawnienia.

   ![Nowy obszar roboczy](media/embed-sample-for-customers/embed-sample-for-customers-025.png)

### <a name="create-and-publish-your-reports"></a>Tworzenie i publikowanie raportów

Raporty i zestawy danych można tworzyć przy użyciu programu Power BI Desktop, a następnie publikować je w obszarze roboczym aplikacji. Aby móc publikować raporty w obszarze roboczym aplikacji, użytkownik końcowy publikujący je musi mieć licencję usługi Power BI Pro.

1. Pobierz przykład [Blog Demo](https://github.com/Microsoft/powerbi-desktop-samples) (Pokaz bloga) z usługi GitHub.

    ![przykładowy raport](media/embed-sample-for-customers/embed-sample-for-customers-026-1.png)

2. Otwórz przykładowy raport PBIX w programie **Power BI Desktop**.

   ![Raport programu PBI Desktop](media/embed-sample-for-customers/embed-sample-for-customers-027.png)

3. Opublikuj w **obszarze roboczym aplikacji**.

   ![Raport programu PBI Desktop](media/embed-sample-for-customers/embed-sample-for-customers-028.png)

    Teraz możesz przeglądać raport w trybie online za pomocą usługi Power BI.

   ![Raport programu PBI Desktop](media/embed-sample-for-customers/embed-sample-for-customers-029.png)

## <a name="embed-your-content"></a>Osadzanie zawartości

1. Pobierz [przykład App Owns Data](https://github.com/Microsoft/PowerBI-Developer-Samples) (dane należą do aplikacji) z usługi GitHub, aby rozpocząć pracę.

    ![Przykład aplikacji App Owns Data (dane należą do aplikacji)](media/embed-sample-for-customers/embed-sample-for-customers-026.png)

2. Otwórz plik Web.config w przykładowej aplikacji. Aby pomyślnie uruchomić aplikację, należy wypełnić 5 pól: **clientID**, **groupId**, **reportId**, **pbiUsername** i **pbiPassword**.

      ![Plik Web.config](media/embed-sample-for-customers/embed-sample-for-customers-030.png)

    * W polu **clientId** podaj **identyfikator aplikacji** z platformy **Azure**. Za pomocą wartości **clientId** aplikacja identyfikuje się dla użytkowników, od których żądasz uprawnień. Aby uzyskać wartość **clientId**, wykonaj następujące czynności:

        1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com).

        ![Główna część witryny Azure Portal](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

        2. W okienku nawigacji po lewej stronie wybierz pozycję **Wszystkie usługi** i pozycję **Rejestracje aplikacji**.

        ![Wyszukiwanie rejestracji aplikacji](media/embed-sample-for-customers/embed-sample-for-customers-003.png)
        3. Wybierz aplikację, dla której chcesz uzyskać wartość **clientId**.

        ![Wybieranie aplikacji](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

      4. Powinien zostać wyświetlony **identyfikator aplikacji** wymieniony jako identyfikator GUID. Użyj tego **identyfikatora aplikacji** jako wartości **clientId** dla aplikacji.

        ![clientId](media/embed-sample-for-customers/embed-sample-for-customers-007.png)     

    * W polu **groupId** podaj **identyfikator GUID obszaru roboczego aplikacji** z usługi Power BI.

        ![groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    * W polu **reportId** podaj **identyfikator GUID** z usługi Power BI.

        ![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)    

    * W polu **pbiUsername** określ główne konto użytkownika usługi Power BI.
    * W polu **pbiPassword** podaj hasło głównego konta użytkownika usługi Power BI.

3. Uruchom aplikację!

    Najpierw wybierz pozycję **Uruchom** w programie **Visual Studio**.

    ![Uruchamianie aplikacji](media/embed-sample-for-customers/embed-sample-for-customers-033.png)

    Następnie wybierz pozycję **Osadź raport**. W zależności od zawartości, którą chcesz testować — raporty, pulpity nawigacyjne lub kafelki — wybierz tę opcję w aplikacji.

    ![Wybieranie zawartości](media/embed-sample-for-customers/embed-sample-for-customers-034.png)
 
    Teraz możesz przeglądać raport w przykładowej aplikacji.

    ![Wyświetlanie aplikacji](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

Aby uzyskać pełen przykład użycia interfejsu API języka JavaScript, można użyć [narzędzia Playground](https://microsoft.github.io/PowerBI-JavaScript/demo). Jest to szybki sposób na zapoznanie się z różnymi typami przykładów usługi Power BI Embedded. Możesz również uzyskać więcej informacji na temat interfejsu API języka JavaScript odwiedzając stronę [wiki Power BI-JavaScript](https://github.com/Microsoft/powerbi-javascript/wiki).

Jeśli masz dalsze pytania dotyczące usługi Power BI Embedded, odwiedź stronę [często zadawanych pytań](embedded-faq.md).  Jeśli masz problemy z usługą Power BI Embedded w aplikacji, odwiedź stronę [rozwiązywania problemów](embedded-troubleshoot.md).

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/) 