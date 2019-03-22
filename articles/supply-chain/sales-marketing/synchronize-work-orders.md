---
title: Projektszámmal rendelkező munkarendelések szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelye a Microsoft Dynamics 365 for Field Service munkarendeléseinek a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban található projektszámaival történő szinkronizálására használatos.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2019
ms.locfileid: "836442"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Projektszámmal rendelkező munkarendelések szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelye a Microsoft Dynamics 365 for Field Service munkarendeléseinek a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban található projektszámaival történő szinkronizálására használatos.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

A használt **Mukerdnelések projektekkel (Fin and Ops – Field and Ops)** sablon a **Munkarendelések (Field Service – Fin and Ops)** sablonon alapul. További információért, lásd: [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Finance and Operations értékesítési rendeléseivel](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)

Ez a témakör csak a két sablonok eltéréseit írja le:
- **Munkarendelések projektszámmal (a Field Service alkalmazásból a Fin and Ops alkalmazásba)**
- **Munkarendelések (a Field Service alkalmazásból a Fin and Ops alkalmazásba)**

A fő különbség, hogy ez a sablon tartalmazza a munkarendeléshez hozzárendelt projektszámot a Field Service megoldásban, ami biztosítja, hogy a Finance and Operations megoldásban létrehozott értékesítési rendelés tartalmazza a projektszámot, és hogy megtörténhessen a számlázás a kapcsolódó projektben. Emellett a sablon használja a speciális lekérdezés és szűrést.

## <a name="templates-and-tasks"></a>Sablonok és feladatok

**A sablon neve az adatintegrációban:**

- Munkarendelések projektszámmal (a Field Service alkalmazásból a Fin and Ops alkalmazásba)

**A feladat neve az adatintegrációs projektben:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás
A **Külső projekt** mezőt hozzáadtuk a munkarendelés entitáshoz. Ez a mező egy keresés és vásárlás, felcímkézi a Munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez a Finance and Operations megoldáson belül. Miután a **Rendszer állapota** Nyitott – folyamatban (690,970,000) állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és nem lehet felvenni, törölni vagy módosítani az értéket.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a>Munkarendelések projektszámmal (a Field Service alkalmazásból a Fin and Ops alkalmazásba): WorkOrderHeader

[![Sablonleképezés az adatintegrátorban](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a>Munkarendelések projekttel(a Field Service alkalmazásból a Fin and Ops alkalmazásba): WorkOrderHeaderProject

[![Sablonleképezés az adatintegrátorban](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a>Munkarendelések projekttel (a Field Service alkalmazásból a Fin and Ops alkalmazásba): WorkOrderProduct

[![Sablonleképezés az adatintegrátorban](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a>Munkarendelések projekttel (a Field Service alkalmazásból a Fin and Ops alkalmazásba): WorkOrderService

[![Sablonleképezés az adatintegrátorban](./media/FSWOP4.png)](./media/FSWOP4.png)
