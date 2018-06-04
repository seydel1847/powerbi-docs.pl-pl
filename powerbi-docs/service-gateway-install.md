---
title: Instalowanie bramy usługi Power BI
description: Dowiedz się, jak zainstalować bramę, aby umożliwić nawiązywanie połączenia z danymi lokalnymi w usłudze Power BI.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 04/18/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 936e794b187366e91cf550c16379216ddf1fbf36
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34298555"
---
# <a name="install-a-gateway-for-power-bi"></a>Instalowanie bramy usługi Power BI

Brama usługi Power BI to oprogramowanie instalowane w sieci lokalnej. Ułatwia ono dostęp do danych w tej sieci. Jak opisano w [omówieniu](service-gateway-getting-started.md), bramę można zainstalować w trybie osobistym lub trybie standardowym (opcja zalecana). W trybie standardowym można zainstalować bramę autonomiczną lub dodać bramę do *klastra*. Takie rozwiązanie jest zalecane w przypadku wysokiej dostępności. W tym artykule opisano, jak zainstalować bramę standardową, a następnie dodać inną bramę, aby utworzyć klaster.

Jeśli nie masz konta usługi Power BI, na początku [zacznij korzystać z bezpłatnej wersji próbnej](https://app.powerbi.com/signupredirect?pbi_source=web).


## <a name="download-and-install-a-gateway"></a>Pobieranie i instalowanie bramy

Brama działa na komputerze, na którym ją zainstalowano, jest więc istotne, aby zainstalować ją na zawsze włączonym komputerze. W celu uzyskania lepszej wydajności i niezawodności zalecamy, aby komputer znajdował się w sieci przewodowej, a nie w sieci bezprzewodowej.

1. W usłudze Power BI w prawym górnym rogu wybierz **ikonę pobierania** ![Ikona pobierania](media/service-gateway-install/icon-download.png) > **Brama danych**.

    ![Brama danych](media/service-gateway-install/data-gateway.png)

2. Na stronie pobierania wybierz przycisk **POBIERZ BRAMĘ**.

3. Wybierz pozycję **Dalej**.     

    ![Instalator bramy danych](media/service-gateway-install/gateway-installer.png)

4. Wybierz pozycję **Lokalna brama danych (zalecane)** > **Dalej**.

    ![Typ bramy](media/service-gateway-install/gateway-type.png)

5. Zachowaj domyślną ścieżkę instalacji i zaakceptuj postanowienia > **Zainstaluj**.

    ![Ścieżka instalacji](media/service-gateway-install/install-path.png)

6. Wprowadź konto używane do logowania do usługi Power BI > **Zaloguj**.

    ![Adres e-mail](media/service-gateway-install/email-address.png)

    Brama jest kojarzona z indywidualnym kontem usługi Power BI, a zarządzanie bramami odbywa się w obrębie usługi Power BI. Obecnie użytkownik jest zalogowany do swojego konta.

7. Wybierz pozycję **Zarejestruj nową bramę na tym komputerze** > **Dalej**.

    ![Rejestrowanie bramy](media/service-gateway-install/register-gateway.png)

8. Wprowadź nazwę bramy (musi być unikatowa w dzierżawie) i klucz odzyskiwania. Klucz ten jest wymagany, gdy zajdzie potrzeba przeniesienia lub odzyskania bramy. Wybierz pozycję **Skonfiguruj**.

    ![Konfigurowanie bramy](media/service-gateway-install/configure-gateway.png)

    Zwróć uwagę na opcję **Dodaj do istniejącego klastra bramy**. Użyjemy tej opcji w następnej sekcji tego artykułu.

9. Przejrzyj informacje w oknie końcowym. Zwróć uwagę, że brama jest dostępna dla usługi Power BI, a także usług PowerApps i Flow, ponieważ użyto tego samego konta dla wszystkich trzech rozwiązań. Wybierz pozycję **Zamknij**.

    ![Ekran podsumowania](media/service-gateway-install/summary-screen.png)

Po pomyślnym zainstalowaniu bramy można dodać inną bramę, aby utworzyć klaster.


## <a name="add-another-gateway-to-create-a-cluster"></a>Dodawanie innej bramy w celu utworzenia klastra

Klaster umożliwia administratorom bramy uniknąć pojedynczego punktu awarii podczas dostępu do danych lokalnych. Jeśli brama podstawowa jest niedostępna, można dodać kolejną bramę, do której kierowane są żądania danych itd. Na danym komputerze można zainstalować tylko jedną bramę standardową, dlatego drugą bramę dla klastra należy zainstalować na innym komputerze. Takie rozwiązanie ma sens, ponieważ potrzebujesz nadmiarowości w klastrze.

Klastry bramy o wysokiej dostępności wymagają aktualizacji z listopada 2017 r. (lub nowszej) dla lokalnej bramy danych.

1. Pobierz bramę na inny komputer i zainstaluj ją.

2. Po zalogowaniu do konta usługi Power BI zarejestruj bramę. Wybierz pozycję **Dodaj do istniejącego klastra**. W obszarze **Dostępne klastry bramy** wybierz pierwszą zainstalowaną bramę (*bramę główną*) i wprowadź klucz odzyskiwania dla tej bramy. Wybierz pozycję **Skonfiguruj**.

    ![Dodawanie bramy do klastra](media/service-gateway-install/add-cluster.png)


## <a name="next-steps"></a>Następne kroki

[Zarządzanie bramą usługi Power BI](service-gateway-manage.md)

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)