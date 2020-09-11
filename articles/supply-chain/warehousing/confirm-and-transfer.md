---
title: Megerősítés és áthelyezés
description: Ez a témakör azt mutatja be, hogyan kell használni a Megerősítés és áthelyezés funkciót, amely lehetővé teszi a felhasználók számára a rakományok szállítását, mielőtt elvégzik a rakományhoz társított összes munkát.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate,WHSWorkTemplateTable,WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6104e457a62f340951c187d0f2dbe48b0dffdf7f
ms.sourcegitcommit: d25d0feb3f8a5a760eba50ba5f46e1db02737d25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/10/2020
ms.locfileid: "3677410"
---
# <a name="confirm-and-transfer"></a>Megerősítés és áthelyezés

[!include [banner](../includes/banner.md)]

A *Megerősítés és áthelyezés* funkció lehetővé teszi a felhasználók számára a rakományok szállítását, mielőtt elvégzik a rakományhoz társított összes munkát. Amikor olyan szállítmány érkezik, amely nem teljes egészében átvett rakománysorokat tartalmaz, a visszaigazoló felhasználó számára a program az javasolja, hogy a fennmaradó mennyiségeket egy új rakományra ossza fel vagy érvénytelenítse a nem teljes mennyiségeket.

Azokat a rendszereket, amelyekben rakományfelosztás-támogatási forgatókönyvek beállíthatók, a tervezett és a részlegesen betöltött rakományokat módosítani kell az új vagy változó körülmények miatt.

Az ügyfél olyan logikát tartalmaz, amely lehetővé teszi a részlegesen betöltött rakomány lezárását és visszaigazolását szállítottként. A program ezután átmásolja a fennmaradó szállítmányokat és rakománysorokat (a teljes és a részleges mennyiségeket is), és továbbviszi az újonnan létrehozott rakományba és szállítmányba, ha ez a továbbadás szükséges, és a beállítás lehetővé teszi. A program automatikusan létrehozza az új szállítmányokat és rakományokat a szállítás és a rakomány létrehozásának kezdeti feltételei alapján, a fő attribútumok pedig változatlanok maradnak. Lehetőség van arra is, hogy a fennmaradó mennyiségeket automatikusan érvénytelenítse, ha egy munkarendelést még nem hoztak létre, és a felhasználó ezt az érvénytelenítést szükségesnek tartja.

Ez a funkció olyan eseteket támogat, amikor a teljes rakomány nem fér fel egyetlen teherautóra, vagy a rakomány egy része előbb elhagyja a raktárat, mint a többi része. Ezekben az esetekben a fennmaradó termékeket át lehet vinni egy új rakományba, és így egy új teherautóra. Mivel ez a funkció olyan rakományokhoz is használható, amelyek nem igényelnek teljes rakományú szállítmányt, a szállítmányozók rendkívül rugalmasan tudják megoldani a nem szabványos vagy előre nem látható eseteket.

A rakományok megosztásakor a *Megerősítés és áthelyezés* funkció a következő műveleteket hajtja végre:

- Szükség szerint új rakományok és szállítmányok jönnek létre. Minden rakományhoz vagy szállítmányhoz ugyanazok a tulajdonságok tartoznak, mint az eredeti rakományhoz vagy szállítmányhoz. A kivétel az a rakományállapot, amely a munka állapota alapján lesz újraszámolva.
- A felhasználó értesítést kap arról, hogy új rakomány jött létre. A felhasználó az új rakomány azonosítójáról is értesül.
- A program az új rakományok és szállítmányok adataival frissíti a megosztott rakománysorokat, munkafejléceket és munkasorokat.
- Ha egy teljes szállítmány fel van osztva, akkor a program megtartja a szállítmányt, és csak a rakomány hivatkozásait frissíti. Ha a szállítmányt fel kell osztani, akkor létrejön egy új szállítmány.

Ha a fennmaradó mennyiségeket érvénytelenítik, akkor a nem kiválasztott rakománysor-mennyiségeket és azokat, amelyekhez nincs nem érvényelített munka hozzárendelve, a program eltávolítja a rakományból. Ha bármilyen munka folyamatban van, a felhasználó csak a rakományt tudja felosztani. A fennmaradó mennyiségek nem vonhatók vissza.

