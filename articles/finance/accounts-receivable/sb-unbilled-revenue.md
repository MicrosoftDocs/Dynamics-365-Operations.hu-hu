---
title: Számlázatlan bevétel
description: Ez a cikk bemutatja, hogyan lehet beállítani a cikkeket és számlákat a nem számlázandó bevétel funkció használatára az előfizetési számlázásban.
author: JodiChristiansen
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: adf6f06ee454f368fa194315a87cfdec9e5e13da
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644168"
---
# <a name="unbilled-revenue"></a>Számlázatlan bevétel

Ez a témakör leírja azt a nem számlázatlan bevétel funkciót, amellyel a teljes számlázási ütemezések összegeit szerepeltetheti a mérlegben. Ezek az összegek egy nem számlázandó bevételi számlán és egy nem számlázandó bevételi ellenszámlán szerepelnek, és a szerződés számlázása részletekben megy el.

## <a name="set-up-unbilled-revenue"></a>Nemszámlázatlan bevétel beállítása

A nemszámlázatlan bevétel beállítását a következő lépések szerint hajtsa végre.

- Az Ismétlődő szerződés **számlázási paraméterei** oldalon állítsa **be a mezőket a Nem számlázandó bevétel szakaszban**.
- A nemszámlázatlan bevétel szolgáltatás olyan **cikkekhez használható, ahol a Cikktípus** mező beállítása **Normál**. Halasztásos cikkekhez is használható. A nem számlázatlan bevételnek **a rövid távú funkcióval való használatához állítsa be a rövid távú beállításokat az Ismétlődő szerződés számlázási paraméterei oldalon**.

A cikkek nemszámlázatlan bevétel használatára való beállítását a következő lépések szerint hajtsa végre.

1. A Nemszámlázatlan **bevétel beállítási lapján**, a **Cikkek** lapon válassza a Hozzáadás **elemet**.
2. Az új sor Cikkkód elemében **válassza** ki a cikk-kódot.
3. A Cikk-kapcsolat **mezőben** válassza ki a cikk-kapcsolatot.
4. Ismételje meg ezeket a lépéseket további sorok hozzáadásához.
5. Válassza a **Mentés** lehetőséget.

A cikkek és a nem számlázatlan bevételi számlák beállításának lépéseit hajtsa végre.

1. A Nem számlázandó **bevétel beállítása** lapon, a **Számlák** lapon válassza a Hozzáadás **lehetőséget**.
2. Az új sor Cikkkód elemében **válassza** ki a cikk-kódot.
3. A Cikk-kapcsolat **mezőben** válassza ki a cikk-kapcsolatot.
4. A nem számlázandó bevétel, a nem számlázandó engedmény és a nem számlázatlan bevétel ellentételének számlái. A rövid távú számlák csak akkor használhatók, **·** **·** **·** **ha az Ismétlődő szerződés számlázási paraméterei oldalon az Időszakok vagy a Rögzített év beállításra a Rövid távú nem számlázandó mód mezőt kell** beállítani.
5. Ismételje meg ezeket a lépéseket további sorok hozzáadásához.
6. Válassza a **Mentés** lehetőséget.

## <a name="use-unbilled-revenue"></a>Nemszámlázatlan bevétel használata

1. Hozzon létre **egy számlázási** ütemezést a Minden számlázási ütemezés lapon.
2. Ha a cikk még nincs beállítva a nem számlázatlan bevétel használatára, **jelölje be a Nem számlázatlan** bevétel jelölőnégyzetet a számlázási ütemezés sorában.
3. Állítsa a **Nemszámlázatlan bevétel** lehetőséget Igen **beállításra**. Ezután szükség szerint tekintse át és szerkessze a nem számlázandó bevételeket, engedményeket és a nem számlázandó bevételek ellenszámláit.
4. A számlázási ütemezés Nem **számlázatlan** **bevétel** feldolgozása csoportban válassza a Naplóbejegyzés létrehozása lehetőséget a nem számlázandó bevétel kezdeti naplóbejegyzésének létrehozásához. Ezt a lépést a számlázási ütemezés számlázása előtt végre kell végrehajtani.
5. A napló kezdeti bejegyzésének **létrehozása után válassza a Számla létrehozása** lehetőséget az értékesítési rendelések létrehozásához és a számlázási ütemezések számláinak feladásához.
6. A számlák **feladása** **után a Minden számlázási ütemezés lap Megújítások lapján áttekintheti a könyvvizsgálati** adatokat.

### <a name="milestone-billing"></a>Mérföldkőszámlázás

