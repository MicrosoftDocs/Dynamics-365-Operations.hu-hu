---
title: "Változó kompenzációs tervek létrehozása"
description: "A változó kompenzáció teszi ki egy alkalmazott az alapon felüli kifizetéseit, például a bónuszokat vagy a készlet díjakat. Ez a témakör ismerteti az összetevőket, amelyek be kell állítani mielőtt változó kompenzációs használja, és az alkalmazott változó kompenzációs tervben igényelni."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9397e84f03ee5b340fa2aa0a64e582fc0078526e
ms.openlocfilehash: be156afa73de731e54985485b617bcbae883db3a
ms.lasthandoff: 03/31/2017


---

# <a name="create-variable-compensation-plans"></a>Változó kompenzációs tervek létrehozása

A változó kompenzáció teszi ki egy alkalmazott az alapon felüli kifizetéseit, például a bónuszokat vagy a készlet díjakat. A cikk ismerteti az összetevőket, amelyeket be kell állítani, mielőtt használhatna változó kompenzációt és bejegyezhetne egy alkalmazottat a változó kompenzációs tervbe.

Az alkalmazottaknak járó változó kompenzációs összegek számítása számos tényező alapján történhet, például az alkalmazott teljesítménye, kompenzációs szintje és a részleg teljesítménye alapján.

## <a name="variable-compensation-components"></a>Változó kompenzációs elemei
### <a name="create-compensation-types"></a>Kompenzációs típusok létrehozása

A**Változó kompenzációtípusok **szükséges elemek. A Változó kompenzációtípusokkal megadhatja, hogy szervezete milyen változó kompenzációt díjaz. Továbbá ezek segítségével meghatározhatja, hogy a kompenzáció készpénzben vagy nem pénzügyi formában történjen, például a készletből.

### <a name="describe-vesting-rules"></a>Átruházási szabályok leírása

Ha van rá igény a vállalatok megadhatnak **átruházási szabályokat**. Átruházási szabályok írják le, hogyan kell szétosztani a változó jutalom idő. Átruházási szabály például előfordulhat, hogy adja meg, hogy az alkalmazott kap saját teljes odaítélés 25 %-át minden évben a következő négy évig. Átruházási szabályok csak tájékoztató jellegűek.

## <a name="variable-compensation-plans"></a>Változó kompenzációs konstrukciók
A **változó kompenzációterv** tartalmazza a szabályokat, számítási módszereket és az alapértelmezett adatokat a listázott alkalmazottak változó kompenzációjának számításához. A változó kompenzációs konstrukció létrehozásakor be kell állítani a változó kompenzációs típus. A változó kompenzációs típus határozza meg, hogy a rendszer kiszámítja a pénzösszegre vagy egységek száma, az ítélet. A számítási módszert is meg kell adni:

-   **Pont időben** – a változó jutalom kiszámítása, amely az alkalmazott egy adott napon a fix kompenzációs alapul. Új kompenzációs összegek feldolgozásakor a feldolgozási esemény időpont van megadva.
-   **Összetett** – Kiszámításra kerül a jutalom összege minden egyedi fix kompenzációs fizetési mértékhez ami az alkalmazottnak jár a ciklus kezdő és záró dátuma között a feldolgozási folyamat során. A díjak kerülnek össze, hogy a végső jutalom megállapítására. Például a ciklus alatt alkalmazott át egy másik helyre, amely egy másik fizetési díjalap. Ebben az esetben a változó jutalom módosul, az egyes fizetési kategóriákban eltöltött idő szerint.

A változó jutalom összege alapulhat az alkalmazott rendszeres fizetésének bizonyos százalékán vagy adott egységeken.

