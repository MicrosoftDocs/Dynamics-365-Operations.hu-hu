---
title: Raktári időközökre bontás
description: Ez a témakör a raktári időközökre bontással kapcsolatban tartalmaz információkat. A raktári időközökre bontás lehetővé teszi a kereslet cikkek és mértékegységek szerinti konszolidációját a rendelésekből, amelyek Megrendelt, Lefoglalt vagy Kiadott állapottal rendelkeznek. A raktári kezelők számára intelligens módon segít kitárolási helyeket tervezni, mielőtt a rendeléseket a raktárba kiadnák, és kitárolási munkát hoznának létre.
author: mirzaab
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 92e0d2ef468a47579d21428009f1fd2dfcb8b0c19874d1a8d44e638f9f0a7c89
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738125"
---
# <a name="warehouse-slotting"></a>Raktári időközökre bontás

[!include [banner](../includes/banner.md)]

A számos raktári időközökre bontási funkció elérhető a kezelők számára, hogy intelligens módon segítsen kitárolási helyeket tervezni, mielőtt a rendeléseket a raktárba kiadnák, és kitárolási munkát hoznának létre.

A *Raktári időközökre bontási funkció* lehetővé teszi a kereslet cikkek és mértékegységek szerinti konszolidációját a rendelésekből, amelyek *Megrendelt*, *Lefoglalt* vagy *Kiadott* állapottal rendelkeznek. A létrejövő igény ezután alkalmazható a kitárolásra használt helyekre, mennyiség, egység, fizikai méretek, rögzített helyek és egyebek alapján. Az időközökre bontási terv létrehozását követően létrehozható a feltöltési munka, hogy a megfelelő mennyiségű készletet helyezze el minden helyen.

A *Raktári időközökre bontás átmozgatási rendelésekhez* funkció lehetővé teszi a raktári vezetőknek, hogy feltöltsék a kitárolási helyeket az olyan rendelések áthelyezése alapján, amelyeket még nem adtak ki a raktárnak. Ez biztosítja, hogy a kitárolási helyek tartalmazzák az áthelyezési rendelésekhez szükséges összes cikket, miután kiadták őket a raktárba. Ehhez a funkcióhoz be kell kapcsolnia a *Raktár időközökre bontás* funkciót is.

A *Raktári időközökre bontás felosztási fejlesztései* funkció lehetőséget ad a *Raktár időközökre bontási funkció* által használt sablonsorokhoz. Ez a beállítás lehetővé teszi a rendszer számára, hogy a célhelyen meglévő aktuális készletet vegye figyelembe. Ezért kevesebb feltöltés keletkezik az időközökre bontáshoz. A *Raktári időközökre bontás felosztási fejlesztései* funkcióhoz a *Raktár időközökre bontási funkciót* is be kell kapcsolnia. Opcionálisan használható a *Raktári időközökre bontás átmozgatási rendelésekhez* funkcióhoz.

## <a name="turn-on-the-warehouse-slotting-features"></a>A raktári időközökre bontási funkciók bekapcsolása

A funkciók használata előtt be kell azokat kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat ezen funkciók állapotának ellenőrzéséhez, és szükség esetén a bekapcsolásához. Szükség szerint kapcsolja be a következő szolgáltatásokat:

- Raktári időközökre bontási funkció
- Raktári időközökre bontás átmozgatási rendelésekhez

    > [!IMPORTANT]
    > A *Raktári időközökre bontás* funkciót be kell kapcsolni a funkció előtt.

- Raktári időközökre bontási felosztás fejlesztései

    > [!IMPORTANT]
    > A *Raktári időközökre bontás* funkciót be kell kapcsolni a funkció előtt.

## <a name="set-up-warehouse-slotting"></a>Raktári időközökre bontás beállítása

A raktári időközökre bontási használatához a következő elemeket kell beállítania a rendszerben:

- Időközökre bontás mértékegységszintjei
- Utasításkódok
- Időközökre bontási sablonok
- Helyutasítások

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a>Mértékegységszintek létrehozása az időközökre bontáshoz

