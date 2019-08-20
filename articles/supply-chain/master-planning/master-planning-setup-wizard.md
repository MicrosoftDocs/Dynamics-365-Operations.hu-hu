---
title: Alaptervezés-beállítási varázsló
description: Ez a témakör az alaptervezés beállításához használt különböző fontos stratégiákat és paramétereket ismerteti.
author: t-benebo
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 9cc2d99a8dfc28f8d9a9b36a5b74059a515822b9
ms.sourcegitcommit: 299e20b59ebefa584ed46a13da3f1a7ff709e43c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863609"
---
# <a name="master-planning-setup-wizard"></a>Alaptervezés-beállítási varázsló

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

Ez a témakör útmutatót tartalmaz az **Alaptervezés-beállítási varázsló** funkcióhoz. Bemutatja a paraméterjavaslatok kiszámításának módját, valamint példákat is tartalmaz, amelyek bemutatják, hogy a különböző vállalatok hogyan állíthatják be az alaptervezést az üzleti igényeik alapján.

## <a name="specific-requirements-of-your-company"></a>A vállalat egyedi igényei

A varázsló első oldala a vállalat egyedi igényeire kérdez rá. Az ezekre a kérdésekre adott válaszainak nem kell pontosnak lenniük, de hozzávetőleges információt kell biztosítaniuk a jogi személy esetén rendelkezésre álló cikkek és tervezett megrendelések számáról. A válaszait a rendszer a jogi személyre vonatkozó paraméterek konfigurálására használja, nem csak a kiválasztott alaptervezésre. A következő szakaszok a kiszámított paramétereket és a használt képleteket ismertetik.

### <a name="number-of-threads"></a>Szálak száma

- **Ha a vállalat a cikkek bármekkora részét gyártják:** Szálak száma = Tervezett rendelések száma ÷ 1000
- **Ha a vállalat nem gyártja a cikkek bármekkora részét:** Szálak száma = Cikkek száma ÷ 1000

Ha a szálak kiszámított száma meghaladja a rendelkezésre álló szálak számát, akkor a rendszer az egyes vevőkhöz rendelkezésre álló szálak számát 75%-ra korlátozza. (A rendelkezésre álló szálak száma az egyes vevőknél lesz meghatározva.)

További információért tekintse meg a [Szálak száma](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-threads) részt.

### <a name="bundle-size"></a>Csomag mérete

A csomagméret értékét **1**-re állítja a rendszer. Ez az érték gyakran a legjobb érték, mivel segít az Alaptervezés teljesítményének javításában.

További információ: [A segítő feladatcsomagban található feladatok száma](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-tasks-in-helper-task-bundle).

### <a name="firming-bundle-size"></a>Megerősítő csomagméret

- **Ha valamelyik cikket az Ön vállalata gyártja:** A megerősítő csomagméret a következő két érték közül a nagyobbra lesz állítva: **10** és a csomagszámítás értéke
- **Ha egyik cikket sem az Ön vállalata gyártja:** A megerősítő csomagméret a következő két érték közül a nagyobbra lesz állítva: **50** és a csomagszámítás értéke

Csomagszámítás = (Tervezett rendelések száma × (Megerősítési időkorlát ÷ Fedezeti idő kerítés) ÷ Szálak száma) ÷ 10

### <a name="cache-size"></a>Gyorsítótár mérete

A gyorsítótár értékét **Maximum**-ra állítja a rendszer. Ez az érték gyakran a legjobb érték, mivel segít az Alaptervezés teljesítményének javításában.

További információ: [Idők hozzárendelése egy feladatköteg feladataihoz](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/allocate-time-jobs-job-bundle).

### <a name="manufacturing-setup"></a>Gyártási beállítás

Ha gyártanak cikkeket, akkor a varázslóban később megjelenik a **Gyártási beállítás** oldal.

## <a name="scope-of-the-current-plan"></a>Aktuális terv hatóköre

A varázsló **Aktuális terv hatóköre** oldalán meg kell válaszolnia kérdéseket, amelyek arra vonatkoznak, hogy milyen távol a jövőben vegye figyelembe a rendszer a különböző követelményeket, és számítsa ki őket az alaptervezésben. Minden kérdés megkérdezi, hogy szeretne-e használni egy funkciót, és hogyan kívánja konfigurálni.

