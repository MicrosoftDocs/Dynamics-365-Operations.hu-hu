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
ms.openlocfilehash: 4a85520c0911bb7eed5842b3fd5bd706009351e5
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500355"
---
# <a name="inventory-visibility-reservations"></a>Készletláthatóság-foglalások

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Ez a témakör azt írja le, hogyan kell beállítani a foglalási funkciót, hogy a Készletláthatóság használatával foglalásokat hozzon létre, foglalásokat fogyasszon el és/vagy feloldjon meghatározott készletmennyiségeket.

A foglalások olyan készletmennyiséget jelölnek, amelyet a jövőben fognak felhasználni. A foglalás létrehozásakor a rendszer megakadályozza, hogy más megrendelések lefoglalják vagy elfogyasszák a lefoglalt árukat, amíg a foglalás el nem fogy vagy fel nem oldják a foglalás feloldását. A foglalások létrehozása, felhasználása és törlése a Készletláthatóság szolgáltatáshoz intézett API-hívások segítségével történik.

Opcionálisan beállíthatja a Microsoft Dynamics 365 Supply Chain Management (és más, harmadik féltől származó rendszerek) rendszerét úgy, hogy a Készletláthatóság használatával automatikusan kiegyenlítse a lefoglalt mennyiséget. Az eltolt mennyiség törlésre kerül a Készletláthatóságban lévő foglalási rekordokból.

Ha bekapcsolja a foglalási funkciót, a Supply Chain Management automatikusan készen áll a készletek láthatóságának használatával készített foglalások kiegyenlítésére.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>A foglalási funkció bekapcsolása és beállítása

