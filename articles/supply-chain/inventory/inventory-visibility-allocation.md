---
title: Inventory Visibility – készlet felosztása
description: Ez a cikk bemutatja a készletfelosztási funkció beállítását és használatát, amelynek segítségével félreteheti a külön kijelölt készletet, hogy a legnyereségesebb csatornákat és vevőket teljesíteni tudja.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: ccc3a8c4b3d0649397b1d1f9139f7feebf39b02f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852505"
---
# <a name="inventory-visibility-inventory-allocation"></a>Inventory Visibility – készlet felosztása

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Üzleti háttér és cél

Sok esetben a gyártóknak, kiskereskedőknek és más ellátásilánc-üzletkötőknek előre el kell osztaniuk a készletet a fontos értékesítési csatornákhoz, helyekhez és vevőkhöz, illetve meghatározott értékesítési eseményekhez. A készletfelosztás az értékesítés üzemeltetési tervezési folyamatának tipikus gyakorlata, amely még azelőtt meg történik, hogy a tényleges értékesítési tevékenységekre sor kerülne, és létrejönne egy értékesítési rendelés.

Például egy kerékpárvállalatnál korlátozott készlet áll rendelkezésre egy nagyon népszerű kerékpár számára. Ez a vállalat egyszerre online és üzleten belül is értékesítést tesz. A vállalat mindegyik értékesítési csatornában van néhány fontos vállalati partner (piactér és nagy kiskereskedők), amelyek a számukra rendelkezésre álló készlet egy bizonyos részének mentését követelik meg. Ennek megfelelően a kerékpárvállalatnak képesnek kell lennie a csatornák készletelosztásainak egyenlegére és a VIP-partnerek várakozásainak kezelésére. Mindkét cél elérésének legjobb módja a készletfelosztás használata, hogy minden csatorna és kiskereskedők megkapják a meghatározott felosztott mennyiségeket, és ezt később el lehet adni a ügyfeleknek.

A készletfoglalásnak két alapvető üzleti célja van:

- **Készlet védelem (ringfencing)** – a szervezetek előzetesen fel szeretnék osztani a korlátozott vagy korlátozott készletet a csatornák, régiók, VIP vevők és leányvállalatok prioritásának meghatározására. A készlet láthatósági felosztási szolgáltatása okkal védi a felosztott készletet, így a többi felosztás, foglalás és egyéb értékesítési igény nem fogja befolyásolni a korábban lefoglalt készletet.
- **Túlértékesítési** ellenőrzés – a készlet láthatósági felosztási szolgáltatása lehetővé teszi a korábban lefoglalt mennyiségek korlátozását, így a fogadó fél (például csatorna vagy vevőcsoport) nem fogja túl felhasználtként felosztani őket, amikor a tényleges értékesítési tranzakció, amely az előzetes lefoglaláson alapul, életbe lép.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Felosztás definíciója a készlet láthatósági szolgáltatásában

Bár a Készlet láthatósági szolgáltatásának felosztási funkciója nem teszi félre a tényleges készletmennyiségeket, *mégis* a rendelkezésre álló fizikai készletmennyiségre hivatkozik, hogy meghatározza a kezdeti rendelkezésre álló mennyiséget a virtuális készlet mennyiségének felosztása érdekében. A készlet láthatósága esetén a készletfoglalás egy nem teljes felosztás. Ez még a tényleges értékesítési tranzakciók előtt történik, és nem függ az értékesítési rendelésektől. A készletet feloszthatja például a legfontosabb értékesítési csatornákra vagy nagyvállalati kiskereskedőkre, mielőtt a végfelhasználók felkeresik az értékesítési csatornát vagy kiskereskedelmi üzletet, hogy megvásárolják azt.

