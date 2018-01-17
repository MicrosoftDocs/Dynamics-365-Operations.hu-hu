---
title: "Értékesítésirendelés-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, amelyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti közvetlen szinkronizálásra használhatók az értékesítési rendelések fejlécei és sorai esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Értékesítésirendelés-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, amelyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti közvetlen szinkronizálásra használhatók az értékesítési rendelések fejlécei és sorai esetében.

## <a name="data-flow-in-prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása adatfolyama

A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között. A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.

[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration). Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.

A következő sablon és alapul szolgáló feladatok vannak használatban az értékesítési rendelési fejlécek és sorok szinkronizálásához a Finance and Operations és a Sales között:

- **Sablon neve az adatintegrációban:** Értékesítési rendelések (Fin and Ops – Sales) – Közvetlen
- **A feladatok nevei az adatintegrációs projektben:**

    - OrderHeader
    - OrderLine

A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési számla fejlécének és sorainak szinkronizálása megtörténhetne:

- Termékek (Fin and Ops – Sales) – Közvetlen
- Számlák (Sales a Fin and Opshoz) – Közvetlen (ha van)
- Kapcsolattartók vevőkkel (Sales a Fin and Opshoz) – közvetlen (ha van)

## <a name="entity-set"></a>Entitás beállítása

| Finance and Operations  | Értékesítés             |
|-------------------------|-------------------|
| CDS értékesítési rendelési fejlécek | SalesOrders       |
| CDS értékesítési rendelés sorai   | SalesOrderDetails |

## <a name="entity-flow"></a>Entitás folyamata

Az értékesítési rendelések létrehozása a Finance and Operationsben történik, majd szinkronizálódnak a Sales programban.

A sablonban található szűrők segítenek gondoskodni róla, hogy hogy csak a megfelelő értékesítési rendelések szerepeljenek a szinkronizálásban:

- A Sales szolgáltatásból származó értékesítési ajánlatban szereplő értékesítési és számlázási vevő is szerepelni fog a szinkronizálásban. A Finance and Operations szolgáltatásban az **OrderingCustomerIsExternallyMaintained** és az **InvoiceCustomerIsExternallyMaintained** mezők az adatentitások szinkronizálásának nyomon követésére szolgálnak.
- Az Értékesítési rendelést a Finance and Operations szolgáltatásban jóvá kell hagyni. Csak a megerősített értékesítési rendelések vagy magasabb, például **Szállított** vagy **Számlázott** feldolgozási állapotú értékesítési rendelések szinkronizálódnak a Sales szolgáltatásba.
- Értékesítési rendelés létrehozása vagy módosítása után a Finance and Operations szolgáltatásban végre kell hajtani az **Eladási összegek számítása** kötegelt feladatot. Csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a Sales szolgáltatásba.

> [!NOTE]
> A költségekhez kapcsolódó adók az Értékesítési rendelés fejlécében jelenleg nem szerepelnek a Finance and Operations szolgáltatásból a Sales szolgáltatásba történő szinkronizálásban. A Sales nem támogatja az adózási adatokat a fejléc szintjén. Azonban a sorszintű díjakhoz kapcsolódó adó szerepel a szinkronizálásban.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

Új mezők kerülnek hozzáadásra a **Rendelés** entitáshoz, és megjelennek a lapon:

- **Külsőleg karbantartva** – beállítása **Igen**, ha a megrendelés a Finance and Operations szolgáltatásból érkezik.
- **Feldolgozás állapota** – a mező a rendelés feldolgozottsági állapotát mutatja a Finance and Operations szolgáltatásban. A következő értékek állnak rendelkezésre:

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

Az **Ajánlat csak külsőleg fenntartott termékekre vonatkozik** beállítást más értékesítési forgatókönyvekben használják (például a Sales és a Finance and Operation között történő szinkronizálás), hogy következetesen nyomon kövessék, hogy egy értékesítési megbízás teljes egészében külsőleg karbantartott termékekből áll-e. Ha az értékesítési rendelés csak külsőleg fenntartott termékeket tartalmaz, a termékeket a Finance and Operations kezeli. Ez a beállítás garantálja, hogy nem próbálja szinkronizálni az értékesítési rendelési sorokat olyan termékekkel, amelyek ismeretlenek a Finance and Operations számára.

A **Számla létrehozása**, **Rendelés érvénytelenítése**, **Újraszámítás**, **Termékek beszerzése** és **Keresési cím** gombok az **Értékesítési rendelés** oldalon rejtve vannak külsőleg karbantartott rendeléseknél, mivel a számlák a Finance and Operations szolgáltatásban jönnek létre, majd szinkronizálódnak a Sales szolgáltatásba. Ezeket a megrendeléseket nem lehet szerkeszteni, mert az értékesítési rendelési adatok szinkronizálódnak a Finance and Operations szolgáltatással.

