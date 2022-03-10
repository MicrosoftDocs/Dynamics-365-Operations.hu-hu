---
title: Biztonsági készlet teljesítése cikkek számára
description: Ez a témakör bemutatja a biztonsági készlet teljesítését és a biztonsági készletmennyiség beállítását cikkek számára.
author: thethehelga
ms.date: 8/23/2021
ms.topic: article
ms.search.form: ReqSafetyKey, ReqItemTableSetup, ReqItemJournalName, ReqItemTable, EcoResProductDetailsExtended, ReqSafetyKeyDefaultDataWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-oldolg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 937341e17688959e5721153c61af904a88608b17
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790938"
---
# <a name="safety-stock-fulfillment-for-items"></a>Biztonsági készlet teljesítése cikkek számára

[!include [banner](../includes/banner.md)]

A biztonsági készlet egy cikk készletbeli többletét jelenti annak érdekében, hogy csökkentse a cikk készletből való kifogyásának kockázatát. A biztonsági készlet az ütközőkészlet szerepét tölti be, ha vevői rendelés érkezik, és a szállító nem képes további cikkek küldésére a vevő kért szállítási dátumának megtartásával. Ha a biztonsági készletet egy vevői rendelés teljesítésére használja, az csökkenti a biztonsági készletet. Használhatja az alaptervezést a készlet biztonsági szinthez való automatikus visszaállításához.

## <a name="set-up-safety-stock-levels-for-items"></a>Biztonsági készlet szintjének beállítása cikkek számára

A biztonsági készlet a cikkfedezet részeként van beállítva a **Cikkfedezet** oldalon a **Kiadott termékek \> Terv \> Fedezet** szekcióban.

A **Minimum** mezőben adja meg az ön által fenntartani kívánt biztonsági készlet szintet a cikk számára. Az értéket készletegységben kell kifejezni. Ha üresen hagyja a mezőt, az alapértelmezett érték nulla. A mező akkor érhető el, ha az **Időszak**, **Követelmény**, vagy a **Min/Max** beállítást választja a **Fedezeti kód** listában. A készlet szintkorlátja az elérhető készletre érvényes, tehát a foglalások és jelölések akkor is előidézhetik a biztonsági készlet feltöltését, ha a tényleges mennyiség még nem csökkent a megadott minimum alá.

> [!NOTE]
> A **Minimum** mezőt csak minden más tervezett fedezetdimenzió megadása után lehet megadni. Ezzel megelőzhető az érvénytelen rekordok használata az alaptervezés során. Ilyen helyzet például akkor fordulhat elő, ha egy dimenziócsoportot kibővítenek még egy tervezett fedezetdimenzióval, és annak még nincs megadva a minimális és a maximális készletmennyisége.

A minimumkulcsok használatával kezelhetők a szezonális igényingadozások. Például egy cikk minimális készletszintje a szezonon kívül csökkenthető, majd az elkövetkező hónapok során fokozatosan növelhető. Minimumkulcs létrehozásához nyissa meg ezt: **Alaptervezés \> Beállítás \> Fedezet \> Minimum-és maximumkulcsok**. A biztonsági készlet szintjének szezonalitás szerinti beállításához adja meg a minimumkulcsot a **Minimumkulcs** mezőben a **Cikkfedezet** oldalon.

## <a name="example-minimum-key"></a>Példa: Minimumkulcs

Az alábbi művelet egy példát mutat be, amely megmutatja, hogyan lehet beállítani egy minimumkulcsot, amely a magasabb szezonális igényeket figyelembe veszi a tavaszi és nyári hónapokban.