A mérföldkőszámlázás a nem számlázatlan bevétellel a következő feltételek mellett működik:

- Ha a mérföldkőhöz tartozó szülőcikk nem számlázatlan (**be** van jelölve a Nem számlázatlan bevétel jelölőnégyzet), és a mérföldkőhöz tartozó gyermekcikkek számlázása meg van adva (**a Nem számlázandó** bevétel jelölőnégyzet nincs bejelölve), meg kell adni a szülőcikk kezdő és záró dátumát. Ezek a dátumok a kezdeti naplóbejegyzés létrehozásához használatosak.
- Ha a mérföldkőhöz tartozó szülőcikk nem számlázatlan (**a** Nem számlázatlan bevétel jelölőnégyzet nincs bejelölve), és a mérföldkőhöz tartozó gyermekcikkek számlázva lesznek (**be van jelölve a Nem számlázható** bevétel jelölőnégyzet), a záró dátumot csak azok a gyermek cikkek esetén kell megadni, amelyekhez létre szeretné hozni a kezdeti naplóbejegyzést.

Minden mérföldkőhöz tartozó gyermekelem külön-külön is feldolgozható. A záró dátumokat akkor lehet megadni, amikor készen áll a kezdő naplóbejegyzés létrehozására.

> [!NOTE]
> Ha a mérföldkőhöz tartozó szülőcikk vagy gyermek cikkek első naplóbejegyzése már létre van hozva, vagy már van számla, akkor a kezdő és a záró dátum nem szerkeszthető.

### <a name="unbilled-revenue-with-straight-line-deferrals"></a>Nemszámlázandó bevétel sor halasztásokkal

Ha a nemszámlázatlan bevételt straight line halasztás ütemezésekkel együtt használni, kövesse ezeket a lépéseket.

1. Hozzon létre **egy számlázási** ütemezést a Minden számlázási ütemezés lapon.
2. Cikk hozzáadása a számlázási ütemezés sorához.
3. Halasztások **kiválasztása** a sorhoz.
4. A Tranzakció **halasztás lapján** hajtsa végre a következő lépéseket:

    1. A Halasztott **lehetőség beállítása Igen** beállításra **·**.
    2. Módosítsa a számlákat a szükséges beállításoknak megfelelően.
    3. Az Ütemezés **szakaszban** válassza a Straight **Line** lehetőséget, és szükség szerint szerkessze az egyéb értékeket.
    4. Válassza ki az **OK** lehetőséget.

5. Válassza **ki a sor nemszámlázatlan** bevételét, majd hajtsa végre a következő lépéseket:

    1. Állítsa a **Nemszámlázatlan bevétel** lehetőséget Igen **beállításra**.
    2. Válassza ki a bevétel, engedmény és bevétel ellentételének könyvelési számláit.

6. A számlázási ütemezés Nem számlázatlan **bevétel** feldolgozása csoportban válassza a Naplóbejegyzés **létrehozása lehetőséget**. Másik lehetőségként a Nemszámlázatlan **bevételek tömeges feldolgozásával** hozza létre a naplóbejegyzést.
7. A halasztás ütemezése létrehozva. A részleteket a Minden halasztás **ütemezése lapon lehet** áttekintheti. Halasztás ütemezésének létrehozása után módosíthatja a számlázási ütemezés sortételének különféle értékeit. Módosíthatja például az egységárat, a mennyiséget vagy a dátumokat.

### <a name="unbilled-revenue-with-event-based-deferrals"></a>Nemszámlázatlan bevétel esemény alapú halasztásokkal

A nemszámlázatlan bevétel esemény alapú halasztás-ütemezéssel való alkalmazáshoz kövesse ezeket a lépéseket.

1. Hozzon létre **egy számlázási** ütemezést a Minden számlázási ütemezés lapon.
2. Cikk hozzáadása a számlázási ütemezés sorához.
3. Halasztások **kiválasztása** a sorhoz.
4. A Tranzakció **halasztás lapján** hajtsa végre a következő lépéseket:

    1. A Halasztott **lehetőség beállítása Igen** beállításra **·**.
    2. Módosítsa a számlákat a szükséges beállításoknak megfelelően.
    3. Az Ütemezés **szakaszban** válassza ki az **Eseményalapú, a** Sablon, **·** **a Felosztás típusa** és a Lejárati **számla lehetőséget.**
    4. Válassza ki az **OK** lehetőséget.

