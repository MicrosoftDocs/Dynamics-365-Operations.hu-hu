---
title: Készletláthatóság alkalmazás
description: Ez a témakör a Készletláthatóság alkalmazás használatát ismerteti.
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
ms.openlocfilehash: cc09dd82547ec42041889e9a96662cd17549a3ea
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345002"
---
# <a name="inventory-visibility-app"></a>Készletláthatóság alkalmazás

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Ez a témakör a Készletláthatóság alkalmazás használatát ismerteti.

A Készletláthatóság modellvezérelt alkalmazást biztosít a vizualizációhoz. Az alkalmazás három oldalt tartalmaz: **Konfiguráció**, **Üzemeltetési láthatóság** és **Készlet-összefoglaló**. A következő jellemzőkkel rendelkezik:

- Felhasználói felületet (UI) biztosít a kézi konfigurációhoz és a lágy foglalások konfigurálásához.
- Támogatja a különböző dimenziókombinációk valós idejű készletlekérdezéseit.
- Felhasználói felületet biztosít a foglalási kérelmek feladásához.
- Egyénre szabott nézetet nyújt a termékek készletéről, az összes dimenzióval együtt

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené, telepítse és állítsa be a Készletláthatóság bővítményt a [Készletláthatóság beállítása](inventory-visibility-setup.md)című fejezetben leírtak szerint.

## <a name="configuration"></a><a name="configuration"></a>Konfiguráció

A **Konfiguráció** oldal segít a kézben lévő konfiguráció és a lágy foglalási konfiguráció beállításában. A bővítmény telepítése után az alapértelmezett konfiguráció tartalmazza a Microsoft Dynamics 365 Supply Chain Management (a `fno` adatforrás) értékét. Az alapértelmezett beállítást felülvizsgálhatja. Ezen felül, az Ön üzleti követelményei és a külső rendszer készletkönyvelési követelményei alapján módosíthatja a konfigurációt a [Dataverse](/powerapps/maker/common-data-service/data-platform-intro)-ban, hogy egységesítse a készletváltozások könyvelésének, rendszerezésének és lekérdezésének módját a több rendszerben.

### <a name="define-data-sources"></a>Adatforrások meghatározása

Meghatározza az egyes *adatforrásokat*, amelyeket integrálni kíván a Készletláthatósággal. A Készletláthatóság támogatja a különböző adatforrásokkal való integrációt, például az Ön POS-rendszerével, a Supply Chain Managementtel és más külső rendszerekkel. Alapértelmezés szerint a Supply Chain Management alapértelmezett adatforrásként van beállítva (`fno`) a Készletláthatóságban.

Adatforrás hozzáadásához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. Az **Adatforrás** lapon válassza az **Új adatforrás** lehetőséget egy adatforrás hozzáadásához.

> [!NOTE]
> Adatforrás hozzáadásakor győződjön meg róla, hogy az adatforrás nevét, a fizikai mérőszámokat és a dimenzió-hozzárendeléseket érvényesítette, mielőtt frissítené a Készletláthatósági szolgáltatás konfigurációját. Ezeket a beállításokat nem tudja módosítani, miután kiválasztotta a **Konfiguráció frissítése** lehetőséget.

### <a name="set-up-dimension-mappings"></a>A dimenziók hozzárendelésének beállítása

A Készletláthatósága az adatforrás dimenzióiból leképezhető alapdimenziók listáját biztosítja. Harminchárom dimenzió áll rendelkezésre a leképezéshez.

- Alapértelmezés szerint, ha a Supply Chain Managementet használja az egyik adatforrásként, 13 dimenzió kerül leképezésre a Supply Chain Management szabványos dimenzióihoz. Tizenkét másik dimenzió (`inventDimension1` - `inventDimension12`) a Supply Chain Managementt egyedi dimenzióihoz van rendelve. A fennmaradó nyolc dimenzió olyan kiterjesztett dimenziók, amelyeket külső adatforrásokhoz rendelhet.
- Ha nem a Supply Chain Managementet használja az egyik adatforrásként, akkor szabadon leképezheti a dimenziókat. A következő táblázat a rendelkezésre álló dimenziók teljes listáját tartalmazza.

