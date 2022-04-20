---
title: Előfizetés számlázási halasztástranzakciói
description: Ez a témakör olyan tranzakciókat ír le, amelyek a halasztások tranzakcióiban felhasználhatók az előfizetési számlázás bevételének és költség halasztásának részeként.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: f66c538afc732caf3faed3cfea6c695ff7f16273
ms.sourcegitcommit: d0e99545d722c924db57ae2bd06f72154a1f1f97
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/08/2022
ms.locfileid: "8557971"
---
# <a name="deferral-default-transactions"></a>Halasztás alapértelmezett tranzakciói

Ez a témakör azokat a tranzakciókat írja le, amelyek bevétel- és költség halasztásokat engedélyeznek. A halasztások ütemezése mindig egy eredeti dokumentumon vagy számlázási ütemezésen alapul, és attól függ. A halasztások ütemezésének létrehozása az alapértelmezések alapján történik, és nem lehet külön megadni vagy létrehozni.

## <a name="sales-order-transaction-deferral"></a>Értékesítési rendelés tranzakció - halasztás

A Halasztások **vagy** **a Jóváírás létrehozása** lapon lehet megadni vagy módosítani az értékesítésirendelés-sor halasztás paramétereit.

> [!NOTE]
> Ha számlázási ütemezés alapján hoz létre értékesítési rendelést, **·** **a** Halasztások vagy a Jóváírás létrehozása lapon található összes érték írásra olvasható, és a halasztások paraméterei nem szerkeszthetők. Az értékek szerkesztéséhez használja az Ütemezés **módosítása lapot**.

### <a name="edit-deferral-options"></a>Halasztás beállításainak szerkesztése

A sorok halasztási beállításainak szerkesztéséhez kövesse ezeket a lépéseket.

1. Hozzon létre egy értékesítésirendelés-tranzakciót.
2. Válassza ki a sort, majd válassza ki **a Halasztások lehetőséget**.
3. A Tranzakció **halasztás lapján** a **Halasztás** beállítást Igen beállításra kell **állítani**. Szükség szerint szerkessze a további mezőket.
4. A halasztás ütemezésének előzetes megtekintéséhez válassza az Előnézet **lehetőséget**.
5. Ha módosításokat végrehajtott a tranzakció halasztásán, válassza az **OK** gombra, majd térjen vissza a tranzakcióoldalra.
6. Véglegesítés és a tranzakció feladja.

A tranzakció feladása után a **halasztás** ütemezésének megtekintéséhez nyissa meg az Összes halasztás ütemezése lapot.

### <a name="create-a-credit-note"></a>Jóváírás létrehozása

Munkafolyamat létrehozásához kövesse az alábbi lépéseket.

1. Hozzon létre egy értékesítésirendelés-tranzakciót.
2. Az Értékesítésirendelés-sorok **szakaszban** válassza ki azt a cikket, amelyhez jóváírást szeretne létrehozni.
3. Válassza az **Új értékesítésirendelés-sort** \> **·**, majd a Jóváírás **lehetőséget.**
4. Halasztások **kiválasztása**.
5. Az Értékesítési rendelés **tranzakció halasztása lapon** állítsa **·** **a cikk meglévő ütemezésének Beállítása Igen** beállításra.
6. A Módosított **ütemezés mezőben** válassza ki azt a halasztás-ütemezést, amelybe a jóváírást alkalmazni szeretné.
7. Szükség szerint **frissítse a Dátum és** **záró** dátum újraszámítása mezőt.
8. Válassza ki az **OK** lehetőséget.
9. Az értékesítési rendelési tranzakció feladásának befejezése.

### <a name="purchase-orders-and-purchase-invoices"></a>Beszerzési rendelések és beszerzési számlák

Ha a halasztás funkciót szeretné használni egy beszerzési rendeléshez, először generálja a számlát. Ezután a Függőben lévő **szállítói számlák lapon** szerkesztheti és hozzáadhatja a halasztás cikkeket. Beszerzési rendelésen nem lehet közvetlenül halasztásokat szerkeszteni és hozzáadni.

