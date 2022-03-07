---
title: A bevételelszámolás beállítása
description: Ez a cikk a bevételmegjelenítés beállítási lehetőségeit és a beállítások hatását mutatja be.
author: kweekley
ms.date: 11/24/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: e8e29ec1ca5a02db67bb4baf522da96ec23c740f
ms.sourcegitcommit: ac23a0a1f0cc16409aab629fba97dac281cdfafb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/29/2021
ms.locfileid: "7867220"
---
# <a name="revenue-recognition-setup"></a>A bevételelszámolás beállítása
[!include [banner](../includes/banner.md)]

A programba új **Bevételmegjelenítés** modul került, amelyben minden szükséges beállításhoz tartozik menüelem. Ez a cikk a beállítási lehetőségeket és a beállítások hatását mutatja be.

> [!NOTE]
> A „Bevétel megjelenítése” funkció mostantól alapértelmezés szerint engedélyezve van a Funkciókezelésben. Ha az Ön szervezete nem használja ezt a funkciót, a **Funkciókezelés** munkaterületen bármikor kikapcsolhatja.
>
> A bevételelszámolási funkció, beleértve a csomagfunkciót is, nem támogatott a Commerce-csatornákon (e-kereskedelem, pénztár és hívásközpont). A bevételelszámolási funkció számára konfigurált tételeket nem szabad hozzáadni a Commerce-csatornákon létrehozott rendelésekhez vagy tranzakciókhoz.

A **Bevételelszámolás** modulban a következő beállítások érhetők el:

- Bevételmegjelenítési naplók
- A bevételmegjelenítés paraméterei
- Bevételek ütemezései 
- Készletbeállítás

    - Cikkcsoportok és kiadott termékek
    - A bevételütemezés meghatározása
    - A bevételi ár meghatározása
    - Készletbeállítás

        - A bevételütemezés meghatározása
        - A bevételi ár meghatározása

    - Feladási profilok
    - Csomagok

        - A csomagok összetevői
        - Csomagolt cikk

- Projekt beállítása

## <a name="revenue-recognition-journals"></a>Bevételmegjelenítési naplók

A bevétel megjelenítéséhez új naplótípust vezettünk be. A napló két esetben szükséges és használatos.

Az első: miután az összes szerződéses kötelezettség teljesül, és sor kerül a halasztott bevételnek a bevételi ütemezés részletein alapuló bevételmegjelenítési naplóval való megjelenítésére. A napló olyan könyvelési bejegyzést tartalmaz, amely áthelyezi az egyenleget a halasztott bevételi főkönyvi számláról a bevételi főkönyvi számlára.

A második eset akkor fordul elő, amikor napló jön létre az újbóli felosztást követően. Újbóli felosztás akkor történik, amikor az értékesítési rendelés egy sorát hozzáadják egy korábban számlázott értékesítési rendeléshez, vagy amikor olyan új értékesítési rendelés jön létre, amely az eredeti szerződés részét képező sort tartalmaz. Ha egy számlát feladtak az értékesítési rendelés új sorának a hozzáadása előtt, a feladott vevői számlához helyesbítő könyvelési tételt kell létrehozni.

A naplót a **Naplónevek** oldalon (**Bevételmegjelenítés \> Beállítás \> Naplónevek**) lehet beállítani. A napló típusaként a **Bevételmegjelenítést** kell megadni. 

## <a name="parameters-for-revenue-recognition"></a>A bevételmegjelenítés paraméterei

A bevételelszámolás beállításai a **Főkönyvi paraméterek** oldal (**Bevételmegjelenítés \> Beállítás \> Főkönyvi paraméterek**) **Bevételmegjelenítés** lapján állíthatók be. A következő beállítások állnak rendelkezésre:

- **Bevételmegjelenítési napló neve** – Válassza ki a bevételmegjelenítéshez létrehozott naplót. Ha a bevétel megjelenítése a bevételi ütemezésből történik, vagy ha már számlázott értékesítési rendeléshez hajt végre újbóli felosztást, akkor a naplóra szükség van.
- **Engedményfelosztási mód engedélyezése** – Ha az egyes kiadott termékek bevételi árában meghatározott méltányos piaci érték felosztásával szeretné meghatározni a bevételi árat, adja meg az **Igen** értéket a beállításhoz. Ez a felosztás a cikkek minden sorengedményének a felosztását tartalmazza. Ha a beállítás értéke **Nem**, akkor a rendszer az egyes kiadott termékek bevételi árában megadott medián árat használja. Ha a beállítás értéke **Nem**, de nem állít be medián árat a kiadott termékekhez, akkor nem kerül sor a bevételi ár felosztására.
- **Fejlécben szereplő engedmények belefoglalása** – Ha a bevételi árat a fejlécben szereplő engedmények termékek közötti felosztásával szeretné meghatározni, az **Igen** lehetőséget válassza. Ha a beállítás értéke **Nem**, akkor a rendszer nem foglalja be a fejlécben szereplő engedményeket a bevételi ár felosztásába.
- **Szerződési feltételek letiltása** – Adja meg az **Igen** értéket, ha azt szeretné, hogy a **Támogatási szerződés feladása** bevételi típusú termékeket akkor is ki lehessen adni, ha nincs megadva hozzájuk a szerződés kezdő és záró dátuma. A szerződés kezdő és záró dátuma általában szükséges a **Támogatási szerződés feladása** bevételi típusú cikkekhez. Ha a szerződés kezdő és záró dátuma nincs meghatározva, akkor a bevételütemezés feladási részleteit az előfordulások számának és a számla dátumának a használatával számítja ki a rendszer.
- **Az újrafelosztáskor a számlajavítások feladása a Kinnlevőségek modulba** – Már feladott számlák újrafelosztása esetén a feladott számla könyvelési bejegyzését ki kell javítani. Ezzel a beállítással adhatja meg, hogyan történjen a korrekció.

    - Ha a **Nem** értéket adja meg, korlátozhatja a helyesbítő tranzakció főkönyvbe történő feladását. Ha a beállítás értéke **Nem**, akkor nem jönnek létre további dokumentumokat a Kinnlevőségek modulban a belső számviteli korrekcióhoz. A számla kifizetésekor az elszámolási folyamat a régi könyvelési bejegyzést használja fel a készpénzfizetési engedmények, illetve a realizált nyereségek vagy veszteségek feladásához.
    - Ha a beállításhoz az **Igen** értéket adja meg, a Kinnlevőségek modulban automatikusan létrejön egy sztornírozási dokumentum és egy új számla a helyesbítő tranzakcióhoz. Mivel ez a javítás belső könyvelési korrekció, a program nem küldi el és nem továbbítja a vevőnek az új dokumentumokat. A sztornírozási dokumentumot az eredeti számlára egyenlíti ki a program, és a vevő az új, helyesbített számlát fizeti ki. Ne feledje, hogy mindhárom dokumentum megjelenik a jelentésekben, például a vevői kivonatban.

[![Beállítási adatok.](./media/revenue-recognition-setup-info.png)](./media/revenue-recognition-setup-info.png)

## <a name="revenue-schedules"></a>Bevételek ütemezései

Minden olyan esetben létre kell hozni bevételi ütemezést, amikor halasztható a bevétel. Ha például a szervezet a 6, 12, 18 és 24 hónapos időszakokat támogatja, akkor minden időszakhoz létre kell hoznia egy bevételi ütemezést. A bevételi ütemezés beállítása határozza meg, hogy a program hogyan osztja fel a bevételi árat a kiválasztott számú időszak között. Ezenkívül a számla feladásakor létrejövő bevételi ütemezéshez megadott alapértelmezett dátumokat is meghatározza.

Ha a bevétel megjelenítése mérföldkövek szerint történik, a megjelenítési dátumoktól függetlenül célszerű bevételmegjelenítési ütemezést készíteni a mérföldkövekhez. Miután létrehozta az ütemezéseket, úgy módosíthatja őket, hogy tükrözzék a mérföldkövek várható dátumát. Ezek a rekordok mindaddig várakoztathatók, amíg Ön nem értesül arról, hogy a mérföldkő teljesült és a bevétel megjeleníthető.

A bevételek a **Bevételek ütemezései** lapon (**Bevételmegjelenítés \> Beállítás \> Bevételek ütemezései**) ütemezhetők.

[![Bevételek ütemezései.](./media/revenue-recognition-revenue-schedules.png)](./media/revenue-recognition-revenue-schedules.png)