> [!NOTE]
> Ha a dimenzió nem szerepel az alapértelmezett dimenziólistában, és külső adatforrást használ, javasoljuk, hogy a `ExtendedDimension1` és a `ExtendedDimension8` segítségével végezze el a leképezést.

| Dimenzió típusa | Dimenzió neve |
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
| Egyéb | `VersionId` |
| Készlet (egyéni) | `InventDimension1` - `InventDimension12` |
| Egyéb | `ExtendedDimension1` - `ExtendedDimension8` |

A dimenzióleképezések hozzáadásához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. Az **Adatforrás** lap **Dimenzióleképezések** szakaszában válassza a **Hozzáadás** lehetőséget a dimenzióleképezések hozzáadásához.
1. A **Dimenzió neve** mezőben adja meg a forrásdimenziót.
1. A **Bázisdimenzióhoz** mezőben válassza ki a Készletláthatóságában azt a dimenziót, amelyet le kíván képezni.
1. Válassza a **Mentés** lehetőséget.

![Dimenzióleképezések hozzáadása](media/inventory-visibility-dimension-mapping.png "Dimenzió leképezések hozzáadása")

Ha például az adatforrás tartalmaz egy termékszín dimenziót, akkor azt leképezheti a `ColorId` alapdimenzióra, hogy a `exterchannel` adatforrásban hozzáadhasson egy `ProductColor` egyéni dimenziót. Ezt követően a `ColorId` alapdimenzióra képezzük le.

## <a name="create-a-physical-measure"></a>Fizikai mérőszám létrehozása

Amikor egy adatforrás készletváltozást könyvel a Készletláthatóságba, a változást *fizikai mérőszámok* segítségével könyveli. A fizikai mérőszámok olyan módosítók, amelyek az összesített készleti tranzakciós állapotokat tükrözik. A lekérdezések a fizikai mérőszámokon alapulhatnak.

A Készletláthatóság rendelkezik az alapértelmezett fizikai mérőszámok listájával. Ezek az alapértelmezett fizikai mérések a Supply Chain Management **Kézi lista** oldalán **(Készletgazdálkodás \> Készletlekérdezések és jelentések \> Készletlista**) található készletmozgás-állapotokból származnak.

| Módosító | Név |
|---|---|
| `PhysicalInvent` | Tényleges készlet |
| `ReservPhysical` | Fizikai fenntartva |
| `AvailPhysical` | Elérhető tényleges |
| `ReservOrdered` | Megrendelt fenntartva |
| `PostedQty` | Feladott mennyiség |
| `Deducted` | Kiszállított |
| `Picked` | Kitárolva |
| `Received` | Bevételezve |
| `Registered` | Regisztrálva |
| `Arrived` | Beérkezett |
| `Ordered` | Megrendelve |
| `OnOrder` | Rendelésre |
| `QuotationReceipt` | Árajánlat átvétele |
| `QuotationIssue` | Árajánlat-probléma |

Ha az adatforrás a Supply Chain Management, nem kell újra létrehoznia az alapértelmezett fizikai mérőszámokat. Külső adatforrásokhoz azonban az alábbi lépésekkel új fizikai mérőszámokat hozhat létre.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. Az **Adatforrás** lap **Fizikai mérések** szakaszában válassza a **Hozzáadás** lehetőséget, adja meg a forrásmérőszám nevét, majd mentse a módosításokat.

## <a name="define-the-product-hierarchy-index"></a>A termékhierarchia indexének meghatározása

Az összesített dimenziócsoportok beállításával a Készletláthatóság segítségével lekérdezheti a készleten lévő készlet állapotát. A Készletláthatóságban az egyes dimenziócsoportok *indexként* ismertek. Minden index egy meghatározott számnak felel meg. A Készletláthatóság lekérdezésének módja alapján eldöntheti, hogy mely dimenziókat használja az indexelés beállításához.

