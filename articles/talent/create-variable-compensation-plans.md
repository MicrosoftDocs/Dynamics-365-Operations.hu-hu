---
title: Változó kompenzációs tervek létrehozása
description: A változó kompenzáció teszi ki egy alkalmazott az alapon felüli kifizetéseit, például a bónuszokat vagy a készlet díjakat. A témakör ismerteti az összetevőket, amelyeket be kell állítani, mielőtt használhatna változó kompenzációt, és bejegyezhetne egy alkalmazottat a változó kompenzációs tervbe.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 4e94307ae82200daa3248afdbfde081656747d47
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898781"
---
# <a name="create-variable-compensation-plans"></a>Változó kompenzációs tervek létrehozása

A változó kompenzáció teszi ki egy alkalmazott az alapon felüli kifizetéseit, például a bónuszokat vagy a készlet díjakat. A cikk ismerteti az összetevőket, amelyeket be kell állítani, mielőtt használhatna változó kompenzációt és bejegyezhetne egy alkalmazottat a változó kompenzációs tervbe.

Az alkalmazottaknak járó változó kompenzációs összegek számítása számos tényező alapján történhet, például az alkalmazott teljesítménye, kompenzációs szintje és a részleg teljesítménye alapján.

## <a name="variable-compensation-components"></a>Változó kompenzációs elemei
### <a name="create-compensation-types"></a>Kompenzációs típusok létrehozása

A**Változó kompenzációtípusok**szükséges elemek. A Változó kompenzációtípusokkal megadhatja, hogy szervezete milyen változó kompenzációt díjaz. Továbbá ezek segítségével meghatározhatja, hogy a kompenzáció készpénzben vagy nem pénzügyi formában történjen, például a készletből.

### <a name="describe-vesting-rules"></a>Átruházási szabályok leírása

Ha van rá igény a vállalatok megadhatnak **átruházási szabályokat**. Az átruházási szabályok leírják, hogy a változó jutalmakat időben hogyan kell felosztani. Például az átruházási szabály megszabhatja, hogy az alkalmazott a teljes jutalmának 25 százalékát kaphatja meg minden évben, a következő négy évben. Az átruházási szabályok csak tájékoztató jellegűek.

## <a name="variable-compensation-plans"></a>Változó kompenzációs konstrukciók
A **változó kompenzációterv** tartalmazza a szabályokat, számítási módszereket és az alapértelmezett adatokat a listázott alkalmazottak változó kompenzációjának számításához. Ha változó kompenzációtervet hoz létre, akkor meg kell adnia a változó kompenzáció típusát. A változó kompenzáció típusa meghatározza, hogy a rendszer egy pénzösszeget vagy egy egységszámot ad meg jutalomként. A számítási módszert is meg kell adni:

-   **Időponthoz kötött** – A változó jutalom számítása a fix kompenzáción alapszik, amivel az alkalmazott rendelkezett egy adott időpontban. Az időpont a folyamateseményben van meghatározva, az új kompenzációs összegek feldolgozásakor.
-   **Összetett** – Kiszámításra kerül a jutalom összege minden egyedi fix kompenzációs fizetési mértékhez ami az alkalmazottnak jár a ciklus kezdő és záró dátuma között a feldolgozási folyamat során. A díjak aztán összeadódnak a végső jutalom meghatározásához. Például a ciklus során egy alkalmazottat másik pozícióba helyeztek, aminek más a jövedelmi besorolása. Ebben az esetben a változó jutalom módosul, az egyes fizetési kategóriákban eltöltött idő szerint.

A változó jutalom összege alapulhat az alkalmazott rendszeres fizetésének bizonyos százalékán vagy adott egységeken.

