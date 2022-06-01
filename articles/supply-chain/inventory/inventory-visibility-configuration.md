---
title: Készletláthatóság konfigurálása
description: Ez a témakör a Készletláthatóság konfigurálását ismerteti.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 7e42c0b49a4083edd0e64551f4840bd74d412fc1
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786838"
---
# <a name="configure-inventory-visibility"></a>Készletláthatóság konfigurálása

[!include [banner](../includes/banner.md)]


Ez a témakör a Készlet láthatósága alkalmazás használatával a Készlet láthatósága bővítmény konfigurálását ismerteti a Power Apps rendszerben.

## <a name="introduction"></a><a name="introduction"></a>Bevezetés

Mielőtt elkezdene dolgozni a Készletláthatósággal, a következő konfigurációt kell elvégeznie a témakörben leírtak szerint:

- [Adatforrás konfiguráció](#data-source-configuration)
- [Partíciókonfiguráció](#partition-configuration)
- [Termékindex-hierarchia konfigurációja](#index-configuration)
- [Foglalási konfiguráció (opcionális)](#reservation-configuration)
- [Alapértelmezett konfigurációs minta](#default-configuration-sample)

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené, telepítse és állítsa be a Készletláthatóság bővítményt a [Készletláthatóság telepítés és beállítása](inventory-visibility-setup.md) című fejezetben leírtak szerint.

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>A Készlet láthatósága alkalmazás konfigurációs lapja

A Power Apps alkalmazásban a [Készlet láthatósága alkalmazás](inventory-visibility-power-platform.md) **Konfiguráció** oldala segít a kézi konfiguráció és a lágy foglalási konfiguráció beállításában. A bővítmény telepítése után az alapértelmezett konfiguráció tartalmazza a Microsoft Dynamics 365 Supply Chain Management (a `fno` adatforrás) értékét. Az alapértelmezett beállítást felülvizsgálhatja. Ezenfelül, az Ön üzleti követelményei és a külső rendszer készletkönyvelési követelményei alapján módosíthatja a konfigurációt, hogy egységesítse a készletváltozások könyvelésének, rendszerezésének és lekérdezésének módját a több rendszerben. A témakör további részei a **Konfiguráció** lap egyes részeinek használatát ismertetik.

A konfiguráció befejezése után mindenképpen válassza ki a **Konfiguráció frissítése** lehetőséget az alkalmazásban.

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>A Készlet láthatósága funkció engedélyezése a Power Apps szolgáltatáskezelésben

A Készlet láthatósága bővítmény számos új funkcióval bővíti a Power Apps telepítését. Alapértelmezés szerint ezek a funkciók ki vannak kapcsolva. A használatukhoz nyissa meg **a** Konfiguráció lapot, **majd** a Funkciókezelés lapon kapcsolja be az alábbi funkciókat a szükséges szerint.

| Funkciókezelés neve | Leírás |
|---|---|
| *OnHandReservation* | Ezzel a funkcióval foglalásokat, foglalásokat és/vagy nem foglalt készletmennyiségeket lehet létrehozni a Készlet láthatósága funkcióval. További információért lásd a [Készletláthatósági foglalások](inventory-visibility-reservations.md) című részt. |
| *OnHandMostSpecificBackgroundService* | Ez a funkció a termékekkel és az összes dimenzióval együtt egy készletösszegzést ad meg. A készletösszegzési adatokat a rendszer rendszeres időközönként szinkronizálja a Készletláthatóságból. További információ a készlet összesítésében [található](inventory-visibility-power-platform.md#inventory-summary). |
| *OnhandChangeSchedule* | Ez az opcionális funkció lehetővé teszi az ígérethez rendelkezésre álló változási ütemezést és az ígérethez rendelkezésre álló funkciókat. A további tudnivalókat lásd [a Készlet láthatósága aktuális készlet változásának ütemezésében, amely ígérethez rendelkezésre áll](inventory-visibility-available-to-promise.md). |
| *Raktári cikkek engedélyezése a Készletláthatóság funkcióban* | Ez az opcionális funkció lehetővé teszi a készlet láthatóságát a speciális raktári folyamatokban (raktárkezelési cikkeknél) engedélyezett cikkek támogatása érdekében. A további tudnivalókat lásd [a raktárkészlet-készlet cikkekkel kapcsolatos láthatósági támogatásában](inventory-visibility-whs-support.md). |

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>A szolgáltatás végpontjának keresése

Ha nem ismeri a megfelelő Készletláthatóság szolgáltatás végpontját, nyissa meg a **Konfiguráció** oldalt a Power Apps oldalon, majd válassza a jobb felső sarokban a **Szolgáltatás végpontjának megjelenítése** lehetőséget. Az oldal a megfelelő szolgáltatás végpontját fogja megjeleníteni.

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Adatforrás konfiguráció

Minden adatforrás azt a rendszert jelöli, amelyből az adatok származnak. Ilyen lehet például az `fno` adatforrás neve (ami a "Dynamics 365 Pénzügyi és műveleti alkalmazások" nevet jelenti) `pos` és (ami azt jelenti, hogy "értékesítési pont"). Alapértelmezés szerint a Supply Chain Management alapértelmezett adatforrásként van beállítva (`fno`) a Készletláthatóságban.

> [!NOTE]
> Az `fno` adatforrás le van foglalva az Ellátásilánc-kezeléshez. Ha a készlet láthatósági bővítménye integrálva van egy ellátásilánc-kezelési környezettel, javasoljuk, `fno` hogy ne törölje az adatforráshoz kapcsolódó konfigurációkat.

Adatforrás hozzáadásához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. Az **Adatforrás** lapon válassza az **Új adatforrás** lehetőséget egy adatforrás hozzáadásához.

> [!NOTE]
> Adatforrás hozzáadásakor győződjön meg róla, hogy az adatforrás nevét, a fizikai mérőszámokat és a dimenzió-hozzárendeléseket érvényesítette, mielőtt frissítené a Készletláthatósági szolgáltatás konfigurációját. Ezeket a beállításokat nem tudja módosítani, miután kiválasztotta a **Konfiguráció frissítése** lehetőséget.

Az adatforrás konfigurációja a következő részeket tartalmazza:

- Dimenziók (dimenzió leképezés)
- Fizikai mérőszámok
- Számított mérőszámok

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimenziók (dimenzió leképezés)

A dimenzió-konfiguráció célja a több rendszerre kiterjedő integráció szabványosítása az események és lekérdezések feladásához a dimenziók kombinációi alapján. A Készletláthatósága az adatforrás dimenzióiból leképezhető alapdimenziók listáját biztosítja. Harminchárom dimenzió áll rendelkezésre a leképezéshez.

- Alapértelmezés szerint, ha a Supply Chain Managementet használja az egyik adatforrásként, 13 dimenzió kerül leképezésre a Supply Chain Management szabványos dimenzióihoz. Tizenkét másik dimenzió (`inventDimension1` - `inventDimension12`) a Supply Chain Managementt egyedi dimenzióihoz van rendelve. A fennmaradó nyolc dimenzió olyan kiterjesztett dimenziók, amelyeket külső adatforrásokhoz rendelhet.
- Ha nem a Supply Chain Managementet használja az egyik adatforrásként, akkor szabadon leképezheti a dimenziókat. A következő táblázat a rendelkezésre álló dimenziók teljes listáját tartalmazza.

> [!NOTE]
> Ha a dimenzió nem szerepel az alapértelmezett dimenziólistában, és külső adatforrást használ, javasoljuk, hogy a `ExtendedDimension1` és a `ExtendedDimension8` segítségével végezze el a leképezést.

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
| Bővítmény | `ExtendedDimension1` - `ExtendedDimension8` |
| System | `Empty` |

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

A dimenzióleképezések hozzáadásához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. Az **Adatforrás** lap **Dimenzióleképezések** szakaszában válassza a **Hozzáadás** lehetőséget a dimenzióleképezések hozzáadásához.
    ![Dimenzióleképezések hozzáadása](media/inventory-visibility-dimension-mapping.png "Dimenzió leképezések hozzáadása")

1. A **Dimenzió neve** mezőben adja meg a forrásdimenziót.
1. A **Bázisdimenzióhoz** mezőben válassza ki a Készletláthatóságában azt a dimenziót, amelyet le kíván képezni.
1. Válassza a **Mentés** lehetőséget.

Ha például az adatforrás tartalmaz egy termékszín dimenziót, akkor azt leképezheti a `ColorId` alapdimenzióra, hogy a `exterchannel` adatforrásban hozzáadhasson egy `ProductColor` egyéni dimenziót. Ezt követően a `ColorId` alapdimenzióra képezzük le.

### <a name="physical-measures"></a><a name="data-source-configuration-physical-measures"></a>Fizikai mérőszámok

Amikor egy adatforrás készletváltozást könyvel a Készletláthatóságba, a változást *fizikai mérőszámok* segítségével könyveli. A fizikai mérőszámok módosítják a mennyiséget és tükrözik a készletállapotot. Az Ön igényei alapján meghatározhatja saját fizikai mérőszámait. A lekérdezések a fizikai mérőszámokon alapulhatnak.

A Készletláthatósága a Supply Chain Managementhez (a `fno` adatforráshoz) kapcsolódó alapértelmezett fizikai mérőszámok listáját biztosítja. Ezek az alapértelmezett fizikai mérések a Supply Chain Management **Kézi lista** oldalán **(Készletgazdálkodás \> Készletlekérdezések és jelentések \> Készletlista**) található készletmozgás-állapotokból származnak. A következő táblázat példát mutat a fizikai mérőszámokra.

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

Ha az adatforrás a Supply Chain Management, nem kell újra létrehoznia az alapértelmezett fizikai mérőszámokat. Külső adatforrásokhoz azonban az alábbi lépésekkel új fizikai mérőszámokat hozhat létre.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. Az **Adatforrás** lap **Fizikai mérések** szakaszában válassza a **Hozzáadás** lehetőséget, adja meg a forrásmérőszám nevét, majd mentse a módosításokat.

### <a name="calculated-measures"></a>Számított mérőszámok

A Készletláthatóság funkcióval a fizikai készletmérések és az *egyéni számított mérések* lekérdezésére egyaránt használható. A kiszámított mérőszámok olyan testreszabott számítási képletet biztosítanak, amely fizikai mérőszámok kombinációjából áll. Ez a funkció lehetővé teszi, hogy meghatározzon egy sor fizikai mérőszámot, amelyeket hozzáad, és/vagy egy sor fizikai mérőszámot, amelyeket kivon, hogy kialakítsa a testreszabott mérést.

> [!IMPORTANT]
> A számított mérték a fizikai mértékek egy összeállítása. Képlete csak ismétlődés nélküli fizikai intézkedéseket tartalmazhat, számított intézkedéseket nem.

A konfiguráció lehetővé teszi, hogy meghatározzon egy sor módosítót, amelyeket összead vagy kivon, hogy megkapja a teljes aggregált kimeneti mennyiséget.

Egyéni számított mérőszám beállításához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Számított intézkedés** lapon válassza az **Új számítási intézkedés** lehetőséget egy számított mérőszám hozzáadásához.
1. Állítsa be a következő mezőket az új számított mértékhez:

    - **Új számított mértéknév** – adja meg a számított mérték nevét.
    - **Adatforrás** – válassza ki az új módosítóhoz társított adatforrást. A lekérdező rendszer egy adatforrás.

1. Ha **módosítót** szeretne hozzáadni az új számított mértékhez, válassza a Hozzáadás lehetőséget.
1. Állítsa be a következő mezőket az új módosítóhoz:

    - **Módosító** – a módosító típusának kiválasztása (*Kiegészítés* vagy *Kivonás*).
    - **Adatforrás** – válassza ki azt az adatforrást, ahol megtalálható a módosító értéket szolgáltató mérték.
    - **Mérték** – válassza ki annak a mértékegységnek a nevét (a kiválasztott adatforrásból), amely a módosító értékét szolgáltatja.

1. Ismételje meg az 5–6. lépést, amíg fel nem adott minden szükséges módosítót.
1. Válassza a **Mentés** lehetőséget.

Például a következő lehet a lekérdezés eredménye.

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

A `MyCustomAvailableforReservation` kimeneti értéke az egyéni mérések számítási beállítása alapján 100 + 50 – 10 + 80 – 20 + 90 + 30 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Partíciókonfiguráció

Jelenleg a partíció-konfiguráció két alapdimenzióból (és `SiteId`) áll,`LocationId` amelyek az adatok elosztását jelzik. Az ugyanazon a partíción található műveletek magasabb teljesítményt és alacsonyabb költségű műveleteket is tudnak szállítani. A következő táblázat bemutatja a készlet láthatósági bővítménye által biztosít alapértelmezett partíció-konfigurációt.

| Alapdimenzió | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

A megoldás alapértelmezés szerint tartalmazza ezt a partíciókonfigurációt. Nem kell *tehát saját magának meghatároznia*.

> [!IMPORTANT]
> Ne szabja testre az alapértelmezett partíciókonfigurációt. Ha törli vagy módosítja, akkor valószínűleg váratlan hibát fog okozhatni.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Termékindex-hierarchia konfigurációja

A legtöbbször a készletállomány-lekérdezés nem csak a legmagasabb „teljes” szinten lesz. Ehelyett érdemes lehet a készletdimenziók alapján összesített eredményeket is látni.

A Készletláthatóság rugalmasságot biztosít azáltal, hogy lehetővé teszi az _indexek_ beállítását. Ezek az indexek egy dimenzión vagy dimenziók kombinációján alapulnak. Egy index egy *halmazszámból*, egy *dimenzióból* és egy *hierarchiából* áll, a következő táblázatban meghatározottak szerint.

| Név | Leírás |
|---|---|
| Beállított szám | Az azonos halmazhoz (indexhez) tartozó dimenziók csoportosítva lesznek, és ugyanaz a halmazszám lesz hozzájuk rendelve. |
| Dimenzió | A lekérdezés eredményének aggregált bázisdimenziója. |
| Hierarchia | A hierarchia a lekérdezhető támogatott dimenziókombinációk meghatározására szolgál. Például létrehoz egy olyan dimenziókészletet, amelynek hierarchiasorrendje a `(ColorId, SizeId, StyleId)`. Ebben az esetben a rendszer négy dimenziókombinációra vonatkozó lekérdezéseket támogat. Az első kombináció üres, a második a `(ColorId)`, a harmadik a `(ColorId, SizeId)`, a negyedik pedig a `(ColorId, SizeId, StyleId)`. A többi kombináció nem támogatott. További információért lásd a következő példát. |

A termékhierarchia-index beállításához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Termékhierarchia-index** lapon a **Dimenzió-leképezések** szakaszban válassza a **Hozzáadás** lehetőséget a dimenzió-leképezések hozzáadásához.
1. Alapértelmezés szerint az indexek listáját adja meg. Egy meglévő index módosításához válassza a **Szerkesztés** vagy a **Hozzáadás** lehetőséget az adott indexre vonatkozó szakaszban. Új indexkészlet létrehozásához válassza az **Új indexkészlet** lehetőséget. Minden indexkészlet minden sora esetében a **Dimenzió** mezőben válasszon az alapdimenziók listájából. A következő mezők értékei automatikusan generálódnak:

    - **Készletszám** - Az azonos csoportba (indexbe) tartozó dimenziók csoportosítva lesznek, és ugyanaz a készletszám lesz hozzájuk rendelve.
    - **Hierarchia** - A hierarchia a dimenziócsoportban (index) lekérdezhető támogatott dimenziókombinációk meghatározására szolgál. Ha például olyan dimenziócsoportot állít be, amelynek hierarchiasorrendje a *Stílus*, a *Szín* és a *Méret*, a rendszer három lekérdezési csoport eredményét támogatja. Az első csoport csak a stílus. A második csoport a stílus és a szín kombinációja. A harmadik csoport pedig a stílus, a szín és a méret kombinációja. A többi kombináció nem támogatott.

### <a name="example"></a>Példa

Ez a szakasz egy példán keresztül mutatja be a hierarchia működését.

A következő táblázat a példához rendelkezésre álló készletek listáját tartalmazza.

| Tétel | ColorId | SizeId | StyleId | Mennyiség |
|---|---|---|---|---|
| Póló | Fekete | Kicsi | Széles | 1 |
| Póló | Fekete | Kicsi | Szabályos | 2 |
| Póló | Fekete | Nagy | Széles | 3 |
| Póló | Fekete | Nagy | Szabályos | 4 |
| Póló | Piros | Kicsi | Széles | 5 |
| Póló | Piros | Kicsi | Szabályos | 6 |
| Póló | Piros | Nagy | Szabályos | 7 |

A következő táblázat az indexhierarchia felépítését mutatja be.

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
> 
> Ha csak olyan készletet kell lekérdeznie, amelyet az összes dimenziókombináció összesít, egyetlen indexet is be lehet állítani, amely az `Empty` alapdimenziót tartalmazza.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Foglalási konfiguráció (opcionális)

A foglalási konfigurációra akkor van szükség, ha a lágy foglalási funkciót használni kívánja. A konfiguráció két alapvető részből áll:

- Lágy foglalási leképezés
- Lágy foglalási hierarchia

### <a name="soft-reservation-mapping"></a>Lágy foglalási leképezés

Foglaláskor érdemes tudni, hogy a készleten lévő készletek jelenleg rendelkezésre állnak-e foglalásra. Az érvényesítés egy számított mértékhez kapcsolódik, amely fizikai mértékek kombinációjának számítási képletét jelenti.

A fizikai mérték és a számított mérték közötti leképezés beállításával lehetővé teszi a Készletláthatóság szolgáltatás számára, hogy a fizikai mérték alapján automatikusan érvényesítse a foglalások rendelkezésre állását.

Mielőtt beállítaná ezt a hozzárendelést, a fizikai mérőszámokat, a számított mérőszámokat és azok adatforrásait a Power Apps oldalon a **Konfiguráció** lap **Adatforrás** és **Számított intézkedés** lapjain kell meghatározni (a témakör korábbi részében leírtak szerint).

A lágy foglalási leképezés definiálásához kövesse az alábbi lépéseket.

1. Határozza meg azt a fizikai mértéket, amely a lágy foglalási mértékként szolgál (például `SoftReservOrdered`).
1. A **Konfiguráció** lap **Számított intézkedés** lapján határozza meg a *Foglalásra rendelkezésre álló* (AFR) számított mérőszámot, amely tartalmazza a fizikai mérőszámhoz leképezni kívánt AFR-számítási képletet. Például beállíthatja a `AvailableToReserve` (foglalható) címet úgy, hogy az a korábban meghatározott `SoftReservOrdered` fizikai mérőszámhoz legyen hozzárendelve. Így megtudhatja, hogy a `SoftReservOrdered` készletállapotú mennyiségek közül melyek lesznek foglalhatók. A következő táblázat az AFR számítási képletét mutatja.

    | Számítás típusa | Adatforrás | Fizikai mérőszám |
    |---|---|---|
    | Hozzáadás | `fno` | `AvailPhysical` |
    | Hozzáadás | `pos` | `Inbound` |
    | Kivonás | `pos` | `Outbound` |
    | Kivonás | `iv` | `SoftReservOrdered` |

    Javasoljuk, hogy úgy állítsa be a számított mérőszámot, hogy az tartalmazza a foglalási mérőszám alapjául szolgáló fizikai mérőszámot. Ilyen módon a kiszámított mérési mennyiséget befolyásolja a foglalási mérés mennyisége. Ebben a példában tehát az `iv` adatforrás számított `AvailableToReserve` mérőszámának összetevőként tartalmaznia kell a `SoftReservOrdered` fizikai mérőszámot az `iv` adatforrásból.

1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Lágy foglalási leképezés** lapon állítsa be a fizikai mérőszám és a számított mérőszám közötti leképezést. Az előző példában a következő beállításokat használhatja a `AvailableToReserve` leképezéséhez a korábban meghatározott `SoftReservOrdered` fizikai mérőszámhoz.

    | Fizikai mérőszám adatforrás | Fizikai mérőszám | Foglalási adatforráshoz rendelkezésre álló | Elérhető foglalásra számított mérőszám |
    |---|---|---|---|
    | `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > Ha a **Lágy foglalási leképezés** lapot nem tudja szerkeszteni, előfordulhat, hogy be kell kapcsolnia az *OnHandReservation* funkciót a **Funkciókezelés** lapon.

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

> [!NOTE]
> A foglalási API hívása esetén a foglalások érvényességének ellenőrzése a logikai `ifCheckAvailForReserv` paraméter megadásával szabályozható a kérelemtörzsben. A `True` érték azt jelenti, hogy ellenőrzés szükséges, míg a `False` érték azt, hogy az ellenőrzés nem kötelező. Az alapértelmezett érték a `True`.

### <a name="soft-reservation-hierarchy"></a>Lágy foglalási hierarchia

A foglalási hierarchia a foglalások során megadandó dimenziók sorrendjét írja le. Ugyanúgy működik, mint a termékindex-hierarchia a kézben lévő lekérdezéseknél.

A foglalási hierarchia független a termékindex-hierarchiától. Ez a függetlenség lehetővé teszi a kategóriamenedzsment megvalósítását, ahol a felhasználók részletekre bonthatják a dimenziókat, hogy pontosabb foglalásokhoz meghatározzák a követelményeket. A lágy foglalás hierarchiájának tartalmaznia kell a `SiteId` és a `LocationId` elemet összetevőként, mivel ezek partíciókonfigurációt alkotnak. A foglalás során meg kell adnia egy partíciót a termékhez.

Íme egy példa a lágy foglalási hierarchiára.

| Alapdimenzió | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

Ebben a példában a foglalást a következő dimenziósorozatokban végezheti el. A foglalás során meg kell adnia egy partíciót a termékhez. Ebből következően a használható alapszintű hierarchia a `(SiteId, LocationId)`.

- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Az érvényes dimenzió-sorrendnek szigorúan követnie kell a foglalási hierarchiát, dimenzióról dimenzióra. Például a `(SiteId, LocationId, SizeId)` hierarchiasorozat nem érvényes, mert hiányzik a `ColorId`.

## <a name="available-to-promise-configuration-optional"></a>Ígérethez rendelkezésre álló konfiguráció (nem kötelező)

A készlet láthatóságának beállításával a jövőbeli aktuális készlet változásait ütemezheti, és kiszámíthatja az ígérethez rendelkezésre álló mennyiségeket. Az ígérethez rendelkezésre álló cikk mennyisége, amely a következő időszakban ígérhető a vevőnek. A számítás használata nagy mértékben megnövelheti a rendelés teljesítését. A funkció használatához engedélyeznie **kell** azt a Funkciókezelés lapon, majd be kell állítania azt **az "ATP- beállítás"** lapon. A további tudnivalókat lásd [a Készlet láthatósága aktuális készlet változásának ütemezésében, és ígérethez rendelkezésre áll](inventory-visibility-available-to-promise.md).

## <a name="complete-and-update-the-configuration"></a>A konfiguráció befejezése és frissítése

Miután befejezte a konfigurációt, minden módosítást rögzítenie kell a Készletláthatóságban. A módosítások rögzítéséhez válassza a Power Apps oldalon a **Konfiguráció** oldal jobb felső sarkában a **Konfiguráció frissítése** lehetőséget.

Amikor először választja a **Konfiguráció frissítése** lehetőséget, a rendszer bekéri a hitelesítő adatokat.

- **Ügyfélazonosító** - Az Az Azure-alkalmazás azonosítója, amelyet a Készletláthatósághoz létrehozott.
- **Bérlőazonosító** - Az Ön Azure bérlőjének azonosítója.
- **Ügyféltitok** - Az Azure-alkalmazás titka, amelyet a Készletláthatósághoz létrehozott.

A bejelentkezés után a konfiguráció frissül a Készletláthatóság szolgáltatásban.

> [!NOTE]
> A Készletláthatóság szolgáltatás konfigurációjának frissítése előtt mindenképpen ellenőrizze az adatforrás nevét, a fizikai mérőszámokat és a dimenziók hozzárendelését. Ezeket a beállításokat nem tudja módosítani, miután kiválasztotta a **Konfiguráció frissítése** lehetőséget.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Alapértelmezett konfigurációs minta

Az inicializálási szakaszban a Készletláthatóság alapértelmezett konfigurációt állít be, amelyet itt részletezünk. A konfigurációt igény szerint módosíthatja.

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