-   Válassza ki az **Alap százaléka** lehetőséget az alapértelmezett százalék magadásához és határozza meg, hogy a fix fizetés vagy az alkalmazottak kompenzációs szintjeinek kontrollpontja legyen az alap. A támogatás szintje az alkalmazott feladat. A viszonyítási pont a kompenzációs struktúrából egyike állítható ellenőrzési pont a fix kompenzációs konstrukció. A rendszer a kompenzációs szint az alkalmazott feldolgozás használja, és a pont, amely az alkalmazott fix kompenzációs konstrukció az alkalmazott kompenzációs szint található ellenőrzési pont összeg szerepel a kereszthivatkozás. Az ellenőrzési pont összeg majd használandó helyett az alkalmazott fix fizetési díjalap alapjául az ítélet.
-   Válassza az** Egységek száma** lehetőséget egy alapértelmezett egységszám, az egyes egységek értékének és az egységérték pénzemének megadásához, ha a kompenzációs terv nem készpénz alapú (például 200 készletegység, amelyek 40 USD értékűek) vagy adja meg csak az egységek számát a kompenzációs tervben ha a kompenzációs terv készpénz alapú. A pénzbeli jutalom, az alkalmazott kap a saját fix kompenzációs konstrukció (például 500 egység 1 USD) használt pénznem egységeinek a megadott számú. -Az-egyhez kapcsolat ellenőrzése azt jelzi, hogy egységeinek számát és az egység értéke közötti közvetlen egyhez használható. Az egységek száma a készpénz alapú terv változó kompenzációs terv létrehozásakor ez a beállítás automatikusan zárolva van a **Igen**, és az egység értéke **1,0000**.

A **felvételi szabály** beállítás segítségével megadhatja, hogy minden alkalmazott jár azonos növekedés, függetlenül azok felvételének dátuma (**felvételi szabály** = **nincs**), vagy hogy alkalmazottak az alkalmazásuk során a ciklus hossza alapuló ítélet százalékában kell kapnia (**felvételi szabály** = **%**). 

**Emelés** lehetővé teszi az alkalmazott jutalom, az alkalmazott szervezeti teljesítmény alapján módosítsa. Teljesítménymutatók minden egyes részleg állítható be a **szervezeti egységek** oldalon, a **kapcsolódó képernyők**&gt;**kompenzációs**&gt;**teljesítmény**. Az ítélet alkalmazottak szervezeti egységhez a százalékokat értéke függ a **a cél elért százalékos** mező, amely azt jelzi, a szervezeti teljesítmény:

-   Ha az osztály teljesítménye 100 százalék, az alkalmazottak jutalma az adott részlegben függ a** Kifizetés 100%-nál** mezőben megadott értéktől.
-   Ha a részleg teljesítménye nagyobb, mint 100 százalék, akkor a rendszer a **1% a cél felett** mezőben lévő értéket adja hozzá a **Kifizetés 100% esetén** mezőhöz, amíg a **Legmagasabb megengedett kifizetés** mező értékét eléri.
-   Ha a részleg teljesítménye kisebb, mint 100 százalék, akkor a rendszer az **1% a cél felett** mezőben lévő értéket kivonja a **Kifizetés 100% esetén** mezőből, amíg a **Legalacsonyabb megengedett kifizetés** mező értékét eléri.

Beállíthat** toleranciaszinteket** a küszöbérték százalékoknál, így egy figyelmeztető üzenet jelenik meg, ha az emelés miatt a százalék átlépi a küszöbértéket. 

Alapértelmezés szerint a rendszer keresi a osztály, az alkalmazott beosztása van beállítva. Az egyes alkalmazottak az ítélet azonban több szervezeti egységek teljesítményének a is függhet. Ebben az esetben a különböző szervezeti egységei és az ítélet, amely az egyes szervezeti egységek teljesítményének rendelt százalékos állítható be az alkalmazott változó kompenzációs tagság. További információt a következő "változó kompenzációs tagság" szakaszban talál. 

Emelés csak a **Teljesítménybérezés** kiválasztásakor használatos, amikor a kompenzációs feldolgozás futtatásakor. 

A **felülírások szintek** lap segítségével felül lehet bírálni az ítélet alapértelmezett százalék vagy egységszám, az alkalmazott kompenzációs szintet alapul. Ha **engedélyezése felülírja szintek** értéke **Igen** az alkalmazottak, akik feliratkoztak a változó kompenzációs konstrukció, a rendszer a feladat az alkalmazott szintjét veszi, és ezután megkeresi azt a szintek felülbírálja a tábla határozza meg a százalékot vagy szint egységek száma. Ha a szint nem található a szint felülbírálja a tábla, az alapértelmezett százalékos vagy egységeinek számát a **általános** lapon. A százalékos és egységek számát is felülírható az alkalmazott belépés a változó kompenzációs terv.

## <a name="variable-compensation-enrollment"></a>Változó kompenzációs tagság
### <a name="determine-who-is-eligible-for-the-plan"></a>A konstrukcióra jogosultak meghatározása