1. A Függőben **lévő szállítói számlák lapon** lehet megadni egy szállítói számlát.

    Sor beírása esetén a halasztás automatikusan be lesz állítva a kiválasztott cikkhez vagy beszerzési kategóriához. Ez a halasztás a halasztás alapértelmezett **lapján beállított halasztáson** alapul. A halasztások a felosztás szintjén szerkeszthetők és hozzáadhatók.

3. A beszerzési sorban válassza a Pénzügyi **elosztás – összegek beállítását \>**.
4. Minden felosztási összeghez válassza ki a **halasztásokat**. A számla feladása során a halasztás ütemezése minden olyan felosztáshoz létrejön, amelybe be van állítva halasztás.

### <a name="tax"></a>Adó

Bizonyos esetekben az adóösszeg részben vagy teljesen vissza nem térhető lehet. Ha egy halasztható sor adóösszege nem visszahajtható összeget tartalmaz, akkor a nem visszahajtható adóösszeg a számla feladott ütemezési összegében fog szerepelni a halasztható ütemezésben.

### <a name="variance"></a>Eltérés

Ha a szállítói számla sorában szereplő összeg eltér a beszerzési rendelés sorában szereplő összegtől, különbözetek felosztása jön létre. Ha a sor halasztás, akkor ezeknek a felosztásoknak a főkönyvi számlája a halasztás számlájára lesz állítva, és a számla feladott ütemezési összegében az összegek szerepelnek a halasztható ütemezés összegében. Az ilyen felosztások neve Áreltérés **és Költségeltérés** **.**

### <a name="general-journals-and-invoice-journals"></a>Általános naplók és számlanaplók

A Halasztások **lapon** megadhatja a naplóbizonylatsorok halasztás paramétereit. A halasztások ütemezését előnézetben is megtekintheti a straight line halasztásoknál. Sor beírása esetén **a halasztás beállítása automatikusan történik a halasztások alapértelmezései lapon beállított halasztások alapján**. Az egyes sorokhoz kézzel módosíthatja a halasztás beállításait. A naplóbizonylat feladásakor létrejön a halasztás ütemezése.

#### <a name="post-and-transfer"></a>Feladás és átvitel

A naplóbizonylat feladására használja a Feladás **és átvitel parancsot**. A halasztás beállításai azt a sort követik, amelyre a bizonylat vonatkozik. Halasztás esetén a program halasztás ütemezést hoz létre az olyan bizonylatok számára, amelyek nem tartalmaznak hibát. Hibás bizonylatok esetén a halasztások átvitele is meg történik.

#### <a name="tax"></a>Adó

Bizonyos esetekben az adóösszeg részben vagy teljesen vissza nem térhető lehet. Ha egy halasztható sor adóösszege nem visszahajtható összeget tartalmaz, akkor a nem visszahajtható adóösszeg a számla feladott ütemezési összegében fog szerepelni a halasztható ütemezésben.

## <a name="free-text-invoice-transaction-deferral"></a>Szabadszöveges számlatranzakció halasztása

A Halasztások **lapon** lehet megadni a szabadszöveges számlasorok felosztásának halasztásparaméterét. Felosztás megadásakor **a halasztás automatikusan be van állítva a Halasztás alapértelmezései lapon megadott halasztások beállításai** alapján.

## <a name="fields"></a>Mezők

A **Tranzakció halasztás lapja** a következő mezőket tartalmazza.

