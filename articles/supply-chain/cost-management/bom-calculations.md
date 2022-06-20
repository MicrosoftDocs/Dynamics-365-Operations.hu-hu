---
title: Anyagjegyzék-számítások
description: A költségösszesítés és az eladási ár számítását anyagjegyzék-számításoknak nevezik, és indításuk a Számítások lapról történik. Ez a cikk az anyagjegyzék-számításokkal kapcsolatban tartalmaz tájékoztatást.
author: JennySong-SH
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion, InventItemPrice, ProdSetupCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 273763
ms.assetid: c6fa3348-eafa-4847-9132-e65c5f55cbf4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: c19c15f807a809a68043a75ca935fa92217fcd5f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902802"
---
# <a name="bom-calculations"></a>Darabjegyzék-számítások

[!include [banner](../includes/banner.md)]

A költségösszesítés és az eladási ár számítását anyagjegyzék-számításoknak nevezik, és indításuk a Számítások lapról történik. Ez a cikk az anyagjegyzék-számításokkal kapcsolatban tartalmaz tájékoztatást.

A költségösszesítés és az eladási ár számítását anyagjegyzék-számításoknak nevezik, és indításuk a **Számítások** lapról történik. A **Számítások** lapon a következő műveleteket végezheti el:

-   Kiszámíthatja egy legyártott cikk költségét, valamint egy költségszámítási verzión belül létrehozhatja a társított cikk-költségrekordot.
-   A használatával ki lehet számítani a legyártott cikk eladási árát, valamint létre lehet hozni a költségszámítási verzión belül egy társított eladásiár-rekordot a cikkhez.

A **Számítások** lap használata némiképpen más attól függően, hogyan kezdeményezi az anyagjegyzék-számításokat. A **Számítások** lap használata attól is függ, hogy az anyagjegyzék-számítások elszámolóárakhoz vagy tervezett költségekhez tartalmaznak-e költségszámítási verziót, valamint az anyagjegyzék-számításokban használt költségszámítási verzión belül meghatározott számos szabály is befolyásolja. **Megjegyzés:** Az értékesítési rendelésekkel, az értékesítési ajánlatokkal, illetve a szervizrendelések sorcikkeivel összefüggésben a **Számítások** lap más-más változatai használhatók. Ezeket a számításokat rendelésspecifikus anyagjegyzék-számításoknak nevezik. Először is, a rendelésspecifikus anyagjegyzék-számítással nem jön létre költségszámítási verzión belül cikk-költségrekord. Ehelyett egy számítási rekordot hoz létre, amely az **Anyagjegyzék-számítás részletei** lapon jelenik meg. A számítási rekord tartalmazza a számított költséget és a számított eladási árat. A **Számítások** lapot meg lehet nyitni egyetlen legyártott cikkhez vagy egy költségszámítási verzióhoz is:

-   Az egy legyártott cikkre jutó költség kiszámításához indítsa az anyagjegyzék-számításokat a **Cikk ára** lapról. A **Számítások** lap örökli a cikk azonosítóját. A költségszámítási verziót, az anyagjegyzék-verziót, az útvonalverziót, a számítási mennyiséget, a számítási dátumot és helyet meg kell adni.
    -   Alapértelmezés szerint az anyagjegyzék-verzió és az útvonalverzió értéke a cikk, a hely, a dátum és a számítási mennyiség aktív verzióiként vannak beállítva. Azonban az alapértelmezett értékek jóváhagyott verziókkal felülbírálható.
    -   Alapértelmezés szerint a számítási mennyiség a cikk szokásos rendelési mennyiségéhez van beállítva. Az alapértelmezett értéket azonban felülbírálhatja.
    -   A számítás dátumát vagy a telephelyet a költségszámítási verzió meghatározhatja, vagy pedig felhasználó által megadott értékeket lehet engedélyezni, ha a költségszámítási verzió nem határozza meg a dátumot vagy a telephelyet. A jövőbeli dátum meghatározza a függő költségek rekordjainak használatát. Az anyagjegyzék-számítások függőköltség-rekordot fognak használni a számítás napját jelentő vagy azt megelőző legközelebbi kezdődátummal.