Csak olyan rakományok oszthatók fel, amelyek megfelelnek az összes következő feltételnek:

- Egy vagy több rakománysor már kitárolt mennyiséget tartalmaz.
- A rakomány állapota kisebb, mint a betöltött.
- Nincs rakománysoradat. (Ez az adat az azonosítótábla-konszolidáción keresztül jön létre az előkészítési helyen, és a *Megerősítés és áthelyezés* funkció nem támogatja az azonosítótábla-konszolidációt.)
- Jelenleg nem vár készlet csomagolásra a csomagolás helyén. (A *Megerősítés és áthelyezés* funkció nem támogatja azt a készletet, amely már ki van adva a csomagolási állomásnak, de még nincs bepakolva.)

> [!NOTE]
> Ez a funkció eltér a szállítási raktárfunkciótól, amelyet olyan raktárakban kell használni, amelyek nem tervezhetnek és nem hozhatnak létre rakományokat a kitárolás előtt, de a kitárolás után betölti a rendelkezésre álló szállítási helyet.
>
> A *Megerősítés és áthelyezés* funkció olyan helyzetekben használható, amikor a rakományt általában előre megtervezik és létrehozzák, de ha kivételek történnek, amikor a rakomány nem fér el a rendelkezésre álló szállítóeszközben (például teherautóban).

## <a name="turn-on-confirm-and-transfer"></a>A megerősítés és áthelyezés bekapcsolása

A *Megerősítés és áthelyezés* funkciót használata előtt be kell kapcsolni a rendszerben. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Megerősítés és áthelyezés*

## <a name="set-up-confirm-and-transfer"></a>A megerősítés és áthelyezés beállítása

A *Megerősítés és áthelyezés* funkció használatához be kell kapcsolnia azt minden megfelelő rakománysablonban. Ezenkívül az igényektől függően előfordulhat, hogy a munkasablonok előkészítésére is szükség van a funkció támogatásához. Ha szeretne végighaladni a jelen témakörben később megadott példákon, állítsa be a rendszert az ebben a szakaszban ismertetett módon. (Ez a forgatókönyv az **USMF** bemutatóadatokon alapul.)

### <a name="prepare-your-load-templates"></a>A rakomány sablonjainak előkészítése

1. Ugorjon a **Raktárkezelés \> Beállítás \> Rakomány \> Rakománysablonok** elemre.
1. A műveleti ablaktáblán válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.
1. Jelölje be a **Rakománymegosztás engedélyezése a szállítás jóváhagyása közben** jelölőnégyzetet minden olyan meglévő sablonhoz, amelyhez be kívánja kapcsolni a szolgáltatást. Azt is megteheti, hogy az **Új** elemre kattintva új sablont hoz létre, és a szükséges módon konfigurálja. Minden, az adott sablon alapján létrehozott rakomány örökölni fogja ezt a funkciót. (Ha az **USMF** bemutatóadatokkal dolgozik, kapcsolja be a funkciót a **20 lábas konténer** rakománysablonhoz.)

### <a name="prepare-your-work-templates"></a>Munkasablonok előkészítése

Ez a beállítás nem szükséges minden helyzetben. Az itt megjelenített példa lehetővé teszi a munka megszakítását a szállítással annak érdekében, hogy támogassa a jelen témakörben később megadott példaforgatókönyvet. Más lehetőségek is vannak az eredmény elérésére.

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A lap felső részén található rácsban válasszon ki egy olyan meglévő munkasablont, amelynél be szeretné állítani a *Megerősítés és áthelyezés* funkciót. (Ha az **USMF** bemutatóadatokkal dolgozik, válassza ki a **51 kitárolás szakaszhoz** munkasablont.) Másik lehetőségként hozzon létre egy új munkasablont.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget az **Értékesítés** párbeszédpanel megnyitásához.
1. Az **Értékesítés** párbeszédpanelen, a **Rendezés** lapon válassza ki a **Hozzáadás** gombot, hogy hozzáadjon egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Tábla:** *Ideiglenes munkatranzakciók*
    - **Származtatott tábla:** *Ideiglenes munkatranzakciók*
    - **Mező:** *Szállítmány azonosítója*
    - **Keresés iránya:** *Növekvő*

