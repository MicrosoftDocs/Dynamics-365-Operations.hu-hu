---
title: Feltöltés a zóna küszöbértéke alapján
description: A zónaalapú feltöltés a minimális/maximális (min/max) feltöltési stratégiát használja, de az egész raktári zónákat értékeli az egyes helyek helyett. Ezért a raktárkezelők gyorsabban megtudhatják, ha a kitárolási zónában további készlet szükséges.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6f4ddd03ec16ac43b007b904eb688563735e0941
ms.sourcegitcommit: d9bffbeae2ba14f06294dd275383077d4d65c4fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654172"
---
# <a name="zone-threshold-replenishment"></a>Feltöltés a zóna küszöbértéke alapján

[!include [banner](../includes/banner.md)]

A zónaalapú feltöltés a minimális/maximális (min/max) [feltöltési](replenishment.md) stratégiát használja, de az egész raktári zónákat értékeli az egyes helyek helyett. Ezért a raktárkezelők gyorsabban megtudhatják, ha a kitárolási zónában további készlet szükséges.

Ennek a funkciónak a beállítása a helyalapú feltöltés beállításához hasonlít. Ha azonban a minimális/maximális feltöltéshez beállítja a sablont, akkor megadhatja azt is, hogy a küszöböt egy helyenként vagy zónánként kell-e értékelni. Ha zónákon alapuló értékelést állított be, akkor meghatározott zónákat kell hozzáadnia a zónák kiválasztása lekérdezéshez.

A helyalapú min/max feltöltéshez hasonlóan a zóna alapú min/max feltöltés alapja a minimális készletküszöb beállítása, amely a kiválasztott cikkekre vonatkozó feltöltési munka létrehozását indítja. Ez a feltöltési munka növeli a készletet a zóna megadott maximális küszöbértékéig.

> [!NOTE]
> Az aktuális kiadásban nem használhatók a zónák feltöltési folyamatai a termékváltozatokhoz.


A hely alapú min/max feltöltéssel ellentétben a zónaalapú min/max feltöltés nem igényel fix helyeket annak kiértékeléséhez, hogy a helyeknek egy adott terméket tárolniuk kell-e. Ennélfogva a zónákon alapuló feltöltésnél a min/max feltöltés akkor is használható, ha a raktárban nincs minden egyes elemhez vagy elemvariánshoz rögzített hely. Ha a zónában szereplő mennyiség a meghatározott minimális küszöbérték alá esik, akkor létrejön a feltöltési munka. A helyutasítások határozzák meg, hogy a készlet mely meghatározott helyen kerüljön elhelyezésre.

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a>A Feltöltés a zóna küszöbértéke alapján funkció bekapcsolása

A *Feltöltés a zóna küszöbértéke alapján* funkció használatához a rendszerben be kell azt kapcsolni. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Feltöltés a zóna küszöbértéke alapján*

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a>Zónaalapú feltöltés beállítása

A zónaalapú feltöltés beállításához a rendszer több részét kell konfigurálnia. Ez a szakasz bemutatja a különböző beállításokat, valamint a bemutató adatértékeket biztosít, amelyeket meg lehet adni, ha végig akar haladni a témakör végén található forgatókönyvön.

### <a name="set-up-directive-codes"></a>Utasításkódok beállítása

Az [utasításkódok](control-warehouse-location-directives.md) segítségével a munkasablonban használt helysablon meghatározásakor pontosabban járhat el. Mindegyik kód egy olyan közös értéket hoz létre, amelyre hivatkozhat, amikor az egyes típusú sablonokat konfigurálja.

#### <a name="view-and-edit-directive-codes"></a>Utasításkódok megtekintése és szerkesztése

Az utasításkódok megtekintéséhez vagy szerkesztéséhez nyissa meg a **Raktárkezelés \> Beállítás \> Utasításkódok** elemet.

#### <a name="prepare-demo-data-directive-codes"></a>A bemutatóadatok utasításkódjainak előkészítése