1. Manjen az **Alaptervezés \> Beállítás \> Fedezet \> Minimum/maximum kulcsok** menübe.
1. Minimum/maximum kulcs létrehozásához válassza az **Új** lehetőséget.
1. A **Minimum vagy maximum kulcs** mezőbe írja be a kulcs azonosítóját. Adjon nevet a kulcsnak a **Név** mezőben.
1. Állítsa az **Érvényességi dátum használata** lehetőséget *Igen* beállításra, és hagyja üresen az **Érvényességi dátum** mezőt, hogy a kulcs az aktuális év első napjától érvényes legyen.

    > [!NOTE]
    > Az **Érvényességi dátum használata** és az **Érvényességi dátum** beállítás kombinációja határozza meg, hogy a kulcs melyik dátumtól érvényes.
    >
    > - Ha az **Érvényességi dátum használata** beállítás *Nem*, a kulcs az aktuális dátumtól vagy a rendszerdátumtól érvényes.
    > - Amikor az **Érvényességi dátum használata** beállítás értéke *Igen*, a kulcs az **Érvényességi dátum** mezőben megadott dátumtól érvényes.

1. Hozzon létre 12 sort az **Időszakok** szakaszban, és állítsa be a következő értékeket:

    - **Módosítás** – Minden sorhoz rendeljen hozzá egy egyedi számot 1 és 12 között. Ez a mező jelzi az **Egység** mező által meghatározott időegység növekményes változását.
    - **Egység** – Válasszon *Hónapokat* minden sorhoz.
    - **Kezdő dátum**, **Befejezési dátum** és **Hónap** – Ezeket a mezőket a rendszer automatikusan beállítja a **Módosítás** és az **Egység** beállítása alapján. A havi időszakok az aktuális év első naptól kezdődnek.
    - **Szorzó** – Adja meg az alábbi táblázatban leírt elemeket és értékeket. Ez a mező azt a szorzót határozza meg, amelyet meg szeretne szorozni a minimális készlettel.

        | Sor (Módosítás) | Szorzó | Eredmény |
        |---|---|---|
        | 1–3 | 1 | A minimum készlet a **Cikkfedezet** oldalon januártól márciusig megadott beállítástól függ. |
        | 4–5 | 2 | A minimum készlet áprilistól májusig 2-es szorzóval van megszorozva. |
        | 6–8 | 2.5 | A minimumkészlet júniustól augusztusig 2,5 értékű szorzóval van megszorozva. |
        | 9–12 | 1 | A minimum készlet visszaáll a **Cikkfedezet** oldalon szeptembertől decemberig megadott beállításra. |

    A beállításoknak most hasonlítaniuk kellene az alábbi ábra beállításaihoz.

    ![Minimum- vagy maximumkulcs-időszakok.](media/min-max-key-periods.png "Minimum- vagy maximumkulcs-időszakok")

> [!NOTE]
> A varázsló használatával minimum- vagy maximumkulcs is létrehozható. A **Minimum- vagy maximumkulcsok** lapon, a műveleti ablaktáblán válassza ki a **Varázslót** a **Minimum- és maximumkulcsok** varázsló megnyitásához. A varázsló lépésenként végigvezeti a minimum- és maximumkulcs létrehozásának és beállításának folyamatán.

Ha a fedezeti kód *Min/Max*, akkor megadhatja a Maximum fenntartani kívánt készletmennyiséget egy adott cikk számára. Az értéket készletegységben is ki kell fejezni. Ha az előre jelzett elérhető készlet a minimális mennyiség alá esik, az alaptervezés egy tervezett rendelést generál, hogy mindegyik nyitott követelményt teljesítse, és az elérhető készletet a megadott maximum mennyiségre állítsa. Ahogy a minimum készletmennyiség beállításakor is, a **Maximum** mezőt csak minden más tervezett fedezetdimenzió megadása után lehet megadni.

## <a name="example-minmax-coverage-code"></a>Példa: Min/Max fedezeti kód

A minimális mennyiség 10, a maximális mennyiség pedig 15. Az aktuális készlet értéke 4. Ebből következően a minimum szükséges mennyiség 6. Azonban, mivel a maximális mennyiség 15, az alaptervezés egy tervezett rendelést generál 11 cikkre.

