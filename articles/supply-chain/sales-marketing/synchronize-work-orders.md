---
title: "Munkarendelések szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatot mutatja be, melyek a projektszámmal rendelkező munkarendelések Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti szinkronizálására használhatók."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: f5bd6b8c554688d0d1b2bfd93a34a60a95412bf3
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Projektszámmal rendelkező munkarendelések szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a sablonokat és kapcsolódó feladatot mutatja be, melyek a projektszámmal rendelkező munkarendelések Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti szinkronizálására használhatók.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

A használt **Field Service termékek (Finance and Operations – Field Service)** sablon A potenciális ügyfelek készpénzre váltása alkalmazásból eredő **Termékek (Finance and Operations – Sales) – Közvetlen** sablonon alapul. További tudnivalókért lásd: [Termékek (Finance and Operations – Sales) – Közvetlen](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Ez a témakör csak a **Field Service termékek (Finance and Operations – Field Service)** és a **Field Service termékek (Finance and Operations – Field Serivce)** sablonok közötti különbségeket mutatja be.

A fő különbség, hogy ez a sablon tartalmazza a munkarendeléshez hozzárendelt projektszámot a Field Service megoldásban, ami biztosítja, hogy a Finance and Operations megoldásban létrehozott értékesítési rendelés tartalmazza a projektszámot, és hogy megtörténhessen a számlázás a kapcsolódó projektben. Emellett a sablon használja a speciális lekérdezés és szűrést.

## <a name="templates-and-tasks"></a>Sablonok és feladatok

**A sablon neve az adatintegrációban:**

- Munkarendelések projektszámmal (a Field Service alkalmazásból a Finance and Operations alkalmazásba)

**A feladat neve az adatintegrációs projektben:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás
A **Külső projekt** mezőt hozzáadtuk a munkarendelés entitáshoz. Ez a mező egy keresés és vásárlás, felcímkézi a Munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez a Finance and Operations megoldáson belül. Miután a **Rendszer állapota** Nyitott – folyamatban (690,970,000) állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és nem lehet felvenni, törölni vagy módosítani az értéket.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a>Munkarendelések projektszámmal (a Field Service alkalmazásból a Finance and Operations alkalmazásba): WorkOrderHeader

[![Sablonleképezés az adatintegrátorban](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a>Munkarendelések projektszámmal (a Field Service alkalmazásból a Finance and Operations alkalmazásba): WorkOrderHeaderProject

[![Sablonleképezés az adatintegrátorban](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a>Munkarendelések projektszámmal (a Field Service alkalmazásból a Finance and Operations alkalmazásba): WorkOrderProduct

[![Sablonleképezés az adatintegrátorban](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a>Munkarendelések projektszámmal (a Field Service alkalmazásból a Finance and Operations alkalmazásba): WorkOrderService

[![Sablonleképezés az adatintegrátorban](./media/FSWOP4.png)](./media/FSWOP4.png)