Ez a példa azt mutatja be, hogyan kell előkészíteni az utasításkódot. Ha azt tervezi, hogy végighalad a téma végén található forgatókönyvön, használja az itt megadott bemutatóértékeket. Ellenkező esetben használja a saját értékeit.

1. Válassza ki az **USMF** jogi személyt a bemutatóadatok kezeléséhez.
1. Ugrás a **Raktárkezelés \> Beállítás \> Utasítskódok** elemre.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Utasításkód:** _Zóna felt_
    - **Utasítás leírása:** _Zóna feltöltése_

1. Az új kód mentéséhez válassza a **Mentés** parancsot.

### <a name="set-up-replenishment-templates"></a>Feltöltési sablonok beállítása

[A min/max feltöltési sablonok](tasks/set-up-min-max-replenishment-process.md) a legfontosabbak a megfelelő szintek megtartásához a kitárolási helyeken. Ezekben a sablonokban be kell állítania azokat a szabályokat, amelyek a készletnek a raktárban történő feltöltésekor használatosak. Az a feltöltés, amellyel a sablonok használhatók, zónaalapú feltöltést tartalmaz.

#### <a name="view-and-edit-replenishment-templates"></a>Feltöltési sablonok megtekintése és szerkesztése.

A feltöltési sablont olyan szabályok alkotják, amelyek megszabják, mikor és hogyan töltik fel a helyet. Kiválaszthatja azt a sablont, amely meghatározza, hogy mikor és hogyan történik a feltöltés. A feltöltési sablonjai megtekintéséhez és szerkesztéséhez lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok** pontra.

#### <a name="prepare-a-demo-data-replenishment-template"></a>Bemutatóadatokból álló feltöltési sablon előkészítése

Ez a példa azt mutatja be, hogyan kell előkészíteni egy feltöltési sablont. Ha azt tervezi, hogy végighalad a téma végén található forgatókönyvön, használja az itt megadott bemutatóértékeket. Ellenkező esetben használja a saját értékeit.

1. Válassza ki az **USMF** jogi személyt a bemutatóadatok kezeléséhez.
1. Ugorjon a **Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok** pontra.
1. Válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.
1. A Művelet panelen válassza az **Új** lehetőséget egy sor hozzáadásához az **Áttekintés** rácshoz.
1. Az új sorban állítsa be a következő értékeket: Az összes többi mezőben hagyja meg az alapértelmezett értéket.

    - **Feltöltésisablon:** _Zóna min/max felt_
    - **Leírás:** _Zóna min/max feltöltése_
    - **Feltöltés típusa:** _Minimális vagy maximális_

1. Válassza a **Mentés** lehetőséget.
1. Miközben az új sor továbbra is be van jelölve az **Áttekintés** rácsban, válassza ki az **Új** lehetőséget a **Feltöltési sablon részletei** rács felett a most létrehozott *Zóna min/max feltöltése* feltöltési sablonhoz társított sor hozzáadásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorozatszám:** Adja meg az _1_ értéket.
    - **Leírás:** Adja meg a _Ktárolási zóna feltöltése_ értéket.
    - **Feltöltési egység:** Válassza az _ea_ elemet.
    - **Kérés típusa:** Hagyja üresen ezt a mezőt.
    - **Utasításkód**: Ez a mező hozzákapcsolja a helyutasításokat a feltöltési sablonhoz. Válassza ki a korábban létrehozott bemutatóadat utasításkódot (_Zóne felt_).
    - **Munkasablon:** Hagyja üresen ezt a mezőt.
    - **Minimális mennyiség:** Ez a mező azt a mennyiséget adja meg, amelynél a feltöltés aktiválódik. Adja meg az _50_ értéket.
    - **Maximális mennyiség:** Ez a mező azt a maximális mennyiséget állítja be, amennyi egy adott cikkből egy zónában jelen lehet. A létrejövő feltöltési munka növeli a készletet erre a mennyiségre. Adja meg a _150_ értéket.
    - **Egység:** Ez a mező a minimális és maximális értékek egységét határozza meg. Válassza ki az _ea_ értéket.
    - **Igény növekménye:** Válassza a _Felfelé kerekítés_ lehetőséget.
    - **Üres rögzített helyek feltöltése:** Jelölje be ezt a jelölőnégyzetet.
    - **Csak a rögzített helyek feltöltése:** Jelölje be ezt a jelölőnégyzetet.
    - **A termék lekérdezési módja:** Válassza ki a _Termék lekérdezése_ lehetőséget.
    - **Feltöltési küszöbérték hatóköre:** Ez a mező határozza meg, hogy a sablonnak zónánként vagy adott helyenként kell-e kiértékelnie. Válassza a _Zóna_ lehetőséget.
    - **Raktár:** Válassza a _61_ értéket.

