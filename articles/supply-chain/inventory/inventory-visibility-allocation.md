---
title: Inventory Visibility – készlet felosztása
description: Ez a cikk bemutatja a készletfelosztási funkció beállítását és használatát, amelynek segítségével félreteheti a külön kijelölt készletet, hogy a legnyereségesebb csatornákat és vevőket teljesíteni tudja.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 449ca0616405ba589b92fba1ef078a4350d1e3b1
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762672"
---
# <a name="inventory-visibility-inventory-allocation"></a>Inventory Visibility – készlet felosztása

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Üzleti háttér és cél

A szervezeteknek gyakran előzetesen fel kell használniuk az elérhető készletüket a legfontosabb értékesítési csatornák, vevőcsoportok, régiók és promóciós események számára, hogy az előzetesen lefoglalt készletet megvédjük minden egyéb használattal szemben, és csak a felosztáshoz kapcsolódó értékesítési tranzakciókon keresztül lehet őket használni. A készlet láthatósága az értékesítés üzemeltetési tervezési folyamatának egyik összetevője, amely még a tényleges értékesítési tevékenységek vagy az értékesítési rendelések létrehozása előtt meg történik.

Például egy Contoso nevű vállalat, egy népszerű vállalat. Mivel a legutóbbi ellátásilánc-átvitel hatással van az érintett raktárkészletre, a Contoso csak korlátozott készleten van, és a lehető legjobban ki kell használnia azt. A Contoso online és üzleten keresztül is tevékenykedik. A vállalat mindegyik értékesítési csatornában van néhány fontos vállalati partner (piactér és nagy kiskereskedők), amelyek a számukra rendelkezésre álló készlet egy bizonyos részének mentését követelik meg. Ennek megfelelően a kerékpárvállalatnak képesnek kell lennie a csatornák készletelosztásainak egyenlegére és a VIP-partnerek várakozásainak kezelésére. Mindkét cél elérésének legjobb módja a készletfelosztás használata, hogy minden csatorna és kiskereskedők megkapják a meghatározott felosztott mennyiségeket, és ezt később el lehet adni a ügyfeleknek.

A készletfoglalásnak két alapvető üzleti célja van:

- **Készlet védelem (ringcing)** – a szervezetek előzetesen fel kívánják osztott vagy korlátozott készletet felosztani a csatornák, régiók, VIP vevők és leányvállalatok számára. A készlet láthatósági felosztási szolgáltatása okkal védi a felosztott készletet, így a többi felosztás, foglalás és egyéb értékesítési igény nem fogja befolyásolni a korábban lefoglalt készletet.
- **Túlértékesítési** ellenőrzés – a készlet láthatósági felosztási szolgáltatása lehetővé teszi a korábban lefoglalt mennyiségek korlátozását, így a fogadó fél (például csatorna vagy vevőcsoport) nem fogja túl felhasználtként felosztani őket, amikor a tényleges értékesítési tranzakció, amely az előzetes lefoglaláson alapul, életbe lép.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Felosztás definíciója a készlet láthatósági szolgáltatásában

### <a name="allocation-virtual-pool"></a>Virtuális foglalási készlet

Bár a készlet láthatósági felosztási funkciója nem teszi félre a fizikai készletmennyiségeket, *mégis* a rendelkezésre álló fizikai készletmennyiségre hivatkozik, hogy meghatározza a kezdeti rendelkezésre álló mennyiséget a virtuális készlet mennyiségének felosztása érdekében. A készlet láthatósága esetén a készletfoglalás egy nem teljes felosztás. Ez még a tényleges értékesítési tranzakciók előtt történik, és nem függ az értékesítési rendelésektől. A készletet feloszthatja például a legfontosabb értékesítési csatornákra vagy nagyvállalati kiskereskedőkre, mielőtt a végfelhasználók felkeresik az értékesítési csatornát vagy kiskereskedelmi üzletet, hogy megvásárolják azt.

### <a name="difference-between-inventory-allocation-and-soft-reservation"></a>A készletfelosztás és az előzetes foglalás közötti különbség

