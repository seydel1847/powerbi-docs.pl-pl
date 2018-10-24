---
title: Usługa Power BI i ruch wychodzący platformy Azure
description: Omówienie opłat za ruch wychodzący platformy Azure i usługi Power BI na podstawie lokalizacji dzierżawy i usługi Power BI Premium
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: 0150e4e62fffd116b144880ab4aecc81de0b2c49
ms.sourcegitcommit: 1a79e48ac820c28c5d0fd05399f49ed22fc74ed7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2018
ms.locfileid: "49435577"
---
# <a name="power-bi-and-azure-egress"></a>Usługa Power BI i ruch wychodzący platformy Azure

Jeśli używasz usługi Power BI ze źródłami danych platformy Azure, możesz uniknąć opłat za ruch wychodzący platformy Azure w sytuacji, gdy dzierżawa usługi Power BI znajduje się w tym samym regionie co źródła danych platformy Azure.

W przypadku wdrożenia dzierżawy usługi Power BI w tym samym regionie świadczenia usługi Azure, w którym wdrożono źródła danych, nie są naliczane opłaty za ruch wychodzący związane z zaplanowanym odświeżaniem i interakcjami trybu DirectQuery. 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Ustalanie lokalizacji dzierżawy usługi Power BI

Aby dowiedzieć się, gdzie znajduje się dzierżawa usługi Power BI, zobacz artykuł [Gdzie znajduje się moja dzierżawa usługi Power BI](service-admin-where-is-my-tenant-located.md).

Jeśli jesteś klientem usługi Power BI Premium używającym funkcji Multi-Geo i Twoja dzierżawa usługi Power BI nie znajduje się w lokalizacji optymalnej dla niektórych źródeł danych opartych na platformie Azure, możesz wdrożyć funkcję Multi-Geo usługi Power BI Premium w odpowiednim regionie świadczenia usługi Azure i korzystać z zalet umieszczenia dzierżawy usługi Power BI i źródeł danych platformy Azure źródła w tym samym regionie świadczenia usługi Azure.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat usługi Power BI Premium lub funkcji Multi-Geo, zapoznaj się z następującymi zasobami:

* [Co to jest usługa Microsoft Power BI Premium?](service-premium.md)
* [Jak kupić usługę Power BI Premium](service-admin-premium-purchase.md)
* [Obsługa funkcji Multi-Geo dla usługi Power BI Premium (wersja zapoznawcza)](service-admin-premium-multi-geo.md)
* [Gdzie znajduje się moja dzierżawa usługi Power BI?](service-admin-where-is-my-tenant-located.md)
* [Power BI Premium — często zadawane pytania](service-premium-faq.md)