1. Válassza a **Termékek kiválasztása** lehetőséget a **Feltöltési sablon részletei** rács fölött.
1. A **Terméklekérdezés** párbeszédpanelen, a **Tartomány** lapon a **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Tábla:** _Cikkek_
    - **Származtatott tábla:** _Cikkek_
    - **Mező:** _Cikkszám_
    - **Feltételek:** _A0001_

1. Az **OK** gombra kattintva mentse a lekérdezését, és zárja be a párbeszédpanelt.
1. Válassza a **Feltöltendő zónák kiválasztása** lehetőséget a **Feltöltési sablon részletei** rács fölött.
1. A **Zónalekérdezés** párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Tábla:** _Raktári zóna_
    - **Származtatott tábla:** _Raktári zóna_
    - **Mező:** _Zóna azonosítója_
    - **Feltételek:** _EMELET_

1. Az **OK** gombra kattintva mentse a lekérdezését, és zárja be a párbeszédpanelt.

### <a name="set-up-location-directives"></a>Helyutasítások beállítása

A helyalapú min/max feltöltéssel ellentétben a zónákon alapuló min/max feltöltéshez mind a kitárolási helyutasítást, mind az elhelyezési helyutasítást be kell állítani, mivel a rendszer csak a kimenő munka kitárolási helye helyett az egész zónát kiértékeli.

#### <a name="view-and-edit-location-directives"></a>Helyutasítások megtekintése és szerkesztése

A helyutasítások megtekintéséhez vagy szerkesztéséhez nyissa meg a **Raktárkezelés \> Beállítás \> Helyutasítások** elemet.

A szükséges kitárolási helyutasítások és elhelyezési helyutasítások létrehozására vonatkozó beállítások használatával kapcsolatban tekintse meg a következő szakaszt.

#### <a name="prepare-demo-data-location-directives"></a>A bemutatóadatok helyutasításainak előkészítése

A bemutatóadatok előkészítéséhez, hogy a témakör végén felhasználhatók legyenek a forgatókönyvben, két helyutasítást kell létrehoznia, amelyek egyike a kitárolásra, a másik pedig az elhelyezésre vonatkozik.

##### <a name="create-a-replenishment-pick-directive"></a>Feltöltési kitárolási utasítás létrehozása

1. Válassza ki az **USMF** jogi személyt a bemutatóadatok kezeléséhez.
1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A bal oldali ablaktáblában állítsa a **Munkarendelés típusa** mezőt a _Feltöltés_ értékre.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget az új utasítás létrehozásához.
1. Adja meg az alábbi értékeket:

    - **Sorszám:** Fogadja el az alapértelmezett értéket.
    - **Név:** Adja meg a _Zóna kitárolás_ értéket.
    - **Munka típusa:** Válassza a _Kitárolás_ lehetőséget.
    - **Hely:** Válassza a _6_ értéket.
    - **Raktár:** Válassza a _61_ értéket.
    - **Utasításkód:** Hagyja üresen ezt a mezőt.
    - **Több raktározási egység:** Állítsa a beállítást _Nem_ értékre.

