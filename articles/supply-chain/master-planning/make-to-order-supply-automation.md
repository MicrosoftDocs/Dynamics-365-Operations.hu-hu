---
title: Készítés rendelésre ellátás automatizálása
description: Ez a témakör leírja, hogyan lehet beállítani és használni a rendelésre való ellátásautomatizálási funkció által hozzáadott különféle fejlesztéseket.
author: t-benebo
ms.date: 07/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-27
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9044acb472548a797ed387b08ca6892459785793
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220749"
---
# <a name="make-to-order-supply-automation"></a>Készítés rendelésre ellátás automatizálása

[!include [banner](../includes/banner.md)]

A *rendelésre való ellátásautomatizálási* funkció több fejlesztést is tesz lehetővé a Microsoft számára Dynamics 365 Supply Chain Management. Ezek a fejlesztések lehetővé teszik a következő feladatok elvégzését:

- A felhasználó által megadott időszakra vonatkozó erőforrás-kapacitásterhelés megtekintése, és így a kapacitásterhelés hosszú távú értékelésének engedélyezése.
- Javítsa a rugalmasságot az egyes alaptervek késleltetési tűréshatárának (negatív napok) szabályozásával.
- Az utolsó rendelésekhez használható termékek elérhetővé tevéése és a meglévő készletek használatának optimalizálása a lehető legkésőbbi igény alapján, nem pedig az első lehetséges készlet alkalmazásával.
- A megingás után rugalmasan tarthatja a termelési rendelések összetevő-hozzárendelését, hogy a rendszer optimalizálja az utolsó percek igényváltozásait. Más szóval egy szintre korlátozza a jelölést.
- Az egyes értékesítési rendelések teljesítre vonatkozó kötvényének szabályozása. Az alapértelmezett beállítások a vevő beállításaiból állnak.
- A vállalatközi információk folyamatának javítása. A beszerzési rendelések frissülnek, hogy a szállítási mód, a szállítási feltételek és a külső cikkszám mezőit tartalmazzák. Ez a módosítás gondoskodik arról, hogy a részletes igényinformációk át tudjanakáramlást biztosítani a beszállító vállalathoz.

Ez a témakör ismerteti, hogyan lehet beállítani és használni az egyes fejlesztéseket.

> [!NOTE]
> Az ebben a cikkben ismertetett minden fejlesztés a beépített alaptervezést használt rendszerekre vonatkozik. A Microsoft tervezőoptimalizálási bővítménye a következő két továbbfejlesztést támogatja Dynamics 365 Supply Chain Management:
>
> - Alaptervek késleltetési tűréshatára
> - Az alaptervezés során használt pegging-sorrend ellenőrzése

## <a name="turn-on-the-make-to-order-supply-automation-feature"></a>A rendelésre való ellátásautomatizálási funkció bekapcsolása

A jelen cikkben ismertetett funkció használata előtt be kell kapcsolnia azt a rendszeren. A rendszergazdák a szolgáltatáskezelési munkaterületet [használhatja](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), ahol a szolgáltatás a következő módon van felsorolva:

- **Modul:** *Alaptervezés*
- **Funkciónév:** *Rendelésre hozás ellátási automatizálás*

## <a name="set-the-number-of-days-to-show-on-capacity-load-page"></a>A Kapacitásterhelés lapon megjelenő napok számának beállítása

A **Kapacitásterhelés** lapon áttekintheti egy erőforrás rendelkezésre álló kapacitását. A *rendelésre való ellátásautomatizálási* **funkció** a Napok száma mező felvételével javítja a **Kapacitásterhelés** lapot. Ezzel a mezővel korlátozhatja az Áttekintés rács által **látható** napok számát. A beállított értéket a program a memóriába menti. Ezért ha elhagyja a lapot, majd később visszatér, **az** Áttekintés rácsban továbbra is a legutóbb megadott napok száma látható.

A Kapacitásterhelés **lap** megnyitásához, amely egy adott erőforrás rendelkezésre álló kapacitásának áttekintésére használható, kövesse ezeket a lépéseket.