A mértékegységszintek lehetővé teszik a különböző mértékegységek csoportosítását az időközökre bontás céljából. Ha például több dobozméret van kiválasztva ugyanarról a dobozkitárolási területről, akkor az összes mérethez létrehozható egy szint. **Minden mértékegységhez létre kell hozni egy sort, amely a szint része.**

1. Lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Mértékegységszintek időközökre bontása**.
1. Válassza az **Új** lehetőséget.
1. A fejlécben állítsa be a következő értékeket:

    - **Mértékegységszint:** *EaBoxPl*
    - **Leírás:** *Minden doboz raklap*

1. Válassza a **Mentés** lehetőséget.
1. A **Mértékegységek** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Egység:** *Doboz*
    - **Leírás:** Hagyja üresen ezt a mezőt. A módosítások mentésekor a program automatikusan kitölti ezt a mezőt.
    - **Egységosztály:** *Mennyiség*

1. Válassza az **Új** lehetőséget egy második sor rácshoz való hozzáadásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Egység:** *ea*
    - **Leírás:** Hagyja üresen ezt a mezőt. A módosítások mentésekor a program automatikusan kitölti ezt a mezőt.
    - **Egységosztály:** *Mennyiség*

1. Válassza az **Új** lehetőséget egy harmadik sor rácshoz való hozzáadásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Egység:** *PL*
    - **Leírás:** Hagyja üresen ezt a mezőt. A módosítások mentésekor a program automatikusan kitölti ezt a mezőt.
    - **Egységosztály:** *Mennyiség*

1. A szint mentéséhez válassza a **Mentés** parancsot.

### <a name="create-a-directive-code-for-slotting"></a>Utasításkód létrehozása az időközökre bontáshoz

Ki kell választania a sablonhoz társítani kívánt utasításkódot.

1. Ugrás a **Raktárkezelés \> Beállítás \> Utasítskódok** elemre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **irányelv kódja** mezőbe írja be az *Időközökre bontás* értéket.
1. Az **Utasítás leírása** mezőbe írja be az *Időközökre bontás* értéket.

### <a name="set-up-slotting-templates"></a>Időközökre bontás sablonok beállítása

Minden időközökre bontási sablon azt vezérli, hogy a készlet milyen módon van hozzárendelve egy adott raktár helyeihez. Minden sablonnak tartalmaznia kell egy sort mindegyik időközökre bontási specifikációból. Az ebben a szakaszban található eljárások segítségével lehet beállítani az időközökre bontási sablonokat.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Feltöltés \> Időközökre bontási sablonok** pontra.
1. Válassza az **Új** lehetőséget egy sablon létrehozásához.

Ezután be kell állítania a sablon fejlécét, az időközökre bontási specifikációkat és a helyutasításokat, ahogyan azt a következő alszakaszok részletezik. Az időközökre bontás átmozgatási rendelésekhez beállítása hasonlít az időközökre bontás értékesítési rendelések beállításaihoz, de a **Kereslet típusa** mező az *Értékesítési rendelés* helyett az *Átmozgatási rendelések* értékre van beállítva.

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a>Értékesítési rendelés időközökre bontási sablon fejlécének beállítása

1. A sablon fejlécében adja meg a következő értékeket:

    - **Időközökre bontási sablon** _61_
    - **Leírás:** _61_
    - **Kereslet típusa:** *Értékesítési rendelés*

        > [!NOTE]
        > Jelenleg az *Értékesítési rendelések* és az *Átmozgatási rendelések* az egyetlen támogatott kereslettípusok. Csak akkor választhatja az *Átmozgatási rendeléseket,* ha az *Raktári időközökre bontás átmozgatási rendelésekhez* funkció be van kapcsolva.

    - **Kereslet stratégia:** _Megrendelve_

        A következő értékek állnak rendelkezésre ebben a mezőben:

        - **Megrendelt** – Az értékesítési rendelés teljes megrendelt mennyiségét keresletnek kell tekinteni.
        - **Lefoglalva** – Csak az értékesítési rendelés sor lefoglalt (tényleges és rendelt) mennyiségét kell figyelembe venni.
        - **Kiadott** – A kiadott mennyiséget keresletnek kell tekinteni.

    - **Raktár:** _61_
    - **A hullám keresletének engedélyezése nem foglalt mennyiségek használatához:** _Igen_