Adjon meg leíró értéket a **Bevétel ütemezése** és a **Leírás** mezőben. A program a következő további beállításokat használja a bevételi ütemezés számla feladásakor történő létrehozásához.

- **Előfordulások** – Adja meg a bevétel halasztásához tartozó hónapok vagy előfordulások számát.
- **Automatikus várakoztatás** – Jelölje be ezt a jelölőnégyzetet, ha a számla feladásakor a bevételi ütemezés minden sorát automatikusan várakoztatni szeretné. A visszatartást a sor elhalasztott bevételének a megjelenítése előtt az ütemezés minden sorából manuálisan el kell távolítani.
- **Automatikus szerződési feltételek** – Jelölje be ezt a jelölőnégyzetet, ha automatikusan szeretné beállítani a szerződés kezdő és záró dátumát. A dátumokat csak a **Támogatási szerződés feladása** bevételi típusú kiadott termékekhez állítja be automatikusan a rendszer. A szerződés kezdő dátumát a program automatikusan az értékesítési rendelés sorának a kért szállítási dátumára állítja, a szerződés záró dátumát pedig automatikusan annyi hónappal vagy előfordulással a kezdő dátum után, amennyi meg van adva a bevételi ütemezés beállításában. Az értékesítési rendelés sorában szereplő termék jótállása például egy év. Az alapértelmezett bevételi ütemezés **12M** (12 hónap), az **Automatikus szerződési feltételek** jelölőnégyzet pedig be van jelölve ehhez a bevételi ütemezéshez. Ha az értékesítési rendelés sorában a kért szállítási dátum 2019. december 16., a szerződés alapértelmezett kezdő dátuma 2019. december 16. lesz, az alapértelmezett záró dátuma pedig 2020. december 15.
- **Megjelenítés alapja** – A megjelenítés alapja határozza meg a bevételi ár előfordulások közötti felosztását.

    - **Havi, napok szerint** – Az összeg felosztása az egyes naptári hónapok tényleges napjai alapján történik.
    - **Havi** – Az összeg felosztása az előfordulásokban meghatározott hónapok között egyenlően történik.
    - **Előfordulások** – Az összeg egyenlően oszlik el az előfordulások között, de ha a **Tényleges indítási dátumot** választja ki megjelenítési szabályként, akkor egy további időszakra is kiterjedhet.
    - **Pénzügyi időszak, napok szerint** – Az összeg felosztása az egyes pénzügyi időszakok tényleges napjai alapján történik. 

    A **Havi, napok szerint** és a **Pénzügyi időszak, napok szerint** beállítás ugyanazt az eredményt adja, ha a pénzügyi időszakok megegyeznek a naptári hónapokkal. Az egyetlen kivétel, ha a Megjelenítési szabály beállításnál a **Hónap/időszak vége** beállítást választja, és a **Szerződés kezdő dátuma** és a **Záró dátum** mezőket üresen hagyják az értékesítési rendelés soránál.

- **Megjelenítési szabály** – A megjelenítési szabály határozza meg a számla bevételi ütemezésének dátumait.

    - **Tényleges indítási dátum** – Az ütemezés vagy a szerződés kezdő dátuma (a támogatási szerződés \[PCs\] cikkeinek feladásához), vagy a számla dátuma (az alapvető és a nem alapvető cikkek esetében) alapján jön létre.
    - **Hónap/időszak első napja** – Az első ütemezési sor dátuma a szerződés kezdő dátuma (vagy a számla dátuma). A program azonban az összes további ütemezési sort a hónap vagy a pénzügyi időszak első napjához hozza létre.
    - **Felosztás a hónap közepén** – Az ütemezés első sorának dátuma a számla dátumától függ. Ha a számla feladása a hónap első és tizenötödik napja közé esik, a bevétel ütemezése a hónap első napja alapján jön létre. Ha a számla feladása a hónap tizenhatodik napjára vagy később esik, a bevétel ütemezése a következő hónap első napja alapján jön létre.

        A **Felosztás a hónap közepén** beállítás nem választható ki, ha a megjelenítési beállításnál a **Pénzügyi időszak, napok szerint** értéket választotta.

    - **Következő hónap/időszak első napja** – Az ütemezés kezdő dátuma a következő hónap vagy pénzügyi időszak első napja.
    - **Hónap/időszak vége** – Az első ütemezési sor dátuma a szerződés kezdő dátuma (vagy a számla dátuma). A program azonban az összes további ütemezési sort a hónap vagy a pénzügyi időszak utolsó napjához hozza létre. 

