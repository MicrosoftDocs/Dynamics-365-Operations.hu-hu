---
title: Raktári folyamatok minőségkezelése
description: A témakör raktárfolyamatok funkcióhoz tartozó minőségkezelési folyamatról tartalmaz információkat. Ez a funkció kiterjeszti a minőségkezelési funkciókat, és lehetővé teszi a felhasználók számára, hogy a speciális raktárkezelés modul segítségével cikk-mintavételezési funkciókat integráljanak a raktárba.
author: Henrikan
manager: tfehr
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-02
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: fd6b4b0c30a8a4cb36955e9b131c937c4db80772
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983725"
---
# <a name="quality-management-for-warehouse-processes"></a>Raktári folyamatok minőségkezelése

A _Minőségkezelés a raktárfolyamatokhoz_ funkció lehetővé teszi, hogy a speciális raktárkezelés modul segítségével cikk-mintavételezési funkciókat integráljon a raktárba. A raktári munka automatikusan létrehozható úgy, hogy a készletet a minőség-ellenőrzési helyre helyezze át, egy százalék vagy a rögzített mennyiség szerint ,illetve minden *n*. azonosítótáblára vonatkozóan. A minőségi rendelés befejezése után a minőségi eredményektől függően automatikusan létrehozható a munka a készlet következő helyre történő áthelyezéséhez.

A _Minőségkezelés a raktári folyamatokhoz_ funkció kiterjeszti az alapvető minőségkezelési funkció képességeit. A minőség-ellenőrzési helyre küldött készlethez minőségi rendelések létrehozását teszi lehetővé, bár a minőségi rendelések nem mindig szükségesek. Így egy könnyű minőségellenőrzési folyamatot tesz lehetővé, amely a raktári munkákon alapul.

## <a name="turn-on-the-quality-management-for-warehouse-processes-feature"></a>A Raktári folyamatok minőségkezelése funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Raktári folyamatok minőségkezelése*

## <a name="key-benefits"></a>Legfontosabb előnyök

A _Raktári folyamatok minőségkezelése_ funkció automatikusan hoz létre a munkát a bevételezési folyamat részeként, hogy a minőség-ellenőrzéshez szükséges készletmennyiség a minőség-ellenőrzési helyre kerüljön. Ha a bevételezett mennyiség meghaladja a minőség-ellenőrzéshez szükséges mennyiséget (a cikk-mintavételezés beállításai alapján), akkor a rendszer áthelyezi a felesleges mennyiséget egy bejövő helyre, amely a helyutasítás beállításaiban meg van határozva. A minőségi rendelés ellenőrzése után a program automatikusan létrehoz egy munkát, hogy a minőségi rendelés mennyiségét áthelyezze egy új bejövő vagy visszaküldési helyre az ellenőrzés eredménye és a helyutasítás beállításai alapján. Az automatikus munkalétrehozás, amely csak azt a mennyiséget tartalmazza, amelyet át kell helyezni minőségellenőrzésre, illetve elvinni onnan egy integrált folyamatélményt nyújt.

> [!NOTE]
> Ha be van kapcsolva a _Raktári folyamatok minőségkezelése_ funkció, akkor is igénybe veheti a manuális folyamatot. A kézi folyamatban a készletmozgatás és a mozgatás sablonnal használatos arra, hogy a raktári munkás elindítsa a rakátri munka létrehozását, hogy a raktárkészletet a minőségellenőrzés helyszínéről az új helyszínre helyezze át. Továbbra is be lehet állítani egy olyan bejövő helyutasítást, amely a készletet teljes egészében a fogadó helyről egy minőségiellenőrzési helyre mozgatja, a cikkek mintavételi beállításainak figyelembe vétele nélkül.

## <a name="quality-management-and-the-quality-management-for-warehouse-processes-feature"></a>Minőségkezelés és Raktári folyamatok minőségkezelése folyamatok funkció

Amikor be van kapcsolva a _Raktári folyamatok minőségkezelése_ funkció, az megváltoztatja a központi raktárkezelés és a minőségirányítási entitások beállítását. A következő ábra áttekintést nyújt azokról az entitásokról, amelyek a raktári folyamatokhoz minőségi rendeléseket engedélyeznek. A zárójelben lévő szöveg javasolt műveleteket jelez , amikor a minsőégkezelés azelőtt lett alkalmazva, hogy a _Raktári folyamatok minőségkezelése_ funkciót bekapcsolták volna.

![Minőségkezelési entitások](media/quality-management-entity-diagram.png "Minőségkezelési entitások")

## <a name="enablers-the-quality-item-sampling-and-quality-order-work-order-types"></a>Előmozdítók: A Minőségi cikk-mintavételezés és Minőségi rendelés munkarendelés munkatípusok

A _Raktári folyamatok minőségkezelése_ funkció a munkalétrehozási folyamatot engedélyező két munkarendelés-típust vezet be:

- **Minőségi cikk-mintavételezés** – Ez a munkarendelés-típus a regisztrált készletet minőségellenőrzésre áthelyező munka létrehozásához használatos.
- **Minőségi rendelés** – Ez a munkarendelés-típus olyan munka létrehozására használható, amely a minőség-ellenőrzésből egy új helyre helyezi át a készletet a helyutasítások beállításai alapján.

### <a name="work-classes-location-directives-and-work-templates"></a>Munkaosztályok, helyutasítások és munkasablonok

A _Minőségi cikk-mintavételezés_ és _Minőségi rendelési_ munkatípusok a helyutasítások, munkaosztályok és munkasablonok által kerülnek felhasználásra.

Mielőtt a raktári munka automatikusan létrehozható lenne a készlet minőség-ellenőrzésbe történő áthelyezéséhez, a következő lépések végrehajtásával be kell állítani a rendszert.

1. Hozzon létre külön munkaosztályokat hozhat létre a _Minőségi cikk-mintavételezés_ és _Minőségi rendelési_ munkatípusokhoz. Így gondoskodhat arról, hogy a két munkarendelés-típus alapján automatikusan létrehozható legyen a megfelelő munka, és ezt a munka azután futtatható legyen a raktári alkalmazás használatával.
1. Munkasablon beállítása ez egyes munkarendelés-típusokhoz.

    - Olyan munkasablont állítson be, amely a _Minőségi cikk-mintavételezés_ munkarendelés-típust használja a regisztrált készlet automatikus mozgatására egy minőségellenőrzési helyre.
    - Olyan munkasablont állítson be, amely a _minőségi rendelés_ munkarendelés-típust használja a regisztrált készlet automatikus mozgatására egy minőségellenőrzési helyről, a minőségellenőrzés befejeztével.

1. Minden munkarendelés-típusnál állítsa be a helyutasításokat, amelyek alkalmazzák a megfelelő minőségellenőrzési helyeket, ahová a készletet át kell helyezni. A minőség-ellenőrzés befejezése után a _Minőségi rendelés_ munkarendelés-típushoz tartozó helyutasítás gondoskodik arról, hogy az új célhely ki legyen jelölve, hogy a készlet áthelyezhető legyen a minőség-ellenőrzés helyéről.
1. A megfelelő mobileszköz-menüelemek beállításával támogathatja a bevételezett készlet mozgását a minőség-ellenőrzési helyre, valamint a minőségellenőrzésen átmenő, illetve elbukó készlet áthelyezését minőség-ellenőrzés helyétől egy új helyre.