1. Az **OK** gombra kattintva mentse a beállításokat, és zárja be az **Értékesítés** párbeszédpanelt.
1. Ha egy üzenet jelenik meg, amely jelzi, hogy a csoportosítás alaphelyzetbe kerül, válassza az **Igen** lehetőséget a folytatáshoz.
1. A **Munkasablonok** lap felső részén található rácson jelölje ki az imént szerkesztett sablont, majd a műveleti ablaktáblán válassza ki a **Munkafejléc-töréseket**.
1. A műveleti ablaktáblán válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.
1. A rácson állítsa be a következő értékeket:

    - **Tábla neve:** *Ideiglenes munkatranzakciók*
    - **Mező neve:** *Szállítmány azonosítója*
    - **Csoportosítás a mező szerint:** Jelölje be ezt a jelölőnégyzetet.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Zárja be a lapot.

## <a name="scenario"></a>Forgatókönyv

Ez a forgatókönyv olyan példát szemléltet, amelynél még nem fejeződött be a kitárolási folyamat, de a már kitárolt cikkeket fel kell rakodni egy teherautóra, és le kell szállítani. Emiatt a felhasználó a ki nem tárolt rakomány sorait egy új rakományra osztja fel. A program automatikusan frissíti az összes adatkapcsolatot.

> [!NOTE]
> Az ebben a helyzetben ismertetett konkrét értékek az **USMF** bemutatóadatokon alapulnak. Javasoljuk, hogy ezeket a bemutatóadatokat akkor használja, amikor bemutatja vagy tanulja a funkció használatát. Ha nem használja az **USMF** bemutatóadatokat, akkor a saját értékeit a szükséges módon kell helyettesítenie.

### <a name="step-1-create-a-load-that-has-multiple-load-lines"></a>1. lépés: Több rakománysorral rendelkező rakomány létrehozása

Ez a funkció csak akkor használható, ha van olyan rakomány, amely több rakománysort tartalmaz. Arról is meg kell győződnie, hogy a kitárolási helyek elegendő készlettel rendelkeznek az értékelési rendelésekben található minden cikkhez, amelyet Ön létrehoz. Tekintse át a helyutasítás beállítását (**Raktárkezelés \> Beállítás \> Helyutasítások**), és jegyezze fel az értékesítési rendelés kitárolásához használt kitárolási helyeket. Ha módosítania kell a készletet, akkor hozzon létre manuális mozgásokat, használja a feltöltést vagy szükség szerint bármilyen egyéb folyamatot.

Minősítő rakomány létrehozásához először három értékesítési rendelést kell létrehoznia a következő lépések végrehajtásával:.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A műveleti ablaktáblán kattintson az **Új** gombra az **Értékesítési rendelés létrehozása** párbeszédpanel megnyitásához.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket (minimum):

    - A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-004* (*Cave Wholesales*) értékhez.
    - Az **Általános** gyorslap **Raktár** mezőjében állítsa be az *51* értéket.

1. Válassza az **OK** gombot az új beszerzési rendelés létrehozásához és az **Értékesítési rendelés létrehozása** párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Az **Értékesítésirendelés-sorok** rácshoz adjon hozzá egy sort, amely a következő értékeket tartalmazza:

    - **Cikkszám:** *M9200*
    - **Mennyiség:** *40*
    - **Egység:** *ea*

1. A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.
1. A műveleti ablaktáblán válassza ki az **Adag foglalása** lehetőséget a **Foglalás** oldal megnyitásához.
1. Foglaljon le egy készletet az értékesítési sorban, majd zárja be a **Foglalás** lapot.
1. Ismételje meg az 1–4. lépést az ugyanazon vevőhöz és raktárhoz tartozó második értékesítési rendelés hozzáadásához.
1. Adjon hozzá két értékesítési sort a következő értékekkel. Miután hozzáadta az egyes sorokat, foglalja le a készletet a 6–8. lépésben leírtak szerint.

    - **1. sor:** Állítsa be a **Cikkszám** mezőt *M9200* értékre, a **Mennyiség** mezőt *30* értékre és az **Egység** mezőt *ea* értékre.
    - **2. sor:** Állítsa be a **Cikkszám** mezőt *M9201* értékre, a **Mennyiség** mezőt *20* értékre és az **Egység** mezőt *ea* értékre.