Az általános időszakok és az egyes időszakokban megjelenített százalékos értékek megtekintéséhez kattintson a **Bevételütemezés részletei** gombra. A **Megjelenítés százalékos értéke** alapértelmezés szerint egyenlően oszlik el az időszakok között. Ha a megjelenítés alapja **Havi**, akkor a megjelenítés százalékos értéke módosítható. A megjelenítés százalékos értékének módosításakor figyelmeztető üzenetet kap arról, hogy a teljes érték nem 100 százalék. Ha megjelenik ez az üzenet, folytathatja a sorok szerkesztését. A lap bezárása előtt viszont a teljes százalékos értéknek 100-nak kell lennie.

[![Bevételütemezés részletei.](./media/revenue-schedule-details-2nd-scrn.png)](./media/revenue-schedule-details-2nd-scrn.png)

## <a name="inventory-setup"></a>Készletbeállítás

Ha a dokumentumon nem szerepelnek cikkek, akkor a kiadott termékek bevételeit az értékesítési rendelések értékesítési kategóriáival vagy a szabadszöveges számlákon nem jelenítheti meg, csak az értékesítési rendeléseken. A kiadott termékek beállításakor megadott beállítások határozzák meg a cikk bevételének a megjelenítését. A beállítások például meghatározzák meg, hogy sor kerül-e a bevételi ár felosztására, illetve hogy a bevételt bevételi ütemezéssel halasztották-e el.

A beállítást kezdheti a **Cikkcsoport** oldal (**Bevételmegjelenítés \> Beállítás \> Készlet- és termékbeállítás \> Cikkcsoport**) **Bevételmegjelenítés** gyorslapján. Ez a lap számos beállítási mezőt tartalmaz. Ezek a mezők csak a rendszerben létrehozott új kiadott termékek esetében használatosak az alapértelmezett értékek beállítására. Az új termékek létrehozásakor a rendszer alapértelmezés szerint az itt megadott értékeket használja a cikkcsoporthoz. A kiadott termékek alapértelmezett értékeit a **Kiadott termékek** oldalon (**Bevételmegjelenítés \> Beállítás \> Készlet- és termékbeállítás \> Kiadott termékek**) írhatja felül. A kiadott termékekhez beállított alapértelmezett értékeket ezután a program átviszi az értékesítési rendelésbe.

## <a name="item-groups-and-released-products"></a>Cikkcsoportok és kiadott termékek

### <a name="define-the-revenue-schedule"></a>A bevételütemezés meghatározása

Az értékesítési rendelés sorában szereplő bevétel el lesz halasztva, ha a bevételi ütemezést meghatározza a kiadott termékhez, majd alapértelmezés szerint használja az értékesítési rendelés sorában. Ha a beállítást alapértelmezettként kell használni a termékhez, akkor a bevételi ütemezés a **Cikkcsoport** oldal (**Bevételmegjelenítés \> Beállítás \> Készlet- és termékbeállítás \> Cikkcsoport**) **Bevételmegjelenítés** gyorslapján határozható meg. A kiadott termék beállítását a **Kiadott termékek** oldal (**Bevételmegjelenítés \> Beállítás \> Készletbeállítás \> Kiadott termékek**) **Bevételmegjelenítés** gyorslapján is megadhatja.

A **Bevételütemezés** mezőben válassza ki azt a bevételütemezést, amely ahhoz az időszakhoz tartozik, amelyre halasztani kell a bevételt. A bevétel ütemezése automatikusan bekerül az értékesítési rendelés sorába, és az ütemezés részletei létrejönnek az értékesítési rendelés számlájának a feladásakor.

### <a name="define-the-revenue-price"></a>A bevételi ár meghatározása

A cikkcsoportok és a kiadott termékek a medián ár használatával vagy az engedmény felosztásával állíthatók be. A használt módszertől függően különböző beállításokat kell megadni a **Kiadott termékek** oldalon:

- **A bevételfelosztás aktív** – Használja az **Igen** értéket, ha fel szeretné venni a kiadott terméket a bevételfelosztási számításba. Ha a beállítás értéke **Nem**, akkor a kiadott termék a medián árat használja (ha van megadott medián ár). Ha nincs megadva a medián ár, akkor az értékesítési rendelés sorában szereplő egységárat használja a rendszer a bevétel vagy a halasztott bevétel feladására.
- **Bevétel típusa** – Válassza ki azt a bevételtípust, amely meghatározza a kiadott terméket:

    - **Fontos** – A cikk egy szervezet bevételének elsődleges forrása. Ez az érték az alapértelmezett beállítás.
    - **Nem fontos** – A cikk nem egy szervezet bevételének elsődleges forrása. Amikor a medián ár beállításait használja, a program a hozzárendelés előtt levonja a medián árból az árat. Egy fontos elemhez például olyan fix árat kell használni, amelyet meg kell jeleníteni a bevételhez. Ha van engedmény, előfordulhat, hogy a kedvezmény levonható a fontos cikk bevételeiből – de **csak** a rögzített ár összegéig. Az engedmény többi része a nem fontos cikkek bevételéből lesz levonva. Másik lehetőségként előfordulhat, hogy az engedmény nem lesz levonva a fontos cikk bevételéből.
    - **Támogatási szerződés feladása** – A cikk támogatja a vevőnek történő értékesítésben szereplő többi elemet. A bevételi ár az értékesítésben foglalt fontos és nem fontos termékek között oszlik meg. A beállításoktól függően előfordulhat, hogy a darabszámú cikkekhez nem szükséges meghatározni az értékesítési rendelés sorában a szerződés kezdő és záró dátumát.

- **Kizárás a levonásból** – Ha az **Igen** értéket használja, jelezheti, hogy a cikk medián ára nem módosítható a meghatározott minimális százalék alá vagy a maximális százalék fölé. A bevételi árak az értékesítési rendelésben szereplő másik kiadott termék bevételi áraiból származnak majd. Ha a beállítás értéke **Nem**, akkor a cikk medián ára korrigálható vagy levonható. Ügyeljen rá, hogy ha több medián árú cikket árul , akkor legalább egy olyan kiadott terméket be kell állítani, amelynél a **Kizárás a levonásból** beállítás értéke **Nem**. Így lesz legalább egy olyan cikk, amelyhez hozzárendelhető a bevételi ár eltérése.
- **Medián ár** – Ha az **Igen** értéket használja a beállításhoz, azzal jelezheti, hogy a cikk bevételi árát úgy kell beállítani, hogy egyenlő legyen a medián árral, ha alacsonyabb a megadott minimális vagy magasabb a maximális tűréshatárnál, és a levont összeget olyan termékeket tartalmazó sorokhoz kell rendelni, amelyeknél a **Kizárás a levonásból** beállítás értéke **Nem**.

    - **Maximális tűréshatár** – Adja meg, hogy az érték hány százalékkal lehet a medián ár felett.
    - **Minimális tűréshatár** – Adja meg, hogy az érték hány százalékkal lehet a medián ár alatt.

Miután megadta a kiadott termék beállításait, manuálisan kell megadnia a bevételi árat a forgalmi érték árának vagy a medián árnak (ha medián árat használ) a **Bevételi árak** oldalon (lépjen a **Bevételmegjelenítés \> Beállítás \> Készletbeállítás \> Kiadott termékek** részre, majd a műveleti ablaktábla **Eladás** lapjának **Bevételmegjelenítés** csoportjában válassza a **Bevételi árak lehetőséget**) való megadásával.

[![Bevételi árak.](./media/revenue-recognition-revenue-prices.png)](./media/revenue-recognition-revenue-prices.png)

Az ezen az oldalon manuálisan meghatározott bevételi ár határozza meg az egyes értékesítési rendelések bevételi árának megadott feltételek alapján történő felosztását. A rendszer minden feltételt egyeztet az értékesítési rendelés sorával, és így határozza meg, hogy milyen bevételi árat kell használnia a felosztás során.