A szezonális keresletet követő cikkek esetében szükség lehet különböző maximum szintek fenntartására. Ehhez meg kell határoznia ezt: **Maximumkulcsok**, ami itt található: **Alaptervezés \> Beállítás \> Fedezet \> Minimum-és maximumkulcsok**. Töltse ki a **maximumkulcs** mezőjét a **Cikkfedezet** oldalon. Megtekintheti a biztonsági készletszintről szóló információkat, amik minimumkulcsokkal vannak definiálva a **Min/Max** lapon, a **Cikkfedezet** lapon. Győződjön meg arról, hogy egy bizonyos ideig a minimum- és maximum értékek szinkronban vannak.

## <a name="safety-stock-fulfillment"></a>Biztonsági készlet teljesítése

A **Minimum teljesítése** paraméter segítségével megadhatja azt az időkeretet, amikorra a készletszintnek el kell érnie a **Minimum** mezőben meghatározott mennyiséget. A mező akkor érhető el, ha az **Időszak**, **Követelmény**, vagy a **Min/Max** beállítást választja a **Fedezeti kód** listában.

Ha használatban vannak **Minimumkulcsok**, jelölje be a **Minimum időszakok** jelölőnégyzetet, ha a minimumkulcsban beállított valamennyi időszak minimum készletszintjét teljesíteni kívánja. Ha nincs bejelölve a jelölőnégyzet, akkor csak az aktuális időszak minimumkészlete lesz kielégítve.

A következő forgatókönyv bemutatja, hogyan működik ez a paraméter, és milyen különbségek vannak az értékei között.

> [!NOTE]
> Minden ebben a témakörben található illusztráció esetében az x tengely a készletet, az y tengely a napokat, az oszlopok a készlet szintjét, és a nyilak a tranzakciókat, mint például az értékesítési rendeléssorok, beszerzési rendeléssorok, vagy tervezett rendelések, jelölik.

[![ Gyakori forgatókönyv biztonsági készlet teljesítése számára.](media/Scenario1.png)](media/Scenario1.png)

A **Minimális teljesítése** paraméter a következő értékeket tartalmazhatja:

### <a name="todays-date"></a>Mai dátum

A megadott minimum mennyiség az alaptervezés futtatásának napján teljesül. A rendszer megpróbálja a lehető leghamarabb teljesíteni a biztonsági készletkorlátot, ez azonban irreális lehet az átfutási idő miatt.

[![ Követelmény a mai dátumra.](media/TodayReq.png)](media/TodayReq.png)

Egy P1 tervezett rendelés jön létre a mai dátumra az elérhető készlet biztonsági készletszintre hozásához ezen a dátumon. Az értékesítési rendeléssorok S1 és S3 között folytatják a készletszint csökkentését. A P2-P4 tervezett rendeléseket az Alaptervezés hozza létre úgy, hogy a készletszint minden értékesítési rendelés-követelmény után visszaáll a biztonsági korlátra.

Ha a **Követelmény** fedezeti kódot használja, több tervezett rendelés lesz létrehozva. Mindig érdemes **Időszak** vagy **Min/Max** fedezetet használni a folyamatosan keresett cikkek és anyagok esetén, a feltöltés kötegelésének érdekében. A következő ábrán egy példa látható az **Időszak** fedezeti kódra.

[![ Időszak. Mai dátum.](media/TodayPeriod.png)](media/TodayPeriod.png)

A következő ábrán egy példa látható a **Min/Max** fedezeti kódra.

[![ Min/Max. Mai dátum.](media/TodayMinMax.png)](media/TodayMinMax.png)

### <a name="todays-date--procurement-time"></a>Mai dátum + beszerzési idő

A megadott minimum mennyiség az alaptervezés futtatását követően a beszerzéshez vagy termeléshez szükséges átfutási idő által meghatározott napon teljesül. Ez az idő tartalmazhat bármilyen biztonsági időtartalékot. Ha a cikkhez kereskedelmi megállapodás tartozik, és be van jelölve a **Kereskedelmi megállapodások keresése** jelölőnégyzete az **Alaptervezés paraméterek** oldalon, a program nem veszi figyelembe a kereskedelmi megállapodásban megadott szállítás átfutási idejét. Az átfutási idők a cikk fedezeti beállításaiból vagy magából a cikkből származnak.