1. Ugrás a Szervezet felügyelete **– Erőforrások \> stb \>**.
1. Jelöljön ki egy megvizsgálni kívánt erőforrást.
1. A műveletpanel Erőforrás **lapján**, **a** Nézet csoportban válassza ki a Kapacitásterhelés **lehetőséget**.
1. A Napok **száma** szűrővel korlátozhatja **az Áttekintés rács által látható napok** számát.

A Kapacitásterhelés **lap** megnyitásához, hogy áttekinthető az erőforráscsoportok rendelkezésre álló kapacitása, kövesse ezeket a lépéseket.

1. Menjen a **Szervezet felügyelete \> Erőforrások \> Erőforráscsoportok** részhez.
1. Válassza ki a vizsgálni kívánt erőforráscsoportot.
1. A műveletpanel Erőforráscsoport **lapján**, **a** Nézet csoportban válassza **a Kapacitásterhelés lehetőséget**.
1. A Napok **száma** szűrővel korlátozhatja **az Áttekintés rács által látható napok** számát.

## <a name="apply-a-single-level-of-marking-when-you-firm-planned-orders"></a>Egyszintű jelölés alkalmazása a tervezett rendeléseknél

A *Jelölés* a kínálat és kereslet összekapcsolására szolgál. Ez hasonlít az *igénykövetés* műveletre, amely azt jelzi, hogy az alaptervezés hogyan tervezi a szükségletek lefedését. A jelölés azonban állandóbb, mint az pegging. A *rendelésre való ellátásautomatizálási* funkció lehetőséget ad a készletjelölés egyetlen szintre való korlátozására a tervezett rendeléseknél. A tervezett rendeléseknél **a** **következő** új beállításokat adja hozzá a Megingás párbeszédpanel Jelölés frissítése mezőjéhez:

- *Egyszintű szabvány* – egyszintű jelölést használ. Az egyszintű jelölés csak a fő cikket jelöli, az anyagjegyzék összetevőit nem. Ezért a megingás után rugalmasan lehet tartani a termelési rendelések összetevő-hozzárendelését. Az egyszintű jelölés segítségével optimalizálhatja a rendszer az utolsó percek igényváltozását. Az *egyszintű* normál jelölésnél a követelményrendelések a teljesítménnyel vannak megjelölve, de a teljesítménnyel kapcsolatos rendelések nem jelölve meg, ha maradt mennyiségük.
- *Egyszintű kiterjesztett* – egyszintű jelölést használ. A *kiterjesztett* egyszintű jelölésnél a követelményrendelések a teljesítménnyel, a teljesítménnyel kapcsolatos rendeléseket pedig mindig megjelölik, függetlenül attól, hogy marad-e mennyiség.

Ezek a lehetőségek **az** **·** **Alaptervezés** paraméterei lap Szokásos frissítés lapjának Frissítés jelölés mezőjében is elérhetők, **ahol a Meg lehet határozni a Meg lehet erősítő párbeszédpanel alapértelmezett** beállítását.

A további tudnivalókat lásd a [Készletjelölés tervezésoptimalizálással.](planning-optimization/marking.md)

## <a name="set-delay-tolerance-negative-days-at-the-master-plan-level"></a>Késleltetési tűréshatár (negatív napok) beállítása az alapterv szintjén

A *Rendelésre automatizálási* funkció lehetővé teszi az alapterv szintjén a késleltetett tűréshatár (negatív napok) konfigurálást. A beállítás cikkfedezeti és fedezeti csoportszinten is elérhető. Ha egynél több szinten vannak negatív napok hozzárendelve, a rendszer az alábbi hierarchiában határozza meg, hogy melyik beállítást használja:

- Ha az Alaptervek **lapon** negatív napok vannak beállítva, ez a beállítás felülbírálja a terv futtatásakor megadott összes többi negatív napbeállítást.
- Ha a Cikkfedezet **lapon** negatív napok vannak beállítva, ez a beállítás felülbírálja a fedezeti csoport beállítását.
- A Fedezetcsoportok lapon **beállított** negatív napok csak akkor érvényesek, ha egy adott cikkhez vagy alaptervhez nincsenek beállítva negatív napok.

Az alaptervek negatív napjainak beállítását a következő lépések szerint hajtsa végre.

1. Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.
1. Válasszon egy alaptervet a listaablakban, vagy hozzon létre egy újat.
1. Az időkorlátok napokban gyorsét **úgy állítsa a Negatív napok** beállítást, **hogy Igen**.*·*
1. A közeli mezőben adja meg a negatív napok számát.

A negatív napok használatával kapcsolatos további tudnivalókat lásd [: Késleltetési tűréshatár (negatív napok)](planning-optimization/delay-tolerance.md).

## <a name="control-the-pegging-sequence-used-during-master-planning"></a>Az alaptervezés során használt pegging sorrend vezérlése

Az alaptervezés az igénytervezési *sorrend* alapján határozza meg, hogy melyik készlet fogja fedezni az igényt. A *rendelésre való ellátásautomatizálási* funkció új Lehetőség használata a **lehető** legkésőbbi készlethez, így jobban szabályozhatja az automatizációs sorrendet. Az új lehetőséggel elérhetővé teszi a termékeket az utolsó rendelésekhez, és optimalizálhatja a meglévő készlet használatát azáltal, hogy a lehető legkésőbbi készletet igényként használja, és nem az első lehetséges készletet használja.

Az pegging sorrendet az alapterv, a cikkfedezet vagy a fedezeti csoport szintjén lehet beállítani. Ha egy helykeresési sorrend több szinten van beállítva, a rendszer a következő hierarchiára alkalmazza, hogy eldöntse, melyik beállítást használja:

- Ha az Alaptervek **lapon** be van állítva egy rögzített sorrend, a beállítás felülbírál minden más rögzített beállítást a terv futtatásakor.
- Ha a Cikkfedezet **lapon** be van állítva az alapértelmezett beállítás, az felülbírálja a fedezeti csoport beállítását.
- A Fedezeti csoportok **lapon** beállított beállítási sorrend csak akkor érvényes, ha egy adott cikkhez vagy alaptervhez nincsenek beállítva az pegging-sorrend beállításai.

A fedezeti csoport szintjén való beállításhoz kövesse az alábbi lépéseket.

1. Manjen az **Alaptervezés \> Beállítás \> Fedezet \> Fedezeti csoportok** menübe.
1. Válasszon ki egy csoportot a listaablakban, vagy hozzon létre egy újat.
1. Az Általános **gyors lap** **·** **·** **Rögzítési sorrend szakaszban használja az Aktuális készlet felhasználása és a legutóbbi készletmezők használata az rögzítési sorrend konfigurálása érdekében.** A szakasz későbbi táblázata bemutatja, hogy ezeknek a beállításoknak az egyesítve hogyan kell definiálni az pegging sorrendet.

A cikkfedezeti szinten való beállításhoz kövesse ezeket a lépéseket.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válasszon egy terméket a rácson, vagy hozzon létre egy újat.
1. A Munkaablak Terv lapján **válassza** a Cikkfedezet **lehetőséget**.
1. A **Cikkfedezet** lap sorokat biztosít, amelyek segítségével meghatározhatja a cikkre az egyes raktárakban érvényes fedezeti szabályokat. Válasszon ki egy meglévő sort a rácsban, vagy hozzon létre egy újat.
1. Az Általános **lapon** jelölje be az Értékkeresési **sorrend felülbírálása jelölőnégyzetet**.
1. Az aktuális **készlet felhasználása és** **a legújabb ellátási mezők** használata az adatkeresési sorrend konfigurálása érdekében A szakasz későbbi táblázata bemutatja, hogy ezeknek a beállításoknak az egyesítve hogyan kell definiálni az pegging sorrendet.

Az alábbi lépések szerint állíthatja be az alapterv szintjén való követést.

1. Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.
1. Válasszon egy alaptervet a listaablakban, vagy hozzon létre egy újat.
1. Az Általános **gyorsététen állítsa Igen beállításra** az Rögzítési sorrend **felülbírálása beállítást** *.*
1. Az aktuális **készlet felhasználása és** **a legújabb ellátási mezők** használata az adatkeresési sorrend konfigurálása érdekében A szakasz későbbi táblázata bemutatja, hogy ezeknek a beállításoknak az egyesítve hogyan kell definiálni az pegging sorrendet.