- **Cikk kódja** és **Cikk-kapcsolat** – Egy adott termék vagy termékcsoport esetében adható meg bevételi ár. Ha a **Cikk kódja** mezőben a **Tábla** lehetőséget választja, a **Cikk-kapcsolat** mezőben válassza ki a kiadott terméket. Ha a **Cikk kódja** mezőben a **Csoport** lehetőséget választja, a **Cikk-kapcsolat** mezőben válassza ki a cikkcsoportot.
- **Számlakód** és **Számla/csoport száma** – Az összes vevőhöz, egyéni vevőhöz vagy vevőcsoporthoz határozható meg bevételi ár. Ha a **Számla kódja** mezőben az **Összes** lehetőséget választja, akkor a program az összes vevőhöz használja az árat. Ha a **Számla kódja** mezőben a **Tábla** lehetőséget választja, a **Számla/csoport száma** mezőben válassza ki a vevőt. Ha a **Számla kódja** mezőben a **Csoport** lehetőséget választja, a **Számla/csoport száma** mezőben válassza ki a vevőcsoportot.
- **Pénznem** – Minden olyan pénznemhez külön bevételi árat kell megadni, amelyben ad meg értékesítési rendelést. Ha például jelenleg amerikai dollárban, kanadai dollárban és euróban értékesít, akkor mindhárom pénznemhez kell meghatároznia bevételi árat. A bevételi árat nem váltja át a rendszer egy adott pénznemről (például a könyvelési pénznemről) egy másik, a tranzakciókhoz használt pénznemre.
- **Összeg vagy a lista százalékos értéke** – Adja meg, hogy a bevételi ár összegként vagy a listaár százalékában van-e megadva. Ha a **Lista százalékos értéke** beállítást választja, akkor a felhasználók a medián árat a listaár százalékában adhatják meg, és nem kell összeget használniuk. A **Lista százalékos értéke** csak olyan kiadott termékekhez használatos, amelyek darabszámú cikkekként lettek beállítva.
- **Bevételfelosztási ár** – Az **Összeg vagy a lista százalékos értéke** mezőben kiválasztott értéktől függően adjon meg egy összeget vagy százalékos értéket a bevétel értékesítési rendelésen lévő elemek közötti felosztásához használatos bevételi árhoz.
- **Kezdő dátum** és **Záró dátum** – Adja meg azt a dátumtartományt, amikor a bevételi ár aktív. Ezeknek a mezőknek az értékét nem kötelező megadni.

Ha a **Főkönyvi paraméterek** oldal **Engedményfelosztási mód engedélyezése** beállításának az értéke **Igen**, és ha a kiadott termékhez tartozó **Bevétel típusa** mező értéke **Támogatási szerződés feladása**, akkor azokat a cikkeket is meg kell adnia, amelyeket a kiadott termék támogat. Ez a beállítás az **Alapok beállítása** oldalon (lépjen a **Bevételmegjelenítés \> Beállítás \> Készletbeállítás \> Kiadott termékek** részre, majd a műveleti panel **Eladás** lapjának **Bevételmegjelenítés** csoportjában válassza az **Alapok beállítása** lehetőséget) adható meg.

Az **Alapok beállítása** oldalon minden olyan cikkcsoporthoz adjon meg egy rekordot, amelyet a cikk támogat. A bevétel felosztásakor a program a bevételi árat a darabszámú cikkek fontos és nem fontos részei között osztja fel.

### <a name="posting-profiles"></a>Feladási profilok

Három további feladási típus segíti a bevétel elhalasztását. Ezek a feladási típusok a **Feladás** oldal **Értékesítési rendelés** lapján (**Bevételmegjelenítés \> Beállítás \> Készlet- és termékbeállítás \> Feladás**) állíthatók be.

- **Halasztott bevétel** – Adja meg annak a bevételi árnak a fő számláját, amely a halasztott bevételhez (és nem a bevételhez) végez feladást. Ha az értékesítési rendelés sorához tartozik bevételi ütemezés, akkor a program elhalasztja a bevételi árat.
- **Eladott áruk halasztott beszerzési értéke** – Adja meg az eladott áruk beszerzési értékének összegéhez tartozó fő számlát, amely az eladott áruk halasztott beszerzési értékére végez feladást, ha a bevétel is el lett halasztva.
- **Számla bevételének részleges elszámolása** – Adja meg annak az elszámolási számlának a fő számláját, amely akkor használatos, ha az értékesítési rendelés részben számlázott vagy újrafelosztásra kerül sor. Az értékesítési rendelések teljes számlázása esetén ennek a számlának az egyenlege 0 (nulla) értékre áll vissza.