A termékhierarchia-index beállításához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Termékhierarchia-index** lapon a **Dimenzió-leképezések** szakaszban válassza a **Hozzáadás** lehetőséget a dimenzió-leképezések hozzáadásához.
1. Alapértelmezés szerint az indexek listáját adja meg. Egy meglévő index módosításához válassza a **Szerkesztés** vagy a **Hozzáadás** lehetőséget az adott indexre vonatkozó szakaszban. Új indexkészlet létrehozásához válassza az **Új indexkészlet** lehetőséget. Minden indexkészlet minden sora esetében a **Dimenzió** mezőben válasszon az alapdimenziók listájából. A következő mezők értékei automatikusan generálódnak:

    - **Készletszám** - Az azonos csoportba (indexbe) tartozó dimenziók csoportosítva lesznek, és ugyanaz a készletszám lesz hozzájuk rendelve.
    - **Hierarchia** - A hierarchia a dimenziócsoportban (index) lekérdezhető támogatott dimenziókombinációk meghatározására szolgál. Ha például olyan dimenziócsoportot állít be, amelynek hierarchiasorrendje a *Stílus*, a *Szín* és a *Méret*, a rendszer három lekérdezési csoport eredményét támogatja. Az első csoport csak a stílus. A második csoport a stílus és a szín kombinációja. A harmadik csoport pedig a stílus, a szín és a méret kombinációja. A többi kombináció nem támogatott.