Ez a teljesítési mód kevesebb késéssel és tervezett rendeléssel rendelkező terveket hoz létre ,a cikk beállított fedezeti csoportjától függetlenül.

A következő ábra a terv eredményét mutatja be, ha a fedezeti kód **Követelmény** vagy **Időszak**.

[![ Követelmény vagy Időszak. Mai dátum és átfutási idő.](media/TodayPLTReq.png)](media/TodayPLTReq.png)

A következő ábra a terv eredményét mutatja be, ha a fedezeti kód **Min/Max**.

[![ Min/Max. Mai dátum és átfutási idő.](media/TodayPLTMinMax.png)](media/TodayPLTMinMax.png)

### <a name="first-issue"></a>Első kiadás

A megadott minimum mennyiség azon a napon teljesül, amikor az elérhető készlet a minimum szint alá csökken, ahogy az alábbi ábra mutatja. Ha az elérhető készlet a minimum szint alatt az Alaptervezés futtatásának napján, az **Első kiadás** akkor sem kísérli meg a fedezést a következő követelmény beérkezéséig.

A következő ábrán egy példa látható a **Követelmény** fedezeti kódra.

[![ Cikk tervezése Követelmény fedezeti kóddal és Első kiadás teljesítéssel.](media/FirstIssueReq.png)](media/FirstIssueReq.png)

A következő ábrán egy példa látható az **Időszak** fedezeti kódra.

[![ Cikk tervezése Időszak fedezeti kóddal és Első kiadás teljesítéssel.](media/FirstIssuePeriod.png)](media/FirstIssuePeriod.png)

A következő ábrán egy példa látható a **Min/Max** fedezeti kódra.

[![ Cikk tervezése MinMax fedezeti kóddal és Első kiadás teljesítéssel.](media/FirstIssueMinMax.png)](media/FirstIssueMinMax.png)

Az alaptervezés futtatásának napján, ha az elérhető készlet már a biztonsági készletkorlát alatt van, akkor a **Mai dátum** és a **Mai dátum + beszerzési idő** azonnal elindítják a feltöltést. Az **Első kiadás** vár, amíg nem érkezik még egy kiadási tranzakció (például értékelési rendelés vagy anyajegyzéksor-követelmény) a cikkre, majd a tranzakció napján elindítja a feltöltést.

Az alaptervezés futtatásának napján, ha az elérhető készlet nem ment a biztonsági készletkorlátozás alá, akkor a **Mai dátum** és az **Első kiadás** pontosan ugyanazt az eredményt nyújtja, ahogy az az alábbi ábrán is látható.

[![ Nem korláton belül.](media/ReqFirstIssue.png)](media/ReqFirstIssue.png)

Az alaptervezés futtatásának napján, ha az elérhető készlet nem ment a biztonsági készletkorlátozás alá, akkor a **Mai dátum + beszerzési idő** a következő eredményt nyújtja, mivel elhalasztja a teljesítést a beszerzési átfutási idő végéig.

![A teljesítés elhalasztva a beszerzés átfutási ideje végéig.](media/ReqTodayLT.png)

### <a name="coverage-time-fence"></a>Fedezet időkorlátja

A megadott minimum mennyiség a **Fedezet időkorlátja** mezőben megadott időszakon belül teljesül. Ez a beállítás akkor hasznos, ha az alaptervezés nem engedélyezi az elérhető készlet használatát valós rendelésekhez, mint például értékesítések vagy átvitelek, a biztonsági szint fenntartásának érdekében. Azonban a jövőbeli programverziókban erre a feltöltési módra már nem lesz szükség, és ez a beállítás elavult lesz.

## <a name="plan-safety-stock-replenishment-for-first-expired-first-out-fefo-items"></a>Biztonsági készlet feltöltésének tervezése az első lejárt, első kiesett (FEFO) cikkekre