5. Válassza **ki a sor nemszámlázatlan** bevételét, majd hajtsa végre a következő lépéseket:

    - Állítsa a **Nemszámlázatlan bevétel** lehetőséget Igen **beállításra**.
    - Válassza ki a bevétel, engedmény és bevétel ellentételének könyvelési számláit.

6. A számlázási ütemezés Nem számlázatlan **bevétel** feldolgozása csoportban válassza a Naplóbejegyzés **létrehozása lehetőséget**. Másik lehetőségként a Nemszámlázatlan **bevételek tömeges feldolgozásával** hozza létre a naplóbejegyzést.
7. A halasztás ütemezése létrehozva. A részleteket a Minden halasztás **ütemezése lapon lehet** áttekintheti. Halasztás ütemezésének létrehozása után módosíthatja a számlázási ütemezés sortételének különféle értékeit. Módosíthatja például az egységárat, a mennyiséget vagy a dátumokat. A halasztás ütemezése az új értékek alapján újraszámul.

A felosztások újraszámulnak a kiválasztott felosztási típus alapján (**Százalék**, **Százalékos teljesítési** érték vagy **Egyenlő összegek**). A Változó **összegek** felosztási típusnál a felosztás újraszámul az esemény kezdeti értékének százalékos megfelelője alapján. Például az eredeti egységár $100.00, a kezdeti érték százalékos értéke pedig $55.00 (55 százalék). Ha az egységár változóra $200.00, akkor az esemény változó összege $110.00 lesz (55 százalék).

> [!NOTE]
> Ha halasztás-ütemezési sorokat ismer fel, akkor a számlázási ütemezés sortétele nem szerkeszthető. A sortétel szerkesztéséhez először sztornírozni kell a felismert sorokat. Ezután frissíteni lehet a számlázási ütemezés sorát.

### <a name="unbilled-revenue-and-top-billing"></a>Nem számlázandó bevétel és fő számlázás

A számlázási ütemezés három évre van megadva, és a számlák számlázása éves szinten, három év alatt fog leszámlázva. A szerződés teljes összegét abban a nem számlázott bevételi számlán rögzíti a rendszer, amelyről az éves számlákat létrehozták. Az ellenszámla a bevétel vagy a halasztott bevételszámla.

A fő számlázási és a nem számlázatlan bevétel nem működik együtt, mert egyeztetési problémák fordulhatnak elő a főkönyvben. A Cikkcsoport beállítási **lapon** például az **A** **cikkcsoport úgy van beállítva, hogy a Felső sorok száma mezőben a 2-es** számot állítsa. A Számlázási **ütemezések** lapon három elem van hozzáadva. Mindhárom cikk az A cikkcsoportba tartozik. Amikor a nem számlázandó bevétel funkcióhoz létrejön a kezdeti naplóbejegyzés, mindhárom cikk összegét feldolgozja a rendszer a nem számlázatlan számlára. Amikor számla jön létre a számlázási ütemezéshez, csak a két első cikk összegét tartalmazza a program. Emiatt a számlaösszeg nem egyezik meg a feldolgozott összeggel a nem számlázott bevételi számlával, és egyeztetési problémák lépnek fel a főkönyvben.

Ha nemszámlázandó bevételt szeretne használni, **hagyja** üresen a Cikkcsoport beállítása lapot, **·** **vagy állítson be minden cikkcsoportot úgy, hogy a Felső sorok száma mezőben a 0 (nulla**) érték legyen beállítva. Ha fő számlázást szeretne használni, nem érhetők el nem számlázandó bevételi műveletek.

### <a name="examples"></a>Példák

A 10.0.29-es verziótól egy új paramétert ad a rendszer az ismétlődő szerződés számlázási paramétereihez. Igen beállítás esetén a Nem számlázatlan **ellenszámlák** használata paraméter **két új számlát tesz lehetővé a Nem számlázatlan bevétel beállításban**. A nem számlázandó bevétel ellenszámlái és a nem számlázandó engedmény ellenszámlái válnak elérhetővé, és akkor használhatók, ha a számlázási ütemezéseket a könyvelési pénznemtől különböző pénznemben hozták létre. Az ellenszámlák használatával garantálható, hogy a be nem számlázatlan bevételi és engedményszámlák sztornírozása a kezdő bejegyzésekkel azonos árfolyamokkal legyen kiegyenlítve. A Naplóbejegyzés **létrehozása kezdeti** folyamata megegyezik a nem terhelt bevételre és a bevételre történő jóváírás terhelésének folyamatával. Engedmény használata esetén a napló kezdeti bejegyzése megegyezik az Engedmény tartozik tételsel és a nem terhelt engedmény követel tételsel. 

