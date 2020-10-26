---
title: Biztonsági készlet teljesítése cikkek számára
description: Ez a témakör bemutatja a biztonsági készlet teljesítését és a biztonsági készletmennyiség beállítását cikkek számára.
author: roxanadiaconu
manager: tfehr
ms.date: 11/27/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqSafetyKey, ReqItemTableSetup, ReqItemJournalName, ReqItemTable, EcoResProductDetailsExtended, ReqSafetyKeyDefaultDataWizard
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: kamaybac
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: ee5775826c4f7f499d015145a5e8f0f6c7a42903
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3987389"
---
# <a name="safety-stock-fulfillment-for-items"></a>Biztonsági készlet teljesítése cikkek számára

[!include [banner](../includes/banner.md)]

A biztonsági készlet egy cikk készletbeli többletét jelenti annak érdekében, hogy csökkentse a cikk készletből való kifogyásának kockázatát. A biztonsági készlet az ütközőkészlet szerepét tölti be, ha vevői rendelés érkezik, és a szállító nem képes további cikkek küldésére a vevő kért szállítási dátumának megtartásával. Ha a biztonsági készletet egy vevői rendelés teljesítésére használja, az csökkenti a biztonsági készletet. Használhatja az alaptervezést a készlet biztonsági szinthez való automatikus visszaállításához.    

## <a name="set-up-safety-stock-levels-for-items"></a>Biztonsági készlet szintjének beállítása cikkek számára

A biztonsági készlet a cikkfedezet részeként van beállítva a **Cikkfedezet** oldalon a **Kiadott termékek** > **Terv** > **Fedezet** szekcióban.

A **Minimum** mezőben adja meg az ön által fenntartani kívánt biztonsági készlet szintet a cikk számára. Az értéket készletegységben kell kifejezni. Ha üresen hagyja a mezőt, az alapértelmezett érték nulla. A mező akkor érhető el, ha az **Időszak** , **Követelmény** , vagy a **Min/Max** beállítást választja a **Fedezeti kód** listában. A készlet szintkorlátja az elérhető készletre érvényes, tehát a foglalások és jelölések akkor is előidézhetik a biztonsági készlet feltöltését, ha a tényleges mennyiség még nem csökkent a megadott minimum alá.

> [!NOTE]
> A **Minimum** mezőt csak minden más tervezett fedezetdimenzió megadása után lehet megadni. Ezzel megelőzhető az érvénytelen rekordok használata az alaptervezés során. Ilyen helyzet például akkor fordulhat elő, ha egy dimenziócsoportot kibővítenek még egy tervezett fedezetdimenzióval, és annak még nincs megadva a minimális és a maximális készletmennyisége.

A minimumkulcsok használatával kezelhetők a szezonális igényingadozások. Például egy cikk minimális készletszintje a szezonon kívül csökkenthető, majd az elkövetkező hónapok során fokozatosan növelhető. Minimumkulcs létrehozásához nyissa meg ezt: **Alaptervezés** > **Beállítás** > **Fedezet** > **Minimum-és maximumkulcsok** . A biztonsági készlet szintjének szezonalitás szerinti beállításához adja meg a minimumkulcsot a **Minimumkulcs** mezőben a **Cikkfedezet** oldalon. 

## <a name="example-minimum-key"></a>Példa: Minimumkulcs
Ha be szeretne állítani egy minimumkulcsot, ami a tavaszi- és nyári hónapokban magasabb szezonális kereslettel foglalkozik, nyissa meg ezt: **Alaptervezés** > **Beállítás** > **Fedezet** > **Minimum- és maximumkulcsok** , és kövesse az alábbi lépéseket.

1. Hozzon létre 12 sort, és rendeljen hozzájuk 1 és 12 közötti számokat a **Módosítás** mezőben.
2. Válassza ki az **Egység** mezőben a **Hónapok** lehetőséget.
3. Adja meg az alábbi táblázatban leírt elemeket és értékeket a **Szorzó** mezőben.

|Vonal|A következő érték megadása|Eredmény|
|---|---|---|
|1–3|1|A minimum készlet a **Cikkfedezet** oldalon januártól márciusig megadott beállítástól függ.|
|4-5|2|A minimum készlet áprilistól májusig 2-es szorzóval van megszorozva.|
|6-8|2,5|A minimumkészlet júniustól augusztusig 2,5 értékű szorzóval van megszorozva.|
|9-12|1|A minimum készlet visszaáll a **Cikkfedezet** oldalon szeptembertől decemberig megadott beállításra.|