1. Ismételje meg az 1–4. lépést az ugyanazon vevőhöz és raktárhoz tartozó harmadik értékesítési rendelés hozzáadásához.
1. Adjon hozzá két értékesítési sort a következő értékekkel. Miután hozzáadta az egyes sorokat, foglalja le a készletet a 6–8. lépésben leírtak szerint.

    - **1. sor:** Állítsa be a **Cikkszám** mezőt *M9201* értékre, a **Mennyiség** mezőt *20* értékre és az **Egység** mezőt *ea* értékre.
    - **2. sor:** Állítsa be a **Cikkszám** mezőt *M9202* értékre, a **Mennyiség** mezőt *60* értékre és az **Egység** mezőt *ea* értékre.

#### <a name="load-planning-workbench"></a>Rakománytervező munkaterület

A rakománytervezési munkaterület a rakománysablon azonosítója alapján fogja összeállítani a szállítmányokat és kiadni az értékesítésirendelés-sorokat a raktárnak.

1. Ugorjon a **Raktárkezelés \> Rakományok \> Rakománytervező munkaterület** elemre.
1. A **Raktár** mezőben válassza ki az *51* értéket.

    Most összeállítja a rakományt az újonnan létrehozott értékesítési rendelésekhez.

1. Az **Értékesítési sorok** lap rácsán válassza ki az új értékesítési rendelések értékesítési sorait.
1. A műveleti ablaktáblán a **Kínálat és kereslet** lapon, a **Hozzáadás** csoportban válassza az **Új rakományba** elemet.
1. A **Rakománysablon hozzárendelése** párbeszédpanelen, a **Rakománysablon azonosítója** mezőben válassza ki a *20 lábas konténer* értéket.
1. Válassza ki az **OK** lehetőséget.
1. A **Rakománytervezési munkaterület** oldal **Rakományok** szakaszának rácsában keresse meg az újonnan létrehozott azonosítót az *51-es* raktárhoz. Görgessen jobbra addig, amíg meg nem jelenik a **Rakománymegosztás engedélyezése a szállítás jóváhagyása közben** oszlop. A rakományhoz be kell jelölni a jelölőnégyzetet.
1. Jelölje ki a rakományt.
1. A rács fölötti **Kiadás** menüben válassza ki a **Kiadás raktárba** lehetőséget a munka létrehozásához.
1. A **Rakomány kiadása raktárnak** párbeszédpanelen ellenőrizze, hogy a **Belefoglalandó rekordok** gyorslap megjeleníti-e a rakomány azonosítóját.
1. Válassza ki az **OK** lehetőséget.

    Előfordulhat, hogy a „Művelet feldolgozása” üzenet jelenik meg, miközben a rendszer létrehozza a szállítmányokat és a munkát.

1. A **Rakománytervezési munkaterület** oldal **Rakományok** szakaszán a rakomány állapotának *Hullámba sorolva* értékűnek kell lennie. Válassza ki a rakományt, majd a rács fölötti **Kapcsolódó információ** menüben válassza ki a létrehozott szállítmány-azonosítók megjelenítéséhez a **Hullám részletei** elemet. Amikor végzett, zárja be a **Hullámok** oldalt.
1. A **Rakománytervezési munkaterület** oldal **Rakományok** szakaszában válassza ki a rakományt, majd a rács fölötti **Kapcsolódó információ** menüben válassza ki a **Munka részletes adatai** lehetőséget az értékesítési rendelésekhez létrehozott munka megtekintéséhez.
1. Jegyezze fel a létrehozott munkaazonosítókat. Előfordulhat, hogy a munkaazonosítóhoz társított értékesítési rendelés számának és szállítási azonosítójának megtekintéséhez jobbra kell görgetnie.

