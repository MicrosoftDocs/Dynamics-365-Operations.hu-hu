---
title: Potenciális vevők készpénzre váltása kettős írásban
description: Ez a témakör a potenciális vevők készpénzre váltásáról a kettős írásban tartalmaz tájékoztatást.
author: RamaKrishnamoorthy
ms.date: 01/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 33ed1c7f69fa92bbd123042a139dd8fd0ee3e73a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754088"
---
# <a name="prospect-to-cash-in-dual-write"></a>Potenciális vevők készpénzre váltása kettős írásban

[!include [banner](../../includes/banner.md)]



A legtöbb vállalat számára fontos cél a potenciális vevők konvertálása, majd a vevőkkel folytatott folyamatos üzleti kapcsolatok fenntartása. A Microsoft Dynamics 365 alkalmazások esetében a potenciális vevő készpénzre váltásának folyamata az árajánlatok vagy a rendelés feldolgozási munkafolyamatokon keresztül történik, és a program egyezteti és felismeri a pénzügyeket. A potenciális vevők készpénzre váltásának integrációja a kettős írással egy olyan munkafolyamatot hoz létre, amely árajánlatot és egy rendelést a Dynamics 365 Sales vagy Dynamics 365 Supply Chain Management alkalmazásból kezel és az árajánlatot és a rendelést mindkét alkalmazásban elérhetővé teszi.

Az alkalmazások kezelőfelületén a feldolgozási állapotok és a számlázási adatok valós időben érhetők el. Így könnyebben kezelhetők az olyan funkciók, mint a termékek készletezése, a készlet kezelése és a teljesítés a Supply Chain Management alkalmazásban anélkül, hogy újra létre kellene hozni az ajánlatokat és a rendeléseket.

![Kettős írású adatfolyamat a potenciális vevők készpénzre váltása funkcióban](../dual-write/media/dual-write-prospect-to-cash[1].png)

A vevői és kapcsolattartói integrációval kapcsolatos tudnivalókat lásd: [Integrált vevői alapadatok](customer-mapping.md). A termékintegrációval kapcsolatos tudnivalókat lásd: [Egyesített termékkel kapcsolatos tapasztalat](product-mapping.md).

> [!NOTE]
> A Dynamics 365 Sales megoldásban mind a potenciális vevő, mind a vevő egy olyan rekordra hivatkozik a **Számla** táblában, ahol a **RelationshipType** oszlop **Potenciális vevő** vagy **Vevő**. Ha az üzleti logikában szerepel egy **Számla** minősítési folyamat, ahol a **Számla** rekordot létrehozták, majd előbb potenciális vevőként, majd vevőkén minősítették, akkor ez a rekord csak akkor szinkronizál a Finance and Operations alkalmazással, amikor az egy vevő (`RelationshipType=Customer`). Ha azt szeretné, hogy a **Számla** sor potenciális vevőként szinkronizálva legyen, a potenciális vevői adatok integrálásához egyéni leképezés szükséges.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Az értékesítési ajánlatok szinkronizálása előtt frissíteni kell a következő beállításokat.

### <a name="setup-in-sales"></a>Beállítás a Salesben

A Sales alkalmazásban válassz a **Beállítások \> Adminisztráció \> Rendszerbeállítások \> Értékesítés** lehetőséget, és győződjön meg róla, hogy a következő beállításokat használja:

- A **Rendszer díjazási számítási** rendszerének használata beállítás értéke **Igen**.
- Az **Engedményszámítási módszer** oszlop értéke a **Sortétel**.

### <a name="sites-and-warehouses"></a>Telephelyek és raktárak

A Supply Chain Management alkalmazásban az ajánlati sorokban és a rendelési sorokban kötelező megadni a **Telephely** és **Raktár** oszlopokat. Ha az alapértelmezett rendelés beállításaiban beállítja a telephelyet és a raktárat, akkor a program automatikusan beállítja ezeket az oszlopokat, amikor terméket ad hozzá egy ajánlati sorhoz vagy egy rendelési sorhoz. 

### <a name="number-sequences-for-quotations-and-orders"></a>Számsorozatok árajánlatokhoz és rendelésekhez

