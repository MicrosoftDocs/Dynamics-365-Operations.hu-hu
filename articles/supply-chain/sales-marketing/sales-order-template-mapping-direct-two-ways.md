---
title: "Értékelési rendelések szinkronizálása közvetlenül a Sales és a Finance and Operations között"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, amelyek a Microsoft Dynamics 365 for Sales és a Microsoft Dynamics 365 for Finance and Operations közötti közvetlen szinkronizálásra használhatók az értékesítési rendelések esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 10/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a8c033caa8a4c4cf579ec166dce7a9982408d816
ms.openlocfilehash: 985a5a908308bc2268b80e8eef7117fdd6d54af6
ms.contentlocale: hu-hu
ms.lasthandoff: 10/11/2018

---

# <a name="synchronization-of-sales-orders-directly-between-sales-and-finance-and-operations"></a>Értékelési rendelések szinkronizálása közvetlenül a Sales és a Finance and Operations között

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, amelyek a Microsoft Dynamics 365 for Sales és a Microsoft Dynamics 365 for Finance and Operations közötti közvetlen szinkronizálásra használhatók az értékesítési rendelések esetében.

## <a name="data-flow-in-prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása adatfolyama

A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között. A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.

[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration). Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.

A következő sablonokat és alapul szolgáló feladatokat használják az értékesítési rendelések közvetlen szinkronizálásához a Sales és a Finance and Operations között:

- **A sablonok nevei az adatintegrációban:** 

    - Értékesítési rendelések (Sales a Fin és Opshoz) – Közvetlen
    - Értékesítési rendelések (Fin and Ops – Sales) – Közvetlen

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

Az értékelési rendelések a Sales-ben jönnek létre, és akkor szinkronizálódnak a Finance and Operations szolgáltatással, amikor a **Projekt futtatása** aktiválódik egy projektnél az **Értékesítési rendelések (Sales – Fin and Ops) – közvetlen** sablonnál. Csak akkor lehet aktiválni és szinkronizálni a rendeléseket a Sales-től, ha minden **Termékek rendelése** hivatkozás külsőleg karbantartott termékekből áll. Ezért nem lehet írható termék. A rendelés aktiválása után az értékesítési rendelés csak a felhasználói felületen (UI) olvasható. Ezen a ponton a frissítések a Finance and Operations szolgáltatásból származnak. Miután az értékesítési rendelés állapota **Megerősítve**, az **Értékesítési rendelések (Fin and Ops – Sales) – Közvetlen** sablon használható a frissítések és a teljesítési állapot szinkronizálásához a Finance and Operations és a Sales között.

Nem kell rendeléseket létrehoznia a Sales-ben. Ehelyett új értékesítési rendeléseket hozhat létre a Finance and Operations szolgáltatásban. Miután az értékesítési rendelés állapota **Megerősítve**, az előző bekezdésben leírtak szerint szinkronizálódik a Sales szolgáltatással.

A Finance and Operations szolgáltatásban a sablonokban lévő szűrők garantálják, hogy csak a vonatkozó értékesítési rendelések szerepelnek a szinkronizálásban:

- A Sales szolgáltatásból származó értékesítési ajánlatban szereplő értékesítési és számlázási vevőnek is szerepelnie kell a szinkronizálásban. A Finance and Operations szolgáltatásban az **OrderingCustomerIsExternallyMaintained** és az **InvoiceCustomerIsExternallyMaintained** mezők az értékesítési rendelések adatentitásokból való szűrésére szolgálnak.
- Az Értékesítési rendelést a Finance and Operations szolgáltatásban jóvá kell hagyni. Csak a megerősített értékesítési rendelések vagy magasabb, például **Szállított** vagy **Számlázott** feldolgozási állapotú értékesítési rendelések szinkronizálódnak a Sales szolgáltatásba.
- Értékesítési rendelés létrehozása vagy módosítása után a Finance and Operations szolgáltatásban végre kell hajtani az **Eladási összegek számítása** kötegelt feladatot. Csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a Sales szolgáltatásba.

## <a name="freight-tax"></a>Fuvardíj

A Sales nem támogatja az adót a fejléc szintjén, mert az adót a vonal szintjén tárolja. A Finance and Operations fejlécszintű adói, például az áruszállítás adójának támogatása érdekében a rendszer szinkronizálja az adót a Sales felé, mint írható termék, amelynek neve **Fuvardíj**, és az adóösszeg a Finance and Operations szolgáltatásból származik. Ily módon a Sales árának általános árkalkulációja felhasználható a teljes összegekhez, még akkor is, ha az adó a fejléc szintjén a Finance and Operations részéről van.

## <a name="discount-calculation-and-rounding"></a>Engedmények kiszámítása és kerekítése