### <a name="bundles"></a>Csomagok

A csomagolt cikkek olyan egyedi kiadott termékek, amelyek úgy lettek beállítva, hogy összetevőket tartalmazzanak. A beállítást az anyagjegyzék (AJ) funkcióval lehet elvégezni. Ha egy értékesítési rendeléshez csomagolt cikket ad meg, akkor a rendszer az egyes összetevőket használja a bevételi árak és a bevételi ütemezések meghatározására. A vevőhöz tartozó nyomtatott dokumentumok (például az értékesítési rendelés és a számla) azonban a csomag cikkét tükrözik.

#### <a name="bundle-components"></a>A csomagok összetevői

A csomagban található összetevőket be kell állítani a **Kiadott termékek** oldalon (**Bevételmegjelenítés \> Beállítás \> Készlet- és termékbeállítás \> Kiadott termékek**). Ezek az összetevők kiadott termékek, és ugyanúgy kell beállítani őket, mint az anyagjegyzékben szereplő termékeket. Egy kiadott termék lehet például **Cikk** vagy **Szolgáltatás** típusú, de a terméket olyan cikkmodellcsoporthoz kell hozzárendelni, amely esetében a **Raktározott termék** beállítás értéke **Igen**. További részletek az anyagjegyzék cikkeinek a beállítási dokumentációjában találhatók.

Az összetevőket – mintha egy értékesítési rendelésen egyenként értékesíthető termékek lennének – be kell állítani a bevételmegjelenítéshez. Győződjön meg például arról, hogy helyes bevételi árat adott meg az egyes összetevőkhöz, illetve hogy beállította az áralapot a darabszámú cikkekhez.

#### <a name="bundle-items"></a>Cikkek csomagolása

Amikor csomagolt cikket állít be, két mezőt kell kitöltenie a **Kiadott termékek** oldalon (**Bevételmegjelenítés \> Beállítás \> Készlet- és termékbeállítás \> Kiadott termékek**):

- A **Mérnöki feladatok** gyorslap **Termelés típusa** mezőjében a cikket be kell állítani egy anyagjegyzék tételeként.
- Az **Általános** gyorslap **Csomag** mezőjében meg kell jelölni a cikket csomagolt cikk-ként.

Ezután az összetevőket hozzá kell rendelni a csomag/anyagjegyzék szülőcikkéhez az **Anyagjegyzék-verziók** oldalon (lépjen a **Bevételmegjelenítés \> Beállítás \> Készlet- és termékbeállítás \> Kiadott termékek** részre, és a műveleti panel **Mérnöki feladatok** lapjának **Anyagjegyzék** csoportjában válassza ki az **Anyagjegyzék-verziók** lehetőséget). További részletek az anyagjegyzékek beállítási dokumentációjában találhatók.

[![Kiadott termékek, anyagjegyzék ütemezései.](./media/revenue-recognition-bom-scheduleds.jpg)](./media/revenue-recognition-bom-scheduleds.jpg)

Ha a csomag szülőcikkét és a csomag összetevőit beállítja felosztáshoz, akkor a program – a bevételhez való hozzájárulás százalékos értéke alapján – felosztja a csomag bevételi árát az összetevők között.

## <a name="project-setup"></a>Projekt beállítása

A bevételmegjelenítés idő- és anyagelszámolású projektből létrehozott értékesítési rendelésekhez is használható. A projektekből származó értékesítési rendelésekhez csak meg kell határozni a projekt számláinak a feladásához használt projektfeladási profilokban szereplő fő számlákat. A fő számlák a **Főkönyvi feladás beállítása** oldalon (**Bevételmegjelenítés \> Beállítás \> Projekt beállítása \> Főkönyvi feladás beállítása**) határozhatók meg.

- **Halasztott számla bevétele** (a **Bevételi számlák** részen) – Adja meg annak a bevételi árnak a fő számláját, amely a halasztott bevételhez (és nem a bevételhez) végez feladást. Ha az értékesítési rendelés sorához tartozik bevételi ütemezés, akkor a program elhalasztja a bevételi árat.
- **Halasztott költség** (a **Költségszámlák** részen) – Adja meg az eladott áruk beszerzési értékéhez tartozó fő számlát, amely az eladott áruk halasztott beszerzési értékére végez feladást, ha a bevétel is el lett halasztva.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