Az alábbi táblázat bemutatja, **·** **hogy** hogyan lehet kombinálni az Aktuális készlet használata és a Legutóbbi készlet használata beállítást az raktározási folyamat létrehozására.

| | A legújabb készlet használata = Igen | Legújabb készlet használata = Nem |
|---|---|---|
| **Aktuális készlet felhasználása minden** = *készlet előtt* | <ol><li>Aktuális készlet</li><li>Az igénydátumnak megfelelő meglévő készlet</li><li>Olyan meglévő készlet, amely nem felel meg az igény dátumának, de még mindig negatív napokon belül</li><li>Új ellátás létrehozása (tervezett rendelés)</li></ol> | <ol><li>Aktuális készlet</li><li>Az igénydátumnak megfelelő meglévő készlet</li><li>Olyan meglévő készlet, amely nem felel meg az igény dátumának, de még mindig negatív napokon belül</li><li>Új ellátás létrehozása (tervezett rendelés)</li></ol> |
| **Aktuális készlet felhasználása** = *a teljes készlet után* | <ol><li>Az igénydátumnak megfelelő meglévő készlet</li><li>Aktuális készlet</li><li>Olyan meglévő készlet, amely nem felel meg az igény dátumának, de még mindig negatív napokon belül</li><li>Új ellátás létrehozása (tervezett rendelés)</li></ol> | <ol><li>Az igénydátumnak megfelelő meglévő készlet</li><li>Olyan meglévő készlet, amely nem felel meg az igény dátumának, de még mindig negatív napokon belül</li><li>Aktuális készlet</li><li>Új ellátás létrehozása (tervezett rendelés)</li></ol> |

## <a name="review-and-set-the-fulfillment-policy-that-applies-to-each-sales-order"></a>Az egyes értékesítési rendelésekre vonatkozó teljesítő irányelvek áttekintése és beállítása

A teljesítő szabályok a teljes rendelési ár vagy mennyiség százalékos hányadát szértékelik, ezt kell ténylegesen lefoglalni ahhoz, hogy az értékesítési rendelést kiadja a raktárba. Beállíthatja a globális alapértelmezett teljesítási házirendet, és felülírhatja azt az egyes vevőkhöz. A *rendelésre való ellátásautomatizálási* funkció lehetővé teszi annak megtekintését, hogy milyen alapértelmezett irányelv vonatkozik valójában egy rendelésre, és szükség esetén rendelésspecifikus felülbírálást alkalmaz.

- Az értékesítési rendelések globális teljesít kapcsolatos kötvényének beállításához használja **\>\> a Kinnlevőségek beállítása – Kinnlevőségek paraméterei lehetőséget.** Ezután a Raktárkezelés **lapon** állítsa **be** az Értékesítési rendelés teljesítése irányelvmezőt az használni kívánt irányelv nevének. 
- Az értékesítési rendelések vevőspecifikus teljesítre vonatkozó irányelveinek beállítását **\> a Kinnlevőségek – Vevők \> – Minden vevőnél adja meg**. Ezután a Raktár **lapon** állítsa **be a Teljesítés** irányelv mezőben a használni kívánt irányelv nevét.

A következő lépések szerint lehet megtekinteni egy rendelésre vonatkozó alapértelmezett házirendet, és egy rendelésspecifikus felülbírálást alkalmazni.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Nyissa meg a vizsgálni vagy szerkeszteni kívánt értékesítési rendelést.
1. Válassza a Fejléc **nézetet**.
1. Szükség szerint **ellenőrizze** és szerkessze a Következő mezőket a Raktár gyorsgombra gombra ásva:

    - **Rendelés teljesítésére vonatkozó irányelv** – a kiválasztott rendelésre vonatkozó teljesítés irányelvének kiválasztása. Az alapértelmezett irányelv felül lesz bírálva. Az Alapértelmezett teljesítés **irányelv** mezőben látható alapértelmezett teljesítő irányelv alkalmazásával hagyja üresen ezt a mezőt.
    - **Alapértelmezett teljesítő irányelv** – ez a mező mutatja azt az alapértelmezett **teljesít teljesítő házirendet, amely akkor érvényes, ha a Rendelés** teljesítése irányelv mező üres. Ez a mező csak olvasható. Ha üres, nincs meghatározva vevőspecifikus vagy globális alapértelmezett teljesítés irányelv.

    Ha a Rendelési **teljesítés irányelv** mezője **és az Alapértelmezett teljesítés irányelv** mezője is üres, akkor nem vonatkozik a teljesítés irányelve. Előfordulhat azonban, hogy más korlátozások vannak érvényben, és előfordulhat, hogy az értékesítési rendelés kiadása előtt kötelező a foglalások vagy más feltételek teljesülni.