További információért lásd: [Termékindex-hierarchia konfigurálása](inventory-visibility-configuration.md#index-configuration).

### <a name="example"></a>Példa

Ez a szakasz egy példán keresztül mutatja be a hierarchia működését. A következő táblázat a példához rendelkezésre álló készletek listáját tartalmazza.

| Tétel | Stílus | Szín | Méret | Mennyiség |
|---|---|---|---|---|
| I0001 | Széles | Fekete | Kicsi | 1 |
| I0001 | Széles | Fekete | Nagy | 2 |
| I0001 | Széles | Piros | Kicsi | 3 |
| I0001 | Szabályos | Fekete | Kicsi | 4 |
| I0001 | Szabályos | Fekete | Nagy | 5 |
| I0001 | Szabályos | Piros | Kicsi | 6 |
| I0001 | Szabályos | Piros | Nagy | 7 |

A következő táblázat az indexhierarchia felépítését mutatja be.

| Kulcs | Beállított szám | Hierarchia |
|---|---|---|
| `StyleId` | 1 | 1 |
| `ColorId` | 1 | 2 |
| `SizeId` | 1 | 3 |

Az előző beállítások alapján a Készletláthatóság lekérdezés dimenziókombinációja a *Stílus*, *Szín* és *Méret*. A hierarchia beállítása lehetővé teszi, hogy a külső rendszerek a következő módon kérdezzék le a készletet:

- `()` - Csoportosítva minden szerint Íme a kimenet:

    - I0001, 28

- `(StyleId)` - Csoportosítás stílus szerint. Íme a kimenet:

    - I0001, széles, 6
    - I0001, normál, 22

- `(StyleId, ColorId)` - A stílus és a szín kombinációja szerint csoportosítva. Íme a kimenet:

    - I0001, széles, fekete,3
    - I0001, széles, piros, 3
    - I0001, normál, fekete, 9
    - I0001, normál, piros, 13

- `(StyleId, ColorId, SizeId)` - A stílus, a szín és a méret kombinációja szerint csoportosítva. Íme a kimenet:

    - I0001, széles, fekete, kicsi,1
    - I0001, Széles, Fekete, Nagy, 2
    - I0001, széles, piros, kicsi, 3
    - I0001, normál, fekete, kicsi, 4
    - I0001, normál, Fekete, Nagy, 5
    - I0001, normál, piros, kicsi, 6
    - I0001, normál, piros, nagy, 7

## <a name="set-up-a-custom-calculated-measure"></a>Egyéni számított mérőszám beállítása

A Készletláthatóság funkcióval a fizikai készletmérések és az *egyéni számított mérések* lekérdezésére egyaránt használható.

A konfiguráció lehetővé teszi, hogy meghatározzon egy sor módosítót, amelyeket összead vagy kivon, hogy megkapja a teljes aggregált kimeneti mennyiséget.

1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Számított intézkedés** lapon válassza az **Új számítási intézkedés** lehetőséget egy számított mérőszám hozzáadásához. Ezután állítsa be a mezőket a következő táblázatban leírtak szerint.

    | Mező | Érték |
    |---|---|
    | Új számított mérőszám neve | Adja meg a számított mérőszám nevét. |
    | Adatforrás | A lekérdező rendszer egy adatforrás. |
    | Módosító adatforrás | Adja meg a módosító adatforrását. |
    | Módosító | Adja meg a módosító nevét. |
    | Módosító típusa | Válassza ki a módosító típusát *(összeadás* vagy *kivonás*). |

A következő táblázat egy példát mutat a `MyCustomAvailableforReservation` egyéni számított mérésre. A példával kapcsolatos további információkért lásd az [Adatforrás konfigurálása](inventory-visibility-configuration.md#data-source-configuration) című részt.

| Kiszámított mérőszám adatforrás | Kiszámított mérőszám | Módosító adatforrás | Módosító | Módosító típusa |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `Exteexterchannelrchannel` | `reserved` | `Subtraction` |

### <a name="set-up-a-soft-reservation-mapping"></a><a name="setup-reservation-mapping"></a>Lágy foglalási leképezés beállítása

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Mielőtt a **Lágy foglalási leképezés** lapot szerkesztheti, be kell kapcsolnia az *OnHandReservation* funkciót a **Funkciókezelés** lapon.

A fizikai mérték és a számított mérték közötti leképezés beállításával lehetővé teszi a Készletláthatóság szolgáltatás számára, hogy a fizikai mérték alapján automatikusan érvényesítse a foglalások rendelkezésre állását.

Mielőtt beállítaná ezt a hozzárendelést, a fizikai mérőszámokat, a számított mérőszámokat és azok adatforrásait a Power Apps oldalon a **Konfiguráció** lap **Adatforrás** és **Számított intézkedés** lapjain kell meghatározni (a témakör korábbi részében leírtak szerint).

A lágy foglalási leképezés definiálásához kövesse az alábbi lépéseket.

1. Határozza meg azt a fizikai mértéket, amely a lágy foglalási mértékként szolgál (például `softreservordered`).
1. A **Konfiguráció** lap **Számított intézkedés** lapján határozza meg a *Foglalásra rendelkezésre álló* (AFR) számított mérőszámot, amely tartalmazza a fizikai mérőszámhoz leképezni kívánt AFR-számítási képletet. Például beállíthatja a `availforreserv` (foglalható) címet úgy, hogy az a korábban meghatározott `softreservordered` fizikai mérőszámhoz legyen hozzárendelve. Így megtudhatja, hogy a `softreservordered` készletállapotú mennyiségek közül melyek lesznek foglalhatók. A következő táblázat az AFR számítási képletét mutatja.

    | Módosító | Adatforrás | Méret |
    |---|---|---|
    | `Addition` | `fno` | `availphysical` |
    | `Addition` | `pos` | `inbound` |
    | `Subtraction` | `pos` | `outbound` |
    | `Subtraction` | `iv` | `softreservordered` |

1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Lágy foglalási leképezés** lapon állítsa be a fizikai mérőszám és a számított mérőszám közötti leképezést. Az előző példában a következő beállításokat használhatja a `availforreserv` leképezéséhez a korábban meghatározott `softreservordered` fizikai mérőszámhoz.

    | Fizikai mérőszám adatforrás | Fizikai mérőszám | Foglalási adatforráshoz rendelkezésre álló | Elérhető foglalásra számított mérőszám |
    |---|---|---|---|
    | `iv` | `softreservordered` | `iv` | `availforreserv` |

### <a name="set-up-a-soft-reservation-hierarchy"></a><a name="setup-reservation-hierarchy"></a>Lágy foglalási hierarchia beállítása

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

A **Lágy foglalási hierarchia** lap szerkesztése előtt be kell kapcsolnia az *OnHandReservation* funkciót a **Funkciókezelés** lapon.

A foglalási hierarchia a foglalások során megadandó dimenziók sorrendjét írja le. Ugyanúgy működik, mint a termékindex-hierarchia a kézben lévő lekérdezéseknél.

A foglalási hierarchia eltérhet a készleten lévő index hierarchiájától. Ez a függetlenség lehetővé teszi a kategóriamenedzsment megvalósítását, ahol a felhasználók részletekre bonthatják a dimenziókat, hogy pontosabb foglalásokhoz meghatározzák a követelményeket.

#### <a name="example"></a>Példa

A rendszerben a következő foglalási hierarchia van beállítva.

| Dimenzió | Hierarchia |
|---|---|
| `ColorId` | 1 |
| `SizeId ` | 2 |
| `StyleId` | 3 |

A foglalási hierarchia alapján a foglalásokat a következő dimenziórendekben végezheti el:

- `()` - Nincs megadva méret.
- `(ColorId)`
- `(ColorId, SizeId)`
- `(ColorId, SizeId, StyleId)`

A dimenziók sorrendjének szigorúan követnie kell a foglalási hierarchia sorrendjét, dimenzióról dimenzióra. Például a `(ColorId, StyleId)` címmel rendelkező foglalások ebben a példában nem lesznek megengedettek, mivel ez a szekvencia nincs definiálva a foglalási hierarchiában.

### <a name="control-feature-management"></a><a name="feature-switch"></a>Vezérlőfunkció kezelése

A Készletláthatóság kiegészítő olyan funkciókat biztosít, mint az *OnHandReservation* és az *OnHandMostSpecificBackgroundService*. Alapértelmezés szerint ezek a funkciók ki vannak kapcsolva. Használatukhoz nyissa meg a **Konfiguráció** oldalt a Power Apps oldalon, majd a **Funkicókezelés** lapon kapcsolja be őket.

### <a name="complete-and-update-the-configuration"></a>A konfiguráció befejezése és frissítése

Miután befejezte a konfigurációt, minden módosítást rögzítenie kell a Készletláthatóságban. A módosítások rögzítéséhez válassza a Power Apps oldalon a **Konfiguráció** oldal jobb felső sarkában a **Konfiguráció frissítése** lehetőséget.

Amikor először választja a **Konfiguráció frissítése** lehetőséget, a rendszer bekéri a hitelesítő adatokat.

- **Ügyfélazonosító** - Az Az Azure-alkalmazás azonosítója, amelyet a Készletláthatósághoz létrehozott.
- **Bérlőazonosító** - Az Ön Azure bérlőjének azonosítója.
- **Ügyféltitok** - Az Azure-alkalmazás titka, amelyet a Készletláthatósághoz létrehozott.

A bejelentkezés után a konfiguráció frissül a Készletláthatóság szolgáltatásban.

> [!NOTE]
> A Készletláthatóság szolgáltatás konfigurációjának frissítése előtt mindenképpen ellenőrizze az adatforrás nevét, a fizikai mérőszámokat és a dimenziók hozzárendelését. Ezeket a beállításokat nem tudja módosítani, miután kiválasztotta a **Konfiguráció frissítése** lehetőséget.

### <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>A szolgáltatás végpontjának keresése

Ha nem ismeri a megfelelő Készletláthatóság szolgáltatás végpontját, nyissa meg a **Konfiguráció** oldalt a Power Apps oldalon, majd válassza a jobb felső sarokban a **Szolgáltatás végpontjának megjelenítése** lehetőséget. Az oldal a megfelelő szolgáltatás végpontját fogja megjeleníteni.

## <a name="operational-visibility"></a>Operatív láthatóság

Az **Operatív láthatóság** oldal a különböző dimenziókombinációk alapján egy valós idejű készletlekérdezés eredményeit mutatja be. Ha az *OnHandReservation* funkció be van kapcsolva, akkor az **Operatív láthatóság** oldalról is közzéteheti a foglalási kérelmeket.

### <a name="on-hand-query"></a>Kézi lekérdezés

Az **Kézi lekérdezés** lapon a valós idejű készletlekérdezés eredményei láthatók.

Amikor kiválasztja az **Kézi lekérdezés** lapot, a rendszer lekéri az Ön hitelesítő adatait, hogy megkapja a Bearer tokent, amely a Készletláthatósági szolgáltatás lekérdezéséhez szükséges. A **BearerToken** mezőbe egyszerűen beillesztheti a Bearer tokent, és bezárhatja a párbeszédpanelt. Ezután feltehet egy kézhez kapott lekérdezési kérelmet.

Ha a **BearerToken** mezőbe be kell illesztenie egy újat, ha a BearerToken jelszó érvénytelen vagy lejárt. Adja meg a megfelelő **ügyfél-azonosító**, **bérlőazonosító** és **ügyféltitok** értékeket, majd válassza a **Frissítés** lehetőséget. A rendszer automatikusan kap egy új, érvényes bearer tokent.

Kézi lekérdezés feladásához adja meg a lekérdezést a kérés törzsében. Használja a [lekérdezésben leírt mintát a post módszer használatával](inventory-visibility-api.md#query-with-post-method).

![Kézi lekérdezés beállításai](media/inventory-visibility-query-settings.png "Kézi lekérdezés beállításai")

### <a name="reservation-posting"></a>Foglalási feladás

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Használja a **Foglalások közzététele** lapot a foglalási kérelem feladásához. Mielőtt foglalási kérelmet adhatna fel, be kell kapcsolnia az *OnHandReservation* funkciót. A funkcióval kapcsolatos további információkért lásd a [Készletláthatósági fenntartások](inventory-visibility-reservations.md) című részt.

A foglalási kérelem elküldéséhez meg kell adnia egy értéket a kérelem törzsében. Használja az [Egy foglalási esemény létrehozása](inventory-visibility-api.md#create-one-reservation-event) című fejezetben leírt mintát. Ezután válassza a **Feladás** menüpontot. A kérelemre adott válasz részleteinek megtekintéséhez válassza a **Részletek megjelenítése** lehetőséget. A **reservationId** értéket a válasz adataiból is lekérdezheti.

## <a name="inventory-summary"></a>Készlet-összesítő

A **Készletösszesítő** a *Készlet OnHand Sum Entitás* testreszabott nézete. A termékek készlet összesítését az összes dimenzióval együtt biztosítja. A Dataverse által biztosított **Speciális szűrő** használatával létrehozhat egy olyan személyes nézetet, amely az Ön számára fontos sorokat mutatja. A fejlett szűrési lehetőségekkel a nézetek széles skáláját hozhatja létre, az egyszerűtől az összetettig. Lehetővé teszik továbbá, hogy csoportosított és egymásba ágyazott feltételeket adjon a szűrőkhöz.

Ha többet szeretne megtudni a **Speciális szűrő** használatáról, lásd: [Személyes nézetek szerkesztése vagy létrehozása a speciális rácsszűrők használatával](/powerapps/user/grid-filters-advanced)

A testreszabott nézet tetején három mező található: **Alapértelmezett méret**, **Egyéni méret** és **Méret**. Ezekkel a mezőkkel szabályozhatja, hogy mely oszlopok legyenek láthatóak.

Kiválaszthatja az oszlopfejlécet az aktuális eredmény szűréséhez vagy rendezéséhez.

A testreszabott nézet alján olyan információk jelennek meg, mint például „50 rekord (29 kiválasztott)” vagy „50 rekord”. Ez az információ a **Speciális szűrő** eredményéből jelenleg betöltött rekordokra vonatkozik. A „29 kiválasztott” szöveg a betöltött rekordok oszlopfejlécszűrőjének használatával kiválasztott rekordok számára utal.

A nézet alján található a **Továbbiak betöltése** gomb, amellyel további rekordokat tölthet be a Dataverse rendszerből. A betöltött rekordok alapértelmezett száma 50. Ha a **Továbbiak betöltése** lehetőséget választja, a következő 1000 elérhető rekord kerül betöltésre a nézetbe. A **Továbbiak betöltése** gombon megjelenő szám a jelenleg betöltött rekordokat és a **Speciális szűrő** eredményének összes rekordját jelzi.

![Készlet-összesítő](media/inventory-visibility-onhand-list.png "Készlet-összesítő")