A biztonsági készlet számára bármilyen időpontban a legkésőbbi lejárati dátumú készletbevételezés lesz használatban, hogy a valós kereslet teljesülhessen a FEFO (első lejárt, első kiesett) rendelésben.

A folyamat megértéséhez vegye figyelembe a következő forgatókönyvet.

[![ FEFO eset.](media/FEFOScenario.png)](media/FEFOScenario.png)

A tervezés futtatásakor az fedezi az első értékesítési rendelést az aktuális készletből, illetve egy további rendelést a hátralévő mennyiséggel.

[![ FEFO 1.](media/FEFO1.png)](media/FEFO1.png)

Egy tervezett rendelés jön létre, hogy biztosítsa, hogy az elérhető készlet visszaáll a biztonsági korlátra.

[![ FEFO 2.](media/FEFO2.png)](media/FEFO2.png)

A második értékesítési rendelés tervezésekor az előző, a biztonsági készletet fedező tervezett rendelés kerül használatba ezen mennyiség fedezésére. Emiatt a biztonsági készlet folyamatosan gördül.

[![ FEFO 3.](media/FEFO3.png)](media/FEFO3.png)

Végül egy másik tervezett rendelés jön létre a biztonsági készlet fedezésére.

[![ FEFO 4.](media/FEFO4.png)](media/FEFO4.png)

Az összes köteg ennek megfelelően jár le, és tervezett rendelések jönnek létre a biztonsági készlet feltöltéséhez annak lejárta után.

## <a name="how-master-planning-handles-the-safety-stock-constraint"></a>Az alaptervezés módszere a biztonsági készlet megszorítás kezelésére

A rendszer követelménytípusként követi nyomon a biztonsági készletet, éppúgy, mint az értékesítési sorokat vagy az anyajegyzék-követelményeket. A biztonsági készlet cikkszükséglet-sorát a **Nettó követelmények** oldalon tekintheti meg, ha eltávolítja az alapértelmezett szűrőt a **Követelmény típusa** oszlopban.

A biztonsági készlet követelmény-tranzakciójának teljesítése elveszti prioritását, ha a rendszer úgy határozza, hogy ez késéseket okoz a valós kereslet teljesítésében, mint például az értékesítési sorok, az anyajegyzék-sorok, az átviteli követelmények, vagy az igény-előrejelzési sorok. Alapesetben az elérhető készlet biztonsági készlet mennyiség felett tartása ugyanolyan prioritást élvez, mint bármelyik más kereslettípus. Ez biztosítja, hogy a valós tranzakciók késés nélkül történnek, és segít a biztonsági készlet túltöltésének, illetve korai feltöltésének megakadályozásában.

Az Alaptervezés fedezeti időszaka során a biztonsági készlet feltöltése visszanyeri prioritását. Az aktuális készlet minden egyéb igénytípus előtt használható. A késleltetés számítása során egy új logika adódik hozzá a késleltetett értékesítési sorokhoz, anyajegyzéksor-követelményekhez, és minden egyéb igénytípushoz, hogy meghatározza, hogy ezek időben történő kiszállítása lehetséges-e a biztonsági készlet használatával. Ha a rendszer arra az eredményre jut, hogy a biztonsági készlet használatával minimalizálhatja a késéseket, akkor az értékesítési-, illetve anyajegyzéksorok a kezdeti fedezetüket a biztonsági készletre cserélik, és a rendszer a biztonsági készlet feltöltését indítja el.

Ha a terv vagy a cikk nem késleltetett számításra van beállítva, akkor a biztonsági készlet megszorítás ugyanolyan prioritást élvez, mint bármelyik más keresettípus. Ez azt jelenti, hogy van egy aktuális-, és egyéb elérhető készletből álló tartalék más keresettípusok előtt.

## <a name="additional-resources"></a>További erőforrások

- [A biztonsági készlet napló használata a cikkek minimális fedezetének frissítésére](safety-stock-journal.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
