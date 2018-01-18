---
title: "Értékesítésiszámla-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, amelyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti közvetlen szinkronizálásra használhatók az értékesítési számlák fejlécei és sorai esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e9d7e756c56932372ed931620016973c794fb3fc
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Értékesítésiszámla-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, amelyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti közvetlen szinkronizálásra használhatók az értékesítési számlák fejlécei és sorai esetében.

## <a name="data-flow-in-prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása adatfolyama

A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között. A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.

[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration). Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.

A következő sablon és alapul szolgáló feladatok vannak használatban az értékesítési számlafejlécek és sorok szinkronizálásához a Finance and Operations és a Sales között:

- **Sablon neve az adatintegrációban:** Értékesítési számlák (Fin and Ops – Sales) – Közvetlen
- **A feladatok nevei az adatintegrációs projektben:**

    - SalesInvoiceHeader
    - SalesInvoiceLine

A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési számla fejlécének és sorainak szinkronizálása megtörténhetne:

- Termékek (Fin and Ops – Sales) – Közvetlen
- Számlák (Sales a Fin and Opshoz) – Közvetlen (ha van)
- Névjegyek (Sales a Fin and Opshoz) – Közvetlen (ha van)
- Értékesítési rendelés fejléce és sorai (Fin és Ops – Sales) – Közvetlen

## <a name="entity-set"></a>Entitás beállítása

| Finance and Operations                               | Értékesítés          |
|------------------------------------------------------|----------------|
| Külsőleg karbantartott vevői értékesítésiszámla-fejlécek | Számlák       |
| Külsőleg karbantartott vevői értékesítésiszámla-sorok   | InvoiceDetails |

## <a name="entity-flow"></a>Entitás folyamata

Az értékesítési számlák létrehozása a Finance and Operationsben történik, majd szinkronizálódnak a Sales programban.

> [!NOTE]
> A költségekhez kapcsolódó adók az Értékesítési számla fejlécében jelenleg nem szerepelnek a Finance and Operations szolgáltatásból a Sales szolgáltatásba történő szinkronizálásban. A Sales nem támogatja az adózási adatokat a fejléc szintjén. Azonban a sorszintű díjakhoz kapcsolódó adó szerepel a szinkronizálásban.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

- Egy **Számla száma mező** hozzáadódik a **Számla** entitáshoz, és megjelenik a lapon.
- A **Számla létrehozása** gomb az **Értékesítési rendelés** lapon rejtve van, mivel a számlák létrehozása a Finance and Operations szolgáltatásban történik, és szinkronizálódik a Sales szolgáltatásba. A **Számla** lap tartalma nem szerkeszthető, mert a számlák a Finance and Operations szolgáltatásból szinkronizálódnak.
- Az **Értékesítési rendelés állapota** automatikusan **Számlázott** értékre változik, amikor a Finance and Operations szolgáltatásból a kapcsolódó számla szinkronizálása a Sales szolgáltatásba megtörténik. Az értékesítési rendelés tulajdonosa, amelyből a számlát létrehozták, hozzárendelésre kerül a számla tulajdonosaként. Emiatt az értékesítési rendelés tulajdonosa megtekintheto a számlát.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Értékesítési számlák szinkronizálása előtt fontos frissíteni a rendszert a következő beállításokkal.

### <a name="setup-in-sales"></a>Beállítás a Salesben

Lépjen a **Beállítások** > **Adminisztráció** > **Rendszerbeállítások** > **Értékesítés** pontra, és győződjön meg róla, hogy a következő beállításokat használja:

- A **Rendszer díjazási számítási rendszerének használata** beállítás értéke **Igen**.
- Az **Engedményszámítási módszer** mező értéke a **Sortétel**.

### <a name="setup-in-the-data-integration-project"></a>Beállítás az adatintegrációs projektben

#### <a name="salesinvoiceheader-task"></a>SalesInvoiceHeader feladat

- Győződjön meg róla, hogy a szükséges leképezés létezik: **InvoiceCountryRegionId** – **BillingAddress\_Country**.

    A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve.

- Számláknak a Sales szolgáltatásban történő létrehozásához szükség van árlistára. Frissítse a **pricelevelid.name \[Price list name\]** leképezését olyan árlistára, amelyet a Sales is használja valutánként. Az alapértelmezett árlistát használhatja egy pénznemnél. Alternatív megoldásként, ha több pénznemben van árlistája, használhat értékképpontot.

    A **pricelevelid.name \[Price list name\]** sablon értéke az USD = CRM Service USA értékein alapul (minta).  
    
#### <a name="salesinvoiceline-task"></a>SalesInvoiceLine feladat

- Ügyeljen arra, hogy meglegyen a szükséges leképezés a **mértékegységnél**.
- Győződjön meg arról, hogy a **SalesUnitSymbol** szükséges értékmegfeleltetése meg van adva a Finance and Operations szolgáltatásban.

    Olyan sablonérték, amely rendelkezik értékmegfeleltetéssel a **SalesUnitSymbol** esetében az **Quantity\_UOM** értékkel.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

> [!NOTE]
> A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem szerepelnek a alapértelmezett-leképezései. Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése. 

> [!NOTE]
> A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Finance and Operations irányban.

### <a name="salesinvoiceheader"></a>SalesInvoiceHeader

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>SalesInvoiceLine

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Kapcsolódó témakörök

[A potenciális ügyfelek készpénzre váltása](prospect-to-cash.md)

[A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre](accounts-template-mapping-direct.md)

[A Finance and Operations-termékek közvetlen szinkronizálása a Sales-termékekre](products-template-mapping-direct.md)

[A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping-direct.md)

[Értékesítésirendelés-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-order-template-mapping-direct.md)







