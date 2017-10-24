---
title: "Értékesítésiszámla-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba"
description: "A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók az értékesítési számlák fejlécei és sorai esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fb5ba099911deda5308daf92d82cd6b3489995bf
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a>Értékesítésiszámla-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba

[!include[banner](../includes/banner.md)]

A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók az értékesítési számlák fejlécei és sorai esetében. 

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A következő sablonok és alapul szolgáló feladatok vannak használatban az értékesítési számlafejlécek és sorok szinkronizálásához a Finance and Operations és a Sales között:

- **A sablon neve az adatintegrációban** 

     - Értékesítési számlák (Fin és Ops a Saleshez)

- **A feladatok nevei az adatintegrációs projektben**

    - SalesInvoiceHeader
    - SalesInvoiceLine

Szükséges szinkronizálási feladatok az értékesítési számla fejléce és a sorok szinkronizálása előtt:
-   Termékek (Fin és Ops a Saleshez)
-   Számlák (Sales a Fin and Opshoz) (ha van)
-   Kapcsolattartók (Sales a Fin and Opshoz) (ha van)
-   Értékesítési rendelés fejléce és sorai (Fin és Ops a Saleshez)

## <a name="entity-set"></a>Entitás beállítása

| Finance and Operations                               | Common Data Service (CDS)              | Értékesítés          |
|------------------------------------------------------|------------------|----------------|
| Külsőleg karbantartott vevői értékesítésiszámla-fejlécek | SalesInvoice     | Számlák       |
| Külsőleg karbantartott vevői értékesítésiszámla-sorok   | SalesInvoiceLine | InvoiceDetails |

## <a name="entity-flow"></a>Entitás folyamata

Az értékesítési számlák létrehozása a Finance and Operationsben történik, majd szinkronizálódnak a Sales programban.

> [!NOTE]
> A költségekhez kapcsolódó adók az **értékesítési számla fejlécében** jelenleg nem szerepelnek a Finance and Operationsből a Salesbe történő szinkronizálásban. Ennek oka, hogy a Sales nem támogatja az adózási adatokat a fejléc szintjén. A sor szintjén a költségekhez kapcsolódó adók beletartoznak.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

-  Egy **Számla száma mező** hozzáadódik a **Számla** entitáshoz és megjelenik a lapon.
 
-  A **Számla létrehozása** gomb az **Értékesítési rendelés** lapon rejtve van, mivel a számlák létrehozása a Finance and Operationsben történik, és szinkronizálódik a Salesbe. A **Számla** lap tartalma nem szerkeszthető, mert a számlák a Finance and Operationsből szinkronizálódnak.
 
-  Az **Értékesítési rendelés állapota** automatikusan **Számlázott** értékre változik, amikor a Finance and Operationsből a kapcsolódó számla szinkronizálása a Salesbe megtörténik. Az értékesítési rendelés tulajdonosa, amelyből a számlát létrehozták, hozzárendelésre kerül a számla tulajdonosaként. Ez lehetővé teszi az értékesítési rendelés tulajdonosa számára a számla megtekintését.
 
## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Értékesítési számlák szinkronizálása előtt fontos frissíteni a rendszert a következő beállítással:

### <a name="setup-in-sales"></a>Beállítás a Salesben

- A **Beállítások** > **Felügyelet** > **Rendszerbeállítások** > **Sales** menüpontban a **Rendszer díjazási számítási rendszerének használata** paramétert állítsa **Igen** értékre. 

- A **Beállítások** > **Felügyelet** > **Tendszerbeállítások** > **Sales** menüpontban az **Engedményszámítási módszer** paramétert állítsa **Sortétel** értékre. 

### <a name="setup-in-the-data-integration-project"></a>Beállítás az adatintegrációs projektben

#### <a name="salesinvoiceheader-task"></a>SalesInvoiceHeader feladat

- Frissítse a **CDS-szervezetazonosítót** a **Forrás pontban** > **CDS** értékre. 

    -  A sablon alapértelmezett **SalesOrder_Organization_OrganizationId** értéke ORG001.
    -  A sablon alapértelmezett **Account_Organization_OrganizationId** értéke ORG001.
    -  A sablon alapértelmezett **Organization_OrganizationId** értéke ORG001.

- Ügyeljen, hogy meglegyen a **Forrás** > **InvoiceCountryRegionId CDS-e** szükséges leképezése a **BillingAddress_Country**-hoz.

    -  A sablon értéke **ValueMap** az országok számával leképezve.

- Számlák a Salesben történő létrehozásához szükség van **Árlistára**. Frissítse a **ValueMap** elemet a **CDS** > **pricelevelid.name [Árlista neve] célhelye** helyen a Salesben pénznemenként használt **Árlistára**. Használhatja az alapértelmezett **Árlistát** egyetlen pénznemhez, vagy egy **ValueMap** elemet, ha több pénznemben vannak **Árlisták**.

    -  A **pricelevelid.name [Árlista neve]** sablonértéke **ValueMap** a **Pénznem** alapján.
    -  usd: CRM szolgáltatás USA (minta). 

#### <a name="salesinvoiceline-task"></a>SalesInvoiceLine feladat

- Ellenőrizze, hogy létezik-e a szükséges leképezés a **Forrás** > **Mértékegység-CDS** helyen.

- Győződjön meg arról, hogy a Finance and Operationsben a szükséges **ValueMap** a **SalesUnitSymbol** elemhez létezik a **Forrás** > **CDS-hozzárendelés** helyen. 
    
    - A **ValueMap** sablonérték meghatározása a **SalesUnitSymbol to Quantity_UOM** révén történik.
    
-  Frissítse a leképezést a következőre: **CDS-szervezetazonosító forrásban** > **CDS**. 

    -  A sablon alapértelmezett **SalesInvoicer_Organization_OrganizationId** értéke ORG001.
    -  A sablon alapértelmezett **Product_Organization_OrganizationId** értéke ORG001.
 
## <a name="template-mapping-in-data-integrator"></a>Sablonleképezés az adatintegrátorban

> [!NOTE]
> A **Fizetési feltételek**, **Szállítási feltételek**, **Kiszállítási feltételek**, **Szállítási mód** és **Kézbesítés módja** nem találhatók meg az alapértelmezett leképezésekben. Ezen mezők megfeleltetéséhez be kell állítani az értékek olyan leképezését, amely konkrétan azon szervezetek adataira vonatkozik, amelyek között az entitás szinkronizálása megtörténik.

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Kapcsolódó témakörök

[A Finance and Operations-termékek szinkronizálása a Sales-termékekre](products-template-mapping.md)

[A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre](accounts-template-mapping.md)

[A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping.md)

[Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba](sales-quotation-template-mapping.md)

[Értékesítésirendelés-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-order-template-mapping.md)


