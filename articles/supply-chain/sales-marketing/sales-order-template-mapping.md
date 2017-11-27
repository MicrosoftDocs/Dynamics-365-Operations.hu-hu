---
title: "Értékesítésirendelés-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba"
description: "A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók az értékesítési rendelések fejlécei és sorai esetében."
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c7b2ff6430e99661ee284f65089086df9fa5a1ad
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a>Értékesítésirendelés-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba

[!include[banner](../includes/banner.md)]

A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók az értékesítési rendelések fejlécei és sorai esetében. 

## <a name="template-and-tasks"></a>Sablon és feladatok

A következő sablonok és alapul szolgáló feladatok vannak használatban az értékesítési rendelési fejlécek és sorok szinkronizálásához a Finance and Operations és a Sales között:

- **Sablon neve az adatintegrációban** 

    - Értékesítési rendelések (Fin és Ops a Saleshez)
    
- **Feladatok nevei az adatintegrációs projektben**

    - OrderHeader
    - OrderLine

Az értékesítési számla fejléce és a sorok szinkronizálása előtt szükséges szinkronizálási feladatok:

- Termékek (Fin és Ops a Saleshez)
- Számlák (Sales a Fin and Opshoz) (ha van)
- Kapcsolattartók vevőkkel (Sales a Fin and Opshoz) (ha van)

## <a name="entity-set"></a>Entitás beállítása

| Finance and Operations |    Common Data Service (CDS)         |     Értékesítés      |
|------------------------|----------------|----------------|
| CDS értékesítési rendelési fejlécek| SalesOrder     | SalesOrders |
| CDS értékesítési rendelés sorai  | SalesOrderLine | SalesOrderDetails|

## <a name="entity-flow"></a>Entitás folyamata

Az értékesítési rendelések létrehozása a Finance and Operationsben történik, majd szinkronizálódnak a Sales programban.

A sablonban található szűrők gondoskodnak róla, hogy hogy csak a megfelelő értékesítési rendelések szerepeljenek a szinkronizálásban:

- A Salesből származó értékesítési ajánlatban szereplő értékesítési és számlázási vevő is szerepelni fog a szinkronizálásban. A Finance and Operationsben az **OrderingCustomerIsExternallyMaintained** és az **InvoiceCustomerIsExternallyMaintained** mezők az adatentitások szinkronizálásának nyomon követésére szolgálnak.

- Az **Értékesítési rendelést** a Finance and Operationsben jóvá kell hagyni. Csak a megerősített értékesítési rendelések vagy magasabb, például Szállított vagy Számlázott feldolgozási állapotú értékesítési rendelések szinkronizálódnak a Salesbe.

- Értékesítési rendelés létrehozása vagy módosítása után a Finance and Operationsben végre kell hajtani az **Eladási összegek számítása** kötegelt feladatot. Csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a CDS-be és a Salesbe.

> [!NOTE]
> A költségekhez kapcsolódó adók az **Értékesítési rendelés fejlécében** jelenleg nem szerepelnek a Finance and Operationsből a Salesbe történő szinkronizálásban. Ennek oka, hogy a Sales nem támogatja az adózási adatokat a fejléc szintjén. A sor szintjén a költségekhez kapcsolódó adók beletartoznak.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

Új mezők kerülnek hozzáadásra a **Rendelés** entitáshoz, és megjelennek a lapon:

- **Külsőleg karbantartva** – beállítása **Igen**, ha a megrendelés a Finance and Operationsből érkezik.

- **Feldolgozás állapota** – a rendelés feldolgozottsági állapotát mutatja a Finance and Operationsben. Az értékek:

    - Aktív
    - Visszaigazolva
    - Csomagjegyzék
    - Számlázva
    - Kitárolva
    - Részben kitárolva
    - Részben csomagolva
    - Szállítva
    - Részben szállítva
    - Részben számlázva
    - Visszavonva

A **Csak külsőleg karbantartott termékei vannak** beállítással értékesítési rendelési forgatókönyvek esetén (a Salesből a Finance and Operationsbe történő szinkronizációnál) következetesen nyomon követheti, hogy az értékesítési rendelés teljesen **Külsőleg karbantartott termékekből** tevődik-e össze, amely esetben termékek karbantartása a Finance and Operationsben történik. Ez garantálja, hogy ne próbálja szinkronizálni az értékesítési rendelési sorokat olyan termékekkel, amelyek ismeretlenek a Finance and Operations számára.
 
A **Számla létrehozása**, **Rendelés érvénytelenítése**, **Újraszámítás**, **Termékek beszerzése** és **Keresési cím** gombok az **Értékesítési rendelés** oldalon rejtve vannak külsőleg karbantartott rendeléseknél, mivel a számlák a Finance and Operationsben jönnek létre, majd szinkronizálódnak a Salesbe. A rendelési lap tartalma nem szerkeszthető, mert az értékesítési rendelési adatok a Finance and Operationsből szinkronizálódnak.
 
Az **Értékesítési rendelés állapota** aktív marad annak biztosítására, hogy a Finance and Operations módosításai átkerülhessenek az **Értékesítési rendelésbe** a Salesben. Ennek vezérléséhez az alapértelmezett **Statecode [állapot]** értékét **Aktívra** kell állítani az adatintegrációs projektben.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás 