Ha a fedezeti kód **Min/Max** , akkor megadhatja a **Maximum** fenntartani kívánt készletmennyiséget a cikk számára. Az értéket készletegységben is ki kell fejezni. Ha az előre jelzett elérhető készlet a minimális mennyiség alá esik, az alaptervezés egy tervezett rendelést generál, hogy mindegyik nyitott követelményt teljesítse, és az elérhető készletet a megadott maximum mennyiségre állítsa. Ahogy a **Minimum** mező esetében is, a **Maximum** mezőt csak minden más tervezett fedezetdimenzió megadása után lehet megadni.

## <a name="example-minmax-coverage-code"></a>Példa: Min/Max fedezeti kód
A minimális mennyiség 10, a maximális mennyiség pedig 15. Az aktuális készlet értéke 4. Ebből következően a minimum szükséges mennyiség 6. Azonban, mivel a maximális mennyiség 15, az alaptervezés egy tervezett rendelést generál 11 cikkre.

A szezonális keresletet követő cikkek esetében szükség lehet különböző maximum szintek fenntartására. Ehhez meg kell határoznia ezt: **Maximumkulcsok** , ami itt található: **Alaptervezés** > **Beállítás** > **Fedezet** > **Minimum-és maximumkulcsok** . Töltse ki a **maximumkulcs** mezőjét a **Cikkfedezet** oldalon. Megtekintheti a biztonsági készletszintről szóló információkat, amik minimumkulcsokkal vannak definiálva a **Min/Max** lapon, a **Cikkfedezet** lapon. Győződjön meg arról, hogy egy bizonyos ideig a minimum- és maximum értékek szinkronban vannak.

## <a name="safety-stock-fulfillment"></a>Biztonsági készlet teljesítése 

A **Minimum teljesítése** paraméter segítségével megadhatja azt az időkeretet, amikorra a készletszintnek el kell érnie a **Minimum** mezőben meghatározott mennyiséget. A mező akkor érhető el, ha az **Időszak** , **Követelmény** , vagy a **Min/Max** beállítást választja a **Fedezeti kód** listában.

Ha használatban vannak **Minimumkulcsok** , jelölje be a **Minimum időszakok** jelölőnégyzetet, ha a minimumkulcsban beállított valamennyi időszak minimum készletszintjét teljesíteni kívánja. Ha nincs bejelölve a jelölőnégyzet, akkor csak az aktuális időszak minimumkészlete lesz kielégítve.

A következő forgatókönyv bemutatja, hogyan működik ez a paraméter, és milyen különbségek vannak az értékei között.

> [!NOTE]
> Minden ebben a témakörben található illusztráció esetében az x tengely a készletet, az y tengely a napokat, az oszlopok a készlet szintjét, és a nyilak a tranzakciókat, mint például az értékesítési rendeléssorok, beszerzési rendeléssorok, vagy tervezett rendelések, jelölik.