Ez a példa bemutatja, hogyan lehet a nem beszámlázatlan bevételt használni egy szerződés teljes összegének mérlegszámlázatlan bevételként való felismerésére. A bejegyzés másik oldala a bevétel vagy a halasztott bevétel. A vevői számlázáskor a nem számlázott bevétel sztornírozva lesz. A bevétel-kimutatás vagy a számlázáskor, vagy a beállított halasztás-felismerési ütemezés szerint történik.

#### <a name="assumptions"></a>Feltételezések

- Az aktuális év január 1-jén a vevő három évre szóló szerződést $390.
- A szerződés két részből áll: licencekből és karbantartási szerződésből.
- Az licencdíj eladási ára $300, a vevőnek minden szerződési év január 1-jén $100 számlázva lesz. A $300 szerződés aláírásakor a licencdíj bevételként lesz figyelembe venni.
- A karbantartási díj eladási ára nem $90, és a vevőnek minden szerződési év január 1-jén $30 meg lesz számlázva. A $90 karbantartási díj halasztva lesz, és $2.50 a rendszer a szerződés élettartamának minden hónapját ismeri el.
- A vevőnek a szerződés három $130 évének kezdetétől (január 1-jén) számlát kap.

#### <a name="steps"></a>Lépések

1. A két kiadott cikk beállítása nemszámlázandó cikkként. A Nem számlázatlan **bevétel beállítási** lapon lehet beállítani a nem számlázandó bevételt használó cikkeket és számlákat.
2. Ebben a példában a karbantartási díj halasztva van. A cikkhez halasztássablon szükséges, amelynek beállítása a Halasztássablonok **lapon van beállítva**. A sablon **36** havi gyakorisággal és 36 hónapos felismerési időszakokkal rendelkezik. Ebből következően a havi bevételt fel kell $2.50.
3. A Cikkek halasztás **alapértelmezett lapján** állítsa **·** **a Karbantartási díj mezőt Halasztható cikkre.** Ez a lépés és a következő lépés halasztja a karbantartási díjtételt az eladáskor vagy a számlázási ütemezésben való szerepeltetése esetén.
4. Válassza **ki az Alapértelmezett halasztás** \> **sablont**, és adja hozzá a cikket a karbantartási díjhoz és a straight-line sablonhoz a 2. lépésben. A karbantartási díjtétel 36 hónapos halasztási ütemezéshez lesz csatolva.
5. Hozzon létre egy számlázási ütemezést, amely tartalmazza a két nem számlázandó elemet. A szerződés számlázási ütemezése a következő elemekre van beállítva.

    | Cikk | Kezdés dátuma | Befejezés dátuma | Összeg | Számlázási gyakoriság | Halasztás - cikk | Számlázatlan bevétel | Leírás |
    |---|---|---|---|---|---|---|---|
    | Licenc | 2022. január 01. | 2024. december 31. | $100.00 | Évente | Nem | Igen | A vevőnek minden évben $100.00 számlát kell kiszámlázni. A $300.00 összeget a mérlegszámlán be nemszámlázatlan bevételként, illetve az eredmény bevételeként rögzíti a rendszer. Minden számla csökkenti a nem számlázott összeget. |
    | Karbantartás | 2022. január 01. | 2024. december 31. | $30.00 | Évente | Igen | Igen | A vevőnek minden évben $30.00 számlát kell kiszámlázni. A $90.00 a mérlegben előre elszámolatlan bevételként és halasztott bevételként lesz rögzítve. Minden számla csökkenti a nem számlázott összeget. A halasztott bevételt havonta, 36 hónap alatt ismeri el a rendszer. |

6. A Minden számlázási **ütemezés** lapon a **Naplóbejegyzés** létrehozása folyamat használatával lehet a szerződés értékét a mérlegbe beszámlázatlan bevételként feladni.

Két naplóbejegyzés jön létre, a számlázási ütemezés minden sorához egy.

| Számla | Terhelés összege | Jóváírási összeg |
|---|---|---|
| Számlázatlan bevételszámla | $300.00 | |
| Bevételi számla | | $300.00 |

| Számla | Terhelés összege | Jóváírási összeg |
|---|---|---|
| Számlázatlan bevételszámla | $90.00 | |
| Halasztott bevétel | | $90.00 |

A szerződés előírja, hogy a vevő számláját minden év elején ki kell létrehozni. A számla **létrehozásához használja** a Számla létrehozása folyamatot. A számla létrehozásakor a következő számlabizonylat feladása történik meg.