### <a name="step-2-set-up-the-execution-flow-for-mobile-devices"></a>2. lépés: Mobileszközre szánt eszközök végrehajtási folyamatának beállítása

A mobileszközhöz kapcsolódó feladatokhoz felhasználói adatok szükségesek, például a munkaazonosító vagy az azonosítótábla azonosítója. A mezőkben ez az információ általában a dokumentációban, csomagoláson vagy állványon található vonalkódok formájában van megadva a raktári felhasználók számára. A forgatókönyvekhez tartozó mobileszköz lépéseinek befejezéséhez győződjön meg arról, hogy azonosította a tranzakciók munkaazonosítóit, valamint a tranzakciókban szereplő cikkhez és helyhez tartozó azonosítótáblák azonosítóit.

1. Jelentkezzen be a mobileszközön az *51-es* raktárhoz tartozó felhasználói azonosító és jelszó használatával.
1. Válassza ki a **Kimenő** lehetőséget.
1. Válassza ki az **Értékesítési kitárolás** lehetőséget.
1. Lehetőség van a munkaazonosító vagy az azonosítótábla azonosítójának megadására. Adja meg az első értékesítési rendelés munkaazonosítóját, majd válassza a **Bevitel** lehetőséget.
1. A **Hely** mezőben adja meg azt a helyet, amely a kitárolási hely jóváhagyásához látható. Ezután válassza a **Bevitel** lehetőséget.
1. Az **AT** mezőben adja meg az azonosítótábla azonosítóját. Az azonosítótábla azonosítójának meg kell egyeznie a cikk, a raktár és a kiválasztott helyről kitárolt cikk helye esetében. Amikor elkészült, válassza a **Bevitel** elemet.
1. A **Cikk** mezőben adja meg a cikknek a számát, hogy jóváhagyja a kitárolás alatt álló cikket, majd válassza a **Bevitel** lehetőséget.
1. A **Mennyiség** mezőben adja meg a kitárolás alatt álló cikk mennyiségét, majd válassza a **Bevitel** lehetőséget.
1. A **cél LP** mezőben adja meg a cél azonosítótábla azonosítóját. A cél azonosítótábla felhasználó által definiált. Ügyeljen arra, hogy egy olyan azonosítótábla-azonosítót adjon meg, amelyre emlékezni fog. Javasoljuk, hogy az aktuális dátumot plusz egy kétjegyű sorozatot (ÉÉHHNN\#\#) használja formátumként, például *19112301*. Amikor elkészült, válassza a **Bevitel** elemet.
1. Tekintse át a megjelenített információt. Ezek az információk a *Kitárolás* adatai, amelyek most az *Eltárolás* adatok közé kerülnek az eltárolási tranzakció esetében. Amikor elkészült, válassza a **Bevitel** elemet.

    - Megjelenik a **Munka befejezve** üzenet.

1. Ismételje meg a 4–10. lépést a második értékesítési rendelés munkaazonosítójához.

A következő lépés az, hogy a két kitárolt azonosítótáblát be kell tölteni a teherautóba.

1. Jelentkezzen be a mobileszközön az *51-es* raktárhoz tartozó felhasználói azonosító és jelszó használatával.
1. Válassza ki a **Kimenő** lehetőséget.
1. Válassza ki az **Értékesítés betöltése** lehetőséget.
1. Adja meg azt a felhasználó által definiált cél azonosítótábla azonosítóját, amelyet a korábbi eljárás első munkaazonosítójához hozott létre. Ezt követően válassza a **Bevitel** lehetőséget a cél azonosítótábla elhelyezéséhez a **FOKOZAT** helyre.
1. Írja be újra a cél azonosítótábla azonosítóját, majd válassza a **Bevitel** lehetőséget, hogy az azonosítótáblát elhelyezze a **BAYDOOR** helyre.
1. Ismételje meg a 4–5. lépést a második munkaazonosítóhoz létrehozott cél azonosítótábla azonosítója esetében.

A két munkaazonosító most le lesz zárva (betöltve).

### <a name="step-3-confirm-the-outbound-shipment"></a>3. lépés: A kimenő szállítmány jóváhagyása

Ebben a lépésben Ön megerősíti azt a két értékesítési rendelést és munkát, amelyet a rakomány kitárolt cikkeinek szállításához teljesített, és létrehozza a kitárolt cikkek új rakományát. A kimenő szállítmány megerősítés a **Rakomány részletei** oldalon kell végrehajtani.

1. Ugorjon a **Raktárkezelés \> Rakományok \> Rakománytervező munkaterület** elemre.
1. A **Rakományok** szakasz rácsában válassza ki a létrehozott rakományazonosító sorát.
1. A **Rakomány részletei** lap megnyitásához válassza a rakomány azonosítója hivatkozást.
1. A **Rakomány részletei** lap műveleti ablaktábláján a **Szállítás és fogadás** lap **Jóváhagyás** csoportjában válassza ki a **Kimenő szállítmány** elemet a megerősítés megkezdéséhez.
1. A **Szállítás megerősítése** párbeszédpanelen a **Megosztási metódus betöltése szállítás jóváhagyása közben** mezőben válassza ki a *Mennyiség megosztása új rakományhoz* beállítást.
1. Válassza ki az **OK** lehetőséget.

    Megjelenhet a „Művelet feldolgozása” üzenet a képernyőn.

    Olyan tájékoztató üzeneteket kap, amelyek azt jelzik, hogy a rakománya szállítását megerősítették, és a rendszer új rakományt hozott létre a megosztott mennyiségből.

Frissítse a **Rakománytervezési munkaterület** oldalt, hogy megtekintse az újonnan létrehozott rakományt.

Azt is megerősítheti, hogy a tranzakciók kapcsolatai a következő módon lettek frissítve:

- A fennmaradó (feldolgozatlan) szállítmányok és szállítmánysorok új rakományazonosítóval frissültek.
- Az értékesítési rendelés az új rakomány azonosítójához van hozzákapcsolva.
- Az eredeti rakomány nem tartalmazza a fennmaradó rakománysorokat.
- A fennmaradó munka frissítve lett az új rakományazonosítóval.
- A hullám ugyanaz marad.
- Az új rakomány állapota helyesen módosult. (Ha a munka állapota _Folyamatban_, a rakomány állapotának _Folyamatban_ állapotúnak kell lennie.)

## <a name="notes-and-tips"></a>Megjegyzések és tippek

- A **Rakománymegosztás engedélyezése a szállítás jóváhagyása közben** paramétert is bekapcsolhatja, miután létrehozta a rakományt, és a **Rakománysablon** paramétert kikapcsolta még a betöltési folyamat megkezdése előtt. Nyissa meg a kívánt rakományt, majd a fejléc nézetben kapcsolja be a paramétert.
- A **Mennyiség megosztása új rakományhoz** beállítás akkor is működik, ha a fennmaradó munkafejlécek egy része *Folyamatban* állapotú. Ennek megfelelően még akkor is használhatja a funkciót, ha a dolgozók már futtatják a kitárolási rendeléseket.
- Ha be van jelölve a **Nem teljesített mennyiség érvénytelenítése**, miközben a fennmaradó munka állapota *Nyitott* vagy *Folyamatban*, a következő hibaüzenet jelenik meg: „Nem lehet érvényteleníteni a rakomány fennmaradó mennyiségét. A rakománnyal munkavégzés zajlik.”
- Ha bejelöli a **Nem teljesített mennyiség érvénytelenítése** lehetőséget, ha nincs fennmaradó munka, de a rakomány nem kiadott sorokat tartalmaz, akkor a következő hibaüzenet jelenik meg: „A rakomány szállítása nem erősíthető meg, mert a cikkmennyiség meghaladja a szállítás alatti rakomány megadott arányát.” A hiba elkerüléséhez beállíthatja a **Szállítás alatt** százalékos arányát a kiadatlan rakományok sorában 100 százalékra. A kiadatlan sorok nem kerülnek át az új rakományba, de az aktuális rakományt a rendszer szállítás alattiként megerősíti. Ebben az esetben nem fogja tudni újra kiadni az eredeti rendelést. Ezért ezt Önnek másképp kell majd kezelnie.