Ha készen áll az alkalmazottak beléptetésére a változó kompenzációs tervbe, akkor elsőként meg kell határozni ki jogosult a tervben meghatározott kompenzációra A tervet nem lehet hozzárendelni egyetlen alkalmazotthoz sem, amíg nincs meghatározva a jogosultság. A jogosultság beállításához nyissa meg a **Jogosultsági szabályok** oldalt egy új jogosultsági szabály létrehozásához a tervben, és aztán adja meg a szükséges kritériumokat, amelyek alapján az alkalmazott jogosult a kompenzációs tervre. Korlátozhatja a jogosultságot részleg, szakszervezet, kompenzációs régió (hely), munka, beosztás funkciója, munka típusa és/vagy kompenzációs szint szerint. Az alkalmazottak csak akkor léptethetők be a kompenzációs tervbe, ha megfelelnek az **összes** jogosultsági szabályban meghatározott követelménynek. 

**Megjegyzés:** A jogosultsági szabályok meghatározzák a fix kompenzációs tervhez és a változó kompenzációs tervhez való jogosultságot. A jogosultsági szabályok az alábbi mezőket használják a munka, beosztás és alkalmazotti rekordokból, hogy meghatározható legyen egy alkalmazott jogosult.e a kompenzációs tervre:

-   A **Munka** oldalon:
    -   A **Munka** mező
    -   A **Funkció** és **Feladattípus** mezőket a **Munkaköri besorolás** lapon
    -   A **Szint** mezőt a **Kompenzáció** lapon
-   A **Beosztások** oldalon: A **Részleg** és **Kompenzációs régió** mezőket
-   A a **alkalmazottak** oldal: szakszervezetek mellett az alkalmazott kapcsolódó információt **személyes adatok**&gt;**szakszervezetek** a a *** dolgozó *** lap

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Beléptetés engedélyezése változó kompenzációs tervbe

A **Változó kompenzációs tervek** oldalon, állítsa be a **Beléptetés engedélyezései** lehetőséget **Igen** értékre, hogy a jogosult alkalmazottakat beléptesse a tervbe.

### <a name="enroll-the-employee"></a>Alkalmazott beléptetése

Már beléptethet alkalmazottakat a változó kompenzációs tervbe. Alkalmazott beléptetéséhez ugorjon az **Alkalmazottak** oldalra és válassza ki az alkalmazottat. Ezután kattintson a műveletek ablaktábla **kompenzáció**&gt;**változó konstrukciós felvétel**. 

**Megjegyzés:** A **Belépéptetés** mezőt **Igen** értékre kell állítani a változó kompenzációs konstrukciónál. A **tervezett** a mezőben látható az alkalmazott rendszer hatálya alá tartozó, az e tervekre vonatkozó beállított jogosultsági szabályok alapján terveket. Az alkalmazhatósági szabály nincs beállítva a terv, ha nem a munkavállalók jogosultak lesznek a terv. 

Ellenőrizze, hogy a **napjával** mező helyesen van beállítva. Ha a változó kompenzációs konstrukció használ a **összetett** számítási módszer, a tagság hatálybalépésének napjával lehet tekinteni az alkalmazott jutalom kiszámítása során. 

Használhatja a **felülírja a** lapon megadott értékek felülírják az alkalmazott. Például ha **felvételi szabály** értéke **százalék** a terv és a különböző felvételi dátum az alkalmazott felvételi százalék kiszámítása során kell használni, beállíthatja a belépés dátuma a **felvételi szabály dátuma** mező. Is felül vagy a **jutalomszázalék** érték vagy a **egységek száma** értékét egy adott alkalmazott, a terv beállításaitól függően. Ezeket az értékeket fogja továbbra is figyelembe venni a felvételi szabály, teljesítmény tényezők és egyéb beállításokat a terv. 

**Szervezeti felülbírálások** egy vagy több szervezeti egységek teljesítményének a az alkalmazott közbeszerzési alapjául használják. A részleg lefoglalt százalékos kell teljes 100 százalék. Az alkalmazott egyéni teljesítményét is figyelembe veszi. Ezek a beállítások csak akkor, ha használt **Teljesítménybérezés** van jelölve, a kompenzációs folyamat futása során.

<a name="see-also"></a>Lásd még
--------

[Kompenzációs konstrukciók](compensation-plans.md)