A témakör végén található [példa forgatókönyvben](#example-scenario) talál egy részletes útmutatót a beállítás elvégzéséről.

## <a name="enable-a-warehouse-for-quality-management"></a>Raktár engedélyezése minőségkezeléshez

Mielőtt a _Raktári folyamatok minőségkezelése_ funkciót egy adott raktárra alkalmazni lehet, a következő lépések végrehajtásával kell elérhetővé tennie a funkciót a raktárhoz.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Raktárak** pontra.
1. Jelölje ki a raktárat, amelyet engedélyezni szeretne a minőségkezeléshez.
1. A **Raktár** gyorslapon állítsa be a **Minőségi rendelések engedélyezése a raktári folyamatokhoz** beállítást _Igen_ értékre. (Ne feledje, hogy ez a beállítás csak a raktárkezelési folyamatokat használó raktárak esetében lehet _Igen_ értékre állítani.)

Ha a **Raktári folyamatok minőségi rendelésének engedélyezése** beállítás _Igen_ értékre van állítva, akkor a minőség társítása beállítás határozza meg, hogy a _Raktári folyamatok minőségkezelése_ funkció valójában alkalmazva van-e a kijelölt raktárra. A beállítás értékét bármikor _Nem_ értékre módosíthatja. Ebben az esetben a funkció a minőség társítása beállításaitól függetlenül nem lesz érvényes a raktárra.

## <a name="quality-control"></a>Minőség-ellenőrzés

A _Raktári folyamatok minőségkezelése_ funkció a minőségi társítások és a cikkek mintavételezése számos kulcsfontosságú beállítását vezérli.

### <a name="quality-associations"></a>Minőségi társítások

Minden [minőség-hozzárendelési rekord](enable-quality-management.md) meghatározza továbbá a teszteket, az elfogadható minőségi szintet és a mintavételi eljárást, amelyeket a minőségi rendelésekre alkalmaz. A minőségi társítási rekord beállításához tegye a következőket.

1. Ugorjon a következőhöz: **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Minőségi társítások**.
1. Hozza létre vagy válassza ki annak a cikknek vagy csoportnak a minőségi társítási bejegyzését, amelyen éppen dolgozik, vagy az összes cikkhez.
1. A **Feltételek** gyorslapon állítsa be a **Vonatkozó raktártípus** mezőt a következő értékek valamelyikére:

    - **Csak Raktári folyamatok minőségkezelése** – Aktiválja a _Raktári folyamatok minőségkezelése_ funkciót. Ez az érték csak akkor választható ki, ha a hivatkozás típusa *Beszerzés* vagy *Termelés*.
    - **Mind** – A _Raktári folyamatok minőségkezelése_ funkció kikapcsolása. Válassza ki ezt az értéket minden hivatkozástípus esetében a *Beszerzés* és *Termelés* kivételével.

> [!NOTE]
> A _Raktári folyamatok minőségkezelése_ funkció csak akkor lép érvénybe, ha a forrásbizonylat sorában található cikk speciális raktárkezelési folyamatokat használ, és ha a **Minőségi rendelések engedélyezése a raktári folyamatokhoz** beállítás értéke _Igen_ a forrásbizonylat sorában található raktárhoz.

Mivel minden egyes cikk regisztrálva van (vagy készként jelentve), a rendszer határozza meg, hogy melyik minőségi társítás vonatkozik rá.

Ha be van kapcsolva a _Raktári folyamatok minőségkezelése_ funkció, akkor a vonatkozó raktártípus logikailag be lesz illesztve a minőségi társítás keresési hierarchia negyedik keresési csoportjába. A következő táblázat a keresési hierarchia logikai megjelenítését mutatja be.

| Keresési csoport | Leírás |
|---|---|
| 1. csoport | Minden minőségi társítás esetében ellenőrizze a **Hivatkozástípus**, az **Eseménytípus** és a **Végrehajtási egyeztetés** értékét a cikkel szemben. Ha van egyezés a forrásbizonylat sorához, akkor folytassa a 2. csoporttal. |
| 2. csoport | Minden minőségi társítás esetében ellenőrizze **Cikk-kód** értékét (_Tábla_, _Csoport_ vagy _Mind_) a cikkel szemben. A _Tábla_ specifikusabb, mint a _Csoport_, és a _Csoport_ specifikusabb, mint a _Mind_. Ha van egyezés a _Táblához_ (egy konkrét cikk), akkor lépjen tovább a 3. csoportra. Ha nincs egyezés a _Táblához_, keressen egyezést a _Csoportban_. Ha nincs egyezés a _Csoportban_ akkor a _Mind_ vonatkozik. Ha van egyezés, lépjen tovább a 3. csoportra. |
| 3. csoport | Minden minőségi társításnál ellenőrizze a **Számlakód** és az **Erőforrás kódja** értékét a cikkel szemben. Az alkalmazott logika hasonlít a **cikk-kód** értékére alkalmazott logikához. |
| 4. csoport | Minden minőségi társításnál ellenőrizze a **Vonatkozó raktártípus** értékét (_Csak Raktári folyamatok minőségkezelés_ vagy _Mind_) a cikkel szemben. Ha a **Minőségi rendelések engedélyezése a raktári folyamatokhoz** beállítás _Igen_ értékre van állítva a forrásbizonylat raktárában, és a forrásbizonylat sorában cikk beállítása _Raktárkezelési folyamatok használata_ akkor a társításoknál, ahol van egyezés a _Csak Raktári folyamatok minőségkezelése_ elemre és a társításoknál, ahol van egyezés a _Mind_ elemre párhuzamosan vonatkoznak, ha mindkettő létezik. A **Raktári folyamatok minőségkezelése** beállítás értéke _Nem_ a forrásbizonylat raktárához és a forrásbizonylat sorában szereplő cikk beállítása _Raktárkezelési folyamatok használata_ csak a minőségkezelés fog vonatkozni. |

Például olyan raktárat definiált, ahol a **Minőségi rendelés engedélyezése a raktári folyamatokhoz** beállítás _Igen_ értékre van állítva, és két minőségi társítás van megadva a *Beszerzés* hivatkozástípushoz: egy az összes cikkre és egy a *Regisztráció* eseménytípushoz. A két minőségi társítás között a különbséget csak a **Vonatkozó raktártípus** érték jelenti: az egyik minőségi társításhoz _Mind_ értékre van állítva, míg a másikhoz _Csak Raktári folyamatok minőségkezelése_ értékre. Ebben az esetben mindkét minőségi társítás egyenlően specifikus és mindkettő alkalmazható lesz.

A minőségi társítások **Tesztjelentés** mezőjének értéke is tényező. Ez a mező azt a teszt-eljárást határozza meg, amelyet alkalmazni kell. Ha a **Tesztcsoport** értéke megegyezik mindkét társításhoz csak egy minsági rendelés lesz létrehozva a minőségi társításhoz, ahol a **Vonatkozó raktártípus** értéke _Csak Raktári folyamatok minőségkezelése_. Ha a **Tesztcsoport** értéke mindkét társítás esetében nem egyezik meg, akkor két minőségi rendelés jön létre. Az első minőségi rendelés ahhoz a minőségi társításhoz jön létre, ahol a **Vonatkozó raktártípus** értéke _Csak Raktári folyamatok minőségkezelése_. A második minőségi rendelés ahhoz a minőségi társításhoz jön létre, ahol a **Vonatkozó raktártípus** értéke _Mind_.

> [!NOTE]
> A _Csak Raktári folyamatok minőségkezelése_ értékek specifikusabb, mint a _Mind_, ha az 1. és 2. csoport minőségi társításának kritériumai megegyeznek, és a tesztcsoport is megegyezik. Csak akkor jön létre két minőségi rendelés, ha a tesztcsoportok eltérnek.

#### <a name="reference-types"></a>Hivatkozástípusok

Ha a **Hivatkozástípus** értéke _Beszerzés_, és a **Vonatkozó raktártípus** értéke _Csak Raktári folyamatok minőségkezelése_ akkor az **Eseménytípus** mezőt a **Folyamat** gyorslapon _Regisztráció_ értékre kell állítani. A _Regisztráció_ az egyetlen támogatott eseménytípus a _Beszerzés_ hivatkozástípushoz, ha a _Raktári folyamatok minőségkezelése_ funkciót használja.

#### <a name="quality-processing-policy"></a>Minőségfeldolgozási irányelv

A _Raktári folyamatok minőségkezelése_ funkció lehetővé teszi a munka létrehozását csak a cikk-mintavétel alapján. Ez lehetővé teszi a könnyű feldolgozást. A munka által létrehozott készlet a minőségi társításhoz társított cikk-mintavételezéstől függ. A könnyű eljárás alkalmazása esetén, miután a dolgozó a minőség-ellenőrzési helyre elhelyezi a mennyiséget, ha minőségi rendelés szükséges, akkor a minőségbiztoítási osztály manuálisan létrehozhatja a minőségi rendelést.

A **Minőségfeldolgozási házirend** mező a **Minőségi rendelés folyamata** gyorslapon határozza meg, hogy egy minőségi rendelés is létrejön-e, amikor munkát hoznak létre egy cikk elhelyezéséhez a minőségellenőrzés helyére. A mező értéke _Minőségi rendelés létrehozása_ vagy _Csak munka létrehozása_ lehet. Az alapértelmezett érték a _Minőségi rendelés_ létrehozása.

> [!NOTE]
> Attól függetlenül, hogy manuálisan vagy automatikusan hozza létre a minőségi rendeléseket, a rendszer automatikusan létrehozza a munkát, hogy a cikkeket áthelyezze a minőségellenőrzés helyéről, ha minőségi rendelés ellenőrzöttnek van megjelölve.

A minőségi rendeléshez tartozó munka létrehozása nem kapcsolódik a minőségi társítási beállításhoz. Ha van olyan munkasablon, amely olyan **Munkarendelés típussal** rendelkezik, amelynek értéke *Minőségi rendelés* és ha a lekérdezési feltételek teljesülnek az adott munkasablonhoz, akkor a minőségi rendelés ellenőrzése elindítja a minőségi rendelés munkájának létrehozását.

#### <a name="referenced-item-sampling"></a>Hivatkozott cikk mintavételezése

Minden minőségi társításnak hivatkoznia kell egy cikk-mintavételezésre. A cikk-mintavételezés határozza meg a minőség-ellenőrzésre elküldendő mennyiséget. Beállítható, hogy csak olyan minőségi társításokra vonatkozzon, ahol a **Vonatkozó raktártípus** értéke _Csak Raktári folyamatok minőségkezelése_. Ha egy cikk-mintavételezés **Mintavételi hatókör** értéke _Rakomány_ vagy a _Szállítmány_, vagy a **Mennyiségi meghatározás** értéke _Teljes azonosítótábla_ akkor a cikk mintavételezésre csak olyan minőségi társítások hivatkozhatnak, amelyeknél a **Vonatkozó raktártípus** értéke _Csak Raktári folyamatok minőségkezelése_.

Ha olyan cikk-mintavételt határoz meg, amely _Csak Raktári folyamatok minőségkezelése_ vonatkozó raktártípust használja , akkor a program hibaüzenetet jelenít meg, ha olyan minőségi társításból próbál meg hivatkozni amely nem használja a _Raktári folyamatok minőségkezelése_ funkciót.

> [!NOTE]
> A teljes blokkolást használó cikk-mintavételezés nem támogatott olyan minőségi társítások esetében, amelyeknél a **Vonatkozó raktár típusa** mező beállítása _Csak raktári folyamatok minőségkezelése_.

### <a name="item-sampling"></a>Cikkmintavétel

A cikk-mintavétel azt szabályozza, hogy milyen gyakran történik a cikkek elküldése a minőség-ellenőrzésre. A _Raktári folyamatok minőségkezelése_ funkció bevezeti a _cikk-mintavételezés hatóköre_ koncepcióját. A rendszer a cikk-mintavételezési hatókört használja, amikor kiértékeli, hogy minőségi rendeléseket és/vagy a minőségi cikk-mintavételi munkát és minőségi rendelési munkát létre kell-e hozni, illetve hogyan kell létrehozni.

A cikkek mintavételezés beállításához nyissa meg a **Készletkezelés \> Beállítások \> Minőségellenőrzés \> Cikk-mintavételezés** lehetőséget majd állítsa be a **Mintavételi hatókör** mezőt a következő értékek egyikére:

- **Rendelés** – A forrásdokumentum sora lesz az alapja annak a kiértékelésének, hogy minőségi rendeléseket és/vagy a minőségi cikk-mintavételi munkát és minőségi rendelési munkát létre kell-e hozni, illetve hogyan kell létrehozni. Ez az érték az alapértelmezett érték, és ha ki van jelölve, akkor a rendszer ugyanúgy működik, mint amikor a _Raktári folyamatok minőségkezelése_ funkció nincs bekapcsolva.
- **Rakomány** – A rakományok lesznek használva annak kiértékeléséhez, hogy létre legyen-e hozva minőségi rendelése és/vagy munka, illetve ez hogyan történjen. Ez az érték csak akkor érhető el , ha be van kapcsolva a _Raktári folyamatok minőségkezelése_ funkció.
- **Szállítmány** – A szállítmányok lesznek használva annak kiértékeléséhez, hogy létre legyen-e hozva minőségi rendelés és/vagy munka, illetve ez hogyan történjen. Ez az érték csak akkor érhető el , ha be van kapcsolva a _Raktári folyamatok minőségkezelése_ funkció.

> [!NOTE]
> Ha a **Mintavételezési hatókör** mező beállítása *Rakomány* vagy *Szállítmány*, akkor a program a rakomány és a szállítmány entitásokat használja, ha rendelkezésre állnak. Ha nem érhetők el, akkor a program a rendelés entitást fogja használni.

A _Raktári folyamatok minőségkezelése_ funkció bevezeti a *Teljes azonosítótábla* értéket is a **Mennyiség meghatározása** mezőhöz. Ez az érték támogatja a minőségi rendelési munka és a minőségi cikk-mintavételi munkák létrehozását az azonosítótábla alapján. Ha ezt az értéket választja, a következő változtatások történnek:

- A **Megszakítások száma cikkenként** beállítás és az **N. azonosítótábla** mezők elérhetővé válnak a **Folyamat** gyorslapon.
- Az **Érték** mező a **Mintavételi mennyiség** gyorslapon nem lesz elérhető.
- A **Frissítettmennyiségenként**, a **Hely** és az **Azonosítótábla** beállításai mind *Igen* értékre vannak állítva, a beállításokat pedig nem lehet módosítani.

A **Megszakítások száma cikkenként** alapján beállítás határozza meg, hogy az azonosítótábla számolást cikkenként vagy az összes cikkre vonatkozóan kell kiértékelni a mintavételi tartományban. A termékváltozatok ugyanazon a cikként vannak kezelve. Ez a beállítás azt is meghatározza, hogy az egyes cikkek esetében az azonosítótábla-számlálás alaphelyzetbe van-e állítva.

Az **N. azonosítótáblánként** értéke határozza meg, hogy milyen gyakran jönnek létre a minőségi rendelések a regisztrált cikkek számához képest.. Például a *3* érték minden harmadik cikket minőség-ellenőrzésre küldi, az első elemmel kezdve. Az értéknek nullánál (0) nagyobbnak kell lennie.

Miközben a dolgozók a raktári alkalmazás segítségével fogadnak cikkeket, a rendszer ellenőrzi, hogy az egyes bejövő cikkek minőségi társítása be van-e állítva. Ha be van állítva egy minőségi társítás, akkor a rendszer az adott minőségi társításhoz konfigurált cikk-mintavételi rekord alapján határozza meg, hogy hogyan fog létrehozni minőségi rendeléseket, minőségi cikk-mintavételi munkát és beszerzési rendelési munkát.

> [!NOTE]
> Amikor a bevételezés regisztrálása a webes ügyfélben történik (a kis regisztrációs lap vagy a cikkek érkeztetési naplója alapján a beszerzésirendelés-sorokban) nem jön létre minőségi cikk-mintavételi munka vagy beszerzési rendelési munkafolyamat a beállítástól függetlenül. Helyette a minőségi társításnak megfelelő cikkek esetében a hivatkozott cikk-mintavétel csak a minőségi rendelések létrehozásának szabályzásához használatos.

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Minőségi rendelések automatikus generálásával kapcsolatos példák

A következő példák azt mutatják be, hogy hogyan befolyásolja a minőségi társítás és a társított cikkek mintavételezése a minőségi rendelések létrehozását , amikor a **Vonatkozó raktártípus** mező értéke _Csak Raktári folyamatok minőségkezelése_.

Ha a **Mennyiség meghatározása** értéke _Teljes azonosítótábla_, akkor az **N. azonosítótáblánként** mező határozza meg, hogy mely azonosítótábla minőségi mintavételezési munka legyen létrehozva. Az első azonosítótábla mindig elmegy minőségellenőrzésre, és a mező értéke azt határozza meg, hogy ezen azonosítótábla után minden *n*-edik azonosítótábla is menjen minőségellenőrzésre.

A következő példák **Hivatkozási típusa** értéke a _Beszerzés_ és az **Eseménytípus** értéke pedig *Regisztráció*.

| Mintavétel hatóköre | Mennyiség megadása | Frissített mennyiségenként | Tárolási dimenziónként | Szám lebontása cikk szerint | N-edik azonosítótábla | Eredmény |
|---|---|---|---|---|---|---|
| Sorrend | Teljes azonosítótábla | Igen _(zárolt/nem szerkeszthető)_ | <p>Hely: Igen</p><p>Azonosítótábla: Igen _(zárolt/nem szerkeszthető)_</p> | Nincs | 3 | <p>**Rendelési sor mennyisége: 100 EA**</p><ol><li>Fogadás regisztrálása a raktári alkalmazásban 20 EA-hoz, LP1<p>Minőségi cikkek mintavétel munka 20 EA számára</p><p>1. minőségi rendelés 20 EA-hoz</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 20 EA-hoz, LP2<p>Beszerzési rendelési munka 20 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 20 EA-hoz, LP3<p>Beszerzési rendelési munka 20 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 20 EA-hoz, LP4<p>Minőségi cikkek mintavétel munka 20 EA számára</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 20 EA-hoz, LP5<p>Beszerzési rendelési munka 20 EA-hoz (elraktározás)</p></li></ol> |
| Megrendelés | Rögzített mennyiség =1 | Igen | <p>Hely: Igen</p><p>Azonosítótábla: Igen</p> | Nincs | Nem alkalmazható | <p>**Rendelési sor mennyisége: 100**</p><ol><li>Fogadás regisztrálása a raktári alkalmazásban 20 EA-hoz, LP1<p>Minőségi cikkek mintavétel munka 1 EA számára</p><p>1. minőségi rendelés 1 EA-hoz</p><p>Beszerzési rendelési munka 19 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 20 EA-hoz, LP2<p>Minőségi cikkmintavétel munka 1 EA számára</p><p>1. minőségi rendelés 1 EA-hoz</p><p>Beszerzési rendelési munka 19-hez (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 20 EA-hoz, LP3<p>Minőségi cikkek mintavétel munka 1 EA számára</p><p>1. minőségi rendelés 1 EA-hoz</p><p>Beszerzési rendelési munka 19 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 20 EA-hoz, LP4<p>Minőségi cikkek mintavétel munka 1 EA számára</p><p>1. minőségi rendelés 1 EA-hoz</p><p>Beszerzési rendelési munka 19 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 20 EA-hoz, LP5<p>Minőségi cikkek mintavétel munka 1 EA számára</p><p>1. minőségi rendelés 1 EA-hoz</p><p>Beszerzési rendelési munka 19 EA-hoz (elraktározás)</p></li></ol> |
| Sorrend | Százalék = 10 | Nincs | <p>Helyszín: Nem</p><p>Azonosítótábla: Nem</p> | Nincs | Nem alkalmazható | <p>**Rendelési sor mennyisége: 100 EA**</p><ol><li>Fogadás regisztrálása a raktári alkalmazásban 50 EA-hoz, LP1<p>Minőségi cikkek mintavétel munka 10 EA számára</p><p>1. minőségi rendelés 10 EA-hoz</p><p>Beszerzési rendelési munka 40 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 50 EA-hoz, LP2<p>Beszerzési rendelési munka 50 EA-hoz (elraktározás)</p></li></ol> |
| Betöltés | Százalék = 5 | Igen _(zárolt/nem szerkeszthető)_ | <p>Helyszín: Nem</p><p>Azonosítótábla: Nem</p> | Nincs | Nem alkalmazható | <p>**Rendelési sor mennyisége: 500 EA**</p><p>**Két rakomány: első rakomány 200 EA, második rakomány 300 EA**</p><ol><li>Fogadás regisztrálása a raktári alkalmazásban az első rakományhoz 100 EA-hoz<p>Minőségi cikkek mintavétel munka 5 EA számára</p><p>1. minőségi rendelés 5 EA-hoz</p><p>Beszerzési rendelési munka 95 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban az első rakományhoz 100 EA-hoz<p>Minőségi cikkek mintavétel munka 5 EA számára</p><p>1. minőségi rendelés 5 EA-hoz</p><p>Beszerzési rendelési munka 95 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban a második rakományhoz 300 EA-hoz<p>Minőségi cikkek mintavétel munka 15 EA számára</p><p>1. minőségi rendelés 15 EA-hoz</p><p>Beszerzési rendelési munka 285 EA-hoz (elraktározás)</p></li></ol> |
| Sorrend | Százalék = 10 | Nincs | <p>Hely: Igen</p><p>Azonosítótábla: Igen</p> | Nincs | Nem alkalmazható | <p>**Rendelési sor mennyisége: 100**</p><ol><li>Fogadás regisztrálása a raktári alkalmazásban 50 EA-hoz, LP1<p>Minőségi cikkek mintavétel munka 5 EA számára</p><p>1. minőségi rendelés 5 EA-hoz</p><p>Beszerzési rendelési munka 45 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 50 EA-hoz, LP2<p>Minőségi cikkek mintavétel munka 5 EA számára</p><p>1. minőségi rendelés 5 EA-hoz</p><p>Beszerzési rendelési munka 45-hez (elraktározás)</p></li></ol> |
| Betöltés | Teljes azonosítótábla | Igen _(zárolt/nem szerkeszthető)_ | <p>Hely: Igen</p><p>Azonosítótábla: Igen _(zárolt/nem szerkeszthető)_</p> | Nincs | 3 | <p>**Két elem:**</p><ul><li>**Rendelési sor mennyisége az A cikkhez: 120 EA (4 raklap)**</li><li>**Rendelési sor mennyisége a B cikkhez: 90 EA (3 raklap)**</li></ul><p>**Egy rakomány, két terhelési sor minden rendelési sorhoz**</p><ol><li>Fogadás regisztrálása a raktári alkalmazásban az A cikkhez, 30 EA-hoz, LP1<p>Minőségi cikkek mintavétel munka 30 EA számára</p><p>1. minőségi rendelés 30 EA-hoz</p></li><li>Fogadás regisztrálása a raktári alkalmazásban az A cikkhez, 30 EA-hoz, LP2<p>Beszerzési rendelési munka 30 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban az A cikkhez, 30 EA-hoz, LP3<p>Beszerzési rendelési munka 30 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban az A cikkhez, 30 EA-hoz, LP4<p>Minőségi cikkek mintavétel munka 30 EA számára</p><p>1. minőségi rendelés 30 EA-hoz</p></li><li>Fogadás regisztrálása a raktári alkalmazásban a B cikkhez, 30 EA-hoz, LP5<p>Beszerzési rendelési munka 30 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban a B cikkhez, 30 EA-hoz, LP6<p>Beszerzési rendelési munka 30 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban az A cikkhez, 30 EA-hoz, LP7<p>Minőségi cikkek mintavétel munka 30 EA számára</p><p>1. minőségi rendelés 30 EA-hoz</p></li></ol> |
| Betöltés | Teljes azonosítótábla | Igen _(zárolt/nem szerkeszthető)_ | <p>Hely: Igen</p><p>Azonosítótábla: Igen _(zárolt/nem szerkeszthető)_</p> | Igen | 3 | <p>**Két elem:**</p><ul><li>**Rendelési sor mennyisége az A cikkhez: 120 EA (4 raklap)**</li><li>**Rendelési sor mennyisége a B cikkhez: 90 EA (3 raklap)**</li></ul><p>**Egy rakomány, két terhelési sor minden rendelési sorhoz**</p><ol><li>Fogadás regisztrálása a raktári alkalmazásban az A cikkhez, 30 EA-hoz, LP1<p>Minőségi cikkek mintavétel munka 30 EA számára</p><p>1. minőségi rendelés 30 EA-hoz</p></li><li>Fogadás regisztrálása a raktári alkalmazásban az A cikkhez, 30 EA-hoz, LP2<p>Beszerzési rendelési munka 30 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban az A cikkhez, 30 EA-hoz, LP3<p>Beszerzési rendelési munka 30 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban az A cikkhez, 30 EA-hoz, LP4<p>Minőségi cikkek mintavétel munka 30 EA számára</p><p>1. minőségi rendelés 30 EA-hoz</p></li><li>Fogadás regisztrálása a raktári alkalmazásban a B cikkhez, 30 EA-hoz, LP5<p>Minőségi cikkek mintavétel munka 30 EA számára</p><p>1. minőségi rendelés 30 EA-hoz</p></li><li>Fogadás regisztrálása a raktári alkalmazásban a B cikkhez, 30 EA-hoz, LP6<p>Beszerzési rendelési munka 30 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban az A cikkhez, 30 EA-hoz, LP7<p>Beszerzési rendelési munka 30 EA-hoz (elraktározás)</p></li></ol> |
| Betöltés | Százalék = 10 | Igen _(zárolt/nem szerkeszthető)_ | <p>Helyszín: Nem</p><p>Azonosítótábla: Nem</p> | Nincs | Nem alkalmazható | <p>**Rendelési sor mennyisége: 100 EA**</p><p>**Nincs rakomány létrehozva. A rendelési hatókör alkalmazva.**</p><ol><li>Fogadás regisztrálása a raktári alkalmazásban 50 EA-hoz, LP1<p>Minőségi cikkek mintavétel munka 5 EA számára</p><p>1. minőségi rendelés 5 EA-hoz</p><p>Beszerzési rendelési munka 45 EA-hoz (elraktározás)</p></li><li>Fogadás regisztrálása a raktári alkalmazásban 50 EA-hoz, LP2<p>Minőségi cikkek mintavétel munka 5 EA számára</p><p>1. minőségi rendelés 5 EA-hoz</p><p>Beszerzési rendelési munka 45 EA-hoz (elraktározás)</p></li></ol> |

Amikor egy dolgozó érvényesít egy olyan minőségi rendelést, amely az előző táblában látható, a rendszer automatikusan minőségi rendelési munkát hoz létre, hogy a készletet áthelyezze a minőség-ellenőrzési helyről arra a helyre, ami definiálva van a helyutasításokban a _Minőségi rendelés_ munkarendeléstípushoz. A minőségi rendelésre vonatkozó teszteredmények alapján bármilyen helyet beállíthat erre a célra, például a visszáru vagy a tárolás helyét. Erre a beállításra példát a [példa forgatókönyv](#example-scenario) tartalmaz a témakör végén.

Újra megnyithatja azt a minőségi rendelést, amely már ellenőrizve lett, feltéve, hogy a minőség-ellenőrzési helyről a készlet áthelyezéséhez kapcsolódó minőségi rendelési munka **Munkaállapot** értéke nem *Lezárt* vagy *Folyamatban*.

## <a name="process-insights-when-multiple-quality-associations-coexist"></a>Információk feldolgozása, amikor több minőségi társítás létezik együtt

Több minőségi társítást is meg lehet határozni és alkalmazni ugyanarra a forrásbizonylat-sorra, és a **Vonatkozó raktártípus** mező beállítható _Csak Raktári folyamatok minőségkezelése_ értékre bizonyos elemekhez, míg _Mind_ értékre más elemekhez.

A következő példában a **Hivatkozástípus típusa** értéke _Beszerzés_.

1. Az első minőségi társítás a következő módon van beállítva:

    - **Vonatkozó raktár típusa:** *Csak a raktári folyamatok minőségkezelése*
    - **Cikk-kód:** *A0001*
    - **Számlakód** *Mind*
    - **Tesztcsoport:** *Doboz*
    - **Cikkmintavétel:** *5 db*

1. A második minőségi társítás a következő módon van beállítva:

    - **Vonatkozó raktár típusa:** *Mind*
    - **Cikk-kód:** *Mind*
    - **Számlakód** *Mind*
    - **Tesztcsoport:** *Doboz*
    - **Cikkmintavétel:** *1 db*

1. A harmadik minőségi társítás a következő módon van beállítva:

    - **Vonatkozó raktár típusa:** *Csak a raktári folyamatok minőségkezelése*
    - **Cikk-kód:** *Mind*
    - **Számlakód:** *104*
    - **Tesztcsoport:** *Ellenállás*
    - **Cikk-mintavételezés**: *Minden második azonosítótábla* (Ez a beállítás azt jelenti, hogy az első, a harmadik, az ötödik azonosítótábla és így tovább fog létrehozni egy minőségi rendelést.)

1. A negyedik minőségi társítás a következő módon van beállítva:

    - **Vonatkozó raktár típusa:** *Mind*
    - **Cikk-kód:** *Mind*
    - **Számlakód** *Mind*
    - **Tesztcsoport:** *Ellenállás*
    - **Cikkmintavétel:** *5 db*

1. Az ötödik minőségi társítás a következő módon van beállítva:

    - **Vonatkozó raktár típusa:** *Mind*
    - **Cikk-kód:** *Mind*
    - **Számlakód** *Mind*
    - **Tesztcsoport:** *Kúp*
    - **Cikkmintavétel:** *10%*

Az A0001 cikk 10 mennyiségéhez jön létre beszerzési rendelés a 104-es szállítóhoz. Ezután egy 10 mennyiséggel rendelkező beszerzésirendelés-sor lesz regisztrálva fogadottként egy azonosítótáblán a raktári alkalmazásban. Az eredmény a következő:

- Egy minőségi rendelés van az első minőségi társításból a *Doboz* tesztelési csoport számára. A mennyiség 5. Nincs minőségi rendelés a második minőségi társításból, mivel az első minőségi társítás feltételei specifikusabbak a *Doboz* tesztcsoporthoz képest.
- Egy minőségi rendelés van a harmadik minőségi társításhoz az *Ellenállás* tesztelési csoport számára. A mennyiség 10. Nincs minőségi rendelés a negyedik minőségi társításból, mivel az első minőségi társítás feltételei specifikusabbak az *Ellenállás* tesztcsoporthoz képest.
- Egy minőségi rendelés van az ötödik minőségi társításhoz a *Kúp* tesztelési csoport számára. A mennyiség 1.

A három minőségi társítás mindegyikéhez a minőségi rendelés létrehozásával kapcsolatban létrejön a minőségi cikkmintavételi munka is. A regisztrált mennyiség csak 10. A cikkmintavételi-beállítás miatt azonban a minőségi rendelések mennyisége, amelyek létre lettek hozva a *Csak a raktári folyamatok minőségkezelése* vonatkozó raktártípushoz 16, amely meghaladja a 10 db-os fizikai regisztrált mennyiséget. Ezért a munka nem jön létre a teljes minőségi rendelési mennyiséghez (16), mert a minőség-ellenőrzési helyre szállításhoz csak 10 cikk érhető ténylegesen el. A minőségi cikkmintavételi munkafolyamatának létrehozásához alkalmazott prioritás a minőségi rendelés létrehozási sorrendjének követi:

- **Első minőségi rendelés (mennyiség = 5):** 5 db-os minőségi cikkmintavételi munka jön létre. Egy 5 db-os (10–5) mennyiség megmarad későbbi cikkmintavételi munkák létrehozásához.
- **Második minőségi rendelés (mennyiség = 10):** 5 db-os minőségi cikkmintavételi munka jön létre. 0 (nulla) mennyiség megmarad későbbi cikkmintavételi munkák létrehozásához.
- **Első minőségi rendelés (mennyiség = 1):** Nem jön létre minőségi cikkmintavételi munka.

A minőségi rendelések létrehozási folyamatának részeként egy 10 darabos készletzárolás jön létre. Ez a készletblokkolás hivatkozva lesz a három minőségi rendeléssel szemben. A minőségi rendelések mennyiségeinek összege 16.

A minőségi rendelések érvényesítése során a rendszer minden érvényesített minőségi rendeléshez megpróbál minőségi rendelési munkát létrehozni. Mivel a minőségi rendelések mennyiségének összege meghaladja a ténylegesen zárolt, így munka létrehozásához elérhető mennyiséget, a minőségi rendelési munka nem hozható létre a teljes minőségirendelés-mennyiséghez, ahogy itt látható. (Ez a példa a témakör előző példájának folytatása.)

1. **A létrehozott második minőségi rendelés ellenőrzése (mennyiség = 10). Minőségi rendelési munka jön létre 4 db mennyiséghez.**

    A minőségi rendelési munka létrehozását a készletblokkolás mennyiségének változása indítja el. Mivel a minőségi rendelési mennyiségek összege 16 volt, a 10 db ellenőrzése a fennmaradó ellenőrzendő minőségi rendelések száma 6 lesz. A készletzárolás mennyisége 10-ről 6-ra csökken. A csökkentett 4 db-os mennyiség minőségi rendelés munkalétrehozáshoz van hozzárendelve.

2. **A létrehozott első minőségi rendelés ellenőrzése (mennyiség = 5). Minőségi rendelési munka jön létre 5 db mennyiséghez.**

    A minőségi rendelési munka létrehozását a készletblokkolás mennyiségének változása indítja el. Mivel a minőségi rendelési mennyiségek összege 6 volt, a 5 db ellenőrzése a fennmaradó ellenőrzendő minőségi rendelések száma 1 lesz. A készletzárolás mennyisége 6-ről 1-ra csökken. A csökkentett 5 db-os mennyiség minőségi rendelés munkalétrehozáshoz van hozzárendelve.

3. **A létrehozott harmadik minőségi rendelés ellenőrzése (mennyiség = 1). Minőségi rendelési munka jön létre 1 db mennyiséghez.**

    A minőségi rendelési munka létrehozását a készletblokkolás mennyiségének változása indítja el. Mivel a minőségi rendelési mennyiségek összege 1 volt, a 1 db ellenőrzése a fennmaradó ellenőrzendő minőségi rendelések száma 0 (nulla) lesz. A rendszer eltávolítja a készletzárolást (azaz a készletzárolás mennyisége1-ről 0-ra csökken). A csökkentett 1 db-os mennyiség minőségi rendelés munkalétrehozáshoz van hozzárendelve.

> [!NOTE]
> A minőségi rendelés munka létrehozása az egy vagy több minőségi rendeléssel szemben hivatkozott készletzárolási mennyiségtől függ. Ha a minőségi rendelési mennyiségek összege meghaladja a hivatkozott készletzárolási mennyiségét, akkor a minőségi rendelések ellenőrzésének sorrendje határozza meg a minőségi rendelési munka létrehozását.

## <a name="canceling-quality-item-sampling-work"></a>Minőségi cikkmintavétel munka visszavonása

A minőségi cikkekmintavételéhez létrehozott munka érvényteleníthető. A következő lépésekkel szabályozhatja, hogy mi történjen, ha a munka érvénytelenítve van.

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. Az **Általános** lap **Munka** gyorslapján állítsa be a **Nyugta regisztrációjának megszüntetése munka érvénytelenítésekor** beállítást a következő értékek valamelyikére:

    - **Igen** – A minőségi cikkmintavételi munka érvénytelenítése esetén a hozzárendelt minőségi rendelés törlődik, és a készlet regisztrálása megszűnik.
    - **Igen** – A minőségi cikkmintavételi munka érvénytelenítése esetén a hozzárendelt minőségi rendelés nem törlődik, és a készlet regisztrálása nem szűnik meg.

## <a name="cross-docking"></a>Áttárolás

Lehet olyan minőségi társítási beállítása, amely cikkmintavételi munkát hoz létre. Ha azonban az áttárolás olyan minőségi társítással párhuzamosan történik, amely minőségi cikkmintavételezési munkát hozlétre, ha csak az áttároláshoz elegendő mennyiség áll rendelkezésre, akkor csak a cikkmintavételi munkafolyamat jön létre. Azokban az esetekben, amikor a **Minőségi rendelések engedélyezése a raktári folyamatokhoz** beállítás _Igen_ értékre van állítva a fogadó raktárban, és a **Vonatkozó raktár típusa** mező _Csak Raktári folyamatok minőségkezelése_ értékre van állítva egy minőségi hozzárendeléshez, akkor a minőségi cikkmintavételi munka elsőbbséget élvez az áttárolási munka létrehozásával szemben. Ha a mennyiség túllépi az áttárolási igényt, akkor a rendszer továbbra is csak a cikkmintavételi munkafolyamatot hozza létre.

## <a name="destructive-testing"></a>Romboló tesztelés

Romboló teszteket végrehajtó csoport is definiálható. Romboló teszt esetében a feltételezés az, hogy a teszt eredményétől függetlenül a tesztelt cikk a teszt részeként megsemmisül. Az a mód, ahogyan a _Raktári folyamatok minőségkezelése_ funkció támogatja a romboló teszteket, hasonlít ahhoz, ahogyan a minőségkezelés támogatja ezeket, ha ez a funkció nincsen bekapcsolva. A minőségi rendelés ellenőrzése előtt a minőségellenőrnek meg kell adnia a megsemmisült mennyiség kitárolási helyét. A kitárolást a minőségi rendelése lapról határozhatja meg a **Készet \> Kitárolás** lehetőség kiválasztásával a Műveleti panelről. Miután a minőségi rendelés mennyiségének kitárolását bejegyezték, az ellenőrzést végre lehet hajtani.

## <a name="example-scenario"></a>Példaforgatókönyv

### <a name="prepare-the-scenario"></a>A forgatókönyv előkészítése

A forgatókönyv elvégzéséhez a következő módon kell felkészíteni a rendszert:

- Győződjön meg róla, hogy a demó adatok telepítve vannak a rendszerben, és válassza ki az **USMF** jogi személyt.
- Kapcsolja be a _Raktári folyamatok minőségkezelése_ funkciót bekapcsolása a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) területen.
- A 51-es raktárt konfigurálja a _Raktári folyamatok minőségkezelése_ funkció használatára a következő lépésekkel:

    1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Raktárak** pontra.
    1. Válasszak ki a 51. raktárt.
    1. A **Raktár** gyorslapon állítsa be a **Minőségi rendelések engedélyezése a raktári folyamatokhoz** beállítást *Igen* értékre.

### <a name="quality-in-setup--move-to-the-quality-control-location"></a>Bejövő minőség beállítása – Áthelyezés a minőség-ellenőrzési helyre

Most el kell készítenie egy alapbeállítást, amely lehetővé teszi a rendszer számára, hogy támogassa a _Raktári folyamatok minőségkezelése_ funkciót az 51-es raktárban. (A demó adatok egy *QMS* nevű minőségirányítási helyet határoznak meg. Erre a helyet többször hivatkozunk ebben a forgatókönyvben.) A következő elemeket fogja előkészíteni a szakasz alszakaszaiban leírtak alapján:

- Munkaosztály
- Munkasablon
- Helyutasítások
- Cikkmintavétel
- Minőségi társítás
- Mobileszköz menüpontjai

#### <a name="work-class-for-quality-in"></a>Munkaosztály a bejövő minőséghez

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.
1. Hozzon létre egy munkaosztályt, és állítsa be a következő értékeket:

    - **Munkaosztály azonosítója:** _QualityIn_
    - **Leírás:** _Minőségi cikkmintavétel_
    - **Munkarendelés típusa:** _Minőségi cikkmintavétel_

#### <a name="work-template"></a>Munkasablon

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. Állítsa a **Munkarendelés típusa** mezőt _Minőségi cikkmintavétel_ értékre.
1. Hozzon létre egy munkasablont, és állítsa be a következő értékeket:

    - **Munkasablon:** _51 minőség_
    - **Munkasablon leírása:** _51 minőség_

1. Adjon hozzá egy sort a munkasablonhoz, és állítsa be a következő értékeket:

    - **Munka típusa:** _Kitárolás_
    - **Munkaosztály azonosítója:** _QualityIn_

1. Adjon hozzá egy második sort a munkasablonhoz, és állítsa be a következő értékeket:

    - **Munka típusa:** _Eltárolás_
    - **Munkaosztály azonosítója:** _QualityIn_

#### <a name="location-directive"></a>Helyutasítások

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. Állítsa a **Munkarendelés típusa** mezőt _Minőségi cikkmintavétel_ értékre.
1. Hozzon létre egy helyutasítást, és állítsa be a következő értékeket:

    - **Név:** _51 minőséghez_
    - **Munka típusa:** _Eltárolás_
    - **Telephely:** 5
    - **Raktár:** _51_

1. Adjon hozzá egy sort a helyutasításokhoz, és állítsa be a következő értékeket:

    - **Kezdő mennyiség:** _1_
    - **Záró mennyiség:** _1000000_

1. Hozzon létre egy helyutasítás-műveletet, és állítsa be a következő értéket:

    - **Név:** _Minőség_

1. Az új helyutasítás-művelethez válassza a **Lekérdezés szerkesztése** lehetőséget, és adja meg a következő értékeket tartalmazó **Tartomány** rekordot:

    - **Tábla:** *Helyek*
    - **Mező:** _Hely profilazonosítója_
    - **Feltételek:** *QMS*

1. Kattintson az **OK** gombra a lekérdezés mentéséhez és az új helyutasítások mentéséhez.

Ezután módosítania kell a meglévő beszerzési rendelés helyutasításokat az 51-es raktárhoz. A demóadatok között szerepel két olyan helyutasítás amelynél van **Beszerzési rendelés típusa** érték a _Beszerzéshez_: az egyik neve _51 QMS_ a másik pedig _51 PO Direct_. Annak érdekében, hogy a 51 raktárra a *Raktári folyamatok minőségkezelése* funkció alkalmazva legyen, meg kell győződnie arról, hogy az _51 QMS_ helyutasítás nincs alkalmazva. Ugyanakkor, ahelyett, hogy törölné a helyutasítást (mivel előfordulhat, hogy a későbbiekben is használni szeretné), azt is megteheti, hogy csak a sorozatot módosítja.

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A **Munkarendelés típusa** mezőt állítsa be _Beszerzési rendelés_ értékre.
1. A sorszám listában válassza ki az 5. sorszámot az _51 PO Direct_ helyutasításhoz.
1. A kiválasztott sorozatot helyezze át a 4-es sorszámra.
1. Győződjön meg róla, hogy az _51 QMS_ helyirányelv sorozatszáma legalább 5.

#### <a name="item-sampling"></a>Cikkmintavétel

A _Raktári folyamatok minőségkezelése_ funkció számos új cikkmintavételi képességet ad hozzá. A **Mintavétel hatóköre** értéke immár lehet _Rendelés_, _Szállítmány_ vagy _Rakomány_, és a **Mintavételi mennyiség** értéke immár lehet _Teljes azonosítótábla_.

1. Ugorjon a következőhöz: **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Cikkmintavétel**.
1. Hozzon létre egy cikkmintavételi rekordot, és adja meg a következő értékeket:

    - **Cikkmintavétel:** _3. LP_
    - **Leírás:** _Minden harmadik azonosítótábla_
    - **Mintavétel hatóköre** _Rendelés_

1. A **Mintavételi mennyiség** gyorslapon állítsa be a **Mennyiség meghatározása** mezőt _Teljes azonosítótábla_ értékre.
1. A **Folyamat** gyorslapon állítsa be az **N. azonosítótáblánként** mezőt _3_ értékre.
1. A **Tárolási dimenziónként** területen engedélyezze a **Raktár** és a **Készletállapot** elemeket.

#### <a name="quality-associations"></a>Minőségi társítások

Hozzon létre egy minőségi társítást, amely az új cikkmintavételt fogja használni.

1. Ugorjon a következőhöz: **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Minőségi társítások**.
1. Hozzon létre egy minőségi társítási rekordot, és adja meg a következő értékeket:

    - **Hivatkozás típusa:** _Beszerzés_
    - **Cikk-kód:** _Tábla_
    - **Cikk:** _M9201_
    - **Telephely:** _5_

1. A **Folyamat** gyorslapon állítsa be az **Eseménytípus** mezőt *Regisztráció* értékre.
1. A **Feltételek** gyorslapon a **Vonatkozó raktártípus** mezőt állítsa be *Csak raktári folyamatok minőségkezelése* értékre.
1. A **Minőségi rendelés folyamat** gyorslapján a **Minőségfolyamat házirendje** mezőt állítsa be _Minőségi rendelés létrehozása_ értékre.
1. Kattintson a jobb gombbal a **Specifikációk** gyorslap **Tesztcsoport** mezőjébe, majd válassza a **Részletek megtekintése** parancsot a **Tesztcsoportok** lap megnyitásához.
1. Hozzon létre egy tesztet a **Tesztcsoportok** oldalon a felső rács **Áttekintés** lapján, és adja meg a következő értékeket:

    - **Tesztcsoport:** _QMS_
    - **Leírás:** _QMS teszt_
    - **Elfogadható mennyiség:** _100_
    - **Cikkmintavétel:** _3. LP_ (kiválasztás)

1. Az alsó rács **Áttekintés** lapján adjon hozzá egy rekordot egy teszthez, és adja meg a következő értékeket:

    - **Sorozat:** *1*
    - **Teszt:** *Doboz mérése*

1. Az alsó rács **Teszt** lapján adja meg a következő értékeket:

    - **Tesztváltozók:** *Megfelelt / Nem felelt meg*
    - **Alapértelmezett eredmény:** *Megfelelt*

1. Mentse az új tesztcsoportot, és zárja be a **Tesztcsoportok** lapot.
1. Ismét a **Minőségi társítások** lapon a **Tesztcsoport** mezőjében válassza ki a **QMS** lehetőséget.
1. Mentse a rekordot.

#### <a name="mobile-device-menu-items-for-quality-in"></a>Mobileszköz menü elemei a bejövő minőséghez

A beállítás befejezéséhez, hogy az áruk a minőség-ellenőrzési helyre legyenek áthelyezve, akkor egy mobileszköz-menüelemből elérhetővé kell tennie a cikkmintavételi munkát.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. Válassza ki a **Beszerzés eltárolása** mobileszköz menüelemet.
1. A **Munkaosztályok** gyorslapon adja hozzá a *QualityIn* munkaosztály-azonosítót.

#### <a name="summary-your-setup-to-move-goods-to-quality-control"></a>Összefoglalás: Az áruk minőség-ellenőrzésre történő áthelyezésének beállítása

Immár definiált egy minőségi társítást, amely a *Raktári folyamatok minőségkezelése* funkciót használja egy minőségi rendelés létrehozásának elindításához. A 51 raktárhoz beállította a munka- és a helyadatokat, hogy biztosítsa a specifikus munka létrehozását, amikor megtörténik a beszerzési regisztráció az M9201 cikkhez. Ez a beállítás gondoskodik arról, hogy minden harmadik regisztrált azonosítótábla egy minőségellenőrzési helyre kerüljön (_QMS_), és hogy a program minőségi rendelést hozzon létre az azonosítótábla mennyiségéhez. Minden mást áthelyez a program az elraktározásba a minőség-ellenőrzési hely helyett.

### <a name="process-quality-management-work"></a>Minőségkezelési munka feldolgozása

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Hozzon létre egy beszerzési rendelést, és állítsa be a következő értékeket:

    - **Konkrét szállítói számla_** *104*
    - **Raktár:** *51*

1. Adjon hozzá egy beszerzésirendelés-sort, és állítsa be a következő értékeket:

    - **Cikk:** *M9201*
    - **Mennyiség:** *20*
    - **Mértékegység:** *ea*
    - **Raktár:** *51*

1. Írja le a beszerzési rendelés számát, hogy később felhasználhassa.
1. Lépjen át a raktári alkalmazást futtató mobileszközre vagy emulátorra, majd jelentkezzen be a 51-es raktárba – a felhasználói azonosító legyen *51* és a jelszó legyen *1*.
1. Nyissa meg a **Bejövő \> Beszerzés fogadása** elemet, és írja be a következő értékeket:

    - **PONum:** Az imént létrehozott beszerzési rendelés száma
    - **Mennyiség:** *5*
    - **Egység:** *ea*

1. Folytassa a bevételezést a sorral szemben, egyszerre *5 ea* értékkel, amíg a sor nincs teljesen bevételezve. (Összesen négy azonosítótábla jön létre.)
1. Jelentkezzen ki a raktári alkalmazásból.
1. Ismét a webes ügyfélben ugorjon a **Beszerzés és forrás \> Beszerzési rendelések \> Összes beszerzési rendelés** elemre.
1. A beszerzési rendelés megkeresése és megnyitása.
1. A **Beszerzésirendelés-sorok** szakaszban válassza ki az *M9201* cikkszám sorát, majd válassza a **Beszerzésirendelés-sorok \> Munkaadatok** lehetőséget.
1. Figyelje meg, hogy a létrehozott második és a harmadik munkafejléc szabályos elraktározási munka, míg az első és a negyedik munkafejléc a minőségi cikkmintavételi munka. Ez az eredmény megfelel cikkmintavételi beállításoknak, amely úgy van beállítva, hogy minden harmadik azonosítótábla esetében legyen mintavétel.

#### <a name="move-to-the-quality-control-location"></a>Átlépés a minőség-ellenőrzési helyre

Ekkor az azonosítótáblákat a kijelölt helyükre helyezi át. Az első és a negyedik azonosítótábla a minőség-ellenőrzési helyre fog kerülni, míg a második és a harmadik azonosítótábla közvetlenül a tárhelyre fog menni.

1. Lépjen át a raktári alkalmazást futtató mobileszközre vagy emulátorra, majd jelentkezzen be a 51-es raktárba – a felhasználói azonosító legyen *51* és a jelszó legyen *1*.
1. Nyissa meg a **Bejövő \> Beszerzés eltárolása** lehetőséget, és tárolja el az összes azonosítótáblát a korábbi eljárásból mindaddig, amíg az összes munkát le nem zárta.

#### <a name="summary-process-quality-management-work"></a>Összefoglalás: Minőségkezelési munka feldolgozása

Most futtatta az első és a negyedik azonosítótáblához a cikkmintavételi munkafolyamatot azok a minőség-ellenőrzési helyre történő áthelyezésével. A második és a harmadik azonosítótáblákat is eltárolta. A következő lépés a minőségi rendelés tesztelése és ellenőrzése.

### <a name="quality-out-setup-move-from-the-quality-control-location-to-storage-or-return"></a>Kimenő minőség beállítása: Áthelyezés a minőség-ellenőrzési helyről a tárolásba vagy visszaküldésre

Amikor a dolgozók a minőségi rendelés eredményeit jelentik, a rendszer automatikusan létrehoz munkát.

Ezután folytatja a munkaosztály, a munkasablon és a helyutasítások szükséges alapbeállításaival, hogy a raktárkezelési folyamatokhoz engedélyezze a minőségkezelést, hogy a szükséges munka létrehozható legyen hogy a minőség-ellenőrzési helyről áthelyezze a minőségi rendelési mennyiségét a kijelölt raktárba.

#### <a name="work-class-for-quality-out"></a>Munkaosztály a kimenő minőséghez

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.
1. Hozzon létre egy munkaosztályt, és állítsa be a következő értékeket:

    - **Munkaosztály azonosítója:** *QualityOut*
    - **Leírás:** *Kimenő minőség*
    - **Munkarendelés típusa:** *Minőségi rendelés*

#### <a name="work-templates"></a>Munkasablonok

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A **Munkarendelés típusa** értékét módosítsa *Minőségi rendelésre*.
1. Hozzon létre egy munkasablont, és állítsa be a következő értékeket:

    - **Munkasablon:** *51 kimenő minőség*
    - **Munkasablon leírása:** *51 kimenő minőség*

1. Adjon hozzá egy sort, és állítsa be a következő értékeket:

    - **Munka típusa:** *Kitárolás*
    - **Munkaosztály azonosítója:** **QualityOut**

1. Adjon hozzá egy második sort, és állítsa be a következő értékeket:

    - **Munka típusa:** *Eltárolás*
    - **Munkaosztály azonosítója:** *QualityOut*

#### <a name="location-directives"></a>Helyutasítások

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A **Munkarendelés típusa** értékét módosítsa *Minőségi rendelésre*.
1. Hozzon létre egy helyutasítást, és állítsa be a következő értékeket:

    - **Név:** *51 átadás*
    - **Munka típusa:** *Eltárolás*
    - **Telephely:** *5*
    - **Raktár:** *51*

1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget a lekérdezés-szerkesztő párbeszédpanel megnyitásához.
1. A **Tartomány** lapon állítsa be a következő értékeket:

    - **Tábla:** *Minőségi rendelések*
    - **Mező:** *Állapot*
    - **Feltétel:** *Megfelelt*

1. Az **OK** gombra kattintva mentse a lekérdezést, és zárja be a párbeszédpanelt.
1. A **Sorok** gyorslapon adjon hozzá egy sort, és állítsa be a következő értékeket:

    - **Kezdő mennyiség:** *1*
    - **Záró mennyiség:** *1000000*

1. A **Helyutasítások műveletei** gyorslapon adjon hozzá egy sort, és adja meg a következő értéket:

    - **Név:** *Megfelelt*

1. A **Helyutasítások műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget a lekérdezés-szerkesztő párbeszédpanel megnyitásához.
1. A **Tartomány** lapon állítsa be a következő értékeket:

    - **Tábla:** *Helyek*
    - **Mező:** *Zóna azonosítója*
    - **Feltétel:** *ömlesztett*

1. Az **OK** gombra kattintva mentse a lekérdezést, és zárja be a párbeszédpanelt.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget az új helyutasítások mentéséhez.
1. Hozzon létre egy második helyutasítást, és állítsa be a következő értékeket:

    - **Név:** *51 Nem felelt meg*
    - **Munka típusa:** *Eltárolás*
    - **Telephely:** *5*
    - **Raktár:** *51*

1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget a lekérdezés-szerkesztő párbeszédpanel megnyitásához.
1. A **Tartomány** lapon állítsa be a következő értékeket:

    - **Tábla:** *Minőségi rendelések*
    - **Mező:** *Állapot*
    - **Feltétel:** *Nem felelt meg*

1. Az **OK** gombra kattintva mentse a lekérdezést, és zárja be a párbeszédpanelt.
1. A **Sorok** gyorslapon adjon hozzá egy sort, és állítsa be a következő értékeket:

    - **Kezdő mennyiség:** *1*
    - **Záró mennyiség:** *1000000*

1. A **Helyutasítások műveletei** gyorslapon adjon hozzá egy sort, és adja meg a következő értéket:

    - **Név:** *Nem felelt meg*

1. A **Helyutasítások műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget a lekérdezés-szerkesztő párbeszédpanel megnyitásához.
1. A **Tartomány** lapon állítsa be a következő értékeket:

    - **Tábla:** *Helyek*
    - **Mező:** *Zóna azonosítója*
    - **Feltétel:** *Visszaküldés*

1. Az **OK** gombra kattintva mentse a lekérdezést, és zárja be a párbeszédpanelt.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget az új helyutasítások mentéséhez.

#### <a name="mobile-device-menu-items-for-quality-out"></a>Mobileszköz menü elemei a kimenő minőséghez

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. Válassza ki a **QMS eltárolás** mobileszköz menüelemet.
1. A **Munkaosztályok** gyorslapon adja hozzá a *QualityPut* munkaosztály-azonosítót.

A raktári dolgozók ezentúl minőségi rendelési munkát kiválaszthatják a **QMS elraktározás** menüpont segítségével. Azok az áruk, amelyek nem feleltek meg a minőségellenőrzésen a visszaküldési helyre helyezhetők, és az megfelelt áruk a bulk-001 helyre helyezhetők el.

#### <a name="summary-your-setup-to-move-goods-from-quality-control"></a>Összefoglalás: Az áruk minőség-ellenőrzésről történő áthelyezésének beállítása

A 51 raktárhoz beállította a munka- és a helyadatokat, hogy biztosítsa a munka létrehozását, a minőségi rendelések befejezésekor. Ez a beállítás gondoskodik arról, hogy az egyes minőségellenőrzött azonosítótábla átkerüljön a tömeges helyre vagy a visszaküldési helyre.

### <a name="process-quality-management-work"></a>Minőségkezelési munka feldolgozása

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** lehetőségre.
1. A regisztrált mennyiségek első minőségi rendelését válassza ki.
1. A **Validálás** kiválasztása. Az teszt állapota *Nem felelt meg* értékre frissül.
1. Ugrás a **Raktárkezelés \> Minden munka** lehetőségre.
1. Nyissa meg az imént létrehozott munkát, és figyelje meg, hogy a **Munkarendelés típusa** értéke *Minőségi rendelés*. A munka tartalmaz egy sort, amelyben a betárolási hely a *Visszaküldés*, az állapot pedig *Nem felelt meg*. (Ha a minőségi rendelés állapota *Megfelelt*, az eltárolási hely *Ömlesztett* lenne ehelyett.)
1. Lépjen vissza a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** lehetőségre.
1. A regisztrált mennyiségek második minőségi rendelését válassza ki.
1. Az alsó rács fölötti válassza ki az **Eredmények** lehetőséget. Frissítse az **Eredményként kapott mennyiség** értékér *5*-re, és ellenőrizze, hogy a **Teszteredmény** érték ki van-e pipálva.
1. Válassza az **Ellenőrzés** gombot, és zárja be az oldalt.
1. Visszatérve a **Minőségi rendelések** lapra válassza az **Ellenőrzés** elemet, és végezze el az ellenőrzést. Az állapota *Megfelelt* értékre frissül.

    > [!NOTE]
    > Az ellenőrzési esemény elindítja a minőségi rendelés munkájának létrehozását, hogy a mennyiséget a minőség-ellenőrzési helyről egy új helyre vigye.

1. Ugrás a **Raktárkezelés \> Minden munka** lehetőségre.
1. Válassza ki az imént létrehozott munkát, és figyelje meg, hogy létrejött egy második minőségi rendelési munkafejléc, ahol az betárolásai hely *BULK-001*.
1. Lépjen át a raktári alkalmazást futtató mobileszközre vagy emulátorra, majd jelentkezzen be a 51-es raktárba – a felhasználói azonosító legyen *51* és a jelszó legyen *1*.
1. Ugorjon a **Minőség \> Betárolás QMS-ből** elemre, dolgozza fel mind a két munkához kapcsolódó azonosítótáblát, hogy minden munka le legyen zárva.

> [!NOTE]
> Fontolja meg a kimenő minőség bejegyzés hozzáadását egy mobileszköz-menüelemhez, ahol a tevékenység kódja *Nyitott munkalista megjelenítése*. Példaként megtekintheti a **Munkalista** nevű mobileszköz munkaelemet a demóadatok között. A *Minőségi rendelés* munkaosztályt először adja hozzá felhasználó által irányított menüelemhez adja hozzá, mivel ez a munkaosztály szükséges munka megjelenítéséhez a munkalistában. Ezután vegye fel a *Minőségi rendelés* munkaosztályt a **Munkalista** menüelembe. Azok a felhasználóknak, akik hozzáférnek a munkalistához, ezután ki tudják választani és fel tudják dolgozni a minőségi rendelés ellenőrzése által automatikusan létrehozott munkát.
