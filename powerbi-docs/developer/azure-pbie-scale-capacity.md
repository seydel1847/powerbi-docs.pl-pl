---
title: Skalowanie pojemności usługi Power BI Embedded | Microsoft Docs
description: Ten artykuł zawiera szczegółowe instrukcje dotyczące skalowania pojemności usługi Power BI Embedded na platformie Microsoft Azure.
services: power-bi-embedded
author: markingmyname
ms.author: maghan
manager: kfile
editor: ''
tags: ''
ms.service: power-bi-embedded
ms.topic: conceptual
ms.date: 07/31/2018
ms.openlocfilehash: 08ba4113eb4988919c249052e883e8887295a028
ms.sourcegitcommit: fecea174721d0eb4e1927c1116d2604a822e4090
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2018
ms.locfileid: "39360370"
---
# <a name="scale-your-power-bi-embedded-capacity-in-the-azure-portal"></a>Skalowanie pojemności usługi Power BI Embedded w witrynie Azure Portal

Ten artykuł zawiera szczegółowe instrukcje dotyczące skalowania pojemności usługi Power BI Embedded na platformie Microsoft Azure. Skalowanie pozwala zwiększać lub zmniejszać rozmiar pojemności.

Zakłada się, że utworzono pojemność usługi Power BI Embedded. Jeśli tego nie zrobiono, zobacz [Tworzenie pojemności usługi Power BI Embedded w witrynie Azure Portal](azure-pbie-create-capacity.md).

> [!NOTE]
> Operacja skalowania może potrwać około minuty. W tym czasie pojemność nie jest dostępna. Załadowanie osadzonej zawartości może okazać się niemożliwe.

## <a name="scale-a-capacity"></a>Skalowanie pojemności

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com/).

2. Wybierz pozycję **Wszystkie usługi** > **Power BI Embedded**, aby wyświetlić pojemności.

    ![Wszystkie usługi w witrynie Azure Portal](media/azure-pbie-scale-capacity/azure-portal-more-services.png)

3. Wybierz pojemność, którą chcesz przeskalować.

    ![Lista pojemności usługi Power BI Embedded w witrynie Azure Portal](media/azure-pbie-scale-capacity/azure-portal-capacity-list.png)

4. W odpowiedniej sekcji pojemności wybierz pozycję **Warstwa cenowa** w obszarze **Skalowanie**.

    ![Opcja warstwy cenowej w obszarze skalowania](media/azure-pbie-scale-capacity/azure-portal-scale-pricing-tier.png)

    Bieżąca warstwa cenowa jest oznaczona na niebiesko.

    ![Bieżąca warstwa cenowa oznaczona na niebiesko](media/azure-pbie-scale-capacity/azure-portal-current-tier.png)

5. Aby przeskalować w górę lub w dół, wybierz nową warstwę. Nowa warstwa zostanie oznaczona za pomocą przerywanej niebieskiej linii. Wybierz pozycję **Wybierz**, aby zaakceptować zmianę skali na nową warstwę.

    ![Wybieranie nowej warstwy](media/azure-pbie-scale-capacity/azure-portal-select-new-tier.png)

    Skalowanie pojemności może potrwać do dwóch minut.

6. Upewnij się, że warstwa została zmieniona, wyświetlając kartę Przegląd. Będzie widoczna informacja o bieżącej warstwie cenowej.

    ![Potwierdzanie zmiany warstwy](media/azure-pbie-scale-capacity/azure-portal-confirm-tier.png)

## <a name="next-steps"></a>Następne kroki

Aby wstrzymać lub uruchomić pojemność, zobacz [Pause and start your Power BI Embedded capacity in the Azure portal (Wstrzymywanie i uruchamianie pojemności usługi Power BI Embedded w witrynie Azure Portal)](azure-pbie-pause-start.md).

Aby rozpocząć osadzanie zawartości usługi Power BI w aplikacji, zobacz [Jak osadzić pulpity nawigacyjne, raporty i kafelki usługi Power BI](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/).

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)