Az előrejelzési terv funkciónál például a varázsló megkérdezi, hogy „Szeretné-e használni az előrejelzési tervet az alaptervezésben, és így a tervezett rendeléseknél a rendszer javaslatot tesz az előrejelzett igény kielégítésére?”

Ehhez a következő lehetőségek állnak rendelkezésre:

- **Nem** – Az Alaptervezés nem javasol tervezett rendeléseket egy előrejelzés kielégítésére. Az **Alaptervezés** oldal **Időkorlát** lapján (**Alaptervezés \> Beállítás \> Tervek \> Alaptervek**) a varázsló beállítja az **Előrejelzési terv (időkorlát)** értékét **Igen** értékre, a napok számát pedig **0** (nulla) értékre. Ez a beállítás felülbírálja a fedezeti csoportban megadott időkorlátot. Mivel a napok száma **0** (nulla), a szolgáltatás nem lesz használatban.
- **Igen, ebben az alaptervben definiáltak szerint** – A mező elérhetővé válik, ahol megadhatja, hogy az Alaptervezés hány napig javasoljon tervezett rendeléseket az előrejelzett igény kielégítésére. A varázsló beállítja az **Előrejelzési terv (időkorlát)** értékét **Igen** értékre, a napok számát pedig az **Alaptervezés** oldal **Időkorlátok** lapjának **Előrejelzési terv** mezőjében megadott napok számára. Ez a beállítás felülírja a fedezeti csoportokban beállított értékeket.
- **Igen, a fedezetben való meghatározás szerint** – A varázsló az **Előrejelzési terv (időkorlát)** beállítást **Nem** értékre állítja. A fedezeti csoportban megadott időkorlátok határozzák meg, hogy mennyi ideig fog tervezni az előrejelzés.

Az oldal további kérdései és válaszai ugyanezt a sémát követik:

- **Nem** – az **Előrejelzési terv (időkorlát)** beállítása **Igen**, és a napok száma **0** (nulla) értékre lesz állítva.
- **Igen, az adott alaptervben való meghatározás szerint** – Az **Előrejelzési terv (időkorlát)** beállítás **Igen** értékre lesz állítva. A beírt napok számát fogja használni a rendszer, és felülírja a fedezeti csoportokban beállított értékeket.
- **Igen, a fedezeti csoportban való meghatározás szerint** – Az **Előrejelzési terv (időkorlát)** beállítás **Nem** értékre lesz állítva.