| Számla| Terhelés összege | Jóváírási összeg |
|---|---|---|
| Számlázatlan bevételszámla | | $130.00 |
| Kinnlevőségek | $130.00 | |

Ugyanez a naplóbejegyzés a következő két év elején feladott számlák alapján jön létre. A nem számlázott bevételek számlája minden évben csökken a számla **létrehozása folyamat** során. A nem számlázatlan bevétel ellenszámlája használatos a nem számlázandó bevételi számla egyenlegének különböző árfolyamok használatakor. 

Az utolsó lépésben az felismerési napló minden hónapban létrejön, hogy elismerje a karbantartási díjból származó halasztott bevételt. A naplóbejegyzést a Felismerés feldolgozása **lapon lehet** létrehozni. Másik lehetőségként a **halasztás** **ütemezési lapjain található Sorok felismerése beállításával is létre lehet hozva**.

| Fő számla | Terhelés összege | Jóváírási összeg |
|---|---|---|
| Halasztott bevétel | $2.50 | |
| Bevétel | | $2.50 |

Ez a naplóbejegyzés minden alkalommal létrejön, amikor a halasztott cikkre (összesen 36-szor) futtatnak felismerési folyamatot.

#### <a name="short-term-fixed-year"></a>Rövid távú: Rögzített év

A nem **számlázatlan** **bevételt a rövid távú funkcióval együtt úgy használhatja, hogy az Ismétlődő szerződés számlázási paraméterei oldal rövid távú nem számlázandó mezőt beáraz**. Az alábbi példa bemutatja **azokat** a számításokat, amelyek a nem számolt bevétel használata esetén, a rögzített év rövid távú nem számolt módszerével együtt történik.

Létrejön egy számlázási ütemezés, amely a következő feltételeket tartalmazza:

- **Kezdő dátum:** 2020. június 1.
- **Záró dátum:** 2021. december 31.
- **Egységár:** $100
- **Gyakoriság:** havi

A Minden számlázási **ütemezés lapon** a napló kezdeti bejegyzését a **Naplóbejegyzés létrehozása folyamat hozza** létre. Az aktuális rövid- és hosszú távú összegek számítása a következőképpen történik:

- **Aktuális rövid távú nemszámlázatlan bevételösszeg:** $700
- **A jelenlegi hosszú távú nemszámlázatlan bevételösszeg:** $1,200

A számla 2020. június 1-től 2020. november 30-ig tart. Az aktuális rövid- és hosszú távú összegek számítása a következőképpen történik:

- **Rövid távú nemszámlázatlan bevételösszeg:** $100
- **A jelenlegi hosszú távú nemszámlázatlan bevételösszeg:** $1,200

A számla 2020. december 1-től 2020. december 31-ig tart. Az aktuális rövid- és hosszú távú összegek számítása a következőképpen történik:

- **Rövid távú nemszámlázatlan bevételösszeg:** $1,200
- **A jelenlegi hosszú távú nemszámlázatlan bevételösszeg:** $0

#### <a name="short-term-rolling-periods"></a>Rövid távú: Az időszakok görgetve

A nem számlázatlan **bevételt a rövid távú funkcióval együtt úgy használhatja, hogy az ismétlődő szerződés számlázási paraméterei oldalon a rövid távú nem számlázandó módszert beáraz**. Az alábbi példa bemutatja **azokat** a számításokat, amelyek a nem számolt bevétel használata esetén, a rövid távú nem fizetési módszerrel együtt végeznek számításokat.

Létrejön egy számlázási ütemezés, amely a következő feltételeket tartalmazza:

- **Kezdő dátum:** 2020. június 1.
- **Záró dátum:** 2021. december 31.
- **Egységár:** $100
- **Gyakoriság:** havi

A Minden számlázási **ütemezés lapon** a napló kezdeti bejegyzését a **Naplóbejegyzés létrehozása folyamat hozza** létre. Az aktuális rövid- és hosszú távú összegek számítása a következőképpen történik:

- **Rövid távú nemszámlázatlan bevételösszeg:** $1,200
- **A jelenlegi hosszú távú nemszámlázatlan bevételösszeg:** $700

A számla 2020. június 1-től 2020. november 30-ig tart. Az aktuális rövid- és hosszú távú összegek számítása a következőképpen történik:

- **Rövid távú nemszámlázatlan bevételösszeg:** $1,200
- **A jelenlegi hosszú távú nemszámlázatlan bevételösszeg:** $100

