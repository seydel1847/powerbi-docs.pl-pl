---
title: Konfigurowanie aplikacji mobilnych za pomocą usługi Microsoft Intune
description: Informacje o sposobie konfigurowania aplikacji mobilnych usługi Power BI przy użyciu usługi Microsoft Intune. W tym informacje o tym, jak dodać i wdrożyć aplikację. Oraz jak utworzyć zasady aplikacji mobilnych na potrzeby sterowania zabezpieczeniami.
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c33fcbdfa93e38283e17b0842e1242634664be7a
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/08/2018
---
# <a name="configure-mobile-apps-with-microsoft-intune"></a>Konfigurowanie aplikacji mobilnych za pomocą usługi Microsoft Intune
Usługa Microsoft Intune umożliwia organizacjom zarządzanie urządzeniami i aplikacjami. Aplikacje mobilne usługi Power BI dla systemów iOS i Android obsługują integrację z usługą Intune, aby umożliwić zarządzanie aplikacjami na urządzeniach oraz sterowanie zabezpieczeniami. Za pomocą zasad konfiguracji można zarządzać elementami na przykład przez wymaganie dostępowego kodu PIN, określanie sposobu obsługi danych przez aplikację, a nawet szyfrowanie danych aplikacji, kiedy aplikacja nie jest używana.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9HF-qsdQvHw?list=PLv2BtOtLblH1nPVPU2etFzTNmpz49dwXm" frameborder="0" allowfullscreen></iframe>

