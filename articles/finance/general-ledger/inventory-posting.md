---
title: Készlet feladása
description: Ez a témakör bemutatja a Készlet feladása lapot a Készletfeladási profil lapon.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 464ffccd658003271b517038f430914fd5d8d50e
ms.sourcegitcommit: 6744cc2971047e3e568100eae338885104c38294
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/20/2022
ms.locfileid: "8783329"
---
# <a name="inventory-posting"></a>Készlet feladása

A **Készletfeladási** profilok lap **Készlet** lapja a készlettranzakciók főkönyvbe való feladásának szabályozására használható. A készlettranzakciók olyan tranzakciók, amelyek nem értékesítési rendelésekből, beszerzési rendelésekből vagy termelési rendelésekből állnak. A fizikai és pénzügyi frissítéseket automatikusan feladják a készletbe egyszerre. Kivételt képeznek az olyan áthozott rendelések, amelyek a készlet ki- és fogadása során elkülönítik a fizikai és a pénzügyi frissítéseket.

Az alábbi táblázat néhány példát mutat be a készlettranzakciókra.

| Tranzakció típusa | Bevételezés vagy kiadás | Tényleges feladás, pénzügyi feladás vagy mindkettő | Leírás |
|---|---|---|---|
| Szállítás | Mindkettő | Mindkettő | <p>A mozgási napló olyan készletnapló, amely készlet hozzáadására vagy eltávolítására használható. Úgy működik, mint egy készletkorrekciós napló. Az egyik kulcsfontosságú különbség az, hogy meg van adva a tételt ellentételét eltló fő számla.</p><p>A mozgási napló a kezdő egyenlegeket és az egyszeres korrekciókat adja meg, ezeket költségként kell elszámolni. Például akkor használatos, amikor a készletet eltávolítják az értékesítési mintából.</p><p>A napló feladása során a tényleges és a pénzügyi frissítések párhuzamosan futnak le.</p><p>A naplósorok pozitív mennyiségei bevételezéseket, a negatív mennyiségek pedig problémákat képviselnek.</p> |
| Készlethelyesbítés | Mindkettő | Mindkettő | A készlet-helyesbítési naplók a készlet hozzáadására és eltávolítására használhatók. Ezzel nem lehet ellenszámlát választani. A főkönyvi bejegyzés frissítéséhez **csak** a Készletfeladási profil lapon megadott számlák használhatók. |
| Átvitel (napló) | Mindkettő | Mindkettő | <p>Az áttárolási naplók segítségével lehet készletet áthelyezni egyik helyről a másikra (tárolási dimenziók használatával). Új termék vagy nyomon követési dimenziókkal frissíti a készlettranzakciók termékinformációját.</p><p>Az átmozgatási napló egy sort hoz létre a cikk mozgására. Ennek a sornak van a készletdimenziókhoz a "1" és a "to" mezője. Az átadási napló minden sora két készlettranzakciót hoz létre. Egy tranzakció jön létre a "from" készletdimenziókhoz. Ez a kiadásnak megfelelő, negatív mennyiséget jelent. A másik tranzakció a "to" készletdimenziókhoz jön létre. A bevételezést jelöli, és pozitív mennyiséget képvisel.</p><p>Előfordulhat, hogy az átmozgatási naplók nem hoznak létre bizonylatot, ha a készletmozgás nem pénzügyi jellegű átmozgatásnak tekinthető. A "from" és a "to" **·** **·** **érték esetében eltérő készletdimenziók nincsenek megjelölve a Pénzügyi készlet beállítással a Tárolási dimenziócsoport vagy a Nyomon követési dimenziócsoport** oldalon. Ha **például** **a** Pénzügyi készlet beállítás nincs megjelölve a Hely dimenzióban, és a készletet ugyanannak a helynek és raktárnak egy másik helyéről áthelyezi, akkor nem jön létre bizonylat.</p><p>Az átmozgatási naplók különböznek az átmozgatási rendelésektől, mert a mozgáshoz nincsenek dokumentumok. A frissítés egyetlen tranzakcióban, a napló felével történik. Ezzel szemben az áttárolási rendelés kitárolási és szállítási dokumentumokat generálhat, és a tranzakció feldolgozásához két frissítést igényel.</p> |
| Átmozgatási rendelés szállítása | Probléma | Mindkettő | <p>Új átátviteli rendelés létrehozásakor egy sor és egy készletdimenzió minden kombinációjához két készlettranzakció van: egy az áthozott rendelés szállítmánya, és egy az áthozott rendelés bevételezéséhez. Az áthozott rendelés szállításakor két készlettranzakció frissül, valamint két további készlettranzakció jön létre az áruk átviteléhez, összesen négy készlettranzakcióval.</p><ol><li>Az első készlettranzakcióval lehet eltávolítani a cikket a forrásraktárból és a helyről. A tranzakció kiadási állapota Eladva **annak** jelzésére, hogy a cikk már nem érhető el a raktárban.</li><li>A második készlettranzakcióval lehet hozzáadni a cikket ahhoz a tranzitraktárhoz, amely ahhoz a raktárhoz van kiválasztva, amelyből a cikket áthelyezik. A tranzakció bevételezési állapota **Beszerzett**.</li><li>A harmadik készlettranzakció a tranzitraktárból a célraktárba történő átvitelre történik. A tranzakció kiadási állapota Foglalt **tényleges**. Ez az állapot gondoskodik arról, hogy a cikket ne használhatja fel egy másik folyamat, amíg a szállítás alatt van.</li><li>A negyedik készlettranzakció az áruknak a célraktárba történő bevételezésére. A tranzakció bevételezési állapota **Megrendelve**.</li></ol> |
| Átmozgatási rendelés bevételezése | Fogadás | Mindkettő | Amikor a célraktárba átrendelt rendelés érkezik, az átszállítási raktárban (az előző példában 3. szám) **készlettranzakció** készletállapota Értékesítés állapotra módosul, **a** célraktár készlettranzakciója pedig a Beszerzett állapotra. |
| Anyagjegyzékek | Mindkettő | Mindkettő | Az anyagjegyzéknaplók segítségével készként jelentheti a terméket, és termelési rendelés nélkül felhasználhatja a folyamat során felhasznált nyersanyagokat. Az anyagjegyzéknapló általában legalább egy pozitív sort tartalmaz a késztermékhez, és egy vagy több negatív sort a felhasznált nyersanyagokhoz. A készterméksor bevételezés a készletbe, míg a negatív sorok a nyersanyagok készletből történő bevételezései. Anyagjegyzéknapló létrehozásakor az első sor az anyagjegyzék fejléce, a további sorok pedig az anyagjegyzéksorok. |
| Készlet tulajdonosváltozása | Mindkettő | Mindkettő | A készlet tulajdonosváltási naplója használatos a feladott készlet tulajdonosának szállítóról a szervezetre való változására. A készlet tulajdonosváltási naplói hasonlítanak a készletátviteli naplókra, amelyekben két készlettranzakció kapcsolódik egy-egy sor és egy készletdimenzió minden egyes kombinációjához. Az egyik készlettranzakció eltávolítja **a** készletet a Tulajdonos dimenzióban a szállítótól, a másik a Tulajdonos dimenzióban hozzáadja a cikket a jogi **személyhez**. |
| Cikk érkezése | Fogadás | Tényleges | A cikkérkezési naplók segítségével a készlet bevételezési állapotát Regisztrálva állapotra lehet **frissíteni**. Jellemzően az áruk beszerzési rendelésének bevételezésére és az értékesítési rendelések visszaküldésére használatos. |
| Termelések beérkezése | Fogadás | Tényleges | A termelésbeérkezési napló hasonlít a cikkérkezési naplóra. A termelési bemenet a késztermékek raktári termelési rendelésből történő fogadására használható. A napló feladása során a készlettranzakció állapota Regisztrálva állapotra **módosul**. |
| Leltár | Mindkettő | Mindkettő | A leltárnapló segítségével lehet rögzíteni a készletdimenziók adott kombinációjához leltárba adott cikkek mennyiségét. A készlettranzakciók akkor jön létre, amikor a naplósorhoz számlálási különbözet van. Ha magasabb a leszámolt mennyiség, akkor bevételezést okoz a készletben. Az a sor, amelynél kisebb a leszámolt mennyiség, kiadást okoz a készletből. Olyan sorok, amelyekben a leszámolt mennyiség megfelel a várt mennyiségnek, nincsenek készlettranzakciók. |
| Címkeleltár | Nem alkalmazható | Nem alkalmazható | A címkeleltárnaplók a hozzárendelt és a teljes készletleltárban használt készletcímkék nyomon követésére használatosak. A napló segítségével címkeszámot rendelhet hozzá egy cikk és egy készletdimenzió meghatározott kombinációjához, és nyomon követheti a címke állapotát a teljes készlet ideje alatt. A címkeleltárnaplók nem hoznak létre készlettranzakciókat. |
| Minőségi rendelések | Probléma | Tényleges | <p>A minőségi rendelés segítségével lehet rögzíteni egy adott készletben egy adott tétel teszteredményét. Minden minőségi rendelés egy meglévő készlettranzakcióhoz vagy egy készlettranzakció egy részével áll kapcsolatban.</p><p>A minőségi rendelés két esetben hoz létre új készlettranzakciót:</p><ul><li>A minőségi rendelés romboló tesztként **van megjelölve** az Általános **lapon**.</li><li>A minőségi rendelés karanténként van megjelölve **az** **Általános** lapon, és a teszt nem felel meg az ellenőrzésen. Ebben az esetben két készlettranzakció jön létre. Az egyik készlettranzakció eltávolítja a cikket az eredeti készletdimenzió-kombinációból és -helyről, a másik hozzáadja a cikket a karanténraktárhoz.</li></ul> |
| Karanténutasítások | Mindkettő | Mindkettő | <p>A karanténutasítások készlettranzakciói olyanak, mint egy átrendelt rendelés. A karanténraktár a készlet nyomon követésére használható. Két bevételezési tranzakció és két kiadási tranzakció van.</p><p>A rendelés kezdeti létrehozásakor két tranzakció jön létre. A bevételezési tranzakció állapota Megrendelve ahhoz **a** karanténraktárhoz, amely ahhoz a raktárhoz van kapcsolva, ahol a cikk található. A kiadási tranzakció állapota Megrendelt **abban** a raktárban, ahol a cikket tárolják.</p><p>A karanténutasítás elindítani a karanténutasítást, két további tranzakció jön létre, és a meglévő tranzakciók frissülnek. A karanténraktár bevételezési tranzakciója **állapota** Beérkezettre módosul, **a tárolási raktár kiadási tranzakciója pedig Levonva állapotúra**.</p><p>A két új tranzakció a tárolási raktárba való esetleges visszamozgás jelzésére használható. A bevételezési tranzakció állapota Megrendelve **a** tárolási raktárhoz, **és a kiadási tranzakció állapota Foglalt fizikai** a karanténraktárban.</p><p>Ha készként jelent egy karanténutasítást, akkor ez a művelet a karanténutasítás fizikai frissítését képviseli. A tárolási raktár bevételezési állapota Beérkezett állapotra **módosul**.</p><p>A karanténutasítás végén ez a művelet a karanténutasítás pénzügyi frissítését képviseli. A kiadási tranzakciók állapota Eladva **állapotúra**, a bevételezési tranzakciók állapota Pedig "Beszerzett" állapotúra **módosul**.</p><p>Arra is lehetőség van, hogy a karanténutasítást selejtezje. Ez a művelet eltávolítja a cikket a készletből. Karanténutasítás selejtezése esetén csak három tranzakció marad. A rendszer eltávolítja a tárolási raktár bevételezési tranzakcióját, és a fennmaradó bevételezési tranzakció állapotát a Rendszer Beszerzett állapotúra **frissíti**. A két kiadási tranzakció állapota Eladva állapotra **módosul**. Ez a művelet a rendelés fizikai és pénzügyi frissítése.</p> |