A Sales árengedménykalkulációs modellje különbözik a Finance and Operations árengedménykalkulációs modelljétől. A Finance and Operations szolgáltatásban a záró engedmény összege az értékesítési soron az engedményösszegek és az engedményszázalékok kombinációjának eredménye is lehet. Ha ezt a végső kedvezményes árat a sorban lévő mennyiséggel osztja el a rendszer, kerekítés történhet. Ezt a kerekítést azonban nem veszik figyelembe, ha a kerekített egységenkénti engedményösszeg szinkronizálásra kerül a Sales szolgáltatással. Annak érdekében, hogy garantálja, hogy a Finance and Operations értékesítési sorában szereplő teljes árengedmény helyesen szinkronizálva van a Sales-szel, a teljes összeget szinkronizálni kell, anélkül, hogy a sor mennyiségét felosztaná. Emiatt az **Engedményszámítási módszer** beállításnál a **Sortétel** értéket adja meg a Sales-ben.

Amikor egy értékesítésirendelés-sor szinkronizálódik a Sales szolgáltatástól a Finance and Operations felé, az árengedmény teljes összegét használja. Finance and Operations legalább mező nem tárolható egy sor a teljes engedmény összege, az összeg osztva a mennyiséggel és tárolja a **sorengedmény** mező. Az ebben a részlegben előforduló minden kerekítés az **Értékesítési költségek** mezőben tárolódik az értékesítési sorban.

### <a name="example"></a>Példa

**Szinkronizálás Sales szolgáltatásból a Finance and Operations alkalmazásba**

- **Sales:** mennyiség = 3, akkor a sor engedmény = $10.00
- **Finance and Operations:** mennyiség = 3, Sorengedmény összege = $3.33, értékesítési költség = – $0,01 

**Szinkronizálás a Finance and Operations alkalmazásból a Sales szolgáltatásba**

- **Finance and Operations:** mennyiség = 3, Sorengedmény összege = $3.33, értékesítési költség = – $0,01
- **Sales:** mennyiség = 3, akkor a sor engedmény = (3 × $3.33) + $0.01 = $10.00

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

Új mezők kerülnek hozzáadásra a **Rendelés** entitáshoz, és megjelennek a lapon:

- **Külsőleg karbantartva** – beállítása **Igen**, ha a megrendelés a Finance and Operations szolgáltatásból érkezik.
- **Feldolgozás állapota** – a mező a rendelés feldolgozottsági állapotát mutatja a Finance and Operations szolgáltatásban. A következő értékek állnak rendelkezésre:

    - **Vázlat** – A megrendelés kezdeti állapota, amikor egy rendelést hoz létre a Sales-ben. A Sales szolgáltatásban csak az ilyen feldolgozási állapotú rendelések szerkeszthetők.
    - **Aktív** – Az állapot, miután a rendelést aktiválták a Sales szolgáltatásban az **Aktiválás** gombbal.
    - **Visszaigazolva**
    - **Csomagjegyzék**
    - **Számlázva**
    - **Kitárolva**
    - **Részben kitárolva**
    - **Részben csomagolva**
    - **Szállítva**
    - **Részben szállítva**
    - **Részben számlázva**
    - **Visszavonva**

A **Csak külsőleg karbantartott termékei vannak** beállítás rendelésaktiválásnál használatos annak érdekében, hogy konzisztensen követni lehessen, hogy az értékesítési rendelés teljes mértékben külsőleg karbantartott termékekből áll-e. Ha az értékesítési rendelés csak külsőleg fenntartott termékeket tartalmaz, a termékeket a Finance and Operations kezeli. Ez a beállítás garantálja, hogy nem aktiválja és próbálja szinkronizálni az értékesítési rendelési sorokat olyan termékekkel, amelyek ismeretlenek a Finance and Operations számára.

A **Számla létrehozása**, **Rendelés érvénytelenítése**, **Újraszámítás**, **Termékek beszerzése** és **Keresési cím** gombok az **Értékesítési rendelés** oldalon rejtve vannak külsőleg karbantartott rendeléseknél, mivel a számlák a Finance and Operations szolgáltatásban jönnek létre, majd szinkronizálódnak a Sales szolgáltatásba. Ezeket a megrendeléseket nem lehet szerkeszteni, mert az értékesítési rendelési adatok az aktiválás után szinkronizálódnak a Finance and Operations szolgáltatással.

Az értékesítési rendelés állapota **Aktív** marad annak biztosítására, hogy a Finance and Operations módosításai átkerülhessenek az értékesítési rendelésbe a Sales szolgáltatásban. Ennek vezérléséhez az alapértelmezett **Statecode \[állapot\]** értékét **Aktívra** kell állítani az adatintegrációs projektben.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Értékesítési rendelések szinkronizálása előtt fontos frissíteni a rendszert a következő beállításokkal.

### <a name="setup-in-sales"></a>Beállítás a Salesben