Az értékesítési rendelés állapota **Aktív** marad annak biztosítására, hogy a Finance and Operations módosításai átkerülhessenek az értékesítési rendelésbe a Sales szolgáltatásban. Ennek vezérléséhez az alapértelmezett **Statecode \[állapot\]** értékét **Aktívra** kell állítani az adatintegrációs projektben.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Értékesítési rendelések szinkronizálása előtt fontos frissíteni a rendszert a következő beállításokkal.

### <a name="setup-in-sales"></a>Beállítás a Salesben

- Győződjön meg róla, hogy beállították az engedélyeket ahhoz a csapathoz, amelytől a Sales kapcsolatkészletének felhasználója hozzá van rendelve. Bemutatóadatok használatakor rendszerint a felhasználó rendelkezik rendszergazdai hozzáféréssel, de nem a csoport. Ha a csapatnak nincs adminisztrátori hozzáférése is, akkor ha a projektet az adatintegrálásból futtatja, hibaüzenet jelenik meg, amely azt jelzi, hogy a fő csapat hiányzik.

    A **Beállítások** > **Biztonság** > **Csapatok** pontnál válassza ki a megfelelő csapatot, majd a **Szerepkörök kezelése** lehetőséget, és válasszon ki egy olyan szerepkört, amely a megfelelő engedélyekkel rendelkezik, pl. **Rendszergazda**.

- Lépjen a **Beállítások** > **Adminisztráció** > **Rendszerbeállítások** > **Értékesítés** pontra, és győződjön meg róla, hogy a következő beállításokat használja:

    - A **Rendszer díjazási számítási rendszerének használata** beállítás értéke **Igen**.
    - Az **Engedményszámítási módszer** mező értéke a **Sortétel**.

### <a name="setup-in-finance-and-operations"></a>Beállítás a Finance and Operations alkalmazásban

Lépjen az **Értékesítés és marketing** > **Időszakos feladatok** > **Eladási összegek számítása** ponthoz, állítsa be a feladatot kötegelt futásra. Állítsa az **Értékesítési rendelések teljes összegének kiszámítása** beállítást **Igen** értékre. Ez a lépés azért fontos, mert csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a Sales szolgáltatásba. A kötegelt feladat gyakoriságát az értékesítési rendelés szinkronizálásának gyakoriságához kell igazítani.

### <a name="setup-in-the-data-integration-project"></a>Beállítás az adatintegrációs projektben

#### <a name="salesheader-task"></a>SalesHeader feladat

- Győződjön meg róla, hogy a szükséges leképezés létezik: **InvoiceCountryRegionId** – **BillingAddress\_Country**, továbbá **DeliveryCountryRegionId** – **DeliveryAddress\_Country**.

    A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve.

- Rendeléseknek a Sales szolgáltatásban történő létrehozásához szükség van árlistára. Frissítse a **pricelevelid.name \[Price list name\]** leképezését olyan árlistára, amelyet a Sales is használja valutánként. Az alapértelmezett árlistát használhatja egy pénznemnél. Alternatív megoldásként, ha több pénznemben van árlistája, használhat értékképpontot.

    A sablon alapértelmezett neve **pricelevelid.name \[Árlista neve\]** – **CRM Service USA (minta)**.

#### <a name="salesline-task"></a>SalesLine feladat

- Győződjön meg róla, hogy a szükséges leképezés létezik: **DeliveryCountryRegionId** – **DeliveryAddress\_Country**.

    A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve.

- Győződjön meg arról, hogy a **SalesUnitSymbol** szükséges értékmegfeleltetése meg van adva a Finance and Operations szolgáltatásban.

    Olyan sablonérték, amely rendelkezik értékmegfeleltetéssel a **SalesUnitSymbol** esetében az **Quantity\_UOM** értékkel.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

> [!NOTE]
> A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem szerepelnek a alapértelmezett-leképezései. Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése. 

> [!NOTE]
> A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Finance and Operations irányban.

### <a name="orderheader"></a>OrderHeader

![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a>OrderLine

![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Kapcsolódó témakörök

[A potenciális ügyfelek készpénzre váltása](prospect-to-cash.md)

[A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre](accounts-template-mapping-direct.md)

[A Finance and Operations-termékek közvetlen szinkronizálása a Sales-termékekre](products-template-mapping-direct.md)

[A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping-direct.md)

[Értékesítésiszámla-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping-direct.md)




