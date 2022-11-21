---
title: Inventory Visibility konfigurálása
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni a készlet láthatóságát.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 915382c14cc9ba89b9d543cfd668a94cecbc0a55
ms.sourcegitcommit: 4f987aad3ff65fe021057ac9d7d6922fb74f980e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/14/2022
ms.locfileid: "9764866"
---
# <a name="configure-inventory-visibility"></a>Inventory Visibility konfigurálása

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell konfigurálni a készlet láthatóságát a Készlet láthatósága alkalmazásban Power Apps.

## <a name="introduction"></a><a name="introduction"></a>Bevezetés

Mielőtt elkezdené a készlet láthatóságát, be kell fejeződnie a következő konfigurálásnak, amint azt a jelen cikk ismerteti:

- [Adatforrás konfiguráció](#data-source-configuration)
- [Partíciókonfiguráció](#partition-configuration)
- [Termékindex-hierarchia konfigurációja](#index-configuration)
- [Foglalási konfiguráció (opcionális)](#reservation-configuration)
- [Alapértelmezett konfigurációs minta](#default-configuration-sample)

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené, telepítse és állítsa be a Készletláthatóság bővítményt a [Készletláthatóság telepítés és beállítása](inventory-visibility-setup.md) című fejezetben leírtak szerint.

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>A Készlet láthatósága alkalmazás konfigurációs lapja

A Power Apps alkalmazásban a [Készlet láthatósága alkalmazás](inventory-visibility-power-platform.md) **Konfiguráció** oldala segít a kézi konfiguráció és a lágy foglalási konfiguráció beállításában. A bővítmény telepítése után az alapértelmezett konfiguráció tartalmazza a Microsoft Dynamics 365 Supply Chain Management (a `fno` adatforrás) értékét. Az alapértelmezett beállítást felülvizsgálhatja. Ezenfelül, az Ön üzleti követelményei és a külső rendszer készletkönyvelési követelményei alapján módosíthatja a konfigurációt, hogy egységesítse a készletváltozások könyvelésének, rendszerezésének és lekérdezésének módját a több rendszerben. A cikk további részei **a Konfigurációs lap egyes részeinek használatát magyarázzák** el.

A konfiguráció befejezése után mindenképpen válassza ki a **Konfiguráció frissítése** lehetőséget az alkalmazásban.

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>A Készlet láthatósága funkció engedélyezése a Power Apps szolgáltatáskezelésben

A Készlet láthatósága bővítmény számos új funkcióval bővíti a Power Apps telepítését. Alapértelmezés szerint ezek a funkciók ki vannak kapcsolva. A használatukhoz nyissa meg **a** Konfiguráció lapot, **majd** a Funkciókezelés lapon kapcsolja be az alábbi funkciókat a szükséges szerint.

| Funkciókezelés neve | Leírás |
|---|---|
| *OnHandReservation* | Ezzel a funkcióval foglalásokat, foglalásokat és/vagy nem foglalt készletmennyiségeket lehet létrehozni a Készlet láthatósága funkcióval. További információért lásd a [Készletláthatósági foglalások](inventory-visibility-reservations.md) című részt. |
| *OnHandMostSpecificBackgroundService* | Ez a funkció a termékekkel és az összes dimenzióval együtt egy készletösszegzést ad meg. A készletösszegzési adatokat a rendszer rendszeres időközönként szinkronizálja a Készletláthatóságból. Az alapértelmezett szinkronizálási gyakoriság 15 percenként van beállítva, és 5 percenként akárhányszor be lehet állítani. További információ a készlet összesítésében [található](inventory-visibility-power-platform.md#inventory-summary). |
| *onHandIndexQueryPreloadBackgroundService* | Ez a funkció lehetővé teszi a Készlet láthatósága funkció előzetes lekérdezések előzetes betölthetőségét az előre kiválasztott dimenziókkal együtt az aktuális készlet listáinak összeállításához. Az alapértelmezett szinkronizálási gyakoriság 15 percenként van megjelölve. A további tudnivalókat lásd [egy egyszerű, az üzleti folyamatnak megfelelő lekérdezés előzetes betöltésében](inventory-visibility-power-platform.md#preload-streamlined-onhand-query). |
| *OnhandChangeSchedule* | Ez az opcionális funkció lehetővé teszi az ígérethez rendelkezésre álló változási ütemezést és az ígérethez rendelkezésre álló funkciókat. A további tudnivalókat lásd [a Készlet láthatósága aktuális készlet változásának ütemezésében, amely ígérethez rendelkezésre áll](inventory-visibility-available-to-promise.md). |
| *Felosztás* | Ez az opcionális funkció lehetővé teszi, hogy a készlet láthatósága lehetővé teszi a készletellenőrzést (ringinging) és a túlkiértékelést. A további tudnivalókat lásd [a Készlet láthatósága készletfelosztásban](inventory-visibility-allocation.md). |
| *Raktári cikkek engedélyezése a Készletláthatóság funkcióban* | Ez az opcionális funkció lehetővé teszi a készlet láthatóságát a raktárkezelési folyamatokban (WMS) engedélyezett cikkek támogatása érdekében. További információ a WMS-cikkek [készlet láthatósági támogatásában található](inventory-visibility-whs-support.md). |

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>A szolgáltatás végpontjának keresése

Ha nem ismeri a megfelelő készlet-láthatósági szolgáltatási végpontot, **·** Power Apps nyissa meg a Konfiguráció lapot, **majd** válassza a Szolgáltatás részleteinek megjelenítése lehetőséget a jobb felső sarokban. Az oldal a megfelelő szolgáltatás végpontját fogja megjeleníteni. A végpont a Microsoft Dynamics Lifecycle Services szolgáltatásban is elérhető, [a Végpont megkeresása az Ön Lifecycle Services környezetének megfelelően leírtak szerint](inventory-visibility-api.md#endpoint-lcs).

> [!NOTE]
> Helytelen végpont használata sikertelen készlet-láthatósági telepítést és hibákat okozhat, amikor az ellátásilánc-kezelés szinkronizálva van a készlet láthatóságával. Ha nem tudja biztosan, mi a végpont, forduljon a rendszergazdához. A végpont URL-címének formátuma a következő:
>
> `https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Adatforrás konfiguráció

Minden adatforrás azt a rendszert jelöli, amelyből az adatok származnak. Ilyen lehet például az adatforrás neve `fno` (amely az ellátásilánc-kezelésnek felel meg) `pos` és (ez azt jelenti, hogy "értékesítési pont"). Alapértelmezés szerint a Supply Chain Management alapértelmezett adatforrásként van beállítva (`fno`) a Készletláthatóságban.

> [!NOTE]
> Az `fno` adatforrás le van foglalva az Ellátásilánc-kezeléshez. Ha a készlet láthatósági bővítménye integrálva van egy ellátásilánc-kezelési környezettel, javasoljuk, `fno` hogy ne törölje az adatforráshoz kapcsolódó konfigurációkat.

Adatforrás hozzáadásához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. Az Adatforrás **lapon** válassza **az** Új adatforrás lehetőséget adatforrás hozzáadásához (`ecommerce` például vagy egy másik értelmezhető adatforrás-azonosítót).

> [!NOTE]
> Adatforrás hozzáadásakor győződjön meg róla, hogy az adatforrás nevét, a fizikai mérőszámokat és a dimenzió-hozzárendeléseket érvényesítette, mielőtt frissítené a Készletláthatósági szolgáltatás konfigurációját. Ezeket a beállításokat nem tudja módosítani, miután kiválasztotta a **Konfiguráció frissítése** lehetőséget.

Az adatforrás konfigurációja a következő részeket tartalmazza:

- Dimenziók (dimenzió leképezés)
- Fizikai mérőszámok
- Számított mérőszámok

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimenziók (dimenzió leképezés)

A dimenzió-konfiguráció célja a több rendszerre kiterjedő integráció szabványosítása az események és lekérdezések feladásához a dimenziók kombinációi alapján. A Készletláthatósága az adatforrás dimenzióiból leképezhető alapdimenziók listáját biztosítja. Harminchárom dimenzió áll rendelkezésre a leképezéshez.

- Ha az ellátásilánc-kezelés az egyik adatforrás, akkor alapértelmezés szerint 13 dimenzió van hozzárendelve az Ellátásilánc-kezelés szabványos dimenzióihoz. A többi 12 dimenzió az`inventDimension1``inventDimension12` Ellátásilánc-kezelés egyéni dimenzióihoz is megfeleltetve van. A fennmaradó nyolc dimenzió (`ExtendedDimension1` át `ExtendedDimension8`) olyan kiterjesztett dimenzió, amely leképezhető külső adatforrásra.
- Ha nem a Supply Chain Managementet használja az egyik adatforrásként, akkor szabadon leképezheti a dimenziókat. A következő táblázat a rendelkezésre álló dimenziók teljes listáját tartalmazza.

> [!NOTE]
> Ha használja az Ellátásilánc-kezelés beállítást, és módosítja az ellátásilánc-kezelés és a készlet láthatósága közötti alapértelmezett dimenzió-hozzárendeléseket, a megváltozott dimenzió nem fogja szinkronizálni az adatokat. Ezért ha a dimenzió nem szerepel az alapértelmezett dimenziólistán, és egy külső adatforrást használ, akkor javasoljuk, `ExtendedDimension1``ExtendedDimension8` hogy a leképezés során használja az adatokat.

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
> Az előző táblázatban felsorolt dimenziótípusok csak a saját referenciájukra szolgálnak. Ezeket nem kell a Készletláthatóságban definiálnia.
>
> Előfordulhat, hogy a készletdimenziók (egyéni) lefoglalhatók az ellátásilánc-kezeléshez. Ebben az esetben használja helyette a kiterjesztett dimenziókat.

A külső rendszerek a RESTful API-kon keresztül érhetik el a Készletláthatóságot. Az integrációhoz az Készletláthatóság lehetővé teszi a *külső adatforrás* és a *külső dimenziók* és az *alapdimenziók* közötti leképezés konfigurálását. Példa a dimenzió-hozzárendelési táblára.

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
1. Az Adatforrás **lapon** válassza ki azt az adatforrást, ahol a dimenziók megfeleltetését el szeretné látni. Ezután a Dimenzióleképezések **szakaszban** válassza a Hozzáadás **dimenzióleképezések** hozzáadásához lehetőséget.

    ![Dimenzióleképezések hozzáadása](media/inventory-visibility-dimension-mapping.png "Dimenzió leképezések hozzáadása")

1. A **Dimenzió neve** mezőben adja meg a forrásdimenziót.
1. A **Bázisdimenzióhoz** mezőben válassza ki a Készletláthatóságában azt a dimenziót, amelyet le kíván képezni.
1. Válassza a **Mentés** lehetőséget.

Létrehozott például egy `ecommerce` már elnevezett adatforrást, amely termékszín-dimenziót tartalmaz. Ebben az esetben a megfeleltetést úgy használhatja, hogy hozzáadja az adatforrás Dimenziónév`ProductColor`**·**`ecommerce` mezőjéhez, `ColorId`**majd kiválasztja a Cél alapdimenzió mezőt.**

### <a name="physical-measures"></a><a name="data-source-configuration-physical-measures"></a>Fizikai mérőszámok

Amikor egy adatforrás készletváltozást könyvel a Készletláthatóságba, a változást *fizikai mérőszámok* segítségével könyveli. A fizikai mérőszámok módosítják a mennyiséget és tükrözik a készletállapotot. A követelmények alapján saját fizikai intézkedéseket lehet meghatározni. A lekérdezések a fizikai mérőszámokon alapulhatnak.

A készlet láthatósága az Ellátásilánc-kezeléshez (az adatforráshoz) hozzárendelt alapértelmezett fizikai intézkedések `fno` listáját tartalmazza. Ezek az alapértelmezett fizikai mérések a Supply Chain Management **Kézi lista** oldalán **(Készletgazdálkodás \> Készletlekérdezések és jelentések \> Készletlista**) található készletmozgás-állapotokból származnak. A következő táblázat példát mutat a fizikai mérőszámokra.

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

Ha az adatforrás az Ellátásilánc-kezelés, nem kell újra létrehozni az alapértelmezett fizikai intézkedéseket. Külső adatforrásokhoz azonban az alábbi lépésekkel új fizikai mérőszámokat hozhat létre.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. Az Adatforrás **lapon** válassza ki azt az adatforrást, amelybe fizikai intézkedéseket szeretne felvenni (például az adatforrást `ecommerce`). Ezután a Fizikai mértékek **szakaszban** válassza a Hozzáadás lehetőséget, **majd** adja meg a mérték nevét (`Returned` például ha rögzíteni szeretné a visszaküldött mennyiségeket ebben az adatforrásban a készlet láthatósága részére). Mentse el a módosításokat.

### <a name="calculated-measures"></a>Számított mérőszámok

A Készletláthatóság funkcióval a fizikai készletmérések és az *egyéni számított mérések* lekérdezésére egyaránt használható. A kiszámított mérőszámok olyan testreszabott számítási képletet biztosítanak, amely fizikai mérőszámok kombinációjából áll. Ez a funkció lehetővé teszi, hogy meghatározzon egy sor fizikai mérőszámot, amelyeket hozzáad, és/vagy egy sor fizikai mérőszámot, amelyeket kivon, hogy kialakítsa a testreszabott mérést.

> [!IMPORTANT]
> A számított mérték a fizikai mértékek egy összeállítása. Képlete csak ismétlődés nélküli fizikai intézkedéseket tartalmazhat, számított intézkedéseket nem.

A konfiguráció segítségével kiszámított mértékképleteket határozhat meg, amelyek a kiegészítés vagy kivonás módosítóit tartalmazzák a teljes összesített kimenő mennyiség bejezése érdekében.

Egyéni számított mérőszám beállításához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Számított intézkedés** lapon válassza az **Új számítási intézkedés** lehetőséget egy számított mérőszám hozzáadásához.
1. Állítsa be a következő mezőket az új számított mértékhez:

    - **Új számított mértéknév** – adja meg a számított mérték nevét.
    - **Adatforrás** – válassza ki azt az adatforrást, amelybe bele kell foglalni az új számított mértéket. A lekérdező rendszer egy adatforrás.

1. Ha **módosítót** szeretne hozzáadni az új számított mértékhez, válassza a Hozzáadás lehetőséget.
1. Állítsa be a következő mezőket az új módosítóhoz:

    - **Módosító** – a módosító típusának kiválasztása (*Kiegészítés* vagy *Kivonás*).
    - **Adatforrás** – válassza ki azt az adatforrást, ahol megtalálható a módosító értéket szolgáltató mérték.
    - **Mérték** – válassza ki annak a mértékegységnek a nevét (a kiválasztott adatforrásból), amely a módosító értékét szolgáltatja.

1. Ismételje meg az 5–6. lépést, amíg nem adott hozzá minden szükséges módosítót, és nem fejeződött be a számított mérték képlete.
1. Válassza a **Mentés** lehetőséget.

Egy divattervező vállalat például három adatforráson keresztül működik:

- `pos`– az üzlet csatornának felel meg.
- `fno`– megfelel az ellátásilánc-kezelésnek.
- `ecommerce`– a webes csatornának felel meg.

Számított mértékek nélkül, ha a D0002 (Kabinet) termékre vonatkozó lekérdezést az 1. helyen, a 11. raktárban és a `ColorID``Red` dimenzióértékben, akkor a következő lekérdezési eredményt jeleníti meg, amely megjeleníti a készletmennyiségeket az egyes előre konfigurált fizikai mértékek alatt. Nem lesz azonban látható a teljes elérhető foglalási mennyiség az adatforrások között.

```json
[
    {
        "productId": "D0002",
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
            "ecommerce": {
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
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `received` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `scheduled` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `issued` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `reserved` | `Subtraction` |

Ha ezt a számítási képletet használja, az új lekérdezés eredménye tartalmazza a testreszabott mérést.

```json
[
    {
        "productId": "D0002",
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
            "ecommerce": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CrossChannel": {
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

A készlet láthatósága rugalmasságot biztosít, mert lehetővé teszi *indexek* beállítását a lekérdezések teljesítményének javítása érdekében. Ezek az indexek egy dimenzión vagy dimenziók kombinációján alapulnak. Egy index egy *halmazszámból*, egy *dimenzióból* és egy *hierarchiából* áll, a következő táblázatban meghatározottak szerint.

| Név | Leírás |
|---|---|
| Beállított szám | Az azonos halmazhoz (indexhez) tartozó dimenziók csoportosítva lesznek, és ugyanaz a halmazszám lesz hozzájuk rendelve. |
| Dimenzió | A lekérdezés eredményének aggregált bázisdimenziója. |
| Hierarchia | A hierarchia lehetővé teszi meghatározott dimenziókombinációk teljesítményének növelését a szűrési és csoportosítási lekérdezési paraméterekben való használata esetén. Ha például egy olyan dimenziókészletet hoz létre, amely hierarchiasorozatot használ, akkor a rendszer gyorsabban feldolgozhatja a `(ColorId, SizeId, StyleId)` négy dimenziókombinációhoz kapcsolódó lekérdezéseket. Az első kombináció üres, a második a `(ColorId)`, a harmadik a `(ColorId, SizeId)`, a negyedik pedig a `(ColorId, SizeId, StyleId)`. Más kombinációk nem lesznek felfelé felgyorsítva. A szűrőket nem korlátozza a rendelés, de ha javítani szeretné a teljesítményüket, akkor ezeken a dimenziókon belül kell lenniük. További információért lásd a következő példát. |

A termékhierarchia-index beállításához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Termékhierarchia-index** lapon a **Dimenzió-leképezések** szakaszban válassza a **Hozzáadás** lehetőséget a dimenzió-leképezések hozzáadásához.
1. Alapértelmezés szerint az indexek listáját adja meg. Egy meglévő index módosításához válassza a **Szerkesztés** vagy a **Hozzáadás** lehetőséget az adott indexre vonatkozó szakaszban. Új indexkészlet létrehozásához válassza az **Új indexkészlet** lehetőséget. Minden indexkészlet minden sora esetében a **Dimenzió** mezőben válasszon az alapdimenziók listájából. A következő mezők értékei automatikusan generálódnak:

    - **Készletszám** - Az azonos csoportba (indexbe) tartozó dimenziók csoportosítva lesznek, és ugyanaz a készletszám lesz hozzájuk rendelve.
    - **Hierarchia** – a hierarchia a szűrési és csoportosítási lekérdezési paramétereknél növeli a dimenzió meghatározott kombinációinak teljesítményét.

> [!TIP]
> Az indexhierarchia beállításakor tartsa szem előtt a következő tanácsokat:
>
> - A partíciókonfigurációban definiált alapdimenziókat nem lehet definiálni az indexkonfigurációkban. Ha az indexkonfigurációban ismét meg van adva alapdimenzió, akkor ezzel az indexszel nem lehet lekérdezést tenni.
> - Ha csak olyan készletet kell lekérdezni, amely az összes dimenziókombinációval összesítve van, akkor egyetlen indexet kell beállítania, amely az alapdimenziót tartalmazza `Empty`.

### <a name="example"></a>Példa

Ez a szakasz egy példán keresztül mutatja be a hierarchia működését.

A következő táblázat a példához rendelkezésre álló készletek listáját tartalmazza.

| Cikk | ColorId | SizeId | StyleId | Mennyiség |
|---|---|---|---|---|
| D0002 | Fekete | Kicsi | Széles | 1 |
| D0002 | Fekete | Kicsi | Szabályos | 2 |
| D0002 | Fekete | Nagy | Széles | 3 |
| D0002 | Fekete | Nagy | Szabályos | 4 |
| D0002 | Piros | Kicsi | Széles | 5 |
| D0002 | Piros | Kicsi | Szabályos | 6 |
| D0002 | Piros | Nagy | Szabályos | 7 |

A következő táblázat az indexhierarchia felépítését mutatja be.

| Készletszám | Dimenzió | Hierarchia |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

Az index segítségével a következő módon kérdezheti le a készletet:

- `()` - Csoportosítva minden szerint

    - D0002, 28

- `(ColorId)` - Csoportosítva `ColorId`

    - D0002, Fekete, 10
    - D0002, Piros, 18

- `(ColorId, SizeId)` - A `ColorId` és a `SizeId` kombinációja alapján csoportosítva

    - D0002, Fekete, Kis, 3
    - D0002, Fekete, Nagy, 7
    - D0002, Piros, Kicsi, 11
    - D0002, piros, nagy, 7

- `(ColorId, SizeId, StyleId)` - A `ColorId`, `SizeId`, és a `StyleId` kombinációja alapján csoportosítva

    - D0002, Fekete, Kis, Széles, 1
    - D0002, Fekete, Kis, Normál, 2
    - D0002, Fekete, Nagy, Széles, 3
    - D0002, Fekete, Nagy, Normál, 4
    - D0002, piros, kicsi, széles, 5
    - D0002, Piros, Kis, Normál, 6
    - D0002, piros, nagy, normál, 7

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Foglalási konfiguráció (opcionális)

A foglalási konfigurációra akkor van szükség, ha a lágy foglalási funkciót használni kívánja. A konfiguráció két alapvető részből áll:

- Lágy foglalási leképezés
- Lágy foglalási hierarchia

### <a name="soft-reservation-mapping"></a>Lágy foglalási leképezés

Foglaláskor érdemes tudni, hogy a készleten lévő készletek jelenleg rendelkezésre állnak-e foglalásra. Az érvényesítés egy számított mértékhez kapcsolódik, amely fizikai mértékek kombinációjának számítási képletét jelenti.

A fizikai mérték és a számított mérték közötti leképezés beállításával lehetővé teszi a Készletláthatóság szolgáltatás számára, hogy a fizikai mérték alapján automatikusan érvényesítse a foglalások rendelkezésre állását.

A megfeleltetés beállítása előtt meg kell határozni a fizikai mérőszámokat, **·** **·** **·** Power Apps a számított mértékeket és azok adatforrását a Konfigurációs lap Számított mérték lapján (a jelen cikknek a korábban ismertetett módon).

A lágy foglalási leképezés definiálásához kövesse az alábbi lépéseket.

1. Határozza meg azt a fizikai mértéket, amely a lágy foglalási mértékként szolgál (például `SoftReservPhysical`).
1. A **Konfiguráció** lap **Számított intézkedés** lapján határozza meg a *Foglalásra rendelkezésre álló* (AFR) számított mérőszámot, amely tartalmazza a fizikai mérőszámhoz leképezni kívánt AFR-számítási képletet. Például beállíthatja a `AvailableToReserve` (foglalható) címet úgy, hogy az a korábban meghatározott `SoftReservPhysical` fizikai mérőszámhoz legyen hozzárendelve. Így megtudhatja, hogy a `SoftReservPhysical` készletállapotú mennyiségek közül melyek lesznek foglalhatók. A következő táblázat az AFR számítási képletét mutatja.

    | Számítás típusa | Adatforrás | Fizikai mérőszám |
    |---|---|---|
    | Hozzáadás | `fno` | `AvailPhysical` |
    | Hozzáadás | `pos` | `Inbound` |
    | Kivonás | `pos` | `Outbound` |
    | Kivonás | `iv` | `SoftReservPhysical` |

    Javasoljuk, hogy úgy állítsa be a számított mérőszámot, hogy az tartalmazza a foglalási mérőszám alapjául szolgáló fizikai mérőszámot. Ilyen módon a kiszámított mérési mennyiséget befolyásolja a foglalási mérés mennyisége. Ebben a példában tehát az `iv` adatforrás számított `AvailableToReserve` mérőszámának összetevőként tartalmaznia kell a `SoftReservPhysical` fizikai mérőszámot az `iv` adatforrásból.

1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Lágy foglalási leképezés** lapon állítsa be a fizikai mérőszám és a számított mérőszám közötti leképezést. Az előző példában a következő beállításokat használhatja a `AvailableToReserve` leképezéséhez a korábban meghatározott `SoftReservPhysical` fizikai mérőszámhoz.

    | Fizikai mérőszám adatforrás | Fizikai mérőszám | Foglalási adatforráshoz rendelkezésre álló | Elérhető foglalásra számított mérőszám |
    |---|---|---|---|
    | `iv` | `SoftReservPhysical` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > Ha a **Lágy foglalási leképezés** lapot nem tudja szerkeszteni, előfordulhat, hogy be kell kapcsolnia az *OnHandReservation* funkciót a **Funkciókezelés** lapon.

Most, amikor a `SoftReservPhysical` rendszerben foglalást végez, a Készletláthatóság automatikusan megtalálja a `AvailableToReserve`-et és a hozzá tartozó számítási képletet a foglalás érvényesítéséhez.

Például a Készletláthatóságban a következő készletekkel rendelkezik.

```json
{
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservPhysical": 90
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

`AvailableToReserve` = `fno.availphysical` + `pos.inbound`– `pos.outbound``iv.SoftReservPhysical`  
= 70 + 50 – 20 – 90  
= 10

Ezért ha foglalásokat próbál meg felhozni `iv.SoftReservPhysical`, `AvailableToReserve` és a mennyiség kisebb vagy egyenlő, mint (10), az soft reservation kérés sikeres lesz.

> [!NOTE]
> A foglalási API hívása esetén a foglalások érvényességének ellenőrzése a logikai `ifCheckAvailForReserv` paraméter megadásával szabályozható a kérelemtörzsben. `True` Az érték azt jelenti, hogy érvényesítés szükséges, `False` ugyanakkor az ellenőrzés nem szükséges (bár lehet, hogy negatív mennyiséggel végződik), a rendszer így is lehetővé teszi a `AvailableToReserve` foglalást. Az alapértelmezett érték a `True`.

### <a name="soft-reservation-hierarchy"></a>Lágy foglalási hierarchia

A foglalási hierarchia a foglalások során megadandó dimenziók sorrendjét írja le. Ugyanúgy működik, mint a termékindex-hierarchia a kézben lévő lekérdezéseknél.

A foglalási hierarchia független a termékindex-hierarchiától. Ez a függetlenség lehetővé teszi a kategóriamenedzsment megvalósítását, ahol a felhasználók részletekre bonthatják a dimenziókat, hogy pontosabb foglalásokhoz meghatározzák a követelményeket. A lágy foglalás hierarchiájának tartalmaznia kell a `SiteId` és a `LocationId` elemet összetevőként, mivel ezek partíciókonfigurációt alkotnak. A foglalás során meg kell adnia egy partíciót a termékhez.

Az alábbi példa az ilyen típusú foglalási hierarchiákra mutat be.

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

Miután befejezte a konfigurációt, minden módosítást rögzítenie kell a Készletláthatóságban. Hajtsa végre a következő lépéseket a változtatások véglegesítéshez.

1. A Power Apps Konfiguráció lap Jobb felső **sarkában** válassza **a** Konfiguráció frissítése lehetőséget. 
1. A rendszer bejelentkezési hitelesítő adatokat kér. Adja meg a következő értékeket:

    - **Ügyfélazonosító** - Az Az Azure-alkalmazás azonosítója, amelyet a Készletláthatósághoz létrehozott.
    - **Bérlőazonosító** - Az Ön Azure bérlőjének azonosítója.
    - **Ügyféltitok** - Az Azure-alkalmazás titka, amelyet a Készletláthatósághoz létrehozott.

    Ezekről a hitelesítő adatokról és azok megkeres erről a [telepítésről és a készlet láthatóságának beállításával kapcsolatban tartalmaz további tájékoztatást](inventory-visibility-setup.md).

    > [!IMPORTANT]
    > A konfiguráció frissítése előtt ellenőrizze az adatforrás nevét, fizikai méreteit és dimenzióleképezését. A frissítés után ezek a beállítások nem módosíthatók.

1. Bejelentkezés után válassza újra a Konfiguráció **frissítése** lehetőséget. A rendszer alkalmazza a beállításokat, és mutatja, mi módosult.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Alapértelmezett konfigurációs minta

Az inicializálási szakaszban a Készletláthatóság alapértelmezett konfigurációt állít be, amelyet itt részletezünk. A konfigurációt igény szerint módosíthatja.

### <a name="data-source-configuration"></a>Adatforrás konfiguráció

#### <a name="configuration-of-the-iv-data-source"></a>Az iv adatforrás konfigurálása

Ez a szakasz a `iv` adatforrás konfigurálását ismerteti.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>A "iv" adatforráshoz konfigurált fizikai intézkedések

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

#### <a name="configuration-of-the-fno-data-source"></a>A "szno" adatforrás konfigurálása

Ez a szakasz a `fno` adatforrás konfigurálását ismerteti.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Dimenzióleképezések a "szno" adatforráshoz

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

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>A "szno" adatforráshoz konfigurált fizikai intézkedések

A következő fizikai mérőszámok vannak beállítva a `fno` adatforráshoz:

- `Arrived`
- `PhysicalInvent`
- `ReservPhysical`
- `onorder`
- `notspecified`
- `availordered`
- `availphysical`
- `picked`
- `postedqty`
- `quotationreceipt`
- `received`
- `ordered`
- `ReservOrdered`

#### <a name="configuration-of-the-pos-data-source"></a>A "POS" adatforrás konfigurálása

Ez a szakasz a `pos` adatforrás konfigurálását ismerteti.

##### <a name="physical-measures-for-the-pos-data-source"></a>Fizikai intézkedések a "POS" adatforráshoz

A következő fizikai mérőszámok vannak beállítva a `pos` adatforráshoz:

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>AvailQuantity számított mérőszám

A `AvailQuantity` számított mérőszámot a `pos` adatforráshoz a következő táblázatban bemutatott módon kell konfigurálni.

| Számítás típusa | Adatforrás | Fizikai mutató |
|---|---|---|
| Hozzáadás | `fno` | `AvailPhysical` |
| Hozzáadás | `pos` | `PosInbound` |
| Kivonás | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>Az "iom" adatforrás konfigurálása

A következő fizikai mérőszámok vannak beállítva a `iom` (intelligens rendeléskezelés) adatforráshoz:

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Az "erp" adatforrás konfigurálása

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
| `iv` | `SoftReservPhysical` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Foglalási hierarchia

A következő táblázat az alapértelmezett foglalási hierarchiát mutatja.

| Alapdimenzió | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