1. A **Mentés** gombra kattintva hozzon létre egy olyan irányelvet, amely az eddig beállított beállításokat tartalmazta.
1. A **Sorok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorozatszám:** Adja meg az _1_ értéket.
    - **Kezdő mennyiség:** Adja meg a _0_ értéket.
    - **Cél mennyiség:** Adja meg a _10000000_ értéket.
    - **Egység:** Ezt a mezőt hagyja üresen.
    - **Mennyiség megkeresése:** Válassza a _Nincs_ beállítást.
    - **Korlátozás egység szerint:** Törölje a jelölőnégyzet kiválasztását.
    - **Felkerekítés az egységhez:** Törölje a jelet a jelölőnégyzetből.
    - **Csomagolási mennyiség keresése:** Törölje a jelet a jelölőnégyzetből.
    - **Felosztás engedélyezése:** Válassza ki ezt a jelölőnégyzetet.

1. Az új sor mentéséhez válassza a **Mentés** parancsot.
1. Ha az új sor továbbra is a **Sorok** rácsban van kiválasztva, akkor a **Helyutasítás műveletei** gyorslap **Új** elemét választva adhat hozzá egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorozatszám:** Adja meg az _1_ értéket.
    - **Név:** Adja meg az _Ömlesztett kitárolás_ lehetőséget.
    - **Helyhez kötött használat:** Válassza a _Rögzített és nem rögzített helyek_ lehetőséget.
    - **Negatív készlet engedélyezése:** Törölje a jelet a jelölőnégyzetből.
    - **Köteg engedélyezve:** Törölje a jelet a jelölőnégyzetből.
    - **Stratégia:** Válassza a _Nincs_ beállítást.

1. Az új művelet mentéséhez válassza a **Mentés** parancsot.
1. Miközben az új művelet továbbra is be van jelölve, jelölje be a **Lekérdezés szerkesztése** elemet a **Helyutasítás műveletei** rács felett.
1. Megjelenik egy lekérdezési párbeszédpanel, amelyen megadhatja, hogy milyen helyekről kell elvégeznie a feltöltést. A **tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Tábla:** _Helyek_
    - **Származtatott tábla:** _Helyek_
    - **Mező:** _Zóna azonosítója_
    - **Feltételek:** _BULK_

1. Az **OK** gombra kattintva mentse a lekérdezését, és zárja be a párbeszédpanelt.
1. A helyutasítás mentéséhez válassza a **Mentés** elemet.

##### <a name="create-a-replenishment-put-directive"></a>Feltöltési elhelyezési utasítás létrehozása

1. A **Helyutasítások** lap bal oldali panelén győződjön meg róla, hogy a **Munkarendelés típusa** mező továbbra is a _Feltöltés_ értékre van beállítva.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget az új utasítás létrehozásához.
1. Adja meg az alábbi értékeket:

    - **Sorszám:** Fogadja el az alapértelmezett értéket.
    - **Név:** Adja meg a _Zóna elhelyezés_ értéket.
    - **Munkarendelés típusa:** Válassza az _Elhelyezés_ elemet.
    - **Hely:** Válassza a _6_ értéket.
    - **Raktár:** Válassza a _61_ értéket.
    - **Utasításkód:** Válassza ki a _Zóna felt_ lehetőséget, hogy ezt a helyutasítást a korábban létrehozott kód alapján a korábban létrehozott feltöltési sablonnal kapcsolja.
    - **Több raktározási egység:** Állítsa a beállítást _Nem_ értékre.

1. A **Mentés** gombra kattintva hozzon létre egy olyan irányelvet, amely az eddig beállított beállításokat tartalmazta.
1. A **Sorok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorozatszám:** Adja meg az _1_ értéket.
    - **Kezdő mennyiség:** Adja meg a _0_ értéket.
    - **Cél mennyiség:** Adja meg a _10000000_ értéket.
    - **Egység:** Ezt a mezőt hagyja üresen.
    - **Mennyiség megkeresése:** Válassza a _Nincs_ beállítást.
    - **Korlátozás egység szerint:** Törölje a jelölőnégyzet kiválasztását.
    - **Felkerekítés az egységhez:** Törölje a jelet a jelölőnégyzetből.
    - **Csomagolási mennyiség keresése:** Törölje a jelet a jelölőnégyzetből.
    - **Felosztás engedélyezése:** Válassza ki ezt a jelölőnégyzetet.