Megadhat egy lekérdezést is a kiértékelt kereslet hatókörének leszűkítéséhez.

#### <a name="set-up-slotting-specifications-for-each-template"></a>Időközökre bontási specifikációk beállítása ez egyes sablontípusokhoz

Minden értékesítési rendelési sablon esetében hajtsa végre az alábbi lépéseket egy sor hozzáadásához az egyes időközökre bontási specifikációkhoz.

1. Az **Időközökre bontási részletek** gyorslapján válassza az **Új** parancsot, és hozzon létre egy sablonfájlt.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorozat:** _1_
    - **Leírás:** _Rögzített hely_
    - **Minimális mennyiség:** _1_

        Ez a mező azt a minimális keresleti mennyiséget határozza meg, amely a sorhoz szükséges.

    - **Maximális mennyiség:** _1000000_

        Ez a mező azt a maximális keresleti mennyiséget határozza meg, amely a sorhoz érvényes.

    - **Egység:** Ezt a mezőt hagyja üresen.

        Ez a mező azt a mértékegységet határozza meg, amelyre a minimális és maximális mennyiségek utalnak.

    - **Mértékegységszint:** _EaBoxPl_

        Ez a mező azt a keresleti mértékegységet határozza meg, amely a sorhoz érvényes. (További információt a [Mértékegységszintek beállítása időközökre bontáshoz](#unit-tiers) című részben talál, a téma korábbi részében.)

    - **Időköz-hozzárendelési feltétel társítása:** _Figyelembe vett mennyiség_

        A következő értékek állnak rendelkezésre ebben a mezőben:

        - **Üresen hagyott** – Ez a rendszer feltételezi, hogy a kitárolási terület minden helye üres, és a készlethez tartozó helyeket nem szabad ellenőrizni.
        - **Figyelembe vett mennyiség** – Ennek a rendszernek ellenőriznie kell a helyeket a készlet kitárolási területein, és ki kell hagynia minden nem üres helyet.
        - **Aktuálisan készleten lévők figyelembe vétele** – A rendszernek ellenőriznie kell, hogy a célhely tartalmaz-e nem foglalt mennyiségeket a kereslet sorban szereplő cikkhez. Ha a mennyiség elég nagy ahhoz, hogy a kereslet sor legalább egy egységét kielégítsen, akkor a létrehozott időközökre bontási terv rekord az elérhető mennyiséggel csökken. Ha például a kereslet 10 eset, és egy eset kéznél van, a megtalált kereslet kilenc eset lesz. Ha a kereslet 10 eset, és mindegyik eset kéznél van, a megtalált kereslet 10 eset lesz. Ez az érték csak akkor érhető el , ha be van kapcsolva a *Raktári időközökre bontás felosztási fejlesztései* funkció.

    - **Irányelv kódja:** _Időközökre bontási_

        Ez a mező határozza meg a feltöltési munka kitárolási helyének megtalálásához használt helyutasítást.

    - **Túlcsordulási hely:** Hagyja üresen ezt a mezőt.

        Ez a mező azt a helyet határozza meg, ahová a készletet elhelyezik, ha a sor feldolgozásakor nem található hely a mennyiséghez.

    - **Felengedés engedélyezése:** _Igen_

        Ha ez a beállítás *Igen* értékre van állítva, akkor ha a kereslet nem bontható időközökre, létrejön munka a készlet felvételéhez olyan készlettel rendelkező helyekről, ahol nincs időközökre bontás. Ezután a sablon újra futni fog. Ez alkalommal figyelmen kívül hagyja a készletet a helyeken. Ez a funkció a legjobban akkor működik, ha a **Időköz-hozzárendelési feltétel társítása** mező _Figyelembe vett mennyiség_ értékkel van megadva.

    - **Rögzített hely használata:** _Csak a termék rögzített helyei_

        A következő értékek állnak rendelkezésre ebben a mezőben:

        - **Rögzített és nem rögzített helyek** – A rendszer nem korlátozható csak a rögzített helyek használatára.
        - **Csak a termék rögzített helyei** – A rendszer csak a termék rögzített helyeit tartalmazó tárolóhelyeket rögzít.
        - **Csak a termékváltozat rögzített helyei** – A rendszer csak a termékváltozat rögzített helyeit tartalmazó tárolóhelyeket rögzít.

> [!NOTE]
> Ha az időközökre bontás sablon legalább egy olyan sort tartalmaz, ahol az **Időköz-hozzárendelési feltétel társítása** mező az *Aktuálisan készleten lévők figyelembe vétele* beállításra van állítva, akkor a sablon egyetlen sorához sem engedélyezettek a beállítások.

1. Válassza a **Mentés** lehetőséget.
1. Ha második sablonsort szeretne létrehozni, kattintson az **Új** elemre.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorozat:** _2_
    - **Leírás:** _Egyéb_
    - **Minimális mennyiség:** _1_
    - **Maximális mennyiség:** _1000000_
    - **Egység:** Ezt a mezőt hagyja üresen.
    - **Mértékegységszint:** _EaBoxPl_
    - **Időköz-hozzárendelési feltétel társítása:** _Figyelembe vett mennyiség_
    - **Irányelv kódja:** _Időközökre bontási_
    - **Túlcsordulási hely:** Hagyja üresen ezt a mezőt.
    - **Felengedés engedélyezése:** _Igen_
    - **Rögzített helyek használata:** _Rögzített és nem rögzített helyek_

    A második sor lekérdezésében megadhatja azokat a feltételeket, amelyekkel meghatározhatja, hogy milyen helyeken lehet az adott sor igénye időközökre bontható.

1. Válassza ki azt a sort, amelynél a **Sorozat** mező értéke *2*.
1. Válassza ki a **Lekérdezés szerkesztése** lehetőséget.
1. A **Tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Tábla:** *Helyek*
    - **Származtatott tábla:** *Helyek*
    - **Mező:** *Hely profilazonosítója*
    - **Feltételek:** *Kitárolás-06* (Válassza ki a dupla plusz jelet \[**++**\] a mezőben a lista kibontásához, majd válassza a *Kitárolás-06* - *6. kitárolási hely* elemet.)

1. Válassza ki az **OK** lehetőséget.

#### <a name="set-up-location-directives"></a>Helyutasítások beállítása

A kitárolások időközökre bontásának támogatásához be kell állítani legalább egy helyutasítást. Az ebben a szakaszban található eljárások segítségével beállíthatja a kitárolások időközökre bontásának új *feltöltési helyutasítását*.

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A bal oldali ablaktáblában állítsa a **Munkarendelés típusa** mezőt a *Feltöltés* értékre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új helyutasítás fejlécében, a **Név** mezőbe írja be a *61 kitárolás időközökre bontása* értéket.
1. A **Sorszám** mezőben fogadja el az alapértelmezett értéket.

##### <a name="configure-the-location-directives-fasttab"></a>Konfigurálja a Helyutasítások gyorslapot

1. A **Helyutasítások** gyorslapon állítsa be a következő értékeket. Az összes többi mezőben hagyja meg az alapértelmezett értéket.

    - **Munka típusa:** _Kitárolás_
    - **Telephely:** _6_
    - **Raktár:** _61_
    - **Irányelv kódja:** _Időközökre bontási_

1. A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap.

##### <a name="configure-the-lines-fasttab"></a>A Sorok gyorslap konfigurálása

1. A **Sorok** gyorslapon kattintson az **Új** lehetőségre egy sor létrehozásához.
1. Az új sorban állítsa be a következő értékeket.

    - **Kezdő mennyiség:** _0_
    - **Záró mennyiség:** _1000000_

1. Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.
1. A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap.

##### <a name="configure-the-location-directive-actions-fasttab"></a>Konfigurálja a Helyutasítási műveletek gyorslapot

1. A **Helyutasítási műveletek** gyorslapon kattintson az **Új** lehetőségre egy sor létrehozásához.
1. Az új sorban állítsa be a következő értékeket. Az összes többi mezőben hagyja meg az alapértelmezett értéket.

    - **Sorszám:** Fogadja el az alapértelmezett értéket.
    - **Név:** _Ömlesztett_
    - **Stratégia:** _Nincs_

1. Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.
1. Válassza a **Mentés** lehetőséget, ha elérhetővé szeretné tenni a **Lekérdezés szerkesztése** gombot.

##### <a name="edit-the-query"></a>A lekérdezés szerkesztése

1. A **Helyutasítás műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A **Tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Tábla:** *Helyek*
    - **Származtatott tábla:** *Helyek*
    - **Mező:** *Zóna azonosítója*
    - **Feltételek:** *Ömlesztett* (Válassza ki a dupla plusz jelet \[**++**\] a mezőben a lista kibontásához, majd válassza az *Ömlesztett* kitárolási hely elemet.)

1. Válassza ki az **OK** lehetőséget.

## <a name="scenario"></a>Forgatókönyv

### <a name="set-up-the-scenario"></a>Forgatókönyv beállítása

Ehhez a forgatókönyvhöz használja a beépített mintaadatokat, és hozza létre a szakaszban ismertetett rekordokat.

#### <a name="use-the-usmf-sample-data"></a>A USMF mintaadatok használata

Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

#### <a name="create-demand"></a>Igény létrehozása

Hajtsa végre az alábbi lépéseket, és hozza létre azt az igényt, amelyre alkalmazni fogja az időközökre bontást.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőben válassza ki azt az _US-007_ értéket.
1. A **Raktár** mezőben válassza ki az _61_ értéket.
1. Válassza ki az **OK** lehetőséget.
1. A program megnyitja az új értékesítési rendelést. Tartalmaz egy üres sort az **Értékesítési rendelés sorai** gyorslapon. Ezen a soron állítsa be a következő értékeket:

    - **Cikk:** _L0101_
    - **Mennyiség:** _20_

1. Válassza ki a **Sor hozzáadása** lehetőséget egy új sor hozzáadásához, és állítsa be a következő értékeket:

    - **Cikk:** _T0100_
    - **Mennyiség:** _8_

1. Válassza a **Mentés** lehetőséget.
1. Második értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőben válassza ki azt az _US-008_ értéket.
1. A **Raktár** mezőben válassza ki az _61_ értéket.
1. A program megnyitja az új értékesítési rendelést. Tartalmaz egy üres sort az **Értékesítési rendelés sorai** gyorslapon. Ezen a soron állítsa be a következő értékeket:

    - **Cikk:** _T0100_
    - **Mennyiség:** _1_

1. Válassza a **Mentés** lehetőséget.

### <a name="walk-through-a-typical-slotting-scenario"></a>Haladjon végig egy tipikus időközökre bontási forgatókönyvön

Miután az összes előfeltétel-elem a helyén van, ahogy azt az előző részben ismertették, készen áll a funkció kipróbálására a jelen szakasz minden egyes gyakorlatán keresztül.

#### <a name="generate-demand"></a>Igény létrehozása

1. Lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Időközökre bontási sablonok** pontra, és válassza ki a korábban létrehozott időközökre bontási sablont.
1. A Művelet ablaktáblán válassza ki a **Kereslet generálása** elemet. Ez a parancs a rendszerben található összes igényt kiértékeli, és megfelel az időközökre bontási sablon lekérdezésének. A program ezután összesíti az összes rendelésen szereplő teljes igényt, egy sorban/mértékegységben. A folyamat befejezésekor egy tájékoztató üzenet jelenik meg.

#### <a name="slotting-demand"></a>Időközökre bontás igénye

Az *időközökre bontási igény* a keresletgenerálás eredményét jeleníti meg az időközökre bontási sablon beállítása alapján.

- A Művelet panelen válassza az **Időközökre bontási igény** elemet a **Keresletgenerálás** parancsból származó eredmények megtekintéséhez. Az időközökre bontási igény sorai szerkeszthetők. Lehetőség van egy sor törlésére, új sor hozzáadására vagy a sor részletes adatainak szerkesztésére.

> [!NOTE]
> A kereslet manuálisan is szerkeszthető, illetve a külső rendszerből is importálhatja az adatkezelés segítségével. Bármi is szerepel az időközökre bontási igényben a következő lépésben, az kerül felhasználásra, függetlenül attól, hogy honnan érkezett.

#### <a name="locate-demand"></a>Igény megkeresése

Miután létrehozta a keresletet, az **Kereslet helyének megkeresése** paranccsal hozhat létre *időközökre bontási tervet*.

- A Művelet ablaktáblán válassza ki a **Kereslet helyének megkeresése** elemet. Az időközökre bontási folyamat fut. A folyamat befejezésekor egy tájékoztató üzenet jelenik meg.

#### <a name="slotting-plan"></a>Időközökre bontási terv

Az időközökre bontási terv azt a helyet jeleníti meg, amelyhez az egyes cikkek/mennyiségek hozzá vannak rendelve, hogy történt-e túlcsordulás, létrehozásra került-e felengedési munka, valamint a sablon felhasznált sorát. *Minden olyan igényt, amelyet nem lehet időközökre bontani, piros színnel van kijelölve.*

- Az eredmények megtekintéséhez válassza ki az **Időközökre bontási tervet** a Művelet ablaktáblán.

> [!NOTE]
> - A **Kereslet generálása**, a **Kereslet helyének megkeresése** és a **Feltöltés futtatása** mostantól egy tesztkörnyezetben fut. (Ezek a folyamatok a Művelet panelen érhetők el az **Időközökre bontási sablonok** oldalon.)
> - A **Kereslet generálása**, a **Kereslet helyének megkeresése**, és a **Feltöltés futtatása** zárolással rendelkezik, amely biztosítja, hogy nem lesznek egyszerre aktiválva. Ellenkező esetben a felhasznált adatok törrlődhetnek.
> - A **Kereslet generálása**, a **Kereslet helyének megkeresése** folyamatok figyelmeztetést jelenítenek meg, ha a futtatás nem hozott létre rekordokat, vagy ha a rekordokból hiányoznak az adatok.
> - Ha az **Időközökre bontási terv** lehetőséget választja, a lapon nem található **Új**, **Szerkesztés** vagy **Törlés** gomb a Művelet panelen, mert az adatforrás nem szerkeszthető.
> - Ha a **Feltöltés futtatása lehetőséget** választja, a rendszer ellenőrzi a kijelölt időközsablont és folyamatokat.

#### <a name="create-replenishment"></a>Feltöltés létrehozása

Miután létrehozta az időközökre bontási tervet, létre kell hoznia egy *feltöltési munkát* a terv alapján.

- A Műveleti ablaktáblán kattintson a **Feltöltés futtatása** elemre. A folyamat befejezésekor egy tájékoztató üzenet jelenik meg. Ez az üzenet a munka-összeállítási azonosítóhoz létrehozott fejlécek számát jelzi.

A rendszer az egyes sablonok sorában megadott utasításkód alapján határozza meg, hogy mely helyutasításokat kell használni.

## <a name="tips"></a>Tippek

### <a name="set-up-automatic-slotting"></a>Automatikus időközökre bontás beállítása

Miután minden szükséges elem be van állítva, beállíthatja, hogy az időközökre bontás automatikusan fusson a következő lépések követésével.

1. Ugorjon a **Raktárkezelés \> Feltöltés \> Időközökre bontás futtatása** pontra.
1. A futtatni kívánt időközökre bontási lépések megadása. Válasszon egy vagy több lépést a következő időközökre bontási lépések közül:

    - Igény létrehozása
    - Igény megkeresése
    - Feltöltési munka létrehozása

    > [!NOTE]
    > Az időközökre bontás lépései progresszívek. Ha ki szeretné választani a *Kereslet helyének megkeresése* elemet, először ki kell választania a *Kereslet generálása* lépést.

1. Adja meg a használni időközökre bontási sablont.
1. Ha kívánja, a program automatikusan futtatja az ismétlődést.

A forgatókönyv gyakorlataihoz **ne** állítson be automatikus időközökre bontást.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]