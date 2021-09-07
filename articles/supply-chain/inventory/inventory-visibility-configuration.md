---
title: Készlet láthatóságának konfigurálása
description: Ez a témakör a Készletláthatóság konfigurálását ismerteti.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 92e42b22d424ab80303d771f760cfcf0599b9f4c
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345033"
---
# <a name="inventory-visibility-configuration"></a>Készlet láthatóságának konfigurálása

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Ez a témakör a Készletláthatóság konfigurálását ismerteti.

## <a name="introduction"></a><a name="introduction"></a>Bevezetés

Mielőtt elkezdene dolgozni a Készletláthatósággal, a következő konfigurációt kell elvégeznie a témakörben leírtak szerint:

- [Adatforrás konfiguráció](#data-source-configuration)
- [Partíciókonfiguráció](#partition-configuration)
- [Termékindex-hierarchia konfigurációja](#index-configuration)
- [Foglalási konfiguráció (opcionális)](#reservation-configuration)
- [Alapértelmezett konfigurációs minta](#default-configuration-sample)

> [!NOTE]
> A Készletláthatósági konfigurációkat a [Microsoft Power Apps](./inventory-visibility-power-platform.md#configuration)-ban tekintheti meg és szerkesztheti. A konfiguráció befejezése után válassza a **Konfiguráció frissítése** lehetőséget az alkalmazásban.

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Adatforrás konfiguráció

Az adatforrás azt a rendszert jelöli, amelyből az adatok származnak. Ilyen például a `fno` (ami a "Dynamics 365 Finance and Operations alkalmazások" rövidítése) és a `pos` (ami a "point of sale" rövidítése).

Az adatforrás konfigurációja a következő részeket tartalmazza:

- Dimenzió (dimenzió leképezés)
- Fizikai mérőszám
- Kiszámított mérőszám

> [!NOTE]
> A `fno` adatforrás a Dynamics 365 Supply Chain Management számára van fenntartva.

### <a name="dimension-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimenzió (dimenzió leképezés)

A dimenzió-konfiguráció célja a több rendszerre kiterjedő integráció szabványosítása az események és lekérdezések feladásához a dimenziók kombinációi alapján.

A készlet láthatósága a következő általános alapméreteket támogatja.

| Dimenzió típusa | Alapdimenzió |
|---|---|
| Termék | `ColorId` |
| Termék | `SizeId` |
| Termék | `StyleId` |
| Termék | `ConfigId` |
| Nyomon követés | `BatchId` |
| Nyomon követés | `SerialId` |
| Helyszín | `LocationId` |
| Helyszín | `SiteId` |
| Készlet állapota | `StatusId` |
| Raktárspecifikus | `WMSLocationId` |
| Raktárspecifikus | `WMSPalletId` |
| Raktárspecifikus | `LicensePlateId` |
| Egyebek | `VersionId` |
| Készlet (egyéni) | `InventDimension1` - `InventDimension12` |
| Mellék | `ExtendedDimension1` - `ExtendedDimension8` |

> [!NOTE]
> Az előző táblázatban felsorolt mérettípusok csak tájékoztató jellegűek. Ezeket nem kell a Készletláthatóságban definiálnia.
>
> A készlet (egyéni) dimenziókat a Supply Chain Management számára lehet fenntartani. Ebben az esetben használhatja helyette a kiterjesztett méreteket.

A külső rendszerek a RESTful API-kon keresztül érhetik el a Készletláthatóságot. Az integrációhoz az Készletláthatóság lehetővé teszi a _külső adatforrás_ és a _külső dimenziók_ és az _alapdimenziók_ közötti leképezés konfigurálását. Íme egy példa egy dimenzió-leképező táblázatra.

| Külső dimenzió | Alapdimenzió |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

A dimenzió-leképezés konfigurálásával a külső dimenziókat közvetlenül a Készletláthatósághoz küldheti. A Készletláthatóság ezután automatikusan átalakítja a külső méreteket alapméretekké.

### <a name="physical-measures"></a>Fizikai mérőszámok

A fizikai mérőszámok módosítják a mennyiséget és tükrözik a készletállapotot. Az Ön igényei alapján meghatározhatja saját fizikai mérőszámait.

A Készletláthatósága a Supply Chain Managementhez (a `fno` adatforráshoz) kapcsolódó alapértelmezett fizikai mérőszámok listáját biztosítja. A következő táblázat példát mutat a fizikai mérőszámokra.

| Fizikai mérőszám neve | Leírás |
|---|---|
| `NotSpecified` | Nincs meghatározva |
| `Arrived` | Beérkezett |
| `AvailOrdered` | Elérhető megrendelt |
| `AvailPhysical` | Elérhető tényleges |
| `Deducted` | Kiszállított |
| `OnOrder` | OnOrder |
| `Ordered` | Megrendelve |
| `PhysicalInvent` | Tényleges készlet |
| `Picked` | Kitárolva |
| `PostedQty` | Feladott mennyiség |
| `QuotationIssue` | Árajánlat kiadása |
| `QuotationReceipt` | Árajánlat-bevételezés |
| `Received` | Bevételezve |
| `Registered` | Regisztrálva |
| `ReservOrdered` | Rendelt, lefoglalt |
| `ReservPhysical` | Ténylegesen fenntartott |

### <a name="calculated-measures"></a><a name="data-source-configuration-calculated-measure"></a>Számított mérőszámok

A kiszámított mérőszámok olyan testreszabott számítási képletet biztosítanak, amely fizikai mérőszámok kombinációjából áll. Ez a funkció lehetővé teszi, hogy meghatározzon egy sor fizikai mérőszámot, amelyeket hozzáad, és/vagy egy sor fizikai mérőszámot, amelyeket kivon, hogy kialakítsa a testreszabott mérést.

Például a következő lekérdezés eredménye.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]
```

Ezután konfigurál egy számított mérőszámot, amelynek neve `MyCustomAvailableforReservation`, ahogyan az a következő táblázatban látható. Ezt a kiszámított mérőszámot a fogyasztási rendszer fogja felhasználni.

| Felhasználó rendszer | Kiszámított mérőszám | Adatforrás | Fizikai mérőszám | Számítás típusa |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `scheduled` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `reserved` | `Subtraction` |

Ha ezt a számítási képletet használja, az új lekérdezés eredménye tartalmazza a testreszabott mérést.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

A `MyCustomAvailableforReservation` kimeneti értéke az egyéni mérések számítási beállítása alapján 100 + 50 + 80 + 90 + 30 - 10 - 20 - 60 - 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Partíciókonfiguráció

A partíció konfigurációja az alapméretek kombinációjából áll. Meghatározza az adatelosztási mintát. Az azonos partícióban végzett adatműveletek nagy teljesítményt támogatnak, és nem kerülnek túl sokba. Ezért a jó partícióminták jelentős előnyökkel járhatnak.

A Készletláthatóság a következő alapértelmezett partíciókonfigurációt biztosítja.

| Alapdimenzió | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

> [!NOTE]
> Az alapértelmezett partíciókonfiguráció csak referenciaként szolgál. Ezt nem kell a Készletláthatóságban definiálnia. Jelenleg a partíciókonfiguráció frissítése nem támogatott.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Termékindex-hierarchia konfigurációja

A legtöbbször a készletállomány-lekérdezés nem csak a legmagasabb „teljes” szinten lesz. Ehelyett a készletdimenziók alapján összesített eredményeket is láthat.

A Készletláthatóság rugalmasságot biztosít azáltal, hogy lehetővé teszi az _indexek_ beállítását. Ezek az indexek egy dimenzión vagy dimenziók kombinációján alapulnak. Egy index egy *halmazszámból*, egy *dimenzióból* és egy *hierarchiából* áll, a következő táblázatban meghatározottak szerint.

| Név | Leírás |
|---|---|
| Beállított szám | Az azonos halmazhoz (indexhez) tartozó dimenziók csoportosítva lesznek, és ugyanaz a halmazszám lesz hozzájuk rendelve. |
| Dimenzió | A lekérdezés eredményének aggregált bázisdimenziója. |
| Hierarchia | A hierarchia a lekérdezhető támogatott dimenziókombinációk meghatározására szolgál. Például létrehoz egy olyan dimenziókészletet, amelynek hierarchiasorrendje a `(ColorId, SizeId, StyleId)`. Ebben az esetben a rendszer négy dimenziókombinációra vonatkozó lekérdezéseket támogat. Az első kombináció üres, a második a `(ColorId)`, a harmadik a `(ColorId, SizeId)`, a negyedik pedig a `(ColorId, SizeId, StyleId)`. A többi kombináció nem támogatott. További információért lásd a következő példát. |

### <a name="example"></a>Példa

Ez a szakasz egy példán keresztül mutatja be a hierarchia működését.

A következő tételek vannak a készletben.

| Tétel | ColorId | SizeId | StyleId | Mennyiség |
|---|---|---|---|---|
| Póló | Fekete | Kicsi | Széles | 1 |
| Póló | Fekete | Kicsi | Szabályos | 2 |
| Póló | Fekete | Nagy | Széles | 3 |
| Póló | Fekete | Nagy | Szabályos | 4 |
| Póló | Piros | Kicsi | Széles | 5 |
| Póló | Piros | Kicsi | Szabályos | 6 |
| Póló | Piros | Nagy | Szabályos | 7 |

Itt az index.

| Készletszám | Dimenzió | Hierarchia |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

Az index segítségével a következő módon kérdezheti le a készletet:

- `()` - Csoportosítva minden szerint

    - Póló, 28

- `(ColorId)` - Csoportosítva `ColorId`

    - Póló, Fekete, 10
    - Póló, piros, 18

- `(ColorId, SizeId)` - A `ColorId` és a `SizeId` kombinációja alapján csoportosítva

    - Póló, Fekete, kicsi, 3
    - Póló, Fekete, Nagy, 7
    - Póló, Piros, kicsi, 11
    - Póló, Piros, Nagy, 7

- `(ColorId, SizeId, StyleId)` - A `ColorId`, `SizeId`, és a `StyleId` kombinációja alapján csoportosítva

    - Póló, Fekete, kicsi, széles, 1
    - Póló, Fekete, kicsi, szabályos, 2
    - Póló, Fekete, Nagy, széles, 3
    - Póló, Fekete, Nagy, szabályos, 4
    - Póló, Piros, kicsi, széles, 5
    - Póló, Piros, kicsi, szabályos, 6
    - Póló, piros, nagy, szabályos, 7

> [!NOTE]
> A partíciókonfigurációban definiált alapméreteket nem szabad definiálni az indexkonfigurációkban.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Foglalási konfiguráció (opcionális)

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

A foglalási konfigurációra akkor van szükség, ha a lágy foglalási funkciót használni kívánja. A konfiguráció két alapvető részből áll:

- Lágy foglalási leképezés
- Lágy foglalási hierarchia

### <a name="soft-reservation-mapping"></a>Lágy foglalási leképezés

Foglaláskor érdemes tudni, hogy a készleten lévő készletek jelenleg rendelkezésre állnak-e foglalásra. Az érvényesítés egy számított mértékhez kapcsolódik, amely fizikai mértékek kombinációjának számítási képletét jelenti.

Például egy foglalási intézkedés a `SoftReservOrdered` fizikai mérőszámon alapul a `iv` (Készletláthatóság) adatforrásból. Ebben az esetben a `iv` adatforrás `AvailableToReserve` számított mérőszámát az alábbiakban bemutatott módon állíthatja be.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `AvailPhysical` |
| Hozzáadás | `pos` | `Inbound` |
| Kivonás | `pos` | `Outbound` |
| Kivonás | `iv` | `SoftReservOrdered` |

Ezután állítson be egy lágy foglalási leképezést, hogy a `SoftReservOrdered` foglalási mértéket leképezze a `AvailableToReserve` számított mértékre.

| Fizikai mérőszám adatforrás | Fizikai mérőszám | Foglalási adatforráshoz rendelkezésre álló | Elérhető foglalásra számított mérőszám |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

Most, amikor a `SoftReservOrdered` rendszerben foglalást végez, a Készletláthatóság automatikusan megtalálja a `AvailableToReserve`-et és a hozzá tartozó számítási képletet a foglalás érvényesítéséhez.

Például a Készletláthatóságban a következő készletekkel rendelkezik.

```json
{
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservOrdered": 90
        },
        "fno": {
            "availphysical": 70.0,
        },
        "pos": {
            "inbound": 50.0,
            "outbound": 20.0
        }
    }
}
```

Ebben az esetben a következő számítás alkalmazandó:

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservOrdered`  
= 70 + 50 – 20 – 90  
= 10

Ezért, ha a `iv.SoftReservOrdered` oldalon próbál foglalni, és a mennyiség kisebb vagy egyenlő, mint `AvailableToReserve` (10), akkor a foglalást megteheti.

### <a name="soft-reservation-hierarchy"></a>Lágy foglalási hierarchia

A foglalási hierarchia a foglalások során megadandó dimenziók sorrendjét írja le. Ugyanúgy működik, mint a termékindex-hierarchia a kézben lévő lekérdezéseknél.

A foglalási hierarchia független a termékindex-hierarchiától. Ez a függetlenség lehetővé teszi a kategóriamenedzsment megvalósítását, ahol a felhasználók részletekre bonthatják a dimenziókat, hogy pontosabb foglalásokhoz meghatározzák a követelményeket.

Íme egy példa a lágy foglalási hierarchiára.

| Alapdimenzió | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

Ebben a példában a foglalást a következő dimenziósorozatokban végezheti el:

- `()` - Nincs megadva dimenzió.
- `(SiteId)`
- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Az érvényes dimenzió-sorrendnek szigorúan követnie kell a foglalási hierarchiát, dimenzióról dimenzióra. Például a `(SiteId, LocationId, SizeId)` hierarchiasorozat nem érvényes, mert hiányzik a `ColorId`.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Alapértelmezett konfigurációs minta

Az inicializálási szakaszban a Készletláthatóság alapértelmezett konfigurációt állít be. A konfigurációt igény szerint módosíthatja.

### <a name="data-source-configuration"></a>Adatforrás konfiguráció

#### <a name="configuration-of-the-iv-data-source"></a>Az iv adatforrás konfigurálása

Ez a szakasz a `iv` adatforrás konfigurálását ismerteti.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Az iv adatforráshoz konfigurált fizikai mérőszámok

A következő fizikai mérőszámok vannak beállítva a `iv` adatforráshoz:

- `Ordered`
- `SoftReservPhysical`
- `SoftReservOrdered`
- `ReservOrdered`
- `ReservPhysical`

##### <a name="orderedtotal-calculated-measure"></a>OrderedTotal számított mérőszám

A `OrderedTotal` számított mérőszámot a `iv` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `Ordered` |
| Hozzáadás | `fno` | `Arrived` |
| Hozzáadás | `iv` | `Ordered` |

##### <a name="onhand-calculated-measure"></a>OnHand számított mérőszám

A `OnHand` számított mérőszámot a `iv` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `PhysicalInvent` |
| Hozzáadás | `iom` | `OnHand` |
| Hozzáadás | `erp` | `Unrestricted` |
| Hozzáadás | `erp` | `QualityInspection` |
| Hozzáadás | `pos` | `PosInbound` |
| Kivonás | `pos` | `PosOutbound` |

##### <a name="reservedtotal-calculated-measure"></a>ReservedTotal számított mérőszám

A `ReservedTotal` számított mérőszámot a `iv` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `ReservPhysical` |
| Hozzáadás | `fno` | `ReservOrdered` |
| Hozzáadás | `iv` | `SoftReservPhysical` |
| Hozzáadás | `iv` | `SoftReservOrdered` |
| Hozzáadás | `iv` | `ReservPhysical` |
| Hozzáadás | `iv` | `ReservOrdered` |

##### <a name="softreserved-calculated-measure"></a>SoftReserved számított mérőszám

A `SoftReserved` számított mérőszámot a `iv` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `iv` | `SoftReservPhysical` |
| Hozzáadás | `iv` | `SoftReservOrdered` |

##### <a name="hardreserved-calculated-measure"></a>HardReserved számított mérőszám

A `HardReserved` számított mérőszámot a `iv` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `ReservPhysical` |
| Hozzáadás | `fno` | `ReservOrdered` |
| Hozzáadás | `iv` | `ReservPhysical` |
| Hozzáadás | `iv` | `ReservOrdered` |

##### <a name="openorder-calculated-measure"></a>OpenOrder számított mérőszám

A `OpenOrder` számított mérőszámot a `iv` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `OnOrder` |
| Hozzáadás | `iom` | `OnOrder` |

##### <a name="onhandavailable-calculated-measure"></a>OnHandAvailable számított mérőszám

A `OnHandAvailable` számított mérőszámot a `iv` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `PhysicalInvent` |
| Hozzáadás | `iom` | `OnHand` |
| Hozzáadás | `erp` | `Unrestricted` |
| Hozzáadás | `erp` | `QualityInspection` |
| Hozzáadás | `pos` | `PosInbound` |
| Kivonás | `fno` | `ReservPhysical` |
| Kivonás | `iv` | `SoftReservPhysical` |
| Kivonás | `pos` | `PosOutbound` |

##### <a name="availabletoreserve-calculated-measure"></a>AvailableToReserve számított mérőszám

A `AvailableToReserve` számított mérőszámot a `iv` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `PhysicalInvent` |
| Hozzáadás | `iom` | `OnHand` |
| Hozzáadás | `erp` | `Unrestricted` |
| Hozzáadás | `erp` | `QualityInspection` |
| Hozzáadás | `pos` | `PosInbound` |
| Hozzáadás | `fno` | `Ordered` |
| Hozzáadás | `fno` | `Arrived` |
| Hozzáadás | `iv` | `Ordered` |
| Kivonás | `fno` | `ReservPhysical` |
| Kivonás | `fno` | `ReservOrdered` |
| Kivonás | `iv` | `SoftReservPhysical` |
| Kivonás | `iv` | `SoftReservOrdered` |
| Kivonás | `iv` | `ReservPhysical` |
| Kivonás | `iv` | `ReservOrdered` |
| Kivonás | `pos` | `PosOutbound` |

##### <a name="inventorysupply-calculated-measure"></a>InventorySupply számított mérőszám

A `InventorySupply` számított mérőszámot a `iv` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `Ordered` |
| Hozzáadás | `fno` | `Arrived` |
| Hozzáadás | `iv` | `Ordered` |
| Hozzáadás | `fno` | `PhysicalInvent` |
| Hozzáadás | `iom` | `OnHand` |
| Hozzáadás | `erp` | `Unrestricted` |
| Hozzáadás | `erp` | `QualityInspection` |
| Hozzáadás | `pos` | `PosInbound` |
| Kivonás | `pos` | `PosOutbound` |

##### <a name="inventorydemand-calculated-measure"></a>InventoryDemand kiszámított mérőszám

A `InventoryDemand` számított mérőszámot a `iv` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `OnOrder` |
| Hozzáadás | `iom` | `OnOrder` |
| Hozzáadás | `iv` | `SoftReservPhysical` |
| Hozzáadás | `iv` | `SoftReservOrdered` |
| Hozzáadás | `fno` | `ReservPhysical` |
| Hozzáadás | `fno` | `ReservOrdered` |
| Hozzáadás | `iv` | `ReservPhysical` |
| Hozzáadás | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>Az fno adatforrás konfigurálása

Ez a szakasz a `fno` adatforrás konfigurálását ismerteti.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Dimenzióleképezések az fno adatforráshoz

A következő táblázatban felsorolt dimenzió-leképezések a `fno` adatforráshoz vannak konfigurálva.

| Külső dimenzió | Alapdimenzió |
|---|---|
| `InventBatchId` | `BatchId` |
| `InventColorId` | `ColorId` |
| `InventLocationId` | `LocationId` |
| `InventSerialId` | `SerialId` |
| `InventSiteId` | `SiteId` |
| `InventSizeId` | `SizeId` |
| `InventStatusId` | `StatusId` |
| `InventStyleId` | `StyleId` |
| `LicensePlateId` | `LicensePlateId` |
| `WMSLocationId` | `WMSLocationId` |
| `WMSPalletId` | `WMSPalletId` |
| `ConfigId` | `ConfigId` |
| `InventVersionId` | `VersionId` |
| `InventDimension1` | `CustomDimension1` |
| `InventDimension2` | `CustomDimension2` |
| `InventDimension3` | `CustomDimension3` |
| `InventDimension4` | `CustomDimension4` |
| `InventDimension5` | `CustomDimension5` |
| `InventDimension6` | `CustomDimension6` |
| `InventDimension7` | `CustomDimension7` |
| `InventDimension8` | `CustomDimension8` |
| `InventDimension9` | `CustomDimension9` |
| `InventDimension10` | `CustomDimension10` |
| `InventDimension11` | `CustomDimension11` |
| `InventDimension12` | `CustomDimension12` |

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Az fno adatforráshoz konfigurált fizikai mérőszámok

A következő fizikai mérőszámok vannak beállítva a `fno` adatforráshoz:

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>A pos adatforrás konfigurálása

Ez a szakasz a `pos` adatforrás konfigurálását ismerteti.

##### <a name="physical-measures-for-the-pos-data-source"></a>Fizikai mérőszámok a pos adatforráshoz

A következő fizikai mérőszámok vannak beállítva a `pos` adatforráshoz:

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>AvailQuantity számított mérőszám

A `AvailQuantity` számított mérőszámot a `pos` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mérőszám |
|---|---|---|
| Hozzáadás | `fno` | `AvailPhysical` |
| Hozzáadás | `pos` | `PosInbound` |
| Kivonás | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>Az iom adatforrás konfigurálása

A következő fizikai mérőszámok vannak beállítva a `iom` (intelligens rendeléskezelés) adatforráshoz:

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Az erp adatforrás konfigurálása

A következő fizikai mérőszámok vannak beállítva a `erp` (vállalati erőforrás-tervezés) adatforráshoz:

- `Unrestricted`
- `QualityInspection`

### <a name="partition-configuration"></a>Partíciókonfiguráció

A következő táblázat az alapértelmezett partíciókonfigurációt mutatja.

| Alapdimenzió | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>Indexkonfiguráció

A következő táblázat az alapértelmezett indexkonfigurációt mutatja.

| Készletszám | Dimenzió | Hierarchia |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

### <a name="reservation-configuration"></a>Foglalási konfiguráció

Ez a szakasz az alapértelmezett foglalási konfigurációt ismerteti.

#### <a name="reservation-mapping"></a>Foglalási leképezés

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

A következő táblázat az alapértelmezett foglalási leképezést mutatja.

| Fizikai mérőszám adatforrás | Fizikai mérőszám | Foglalási adatforráshoz rendelkezésre álló | Elérhető foglalásra számított mérőszám |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Foglalási hierarchia

A következő táblázat az alapértelmezett foglalási hierarchiát mutatja.

| Alapdimenzió | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |
| `BatchId` | 6 |
| `SerialId` | 7 |
| `StatusId` | 8 |
| `LicensePlateId` | 9 |
| `WMSLocationId` | 10 |
| `WMSPalletId` | 11 |
| `ConfigId` | 12 |
| `VersionId` | 13 |
| `CustomDimension1` | 14 |
| `CustomDimension2` | 15 |
| `CustomDimension3` | 16 |
| `CustomDimension4` | 17 |
| `CustomDimension5` | 18 |
| `CustomDimension6` | 19 |
| `CustomDimension7` | 20 |
| `CustomDimension8` | 21 |
| `CustomDimension9` | 22 |
| `CustomDimension10` | 23 |
| `CustomDimension11` | 24 |
| `CustomDimension12` | 25 |
| `ExtendedDimension1` | 26 |
| `ExtendedDimension2` | 27 |
| `ExtendedDimension3` | 28 |
| `ExtendedDimension4` | 29 |
| `ExtendedDimension5` | 30 |
| `ExtendedDimension6` | 31 |
| `ExtendedDimension7` | 32 |
| `ExtendedDimension8` | 33 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