1. Az új sor mentéséhez válassza a **Mentés** parancsot.
1. Ha az új sor továbbra is a **Sorok** rácsban van kiválasztva, akkor a **Helyutasítás műveletei** gyorslap **Új** elemét választva adhat hozzá egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorozatszám:** Adja meg az _1_ értéket.
    - **Név:** Adja meg a _Zóna elhelyezés_ értéket.
    - **Helyhez kötött használat:** Válassza a _Rögzített és nem rögzített helyek_ lehetőséget.
    - **Negatív készlet engedélyezése:** Törölje a jelet a jelölőnégyzetből.
    - **Köteg engedélyezve:** Törölje a jelet a jelölőnégyzetből.
    - **Stratégia:** Válassza a _Konszolidáció_ elemet.

1. Az új művelet mentéséhez válassza a **Mentés** parancsot.
1. Miközben az új művelet továbbra is be van jelölve, jelölje be a **Lekérdezés szerkesztése** elemet a **Helyutasítás műveletei** rács felett.
1. Megjelenik egy lekérdezési párbeszédpanel, amelyen megadhatja, hogy milyen zónákat kell feltölteni. Ennek a zónának meg kell egyeznie a feltöltési sablonban megadott zónával. A **tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Tábla:** _Helyek_
    - **Származtatott tábla:** _Helyek_
    - **Mező:** _Zóna azonosítója_
    - **Feltételek:** _EMELET_

1. Az **OK** gombra kattintva mentse a lekérdezését, és zárja be a párbeszédpanelt.
1. A helyutasítás mentéséhez válassza a **Mentés** elemet.

## <a name="scenario"></a>Forgatókönyv

Ez a szakasz egy példaesetet tartalmaz, amely bemutatja a funkció kezelését.

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a>Készítse elő a mintaesethez szükséges mintaadatokat

Mielőtt elkezdené a munkafolyamatot, aktiválni kell a mintaadatokat, és be kell állítania a szolgáltatást az ebben a szakaszban és a témakör korábbi szakaszaiban ismertetett módon.

#### <a name="use-the-usmf-legal-entity"></a>Az USMF jogi személy használata

Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

#### <a name="prepare-additional-sample-data"></a>További mintaadatok előkészítése

