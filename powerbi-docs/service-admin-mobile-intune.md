---
title: Konfigurowanie aplikacji mobilnych za pomocą usługi Microsoft Intune
description: Informacje o sposobie konfigurowania aplikacji mobilnych usługi Power BI przy użyciu usługi Microsoft Intune. W tym informacje o tym, jak dodać i wdrożyć aplikację. Oraz jak utworzyć zasady aplikacji mobilnych na potrzeby sterowania zabezpieczeniami.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/01/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 428ea77de2151f4ec3417f62819b3d6481c17ae2
ms.sourcegitcommit: 0611860a896e636ceeb6e30ce85243bfd8e7b61d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2018
ms.locfileid: "50909691"
---
# <a name="configure-mobile-apps-with-microsoft-intune"></a>Konfigurowanie aplikacji mobilnych za pomocą usługi Microsoft Intune

Usługa Microsoft Intune umożliwia organizacjom zarządzanie urządzeniami i aplikacjami. Aplikacje mobilne usługi Power BI dla systemów iOS i Android są zintegrowane z usługą Intune. Integracja umożliwia zarządzanie aplikacją na urządzeniach oraz kontrolowanie zabezpieczeń. Za pomocą zasad konfiguracji można zarządzać takimi zabezpieczeniami jak wymóg użycia dostępowego kodu PIN, sposób obsługi danych przez aplikację, a nawet szyfrowanie danych aplikacji, kiedy aplikacja nie jest używana.

## <a name="general-mobile-device-management-configuration"></a>Ogólna konfiguracja zarządzania urządzeniami przenośnymi

W tym artykule przyjęto założenie, że usługa Intune jest skonfigurowana prawidłowo i że masz urządzenia zarejestrowane w usłudze Intune. Artykułu nie należy traktować jako pełnego przewodnika po konfiguracji usługi Microsoft Intune. Aby uzyskać więcej informacji o usłudze Intune, zobacz temat [Co to jest Intune?](/intune/introduction-intune/)

Usługa Microsoft Intune może współistnieć z funkcją zarządzania urządzeniami przenośnymi (MDM) w usłudze Office 365. Jeśli korzystasz z oprogramowania MDM, urządzenie będzie wyświetlane jako zarejestrowane w ramach tego oprogramowania, ale pozostanie dostępne do zarządzania w usłudze Intune.

> [!NOTE]
> Po skonfigurowaniu usługi Intune odświeżanie danych w tle jest wyłączone w aplikacji mobilnej Power BI na urządzeniu z systemem iOS lub Android. Aplikacja Power BI odświeża dane z usługi Power BI online po otwarciu aplikacji.

## <a name="step-1-get-the-url-for-the-application"></a>Krok 1. Uzyskiwanie adresu URL aplikacji

Przed utworzeniem aplikacji w usłudze Intune trzeba uzyskać adresy URL aplikacji. W przypadku systemu iOS można je uzyskać z programu iTunes. W przypadku systemu Android można je uzyskać ze strony aplikacji mobilnej usługi Power BI.

Zapisz adres URL, ponieważ będzie on potrzebny podczas tworzenia aplikacji.

### <a name="get-ios-url"></a>Uzyskiwanie adresu URL dla systemu iOS

Aby uzyskać adres URL aplikacji dla systemu iOS, trzeba go pobrać z programu iTunes.

1. Otwórz program iTunes.

1. Wyszukaj usługę *Power BI*.

1. Aplikacja **Microsoft Power BI** powinna być wyświetlana na listach **aplikacji dla urządzenia iPhone** i **aplikacji dla urządzenia iPad**. Można skorzystać z dowolnej z nich, ponieważ adres URL będzie taki sam.

1. Wybierz listę rozwijaną **Pobierz** i wybierz pozycję **Kopiuj link**.

    ![Adres URL aplikacji z programu iTunes](media/service-admin-mobile-intune/itunes-url.png)

Powinien on wyglądać podobnie do następującego: *https://itunes.apple.com/us/app/microsoft-power-bi/id929738808?mt=8*.

### <a name="get-android-url"></a>Uzyskiwanie adresu URL dla systemu Android