[![Átlagos forgatókönyv biztonsági készlet teljesítésére](./media/Scenario1.png)](./media/Scenario1.png) a **Minimum teljesítése** paraméter a következő értékeket veheti fel:
### <a name="todays-date"></a>Mai dátum 
A megadott minimum mennyiség az alaptervezés futtatásának napján teljesül. A rendszer megpróbálja a lehető leghamarabb teljesíteni a biztonsági készletkorlátot, ez azonban irreális lehet az átfutási idő miatt. 
[![Követelmény a mai dátumra](./media/TodayReq.png)](./media/TodayReq.png) Egy P1 tervezett rendelés jön létre a mai dátumra az elérhető készlet biztonsági készletszintre hozásához ezen a dátumon. Az értékesítési rendeléssorok S1 és S3 között folytatják a készletszint csökkentését. A P2-P4 tervezett rendeléseket az Alaptervezés hozza létre úgy, hogy a készletszint minden értékesítési rendelés-követelmény után visszaáll a biztonsági korlátra.
Ha a **Követelmény** fedezeti kódot használja, több tervezett rendelés lesz létrehozva. Mindig érdemes **Időszak** vagy **Min/Max** fedezetet használni a folyamatosan keresett cikkek és anyagok esetén, a feltöltés kötegelésének érdekében. A következő ábrán egy példa látható az **Időszak** fedezeti kódra.
[![Időszak. Mai dátum](./media/TodayPeriod.png)](./media/TodayPeriod.png) A következő ábrán egy példa látható a **Min/Max** fedezeti kódra.
[![MinMax. Mai dátum](./media/TodayMinMax.png)](./media/TodayMinMax.png)
### <a name="todays-date--procurement-time"></a>Mai dátum + beszerzési idő 
A megadott minimum mennyiség az alaptervezés futtatását követően a beszerzéshez vagy termeléshez szükséges átfutási idő által meghatározott napon teljesül. Ez az idő tartalmazhat bármilyen biztonsági időtartalékot. Ha a cikkhez kereskedelmi megállapodás tartozik, és be van jelölve a **Kereskedelmi megállapodások keresése** jelölőnégyzete az **Alaptervezés paraméterek** oldalon, a program nem veszi figyelembe a kereskedelmi megállapodásban megadott szállítás átfutási idejét. Az átfutási idők a cikk fedezeti beállításaiból vagy magából a cikkből származnak.
Ez a teljesítési mód kevesebb késéssel és tervezett rendeléssel rendelkező terveket hoz létre ,a cikk beállított fedezeti csoportjától függetlenül. A következő ábra a terv eredményét mutatja be, ha a fedezeti kód **Követelmény** vagy **Időszak** .  
[![Követelmény.Időszak. Mai dátum és átfutási idő](./media/TodayPLTReq.png)](./media/TodayPLTReq.png) A következő ábra a terv eredményét mutatja be, ha a fedezeti kód **Min/Max** .  
[![MinMax. Mai dátum és átfutási idő](./media/TodayPLTMinMax.png)](./media/TodayPLTMinMax.png)
### <a name="first-issue"></a>Első kiadás 
A megadott minimum mennyiség azon a napon teljesül, amikor az elérhető készlet a minimum szint alá csökken, ahogy az alábbi ábra mutatja. Ha az elérhető készlet a minimum szint alatt az Alaptervezés futtatásának napján, az **Első kiadás** akkor sem kísérli meg a fedezést a következő követelmény beérkezéséig.
A következő ábrán egy példa látható a **Követelmény** fedezeti kódra.
[![Cikk tervezése **Követelmény** fedezeti kóddal és **Első kiadás** teljesítése](./media/FirstIssueReq.png)](./media/FirstIssueReq.png) A következő ábrán egy példa látható az **Időszak** fedezeti kódra.
[![Cikk tervezése **Időszak** fedezeti kóddal és **Első kiadás** teljesítése](./media/FirstIssuePeriod.png)](./media/FirstIssuePeriod.png) A következő ábrán egy példa látható a **Min/Max** fedezeti kódra.
[![Cikk tervezése **MinMax** fedezeti kóddal és **Első kiadás** teljesítése](./media/FirstIssueMinMax.png)](./media/FirstIssueMinMax.png) Az alaptervezés futtatásának napján, ha az elérhető készlet már a biztonsági készletkorlát alatt van, akkor a **Mai dátum** és a **Mai dátum + beszerzési idő** azonnal elindítják a feltöltést. Az **Első kiadás** vár, amíg nem érkezik még egy kiadási tranzakció (például értékelési rendelés vagy anyajegyzéksor-követelmény) a cikkre, majd a tranzakció napján elindítja a feltöltést. Az alaptervezés futtatásának napján, ha az elérhető készlet nem ment a biztonsági készletkorlátozás alá, akkor a **Mai dátum** és az **Első kiadás** pontosan ugyanazt az eredményt nyújtja, ahogy az az alábbi ábrán is látható. 

