---
title: Osadzanie raportu w bezpiecznym portalu lub witrynie internetowej
description: Dzięki funkcji bezpiecznego osadzania usługi Power BI możesz umożliwić użytkownikom łatwe i bezpieczne osadzanie raportów w wewnętrznych portalach internetowych.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/08/2019
LocalizationGroup: Share your work
ms.openlocfilehash: b816b504d3eed3aa91eb25c0bb3c6189d3075d1f
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54285834"
---
# <a name="embed-a-report-in-a-secure-portal-or-website"></a>Osadzanie raportu w bezpiecznym portalu lub witrynie internetowej

Nowa opcja bezpiecznego **osadzania** dla raportów usługi Power BI umożliwia użytkownikom łatwe i bezpieczne osadzanie raportów w wewnętrznych portalach internetowych: **opartych na chmurze** lub **hostowanych lokalnie**, takich jak SharePoint 2019 r. W raportach osadzonych w ten sposób wszystkie uprawnienia elementów oraz zabezpieczenia danych są stosowane za pośrednictwem zabezpieczeń na poziomie wiersza (RLS). Funkcja została zaprojektowana tak, aby umożliwić osadzanie bez użycia kodu w dowolnym portalu, który akceptuje adres URL lub element iFrame do osadzania.

Opcja **Osadź** obsługuje również [filtry adresów URL](service-url-filters.md) i ustawienia adresów URL. Opcja **Osadź** umożliwia integrację z portalami przy użyciu podejścia z niewielką ilością kodu, które wymaga podstawowej wiedzy na temat języków HTML i JavaScript.

## <a name="how-to-embed-power-bi-reports-into-portals"></a>Jak **osadzać** raporty usługi Power BI w portalach

1. Nowa opcja **Osadź** jest dostępna w menu **Plik** dla raportów w usłudze Power BI.

    ![Opcja bezpiecznego osadzania na liście rozwijanej](media/service-embed-secure/secure-embed-drop-down-menu.png)

2. Wybierz opcję Osadź, aby otworzyć okno dialogowe zawierające link i element iFrame, które są używane do bezpiecznego osadzania raportu.

    ![Okno dialogowe opcji osadzania](media/service-embed-secure/secure-embed-code-dialog.png)

3. Po osadzeniu adresu URL w portalu internetowym lub bezpośrednim otwarciu adresu URL użytkownik jest uwierzytelniany przed uzyskaniem praw dostępu do raportu. Poniżej użytkownik nie zalogował do usługi Power BI w sesji przeglądarki. Po naciśnięciu pozycji **Zaloguj się** być może trzeba będzie otworzyć nowe okno lub kartę przeglądarki. Jeśli monit o zalogowanie nie zostanie wyświetlony, sprawdź programy do blokowania wyskakujących okienek.

    ![Logowanie się w celu wyświetlenia raportu](media/service-embed-secure/secure-embed-sign-in.png)

4. Gdy użytkownik się zaloguje, zostanie otwarty raport zawierający dane i umożliwiający użytkownikom przechodzenie między stronami i ustawianie filtrów. Raport jest widoczny tylko dla użytkowników, którzy mają uprawnienie do wyświetlania raportu w usłudze Power BI. Są również stosowane wszystkie reguły zabezpieczeń na poziomie wiersza (RLS). Ponadto użytkownik musi być prawidłowo licencjonowany — musi mieć licencję usługi Power BI Pro lub raport musi należeć do obszaru roboczego w pojemności usługi Power BI Premium. Użytkownik musi logować się po każdym otwarciu nowego okna przeglądarki, ale po pierwszym zalogowaniu inne raporty będą ładowane automatycznie.

    ![Osadzanie raportu](media/service-embed-secure/secure-embed-report.png)

5. W przypadku korzystania z opcji iFrame najlepszym rozwiązaniem jest edytowanie udostępnionego kodu HTML w celu określenia żądanej wysokości i szerokości umożliwiającej dopasowanie strony internetowej portalu.

    ![Ustawianie wysokości i szerokości](media/service-embed-secure/secure-embed-size.png)

## <a name="granting-access-to-reports"></a>Udzielanie dostępu do raportów

Opcja osadzania nie zezwala automatycznie użytkownikom na wyświetlanie raportu. Uprawnienia do wyświetlania raportu są ustawiane w usłudze Power BI.

Aby zapewnić dostęp do raportu w usłudze Power BI, możesz udostępnić raport użytkownikom, którzy wymagają dostępu do osadzonego raportu. Jeśli używasz grupy usługi Office 365, możesz uwzględnić użytkownika jako członka obszaru roboczego aplikacji w usłudze Power BI. Aby uzyskać więcej informacji, zobacz instrukcje dotyczące [zarządzania obszarem roboczym aplikacji](service-manage-app-workspace-in-power-bi-and-office-365.md).

## <a name="licensing"></a>Licencjonowanie

Użytkownicy wyświetlający raport osadzony potrzebują licencji usługi Power BI Pro lub zawartość musi zostać zapisana w obszarze roboczym w [pojemności usługi Power BI Premium (jednostka SKU EM lub P)](service-admin-premium-purchase.md).