A készletfoglalás és [a készlet-soft reservation közötti különbség](inventory-visibility-reservations.md) az, hogy az soft reservation általában a tényleges értékesítési tranzakciókhoz (értékesítésirendelés-sorokhoz) kapcsolódik. Ezért ha a felosztási és az együtt foglalási funkciókat együtt szeretné használni, ajánlott először készletfoglalást, majd utána a felosztott mennyiségekre felosztani az elosztást. A további tudnivalókat lásd [: Felhasznált, mint egy soft reservation](#consume-to-soft-reserved).

A készletfelosztási funkció lehetővé teszi, hogy az értékesítők vagy a fő számlavezetők kezelni és előre kiosztják a fontos készleteket a felosztási csoportok között (például csatornák, régiók és vevőcsoportok). Támogatja továbbá a felhasználás valós idejű követését, beállítását és analitikát a felosztott mennyiségekkel szemben, így a feltöltést és az újraelosztást időben el lehet végezni. Különösen fontos, hogy valós idejű rálátás legyen a felosztásra, a felhasználásra és a felosztási egyenlegre a gyors értékesítési és promóciós események során.

## <a name="terminology"></a>Fogalmak

A következő kifejezések és fogalmak jól használhatók a készletfelosztásokkal kapcsolatos vitafórumokban:

- **Felosztási** csoport – az a csoport, amely a felosztást tulajdonja, például értékesítési csatorna, vevőcsoport vagy rendeléstípus.
- **Felosztási csoport értéke** – az egyes felosztási csoportok értéke. Például a *web vagy* *üzlet* lehet az értékesítési csatorna felosztási csoportjának értéke, *míg a VIP* *vagy* a normál a vevői felosztási csoport értéke.
- **Felosztási hierarchia** – a felosztási csoportok hierarchikus kombinálása egy módszer. Meghatározhatja például az *1*. hierarchiaszint csatornáját, *a* régiót 2. szintként, *a* vevőcsoportot pedig a 3. szintként. A készletfoglalás során a felosztási csoport értékének megadásakor követnie kell a felosztási hierarchia sorrendjét. Hozzárendelhet például 200 *piros tartományt a webcsatornához*, *a londoni* *régióhoz és a VIP vevőcsoporthoz*.
- **Felosztható** – *a virtuális közös készlet*, amely a további foglalásra rendelkezésre álló mennyiséget jelzi. Ez egy számított mérték, amelyet a saját képlettel szabadon meghatározhat. Ha az egyszerű foglalás funkciót is használja, javasoljuk, hogy ugyanazt a képletet használja a "felosztható" és a "foglalható" képlet kiszámításához.
- **Felosztva** – fizikai mérték, amely megjeleníti a felosztási csoportok által igénybeveható felosztott költségeket.
- **Felhasznált** – fizikai mérték, amely azt jelzi, hogy az eredeti felosztott mennyiséghez felhasznált mennyiségek. Ahogyan ehhez a fizikai mértékhez számokat adnak hozzá, a Hozzárendelt fizikai mérték automatikusan csökken.

Az alábbi ábra a készletfoglalás üzleti munkafolyamatát mutatja be.

![Készlet láthatóságának felosztása üzleti munkafolyamata](media/inventory-visibility-allocation-flow.png "Készlet láthatóságának felosztása üzleti munkafolyamata")

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

A felosztási funkció konfigurálása két lépésből áll:

- Az adatforrás [és a](inventory-visibility-configuration.md#data-source-configuration) rá vonatkozó intézkedések [beállítása](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- A felosztási csoport nevének és hierarchiájának beállítása.

### <a name="predefined-data-source"></a>Előre definiált adatforrás

Ha engedélyezi a felosztási funkciót, és hívja a konfigurációfrissítési API-t, a készlet láthatósága egy előre definiált adatforrást és több kezdeti beállítást hoz létre.

Az adatforrás neve .`@iv`

A következő kezdeti fizikai intézkedések:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Itt vannak a kiindulási számított intézkedések:

- `@iv`

    - `@iv.@available_to_allocate` = `??`– `??``@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>További fizikai mértékek hozzáadása a felosztásra elérhető számított mértékhez

A felosztás csak akkor használható, ha be van állítva a felosztásra elérhető számított mérték (`@iv.@available_to_allocate`). Van például egy `fno` adatforrás, a `onordered` mérték, `pos``inbound` az adatforrás és a mérték, és az összeg és a mérték kiosztása az `fno.onordered``pos.inbound` rendelkezésren, az összeg és a. Ebben az esetben tartalmaznia `@iv.@available_to_allocate` kell a képletet `pos.inbound``fno.onordered` és a képletet. Példa:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound`– `@iv.@allocated`

### <a name="change-the-allocation-group-name"></a>Felosztási csoport nevének módosítása

Legfeljebb nyolc felosztásicsoport-név lehet beállítva. A csoportoknak hierarchiájuk van.

A csoportneveket a Készlet **láthatósága power app konfigurációja oldalon lehet** beállítani. A lap a környezetben Microsoft Dataverse való megnyitásához nyissa meg a Készlet láthatósága alkalmazást, és válassza a Konfiguráció **foglalása \> lehetőséget**.

Ha például négy \[`channel` csoportnevet használ, és ezeket a `customerGroup` következőre állítsa, akkor `region``orderType`\] ezek a nevek a konfigurációfrissítési API hívata esetén érvényesek lesznek a felosztással kapcsolatos kérések esetén.

### <a name="allocation-using-tips"></a>Felosztás tippek használatával

- A felosztási funkciónak *minden* termékre a termékindex-hierarchia konfigurációjában beállított termékindex-hierarchia [szerint ugyanazon dimenziószinten kell használnia](inventory-visibility-configuration.md#index-configuration). Tegyük fel például, hogy az indexhierarchia \[`Site`, `Location`, `Color`. `Size`\] Ha egy termékhez \[`Site` mennyiséget foglal le a dimenziószinten, `Location` akkor `Color`\] a következő alkalommal, amikor fel szeretné osztani ezt a terméket, ugyanazon a szinten kell felosztani, \[`Site`, `Location`. `Color`\] A szint \[`Site`, az `Location`, `Color` vagy a `Size`\]\[`Site`, használata `Location`\] esetén az adatok inkonzisztensek lesznek.
- A felosztási csoport nevének módosítása nem fogja befolyásolni a szolgáltatásban mentett adatokat.
- A felosztásnak azt követően kell történnie, hogy a termékhez a pozitív tényleges készletmennyiség van megszava.
- Ha egy magas felosztási szintű *csoport termékeit* alcsoporthoz is fel kell osztani, használja az `Reallocate` API-t. Például van \[`channel` egy felosztási csoport hierarchiája, `customerGroup`, `region`, `orderType`\]\[és néhány terméket online felosztási csoportból szeretne felosztani, a VIP-t\]\[az Online, VIP, EU\] alfelosztási csoportba, `Reallocate` az API segítségével áthelyezni a mennyiséget. Ha az API-t használja `Allocate`, a rendszer felosztja a mennyiséget a virtuális közös készletből.

### <a name="using-the-allocation-api"></a><a name="using-allocation-api"></a> A felosztási API használata

Jelenleg öt felosztási API van megnyitva:

- POST /api/environment/{environmentId}/allocation/allocate
- POST /api/environment/{environmentId}/allocation/unallocate
- POST /api/environment/{environmentId}/allocation/reallocate
- POST /api/environment/{environmentId}/allocation/consume
- POST /api/environment/{environmentId}/allocation/query

#### <a name="allocate"></a>Lefoglalás

Egy, a megadott `Allocate` dimenziókkal rendelkezik termék foglalásához hívja meg az API-t. A kérelem törzsének sémája.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
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
    "id": "???",
    "productId": "Bike",
    "targetGroups": {
        "channel": "Online",
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

#### <a name="unallocate"></a>Nincs felosztva

A művelet `Unallocate` sztornírozhatja az API-t `Allocate`. A negatív mennyiség nem engedélyezett műveletben `Allocate`. A törzs megegyezik `Unallocate` a .`Allocate`

#### <a name="reallocate"></a>Újrafokozni

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
    "targetGroups": {
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
    "id": "???",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "targetGroups": {
        "channel": "Online",
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

#### <a name="consume"></a>Felhasználás

Az API-t `Consume` használja a felhasználási mennyiség felosztással szembeni felad feladára. Ezt az API-t használhatja például a felosztott mennyiség valós intézkedésekhez való áthelyezésre. A kérelem törzsének sémája.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
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
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
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

#### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a> Felhasznált, mint soft foglalás

Az `Consume` API a felosztott mennyiséget is felhasználhatja soft foglalásként. Ebben az esetben a `Consume` művelet csökkenti a felosztott mennyiséget, majd az adott mennyiségre kis mennyiséget foglal. Ez a megközelítés csak akkor használható, ha a [Készlet](inventory-visibility-reservations.md) láthatósága funkció is használatban van.

Beállította például az "soft reservation" módosítót (mértéket `iv.softreserved`). A rendelkezésre álló foglalás kiszámított mértékének képlete a következő:

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
    "targetGroups": {
        "channel": "Online",
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

#### <a name="query"></a>Lekérdezés

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
        "channel": "Online",
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
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```