[![NemKorlátAlatt](./media/ReqFirstIssue.png)](./media/ReqFirstIssue.png) Az alaptervezés futtatásának napján, ha az elérhető készlet nem ment a biztonsági készletkorlátozás alá, akkor a **Mai dátum + beszerzési idő** a következő eredményt nyújtja, mivel elhalasztja a teljesítést a beszerzési átfutási idő végéig.
![Cikk tervezése **Követelmény** fedezeti kóddal és **Első kiadás** teljesítése](./media/ReqTodayLT.png)
### <a name="coverage-time-fence"></a>Fedezet időkorlátja
A megadott minimum mennyiség a **Fedezet időkorlátja** mezőben megadott időszakon belül teljesül. Ez a beállítás akkor hasznos, ha az alaptervezés nem engedélyezi az elérhető készlet használatát valós rendelésekhez, mint például értékesítések vagy átvitelek, a biztonsági szint fenntartásának érdekében. Azonban a jövőbeli programverziókban erre a feltöltési módra már nem lesz szükség, és ez a beállítás elavult lesz.
## <a name="plan-safety-stock-replenishment-for-first-expired-first-out-fefo-items"></a>Biztonsági készlet feltöltésének tervezése az első lejárt, első kiesett (FEFO) cikkekre
A biztonsági készlet számára bármilyen időpontban a legkésőbbi lejárati dátumú készletbevételezés lesz használatban, hogy a valós kereslet teljesülhessen a FEFO (első lejárt, első kiesett) rendelésben.
A folyamat megértéséhez vegye figyelembe a következő forgatókönyvet.
[![FEFOForgatókönyv](./media/FEFOScenario.png)](./media/FEFOScenario.png) A tervezés futtatásakor az fedezi az első értékesítési rendelést az aktuális készletből, illetve egy további rendelést a hátralévő mennyiséggel.
[![FEFO1](./media/FEFO1.png)](./media/FEFO1.png) Egy tervezett rendelés jön létre, hogy biztosítsa, hogy az elérhető készlet visszaáll a biztonsági korlátra.
[![FEFO2](./media/FEFO2.png)](./media/FEFO2.png) A második értékesítési rendelés tervezésekor az előző, a biztonsági készletet fedező tervezett rendelés kerül használatba ezen mennyiség fedezésére. Emiatt a biztonsági készlet folyamatosan gördül.
[![FEFO3](./media/FEFO3.png)](./media/FEFO3.png) Végül egy másik tervezett rendelés jön létre a biztonsági készlet fedezésére.
[![FEFO4](./media/FEFO4.png)](./media/FEFO4.png) Az összes köteg ennek megfelelően jár le, és tervezett rendelések jönnek létre a biztonsági készlet feltöltéséhez annak lejárta után.

## <a name="how-master-planning-handles-the-safety-stock-constraint"></a>Az alaptervezés módszere a biztonsági készlet megszorítás kezelésére

A rendszer követelménytípusként követi nyomon a biztonsági készletet, éppúgy, mint az értékesítési sorokat vagy az anyajegyzék-követelményeket. A biztonsági készlet cikkszükséglet-sorát a **Nettó követelmények** oldalon tekintheti meg, ha eltávolítja az alapértelmezett szűrőt a **Követelmény típusa** oszlopban.

A biztonsági készlet követelmény-tranzakciójának teljesítése elveszti prioritását, ha a rendszer úgy határozza, hogy ez késéseket okoz a valós kereslet teljesítésében, mint például az értékesítési sorok, az anyajegyzék-sorok, az átviteli követelmények, vagy az igény-előrejelzési sorok. Alapesetben az elérhető készlet biztonsági készlet mennyiség felett tartása ugyanolyan prioritást élvez, mint bármelyik más kereslettípus. Ez biztosítja, hogy a valós tranzakciók késés nélkül történnek, és segít a biztonsági készlet túltöltésének, illetve korai feltöltésének megakadályozásában.

Az Alaptervezés fedezeti időszaka során a biztonsági készlet feltöltése visszanyeri prioritását. Az aktuális készlet minden egyéb igénytípus előtt használható. A késleltetés számítása során egy új logika adódik hozzá a késleltetett értékesítési sorokhoz, anyajegyzéksor-követelményekhez, és minden egyéb igénytípushoz, hogy meghatározza, hogy ezek időben történő kiszállítása lehetséges-e a biztonsági készlet használatával. Ha a rendszer arra az eredményre jut, hogy a biztonsági készlet használatával minimalizálhatja a késéseket, akkor az értékesítési-, illetve anyajegyzéksorok a kezdeti fedezetüket a biztonsági készletre cserélik, és a rendszer a biztonsági készlet feltöltését indítja el.

Ha a terv vagy a cikk nem késleltetett számításra van beállítva, akkor a biztonsági készlet megszorítás ugyanolyan prioritást élvez, mint bármelyik más keresettípus. Ez azt jelenti, hogy van egy aktuális-, és egyéb elérhető készletből álló tartalék más keresettípusok előtt.
