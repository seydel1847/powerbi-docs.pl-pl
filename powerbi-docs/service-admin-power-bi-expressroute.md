---
title: Usługi Power BI i ExpressRoute
description: Usługi Power BI i ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 0c4618150094a4eabb0dc9745e9ac93e4f342ff1
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54291101"
---
# <a name="power-bi-and-expressroute"></a>Usługi Power BI i ExpressRoute

**ExpressRoute** to usługa platformy Azure, która pozwala tworzyć połączenia prywatne między centrami danych platformy Azure (na której znajduje się usługa Power BI) i infrastrukturą lokalną lub tworzyć połączenia prywatne między centrami danych platformy Azure i środowiskiem wspólnej lokalizacji.

Korzystając z usług **Power BI** i **ExpressRoute**, możesz utworzyć prywatne połączenie sieciowe z Twojej organizacji do usługi Power BI (lub za pomocą funkcji wspólnej lokalizacji od usługodawcy internetowego), omijając Internet w celu lepszego zabezpieczenia poufnych danych i połączeń usługi Power BI.

Aby uzyskać więcej informacji, zobacz [Omówienie usługi ExpressRoute](/azure/expressroute/expressroute-introduction). Usługa Power BI jest zgodna z usługą ExpressRoute, ale istnieją pewne wyjątki, gdy usługa Power BI pobiera lub wysyła dane za pośrednictwem publicznej sieci Internet. Listę adresów URL używanych przez usługę Power BI można znaleźć w temacie [Adresy URL usługi Power BI](power-bi-whitelist-urls.md).

![Diagram usługi ExpressRoute](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)