-   Válassza ki az **Alap százaléka** lehetőséget az alapértelmezett százalék magadásához és határozza meg, hogy a fix fizetés vagy az alkalmazottak kompenzációs szintjeinek kontrollpontja legyen az alap. A kompenzációs szint alapja az alkalmazott munkája. A kompenzációs szerkezetből az egyik referenciapont beállítható kontrollpontnak a fix kompenzációs terven. A rendszer a kompenzációs szintet használja az alkalmazottak munkaköréből és egyezteti azt az alkalmazott fix kompenzációs tervben listázott kontrollpontokkal, így keresve a kontrollpont-mennyiséget az alkalmazott kompenzációs szintjéhez. Ezután a kontrollpont-mennyiséget használja a program - az alkalmazott fix fizetése helyett - a jutalom alapjának.
-   Válassza az**Egységek száma** lehetőséget egy alapértelmezett egységszám, az egyes egységek értékének és az egységérték pénzemének megadásához, ha a kompenzációs terv nem készpénz alapú (például 200 készletegység, amelyek 40 USD értékűek) vagy adja meg csak az egységek számát a kompenzációs tervben ha a kompenzációs terv készpénz alapú. Készpénzes jutalomnál az alkalmazott adott számú egységet kap a rögzített kompenzációs tervben rögzített pénznemben (például 500 egységet 1 USD értékben). Az egy-egy kapcsolat ellenőrzése használható annak ellenőrzésére, hogy az egységek száma között és az egységérték között egy-egy közötti hozzárendelés van-e. Amikor létrehoz egy változó kompenzációs tervet egy készpénzalapú tervhez az egységek számának használatával, akkor ez a lehetőség automatikusan **Igen** értéket kap, és az egységérték **1,0000** lesz.

A **Felvételi szabály** beállításai segítségével megadhatja, hogy minden alkalmazott ugyanazt a fizetésemelést kapja-e, függetlenül felvételük dátumától (**Felvételi szabály** = **Nincs**), vagy az alkalmazottak a jutalom bizonyos százalékát kapják, alkalmazásuk időtartamának függvényében (**Felvételi szabály** = **Százalék**). 

Az **Emelés** lehetővé teszi egy alkalmazott jutalmának megadását az alkalmazotti részleg által mért teljesítmény alapján. A teljesítménymutatók megadhatók az egyes részlegek számára, a **Részlegek** oldalon, a **Kapcsolódó űrlapok** &gt; **Kompenzáció** &gt; **Teljesítmény** pont alatt. Az adott részlegen dolgozók jutalma függ a **A cél elért százaléka** mező értékétől, amelyik a részleg teljesítményét tükrözi:

-   Ha az osztály teljesítménye 100 százalék, az alkalmazottak jutalma az adott részlegben függ a**Kifizetés 100%-nál** mezőben megadott értéktől.
-   Ha a részleg teljesítménye nagyobb, mint 100 százalék, akkor a rendszer a **1% a cél felett** mezőben lévő értéket adja hozzá a **Kifizetés 100% esetén** mezőhöz, amíg a **Legmagasabb megengedett kifizetés** mező értékét eléri.
-   Ha a részleg teljesítménye kisebb, mint 100 százalék, akkor a rendszer az **1% a cél felett** mezőben lévő értéket kivonja a **Kifizetés 100% esetén** mezőből, amíg a **Legalacsonyabb megengedett kifizetés** mező értékét eléri.

Beállíthat**toleranciaszinteket** a küszöbérték százalékoknál, így egy figyelmeztető üzenet jelenik meg, ha az emelés miatt a százalék átlépi a küszöbértéket. 

Alapértelmezetten a rendszer megkeresi az alkalmazott pozíciójához rendelt részleget. Ugyanakkor néhány alkalmazott számára a jutalom több részleg teljesítményétől is függhet. Ebben az esetben a különböző részlegek és az egyes részlegek jutalmainak százaléka, amelyet az egyes részlegek teljesítményhez rendeltek, állíthatók be az alkalmazott változó kompenzációs bejegyzésében. További információért tekintse meg a „Változó kompenzációs bejegyzés” szakaszt lentebb. 

Emelés csak a **Teljesítménybérezés** kiválasztásakor használatos, amikor a kompenzációs feldolgozás futtatásakor. 

A **Felülbírálási szintek** lap lehetővé teszi az alapértelmezett jutalom százalékának vagy az egységek számának felülírását, amit az alkalmazott kompenzációs szintje alapján számítottak. Ha a **Felülbírálások engedélyezése szintekhez** értéke **Igen** azoknak az alkalmazottaknak, akik részesei a változó kompenzációs tervnek, akkor a rendszer veszi az alkalmazott beosztásának szintjét, és utána megkeresi a felülírási szintek táblázatban, hogy meghatározza a százalékot vagy az egységek számát ahhoz a szinthez. Ha a szint nem található a felülírási szintek táblázatban, akkor az **Általános** lap alapértelmezett százaléka vagy egységszáma kerül felhasználásra. A százalék és az egységszám szintén felülírható az alkalmazottak listáján a változó kompenzációs tervben.

## <a name="variable-compensation-enrollment"></a>Változó kompenzációs tagság
### <a name="determine-who-is-eligible-for-the-plan"></a>A konstrukcióra jogosultak meghatározása