A Supply Chain Management és a Sales számsorozatai nem kapcsolódnak, amikor árajánlatokat és rendeléseket hoz létre, és szinkronizálja azokat a Sales és Supply Chain Management alkalmazásokban. Ha a Sales alkalmazásban létrehozott értékesítési rendelés szinkronizálva van a Supply Chain Management alkalmazásba, ugyanaz az értékesítésirendelés-száma van a Supply Chain Management alkalmazásban. Annak elősegítéséhez, hogy az értékesítési rendelés száma ne legyen duplikálva, a két alkalmazásban különböző számsorozat-rendszereket kell használni.

Például a Supply Chain Management számsorozata **1, 2, 3, 4, 5, ...**, a Sales számsorozata pedig **100, 99, 98, ...**. Ha 100 értékesítési rendelést hoz létre a Sales alkalmazásban, akkor az végül létrejön egy olyan szám, ami már létezik a Supply Chain Management alkalmazásban. Más szóval a két számsorozat átfedésben lesz, mivel az értékesítési rendeléseket a Supply Chain Management és a Sales alkalmazásokban is létrehozzák. Helyette lehet használni egy más számsorozatot, például **F1, F2, F3, ...** a Supply Chain Management alkalmazásban és egy másik számsorozatot, például **C1, C2, C3, ...** a Sales alkalmazásban. Ezek a Számsorozatok soha nem hoznak létre dupla értékesítési rendelési számokat.

## <a name="sales-quotations"></a>Értékesítési ajánlatok

Az értékesítési ajánlat létrehozása a Sales vagy Supply Chain Management programban történik. Ha a Sales alkalmazásban árajánlatot hoz létre, akkor a rendszer valós időben szinkronizálja a Supply Chain Management alkalmazásba. Hasonlóan, ha a Supply Chain Management alkalmazásban árajánlatot hoz létre, akkor a rendszer valós időben szinkronizálja a Sales alkalmazásba. Vegye figyelembe az alábbiakat:

+ A termékre kedvezmény adható az árajánlatban. Ebben az esetben a rendszer szinkronizálja az engedményt a Supply Chain Management alkalmazásba. A fejlécen az **Engedmény**, **Költségek** és **Adó** oszlopok a Supply Chain Management szolgáltatásból szabályozhatók. Ez a beállítás nem támogatja integrációs megfeleltetést. Ehelyett az **Ár**, **Engedmény**, **Költség**, és **Adó** oszlopok karbantartása és kezelése a Supply Chain Management alkalmazásban történik.
+ Az **Árengedmény %** **Árengedmény** és **Szállítási mennyiség** oszlopok az értékesítési ajánlat fejlécében csak olvashatók.
+ A **Szállítási feltételek**, **Kiszállítási feltételek**, **Szállítási módszer** és **Szállítási mód** oszlopok nem találhatók meg az alapértelmezett leképezésekben. Ezen oszlopok megfeleltetéséhez be kell állítania egy értékmegfeleltetést, amely az adott szervezetek adataira specifikus, amelyek között a tábla szinkronizálódik.

Ha a Field Service megoldást is használja, mindenképpen engedélyezze újra az **ajánlati sor gyorslétrehozása** paraméterét. A paraméter ismételt engedélyezése lehetővé teszi az Árajánlati sorok létrehozásának folytatását a gyorslétrehozás funkció segítségével.
1. Keresse meg a Dynamics 365 Sales alkalmazást.
2. A felső navigációs sávon válassza ki a beállítások ikont.
3. Válassza a **Speciális beállítások** elemet.
4. Válassza ki a **Rendszer testreszabása** beállítást.
5. Válassza ki az **Ajánlati sor** menüelemét.
6. Nyissa meg az **Adatszolgáltatások** szakaszt, és jelölje be a **Gyors létrehozás engedélyezése** jelölőnégyzetet.

## <a name="sales-orders"></a>Értékesítési rendelés

Az értékesítési rendelések létrehozása a Sales vagy Supply Chain Management programban történik. Ha a Sales alkalmazásban értékesítési rendelést hoz létre, akkor a rendszer valós időben szinkronizálja a Supply Chain Management alkalmazásba. Hasonlóan, ha a Supply Chain Management alkalmazásban értékesítési rendelést hoz létre, akkor a rendszer valós időben szinkronizálja a Sales alkalmazásba. Vegye figyelembe az alábbiakat:

+ A Dynamics 365 Sales alkalmazásban az írható termékek termékkategóriákként jelennek meg a Dynamics 365 Supply Chain Management alkalmazásban.
+ Engedmények kiszámítása és kerekítése:

    - A Sales árengedménykalkulációs modellje különbözik a Supply Chain Management árengedménykalkulációs modelljétől. A Supply Chain Management szolgáltatásban a záró engedmény összege az értékesítési soron az engedményösszegek és az engedményszázalékok kombinációjának eredménye is lehet. Ha ezt a végső kedvezményes árat a sorban lévő mennyiséggel osztja el a rendszer, kerekítés történhet. Ezt a kerekítést azonban nem veszik figyelembe, ha a kerekített egységenkénti engedményösszeg szinkronizálásra kerül a Sales szolgáltatással. Annak érdekében, hogy biztosítsa, hogy a Supply Chain Management értékesítési sorában szereplő teljes árengedmény helyesen szinkronizálva van a Sales-szel, a teljes összeget szinkronizálni kell, anélkül, hogy a sor mennyiségét felosztaná. Emiatt az Engedményszámítási módszer beállításnál a **Sortétel** értéket adja meg a Sales-ben.
    - Amikor egy értékesítésirendelés-sor szinkronizálódik a Sales szolgáltatástól a Supply Chain Management felé, az árengedmény teljes összegét használja. A Supply Chain Management legalább oszlop nem tárolható egy sor a teljes engedmény összege, az összeg osztva a mennyiséggel és tárolja a **sorengedmény** oszlop. Az ebben a részlegben előforduló minden kerekítés az **Értékesítési költségek** oszlopban tárolódik az értékesítési sorban.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Példa: Szinkronizálás a Sales irányából a Supply Chain Management felé

A következő értékesítési rendelése van:

+ **Sales:** mennyiség = 3, akkor a sor engedmény = $10.00
+ **Supply Chain Management:** Mennyiség = 3, Sorengedmény összege = $3,33, Eladási költség =–0,01 USD

Ha a Supply Chain Management alkalmazásól a Sales alkalmazásba szinkronizál, a következő eredményt kapja:

+ **Supply Chain Management:** Mennyiség = 3, Sorengedmény összege = $3,33, Eladási költség =–0,01 USD
+ **Sales:** mennyiség = 3, akkor a sor engedmény = (3 × $3.33) + $0.01 = $10.00

## <a name="dual-write-solution-for-sales"></a>Kettős írási megoldás a Saleshez

Új oszlopok kerülnek hozzáadásra a **Rendelés** táblához, és megjelennek a lapon. Ezeknek az oszlopoknak a többsége megjelenik az értékesítés modul **Integráció** lapján. Ha további információkat szeretne arról, hogyan lehet leképezni az állapot oszlopokat, lásd: [Értékesítési rendelés állapotához tartozó oszlopok alapján történő leképezés beállításhoz](sales-status-map.md).

+ A **Számla létrehozása** és a **Rendelés törlése** gombok az **Értékesítési rendelés** oldalon rejtettek a Salesben.
+ Az **Értékesítési rendelés állapota** érték **Aktív** marad annak biztosítására, hogy a Supply Chain Management módosításai átkerülhessenek az értékesítési rendelésbe a Sales szolgáltatásban. Ennek vezérléséhez az alapértelmezett **Statecode \[állapot\]** értékét **Aktívra** kell állítani.

## <a name="invoices"></a>Számlák

Az értékesítési számlák létrehozása a Supply Chain Management történik, majd szinkronizálódnak a Sales programban. Vegye figyelembe az alábbiakat:

+ Egy **Számla száma** oszlop hozzáadódik a **Számla** táblához, és megjelenik a lapon.
+ A **Számla létrehozása** gomb az **Értékesítési rendelés** lapon rejtve van, mivel a számlák létrehozása a Supply Chain Management szolgáltatásban történik, és szinkronizálódik a Sales szolgáltatásba. A **Számla** lap tartalma nem szerkeszthető, mert a számlák a Supply Chain Management szolgáltatásból szinkronizálódnak.
+ Az **Értékesítési rendelés állapota** automatikusan **Számlázott** értékre változik, amikor a Supply Chain Management szolgáltatásból a kapcsolódó számla szinkronizálása a Sales szolgáltatásba megtörténik. Az értékesítési rendelés tulajdonosa, amelyből a számlát létrehozták, hozzárendelésre kerül a számla tulajdonosaként. Emiatt az értékesítési rendelés tulajdonosa megtekintheto a számlát.
+ A **Szállítási feltételek**, **Kiszállítási feltételek** és **Kiszállítási mód** oszlopok nem szerepelnek az alapértelmezett leképezésekben. Ezen oszlopok megfeleltetéséhez be kell állítania egy értékmegfeleltetést, amely az adott szervezetek adataira specifikus, amelyek között a tábla szinkronizálódik.

## <a name="templates"></a>Sablonok

A Potenciális vevők készpénzre váltása tartalmazza azokat a központi táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.

| Finance and Operations-alkalmazásoknak | Customer Engagement alkalmazások | Leírás |
|-----------------------------|-----------------------------------|-------------|
| Értékesítésiszámla-fejlécek V2    | számlák                          | Az értékesítési számla fejlécek V2 táblája a Finance and Operations alkalmazásban tartalmazza az értékesítési rendelések és a szabadszöveges számlák számláit. A Dataverse kettős írás szűrője kiszűri a szabadszöveges számladokumentumokat. |
| Értékesítésiszámla-sorok V2      | invoicedetails                    |             |
| CDS értékesítésirendelés-fejlécek     | salesorders                       |             |
| CDS értékesítési rendelés sorai       | salesorderdetails                 |             |
| Értékesítési rendelés eredetkódjai    | msdyn\_salesorderorigins          |             |
| CDS értékesítésiajánlat-fejléc  | ajánlatok                            |             |
| CDS értékesítési ajánlat sorai   | quotedetails                      |             |

Itt találhatók a kapcsolódó alaptáblák leképezései a Potenciális vevők készpénzre váltásához:

+ [V3 vevők a számlákhoz](customer-mapping.md#customers-v3-to-accounts)
+ [CDS V2 kapcsolattartók hozzáadása a kapcsolatok mappához](customer-mapping.md#cds-contacts-v2-to-contacts)
+ [V3 ügyfelek a kapcsolatokhoz](customer-mapping.md#customers-v3-to-contacts)
+ [Az msdyn_sharedproductdetails kiadott termékei](product-mapping.md#released-products-v2-to-msdyn_sharedproductdetails)
+ [A msdyn_globalproducts összes terméke](product-mapping.md#all-products-to-msdyn_globalproducts)
+ [Árlista](product-mapping.md)

## <a name="limitations"></a>Korlátozások
- A visszárurendelések nem támogatottak.
- A jóváírások nem támogatottak.
- Az alapadatokhoz, például a vevőhöz és a szállítóhoz, be kell állítani a pénzügyi dimenziókat. Amikor egy vevőt hozzáadnak egy ajánlathoz vagy értékesítési rendeléshez, a vevői rekordhoz kapcsolódó pénzügyi dimenziók automatikusan bekerülnek a rendelésbe. A kettős írás jelenleg nem tartalmazza az alapadatok pénzügyi dimenzióinak adatait. 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [sales invoice](includes/SalesInvoiceHeaderV2Entity-invoice.md)]

[!include [sales invoice line](includes/SalesInvoiceLineV2Entity-invoicedetail.md)]

[!include [sales order header](includes/SalesOrderHeaderCDSEntity-salesorder.md)]

[!include [sales order line](includes/SalesOrderLineCDSEntity-salesorderdetails.md)]

[!include [sales order origin](includes/SalesOrderOriginEntity-msdyn-salesorderorigin.md)]

[!include [sales quotation header](includes/SalesQuotationHeaderCDSEntity-quote.md)]

[!include [sales quotation line](includes/SalesQuotationLineCDSEntity-QuoteDetails.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]