-   Az összes legyártott cikk vagy a kijelölt cikkek költségeinek kiszámításához, illetve a cikkek használati hely szerint történő frissítéséhez kezdeményezze az anyagjegyzék-számításokat a **Költségszámítási verzió beállítása** lapról vagy a **Költségszámítási verzió karbantartása** lapról elindítva. A **Számítások** lap örökli a költségszámítási verziót.
    -   A számítások feltételezik a legyártott cikkre (valamint a kapcsolódó telephelyre, dátumra és mennyiségre) vonatkozó aktív anyagjegyzék- és útvonalverzió használatát, kivéve abban az esetben, ha egy legyártott összetevőhöz adott részanyagjegyzék vagy részútvonal tartozik.
    -   A számítások feltételezik a legyártott cikkre vonatkozóan a szokásos rendelési mennyiség alkalmazását. A számítások feltételezik a legyártott cikkre vonatkozóan a szokásos rendelési mennyiség alkalmazását, amely meghatározza a vonatkozó anyagjegyzék-verziókat és útvonalverziókat (mennyiségfüggő anyagjegyzékek és útvonalak használata esetén), valamint az állandó költségek amortizációját. Ez az előfeltételezés azonban nem érvényes olyan helyzetben, amikor egy legyártott összetevőhöz **Termelés** vagy **Szállító** típusú anyagjegyzéksor tartozik, vagy ha az anyagjegyzék-számításokhoz rendelésre gyártott alábontási módot alkalmaz, mivel a mennyiségek a megadott számítási mennyiséget fogják tükrözni.
    -   A számítás dátumát vagy a telephelyet a költségszámítási verzió meghatározhatja, vagy pedig felhasználó által megadott értékeket lehet engedélyezni, ha a költségszámítási verzió nem határozza meg a dátumot vagy a telephelyet.

Az anyagjegyzék-számítások egyéb variációi tükrözik a költségszámítási verzió költségtípusait és korlátozásait:

-   Az elszámolóáras anyagjegyzék-számításokat költségszámításiverzió-szabályokkal korlátozni kell, mivel a korlátozások biztosítják a szabványos költségszámítási elvek alkalmazását. Az elszámolóáras költségszámításhoz érvényesíteni kell a beszerzett cikkekhez tartozó elszámolóárak használatára vonatkozó korlátozásokat, egyszintű alábontást kell alkalmazni, valamint az egységenkénti önköltségben szerepeltetni kell a vegyes költségeket.
-   A tervezett költségekkel végzett anyagjegyzék-számítások nem követik az elszámolóáras költségszámítás elveit. Az ilyen anyagjegyzék-számítások alkalmazhatnak eltérő alábontási módokat, a beszerzett cikkekre vonatkozóan alternatív költségadatforrásokat, valamint a költségszámítási verzión belül a korlátozások választható érvényesítését.

### <a name="bom-calculations-that-use-standard-costs"></a>Elszámolóáras anyagjegyzék-számítások

A költségszámítási verzión belüli szabályok (elszámolóár esetén) meghatározhatják öt anyagjegyzék-számítási szabály érvényesítését. A költségszámítási verzió **Rögzítési korlátozás** lehetősége az egyik ilyen szabályt írja elő, amelynek értelmében az egységárban szerepelnie kell a vegyes költségeknek. A beszerzett cikkek vegyes költségeit manuálisan lehet bevinni, míg a gyártott cikkek vegyes költségei tükrözik az állandó költségek számított amortizációját. A **Költségszámítási verzió számítást korlátozó** lehetősége a másik négy anyagjegyzék-számítási szabályt írja elő:

-   A beszerzett cikkek költséghozzájárulásai forrásának elszámolóárakra kell alapulnia. Az anyagjegyzék-számításoknak tehát a cikk-költség rekordokat kell alkalmazniuk a megadott költségszámítási verzión belül, illetve az elszámolóárakat tartalmazó tartalékon belül.
-   Az alábontási módnak egyszintűnek kell lennie, ez biztosítja az elszámolóárak pontos és egységes számítását.
-   A nyereségbeállításnak meghatározottnak kell lennie, hogy a cikk eladási árának számításakor konzisztensek legyenek az eredmények. A költségszámítási verziónak lehetővé kell tennie, hogy az eladási árak tartalma használja a nyereségbeállítást, és hogy létrehozhassák a cikk eladásiár-rekordját.
-   Meg kell lennie határozva a tartalékelvnek, ez lehet **Üres**, **Aktív** (aktív költségrekordok esetében), vagy **Költségszámítási verzió** (megadott költségszámítási verzió esetében).

