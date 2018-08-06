---
title: Wstrzymywanie i uruchamianie pojemności usługi Power BI Embedded w witrynie Azure Portal | Microsoft Docs
description: Ten artykuł zawiera szczegółowe instrukcje dotyczące wstrzymywania i uruchamiania pojemności usługi Power BI Embedded na platformie Microsoft Azure.
services: power-bi-embedded
author: markingmyname
ms.author: maghan
manager: kfile
editor: ''
tags: ''
ms.service: power-bi-embedded
ms.topic: conceptual
ms.date: 09/28/2017
ms.openlocfilehash: 9f939c0eae4f7ea1f24eec473549dc00191f1b67
ms.sourcegitcommit: fecea174721d0eb4e1927c1116d2604a822e4090
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2018
ms.locfileid: "39360504"
---
# <a name="pause-and-start-your-power-bi-embedded-capacity-in-the-azure-portal"></a>Wstrzymywanie i uruchamianie pojemności usługi Power BI Embedded w witrynie Azure Portal

Ten artykuł zawiera szczegółowe instrukcje dotyczące wstrzymywania i uruchamiania pojemności usługi Power BI Embedded na platformie Microsoft Azure. Zakłada się, że utworzono pojemność usługi Power BI Embedded. Jeśli tego nie zrobiono, zobacz [Tworzenie pojemności usługi Power BI Embedded w witrynie Azure Portal](azure-pbie-create-capacity.md).

Jeśli nie masz subskrypcji platformy Azure, przed rozpoczęciem utwórz [bezpłatne konto](https://azure.microsoft.com/free/).

## <a name="pause-your-capacity"></a>Wstrzymywanie pojemności

Wstrzymanie pojemności powoduje zatrzymanie naliczania opłat. To dobre rozwiązanie, jeśli nie jest ona potrzebna przez pewien czas. Aby wstrzymać pojemność, wykonaj następujące kroki.

> [!NOTE]
> Wstrzymanie pojemności może uniemożliwić korzystanie z zawartości w usłudze Power BI. Przed wstrzymaniem pojemności koniecznie cofnij przypisanie obszarów roboczych, aby uniknąć przerw.

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com/).

2. Wybierz pozycję **Wszystkie usługi** > **Power BI Embedded**, aby wyświetlić pojemności.

    ![Wszystkie usługi w witrynie Azure Portal](media/azure-pbie-pause-start/azure-portal-more-services.png)

3. Wybierz pojemność, którą chcesz wstrzymać.

    ![Lista pojemności usługi Power BI Embedded w witrynie Azure Portal](media/azure-pbie-pause-start/azure-portal-capacity-list.png)

4. W obszarze szczegółów pojemności wybierz pozycję **Wstrzymaj**.

    ![Wstrzymywanie pojemności](media/azure-pbie-pause-start/azure-portal-pause-capacity.png)

5. Wybierz pozycję **Tak**, aby potwierdzić, że chcesz wstrzymać pojemność.

    ![Potwierdzanie wstrzymywania](media/azure-pbie-pause-start/azure-portal-confirm-pause.png)

## <a name="start-your-capacity"></a>Uruchamianie pojemności

Po uruchomieniu pojemności możesz wznowić korzystanie z niej. Uruchomienie pojemności powoduje również wznowienie naliczania opłat.

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com/).

2. Wybierz pozycję **Wszystkie usługi** > **Power BI Embedded**, aby wyświetlić pojemności.

    ![Wszystkie usługi w witrynie Azure Portal](media/azure-pbie-pause-start/azure-portal-more-services.png)

3. Wybierz pojemność, którą chcesz uruchomić.

    ![Lista pojemności usługi Power BI Embedded w witrynie Azure Portal](media/azure-pbie-pause-start/azure-portal-capacity-list.png)

4. W obszarze szczegółów pojemności wybierz pozycję **Uruchom**.

    ![Uruchamianie pojemności](media/azure-pbie-pause-start/azure-portal-start-capacity.png)

5. Wybierz pozycję **Tak**, aby potwierdzić, że chcesz uruchomić pojemność.

    ![Potwierdzanie uruchamiania](media/azure-pbie-pause-start/azure-portal-confirm-start.png)

Po uruchomieniu pojemności zawartość przypisana do tej pojemności stanie się dostępna.

## <a name="next-steps"></a>Następne kroki

Jeśli chcesz przeskalować pojemność w górę lub w dół, zobacz [Skalowanie pojemności usługi Power BI Embedded](azure-pbie-scale-capacity.md).

Aby rozpocząć osadzanie zawartości usługi Power BI w aplikacji, zobacz [Jak osadzić pulpity nawigacyjne, raporty i kafelki usługi Power BI](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/).

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)