Ha készen áll az alkalmazottak beléptetésére a változó kompenzációs tervbe, akkor elsőként meg kell határozni ki jogosult a tervben meghatározott kompenzációra A tervet nem lehet hozzárendelni egyetlen alkalmazotthoz sem, amíg nincs meghatározva a jogosultság. A jogosultság beállításához nyissa meg a **Jogosultsági szabályok** oldalt egy új jogosultsági szabály létrehozásához a tervben, és aztán adja meg a szükséges kritériumokat, amelyek alapján az alkalmazott jogosult a kompenzációs tervre. Korlátozhatja a jogosultságot részleg, szakszervezet, kompenzációs régió (hely), munka, beosztás funkciója, munka típusa és/vagy kompenzációs szint szerint. Az alkalmazottak csak akkor léptethetők be a kompenzációs tervbe, ha megfelelnek az **összes** jogosultsági szabályban meghatározott követelménynek. 

**Megjegyzés:** A jogosultsági szabályok meghatározzák a fix kompenzációs tervhez és a változó kompenzációs tervhez való jogosultságot. A jogosultsági szabályok az alábbi mezőket használják a munka, beosztás és alkalmazotti rekordokból, hogy meghatározható legyen egy alkalmazott jogosult.e a kompenzációs tervre:

- A **Munka** oldalon:
  -   A **Munka** mező
  -   A **Funkció** és **Feladattípus** mezőket a **Munkaköri besorolás** lapon
  -   A **Szint** mezőt a **Kompenzáció** lapon
- A **Beosztások** oldalon: A **Részleg** és **Kompenzációs régió** mezőket
- Az <strong>Alkalmazottak</strong> oldalon: Az alkalmazotthoz tartozó szakszervezetek adatait a <strong>Személyes adatok</strong> &gt; <strong>Szakszervezetek</strong> alatt a *<strong><em>Dolgozó</em></strong>* lapot

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Beléptetés engedélyezése változó kompenzációs tervbe

A **Változó kompenzációs tervek** oldalon, állítsa be a **Beléptetés engedélyezései** lehetőséget **Igen** értékre, hogy a jogosult alkalmazottakat beléptesse a tervbe.

### <a name="enroll-the-employee"></a>Alkalmazott beléptetése

Már beléptethet alkalmazottakat a változó kompenzációs tervbe. Alkalmazott beléptetéséhez ugorjon az **Alkalmazottak** oldalra és válassza ki az alkalmazottat. Majd a Műveleti ablakon kattintson a **Kompenzáció** &gt; **Változó konstrukciós felvétel** lehetőségre. 

**Megjegyzés:** A **Belépéptetés** mezőt **Igen** értékre kell állítani a változó kompenzációs konstrukciónál. A **Terv** mezőben csak azok a tervek láthatók amikre jogosult az alkalmazott a terv jogosultsági szabályai alapján. Ha egy tervhez nincs beállítva jogosultsági szabály, akkor egyetlen alkalmazott sem jogosult. 

Győződjön meg róla, hogy az **Érvényességi dátum** mező megfelelően van beállítva. Ha a változó kompenzációs terv **Összetett** számítási módszert használ, a beléptetés érvényességi dátuma figyelembe vehető az alkalmazott jutalmának számításakor. 

Használhatja a **Felülbírálások** lapot az alkalmazotthoz rendelt adott értékek felülírásához. Például ha a **Felvételi szabály** **Százalék** értékre van beállítva a tervben, és egy eltérő felvételi dátumot kell használni az alkalmazott felvételi százalékának számítása során, akkor módosíthatja a **Felvételi szabály** mezőt. Továbbá felülírhatja a **Jutalomszázalék** értéket vagy az **Egységek száma** értéket egy adott alkalmazott esetében, a terv beállításaitól függően. Ezek az értékek ugyanakkor alapértékkel rendelkeznek a felvételi szabálynál, teljesítményfaktoroknál és a terv egyéb beállításainál. 

A **Szervezeti felülbírálások** az alkalmazott jutalmának alapját képezik, egy vagy több részleg teljesítménye szerint. A részlegekhez hozzárendelt százalékok teljes összegének 100-nak kell lennie. Az alkalmazott egyéni teljesítménye szintén beleszámít. Ezek a beállítások csak akkor használatosak, ha a **Teljesítménybérezés** van kiválasztva a kompenzációs folyamat futtatása közben.

<a name="additional-resources"></a>További erőforrások
--------

[Kompenzációs konstrukciók](compensation-plans.md)