### <a name="bom-calculations-that-use-planned-costs"></a>Tervezett költségekkel végzett anyagjegyzék-számítások

A költségszámítási verzión belüli szabályok (tervezett költségek esetén) választható módon meghatározhatják öt anyagjegyzék-számítási szabály érvényesítését. A szabályok pusztán alapértelmezett értékeket is megadhatnak. A költségszámítási verzió **Rögzítési korlátozás** lehetősége határozza meg, hogy a vegyes költségekre vonatkozó anyagjegyzék-számítási szabályt előírja-e, vagy pedig alapértelmezett értékként viselkedik. A vegyes költségek választható módon szerepeltethetők az egységárban. A **Költségszámítás korlátozása** lehetőség határozza meg, hogy a költségszámítási verzió előírja-e a többi négy anyagjegyzék-számítási szabályt, vagy pedig alapértelmezett értékként viselkednek.

-   A beszerzett cikkre vonatkozó költséghozzájárulások lehetnek a költségszámítási verzióban szereplő cikk-költségrekordok. A forrást az az anyagjegyzék-számítási csoport is meghatározhatja, amelyhez a cikk tartozik. Például az anyagjegyzék-számítási csoport a költség-hozzájárulási adatok forrásaként meghatározhat beszerzési árra vonatkozó kereskedelmi megállapodásokat.
-   Az alábontás módja lehet egyszintű, többszintű, rendelésre készített, vagy az anyagjegyzéksor cikkén alapuló. Az anyagjegyzéksor típusához tartozó alábontási mód tükrözi a termelési rendelés becsléséhez tartozó költségszámítási logikát.
-   A profitbeállítás lehet előírt vagy alapértelmezett érték. A költségszámítási verziónak lehetővé kell tennie, hogy az eladási árak tartalma használja a nyereségbeállítást, és hogy létrehozhassák a cikk eladásiár-rekordját.
-   A tartalékelv lehet előírt vagy alapértelmezett érték. A tartalékelv beállítása lehet **Üres**, **Aktív** (aktív költségrekordok esetében), vagy **Költségszámítási verzió** (megadott költségszámítási verzió esetében).

Az anyagjegyzék-számítások figyelmeztető és egyéb típusú üzeneteket hoznak létre. Az üzenetek típusát többféle anyagjegyzék-számítási szabály határozza meg. A figyelmeztetési feltételek meghatározása a cikkhez rendelt anyagjegyzék-számítási csoportban van. Ezek a figyelmeztetési feltételek az anyagjegyzék-számítás kezdeményezésekor azonban felülbírálhatók. Tartalékelv használata esetén gyakran praktikus a tartalékhasználatra vonatkozó információkat üzenetként megjeleníteni. Hiányzó költségrekordok esetében a cikkek számított költségek frissítésekor is hasznos, ha az információs üzenettel azonosítani lehet azokat a cikkeket, amelyeknél nem történt meg a frissítés.

## <a name="bom-calculations-that-use-the-fallback-principle"></a>Tartalékelvet alkalmazó anyagjegyzék-számítások
A következő példák a tartalékelv használatával kapcsolatban kétféle helyzetet mutatnak be:

-   **Az elszámolóárak frissítésének kétverziós megközelítése** – egy költségszámítási verzió tartalmazhatja az elszámolóárak növekményes változásait, például az új cikkeket vagy költségváltozásokat képviselő függőköltség-rekordokat. Ebben a helyzetben a tartalékelv azonosíthatja az egyéb költségszámítási verziókban szereplő aktív költségrekordok használatát.
-   **A költségváltozásoknak a tervezett költségekre gyakorolt hatásának szimulálása** – A tervezett költségekhez tartozó költségszámítási verzió tartalmazhat szimulációs céllal növekményes változásokat. Ez a költségszámítási verzió cikkek, költségkategóriák és közvetett költségek számítási képleteinek szimulált költségváltozásainak megfelelő függőköltség-rekordokat tartalmaz majd. Ebben a helyzetben a tartalékelv azonosíthatja az egyéb költségszámítási verziókban szereplő aktív költségrekordok használatát.

