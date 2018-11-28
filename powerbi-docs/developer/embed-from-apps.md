---
title: Osadzanie raportów lub pulpitów nawigacyjnych z aplikacji
description: Dowiedz się, jak zintegrować albo osadzić raport lub pulpit nawigacyjny z aplikacji Power BI, a nie z obszaru roboczego aplikacji.
author: markingmyname
ms.author: maghan
ms.topic: how-to
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.date: 11/27/2018
ms.openlocfilehash: 8073696907ceff67664a0802a2b7775eea693e37
ms.sourcegitcommit: fdb54145f9bc93b312409c15c603749f3a4a876e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/28/2018
ms.locfileid: "52452527"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>Osadzanie raportów lub pulpitów nawigacyjnych z aplikacji

W usłudze Power BI tworzysz aplikacje łączące ze sobą w jednym miejscu wszystkie powiązane pulpity nawigacyjne i raporty. Następnie publikujesz je dla większych grup osób w Twojej organizacji. Użycie tych aplikacji jest odpowiednie, gdy wszyscy Twoi użytkownicy są użytkownikami usługi Power BI. Możesz więc udostępniać im zawartość za pomocą aplikacji usługi Power BI. W tym artykule znajdziesz kilka szybkich kroków umożliwiających osadzenie zawartości opublikowanej aplikacji usługi Power BI w aplikacji innej firmy.

## <a name="grab-a-report-embedurl-for-embedding"></a>Pobieranie adresu embedURL raportu w celu osadzenia

1. Utwórz wystąpienie aplikacji w obszarze roboczym użytkownika **Mój obszar roboczy**. Udostępnij sobie albo pokieruj innego użytkownika, aby przeszedł przez ten przepływ.

2. Otwórz żądany raport w usłudze Power BI.

3. Przejdź do pozycji **Plik** > **Osadź w usłudze SharePoint Online** i pobierz w tym miejscu adres embedURL raportu. Przykładowy adres embedURL jest pokazany na poniższym zrzucie ekranu. Alternatywnie możesz wywołać interfejs API REST GetReports/GetReport i wyodrębnić odpowiednie pole adresu embedURL raportu z odpowiedzi. Wywołanie REST nie powinno mieć identyfikatora obszaru roboczego jako części adresu URL, ponieważ wystąpienie aplikacji zostało utworzone w obszarze roboczym użytkownika.

    ![Osadzanie z aplikacji](media/embed-from-apps/embed-from-app.png)

4. Użyj adresu embedURL pobranego w kroku 3 za pomocą zestawu SDK języka JavaScript.

## <a name="grab-a-dashboard-embedurl-for-embedding"></a>Pobieranie adresu embedURL pulpitu nawigacyjnego w celu osadzenia

1. Utwórz wystąpienie aplikacji w obszarze roboczym użytkownika **Mój obszar roboczy**. Udostępnij sobie albo pokieruj innego użytkownika, aby przeszedł przez ten przepływ.

2. Wywołaj interfejs API REST GetDashboards i wyodrębnij odpowiednie pole embedURL pulpitu nawigacyjnego z odpowiedzi. Wywołanie REST nie powinno mieć identyfikatora obszaru roboczego jako części adresu URL, ponieważ wystąpienie aplikacji zostało utworzone w obszarze roboczym użytkownika.

3. Użyj adresu embedURL pobranego w kroku 2 za pomocą zestawu SDK języka JavaScript.

## <a name="next-steps"></a>Następne kroki

Zapoznaj się ze sposobem osadzania z obszarów roboczych aplikacji dla klientów innych firm i swojej organizacji:

> [!div class="nextstepaction"]
>[Osadź dla klientów innych firm](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Osadź dla swojej organizacji](embed-sample-for-your-organization.md)
