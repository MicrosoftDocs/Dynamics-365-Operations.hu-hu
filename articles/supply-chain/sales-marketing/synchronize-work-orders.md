---
title: Munkarendelések szinkronizálása projekttel a Field Service alkalmazásból a Supply Chain Management alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelye a Dynamics 365 Field Service munkarendeléseinek a Dynamics 365 Supply Chain Management szolgáltatásban található projektszámaival történő szinkronizálására használatos.
author: ChristianRytt
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: a641789adf27e51b7a3f8ab03269cc2e748eef96
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359811"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a>Munkarendelések szinkronizálása projekttel a Field Service alkalmazásból a Supply Chain Management alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelye a Dynamics 365 Field Service munkarendeléseinek a Dynamics 365 Supply Chain Management szolgáltatásban található projektszámaival történő szinkronizálására használatos.

[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között.](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

A használt **Munkarendelések projektekkel (Field Service-ből a Supply Chain Management szolgáltatásba)** sablon a **Munkarendelések (Field Service-ből a Supply Chain Management szolgáltatásba)** sablonon alapul. További információért, lásd: [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Supply Chain Management értékesítési rendeléseivel](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)

Ez a témakör csak a két sablonok eltéréseit írja le:
- **Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba)**
- **Munkarendelések (a Field Service alkalmazásból a Supply Chain Management alkalmazásba)**

A fő különbség, hogy ez a sablon tartalmazza a munkarendeléshez társított projektszám leképezését a Field Service megoldásban, ami biztosítja, hogy a Supply Chain Management megoldásban létrehozott értékesítési rendelés tartalmazza a projektszámot, és hogy megtörténhessen a számlázás a kapcsolódó projektben. Emellett a sablon használja a speciális lekérdezés és szűrést.

## <a name="templates-and-tasks"></a>Sablonok és feladatok

**A sablon neve az adatintegrációban:**

- Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba)

**A feladat neve az adatintegrációs projektben:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás
A **Külső projekt** mezőt hozzáadtuk a munkarendelés entitáshoz. Ez a mező egy keresőmező, és a munkarendelés egy projekttel való felcímkézése által az értékesítési rendelés kapcsolódik egy projekthez a Supply Chain Management megoldáson belül. Amikor a **Rendszer állapota** Nyitott – folyamatban (690,970,000) állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és nem lehet felvenni, törölni vagy módosítani az értéket.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a>Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba): WorkOrderHeader

[![Sablonleképezés az adatintegrátorban.](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a>Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba): WorkOrderHeaderProject

[![Sablonleképezés az adatintegrátorban.](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a>Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba): WorkOrderProduct

[![Sablonleképezés az adatintegrátorban.](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a>Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba): WorkOrderService

[![Sablonleképezés az adatintegrátorban.](./media/FSWOP4.png)](./media/FSWOP4.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]