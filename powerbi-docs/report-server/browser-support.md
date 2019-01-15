---
title: Obsługa przeglądarek dla serwera raportów usługi Power BI
description: Dowiedz się więcej o obsługiwanych wersjach przeglądarek do zarządzania i wyświetlania serwera raportów serwera Power BI i kontrolek przeglądarki raportów.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 10/24/2018
ms.author: maghan
ms.openlocfilehash: 84f159e38f8fee239e8fca3280d852e456fb61a6
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54274909"
---
# <a name="browser-support-for-power-bi-report-server"></a>Obsługa przeglądarek dla serwera raportów usługi Power BI
Dowiedz się więcej o obsługiwanych wersjach przeglądarek do zarządzania i wyświetlania serwera raportów serwera Power BI i kontrolek przeglądarki raportów.

## <a name="browser-requirements-for-the-web-portal"></a>Wymagania dotyczące przeglądarki dla portalu internetowego
Poniżej znajduje się bieżąca lista przeglądarek obsługiwanych dla portalu internetowego.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9–10.11*

* Apple Safari (+)
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple iOS**  
*Urządzenia iPhone i iPad z systemem iOS 10*

* Apple Safari (+)

**System Google Android**  
*Telefony i tablety z systemem Android 4.4 (KitKat) lub nowszym*

* Google Chrome (+)
  
  **(+)** Najnowsza publicznie wydana wersja

## <a name="browser-requirements-for-the-report-viewer-web-control-2015"></a>Wymagania dotyczące przeglądarki dla kontrolki internetowej przeglądarki raportów (2015)
Poniżej znajduje się bieżąca lista przeglądarek obsługiwanych za pomocą internetowej kontrolki przeglądarki raportów. Przeglądarka raportów obsługuje wyświetlanie raportów z portalu internetowego.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9–10.11*

* Apple Safari (+)
  
  **(+)** Najnowsza publicznie wydana wersja

### <a name="authentication-requirements"></a>Wymagania dotyczące uwierzytelniania
Przeglądarki obsługują określone schematy uwierzytelniania, które muszą być obsługiwane przez serwer raportów, aby żądanie klienta się powiodło. W poniższej tabeli przedstawiono domyślne typy uwierzytelniania obsługiwane przez każdą przeglądarkę działającą w systemie operacyjnym Windows.

| **Typ przeglądarki** | **Obsługuje** | **Przeglądarka domyślna** | **Serwer domyślny** |
| --- | --- | --- | --- |
| **Microsoft Edge** (+) |Negotiate, Kerberos, NTLM, Basic |Negotiate |Tak. Domyślne ustawienia uwierzytelniania działają w przeglądarce Edge. |
| **Microsoft Internet Explorer** |Negotiate, Kerberos, NTLM, Basic |Negotiate |Tak. Domyślne ustawienia uwierzytelniania działają w przeglądarce Internet Explorer. |
| **Google Chrome**(+) |Negotiate, NTLM, Basic |Negotiate |Tak. Domyślne ustawienia uwierzytelniania działają w przeglądarce Chrome. |
| **Mozilla Firefox**(+) |NTLM, Basic |NTLM |Tak. Domyślne ustawienia uwierzytelniania działają w przeglądarce Firefox. |
| **Apple Safari**(+) |NTLM, Basic |Basic |Tak. Domyślne ustawienia uwierzytelniania działają w przeglądarce Safari. |

 **(+)** Najnowsza publicznie wydana wersja

### <a name="script-requirements-for-viewing-reports"></a>Wymagania dotyczące skryptu do wyświetlania raportów
Aby użyć przeglądarki raportów, skonfiguruj przeglądarkę, aby uruchamiała skrypty.

Jeśli nie jest włączona obsługa skryptów, po otwarciu raportu zobaczysz komunikat o błędzie podobny do poniższego:

```
Your browser does not support scripts or has been configured to not allow scripts to run. Click here to view this report without scripts
```

 Jeśli postanowisz wyświetlić raport bez obsługi skryptów, raport jest renderowany w języku HTML bez możliwości przeglądarki raportów, takich jak pasek narzędzi raportu i mapa dokumentu.

> [!NOTE]
> Pasek narzędzi raportu jest częścią składnika przeglądarki HTML. Domyślnie pasek narzędzi jest wyświetlany na początku każdego raportu, który jest renderowany w oknie przeglądarki. Przeglądarka raportów zawiera funkcje obejmujące możliwość wyszukiwania w raporcie informacji, przewijania do określonej strony i dostosowywania rozmiaru strony do celów przeglądania. Aby uzyskać więcej informacji na temat paska narzędzi raportu lub przeglądarki HTML, zobacz [Przeglądarka HTML i pasek narzędzi raportu](https://docs.microsoft.com/sql/reporting-services/html-viewer-and-the-report-toolbar).
> 
> 

## <a name="browser-support-for-report-viewer-web-server-controls-in-visual-studio"></a>Obsługa kontrolek serwera internetowego przeglądarki raportów w programie Visual Studio w przeglądarce
Kontrolki serwera internetowego przeglądarki raportów służą do osadzania funkcji raportu w aplikacji internetowej ASP.NET. Aby uzyskać więcej informacji dotyczących sposobu uzyskania kontrolki przeglądarki raportów, zobacz [Integrowanie usług raportowania za pomocą kontrolek przeglądarki raportów — wprowadzenie](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started).

Użyj przeglądarki, która ma włączoną obsługę skryptów. Jeśli przeglądarka nie może uruchamiać skryptów, nie możesz wyświetlić raportu.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)
  
  **(+)** Najnowsza publicznie wydana wersja

## <a name="next-steps"></a>Następne kroki
[Omówienie dla administratorów](admin-handbook-overview.md)  
[Instalacja serwera raportów usługi Power BI](install-report-server.md)  
[Pobieranie programu Report Builder](https://www.microsoft.com/download/details.aspx?id=53613)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

