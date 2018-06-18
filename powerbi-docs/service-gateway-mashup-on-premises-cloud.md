---
title: Scalanie lub dołączanie lokalnych źródeł danych i źródeł danych w chmurze
description: Użyj lokalnej bramy danych, aby scalać lub dołączać źródła danych lokalne i w chmurze w tym samym zapytaniu.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 06/06/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 3550a3fc0cfc51b61e1d7e51a50c2a36325f2388
ms.sourcegitcommit: 49570ab8f5b5cd5bab4cd388f4281b1372bcb80b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2018
ms.locfileid: "35250656"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>Scalanie lub dołączanie lokalnych źródeł danych i źródeł danych w chmurze

Lokalna brama danych umożliwia scalanie lub dołączanie lokalnych źródeł danych i źródeł danych w chmurze w jednym zapytaniu. Jest to przydatne, gdy chcesz łączyć dane z wielu źródeł bez konieczności używania oddzielnych zapytań.

## <a name="prerequisites"></a>Wymagania wstępne

- [Brama zainstalowana](service-gateway-install.md) na komputerze lokalnym.
- Plik programu Power BI Desktop z zapytaniami, które łączą lokalne źródła danych i źródła danych w chmurze.

1. W prawym górnym rogu ekranu usługi Power BI wybierz ikonę koła zębatego ![Ikona koła zębatego Ustawienia](media/service-gateway-mashup-on-premises-cloud/icon-gear.png) > **Zarządzaj bramami**.

    ![Zarządzaj bramami](media/service-gateway-mashup-on-premises-cloud/manage-gateways.png)

2. Wybierz bramę, którą chcesz skonfigurować.

3. W obszarze **Ustawienia klastra bramy** wybierz pozycję **Zezwalaj na odświeżanie źródeł danych chmury użytkownika przez ten klaster bramy** > **Zastosuj**.

    ![Odświeżanie przez ten klaster bramy](media/service-gateway-mashup-on-premises-cloud/refresh-gateway-cluster.png)

4. W tym klastrze bramy dodaj wszelkie [lokalne źródła danych](service-gateway-enterprise-manage-scheduled-refresh.md#add-a-data-source) używane w zapytaniach. Nie trzeba dodawać tutaj źródeł danych w chmurze.

4. Przekaż do usługi Power BI plik programu Power BI Desktop z zapytaniami, które łączą lokalne źródła danych i źródła danych w chmurze.

5. Na stronie **Ustawienia zestawu danych** dla nowego zestawu danych:

    - W przypadku źródła lokalnego wybierz bramę skojarzoną z tym źródłem danych.

    - W obszarze **Poświadczenia źródła danych** edytuj poświadczenia źródła danych w chmurze stosownie do potrzeb.

    ![Ustawienia zestawu danych](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

6. Po ustawieniu poświadczeń w chmurze możesz odświeżyć zestaw danych za pomocą opcji **Odśwież teraz** lub zaplanować jego okresowe odświeżanie.


## <a name="next-steps"></a>Następne kroki

Aby dowiedzieć się więcej na temat odświeżania danych dla bram, zobacz [Używanie źródła danych do zaplanowanego odświeżania](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh).