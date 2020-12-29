---
title: Értékesítési rendelés szinkronizálása közvetlenül a Sales szolgáltatás és a Supply Chain Management szolgáltatás között
description: Ez a témakör a sablonokat és alapul szolgáló feladatokat mutatja be, amelyeket használnak az értékesítési rendelések közvetlen szinkronizálásához a Dynamics 365 Sales és a Dynamics 365 Supply Chain Management között.
author: ChristianRytt
manager: tfehr
ms.date: 05/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 3eaa25f0befcff448250ba2cce8e568fa4a4c707
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429712"
---
# <a name="synchronization-of-sales-orders-directly-between-sales-and-supply-chain-management"></a>Értékesítési rendelés szinkronizálása közvetlenül a Sales szolgáltatás és a Supply Chain Management szolgáltatás között

[!include [banner](../includes/banner.md)]

Ez a témakör a sablonokat és alapul szolgáló feladatokat mutatja be, amelyeket használnak az értékesítési rendelések közvetlen szinkronizálásához a Dynamics 365 Sales és a Dynamics 365 Supply Chain Management között.

## <a name="data-flow-in-prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása adatfolyama

A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Supply Chain Management és a Sales példányai között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Supply Chain Management és a Sales között. A következő ábra bemutatja a Supply Chain Management és a Sales közötti adatszinkronizálást.

[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [Power Apps Admin Centert](https://preview.admin.powerapps.com/dataintegration). Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.

A következő sablonokat és alapul szolgáló feladatokat használják az értékesítési rendelések közvetlen szinkronizálásához a Sales és a Supply Chain Management között:

- **A sablonok nevei az adatintegrációban:** 

    - Értékesítési rendelések (Sales – Supply Chain Management) – közvetlen
    - Értékesítési rendelések (Supply Chain Management – Sales) – közvetlen

- **A feladatok nevei az adatintegrációs projektben:**

    - OrderHeader
    - OrderLine

A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési számla fejlécének és sorainak szinkronizálása megtörténhetne:

- Termékek (Supply Chain Management – Sales) – közvetlen
- Számlák (Sales – Supply Chain Management) – közvetlen (ha használatban van)
- Kapcsolatok ügyfelekkel (Sales – Supply Chain Management) – közvetlen (ha használatban van)

## <a name="entity-set"></a>Entitás beállítása

| Ellátásilánc-kezelés  | Értékesítés             |
|-------------------------|-------------------|
| CDS értékesítésirendelés-fejlécek | SalesOrders       |
| CDS értékesítési rendelés sorai   | SalesOrderDetails |

## <a name="entity-flow"></a>Entitás folyamata

Az értékelési rendelések a Sales-ben jönnek létre, és akkor szinkronizálódnak a Supply Chain Management szolgáltatással, amikor a **Projekt futtatása** aktiválódik egy projektnél az **Értékesítési rendelések (Sales – Supply Chain Management) – közvetlen** sablonnál. Csak akkor lehet aktiválni és szinkronizálni a rendeléseket a Sales-től, ha minden **Termékek rendelése** hivatkozás külsőleg karbantartott termékekből áll. Ezért nem lehet írható termék. A rendelés aktiválása után az értékesítési rendelés csak a felhasználói felületen (UI) olvasható. Ezen a ponton a frissítések a Supply Chain Management szolgáltatásból származnak. Miután az értékesítési rendelés állapota **Megerősítve**, az **Értékesítési rendelések (Supply Chain Management – Sales) – Közvetlen** sablon használható a frissítések és a teljesítési állapot szinkronizálásához a Supply Chain Management és a Sales között.

Nem kell rendeléseket létrehoznia a Sales-ben. Ehelyett új értékesítési rendeléseket hozhat létre a Supply Chain Management szolgáltatásban. Miután az értékesítési rendelés állapota **Megerősítve**, az előző bekezdésben leírtak szerint szinkronizálódik a Sales szolgáltatással.

A Supply Chain Management szolgáltatásban a sablonokban lévő szűrők garantálják, hogy csak a vonatkozó értékesítési rendelések szerepelnek a szinkronizálásban:

- A Sales szolgáltatásból származó értékesítési ajánlatban szereplő értékesítési és számlázási vevőnek is szerepelnie kell a szinkronizálásban. A Supply Chain Management szolgáltatásban az **OrderingCustomerIsExternallyMaintained** és az **InvoiceCustomerIsExternallyMaintained** mezők az értékesítési rendelések adatentitásokból való szűrésére szolgálnak.
- Az Értékesítési rendelést a Supply Chain Management szolgáltatásban jóvá kell hagyni. Csak a megerősített értékesítési rendelések vagy magasabb, például **Szállított** vagy **Számlázott** feldolgozási állapotú értékesítési rendelések szinkronizálódnak a Sales szolgáltatásba.
- Értékesítési rendelés létrehozása vagy módosítása után a Supply Chain Management szolgáltatásban végre kell hajtani az **Eladási összegek számítása** kötegelt feladatot. Csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a Sales szolgáltatásba.

## <a name="freight-tax"></a>Fuvardíj

A Sales nem támogatja az adót a fejléc szintjén, mert az adót a vonal szintjén tárolja. A Supply Chain Management fejlécszintű adói, például az áruszállítás adójának támogatása érdekében a rendszer szinkronizálja az adót a Sales felé, mint írható termék, amelynek neve **Fuvardíj**, és az adóösszeg a Supply Chain Management szolgáltatásból származik. Ily módon a Sales árának általános árkalkulációja felhasználható a teljes összegekhez, még akkor is, ha az adó a fejléc szintjén a Supply Chain Management részéről van.

## <a name="discount-calculation-and-rounding"></a>Engedmények kiszámítása és kerekítése

A Sales árengedménykalkulációs modellje különbözik a Supply Chain Management árengedménykalkulációs modelljétől. A Supply Chain Management szolgáltatásban a záró engedmény összege az értékesítési soron az engedményösszegek és az engedményszázalékok kombinációjának eredménye is lehet. Ha ezt a végső kedvezményes árat a sorban lévő mennyiséggel osztja el a rendszer, kerekítés történhet. Ezt a kerekítést azonban nem veszik figyelembe, ha a kerekített egységenkénti engedményösszeg szinkronizálásra kerül a Sales szolgáltatással. Annak érdekében, hogy garantálja, hogy a Supply Chain Management értékesítési sorában szereplő teljes árengedmény helyesen szinkronizálva van a Sales-szel, a teljes összeget szinkronizálni kell, anélkül, hogy a sor mennyiségét felosztaná. Emiatt az **Engedményszámítási módszer** beállításnál a **Sortétel** értéket adja meg a Sales-ben.

Amikor egy értékesítésirendelés-sor szinkronizálódik a Sales szolgáltatástól a Supply Chain Management felé, az árengedmény teljes összegét használja. A Supply Chain Management legalább mező nem tárolható egy sor a teljes engedmény összege, az összeg osztva a mennyiséggel és tárolja a **sorengedmény** mező. Az ebben a részlegben előforduló minden kerekítés az **Értékesítési költségek** mezőben tárolódik az értékesítési sorban.

### <a name="example"></a>Példa

**Szinkronizálás a Sales irányából a Supply Chain Management felé**

- **Sales:** mennyiség = 3, akkor a sor engedmény = $10.00
- **Supply Chain Management:** Mennyiség = 3, Sorengedmény összege = $3,33, Eladási költség =-$0,01 

**Szinkronizálás a Supply Chain Management irányából a Sales felé**

- **Supply Chain Management:** Mennyiség = 3, Sorengedmény összege = $3,33, Eladási költség =-$0,01
- **Sales:** mennyiség = 3, akkor a sor engedmény = (3 × $3.33) + $0.01 = $10.00

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

Új mezők kerülnek hozzáadásra a **Rendelés** entitáshoz, és megjelennek a lapon:

- **Külsőleg karbantartva** – beállítása **Igen**, ha a megrendelés a Supply Chain Management szolgáltatásból érkezik.
- **Feldolgozás állapota** – a mező a rendelés feldolgozottsági állapotát mutatja a Supply Chain Management szolgáltatásban. A következő értékek állnak rendelkezésre:

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

A **Csak külsőleg karbantartott termékei vannak** beállítás rendelésaktiválásnál használatos annak érdekében, hogy konzisztensen követni lehessen, hogy az értékesítési rendelés teljes mértékben külsőleg karbantartott termékekből áll-e. Ha az értékesítési rendelés csak külsőleg fenntartott termékeket tartalmaz, a termékeket a Supply Chain Management kezeli. Ez a beállítás garantálja, hogy nem aktiválja és próbálja szinkronizálni az értékesítési rendelési sorokat olyan termékekkel, amelyek ismeretlenek a Supply Chain Management számára.

A **Számla létrehozása**, **Rendelés érvénytelenítése**, **Újraszámítás**, **Termékek beszerzése** és **Keresési cím** gombok az **Értékesítési rendelés** oldalon rejtve vannak külsőleg karbantartott rendeléseknél, mivel a számlák a Supply Chain Management szolgáltatásban jönnek létre, majd szinkronizálódnak a Sales szolgáltatásba. Ezeket a megrendeléseket nem lehet szerkeszteni, mert az értékesítési rendelési adatok az aktiválás után szinkronizálódnak a Supply Chain Management szolgáltatással.

Az értékesítési rendelés állapota **Aktív** marad annak biztosítására, hogy a Supply Chain Management módosításai átkerülhessenek az értékesítési rendelésbe a Sales szolgáltatásban. Ennek vezérléséhez az alapértelmezett **Statecode \[állapot\]** értékét **Aktívra** kell állítani az adatintegrációs projektben.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Értékesítési rendelések szinkronizálása előtt fontos frissíteni a rendszert a következő beállításokkal.

### <a name="setup-in-sales"></a>Beállítás a Salesben

- Győződjön meg róla, hogy beállították az engedélyeket ahhoz a csapathoz, amelytől a Sales kapcsolatkészletének felhasználója hozzá van rendelve. Bemutatóadatok használatakor rendszerint a felhasználó rendelkezik rendszergazdai hozzáféréssel, de nem a csoport. Ha a csapatnak nincs adminisztrátori hozzáférése, akkor ha a projektet az adatintegrálásból futtatja, hibaüzenet jelenik meg, amely azt jelzi, hogy a fő csapat hiányzik.

    Lépjen a **Beállítások** &gt; **Biztonság** &gt; **Csapatok** ponthoz, válassza ki a **Szerepkörök kezelése** elemet, és válassza ki a megfelelő engedélyekkel rendelkező szerepkört – pl. **Rendszergazda**.

- Az engedmény megfelelő számításához a Sales és a Supply Chain Management esetében az **Engedményszámítási módszer** elemet **Sortétel** értékre kell állítani.
- Lépjen a **Beállítások** &gt; **Adminisztráció** &gt; **Rendszerbeállítások** &gt; **Értékesítés** pontra, és győződjön meg róla, hogy a következő beállításokat használja:

    - A **Rendszer díjazási számítási rendszerének használata** beállítás értéke **Igen**.
    - Az **Engedményszámítási módszer** mező értéke a **Sortétel**.

### <a name="setup-in-supply-chain-management"></a>Beállítások a Supply Chain Management rendszerben

- Lépjen az **Értékesítés és marketing** &gt; **Időszakos feladatok** &gt; **Eladási összegek számítása** lehetőséghez, és állítsa be a feladat futását kötegelt feladatként. Állítsa az **Értékesítési rendelések teljes összegének kiszámítása** beállítást **Igen** értékre. Ez a lépés azért fontos, mert csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a Sales szolgáltatásba. A kötegelt feladat gyakoriságát az értékesítési rendelés szinkronizálásának gyakoriságához kell igazítani.

Ha a munkarendelés integrációját is használja, akkor be kell állítania az értékesítési forrást. Az értékesítés forrása használatos azon értékesítési rendelések megkülönböztetésére a Supply Chain Management szolgáltatásban, amelyek a Field Service szolgáltatásban lévő munkarendelésekből jöttek létre. Ha egy értékesítési rendelés értékesítési eredetű a **Munkarendelés-integráció** típusból, a **Külső munkarendelés állapota** mező megjelenik az értékesítési rendelés fejlécében. Ezenkívül az értékesítés származásának segítségével garantálható, hogy munkarendelésekből a Field Service szolgáltatásban létrejött értékesítési rendelések kiszűrésre kerüljenek, amikor az értékesítési rendelések szinkronizálása zajlik a Supply Chain Management szolgáltatásból a Field Service szolgáltatásba.

1. Válassza az **Értékesítés és marketing** \> **Beállítás** \> **Értékesítési rendelések** \> **Értékesítési forrás** lehetőséget.
2. Válassza az **Új** elemet új értékesítési forrás létrehozásához.
3. Az **Értékesítési forrás** mezőbe írjon be egy nevet az értékesítés eredetének, például **SalesOrder**.
4. A **Leírás** mezőben adjon meg egy leírást, például **Értékesítési munkarendelés**.
5. Jelölje be az **Eredettípus hozzárendelése** négyzetet.
6. Állítsa az **Értékesítési forrás típusa** mezőt **Értékesítésirendelés-integráció** értékre.
7. Válassza a **Mentés** lehetőséget.

### <a name="setup-in-the-sales-orders-sales-to-supply-chain-management---direct-data-integration-project"></a>Beállítás Értékesítési rendeléseknél (Sales – Supply Chain Management) – Közvetlen adatintegrációs projekt

- Győződjön meg róla, hogy a szükséges leképezés létezik: **Shipto\_country** – **DeliveryAddressCountryRegionISOCode**. Az értéksávban az alapértelmezett értéket üresen hagyhatja, hogy ne írjon be országot az országos megrendelésekhez. Állítsa a bal oldalt az "Üres" értékre, és állítsa a jobb oldalt a kívánt országra vagy régióra.

    A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve, és ahol a "Blank" = Amerikai Egyesült Államok.

### <a name="setup-in-the-sales-orders-supply-chain-management-to-sales---direct-data-integration-project"></a>Beállítás Értékesítési rendeléseknél (Supply Chain Management – Sales) – Közvetlen adatintegrációs projekt

#### <a name="salesheader-task"></a>SalesHeader feladat

- Rendeléseknek a Sales szolgáltatásban történő létrehozásához szükség van árlistára. Frissítse a **pricelevelid.name \[Price list name\]** leképezését olyan árlistára, amelyet a Sales is használja valutánként. Az alapértelmezett árlistát használhatja egy pénznemnél. Alternatív megoldásként, ha több pénznemben van árlistája, használhat értékképpontot.

    A sablon alapértelmezett neve **pricelevelid.name \[Árlista neve\]** – **CRM Service USA (minta)**.

#### <a name="salesline-task"></a>SalesLine feladat

- Győződjön meg arról, hogy a **SalesUnitSymbol** szükséges értékmegfeleltetése létezik a Supply Chain Management szolgáltatásban.
- Győződjön meg róla, hogy a szükséges mértékegységek meghatározása a Sales szolgáltatásban történik.

    Olyan sablonérték, amely rendelkezik értékmegfeleltetéssel a **SalesUnitSymbol** esetében az **oumid.name** értékkel.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

> [!NOTE]
> A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem találhatók meg a alapértelmezett-leképezései. Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.

> [!NOTE]
> A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Supply Chain Management irányban, illetve melyek fordítva.

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderheader"></a>Értékesítési rendelések (Supply Chain Management – Sales) – közvetlen: OrderHeader

[![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderline"></a>Értékesítési rendelések (Supply Chain Management – Sales) – közvetlen: OrderLine

[![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderheader"></a>Értékesítési rendelések (Sales – Supply Chain Management) – közvetlen: OrderHeader

[![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderline"></a>Értékesítési rendelések (Sales – Supply Chain Management) – közvetlen: OrderLine

[![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Kapcsolódó témakörök

[A potenciális ügyfelek készpénzre váltása](prospect-to-cash.md)