## <a name="fixed-receipt-price-posting"></a>Rögzített bevételezési ár feladása

A rögzített bevételezési ár segítségével elszámolóárat lehet használni a termékekre. Lehetőség van az **Elszámolóáras** **beállítás cikkmodellcsoport-oldalon** való beállításának lehetőségének beállítására is. A rögzített bevételezési ár használata között az a legnagyobb eltérés, hogy az éppen konfigurált önköltségi ár lesz használva a cikkhez a készletbe való bevételezés feladott feladásakor. Rögzített bevételezési árhoz nincs költség-átértékelési folyamat. Pénzügyi frissítés feladása során a rendszer a feladáskor az aktuális önköltségi árat használja. Ha a bevételezéskor használt önköltségi ár és a számla eltér, az eltérést a rögzített bevételezési ár eredményszámláira fogja ad fel a vevő.

A termékek rögzített bevételezési árának igény szerint a következő konfigurációt kell végrehajtania:

- Jelölje be **a Tényleges készlet feladása** jelölőnégyzetet **a Cikkmodellcsoport** lapon a készlettranzakció-sorban kiválasztott cikknél.
- Jelölje be **a Rögzített bevételezési** ár jelölőnégyzetet a Cikkmodellcsoport **lapon**.
- Adja meg a fő számlákat az alábbi feladási típusokhoz a Készletfeladási **profil oldalon**:

    - Rögzített bevételezési ár nyeresége
    - Rögzített bevételezési ár vesztesége

