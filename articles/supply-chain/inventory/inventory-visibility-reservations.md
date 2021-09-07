---
title: Készletláthatóság-foglalások
description: Ez a témakör azt írja le, hogyan kell beállítani a foglalási funkciót, hogy a Készletláthatóság használatával foglalásokat hozzon létre, foglalásokat fogyasszon el és/vagy feloldjon meghatározott készletmennyiségeket.
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
ms.openlocfilehash: 6c87018cbfbe22fbbc441a1a23aee0ac44af9ddc
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345149"
---
# <a name="inventory-visibility-reservations"></a>Készletláthatóság-foglalások

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Ez a témakör azt írja le, hogyan kell beállítani a foglalási funkciót, hogy a Készletláthatóság használatával foglalásokat hozzon létre, foglalásokat fogyasszon el és/vagy feloldjon meghatározott készletmennyiségeket.

A foglalások olyan készletmennyiséget jelölnek, amelyet a jövőben fognak felhasználni. A foglalás létrehozásakor a rendszer megakadályozza, hogy más megrendelések lefoglalják vagy elfogyasszák a lefoglalt árukat, amíg a foglalás el nem fogy vagy fel nem oldják a foglalás feloldását. A foglalások létrehozása, felhasználása és törlése a Készletláthatóság szolgáltatáshoz intézett API-hívások segítségével történik.

Opcionálisan beállíthatja a Microsoft Dynamics 365 Supply Chain Management (és más, harmadik féltől származó rendszerek) rendszerét úgy, hogy a Készletláthatóság használatával automatikusan kiegyenlítse a lefoglalt mennyiséget. Az eltolt mennyiség törlésre kerül a Készletláthatóságban lévő foglalási rekordokból.

Ha bekapcsolja a foglalási funkciót, a Supply Chain Management automatikusan készen áll a készletek láthatóságának használatával készített foglalások kiegyenlítésére.

> [!NOTE]
> Az ellentételezési funkcióhoz a Supply Chain Management 10.0.22-es vagy újabb verziója szükséges. Ha használni szeretné a készleti láthatósági foglalásokat, javasoljuk, hogy várjon, amíg a Supply Chain Management 10.0.22-es vagy újabb verzióra frissíti a Supply Chain Managementet.

## <a name="turn-on-the-reservation-feature"></a>A foglalási funkció bekapcsolása

A foglalási funkció bekapcsolásához kövesse az alábbi lépéseket.

1. A Power Apps oldalon nyissa meg a **Készletláthatóság** lehetőséget.
1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Funkciókezelés** lapon kapcsolja be az *OnHandReservation* funkciót.
1. Jelentkezzen be a Supply Chain Management alkalmazásba.
1. Menjen a **Készletgazdálkodás \> Beállítás \> Készletláthatóság integrációs paraméterek** menüpontba.
1. A **Foglalási eltolás** alatt állítsa a **Foglalási eltolás engedélyezése** opciót *Igen*-re.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Használja a foglalási funkciót a Készletláthatóságban

A foglalási API meghívásakor a rendszer megjelöli a megadott áruk és mennyiségek foglalását. Meg kell határoznia egy foglalási hierarchiát, és a foglalási hierarchiának megfelelő kérelmeket kell feladnia. A foglalások ezután a foglalási API-k közvetlen hívásával végezhetők el.

### <a name="configure-the-reservation-hierarchy"></a>A foglalási hierarchia konfigurálása

A foglalási hierarchia a foglalások során megadandó dimenziók sorrendjét írja le. Ugyanúgy működik, mint az indexhierarchia a kézi lekérdezéseknél.

A foglalási hierarchia eltérhet az indexhierarchiától. Ez a függetlenség lehetővé teszi a kategóriamenedzsment megvalósítását, ahol a felhasználók részletekre bonthatják a dimenziókat, hogy pontosabb foglalásokhoz meghatározzák a követelményeket.

A lágy foglalási hierarchia konfigurálásához a Power Apps oldalon nyissa meg a **Konfiguráció** lapot, majd a **Lágy foglalási leképezés** lapon állítsa be a foglalási hierarchiát a dimenziók és hierarchiaszintjeik hozzáadásával és/vagy módosításával.

