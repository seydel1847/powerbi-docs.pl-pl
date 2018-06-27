---
title: Rozwiązywanie problemu „Firmowy certyfikat SSL nie jest zaufany”
description: Podczas logowania do aplikacji Power BI w systemie Android może zostać wyświetlony komunikat „Nie można przeprowadzić uwierzytelnienia, ponieważ certyfikat SSL nie jest zaufany”
.": ''
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: maggies
ms.openlocfilehash: 494e148a62675aab1a6e799c4e4b61f022483d9f
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34444962"
---
# <a name="fixing-corporate-ssl-certificate-is-untrusted---power-bi"></a>Rozwiązywanie problemu „Firmowy certyfikat SSL nie jest zaufany” — Power BI
Podczas logowania do aplikacji Microsoft Power BI w systemie Android może zostać wyświetlony komunikat „Nie można przeprowadzić uwierzytelnienia, ponieważ certyfikat SSL nie jest zaufany przez to urządzenie. Skontaktuj się z administratorem IT w swojej firmie”. 

Dalsze czynności zwykle zależą od systemu operacyjnego na urządzeniu z systemem Android, ale istnieje kilka innych problemów, które mogą być przyczyną tego błędu.

## <a name="on-android-7-or-later"></a>W systemie Android 7 lub nowszym
Wyszukaj aktualizacje aplikacji o nazwie **Chrome** i zainstaluj je.

## <a name="on-android-6-and-earlier"></a>W systemie Android 6 i starszych
Urządzenie może potrzebować zaktualizowanej wersji aplikacji System Webview. Być może jest już zainstalowana na urządzeniu i wystarczy tylko kliknąć przycisk **Aktualizuj**.

Jeśli aplikacja System Webview nie jest zainstalowana na urządzeniu:

1. Na urządzeniu z systemem Android zamknij usługę Power BI.
2. Otwórz sklep Google Play i wyszukaj aplikację **System Webview** firmy Google Inc.
3. Zainstaluj ją.
4. Ponowne uruchom aplikację Power BI i zaloguj się.

## <a name="time-zone-settings"></a>Ustawienia strefy czasowej
Ustawienia strefy czasowej na urządzeniu mogą być nieprawidłowe. 

Przejdź do pozycji **Ustawienia** > **System** > **Data i godzina** i sprawdź je.

## <a name="custom-authentication-server"></a>Niestandardowy serwer uwierzytelniania
Jeśli używasz niestandardowego serwera uwierzytelniania, certyfikat SSL na firmowym serwerze uwierzytelniania może być nieprawidłowy. Skontaktuj się z administratorem IT w firmie, aby uzyskać pomoc.

## <a name="next-steps"></a>Następne kroki
* [Pobieranie aplikacji systemu Android](http://go.microsoft.com/fwlink/?LinkID=544867) ze sklepu z aplikacjami dla systemu Android.
* Masz pytania? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