[Az soft foglalások](inventory-visibility-reservations.md) általában a tényleges értékesítési tranzakciókhoz (értékesítésirendelés-sorokhoz) kapcsolódnak. A foglalást és az soft foglalást egymástól függetlenül is fel lehet használni, de ha együtt szeretné használni őket, akkor a foglalást követően kell az soft foglalást is alkalmazni. Javasoljuk, hogy először a készletfoglalást, majd a felosztott mennyiségeken belül a tartalékok soft foglalását javasoljuk, hogy a közel valós idejű felhasználás a felosztással szemben megvalósításához szükséges. A további tudnivalókat lásd [: Felhasznált, mint egy soft reservation](#consume-to-soft-reserved).

A készletfelosztási funkció lehetővé teszi, hogy az értékesítők vagy a fő számlavezetők kezelni és előzetesen kiosztják a fontos készleteket a felosztási csoportok között (például csatornák, régiók és vevőcsoportok). Támogatja továbbá a felhasználásnak a felosztott mennyiségekhez történő valós idejű követését, beállítását és analitikát, hogy a feltöltést és újraelosztást időben el lehet végezni. Különösen fontos, hogy valós idejű rálátás legyen a felosztásra, a felhasználásra és a felosztási egyenlegre a gyors értékesítési és promóciós események során.

## <a name="terminology"></a>Fogalmak

A következő kifejezések és fogalmak jól használhatók a készletfelosztásokkal kapcsolatos vitafórumokban:

- **Felosztási** csoport – az a csoport, amely a felosztást tulajdonja, például értékesítési csatorna, vevőcsoport vagy rendeléstípus.
- **Felosztási csoport értéke** – az egyes felosztási csoportok értéke. Például a *web vagy* *üzlet* lehet az értékesítési csatorna felosztási csoportjának értéke, *míg a VIP* *vagy* a normál a vevői felosztási csoport értéke.
- **Felosztási hierarchia** – a felosztási csoportok hierarchikus kombinálása egy módszer. Meghatározhatja például az *1*. hierarchiaszint csatornáját, *a* régiót 2. szintként, *a* vevőcsoportot pedig a 3. szintként. A készletfoglalás során a felosztási csoport értékének megadásakor követnie kell a felosztási hierarchia sorrendjét. Hozzárendelhet például 200 *piros tartományt a webcsatornához*, *a londoni* *régióhoz és a VIP vevőcsoporthoz*.
- **Felosztható** – *a virtuális közös készlet*, amely a további foglalásra rendelkezésre álló mennyiséget jelzi. Ez egy számított mérték, amelyet a saját képlettel szabadon meghatározhat. Ha az egyszerű foglalás funkciót is használja, javasoljuk, hogy ugyanazt a képletet használja a "felosztható" és a "foglalható" képlet kiszámításához.
- **Felosztva** – fizikai mérték, amely megjeleníti a felosztási csoportok által igénybeveható felosztott költségeket. Levonja a rendszer akkor, amikor a felhasznált mennyiséget hozzáadja.
- **Felhasznált** – fizikai mérték, amely azt jelzi, hogy az eredeti felosztott mennyiséghez felhasznált mennyiségek. Ahogyan ehhez a fizikai mértékhez számokat adnak hozzá, a Hozzárendelt fizikai mérték automatikusan csökken.

Az alábbi ábra a készletfoglalás üzleti munkafolyamatát mutatja be.

![Készlet láthatóságának felosztása üzleti munkafolyamata](media/inventory-visibility-allocation-flow.png "Készlet láthatóságának felosztása üzleti munkafolyamata")

Az alábbi ábra a felosztási hierarchiát és a felosztási csoportokat mutatja be. Az *itt látható virtuális* közös készlet a felosztásra elérhető mennyiség.

[<img src="media/inventory-visibility-allocation-hierarchy.png" alt="Inventory Visibility allocation hierarchy." title=" Készlet láthatóságának felosztási hierarchiája" width="720" />](media/inventory-visibility-allocation-hierarchy.png)

## <a name="set-up-inventory-allocation"></a>Készletfoglalás beállítása

A készletfelosztási funkció a következő összetevőkből áll:

- Az előre meghatározott, felosztáshoz kapcsolódó adatforrás, fizikai intézkedések és számított intézkedések.
- Nyolc szinttel testreszabható felosztási csoportok
- A felosztási alkalmazásprogramozási felületek (API-k) egy készlete:

    - felosztás
    - újrafokosítás
    - Nincs felosztva
    - Fogyasztanak
    - Lekérdezés

A felosztási funkció konfigurálási folyamata három lépésből áll:

- Engedélyezze a funkciót a Készlet láthatósága alkalmazásban **\> a Konfiguráció funkciókezelés & Beállítások foglalása funkcióval \>**.
- Az adatforrás [és a](inventory-visibility-configuration.md#data-source-configuration) rá vonatkozó intézkedések [beállítása](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- A felosztási csoport nevének és hierarchiájának beállítása.

### <a name="predefined-data-source"></a>Előre definiált adatforrás

Ha engedélyezi a felosztási funkciót, és hívja a konfigurációfrissítési API-t, a készlet láthatósága egy előre definiált adatforrást és több kezdeti beállítást hoz létre.

Az adatforrás neve `@iv`. Az alapértelmezett fizikai intézkedések készletét tartalmazza. Ezeket a konfiguráció adatforrására való felásás segítségével a Készlet láthatósága alkalmazásból **\> lehet megtekinteni**. A adatforrásnak **(Datasource ) @IV**. Bontsa ki `@iv` az adatforrást a kezdeti fizikai intézkedések listájának megtekintéséhez:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Válassza a Számított **mértékek lapot** a kiindulási számított mérték megtekintéséhez, amelynek neve `@iv.@available_to_allocate`:

- `@iv`

    - `@iv.@available_to_allocate` = `??`– `??``@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>További fizikai mértékek hozzáadása a felosztásra elérhető számított mértékhez

A felosztás csak akkor használható, ha helyesen be van állítva a felosztásra elérhető számított mérték (`@iv.@available_to_allocate`) képlete. Van például egy `fno``onordered` adatforrás, a mérték, `pos``inbound` az adatforrás és a mérték, `fno.onordered``pos.inbound` és a felosztás az készletben az összeg és a. Ebben az esetben tartalmaznia `@iv.@available_to_allocate` kell a képletet `pos.inbound``fno.onordered` és a képletet. Példa:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound`– `@iv.@allocated`

> [!NOTE]
> Az adatforrás `@iv` egy előre definiált adatforrás `@iv``@`, és az előtaggal meghatározott fizikai intézkedések előre meghatározottak. Ezek a intézkedések a felosztási funkció előre definiált konfigurációi, ezért ezeket ne módosítsa vagy törölje, vagy a felosztási funkció használata során váratlan hibákat fog látni.
>
> Az előre meghatározott számított mértékhez `@iv.@available_to_allocate` új fizikai mértékeket lehet hozzáadni, de a nevét nem szabad megváltoztatni.

### <a name="manage-allocation-groups"></a>Felosztási csoportok kezelése

Legfeljebb nyolc felosztásicsoport-név lehet beállítva. A csoportoknak hierarchiájuk van. A felosztási csoportok megtekintéséhez és frissítéséhez hajtsa végre a következő lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg **a Konfiguráció** lapot, majd a **Felosztás** lapon válassza a Konfiguráció szerkesztése **lehetőséget**. Alapértelmezés szerint van egy felosztási hierarchia, amely négy rétegből áll: `Channel` (felső réteg), (második réteg),`customerGroup``Region` (harmadik réteg) és `OrderType` (negyedik réteg).
1. Meglévő felosztási csoportot úgy távolíthat el, hogy az **X** betűt kiválasztja a csoport mellett. Úgy is hozzáadhat új felosztási csoportokat a hierarchiához, hogy közvetlenül beírásával be az egyes csoportok nevét a mezőbe.

    > [!IMPORTANT]
    > Ügyeljen, amikor törli vagy módosítja a felosztási hierarchia megfeleltetését. Az útmutatásért lásd a felosztás [használatának tippekét](#allocation-tips).

1. Amikor befejezte a felosztási csoport és a hierarchia beállításainak konfigurálását, mentse a módosításokat, **majd** válassza a Konfiguráció frissítése lehetőséget a jobb felső oldalon. A beállított felosztási csoportok értékei frissülnek, amikor a felhasználói felület vagy az API POST (/api/environment<wbr><wbr>/\{ environment environmentId\}<wbr>/allocation/allocation/allocate<wbr>) segítségével hoz létre felosztást. A két megközelítésről a későbbiekben ebben a cikkben található részletes információ.

Ha négy csoportnevet használ\[`channel`, és ezeket a `customerGroup` következőre állítsa, akkor `region``orderType`\] ezek a nevek a konfigurációfrissítési API hívata esetén érvényesek lesznek a felosztással kapcsolatos kérések esetén.

### <a name="tips-for-using-allocation"></a><a name="allocation-tips"></a> Tippek a felosztás használatához

- A felosztási funkciónak *minden* termékre a termékindex-hierarchia konfigurációjában beállított termékindex-hierarchia [szerint ugyanazon dimenziószinten kell használnia](inventory-visibility-configuration.md#index-configuration). Tegyük fel például, hogy az indexhierarchia \[`Site`, `Location`, `Color`. `Size`\] Ha egy termékhez \[`Site` mennyiséget foglal le a dimenziószinten, `Location` akkor `Color`\] a következő alkalommal, amikor fel szeretné osztani ezt a terméket, ugyanazon a szinten kell felosztani, \[`Site`,`Location``Color`\]. A szint \[`Site`, az `Location`, `Color` vagy a `Size`\]\[`Site`, használata `Location`\] esetén az adatok inkonzisztensek lesznek.
- **Felosztási csoportok és a hierarchia módosítása:** Ha már léteznek felosztási adatok a rendszerben, a meglévő felosztási csoportok törlése vagy a felosztási csoport hierarchiájának egy műszakja sérült lesz a felosztási csoportok között meglévő leképezésekben. Emiatt az új konfiguráció frissítése előtt mindenképpen manuálisan tisztítsa a régi adatokat. Mivel azonban az új felosztási csoportok hozzáadása a legalacsonyabb hierarchiához nem befolyásolja a meglévő hozzárendeléseket, nem szükséges az adatok tisztítása.
- A felosztás csak akkor sikeres, ha a termékben pozitív mennyiség `available_to_allocate` van.
- Ha egy magas felosztási szintű *csoport termékeit* alcsoporthoz is fel kell osztani, használja az `Reallocate` API-t. Például van \[`channel` egy felosztási csoport hierarchiája, `customerGroup`, `region`, `orderType`\]\[és néhány terméket online felosztási csoportból szeretne felosztani, a VIP-t\]\[az Online, VIP, EU\] alfelosztási csoportba, `Reallocate` az API segítségével áthelyezni a mennyiséget. Ha az API-t használja `Allocate`, a rendszer felosztja a mennyiséget a virtuális közös készletből.
- A teljes termék elérhetőségének (a [közös készletnek) a megtekintéséhez használja az aktuális lekérdezés API-ját](inventory-visibility-api.md#query-on-hand) a felosztásra rendelkezésre álló készletmennyiség *kéréséhez*. Ezt követően felosztási döntéseket hozhat ezen információk alapján.

## <a name="use-the-allocation-api"></a><a name="using-allocation-api"></a> A felosztási API használata

Jelenleg öt felosztási API van megnyitva:

- **POST /API<wbr>/environment<wbr>/\{environmentId/allocation\}<wbr>/allocate<wbr>** – ez az API a kezdeti felosztás létrehozásához használatos.
- **POST /API<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/unallocate** – ez az API a felosztott mennyiségek visszaállításával vagy eltávolításával használatos.
- **POST /API<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/reallocate** – ez az API a felosztott mennyiség meglévő felosztásból más felosztási csoportokba való áthelyezésére használható.
- **POST /API<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/consume** – ez az API a felosztott mennyiség levonásához (felhasználáshoz) szükséges.
- **POST /API<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation/query<wbr>** – ez az API a meglévő felosztási rekordoknak a felosztási csoportoknak és a hierarchiának az ellenőrzéséhez használható.

### <a name="allocate"></a>Lefoglalás

Egy, a megadott `Allocate` dimenziókkal rendelkezik termék foglalásához hívja meg az API-t. A kérelem törzsének sémája.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Például 10 mennyiséget szeretne lefoglalni a 10-es termékhez, az 1-es telephelyhez, a 11-es *·* *helyhez,* *a piros színhez,* az online *csatornához,* a VIP *vevőcsoporthoz és* az Egyesült Államok régiójához.*·* *·* Ehhez a felosztáshoz a következő törzstartalmat tartalmazza a hívás.

```json
{
    "id": "test101",
    "productId": "Bike",
    "groups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 10,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

A mennyiségnek mindig nagyobbnak kell lennie nullánál.

### <a name="unallocate"></a>Nincs felosztva

A művelet `Unallocate` sztornírozhatja az API-t`Allocate`. A negatív mennyiség nem engedélyezett műveletben `Allocate`. A törzs megegyezik `Unallocate` a `Allocate`.

### <a name="reallocate"></a>Újrafokozni

Az API segítségével `Reallocate` egy felosztott mennyiséget át lehet áthelyezni egy másik csoportkombinációba. A kérelem törzsének sémája.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "sourceGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "groups": {
        "groupD": "string",
        "groupE": "string",
        "groupF": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Át lehet például áthelyezni két olyan adatokat, \[amelyekben a site=1, location=11, color=\]\[piros a felosztási csoportból (Online, VIP, US\] to allocation group \[Online, VIP, EU\]`Reallocate`) az API hívása és a következő szöveg törzsszövegének biztosítása.

```json
{
    "id": "test102",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
    "groups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "EU"
    },
    "quantity": 2,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

### <a name="consume"></a>Felhasználás

Az API-t `Consume` használja a felhasználási mennyiség felosztással szembeni felad feladára. Ezt az API-t használhatja például a felosztott mennyiség valós intézkedésekhez való áthelyezésre. A kérelem törzsének sémája.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "physicalMeasures": {
        "datasource1": {
            "measure": "string" // Addition or Subtraction
        }
    }
}
```

Például nyolc olyan felosztott erőforrás van, \[amelyeknél a dimenziók helye=1, a hely=11, a szín=piros\]\[az Online, a VIP, az Egyesült Államok felosztási csoportjában \]. A következő felosztásra elérhető receptúra használható:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound`– `@iv.@allocated`

A nyolcat a mértékből kell `pos.inbound` felosztani.

Most három egész készletet értékesít, és kiveszi őket a felosztási készletből. Az áthelyezés regisztrálása érdekében a következő szöveg törzsével rendelkezik egy hívás.

```json
{
    "id": "test103",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "pos": {
            "inbound": "Subtraction"
        }
    }
}
```

A hívás után a termék felosztott mennyisége 3-val csökken. A készlet láthatósága ezen felül -3`pos.inbound` = *tényleges készletváltozási eseményt is generál*. Másik lehetőségként megtarthatja az `pos.inbound` értéket, és felhasználhatja a felosztott mennyiséget. Ebben az esetben azonban vagy létre kell hozni egy másik fizikai mértéket a felhasznált mennyiségek megtartása vagy az előre megadott mérték használata esetén `@iv.@consumed`.

Ebben a kérelemben figyelje meg, hogy a felhasznált kérés törzsében használt fizikai mértékhez az ellentétes módosító típust (Kiegészítés vagy Kivonás) kell használni, ellentétben a számított mérték módosítótípusával. Tehát ebben a felhasznált törzsben `iv.inbound` az érték `Subtraction` van, nem `Addition`.

Az `fno` adatforrás nem használható a felhasznált törzsben, mert mindig az volt az igény, hogy a készlet láthatósága nem módosíthatja az adatforrás adatait `fno`. Az adatforgalom egy egy mód, ami azt jelenti, `fno` hogy az adatforrás mennyiségi változásainak az Ellátásilánc-kezelés környezetből kell erednie.

### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a> Felhasznált, mint soft foglalás

Az `Consume` API a felosztott mennyiséget is felhasználhatja soft foglalásként. Ebben az esetben a `Consume` művelet csökkenti a felosztott mennyiséget, majd az adott mennyiségre kis mennyiséget foglal. Ez a megközelítés csak akkor használható, ha a [Készlet](inventory-visibility-reservations.md) láthatósága funkció is használatban van.

Például egy fizikai lefoglalást úgy adott `iv.softreserved` meg, mint. A rendelkezésre álló foglalás kiszámított mértékének képlete a következő:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound`– `iv.softreserved`

Ha ezt a beállítást a felosztási funkcióval együtt használni, hozzáadja `@iv.@allocated` a következő `iv.available_to_reserve` képlet előállításához:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound`– `iv.softreserved``@iv.@allocated`

Ezután frissítsen `@iv.@available_to_allocate` ugyanannak az értéknek a ére.

Ha 3 mennyiségű mennyiséget szeretne felhasználhatja, és közvetlenül lefoglalhatja ezt a mennyiséget, akkor a következő szöveg törzsével hívást lehet kérni.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "iv": {
            "softreserved": "Addition"
        }
    }
}
```

Ebben a kérelemben ne figyelje meg, hogy `iv.softreserved` az értéke `Addition` nem .`Subtraction`

### <a name="query"></a>Lekérdezés

Az API `Query` segítségével beolvassa egyes termékek felosztással kapcsolatos adatait. Az eredmények szűkítését dimenziószűrők és felosztási csoportszűrők használatával lehet szűrni. A dimenzióknak pontosan meg kell egyezniük a beolvassani kívánt eredménysel, \[például az 1. hely=11\]\[. hely esetén a nem kapcsolódó eredmények a hely=1, hely=11, szín=piros\] lesz.

```json
{
    "productId": "string",
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "groups": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
    },
}
```

Használja például a \[hely=1, location=11, szín=\] piros és üres csoport mezőt az összes felosztási rekord befoglalására:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

Használja \[a site=1, location=11, color=\] piros és \[csoport csatorna=Online, customerGroup=VIP, region=US\] felosztási rekordokat a csoport felosztási rekordjainak befoglalásához:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

## <a name="use-the-allocation-user-interface"></a>A felosztási felhasználói felület használata

A felosztások manuálisan kezelhetők a felhasználói felületen, **ha megnyitja a Készlet láthatósága alkalmazást, és a felosztást a Üzemeltetési láthatósági felosztásra \> használhatja**. Innen bármelyik műveletet végrehajthatja, amely az alábbi alszakaszok szerint van leírva.

### <a name="create-an-allocation"></a>Felosztás létrehozása

A következő lépések szerint hozhat létre felosztást a **Készlet** láthatósága alkalmazás Felosztás lapján.

1. Válassza ki a **felosztást**.
1. Az alapmezők, dimenziók és célfelosztási csoportok értékeinek beállítása. (Amikor kiválasztja az adatgyűjtési adatforrást a **A** Dimenziók szakasz első lépése a legördülő lista használata a dimenziók megadására (például `siteId`). Ezután adja meg a dimenzióértékeket a megjelenő mezőkben.)
1. Küldés **kiválasztása**

### <a name="consume-an-allocation"></a>Felosztás felhasználta

Felosztási **felhasználásra** a Felhasznált elem kiválasztása. Annak érdekében, hogy a helyes felosztási csoporton és hierarchián belül felhasználódjon fel, adja meg a szervezeti és dimenzióadatoknak azokat a készletét, amelyek a felosztás létrehozásakor megegyezik.

### <a name="reallocate-an-allocation"></a>Felosztás újrafelosztása

Válassza a **Reallocate** lehetőséget, ha a meglévő felosztott mennyiséget át kell áthelyezni egyik felosztási csoportból a másikba.

### <a name="query-existing-allocations"></a>Meglévő felosztások lekérdezése

Válassza **a Lekérdezés** lehetőséget, majd adja meg a termék, a szervezet, a dimenzió és a felosztási csoport értékeit a meglévő felosztások lekérdezési eredményének lekérdezéséhez.