## <a name="set-the-delivery-mode-and-terms-on-individual-purchase-order-lines"></a>A szállítási mód és feltételek beállítása az egyes beszerzésirendelés-sorokhoz

Minden beszerzési rendelés tartalmazza **a rendelés** fejlécében **a Szállítási feltételek és a** Szállítási mód beállítást. A *rendelésre való ellátásautomatizálási* funkció hozzáadja ezeket a beállításokat minden egyes rendelési sorhoz. Ennek megfelelően megadhatja **a** szállítási feltételek és/vagy **a** szállítási mód értékének felülbírálásait bármelyik rendelési sorhoz, illetve az összes szükséges rendelési sorhoz. Olyan sorokhoz, amelyekben nincs megadva felülbírálás, a rendszer a fejlécben megadott értéket használja. Megadhatja, hogy a rendelés fejlécének egyik vagy mindkét mezőjének az értékét módosítva az összes sort is frissítse a rendszer.

A következő lépések szerint adhatja meg, hogy mi történjen, ha egy felhasználó módosítja a szállítási feltételeket és/**vagy** a **szállítási** mód értékét a rendelési fejlécben.

1. Nyissa meg a **Beszerzés és forrás \> Beállítás \> Beszerzés és forrás paraméterei** pontot.
1. Az Általános **lap** Alapértelmezett értékek és **paraméterek** **gyorslapján válassza a Rendeléssorok frissítése hivatkozást**.
1. Válasszon a **Következő** értékek közül a **Rendeléssorok** **frissítése** párbeszédpanel Szállítási feltételek frissítése és a Szállítási mód frissítése mezőben:

    - *Soha* – soha ne frissítse a rendeléssorokat a rendelésfejlécen megadott beállítások módosítása után.
    - *Mindig* – mindig frissítse az összes rendeléssort, ha módosulnak a rendelésfejlécben megadott beállítások.
    - *Kérdés* – ha a felhasználó a rendelésfejlécben módosítja az egyik vagy mindkét beállítást, akkor egy párbeszédpanelt nyit meg, amely rákérdez, hogy szeretné-e frissíteni az összes sort, hogy azok megegyeznek az egyik vagy mindkét beállítással.

A következő lépések szerint állíthatja be a szállítási adatokat a beszerzési rendelés fejlécében.

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Nyissa meg a szerkeszteni kívánt beszerzési rendelést.
1. Válassza a Fejléc **nézetet**.
1. A Szállítási **mód** és **·** **a** Szállítási feltételek mezőket szükség szerint állítsa be a Szállítás gyorsét stb.
1. A Beszerzés és forrás **paraméterei** lapon megadott beállításoktól függően előfordulhat, hogy a módosításokat alkalmazni szeretné-e minden rendeléssorra.

A következő lépések szerint állíthatja be a szállítási adatok felülbírálatát a beszerzésirendelés-sorokhoz.

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Nyissa meg a szerkeszteni kívánt beszerzési rendelést.
1. Válassza a Sorok **nézetet**.
1. Válassza ki **a szerkeszteni kívánt** sort a Beszerzési rendelés sorai gyors oldalon.
1. A Szállítás **lap** Sor részletei **gyorslapján** **állítsa be a Szállítási mód** és **a Szállítási feltételek mezők** kívánt beállítását. Törölje az egyik vagy mindkét mezőt a fejléc egyeztetési beállításainak alkalmazáséhez.

Vállalatközi **·** **rendelések** esetén a rendszer az egyes beszerzésirendelés-sorok Szállítási mód és Szállítási feltételek mezőjének értékeit szinkronizálja a beszerzési rendelés és annak kapcsolódó értékesítési rendelése között.

## <a name="sync-external-item-ids-and-descriptions-for-intercompany-orders"></a>Külső cikk-adatok és leírások szinkronizálása vállalatközi rendelésekhez

A vállalatközi rendelések esetén a rendelésre történő ellátásautomatizálási funkció lehetővé teszi a külső cikk-cikkek és a beszerzésirendelés-sorok szöveges leírásának szinkronizálását a kapcsolódó vállalatközi értékesítésirendelés-sorokkal *, függetlenül attól,* hogy a beszerzési rendelés közvetlen kiszállításra van-e kiszállításra. A funkció lehetőséget ad a vállalatközi beszerzési rendelés végső külső vevői számlájának megadására is. A rendszer ezt követően automatikusan a külső vevőrekordból veszi a külső cikk-cikk-adatokat és szöveges leírásokat a (belső) vállalatközi szállítórekord helyett.

A következő lépésekkel állíthat be vállalatközi szállítót a külső cikk- és cikknevek szinkronizálására a vállalatközi beszerzési rendelések és a kapcsolódó vállalatközi értékesítési rendelések között.

1. Ugrás a **Beszerzés és forrás \> Beszállítók \> Minden szállító** pontra.
1. Válassza ki a beállítani kívánt vállalatközi szállítót.
1. A műveletpanel Általános **lapján, a** Beállítás csoportban **válassza** a Vállalatközi lehetőséget **.**
1. **A Vállalatközi** **·** **\> lap Beszerzési rendelés lap Vállalatközi beszerzési rendelés – Vállalatközi** **értékesítési** rendelés szakaszában jelölje be a Külső cikkazonosító és cikknév jelölőnégyzetet.

A következő lépések szerint adhatja meg a vállalatközi beszerzési rendelések végső külső vevői számláját. A **Vevői számla** mező csak a vállalatközi beszerzési rendelésekre vonatkozik. Használatával megadhatja annak a vevőnek a számlaszámát, aki végül megkapja az árut. Ha ez a mező be van állítva, akkor a beszerzési rendelés sorai a megadott vevői számlára vonatkozó külső cikkleírásokat és -számokat veszik át, nem pedig a beszerzési rendelésen megadott vállalatközi szállítót. Ha később módosítja a vevői számlát, a rendszer frissíti a külső cikkleírásokat és -értékeket, hogy azok megegyeznek az új számla értékeivel. A rendszer az egyes sorok külső cikkleírását és -forgalmi adóját is szinkronizálja az egyező vállalatközi értékesítési rendeléssel.

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Nyissa meg a beállítani kívánt beszerzési rendelést, vagy hozzon létre egy újat.
1. Válassza a Fejléc **nézetet**.
1. A Hivatkozás **szakaszban** állítsa be **a** Vevő számla mezőjét a megfelelő külső vevői számlára.

A következő lépések szerint adhatja meg a vállalatközi rendelések beszerzési rendelési sorában a külső cikk-értékeket és szöveges leírásokat. A beállított értékeket a rendszer szinkronizálja a kapcsolódó vállalatközi értékesítésirendelés-sorokkal, függetlenül attól, hogy a beszerzési rendelés közvetlen kiszállításra van-e kiszállításra.

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Nyissa meg a beállítani kívánt beszerzési rendelést, vagy hozzon létre egy újat.
1. Válassza a Sorok **nézetet**.
1. Válassza ki **a szerkeszteni kívánt** sort a Beszerzési rendelés sorai gyors oldalon.
1. A **Sor** **·** **·** **részletei** gyorslap Általános lapján, a Rendeléssor szakasz Szöveg mezőjében adja meg a kijelölt rendelési sorban megadott cikk külső leírását. Ez az érték szinkronizálva lesz a kapcsolódó vállalatközi értékesítésirendelés-s sortal.
1. A Külső **mező** Hivatkozás **szakaszában** adjon meg egy külső cikkazonosítót a kiválasztott rendelési sorban megadott cikkhez. Ez az érték szinkronizálva lesz a kapcsolódó vállalatközi értékesítésirendelés-s sortal.

A további tudnivalókat [lásd vállalatközi értékesítési rendelés létrehozása és számlázása külső vevő számára](../sales-marketing/intercompany-sales-order-for-external-customer.md).