## <a name="customize-your-embed-experience-using-url-settings"></a>Dostosowywanie środowiska osadzania przy użyciu ustawień adresów URL

Adres URL osadzania obsługuje kilka ustawień wejściowych, które pomagają w dostosowaniu środowiska użytkownika. Jeśli używasz udostępnionego elementu iFrame, pamiętaj o zaktualizowaniu adresu URL w ustawieniach src elementu iFrame.

| Właściwość  | Opis  |  |  |  |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|---|
| pageName  | Parametr ciągu zapytania **pageName** umożliwia ustawienie strony raportu do otwarcia. Wartość **PageName** odpowiada końcowej części adresu URL raportu podczas wyświetlania raportu w usłudze Power BI, jak pokazano poniżej. |  |  |  |
| Filtry adresów URL  | [Filtry adresów URL](service-url-filters.md) w adresie URL osadzania otrzymanym z interfejsu użytkownika usługi Power BI umożliwiają filtrowanie osadzonej zawartości. W ten sposób można tworzyć integracje z niewielką ilością kodu, używając tylko podstawowego środowiska języków HTML i JavaScript.  |  |  |  |

## <a name="set-which-page-opens-when-the-report-is-embedded"></a>Ustawianie strony do otwarcia po osadzeniu raportu

Podana wartość ustawienia *PageName* odpowiada końcowej części adresu URL raportu podczas wyświetlania raportu w usłudze Power BI.

1. Otwórz raport z usługi Power BI w przeglądarce internetowej, a następnie skopiuj adres URL z paska adresu.

    ![Sekcja raportu](media/service-embed-secure/secure-embed-report-section.png)

2. Dołącz ustawienie *pageName* do adresu URL.

    ![Dołączanie ustawienia pageName](media/service-embed-secure/secure-embed-append-page-name.png)

## <a name="filter-report-content-using-url-filters"></a>Filtrowanie zawartości raportu przy użyciu filtrów adresów URL

W przypadku niektórych zaawansowanych funkcji można za pomocą [filtrów adresów URL](service-url-filters.md) tworzyć więcej środowisk korzystających z raportu. Na przykład poniższy adres URL powoduje filtrowanie raportu w celu wyświetlenia danych dotyczących branży energetycznej.

Kombinacja ustawień **pageName** i [Filtry adresów URL](service-url-filters.md) oferuje zaawansowane możliwości. Można tworzyć środowiska przy użyciu podstawowego kodu HTML i JavaScript.

Na przykład w poniższy sposób można dodać przycisk do strony HTML:

```html
<button class="textLarge" onclick='show("ReportSection", "Energy");' style="display: inline-block;">Show Energy</button>
```

Po naciśnięciu przycisk wywołuje funkcję, aby zaktualizować element iFrame przy użyciu zaktualizowanego adresu URL, który obejmuje filtr dotyczący branży energetycznej.

```javascript
function show(pageName, filterValue)

{

var newUrl = baseUrl + "&pageName=" + pageName;

if(null != filterValue && "" != filterValue)

{

newUrl += "&$filter=Industries/Industry eq '" + filterValue + "'";

}

//Assumes there’s an iFrame on the page with id=”iFrame”

var report = document.getElementById("iFrame")

report.src = newUrl;

}
```

![Filtruj](media/service-embed-secure/secure-embed-filter.png)

Można dodać dowolną liczbę przycisków, aby utworzyć niestandardowe środowisko z niewielką ilością kodu. 

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia

* Brak obsługi zewnętrznych użytkowników gości za pomocą funkcji współpracy między firmami (B2B) na platformie Azure.

* Bezpieczne osadzanie działa w przypadku raportów publikowanych w usłudze Power BI.

* Użytkownik musi zalogować się w celu wyświetlania raportu przy każdym otwarciu nowego okna przeglądarki.

* Niektóre przeglądarki wymagają odświeżenia strony po zalogowaniu, szczególnie w przypadku korzystania z trybów InPrivate lub incognito.

* W celu utworzenia środowiska logowania jednokrotnego należy użyć opcji osadzania w usłudze SharePoint Online lub utworzyć niestandardową integrację z zastosowaniem podejścia [user owns data](developer/embed-sample-for-your-organization.md) (użytkownik jest właścicielem danych). Dowiedz się więcej na temat podejścia [user owns data](developer/embed-sample-for-your-organization.md).

* Możliwość automatycznego uwierzytelniania oferowana przez opcję **Osadź** nie działa w przypadku interfejsu API języka JavaScript usługi Power BI. W przypadku interfejsu API języka JavaScript usługi Power BI w celu osadzania należy zastosować podejście [user owns data](developer/embed-sample-for-your-organization.md) (użytkownik jest właścicielem danych). Dowiedz się więcej na temat podejścia [user owns data](developer/embed-sample-for-your-organization.md).

## <a name="next-steps"></a>Następne kroki

* [Sposoby udostępniania pracy](service-how-to-collaborate-distribute-dashboards-reports.md)

* [Filtry adresów URL](service-url-filters.md)

* [Składnik Web Part raportu w usłudze SharePoint Online](service-embed-report-spo.md)

* [Publikowanie w Internecie](service-publish-to-web.md)