## <a name="general-mobile-device-management-configuration"></a>Ogólna konfiguracja zarządzania urządzeniami przenośnymi
Tego artykułu nie należy traktować jako pełnego przewodnika po konfiguracji usługi Microsoft Intune. Jeśli właśnie przeprowadzasz integrację z usługą Intune, istnieje kilka elementów, w przypadku których musisz upewnić się, że zostały skonfigurowane. [Dowiedz się więcej](https://technet.microsoft.com/library/jj676587.aspx)

Usługa Microsoft Intune może współistnieć z funkcją zarządzania urządzeniami przenośnymi (MDM) w usłudze Office 365. [Dowiedz się więcej](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365/)

W tym artykule przyjęto założenie, że usługa Intune jest skonfigurowana prawidłowo i że masz urządzenia zarejestrowane w usłudze Intune. Jeśli masz istniejące wspólnie z zarządzaniem urządzeniami Przenośnymi, urządzenie będzie wyświetlane jako zarejestrowane w ramach zarządzania urządzeniami przenośnymi, ale jest dostępne do zarządzania w usłudze Intune.

> [!NOTE]
> Jeśli korzystasz z aplikacji mobilnej usługi Power BI na urządzeniu z systemem iOS lub Android, a Twoja organizacja skonfigurowała funkcję zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune, odświeżanie danych w tle jest wyłączone. Przy następnym otwarciu aplikacji usługa Power BI odświeży dane na podstawie usługi Power BI w Internecie.
> 
> 

## <a name="step-1-get-the-url-for-the-application"></a>Krok 1: Uzyskiwanie adresu URL aplikacji
Przed utworzeniem aplikacji w usłudze Intune trzeba uzyskać adresy URL aplikacji. W przypadku systemu iOS można je uzyskać z programu iTunes. W przypadku systemu Android można je uzyskać ze strony aplikacji mobilnej usługi Power BI.

Zapisz adres URL, ponieważ będzie on potrzebny podczas tworzenia aplikacji.

### <a name="ios"></a>iOS
Aby uzyskać adres URL aplikacji dla systemu iOS, trzeba go pobrać z programu iTunes.

1. Otwórz program iTunes.
2. Wyszukaj usługę *Power BI*.
3. Aplikacja **Microsoft Power BI** powinna być wyświetlana na listach **aplikacji dla urządzenia iPhone** i **aplikacji dla urządzenia iPad**. Można skorzystać z dowolnej z nich, ponieważ adres URL będzie ten sam.
4. Wybierz listę rozwijaną **Pobierz** i wybierz pozycję **Kopiuj link**.
   
    ![](media/service-admin-mobile-intune/itunes-url.png)

Powinno to wyglądać mniej więcej tak.

    https://itunes.apple.com/us/app/microsoft-power-bi/id929738808?mt=8

### <a name="android"></a>Android
Adres URL do witryny Google Play można pobrać ze [strony aplikacji mobilnej usługi Power BI](https://powerbi.microsoft.com/mobile/). Kliknięcie ikony **Pobierz ze sklepu Google Play** spowoduje przejście na stronę aplikacji. Możesz skopiować adres URL z paska adresu przeglądarki. Powinno to wyglądać mniej więcej tak.

    https://play.google.com/store/apps/details?id=com.microsoft.powerbim

## <a name="step-2-create-a-mobile-application-management-policy"></a>Krok 2. Tworzenie zasad zarządzania aplikacjami mobilnymi
Zasady zarządzania aplikacjami mobilnymi umożliwiają wymuszanie elementów takich jak dostępowy kod PIN. Możesz je utworzyć w portalu usługi Intune. 

Możesz najpierw utworzyć aplikację lub zasady. Kolejność, w której zostaną dodane, nie ma znaczenia. Oba te elementy muszą jedynie istnieć przed wykonaniem kroku wdrażania.

1. Wybierz pozycje **Zasady** > **Zasady konfiguracji**.
   
    ![](media/service-admin-mobile-intune/intune-policy.png)
2. Wybierz pozycję **Dodaj...**.
3. W obszarze **Oprogramowanie** możesz wybrać pozycję Zarządzanie aplikacjami mobilnymi dla systemu Android lub systemu iOS. Aby szybko rozpocząć pracę, możesz wybrać opcję **Utwórz zasady z zalecanymi ustawieniami**. Możesz także utworzyć zasady niestandardowe.
4. Edytuj zasady, aby skonfigurować ograniczenia, które chcesz zastosować do aplikacji.

## <a name="step-3-create-the-application"></a>Krok 3. Tworzenie aplikacji
Aplikacja jest odwołaniem (lub pakietem) zapisanym w usłudze Intune na potrzeby wdrożenia. Konieczne będzie utworzenie aplikacji i odwołania do adresu URL aplikacji, który został uzyskany z usługi Google Play lub programu iTunes.

Możesz najpierw utworzyć aplikację lub zasady. Kolejność, w której zostaną dodane, nie ma znaczenia. Oba te elementy muszą jedynie istnieć przed wykonaniem kroku wdrażania.

1. Przejdź do portalu usługi Intune i z menu po lewej stronie wybierz pozycję **Aplikacje**.
2. Wybierz pozycję **Dodaj aplikację**. Spowoduje to uruchomienie aplikacji **Dodaj oprogramowanie**.

### <a name="ios"></a>iOS
1. Wybierz z listy rozwijanej pozycję **Zarządzana aplikacja systemu iOS ze sklepu App Store**.
2. Wprowadź adres URL aplikacji uzyskany w [kroku 1](#step-1-get-the-url-for-the-application) i wybierz przycisk **Dalej**.
   
    ![](media/service-admin-mobile-intune/intune-add-software-ios1.png)
3. Podaj **wydawcę**, **nazwę** i **opis**. Opcjonalnie możesz udostępnić **ikonę**. **Kategoria** jest określona dla aplikacji Portal firmy. Gdy wszystko będzie gotowe, wybierz przycisk **Dalej**.
4. Możesz zdecydować, czy chcesz opublikować aplikację jako **Dowolną** (ustawienie domyślne), **iPad** lub **iPhone**. Domyślnie zostanie wyświetlona jako **Dowolna** i będzie działać dla obu typów urządzeń. Aplikacja usługi Power BI ma ten sam adres URL dla urządzeń iPhone i iPad. Wybierz pozycję **Dalej**.
5. Wybierz przycisk **Przekaż**.

> [!NOTE]
> Aplikacja może nie być widoczna na liście aplikacji, dopóki strona nie zostanie odświeżona. Aby załadować ponownie stronę, możesz kliknąć pozycję **Przegląd** i wrócić do pozycji **Aplikacje**.
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-ios2.png)

### <a name="android"></a>Android
1. Z listy rozwijanej wybierz pozycję **Odnośnik zewnętrzny**.
2. Wprowadź adres URL aplikacji uzyskany w [kroku 1](#step-1-get-the-url-for-the-application) i wybierz przycisk **Dalej**.
   
    ![](media/service-admin-mobile-intune/intune-add-software-android1.png)
3. Podaj **wydawcę**, **nazwę** i **opis**. Opcjonalnie możesz udostępnić **ikonę**. **Kategoria** jest określona dla aplikacji Portal firmy. Gdy wszystko będzie gotowe, wybierz przycisk **Dalej**.
4. Wybierz przycisk **Przekaż**.

> [!NOTE]
> Aplikacja może nie być widoczna na liście aplikacji, dopóki strona nie zostanie odświeżona. Aby załadować ponownie stronę, możesz kliknąć pozycję **Przegląd** i wrócić do pozycji **Aplikacje**.
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-android2.png)

## <a name="step-4-deploy-the-application"></a>Krok 4. Wdrażanie aplikacji
Po dodaniu aplikacji należy ją wdrożyć, aby była dostępna dla użytkowników końcowych. Jest to krok, w którym utworzone zasady zostaną powiązane z aplikacją.

### <a name="ios"></a>iOS
1. Na ekranie aplikacje wybierz utworzoną aplikację. Następnie wybierz link **Zarządzanie wdrażaniem...**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios1.png)
2. Na ekranie **Wybieranie grup** możesz wybrać grupy, w których chcesz wdrożyć tę aplikację. Wybierz pozycję **Dalej**.
3. Na ekranie **Akcja wdrażania** możesz wybrać sposób, w jaki chcesz wdrożyć tę aplikację. W przypadku wybrania opcji **Dostępna instalacja** lub **Wymagana instalacja** aplikacja zostanie udostępniona użytkownikom w Portalu firmy, do instalacji na żądanie. Po dokonaniu wyboru wybierz pozycję **Dalej**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios2.png)
4. Na ekranie **Zarządzanie aplikacjami mobilnymi** możesz wybrać zasady zarządzania aplikacjami mobilnymi, które zostały utworzone w [kroku 2](#step-2-create-a-mobile-application-management-policy). Te zasady zostaną domyślnie wybrane, jeśli są jedynymi dostępnymi zasadami dla systemu iOS. Wybierz pozycję **Dalej**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios3.png)
5. Na ekranie **Profil sieci VPN** możesz wybrać zasady, jeśli są dostępne dla Twojej organizacji. Ustawieniem domyślnym jest **Brak**. Wybierz pozycję **Dalej**.
6. Na ekranie **Konfiguracja aplikacji mobilnych** możesz wybrać **Zasady konfiguracji aplikacji**, jeśli zostały utworzone. Ustawieniem domyślnym jest **Brak**. Nie jest to wymagane. Wybierz pozycję **Zakończ**.

Po wdrożeniu aplikacji powinna ona zostać wyświetlona z wartością **Tak** jako wdrożona na stronie aplikacji.

### <a name="android"></a>Android
1. Na ekranie aplikacje wybierz utworzoną aplikację. Następnie wybierz link **Zarządzanie wdrażaniem...**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android1.png)
2. Na ekranie **Wybieranie grup** możesz wybrać grupy, w których chcesz wdrożyć tę aplikację. Wybierz pozycję **Dalej**.
3. Na ekranie **Akcja wdrażania** możesz wybrać sposób, w jaki chcesz wdrożyć tę aplikację. W przypadku wybrania opcji **Dostępna instalacja** lub **Wymagana instalacja** aplikacja zostanie udostępniona użytkownikom w Portalu firmy, do instalacji na żądanie. Po dokonaniu wyboru wybierz pozycję **Dalej**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android2.png)
4. Na ekranie **Zarządzanie aplikacjami mobilnymi** możesz wybrać zasady zarządzania aplikacjami mobilnymi, które zostały utworzone w [kroku 2](#step-2-create-a-mobile-application-management-policy). Te zasady zostaną domyślnie wybrane, jeśli są jedynymi dostępnymi zasadami dla systemu Android. Wybierz pozycję **Zakończ**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android3.png)

Po wdrożeniu aplikacji powinna ona zostać wyświetlona z wartością **Tak** jako wdrożona na stronie aplikacji.

## <a name="step-5-install-the-application-on-a-device"></a>Krok 5. Instalowanie aplikacji na urządzeniu
Aplikację zainstalujesz za pomocą aplikacji Portal firmy. Jeśli aplikacja Portal firmy nie została jeszcze zainstalowana, możesz ją pobrać za pośrednictwem sklepu z aplikacjami dla platformy iOS lub Android. Do zalogowania się w Portalu firmy użyjesz swoich organizacyjnych danych logowania.

1. Otwórz aplikację Portal firmy.
2. Jeśli nie widzisz aplikacji Power BI jako polecanej aplikacji, wybierz pozycję **Aplikacje firmowe**.
   
    ![](media/service-admin-mobile-intune/intune-companyportal1.png)
3. Wybierz wdrożoną aplikację usługi Power BI.
   
    ![](media/service-admin-mobile-intune/intune-companyportal2.png)
4. Wybierz pozycję **Zainstaluj**.
   
    ![](media/service-admin-mobile-intune/intune-companyportal3.png)
5. Jeśli pracujesz w systemie iOS, spowoduje to wypchnięcie aplikacji do Twojego urządzenia. W oknie dialogowym wypychania wybierz pozycję **Zainstaluj**.
   
    ![](media/service-admin-mobile-intune/intune-companyportal5.png)

Po zainstalowaniu aplikacji zobaczysz, że jest ona **Zarządzana przez Twoją firmę**. Jeśli w zasadach włączono dostęp przy użyciu numeru PIN, zostanie wyświetlony poniższy ekran.

![](media/service-admin-mobile-intune/intune-powerbi-pin.png)

## <a name="next-steps"></a>Następne kroki
[Konfigurowanie i wdrażanie zasad zarządzania aplikacjami mobilnymi w konsoli usługi Microsoft Intune](https://technet.microsoft.com/library/dn878026.aspx)  
[Aplikacje Power BI dla urządzeń przenośnych](mobile-apps-for-mobile-devices.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