További tájékoztatás: Rögzített [bevételezési ár](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="catch-weight-posting"></a>Akkreta feladása

A catch weight termékeket gyakran használják olyan iparágban, mint például az élelmiszeriparban, ahol a termékek kismértéktől, mérettől vagy mindkettőtől függően kismértékben változhatnak. A tényleges s tömegű termékek két mértékegységet használnak: egy készletegységet és egy tényleges súly egységét. A raktárba történő készletsúly eltérő lehet attól a súlytól, amikor a készletet kiadták a raktárból. A tényleges s súlyú termék feldolgozása korrigálja a készletet.

Ha eltérés van a tényleges súlyban, **·** **·** **a különbözeteket a készletfeladási profil oldalának Tényleges súly veszteség és Tényleges súly nyereség mezőiben megadott számlákra adja fel** a rendszer. Általában mindkét mezőben ugyanaz a fő számla van megadva.

Az alábbi táblázat példákat mutat be az alapértelmezett feladási típusokra, és tartalmazza a minta fő számlákat és leírásokat.

- A "Tartozik/Követel" Oszlop jelzi, hogy a tranzakció jellemzően tartozik vagy követel. Bizonyos esetekben a tranzakció tartozásokat és jóváírásokat is feladhat.
- Az "Elszámolószámla" oszlop azt jelzi, hogy a feladás típusa elszámolószámla. Más szóval az erre a számlára feladott összeg automatikusan sztornírozódik egy későbbi tranzakció feladása során.
- A "P/F" oszlop jelzi a feladás típusát. A "P" a tényleges feladást, az "F" a pénzügyi feladást jelenti.
- A "Követés" oszlop jelzi, hogy a feladási típus fő számlája általában megegyezik-e egy másik feladási típus fő számlájával. Ez a jellemzően a feladáshoz használt feladási típust jelzi.

> [!NOTE]
> A táblázatban szereplő fő számlák és fő számlák nevei csak javaslatok. Javasoljuk, hogy a könyvelővel együtt határozza meg, hogy az üzleti igényeknek megfelelő konfigurációt szeretné-e meghatározni.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | K/F | Kövesse | Leírás |
|---|---|---|---|---|---|---|---|---|
| Tényleges súlyhoz kapcsolódó veszteségszámla | 510520 | Készlethelyesbítés | Költség | | Nem | Mindkettő | Tényleges súlyhoz kapcsolódó nyereségszámla | Ez a számla akkor használatos, ha olyan készlettranzakciót ad fel, ahol kisebb a tényleges súly összege. |
| Tényleges súlyhoz kapcsolódó nyereségszámla | 510520 | Készlethelyesbítés | Költség | | Nem | Mindkettő | Tényleges súlyhoz kapcsolódó veszteségszámla | Ez a számla akkor használatos, ha olyan készlettranzakciót ad fel, ahol magasabb a tényleges súly összege. |

A cikkekkel [kapcsolatban](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.md)[a raktárkezelésben található a cikkekkel és a cikkekkel kapcsolatos, a "Catch weight" termékfeldolgozással kapcsolatos további tájékoztatás.](/supply-chain/warehousing/catch-weight-processing.md)

## <a name="inventory-to-fixed-asset-transfer-posting"></a>Készlet a tárgyi eszköz átvitelének feladása

A készlet – tárgyieszköznapló (**Tárgyi eszközök** \> **·** \> **·**– Naplók – Tárgyieszköznaplók – naplók) segítségével lehet a cikkeket a készletből áthelyezni és tárgyi eszközre konvertálni. További tudnivalókért lásd: [Tárgyieszköz-integráció](/fixed-assets/fixed-asset-integration.md).

Az alábbi táblázat példákat mutat be az alapértelmezett feladási típusokra, és tartalmazza a minta fő számlákat és leírásokat.

- A "Tartozik/Követel" Oszlop jelzi, hogy a tranzakció jellemzően tartozik vagy követel. Bizonyos esetekben a tranzakció tartozásokat és jóváírásokat is feladhat.
- Az "Elszámolószámla" oszlop azt jelzi, hogy a feladás típusa elszámolószámla. Más szóval az erre a számlára feladott összeg automatikusan sztornírozódik egy későbbi tranzakció feladása során.
- A "P/F" oszlop jelzi a feladás típusát. A "P" a tényleges feladást, az "F" a pénzügyi feladást jelenti.
- A "Követés" oszlop jelzi, hogy a feladási típus fő számlája általában megegyezik-e egy másik feladási típus fő számlájával. Ez a jellemzően a feladáshoz használt feladási típust jelzi.

> [!NOTE]
> A táblázatban szereplő fő számlák és fő számlák nevei csak javaslatok. Javasoljuk, hogy a könyvelővel együtt határozza meg, hogy az üzleti igényeknek megfelelő konfigurációt szeretné-e meghatározni.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | K/F | Kövesse | Leírás |
|---|---|---|---|---|---|---|---|---|
| Tárgyi eszköz kiadása | 180100 | Materiális tárgyi eszközök | Eszközök | Jóváírás | Nem | Mindkettő | Nem alkalmazható | Ez a számla akkor használatos, amikor készletet ad fel a tárgyieszköznaplóba egy cikk készletről való eltávolítására és tárgyi eszközre való átalakításakor. |

## <a name="moving-average-posting"></a>Mozgó átlag feladása

A mozgó átlag állandó költségszámítási módszer, amely az átlag elven alapul. A készlet-kiadások költségei nem változnak, ha a beszerzési költség meg nem történik. A különbség tőkésített, és arányos számításon alapul. A fennmaradó összeg kiadásként van könyvelve.

Az alábbi táblázat példákat mutat be az alapértelmezett feladási típusokra a minta fő számlákkal és leírásokkal.

- A "Tartozik/Követel" Oszlop jelzi, hogy a tranzakció jellemzően tartozik vagy követel. Bizonyos esetekben a tranzakció tartozásokat és jóváírásokat is feladhat.
- Az "Elszámolószámla" oszlop azt jelzi, hogy a feladás típusa elszámolószámla. Más szóval az erre a számlára feladott összeg automatikusan sztornírozódik egy későbbi tranzakció feladása során.
- A "P/F" oszlop jelzi a feladás típusát. A "P" a tényleges feladást, az "F" a pénzügyi feladást jelenti.
- A "Követés" oszlop jelzi, hogy a feladási típus fő számlája általában megegyezik-e egy másik feladási típus fő számlájával. Ez a jellemzően a feladáshoz használt feladási típust jelzi.

> [!NOTE]
> A táblázatban szereplő fő számlák és fő számlák nevei csak javaslatok. Javasoljuk, hogy a könyvelővel együtt határozza meg, hogy az üzleti igényeknek megfelelő konfigurációt szeretné-e meghatározni.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | K/F | Kövesse | Leírás |
|---|---|---|---|---|---|---|---|---|
| Árkülönbség a mozgó átlaghoz | 510600 | Mozgóátlagonár-különbözet | Költség | Mindkettő | Nem | Mindkettő | Nem alkalmazható | Ez a számla akkor használatos, ha eltérés van a bevételezés és a számla költsége között. |
| Átértékelés a mozgó átlaghoz | 510610 | Átértékelés-átlag mozgatása | Költség | Mindkettő | Nem | Mindkettő | Nem alkalmazható | Ez a számla akkor használatos, amikor módosítja egy termék mozgóátlagának költségét. |

## <a name="sample-posting-profile-configuration"></a>Minta feladási profil konfigurációja

Az alábbi táblázat példákat mutat be az alapértelmezett feladási típusokra a minta fő számlákkal és leírásokkal.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | K/F | Kövesse | Leírás |
|---|---|---|---|---|---|---|---|---|
| Készletkiadás | 140100 | Anyagkészlet | Eszközök | Jóváírás | Nem | Mindkettő | Készletbevételezés | Ez a számla akkor használatos, ha a feladott készlettranzakció kiadás (negatív mennyiség), és nem kapcsolódik értékesítéshez, beszerzéshez vagy termeléshez. Ennek a számlának az ellenszámlája a Készletkiadás, veszteségszámla. Ez a számla általában a mérlegben képviseli a készletet. |
| Készletkiadás, veszteség | 510100 | Készlet nyeresége és vesztesége | Költség | Terhelés | Nem | Mindkettő | Készletkiadás, nyereség | Ez a számla akkor használatos, ha a feladott készlettranzakció kiadás (negatív mennyiség), és nem kapcsolódik értékesítéshez, beszerzéshez vagy termeléshez. A számla ellenszámlája a Készlet kiadási számlája. |
| Készletbevételezés | 140100 | Anyagkészlet | Eszközök | Terhelés | Nem | Mindkettő | Készletkiadás | Ez a számla akkor használatos, ha a feladott készlettranzakció bevételezés (pozitív mennyiség), és nem kapcsolódik értékesítéshez, beszerzéshez vagy termeléshez. A számla ellenszámlája a készletkiadás, a nyereségszámla. Ez a számla általában a mérlegben képviseli a készletet. |
| Készletkiadás, nyereség | 510100 | Készlet nyeresége és vesztesége | Költség | Jóváírás | Nem | Mindkettő | Készletkiadás, veszteség | Ez a számla akkor használatos, ha a feladott készlettranzakció bevételezés (pozitív mennyiség), és nem kapcsolódik értékesítéshez, beszerzéshez vagy termeléshez. A számla ellenszámlája a készletbevételezési számla. |
| Egységközi kötelezettség | 231500 | Egységközi kötelezettség | Kötelezettség | Terhelés | Nem | Mindkettő | | Ez a számla akkor használatos, amikor a készletet át kell helyezni a különböző készletdimenziók (például helyek) között, és a helyek között különbözik a cikk költsége. |
| Egységközi követelés | 131500 | Egységközi követelés | Eszközök | Jóváírás | Nem | Mindkettő | | Ez a számla akkor használatos, amikor a készletet át kell helyezni a különböző készletdimenziók (például helyek) között, és a helyek között különbözik a cikk költsége. |