További információ: [Feladatütemezés](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="scheduling-options"></a>Ütemezési beállítások

Az **Ütemezési beállítások** oldal csak akkor jelenik meg, ha **Igen** választ adott a „Ön gyártja a tervezett cikkek bármelyikét?” kérdésre a varázsló első oldalán.

Az adott oldalon az első kérdésre adott válasza („Szeretné a műveleteket egyéni feladatokra felosztva ütemezni?”) meghatározza az **Alaptervek** oldal **Általános** lapján található ütemezési módszert.

- **Igen** – A program a feladatütemezést használja.
- **Nem** – A program a műveletütemezést használja.

További információk: [Műveletütemezés](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling) és [Feladatütemezés](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="updates-of-demand-and-supply"></a>Az igény és ellátás frissítései

Az **Igény és ellátás frissítései** oldal kérdései a megerősítéshez, műveleti üzenetekhez és késésekhez kapcsolódnak.

Az alaptervezési beállítást a válaszok alapján frissíti a rendszer, ugyanolyan séma alapján, amelyet az előző szakaszban ismertettünk:

- **Nem** – az **Alaptervek** oldalon az **Időkorlát** beállítás értéke **Igen** lesz, és a napok száma **0** (nulla) értékre lesz állítva.
- **Igen, az adott alaptervben való meghatározás szerint** – Az **Időkorlát** beállítás **Igen** értékre lesz állítva. A beírt napok számát fogja használni a rendszer, és felülírja a fedezeti csoportokban beállított értékeket.
- **Igen, a fedezeti csoportban való meghatározás szerint** – Az **Időkorlát** beállítás **Nem** értékre lesz állítva.

A számított késések esetén a varázsló kérdéseire adott válaszai frissítik a kapcsolódó paramétereket az **Alaptervek** oldal **Számított késések** lapján.

## <a name="summary-of-your-changes"></a>Módosítások összefoglalása

A varázsló utolsó lapja azokat a változtatásokat jeleníti meg, amelyeket a válaszok alapján ajánlottak. Mind a beállítás értékeit (**Aktuális beállítás**), mind a varázsló által javasolt értékeket (**Új konfiguráció**) megjeleníti.

A paramétereket az új konfigurációban is módosíthatja. A paraméterek elkülönülnek az adott jogi személyre vonatkozó paraméterekre, és a csak a kiválasztott alaptervre vonatkozó paraméterekre. A varázslóval módosítható összes beállítási paraméter megjelenítéséhez jelölje be az **Összes paraméter megjelenítése** lehetőséget a lap alján. Ezután módosíthatja a paramétereket.

Végül, amikor a **Befejezés** lehetőséget választja, a rendszer alkalmazza az új konfigurációt. Ha a **Mégse** lehetőséget választja, a módosítások egyike sem lesz alkalmazva.

## <a name="examples"></a>Példák

Ez a rész két kitalált vállalat beállításait írja le, hogy megmutassa, hogyan változhatnak a beállítások az egyes vállalatok igényei szerint.

### <a name="example-1-contoso-manufacturer"></a>1. példa: Contoso Manufacturer

A Contoso Manufacturer olyan gyártó cég, amely hangszórókat gyárt. Megvásárolja azokat a különböző nyersanyagokat és alkatrészeket különböző szállítóktól, amelyeket a végtermék hangszórókhoz használnak. Íme az ellátás és a gyártás néhány jellemzője:

- A vállalat által gyártott végső cikkek anyagjegyzék-struktúrával (BOM) rendelkeznek.
- A végső cikkeket és alkatrészeket az Alaptervezés tervezi. A manuális tervezés nem történik meg.
- Az egyes végleges cikkek előállításához műveleti útvonalat definiáltak.
- A végső cikkeket a gyártóüzem termeli. Ebben meghatározott mennyiségű maró- és fúrógép található, amik az alkatrészek feldolgozására használatosak. A különböző alkatrészeket ezekkel a gépekkel kell feldolgozni.
- Sok beszállítójuk van. A cikkek átlagos átfutási ideje egy hét. Az ugyanattól a szállítótól származó cikkcsoportok átfutási ideje 7 hét.

A varázslóban a Contoso Manufacturer vállalathoz a következő értékeket adták meg:

- **Fedezet:**

    - **Kérdés:** Meg szeretné adni a tervezési horizont napjainak számát?
    - **Válasz:** „Igen, a fedezetcsoportokban meghatározottak szerint.”

    Mivel a cikkek átfutási ideje nagyon eltérő, a Contoso számára nem kell megtervezni az összes cikket ugyanahhoz a jövőbeli időszakhoz. Létrejönnek a cikkekhez tartozó fedezeti csoportok. A hasonló átfutási idővel rendelkező cikkek ugyanahhoz a fedezeti csoporthoz tartoznak. Az egyes fedezeti csoportok tervezési horizontja (azaz a fedezeti időkorlát) megközelítőleg az átfutási idő plusz egy egy hetes különbözet. Az Alaptervezés ezután biztosítja, hogy a cikkek előre tervezettek legyenek, az átfutási idő alapján.

    Ezért ehhez a példához két fedezeti csoport jön létre. Az egyik fedezeti csoport fedezeti időkorlátja két hét lesz, a másiké pedig nyolc hét.

    Ha **Igen, az adott alaptervben való meghatározás szerint** a válasz, akkor a megadott napok számának meg kell haladnia az összes cikk közül a leghosszabb átfutási idejét. Mivel azonban sok cikket nem kell előre tervezni, sok tervezett rendelés kerül kiszámításra, de sosem kerül felhasználásra. Ezért az Alaptervezés futási ideje növekedni fog.

- **Ütemezés:**

    - **Kérdés:** „Szeretné a műveleteket egyéni feladatokra felosztva ütemezni?”
    - **Válasz:** „Igen”.

    A Contoso Manufacturing vállalatnak meg kell terveznie és ütemeznie az egyéni feladatokat, amelyeket az üzemben végre kell hajtani. Ezért a feladatütemezést fogja használni.

- **Kapacitás:**

    - **Kérdés:** „Szeretne az erőforrások kapacitását használva ütemezni?”
    - **Válasz:** „Igen, az alaptervben meghatározottak szerint.” **10 napot** kell beírni.

    A maró- és fúrógépek száma korlátozott. A termeléstervezésben figyelembe kell venni ezt a korlátozást, és az erőforrások kapacitása szerint kell időben rendezni a munkákat. Más szóval az ütemezett feladatokat az erőforrások korlátai alapján újratervezi a program. A tervezés az átfutási időt a megadott időszakon kívül fogja használni. (A tervezett termelési rendelések átfedhetik egymást.) Mivel a cikkek gyártási átfutási ideje hét nap, az alaptervezéshez az erőforrások kapacitását 10 napon keresztül veszi figyelembe a rendszer.

- **Sorrendbe állítás:**

    - **Kérdés:** „Szeretné sorrendbe állítani a tervezett rendelések a termék sorrendi értékei alapján?”
    - **Válasz:** „Igen, a fedezetcsoportokban meghatározottak szerint.”

    Az egyes végleges cikkek előállításához útvonalat definiáltak. Így az alaptervezés a rendeléseket időben a meghatározott útvonalaknak megfelelően fogja ütemezni.

- **Alábontás:**

    - **Kérdés:** „Szeretne rendeléseket tervezni egy anyagjegyzék minden eleméhez (a fölérendelt és az összes alárendelt cikkhez tervezni)?”
    - **Válasz:** „Igen, a fedezetcsoportokban meghatározottak szerint.”

    Minden, a termeléshez felhasznált cikket meg kell tervezni. Mivel a cikkek eltérő átfutási idővel rendelkeznek, az Alaptervezés jobb teljesítményt hozhat, amikor a fedezeti csoportokat használja. Ismét egy hetes különbözetet adnak meg, és az alábontás ugyanarra az időszakra végezhető, mint a fedezet.

### <a name="example-2-contoso-retailer"></a>2. példa: Contoso Retailer

A Contoso Retailer egy divatipari forgalmazócég. Az Alaptervezés alapján számítja ki a beszerzési rendeléseket elküldési időpontját, az előre jelzett értékesítések alapján. Íme néhány jellemzője:

- A Contoso Retailer igény-előrejelzést használ az értékesítések előrejelzéséhez. A beszerzési rendelések az előrejelzésnek megfelelően lesznek megtervezve.
- A kiskereskedelmi áruházak igényléseket használnak a feltöltésre.
- A fő raktárból az egyes üzletekhez vezető átfutási idő minden cikknél körülbelül két hét.

A varázslóban a Contoso Retailer vállalathoz a következő értékeket adták meg:

- **Előrejelzett igény:**

    - **Kérdés:** „Szeretne-e előrejelzési tervet használni az alaptervezésben annak érdekében, hogy a tervezett rendeléseket az előre jelzett igény kielégítésére javasolja a rendszer?”
    - **Válasz:** „Igen, az alaptervben meghatározottak szerint.”

    A Contoso az eladások előrejelzésére egy igény-előrejelzést is szerepeltetett. Ezért az alaptervezésnek javasolnia kell a tervezett rendeléseket az előrejelzés teljesítéséhez.

- **Megerősítés:**

    - **Kérdés:** „Szeretné, ha az alaptervezés automatikusan megerősítené a tervezett rendeléseket rendelési dokumentumokká, például termelési vagy beszerzési rendelésekké?”
    - **Válasz:** „Igen, az alaptervben meghatározottak szerint.” **1 napot** kell beírni.

    Mivel a Contoso Retailer közvetlenül a tervezett beszerzési rendelésekből hoz létre beszerzési rendeléseket, hasznos, ha a tervezett beszerzési rendelések megerősítése automatikusan megtörténik. Mivel a vállalat minden nap alaptervezést futtat, egy napos megerősítési időkorláttal automatikusan minden olyan megrendelést megerősít, amely szükséges a következő napra.

- **Jóváhagyott igénylések:**

    - **Kérdés:** „Szeretné-e felvenni a jóváhagyott igénylések iránti igényt a kiskereskedelmi üzletek feltöltése érdekében?”
    - **Válasz:** „Igen, az alaptervben meghatározottak szerint.” **1 napot** kell beírni.

    A Contoso a kiskereskedelmi üzletei jóváhagyott igénylései segítségével hoz létre tervezett beszerzési rendeléseket az üzletek feltöltése érdekében. Mivel az Alaptervezés minden nap fut, az előző nap igénylései szerepelni fognak a tervezésben.