A foglalási funkció bekapcsolásához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Power Apps-be, és nyissa meg a **Készletlátóság** lehetőséget.
1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Funkciókezelés** lapon kapcsolja be az *OnHandReservation* funkciót.
1. Jelentkezzen be a Supply Chain Management alkalmazásba.
1. Ugorjon a **[Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** munkaterületre, és engedélyezze a *Készletláthatósági integráció foglaláseltolása* funkciót (a 10.0.22-es vagy újabb verzió szükséges).
1. Ugorjon a **Készletkezelés \> Beállítás \> Készletláthatóság integrációs paraméterek** lapra, nyissa meg a **Foglalások eltolása** lapot, és tegye a következő beállításokat:
    - **Foglalási eltolás engedélyezése** – A funkció engedélyezéséhez állítsa *Igen* értékre.
    - **Foglaláseltolás módosítója** – Válassza ki azt a készlettranzakció-állapotot, amely a készlet láthatósága alapján eltolja a foglalásokat. Ez a beállítás határozza meg azt a rendelésfeldolgozási szakaszt, amely az eltolásokat kiváltja. A szakasz nyomon követhető a megrendelés készlettranzakciós státusza alapján. A következők közül választhat:
        - *Megrendeléskor* - A *Tranzakciókor* státusz esetén a megrendelés létrehozásakor a megrendelés elküldi az ellentételezési kérelmet. Az eltolásmennyiség a létrehozott rendelés mennyisége lesz.
        - *Tartalékolás* - A *Megrendelt tartalékolás tranzakciós* státusz esetén a rendelés akkor küld beszámítási kérelmet, amikor lefoglalják, felveszik, feladják a csomagolólapot vagy kiszámlázzák. A kérés csak egyszer, az első lépésben aktiválódik, amikor az említett folyamat bekövetkezik. Az eltolás mennyisége az a mennyiség, amelynél a készlettranzakció állapota a *Megrendelt* állapotról *Lefoglalt rendeltre* (vagy későbbi állapotra) változott a megfelelő rendelési sorban.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Használja a foglalási funkciót a Készletláthatóságban

A foglalási API meghívásakor a rendszer megjelöli a megadott áruk és mennyiségek foglalását. Meg kell határoznia egy foglalási hierarchiát, és a foglalási hierarchiának megfelelő kérelmeket kell feladnia. A foglalások ezután a foglalási API-k közvetlen hívásával végezhetők el.

### <a name="configure-the-reservation-hierarchy"></a>A foglalási hierarchia konfigurálása

A foglalási hierarchia a foglalások során megadandó dimenziók sorrendjét írja le. Ugyanúgy működik, mint az indexhierarchia a kézi lekérdezéseknél.

A foglalási hierarchia eltérhet az indexhierarchiától. Ez a függetlenség lehetővé teszi a kategóriamenedzsment megvalósítását, ahol a felhasználók részletekre bonthatják a dimenziókat, hogy pontosabb foglalásokhoz meghatározzák a követelményeket.

A lágy foglalási hierarchia konfigurálásához a Power Apps oldalon nyissa meg a **Konfiguráció** lapot, majd a **Lágy foglalási hierarchia** lapon állítsa be a foglalási hierarchiát a dimenziók és hierarchiaszintjeik hozzáadásával és/vagy módosításával.

A lágy foglalás hierarchiájának tartalmaznia kell a `SiteId` és a `LocationId` elemet összetevőként, mivel ezek partíciókonfigurációt alkotnak.

A foglalások konfigurálásával kapcsolatos további tudnivalókat lásd: [Foglalási konfiguráció](inventory-visibility-configuration.md#reservation-configuration).

### <a name="call-the-reservation-api"></a>A foglalási API hívása

A foglalások a Készletláthatóság szolgáltatásban a szolgáltatás URL-jének (például `/api/environment/{environment-ID}/onhand/reserve`) küldött POST-kérelemmel történnek.

Foglalás esetén a kérelem testének tartalmaznia kell egy szervezet azonosítóját, egy termék azonosítóját, a lefoglalt mennyiségeket és dimenziókat. A kérés minden egyes foglalási rekordhoz egyedi foglalási azonosítót generál. A foglalási rekord tartalmazza a termék azonosítójának és dimenzióinak egyedi kombinációját.

A foglalási API hívása esetén a foglalások érvényességének ellenőrzése a logikai `ifCheckAvailForReserv` paraméter megadásával szabályozható a kérelemtörzsben. A `True` érték azt jelenti, hogy ellenőrzés szükséges, míg a `False` érték azt, hogy az ellenőrzés nem kötelező. Az alapértelmezett érték a `True`.

Ha érvényteleníteni szeretne egy foglalást, vagy le szeretné foglalni a megadott készleten lévő mennyiségeket, állítsa a mennyiséget negatív értékre, és állítsa be a `ifCheckAvailForReserv` paramétert `False` értékre az ellenőrzés kihagyása céljából.

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

### <a name="set-up-the-reservation-offset-modifier"></a>A foglaláseltolás módosító beállítása

Ha még nem tette meg, állítsa be a foglalásmódosítót [A foglalási funkció bekapcsolása és beállítása](#turn-on) szakaszban leírtak szerint.

### <a name="set-up-reservation-ids"></a>Foglalási azonosítók beállítása

A foglalási azonosító egyedileg jelöl egy foglalási rekordot a Készletláthatóságban. A Supply Chain Managementtben a felhasználók foglalásokat helyeznek el a rendeléssorokon, hogy a megfelelő foglalási rekordhoz tartozó ellentételezést jelöljék meg.

A foglalási azonosítók beállításához a Supply Chain Managementtben kövesse az alábbi lépéseket.

1. Nyisson meg egy értékesítési megbízást (például az **Összes értékesítési megbízás** oldalról).
1. Az **Értékesítési rendeléssorok** gyorslapon válasszon ki egy rendeléssort.
1. Az **Értékesítési rendelés sorai** gyorslap eszköztáron válassza a **sor frissítése \> Készlet \> Készletláthatóság integráció** menüpontot.
1. Adja meg a megfelelő foglalási azonosítókat.

A készletállapot-változás megfelel az ellentételezési módosító beállításának.