Adres URL z Google Play można pobrać ze [strony aplikacji mobilnej usługi Power BI](https://powerbi.microsoft.com/mobile/). Wybierz pozycję **Pobierz z Google Play**, aby przejść na stronę aplikacji. Możesz skopiować adres URL z paska adresu przeglądarki. Powinien on wyglądać podobnie do następującego: *https://play.google.com/store/apps/details?id=com.microsoft.powerbim*.

## <a name="step-2-create-a-mobile-application-management-policy"></a>Krok 2. Tworzenie zasad zarządzania aplikacjami mobilnymi

Zasady zarządzania aplikacjami mobilnymi umożliwiają wymuszanie elementów takich jak dostępowy kod PIN. Możesz je utworzyć w portalu usługi Intune.

Możesz najpierw utworzyć aplikację lub zasady. Kolejność, w której zostaną dodane, nie ma znaczenia. Oba te elementy muszą jedynie istnieć przed wykonaniem kroku wdrażania.

1. W portalu usługi Intune wybierz kolejno pozycje **Zasady** > **Zasady konfiguracji**.

    ![Portal usługi Intune](media/service-admin-mobile-intune/intune-policy.png)

1. Wybierz pozycję **Dodaj...**.

1. W obszarze **Oprogramowanie** możesz wybrać pozycję Zarządzanie aplikacjami mobilnymi dla systemu Android lub systemu iOS. Aby szybko rozpocząć pracę, możesz wybrać opcję **Utwórz zasady z zalecanymi ustawieniami**. Możesz także utworzyć zasady niestandardowe.

1. Edytuj zasady, aby skonfigurować ograniczenia, które chcesz zastosować do aplikacji.

## <a name="step-3-create-the-application"></a>Krok 3. Tworzenie aplikacji

Aplikacja jest odwołaniem (lub pakietem) zapisanym w usłudze Intune na potrzeby wdrożenia. Konieczne będzie utworzenie aplikacji i odwołanie się do adresu URL aplikacji, który został uzyskany z Google Play lub iTunes.

Możesz najpierw utworzyć aplikację lub zasady. Kolejność, w której zostaną dodane, nie ma znaczenia. Oba te elementy muszą jedynie istnieć przed wykonaniem kroku wdrażania.

1. Przejdź do portalu usługi Intune i z menu po lewej stronie wybierz pozycję **Aplikacje**.

1. Wybierz pozycję **Dodaj aplikację**. Spowoduje to uruchomienie aplikacji **Dodaj oprogramowanie**.

### <a name="create-for-ios"></a>Tworzenie aplikacji dla systemu iOS

1. Wybierz z listy rozwijanej pozycję **Zarządzana aplikacja systemu iOS ze sklepu App Store**.

1. Wprowadź adres URL aplikacji uzyskany w [kroku 1](#step-1-get-the-URL-for-the-application) i kliknij przycisk **Dalej**.

    ![Konfigurowanie oprogramowania: iOS](media/service-admin-mobile-intune/intune-add-software-ios1.png)

1. Podaj **wydawcę**, **nazwę** i **opis**. Opcjonalnie możesz udostępnić **ikonę**. **Kategoria** jest określona dla aplikacji Portal firmy. Gdy wszystko będzie gotowe, wybierz przycisk **Dalej**.

1. Możesz zdecydować, czy chcesz opublikować aplikację jako **Dowolną** (ustawienie domyślne), **iPad** lub **iPhone**. Domyślnie zostanie wyświetlona jako **Dowolna** i będzie działać dla obu typów urządzeń. Adres URL aplikacji Power BI jest taki sam dla urządzeń iPhone i iPad. Wybierz pozycję **Dalej**.

1. Wybierz przycisk **Przekaż**.

1. Jeśli nie widzisz aplikacji na liście, odśwież stronę: przejdź do pozycji **Przegląd**, a następnie wróć na kartę **Aplikacje**.

    ![Karta Aplikacje](media/service-admin-mobile-intune/intune-add-software-ios2.png)

### <a name="create-for-android"></a>Tworzenie aplikacji dla systemu Android

1. Z listy rozwijanej wybierz pozycję **Odnośnik zewnętrzny**.

1. Wprowadź adres URL aplikacji uzyskany w [kroku 1](#step-1-get-the-URL-for-the-application) i kliknij przycisk **Dalej**.

    ![Konfigurowanie oprogramowania: Android](media/service-admin-mobile-intune/intune-add-software-android1.png)

1. Podaj **wydawcę**, **nazwę** i **opis**. Opcjonalnie możesz udostępnić **ikonę**. **Kategoria** jest określona dla aplikacji Portal firmy. Gdy wszystko będzie gotowe, wybierz przycisk **Dalej**.

1. Wybierz przycisk **Przekaż**.

1. Jeśli nie widzisz aplikacji na liście, odśwież stronę: przejdź do pozycji **Przegląd**, a następnie wróć na kartę **Aplikacje**.

    ![Karta Aplikacje](media/service-admin-mobile-intune/intune-add-software-android2.png)

## <a name="step-4-deploy-the-application"></a>Krok 4. Wdrażanie aplikacji

Po dodaniu aplikacji należy ją wdrożyć, aby była dostępna dla użytkowników końcowych. Jest to krok, w którym utworzone zasady zostaną powiązane z aplikacją.

### <a name="deploy-for-ios"></a>Wdrażanie aplikacji dla systemu iOS

1. Na ekranie aplikacje wybierz utworzoną aplikację. Następnie wybierz link **Zarządzanie wdrażaniem...**.

    ![Zarządzanie wdrożeniem](media/service-admin-mobile-intune/intune-deploy-ios1.png)

1. Na ekranie **Wybieranie grup** możesz wybrać grupy, w których chcesz wdrożyć tę aplikację. Wybierz pozycję **Dalej**.

1. Na ekranie **Akcja wdrażania** możesz wybrać sposób, w jaki chcesz wdrożyć tę aplikację. W przypadku wybrania opcji **Dostępna instalacja** lub **Wymagana instalacja** aplikacja zostanie udostępniona użytkownikom w Portalu firmy, do instalacji na żądanie. Po dokonaniu wyboru wybierz pozycję **Dalej**.

    ![Akcja wdrażania](media/service-admin-mobile-intune/intune-deploy-ios2.png)

1. Na ekranie **Zarządzanie aplikacjami mobilnymi** możesz wybrać zasady zarządzania aplikacjami mobilnymi, które zostały utworzone w [kroku 2](#step-2-create-a-mobile-application-management-policy). Te zasady zostaną domyślnie wybrane, jeśli są jedynymi dostępnymi zasadami dla systemu iOS. Wybierz pozycję **Dalej**.

    ![Zarządzanie aplikacjami mobilnymi](media/service-admin-mobile-intune/intune-deploy-ios3.png)

1. Na ekranie **Profil sieci VPN** możesz wybrać zasady, jeśli są dostępne dla Twojej organizacji. Ustawieniem domyślnym jest **Brak**. Wybierz pozycję **Dalej**.

1. Na ekranie **Konfiguracja aplikacji mobilnych** możesz wybrać **Zasady konfiguracji aplikacji**, jeśli zostały utworzone. Ustawieniem domyślnym jest **Brak**. Nie jest to wymagane. Wybierz pozycję **Zakończ**.

Po wdrożeniu aplikacji powinna ona zostać wyświetlona z wartością **Tak** jako wdrożona na stronie aplikacji.

### <a name="deploy-for-android"></a>Wdrażanie aplikacji dla systemu Android

1. Na ekranie aplikacje wybierz utworzoną aplikację. Następnie wybierz link **Zarządzanie wdrażaniem...**.

    ![Zarządzanie wdrożeniem](media/service-admin-mobile-intune/intune-deploy-android1.png)
1. Na ekranie **Wybieranie grup** możesz wybrać grupy, w których chcesz wdrożyć tę aplikację. Wybierz pozycję **Dalej**.

1. Na ekranie **Akcja wdrażania** możesz wybrać sposób, w jaki chcesz wdrożyć tę aplikację. W przypadku wybrania opcji **Dostępna instalacja** lub **Wymagana instalacja** aplikacja zostanie udostępniona użytkownikom w Portalu firmy, do instalacji na żądanie. Po dokonaniu wyboru wybierz pozycję **Dalej**.

    ![Akcja wdrażania](media/service-admin-mobile-intune/intune-deploy-android2.png)

1. Na ekranie **Zarządzanie aplikacjami mobilnymi** możesz wybrać zasady zarządzania aplikacjami mobilnymi, które zostały utworzone w [kroku 2](#step-2-create-a-mobile-application-management-policy). Te zasady zostaną domyślnie wybrane, jeśli są jedynymi dostępnymi zasadami dla systemu Android. Wybierz pozycję **Zakończ**.

    ![Zarządzanie aplikacjami mobilnymi](media/service-admin-mobile-intune/intune-deploy-android3.png)

Po wdrożeniu aplikacji powinna ona zostać wyświetlona z wartością **Tak** jako wdrożona na stronie aplikacji.

## <a name="step-5-install-the-application-on-a-device"></a>Krok 5. Instalowanie aplikacji na urządzeniu

Aplikacja jest instalowana za pomocą aplikacji *Portal firmy*. Jeśli aplikacja Portal firmy nie została jeszcze zainstalowana, możesz ją pobrać za pośrednictwem sklepu z aplikacjami dla platformy iOS lub Android. Do zalogowania się w Portalu firmy użyjesz swoich organizacyjnych danych logowania.

1. Otwórz aplikację Portal firmy.

1. Jeśli nie widzisz aplikacji Power BI jako polecanej aplikacji, wybierz pozycję **Aplikacje firmowe**.

    ![Aplikacje firmowe](media/service-admin-mobile-intune/intune-companyportal1.png)

1. Wybierz wdrożoną aplikację Power BI.

    ![Aplikacja Power BI](media/service-admin-mobile-intune/intune-companyportal2.png)

1. Wybierz pozycję **Zainstaluj**.

    ![Instalowanie aplikacji](media/service-admin-mobile-intune/intune-companyportal3.png)

1. Jeśli pracujesz w systemie iOS, spowoduje to wypchnięcie aplikacji do Twojego urządzenia. W oknie dialogowym wypychania wybierz pozycję **Zainstaluj**.

    ![Instalacja aplikacji](media/service-admin-mobile-intune/intune-companyportal5.png)

1. Po zainstalowaniu aplikacji zobaczysz, że jest ona **zarządzana przez Twoją firmę**. Jeśli w zasadach włączono dostęp przy użyciu numeru PIN, zostanie wyświetlony poniższy ekran.

    ![Wprowadzanie numeru PIN](media/service-admin-mobile-intune/intune-powerbi-pin.png)

## <a name="next-steps"></a>Następne kroki

[Konfigurowanie i wdrażanie zasad zarządzania aplikacjami mobilnymi w konsoli usługi Microsoft Intune](/intune/app-protection-policies/)  

[Aplikacje Power BI dla urządzeń przenośnych](consumer/mobile/mobile-apps-for-mobile-devices.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)  