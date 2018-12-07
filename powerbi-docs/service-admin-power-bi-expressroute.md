---
title: Usługi Power BI i ExpressRoute
description: Usługi Power BI i ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 62289c974e25207f3a991e7f17a0ee965c729b8a
ms.sourcegitcommit: b03912343a5a214c6bb972aaa6aa051c2a5f4332
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2018
ms.locfileid: "52900134"
---
# <a name="power-bi-and-expressroute"></a>Usługi Power BI i ExpressRoute

**ExpressRoute** to usługa platformy Azure, która pozwala tworzyć połączenia prywatne między centrami danych platformy Azure (na której znajduje się usługa Power BI) i infrastrukturą lokalną lub tworzyć połączenia prywatne między centrami danych platformy Azure i środowiskiem wspólnej lokalizacji.

Korzystając z usług **Power BI** i **ExpressRoute**, możesz utworzyć prywatne połączenie sieciowe z Twojej organizacji do usługi Power BI (lub za pomocą funkcji wspólnej lokalizacji od usługodawcy internetowego), omijając Internet w celu lepszego zabezpieczenia poufnych danych i połączeń usługi Power BI.

Aby uzyskać więcej informacji, zobacz [Omówienie usługi ExpressRoute](/azure/expressroute/expressroute-introduction). Usługa Power BI jest zgodna z usługą ExpressRoute, ale istnieją pewne wyjątki, gdy usługa Power BI pobiera lub wysyła dane za pośrednictwem publicznej sieci Internet. Listę adresów URL używanych przez usługę Power BI można znaleźć w temacie [Adresy URL usługi Power BI](power-bi-whitelist-urls.md).

![Diagram usługi ExpressRoute](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)