### <a name="call-the-reservation-api"></a>A foglalási API hívása

A foglalások a Készletláthatóság szolgáltatásban a szolgáltatás URL-jének (például `/api/environment/{environment-ID}/onhand/reserve`) küldött POST-kérelemmel történnek.

Foglalás esetén a kérelem testének tartalmaznia kell egy szervezet azonosítóját, egy termék azonosítóját, a lefoglalt mennyiségeket és dimenziókat. A kérés minden egyes foglalási rekordhoz egyedi foglalási azonosítót generál. A foglalási rekord tartalmazza a termék azonosítójának és dimenzióinak egyedi kombinációját.

Itt van egy példa a kérés törzsére, referenciaként.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "SoftReservOrdered",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

## <a name="offset-reservations-in-supply-chain-management"></a>Offszet fenntartások a Supply Chain Managementben

Azon készleti tranzakciós státuszok esetében, amelyek tartalmaznak egy meghatározott tartalékellentételezési módosítót, a tranzakciófrissítés a megfelelő foglalási rekordot akkor veszi figyelembe, ha az alábbi feltételek mindegyike teljesül:

- A készleti tranzakcióban szereplő foglalási azonosító megegyezik a Készletláthatóság szolgáltatásban szereplő foglalási rekord foglalási azonosítójával.
- A készleti tranzakció dimenziói megegyeznek a Készletláthatóság szolgáltatásban szereplő foglalási rekord dimenzióival.
- A készleti tranzakció státuszában bekövetkező változások akkor váltják ki a foglalások ellentételezését, ha a készleti tranzakció státusza azt tükrözi, hogy egy rendelési folyamat befejeződött vagy kihagyásra került.

Az ellentételezési mennyiség a készleti tranzakciókban megadott készletmennyiséget követi. Az ellentételezés nem lép érvénybe, ha a Készletláthatóság szolgáltatásban nem maradt lefoglalt mennyiség.

> [!NOTE]
> Az ellentételezés funkció a 10.0.22-es verziótól érhető el

### <a name="set-up-the-reserve-offset-modifier"></a>A tartalék ellentételezés módosító beállítása

A tartalék ellentételezés módosító határozza meg azt a megbízás-feldolgozási szakaszt, amely az ellentételezéseket kiváltja. A szakasz nyomon követhető a megrendelés készlettranzakciós státusza alapján. A tartalék ellentételezés módosító beállításához kövesse az alábbi lépéseket.

1. Menjen a **Készletgazdálkodás \> Beállítás \> Készletláthatóság integrációs paraméterek \> Foglalási eltolás** pontra.
1. Állítsa be a **Tartalék-ellentételezési módosító** mezőt az alábbi értékek egyikére:

    - *Megrendeléskor* - A *Tranzakciókor* státusz esetén a megrendelés létrehozásakor a megrendelés elküldi az ellentételezési kérelmet.
    - *Tartalékolás* - A *Megrendelt tartalékolás tranzakciós* státusz esetén a rendelés akkor küld beszámítási kérelmet, amikor lefoglalják, felveszik, feladják a csomagolólapot vagy kiszámlázzák. A kérés csak egyszer, az első lépésben aktiválódik, amikor az említett folyamat bekövetkezik.

### <a name="set-up-reservation-ids"></a>Foglalási azonosítók beállítása

A foglalási azonosító egyedileg jelöl egy foglalási rekordot a Készletláthatóságban. A Supply Chain Managementtben a felhasználók foglalásokat helyeznek el a rendeléssorokon, hogy a megfelelő foglalási rekordhoz tartozó ellentételezést jelöljék meg.

A foglalási azonosítók beállításához a Supply Chain Managementtben kövesse az alábbi lépéseket.

1. Nyisson meg egy értékesítési megbízást (például az **Összes értékesítési megbízás** oldalról).
1. Az **Értékesítési rendeléssorok** gyorslapon válasszon ki egy rendeléssort.
1. Az **Értékesítési rendelés sorai** gyorslap eszköztáron válassza a **sor frissítése \> Készlet \> Készletláthatóság integráció** menüpontot.
1. Adja meg a megfelelő foglalási azonosítókat.

A készletállapot-változás megfelel az ellentételezési módosító beállításának.