- Győződjön meg róla, hogy beállították az engedélyeket ahhoz a csapathoz, amelytől a Sales kapcsolatkészletének felhasználója hozzá van rendelve. Bemutatóadatok használatakor rendszerint a felhasználó rendelkezik rendszergazdai hozzáféréssel, de nem a csoport. Ha a csapatnak nincs adminisztrátori hozzáférése, akkor ha a projektet az adatintegrálásból futtatja, hibaüzenet jelenik meg, amely azt jelzi, hogy a fő csapat hiányzik.

    Lépjen a **Beállítások** &gt; **Biztonság** &gt; **Csapatok** ponthoz, válassza ki a **Szerepkörök kezelése** elemet, és válassza ki a megfelelő engedélyekkel rendelkező szerepkört – pl. **Rendszergazda**.

- Az engedmény megfelelő számításához a Sales és a Finance and Operations esetében, az **Engedményszámítási módszer*** elemet **Sortétel** értékre kell állítani.
- Lépjen a **Beállítások** &gt; **Adminisztráció** &gt; **Rendszerbeállítások** &gt; **Értékesítés** pontra, és győződjön meg róla, hogy a következő beállításokat használja:

    - A **Rendszer díjazási számítási rendszerének használata** beállítás értéke **Igen**.
    - Az **Engedményszámítási módszer** mező értéke a **Sortétel**.

### <a name="setup-in-finance-and-operations"></a>Beállítás a Finance and Operations alkalmazásban

- Lépjen az **Értékesítés és marketing** &gt; **Időszakos feladatok** &gt; **Eladási összegek számítása** lehetőséghez, és állítsa be a feladat futását kötegelt feladatként. Állítsa az **Értékesítési rendelések teljes összegének kiszámítása** beállítást **Igen** értékre. Ez a lépés azért fontos, mert csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a Sales szolgáltatásba. A kötegelt feladat gyakoriságát az értékesítési rendelés szinkronizálásának gyakoriságához kell igazítani.

### <a name="setup-in-the-sales-orders-sales-to-fin-and-ops---direct-data-integration-project"></a>Beállítás Értékesítési rendeléseknél (Fin and Ops – Sales) – Közvetlen adatintegrációs projekt

- Győződjön meg róla, hogy a szükséges leképezés létezik: **Shipto\_country** – **DeliveryAddressCountryRegionISOCode**. Az értéksávban az alapértelmezett értéket üresen hagyhatja, hogy ne írjon be országot az országos megrendelésekhez. Állítsa a bal oldalt az "Üres" értékre, és állítsa a jobb oldalt a kívánt országra vagy régióra.

    A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve, és ahol a "Blank" = Amerikai Egyesült Államok.

### <a name="setup-in-the-sales-orders-fin-and-ops-to-sales---direct-data-integration-project"></a>Beállítás Értékesítési rendeléseknél (Fin and Ops – Sales) – Közvetlen adatintegrációs projekt

#### <a name="salesheader-task"></a>SalesHeader feladat

- Rendeléseknek a Sales szolgáltatásban történő létrehozásához szükség van árlistára. Frissítse a **pricelevelid.name \[Price list name\]** leképezését olyan árlistára, amelyet a Sales is használja valutánként. Az alapértelmezett árlistát használhatja egy pénznemnél. Alternatív megoldásként, ha több pénznemben van árlistája, használhat értékképpontot.

    A sablon alapértelmezett neve **pricelevelid.name \[Árlista neve\]** – **CRM Service USA (minta)**.

#### <a name="salesline-task"></a>SalesLine feladat

- Győződjön meg arról, hogy a **SalesUnitSymbol** szükséges értékmegfeleltetése meg van adva a Finance and Operations szolgáltatásban.
- Győződjön meg róla, hogy a szükséges mértékegységek meghatározása a Sales szolgáltatásban történik.

    Olyan sablonérték, amely rendelkezik értékmegfeleltetéssel a **SalesUnitSymbol** esetében az **oumid.name** értékkel.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

> [!NOTE]
> A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem találhatók meg a alapértelmezett-leképezései. Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.

> [!NOTE]
> A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Finance and Operations irányban, illetve melyek fordítva.

### <a name="sales-orders-fin-and-ops-to-sales---direct-orderheader"></a>Értékesítési rendelések (Fin és Ops – Sales) – Közvetlen: OrderHeader

[![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-fin-and-ops-to-sales---direct-orderline"></a>Értékesítési rendelések (Fin és Ops – Sales) – Közvetlen: OrderLine

[![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-fin-and-ops---direct-orderheader"></a>Értékesítési rendelések (Sales a Fin és Opshoz) – Közvetlen: OrderHeader

[![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-fin-and-ops---direct-orderline"></a>Értékesítési rendelések (Sales a Fin és Opshoz) – Közvetlen: OrderLine

[![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Kapcsolódó témakörök

[A potenciális ügyfelek készpénzre váltása](prospect-to-cash.md)