A számla 2020. december 1-től 2020. december 31-ig tart. Az aktuális rövid- és hosszú távú összegek számítása a következőképpen történik:

- **Rövid távú nemszámlázatlan bevételösszeg:** $1,200
- **A jelenlegi hosszú távú nemszámlázatlan bevételösszeg:** $0

### <a name="items-with-revenue-allocation"></a>Cikkek bevételfelosztással

A számlázási ütemezéshez két különböző számlázási gyakoriságú tételt ad hozzá a program. Mindkettő használ nemszámlázható bevételt, és ezek halasztható cikkek.

- **1000 cikkszám:** Pro 128GB felület

    - **Számlázási gyakoriság:** egyszer
    - **Egységár:** $1,500
    - **Önálló eladási ár:** $1,600
    - **Szerződés bevétele:** $1,465.26

- **Cikkszám: Biztosítás az 1000-es** cikkszámmal együtt

    - **Számlázási gyakoriság:** havonta, 12 hónapon keresztül
    - **Egységár:** $20/hónap
    - **Önálló eladási ár:** $25
    - **Szerződés bevétele:** $264.74

Mivel a cikkek nemszámlázandó bevételt és bevételfelosztást is használnak, a megújítási sorban lévő szerződés teljes összege 0 (nulla). **Megjelenik a Szerződés bevétel** oszlopa, és látható a szerződés bevételének összege.

A következő táblázat bemutatja a cikkek és a számla első naplóbejegyzését.

| Fő számla | Terhelés összege | Jóváírási összeg |
|---|---|---|
| **1000-es cikk naplóbejegyzése** | | | 
| Nem számlázandó bevételi számla (401250) | $1,465.26 | |
| Halasztott bevételi számla (250600) | | $1,465.26 |
| **0021-es cikk naplóbejegyzése** | | | 
| Nem számlázandó bevételi számla (401250) | $274.74 | |
| Halasztott bevételi számla (250600) | | $274.74 |
| **Számla** | | |
| Számlázatlan bevételszámla | | $1,465.26 |
| Számlázatlan bevételszámla | | $274.74 |
| Könyvelői számla (130100) | $1,488.16 | |

#### <a name="changes-to-the-billing-schedule-line-billing-detail-line-or-revenue-allocation"></a>A számlázási ütemezés sorának, a számlázási részletsornak vagy a bevételfelosztásnak a módosításai

Ha az egységár vagy a mennyiség megváltozik, frissíteni kell minden olyan cikk szerződéses bevételi összegét, amely része a bevételfelosztásnak. Ebből következően a naplóbejegyzés újra lesz számálva.

Például az 1000-es cikk egységára módosul új $1,500 árról $1,600. Ebben az esetben a szerződés bevételének összege automatikusan újra lesz $1,549.47. A szerződésből származó bevétel az S0021 cikkre újra lesz $290.53.

A módosított elemek visszaigazolt és vállalt visszaigazolt naplóbejegyzései mindkét cikkre sztornírozva, majd új naplóbejegyzések is létrejönnek:

- **1000-es cikk: a** $1,465.26 eredeti naplóbejegyzése sztornírozva van. Új naplóbejegyzés jön létre $1,549.47 naplóbejegyzéshez.
- **S0021 cikk: A** program sztornírozta a $274.74 napló eredeti naplóbejegyzését. A rendszer új naplóbejegyzést $290.53 naplóbejegyzést.

#### <a name="termination"></a>Befejezés

Az S0021 cikk kezdő dátuma 2020 ján belül, a záró dátum 2020 decemberben van, de 2020 júniusában megszűnik. Mindkét cikk szerződési bevételének összegét újra kellszámni:

- **1000-es cikk: A** szerződésből származó bevétel újraszámul új $1,567.67.
- **S0021 cikk: A** szerződésből származó bevétel újra lesz $124.00.

A megszüntetett sorhoz létrejön egy helyesbítésinapló-bejegyzés. A rendszer sztornírozta annak a sornak a naplóbejegyzését, amely ugyan ahhoz a többelem-elrendezéshez (MEA) tartozik, és új naplóbejegyzés jön létre:

- **1000-es cikk: a** $1,465.26 eredeti naplóbejegyzése sztornírozva van. A program létrehoz egy helyesbítési $1,549.47 naplóbejegyzést.
- **S0021 cikk: A** program sztornírozta a $274.74 napló eredeti naplóbejegyzését. A rendszer új naplóbejegyzést $124.00 naplóbejegyzést.