| Mező | Leírás |
|-------|-------------|
| Halasztott | <p>Adja meg, hogy a sor halasztás-e:</p><ul><li>**Igen** – a sor halasztás.</li><li>**Nem** – a sor nem halasztás.</li></ul><p>Ha ez a beállítás **Igen**, a Meglévő **ütemezés** beállítása beállítás nem érhető el. Halasztottként már beállított cikkek és költségek esetén ez a beállítás **Igen**. Halasztottként nem beállított cikkek és költségek esetén ezt a beállítást Igen értéken kell **beállítani**.</p> |
| Meglévő ütemezés módosítása | <p>Adja meg, hogy a sor egy meglévő halasztás-ütemezés helyesbítése-e:</p><ul><li>**Igen** – az új értékesítési sor egy meglévő halasztás-ütemezés helyesbítése. Ebben az esetben a Halasztás ütemezése a Módosított **ütemezés mezőben választható** ki.</li><li>**Nem** – az új értékesítési sor nem egy meglévő halasztás-ütemezés helyesbítése.</li></ul><p>Ha ez a beállítás **Igen**, a Halasztott **lehetőség** nem érhető el.</p> |
| Módosított ütemezés | <p>Válassza ki a sor korrigált halasztás-ütemezését. A lapon található összes érték frissül a származási halasztás ütemezésének értékeivel. Ezek az értékek nem szerkeszthetők.</p><p>Ez a mező csak akkor érhető el, ha **a Meglévő ütemezés** beállítása beállítás Igen **.**</p> |
| Újraszámítás dátuma | <p>Adja meg annak az időszaknak a kezdő dátumát, amelyből újra szeretnészámozni a fennmaradó összeget. Az alapértelmezett dátum a következő fel nem ismert időszak dátuma.</p><p>Ez a mező csak akkor érhető el, ha **a Meglévő ütemezés** beállítása beállítás Igen **.**</p> |
| Záró dátum | <p>A halasztás típusától függően előfordulhat, hogy a záró dátum nem frissül:</p><ul><li>Halasztásos straight line típusú halasztásoknál adja meg az ütemezés új záró dátumát. Az alapértelmezett érték a halasztás ütemezésének meglévő záró dátuma.</li><li>Halasztáson alapuló esemény esetén adja meg a jóváírási esemény sorának záró dátumát. Ez a dátum üresen is marad.</li></ul><p>Ez a mező csak akkor érhető el, ha **a Meglévő ütemezés** beállítása beállítás Igen **.**</p> |
| Számlázási ütemezés száma | <p>A számlázási ütemezés száma.</p><p>Ez a mező csak ismétlődő szerződéses számlázási ütemezések esetében érhető el.</p> |
| Halasztás-kiigazítás módja | <p>A halasztott helyesbítési mód. Az érték megegyezik az ismétlődő szerződés számlázási ütemezésének **tömeges felmondási** feldolgozási lapján található értékkel.</p><p>Ez a mező csak ismétlődő szerződéses számlázási ütemezések esetében érhető el.</p> |
| **Számlák - bevétel** | |
| Halasztási számla | <p>A halasztott számla, amely az **Értékesítési rendelés lapon megjelenő feladási** számla.</p><p>Ha a sor nincs elhalasztva, ez a mező üres. Ebben az esetben a feladási számla az alapértelmezett bevételi számla.</p> |
| Elszámolási számla | <p>Adja meg a halasztás ismerhető felében használt számlát. Ennek a számlának különböznie kell a halasztás számlájától.</p><p>Ha a **Halasztás** lehetőség kezdetben **Igen**, a halasztás számláján használt dimenzióértékeket a program átmásolja a felismerési számlára. Ha a halasztott számlán nem létezik a dimenzió az elismert számlához, akkor a program figyelmen kívül hagyja.</p> |
| Kezdeti elszámolási számla | <p>Válassza ki a kezdeti bevétel-kimutatás számláját. Az alapértelmezett érték a Halasztás **alapértelmezései lapon található**.</p><p>Ez a mező csak akkor érhető el **, ha a Halasztás** **·** **feladási mód mezőjének beállítása Eredmény a Bevétel- és költség halasztások paraméterei oldalon.**</p> |
| Elszámolási ellenszámla | <p>Az árbevétel-ellentételezési kimutatás számlájának kiválasztása. Az alapértelmezett érték a Halasztás **alapértelmezései lapon található**.</p><p>Ez a mező csak akkor érhető el **, ha a Halasztás** **·** **feladási mód mezőjének beállítása Eredmény a Bevétel- és költség halasztások paraméterei oldalon.**</p> |
| **Számlák - Engedmény** | Ez a szakasz csak a halasztott cikkeknél jelenik meg. El van rejtve a halasztott költségek elől. |
| Halasztási számla | <p>Az engedményes halasztás számlaszámának megadása. Az alapértelmezett érték a Halasztás **alapértelmezései lapon található**.</p><p>Ez a mező csak **akkor** **·** **érhető el, ha az Engedmény halasztása beállítás beállítása Külön ütemezés az engedményhez a Bevétel-** és költség halasztások paraméterei oldalon, és a sorra engedmény vonatkozik.</p> |
| Elszámolási számla | <p>Az engedmény-felismerési számla számának megadása. Az alapértelmezett érték a Halasztás **alapértelmezései lapon található**.</p><p>Ez a mező csak **akkor** **·** **érhető el, ha az Engedmény halasztása beállítás beállítása Külön ütemezés az engedményhez a Bevétel-** és költség halasztások paraméterei oldalon, és a sorra engedmény vonatkozik.</p> |
| Kezdeti elszámolási számla | <p>Válassza ki a kezdeti engedmény-felismerés számláját. Az alapértelmezett érték a Halasztás **alapértelmezései lapon található**.</p><p>Ez a mező csak **akkor** **·** **érhető** el, ha a Halasztás feladási mód mezőjében a Bevétel és költség halasztások paraméterei oldalon az Eredmény érték van beállítva, és a sorra engedmény vonatkozik.</p> |
| Elszámolási ellenszámla | <p>Az árbevétel-ellentételezési kimutatás számlájának kiválasztása. Az alapértelmezett érték a Halasztás **alapértelmezései lapon található**.</p><p>Ez a mező csak **akkor** **·** **érhető** el, ha a Halasztás feladási mód mezőjében a Bevétel és költség halasztások paraméterei oldalon az Eredmény érték van beállítva, és a sorra engedmény vonatkozik.</p> |
| **Számlák - felhasználás** | Ez a szakasz csak a halasztott cikkeknél jelenik meg. El van rejtve a halasztott költségek elől. |
| Halasztási számla | <p>A felhasználási halasztás számlaszámának megadása.</p><p>Alaptermékek esetében két halasztás ütemezés jön létre:</p><ul><li>**Normál értékesítés** – olyan bevételi ütemezés, amely követel egyenleggel rendelkezik. Ebben az esetben válassza ki a felhasználási halasztás számláját.</li><li>**Felhasználás** – egy terhelési egyenleggel \[rendelkező felhasználás (eladott áruk költségének ELÁBÉ\]) ütemezése. Ebben az esetben válassza ki a felhasználás-felismerési számlát.</li></ul><p>A számla feladott összege a megadott felhasználási halasztás számlájára lesz feladva. Ezek a mezők szolgáltatási cikkeknél nem érhetők el.</p> |
| Elszámolási számla | A felhasználás-felismerési számlaszám megadása. |
| Kezdeti elszámolási számla | <p>A felhasználás kezdeti felismerési összegének számlaszáma. Az alapértelmezett érték a Halasztás **alapértelmezései lapon található**.</p><p>Ez a mező csak akkor érhető el **, ha a Halasztás** **·** **feladási mód mezőjének beállítása Eredmény a Bevétel- és költség halasztások paraméterei oldalon.**</p> |
| Elszámolási ellenszámla | <p>Adja meg a felhasználás-elismert ellenszámla összegét. Az alapértelmezett érték a Halasztás **alapértelmezései lapon található**.</p><p>Ez a mező csak akkor érhető el **, ha a Halasztás** **·** **feladási mód mezőjének beállítása Eredmény a Bevétel- és költség halasztások paraméterei oldalon.**</p> |
| **Ütemezés** | |
| Ütemezés típusa | <p>Válassza ki a halasztás ütemezésének típusát: **Straight line** (default) **vagy Event based**.</p><p>A lapon megjelenő beállítások a kiválasztott halasztás ütemezési típusán alapulnak.</p><p>Ha az alapértelmezett sablon **a** tranzakciósor Halasztás alapértelmezései lapon van beállítva, akkor a halasztás ütemezési típusa a kiválasztott sablon típusán alapul.</p> |
| **Ütemezés – egyenes** | |
| Megelőző időszakok összesítése | <p>Adja meg, hogy összevonja-e a korábbi időszakok halasztás-ütemezési sorait:</p><ul><li>**Igen** – korábbi időszakok halasztás-ütemezési sorainak összesítése.</li><li>**Nem** – ne vonja össze a korábbi időszakok halasztás-ütemezési sorait.</li></ul><p>Az alapértelmezett érték a Bevételi **és kiadási halasztások paraméterei lapon található**.</p> |
| Időszakonként egyenlő | <p>Adja meg, hogy a napok száma minden időszakban egyenlő vagy időszakonként eltérő legyen:</p><ul><li>**Igen** – minden időszakban megegyezik a napok száma.</li><li>**Nem** – az időszakoknak nem azonos a napok száma.</li></ul><p>Ha ez a beállítás **Nem**, akkor a program az időszak napjainak számát számítja ki, amikor kiszámítja az egyes halasztások ütemezésének összegét az egyes időszakban.</p><p>Az alapértelmezett érték a Bevételi **és kiadási halasztások paraméterei lapon található**.</p> |
| Ütemezés sablonból | <p>Adja meg, hogy a halasztás ütemezése sablon vagy záró dátum alapján jön-e létre:</p><ul><li>**Igen** – a halasztás ütemezése sablon alapján jön létre.</li><li>**Nem** – a halasztás ütemezése a záró dátum alapján jön létre.</li></ul> |
| Sablon | Válassza ki a halasztássablont. |
| Kezdő dátum felülbírálása | <p>Adja meg, hogy felül szeretné-e bírálni a kezdő dátumot:</p><ul><li>**Igen** – a kezdő dátum felülbírálata a Kezdő dátum mezőben beírható **dátummal**.</li><li>**Nem** – a kezdő dátum **az** **alapértelmezett halasztás kezdő dátumszabálya, amely a Számlafeladás lapon megadott számladátumra vonatkozik.** Ez a szabály a Bevételi és kiadási halasztások **paraméterei oldalon lehet** beállítani.</li></ul> |
| Halasztás kezdő dátuma | Adja meg a halasztás kezdő dátumát. Az alapértelmezett érték a tranzakció dátuma. |
| Halasztás záró dátuma | <p>A halasztás záró dátuma.</p><p>A program automatikusan kiszámítja ezt a dátumot a halasztássablon alapján. Ha nincs kiválasztva sablon, manuálisan kell megadnia a dátumot.</p> |
| **Ütemezés – eseményalapú** | |
| Sablon | <p>Válassza ki az esemény alapú sablont. A mező kitöltése nem kötelező.</p><p>Ha kiválaszt egy sablont, akkor a sablonban megadott értékek felülírják az eseményalapú adatokat és eseménysorokat.</p> |
| Foglalás típusa | <p>Válassza ki az eseménysorok felosztási típusát:</p><ul><li>**Változó összegek** – minden sorban egy meghatározott felosztási összeg van megadva.</li><li>**Egyenlő összegek** – az összeg felosztása egyenlően megegyezik minden sorban.</li><li>**Százalék** – az összeg felosztása az egyes sorokban megadott százalékérték alapján.</li><li>**Százalékos teljesítési** érték – minden sorhoz egy összesített teljesítési értéket ad meg a program.</li><p>**Változó mennyiség** – minden sorhoz meghatározott felosztási mennyiség van megadva.</li></ul><p>**Megjegyzés:** Ha a Százalékos teljesítési **értékeket szeretné kiválasztani**, a dátumok csak növekvő sorrendben lehetek.</p> |
| **Egységenkénti külön események létrehozása** | |
| Leírás | <p>Adja meg, hogy egységenként szeretné-e elválasztani az eseményeket:</p><ul><li>**Igen** – válassza el az eseménysorokat úgy, hogy mennyiségenként egy sort tartalmazzanak.<p>Például három eseménysor van, és a számla mennyisége négy. Ebben az esetben az eredményül kapott halasztás ütemezésében 12 sor van.</p></li><li>**Nem** – ne válassza el az eseménysorokat.</li></ul> |
| Lejárati számla | <p>Válassza ki azt a számlát, amely a lejártnak ismerhető sorokhoz használatos. A számlát a halasztás ütemezésének létrehozása után választhatja ki.</p><p>Ha egy eseményhez be van állítva lejárati dátum, a felismerési folyamat során a program a lejárati számlára kerül, nem pedig a felismerési számlára.</p> |
| **Ütemezés – eseményalapú sorok** | |
| Leírás | Az esemény leírása. |
| Halasztás záró dátuma | <p>Az esemény záró dátumának kiválasztása.</p><p>**Megjegyzés:** Ha záró dátumot választ, a Lejárati **dátum** mező üres. Nem használhat mind záró, mind lejárati dátumot.</p> |
| Lejárat dátuma | <p>Az esemény lejárati dátumának kiválasztása.</p><p>**Megjegyzés:** Ha záró dátumot választ, a Lejárati **dátum** mező üres. Nem használhat mind záró, mind lejárati dátumot.</p> |
| Mennyiség | <p>A felosztási mennyiség megadása. Minden sor alapértelmezett értéke **0** (nulla). Ha frissíti a mennyiséget, akkor minden sor teljes mennyiségének egyenlőnek vagy kisebbnek kell lennie, mint az értékesítési rendelésben szereplő sorcikknél megadott mennyiség.</p><p>Ez a mező csak akkor érhető el, ha **a Felosztás típusa** mező értéke Változó **mennyiség**.</p><p>Ha az értékesítési rendelés sortételének mennyisége úgy módosul, hogy kevesebb, mint az eredeti mennyiség, és létrejön a számla, kevesebb esemény alapú sor jön létre. A teljes felosztott mennyiség nem haladja meg az eredeti értékesítési rendelésen vagy számlázási ütemezésben megadott mennyiséget.</p> |
| Felosztási százalék | <p>A felosztási százalék megadása. Ha a **Felosztás típusa mező** értéke **Százalék** **vagy** Százalékos teljesítés, manuálisan is megadhatja a százalékos arányt. Ellenkező esetben a program automatikusan kiszámítja.</p><p>Ha a **Felosztás típusa mező** értéke **Százalék**, a százalékok összegének 100-nak kell lennie.</p> |
| Összeg | <p>A felosztás összegének megadása. Ha a **Felosztás típusa mező** értéke **Változó** **összegek** vagy Százalékos teljesítési érték, manuálisan is megadhatja az összeget.</p><p>Ha a **Felosztás típusa mező** **értéke** Százalékos teljesítés, és itt beír egy összeget, **akkor** a program automatikusan kiszámítja a Teljesítési százalék mező értékét.</p><p>A kerekítés miatt előfordulhat, hogy a számított összeg nem pontosan egyezik meg a manuálisan megadott összeggel. Ha pontos összeget igényel, **állítsa a Felosztás típusa** mezőt Változó **összegek beállításra**.</p> |
| Teljesítés százalékos értéke | <p>Adja meg a teljesítési százalékot. Az értéknek 0 (nulla) és 100 között kell lennie.</p><p>Ez a mező csak akkor érhető el, ha **a Felosztás típusa** mező értéke Százalékos **teljesítési érték**.</p> |
| Teljesítési összeg | <p>A halasztás ütemezésének összes sorában kiszámított összeg.</p><p>Ha a **Felosztás típusa mező** értéke Százalékos **teljesítés**, manuálisan is megadhatja az összeget. Ebben az esetben a **Teljesítési** százalék mező értékét a megadott összeg alapján számítja ki a program.</p><p>A kerekítés miatt előfordulhat, hogy a számított összeg nem pontosan egyezik meg a manuálisan megadott összeggel.</p><p>Ez a mező csak akkor érhető el, ha **a Felosztás típusa** mező értéke Százalékos **teljesítési érték**.</p> |
| Elismerem a postán | <p>Adja meg, hogy a rendszer automatikusan ismeri-e fel a sort a tranzakció feladása után:</p><ul><li>**Bejelölve** – a sor automatikusan megjelenik a tranzakció feladása után.</li><li>**Törölve** – a sor nem ismerhető fel a tranzakció feladása után.</li></ul> |
| Elszámolási számla | <p>Az esemény felismerési számlájának megadása, ha a számla eltér a teljes halasztás ütemezésében használt számlától.</p><p>Ez a mező a Postán való felismerés beállítással **együtt használható**.</p> |