Miután kiválasztotta az **USMF** jogi személyt, vegye fel a szükséges további mintaadattípusokat a témakör korábbi, [Zónaalapú feltöltés beállítása](#setup) című részében írtak szerint.

#### <a name="check-your-on-hand-inventory"></a>Ellenőrizze az aktuális készletet

Kövesse az alábbi lépéseket, és győződjön meg arról, hogy a rendszer elegendő készletet tartalmaz a mintaeset támogatására.

1. Győződjön meg róla, hogy az *A0001* cikk esetében feltöltési sablonban megadott kitárolási zóna (*EMELET*) két különböző helyén is van aktuális készlet. A teljes készletnek azonban kisebbnek kell lennie, mint a feltöltési sablonban megadott kötelező minimális mennyiség (*50*). Ily módon szimulálhatja, hogy hogyan történik a számítás az egész zónában, nem csak egy helyen. **A raktári folyamatokkal a szükséges módon módosíthatja a készletet.**
1. Győződjön meg róla, hogy elegendő készlet van az *A0001* cikkből az ömlesztett tárolóhelyen, amely a zóna kitárolási helyutasításában meg van adva, ahonnan a feltöltési munkának ki kell tárolnia a cikkeket az *ÖMLESZTETT* zónaazonosítóból. A teljes készletnek azonban többnek kell lennie, mint a feltöltési sablonban megadott kötelező maximális mennyiség (*150*).
1. Nem kötelező, de javasolt: Hajtsa végre a következő lépéseket egy készlethelyesbítési napló létrehozásához:

    1. Lépjen a **Készletgazdálkodás \> Naplóbejegyzések \> Cikkek \> Készlethelyesbítés** lehetőségre.
    1. Válassza az **Új** lehetőséget.
    1. Válassza a **Készletnapló létrehozása** párbeszédpanel **Raktár** mezőjének *61* pontját.
    1. Válassza ki az **OK** lehetőséget.
    1. A **Naplósorok** gyorslapon az **Új** gombra kattintva adja hozzá a rácshoz a három sort, és adja meg a következő értékeket. Miután befejezte az egyes sorok beállítását, válassza a **Mentés** elemet.

        - **1. sor:**

            - **Cikkszám:** *A0001*
            - **Telephely:** *6*
            - **Raktár:** *61*
            - **Hely:** *02A01R1S1B*
            - **Azonosítótábla:** Válasszon ki egy meglévő azonosítótáblát a listából, vagy hozzon létre egy új azonosítótáblát.
            - **Mennyiség:** *1000*

        - **2. sor:**

            - **Cikkszám:** *A0001*
            - **Telephely:** *6*
            - **Raktár:** *61*
            - **Hely:** *07A01R2S1B*
            - **Azonosítótábla:** Válasszon ki egy meglévő azonosítótáblát a listából, vagy hozzon létre egy új azonosítótáblát.
            - **Mennyiség:** *15*

        - **3. sor:**

            - **Cikkszám:** *A0001*
            - **Telephely:** *6*
            - **Raktár:** *61*
            - **Hely:** *07A01R1S1B*
            - **Azonosítótábla:** Válasszon ki egy meglévő azonosítótáblát a listából, vagy hozzon létre egy új azonosítótáblát.
            - **Mennyiség:** *10*

    1. A Művelet panelen válassza ki az **Érvényesítés** lehetőséget. A következő lépéshez történő továbblépés előtt javítson minden talált hibát.
    1. A Művelet panelen válassza a **Feladás** parancsot a készletnek a raktárba történő feladásához.

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a>Mintaeset: Zónaalapú min/max feltöltés futtatása

Miután minden előfeltétel mintaadat a helyén van, a feltöltést a következő lépések végrehajtásával aktiválhatja.

1. Ugorjon a **Raktárkezelés \> Feltöltés \> Feltöltések** pontra.
1. A **Feltöltés** párbeszédpanelen, a **Szerepeltetni kívánt rekordok** gyorslapján válassza a **Szűrő** parancsot.
1. A **Lekérdezés** párbeszédpanelben, a **Tartomány** lapon a következő módon szerkessze a táblázat alapértelmezett sorát:

    - **Tábla:** Válassza a _Feltöltési sablonok_ lehetőséget.
    - **Származtatott tábla:** Válassza a _Feltöltési sablonok_ lehetőséget.
    - **Mező:** Válassza a _Feltöltési sablon_ lehetőséget.
    - **Feltételek:** Válassza ki a _Zóna min/max felt_ lehetőséget. Ez a feltöltési sablon az a feltöltési sablon, amelyet ehhez az esethez tartozó bemutatóadatok előkészítése során hozott létre.

1. Az **OK** gombra kattintva mentse a lekérdezést, és lépjen vissza a **Feltöltés** párbeszédpanelre.
1. A feltöltési sablon futtatásához kattintson az **OK** gombra.

A feltöltési munka most létrejön, hogy kitárolja a készletet az *ÖMLESZTETT* zónából, és feltölti az *EMELET* zónába.

## <a name="notes-and-tips"></a>Megjegyzések és tippek

Itt van néhány megjegyzés és tipp a funkció használatához:

- A kívánt zónához vezető feltöltési munka beállításához a feltöltési sablon sorait és a helyutasításokat a következő módokon lehet összekapcsolni:

    - Módosítsa a helyutasítás fejlécének lekérdezését, és szűrje a kiválasztott feltöltési sablon sorait.
    - Használjon egy utasításkódot a feltöltési sablon sorához, és egyeztesse az elhelyezési helyutasítással.

- Ha dinamikus helyeket használ, akkor a feltöltési munka jön létre vagy az első elérhető helyen vagy egy olyan helyen, amely már tartalmaz készletet, ha a helyutasítás művelet be van állítva a **Konszolidáció** stratégia használatára.
- Ha a zónák helyett fix helyeket használ, akkor a [szabvány min/max feltöltést](tasks/set-up-min-max-replenishment-process.md) kell használni.
