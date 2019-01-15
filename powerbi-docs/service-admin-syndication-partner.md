---
title: Nie można dodać usługi Power BI do partnera usługi O365
description: Nie można dodać usługi Power BI do partnera syndykacji usługi Office 365. Model syndykowany to model zakupów używany w kontekście usługi Office 365.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/01/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: f1244535259de2a5b5726d295a64229a0f92f02b
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296480"
---
# <a name="unable-to-add-power-bi-to-office-365-partner-subscription"></a>Nie można dodać usługi Power BI do subskrypcji partnera usługi Office 365

Firmy mogą sprzedawać usługę Office 365 w postaci powiązanej i zintegrowanej z ich własnymi rozwiązaniami, co zapewnia klientom końcowym jeden punkt kontaktu w zakresie zakupów, rozliczeń i pomocy technicznej.

Jeśli interesuje Cię uzyskanie usługi Power BI — oprócz posiadanej subskrypcji usługi Office 365 — zalecamy skontaktowanie się z odpowiednim partnerem. Jeśli partner aktualnie nie oferuje usługi Power BI, możesz skorzystać z innych opcji.

## <a name="work-with-your-partner-to-purchase-power-bi"></a>Współpraca z partnerem w celu zakupienia usługi Power BI

Jeśli chcesz kupić subskrypcję usługi Power BI Pro lub Power BI Premium, razem ze swoim partnerem rozważ dostępne opcje:

* Partner zgadza się dodać usługę Power BI do swojej oferty, aby umożliwić Ci jej zakup u siebie.

* Partner może zaproponować Ci model pozwalający na zakup usługi Power BI bezpośrednio w firmie Microsoft lub od innego partnera, który ma w swojej ofercie usługę Power BI.

## <a name="purchase-from-microsoft-or-another-channel"></a>Zakup od firmy Microsoft lub za pośrednictwem innego kanału

W zależności od relacji z partnerem możesz mieć opcję zakupu usługi Power BI bezpośrednio od firmy Microsoft lub innego partnera. Możesz sprawdzić, czy masz możliwość dodawania subskrypcji usługi Power BI w portalu administracyjnym usługi Office 365 (wymaga to członkostwa w roli administratora globalnego lub administratora rozliczeń).

1. Przejdź do [portalu administracyjnego usługi Office 365](https://admin.microsoft.com/AdminPortal/Home#/homepage).

1. W menu po lewej stronie otwórz obszar **Rozliczenia**:

    * Jeśli widzisz pozycję **Subskrypcje**, możesz kupić usługę bezpośrednio od firmy Microsoft lub możesz skontaktować się z partnerem oferującym usługę Power BI.

        ![Rozliczenia — z subskrypcjami](media/service-admin-syndication-partner/billingsub.png)

    * Jeśli nie widzisz pozycji **Subskrypcje**, nie możesz kupić usługi bezpośrednio od firmy Microsoft ani od innego partnera.

Jeśli partner nie oferuje usługi Power BI i nie możesz kupić jej bezpośrednio od firmy Microsoft ani innego partnera, rozważ możliwość utworzenia konta bezpłatnej wersji próbnej.

## <a name="sign-up-for-a-free-trial"></a>Tworzenie konta bezpłatnej wersji próbnej

Możesz utworzyć konto bezpłatnej wersji próbnej usługi Power BI Pro. Jeśli na końcu okresu próbnego nie kupisz usługi Power BI Pro, będziesz nadal mieć bezpłatną licencję, która oferuje wiele funkcji usługi Power BI. Aby uzyskać więcej informacji, zobacz [Funkcje usługi Power BI według typu licencji](service-features-license-type.md).

### <a name="enable-ad-hoc-subscriptions"></a>Włączanie subskrypcji ad-hoc

Domyślnie opcja tworzenia konta przez użytkowników indywidualnych (znana także jako subskrypcja ad-hoc) jest wyłączona. W takim przypadku podczas próby utworzenia konta jest wyświetlany następujący komunikat: *Twój dział IT wyłączył rejestrowanie w usłudze Microsoft Power BI*.

![Obraz komunikatu z przeprosinami](media/service-admin-syndication-partner/sorry.png)

Aby włączyć subskrypcje ad-hoc, możesz skontaktować się ze swoim partnerem i poprosić o ich włączenie. Jeśli jesteś administratorem dzierżawy i wiesz, jak używać poleceń programu PowerShell usługi Azure Active Directory, możesz samodzielnie włączyć subskrypcje ad-hoc. [Azure Active Directory PowerShell dla programu Graph](/powershell/azure/active-directory/install-adv2/)

1. Zaloguj się do usługi Azure Active Directory przy użyciu poświadczeń usługi Office 365. Pierwszy wiersz poniższego skryptu będzie monitować o podanie poświadczeń. Drugi wiersz spowoduje nawiązanie połączenia z usługą Azure Active Directory.

    ```powershell
    $msolcred = get-credential
    connect-msolservice -credential $msolcred
    ```

    ![Wprowadzanie poświadczeń](media/service-admin-syndication-partner/aad-signin.png)

1. Po zalogowaniu się uruchom następujące polecenie, aby sprawdzić bieżące ustawienie elementu `AllowAdHocSubscriptions`.

    ```powershell
    Get-MsolCompanyInformation
    ```

1. Uruchom poniższe polecenie, aby włączyć bezpłatną rejestrację.

    ```powershell
    Set-MsolCompanySettings -AllowAdHocSubscriptions $true
    ```

## <a name="next-steps"></a>Następne kroki

[Licencjonowanie usługi Power BI w organizacji](service-admin-licensing-organization.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)