## <a name="bom-calculation-of-a-suggested-sales-price"></a>Javasolt eladási ár anyagjegyzék-számítása
A költség + árrés módszer használata esetén a számított eladási ár egy cikkre tükrözheti azokat a nyereségbeállítási százalékokat, amelyek az anyagjegyzék-számításhoz vannak megadva, valamint tükrözi az összetevő cikkek, az útvonalműveletek és az alkalmazandó gyártási többletköltségek összegét. A haszonkulcs számítása a költségcsoportokhoz beállított nyereségbeállítások, valamint a cikkekhez beállított költségcsoportok, az útvonalműveletek költségkategóriái és a gyártási többletköltségek közvetett költségszámítási képletei alapján történik. A nyereségbeállítási százalékok halmazainak címkéi: **Szabványos**, **1. nyereség**, **2. nyereség** és **3. nyereség**. Az 1. nyereség halmazban például be lehetne állítani, hogy a beszerzett anyagokhoz rendelt költségcsoportban a nyereségbeállítás százalékos kulcsa 50 százalék legyen, míg az útvonalműveletek költségkategóriáihoz rendelt költségcsoportok nyereségbeállítási százaléka 80 százalék lehetne. Az anyagjegyzék-számítás kontextusa meghatározza, hogy a program hogyan kezeli a számított eladási árakat:

-   **Anyagjegyzék-számítás egy cikkre és megadott költésgszámítási verzióra** − Az anyagjegyzék-számítás egy függő eladásiár-rekordot generál a költségszámítási verzión belül. Ez az eladásiár-rekord kiindulópontként szolgál a számítási részletek megtekintéséhez (például a **Cikk-költség kiszámítása** lapon). Az eladásiár-rekord elsősorban referenciaadatként szolgál, az értékesítési rendelések eladási árának számításának azonban nem ez az alapja.
-   **Rendelés-specifikus anyagjegyzék-számítás** − Az **Anyagjegyzék-számítás** lap egy változata az értékesítési rendelés, értékesítési ajánlat vagy szolgáltatási rendelés sorában szereplő cikkel összefüggésben használható. A rendelés-specifikus anyagjegyzék-számítás nem állít elő rekordot a költségszámítási verzión belül. Ehelyett egy számítási rekordot hoz létre, amely az **Anyagjegyzék-számítás eredményei** lapon jelenik meg. Ez a számítási rekord kiindulópontként szolgál a számítási részletek megtekintéséhez (például a **Cikk-költség kiszámítása** lapon). A kiválasztott számítási rekord adatai átvihetők az eredeti sorban szereplő cikkbe. Például a számított eladási árat át lehet vinni egy értékesítési rendelési sorban szereplő cikkbe.

## <a name="order-specific-bom-calculations"></a>Rendelésspecifiks anyagjegyzék-számítások
A rendelésspecifikus anyagjegyzék-számítás a legyártott cikkre vonatkozó anyagjegyzék-számítás egyik variációja. A rendelésspecifikus anyagjegyzék-számítást értékesítési rendelés, értékesítési ajánlat vagy szervizrendelések sorainak kontextusában kell végezni. A rendelés-specifikus anyagjegyzék-számítás előállít egy számítási rekordot, amely megjelenik az **Anyagjegyzék-számítás eredményei** lapon. A számítási rekord tartalmazza a számított súlyt, az önköltségi rekordokon alapuló számított költséget, valamint a számított értékesítési árat. Egy-egy cikkhez elvégzett minden rendelésspecifikus anyagjegyzék számítás létrehoz egy számítási rekordot az **Anyagjegyzék-számítások eredményei** lapon, amelyet egyedi módon azonosít egy számítási szám. A számítási rekord eredményeit át lehet vinni a kiindulási pontot jelentő sorra is. A rendelésspecifikus anyagjegyzék-számítás két módon eltér a legyártott cikkre vonatkozó anyagjegyzék-számítástól.

-   Először is, a rendelésspecifikus anyagjegyzék-számítással nem jön létre költségszámítási verzión belül cikk-költségrekord. Ezért az anyagjegyzék-számítási szabályok nem vonatkoznak a cikk-költség rekordok létrehozására vagy a költségrekordok felülírására.
-   A rendelésspecifikus anyagjegyzék-számítás mindig az aktív költségrekordokat használja fel az összetevőkre, a költségkategóriákra és a közvetett költségek számítási képleteire vonatkozóan.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]