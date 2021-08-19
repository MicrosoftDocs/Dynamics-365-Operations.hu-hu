---
title: Potenciális vevők készpénzre váltása kettős írásban
description: Ez a témakör a potenciális vevők készpénzre váltásáról a kettős írásban tartalmaz tájékoztatást.
author: RamaKrishnamoorthy
ms.date: 01/07/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 03bfb5f97b332abb7f34e179d7b294ed2228ab474825a76271f42cc60971a645
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716094"
---
# <a name="prospect-to-cash-in-dual-write"></a>Potenciális vevők készpénzre váltása kettős írásban

[!include [banner](../../includes/banner.md)]

A legtöbb vállalat számára fontos cél a potenciális vevők konvertálása, majd a vevőkkel folytatott folyamatos üzleti kapcsolatok fenntartása. A Microsoft Dynamics 365 alkalmazások esetében a potenciális vevő készpénzre váltásának folyamata az árajánlatok vagy a rendelés feldolgozási munkafolyamatokon keresztül történik, és a program egyezteti és felismeri a pénzügyeket. A potenciális vevők készpénzre váltásának integrációja a kettős írással egy olyan munkafolyamatot hoz létre, amely árajánlatot és egy rendelést a Dynamics 365 Sales vagy Dynamics 365 Supply Chain Management alkalmazásból kezel és az árajánlatot és a rendelést mindkét alkalmazásban elérhetővé teszi.

Az alkalmazások kezelőfelületén a feldolgozási állapotok és a számlázási adatok valós időben érhetők el. Így könnyebben kezelhetők az olyan funkciók, mint a termékek készletezése, a készlet kezelése és a teljesítés a Supply Chain Management alkalmazásban anélkül, hogy újra létre kellene hozni az ajánlatokat és a rendeléseket.

![Kettős írású adatfolyamat a potenciális vevők készpénzre váltása funkcióban.](../dual-write/media/dual-write-prospect-to-cash[1].png)

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
[Minden termék](mapping-reference.md#138) | msdyn_globalproducts | |
[Vevők V3](mapping-reference.md#101) | számlák | |
[Vevők V3](mapping-reference.md#116) | kapcsolattartók | |
[Kapcsolattartók V2](mapping-reference.md#221) | msdyn_contactforparties | |
[CDS értékesítésirendelés-fejlécek](mapping-reference.md#217) | salesorders | |
[CDS értékesítési rendelés sorai](mapping-reference.md#216) | salesorderdetails | |
[CDS értékesítésiajánlat-fejléc](mapping-reference.md#215) | ajánlatok | |
[CDS értékesítési ajánlat sorai](mapping-reference.md#214) | quotedetails | |
[Kiadott termékek V2](mapping-reference.md#189) | msdyn_sharedproductdetails | |
[Értékesítésiszámla-fejlécek V2](mapping-reference.md#118) | számlák | Az értékesítési számla fejlécek V2 táblája a Finance and Operations alkalmazásban tartalmazza az értékesítési rendelések és a szabadszöveges számlák számláit. A Dataverse kettős írás szűrője kiszűri a szabadszöveges számladokumentumokat. |
[Értékesítésiszámla-sorok V2](mapping-reference.md#117) | invoicedetails | |
[Értékesítési rendelés eredetkódjai](mapping-reference.md#186) | msdyn_salesorderorigins | |

Az árlistákkal kapcsolatos tudnivalókat lásd: [Egyesített termékkel kapcsolatos tapasztalat](product-mapping.md).

## <a name="limitations"></a>Korlátozások

- A visszárurendelések nem támogatottak.
- A jóváírások nem támogatottak.
- Az alapadatokhoz, például a vevőhöz és a szállítóhoz, be kell állítani a pénzügyi dimenziókat. Amikor egy vevőt hozzáadnak egy ajánlathoz vagy értékesítési rendeléshez, a vevői rekordhoz kapcsolódó pénzügyi dimenziók automatikusan bekerülnek a rendelésbe. A kettős írás jelenleg nem tartalmazza az alapadatok pénzügyi dimenzióinak adatait.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