Értékesítési rendelések szinkronizálása előtt fontos frissíteni a rendszert a következő beállítással:

### <a name="setup-in-sales"></a>Beállítás a Salesben

- Biztosítja az engedélyeket a csapat számára, amelyhez a felhasználó (a Sales **Beállított kapcsolat** paraméterével) hozzá van rendelve. Bemutatóadatok használatakor általában a felhasználó rendelkezik rendszergazdai hozzáféréssel, de nem a csoport. Enélkül a projekt az adatintegrátorból történő futtatásakor hibaüzenetet kap, amely szerint a fő csoport nincs megadva. 

    - A **Beállítások** > **Biztonság** > **Csapatok** pontban, válassza ki az érintett csapatot, kattintson a **Szerepkörök kezelése** elemre, és válassza ki a kívánt engedélyekkel rendelkező szerepkört (például rendszergazda).

- A **Beállítások** > **Felügyelet** > **Rendszerbeállítások** > **Sales** menüpontban a **Rendszer díjazási számítási rendszerének használata** paramétert állítsa **Igen** értékre. 

- A **Beállítások** > **Felügyelet** > **Tendszerbeállítások** > **Sales** menüpontban az **Engedményszámítási módszer** paramétert állítsa **Sortétel** értékre. 

### <a name="setup-in-finance-and-operations"></a>Beállítás a Finance and Operations alkalmazásban

Állítsa az **Értékesítés és marketing** > **Időszakos feladatok** > **Eladási összegek számítása** elemet kötegelt feladatként történő futtatásra, és az **Értékesítési rendelések teljes összegének kiszámítása** elemet állítsa **Igen** értékre. Ez azért fontos, mert csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a CDS-be és a Salesbe. A kötegelt feladat gyakoriságát az értékesítési rendelés szinkronizálásának gyakoriságához kell igazítani.

### <a name="setup-in-the-data-integration-project"></a>Beállítás az adatintegrációs projektben

#### <a name="salesheader-task"></a>SalesHeader feladat

- Frissítse a leképezést a következőre: **CDS-szervezetazonosító forrásban** > **CDS**.

    - A sablon alapértelmezett **Account_Organization_OrganizationId** értéke ORG001.
    - A sablon alapértelmezett **InvoiceAccount_Organization_OrganizationId** értéke ORG001.
    - A sablon alapértelmezett **Organization_OrganizationId** értéke ORG001.

- Ellenőrizze, hogy létezik-e a szükséges leképezés a **Forrás** > **CDS for InvoiceCountryRegionId to BillingAddress_Country** és a **DeliveryCountryRegionId to DeliveryAddress_Country** között.

    - A sablon értéke **ValueMap** az országok számával leképezve.

- Rendelések a Salesben történő létrehozásához szükség van **Árlistára**. Frissítse a **pricelevelid.name [Árlista neve]** elemet illető **ValueMap** értéket a **CDS** > **Célhely** helyen a Salesben pénznemenként használt **Árlistára**. Használhatja az alapértelmezett **Árlistát** egyetlen pénznemhez, vagy egy **ValueMap** elemet, ha több pénznemben vannak **Árlisták**.
    
    - A sablon alapértelmezett **pricelevelid.name [Árlista neve]** értéke CRM Service USA (minta). 

#### <a name="salesline-task"></a>SalesLine feladat

- Frissítse a leképezést a következőre: **CDS-szervezetazonosító forrásban** > **CDS**. 
    
    - A sablon alapértelmezett **SalesOrder_Organization_OrganizationId** értéke ORG001.
    - A sablon alapértelmezett **Product_Organization_OrganizationId** értéke ORG001.

- Ügyeljen, hogy meglegyen a szükséges leképezés a **Forrás** > **CDS** helyen a **DeliveryCountryRegionId** és a **DeliveryAddress_Country** között.

    - A sablon értéke **ValueMap** az országok számával leképezve.
    
- Győződjön meg arról, hogy a Finance and Operationsben a szükséges **ValueMap** a **SalesUnitSymbol** elemhez létezik a **Forrás** > **CDS-hozzárendelés** helyen.

    - A **ValueMap** sablonérték meghatározása a **SalesUnitSymbol to Quantity_UOM** révén történik.

## <a name="template-mapping-in-data-integrator"></a>Sablonleképezés az adatintegrátorban

> [!NOTE]
> A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem találhatók meg a alapértelmezett-leképezései. Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.

### <a name="orderheader"></a>OrderHeader

![Sablonleképezés az adatintegrátorban](./media/sales-order-template-mapping-data-integrator-1.png)

![Sablonleképezés az adatintegrátorban](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a>OrderLine

![Sablonleképezés az adatintegrátorban](./media/sales-order-template-mapping-data-integrator-3.png)

![Sablonleképezés az adatintegrátorban](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Kapcsolódó témakörök

[A Finance and Operations-termékek szinkronizálása a Sales-termékekre](products-template-mapping.md)

[A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre](accounts-template-mapping.md)

[A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping.md)

[Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba](sales-quotation-template-mapping.md)

[Értékesítésiszámla-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping.md)


