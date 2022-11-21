---
title: Készletláthatóság – foglalások
description: Ez a témakör leírja, hogyan lehet beállítani a foglalási funkciót a foglalások, foglalások és/vagy a megadott készletmennyiségek foglalásának a Készlet láthatósága funkcióval való létrehozásához.
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
ms.openlocfilehash: 0ae0589f8bac7ebf9b43cf0f3bc02680d324b29b
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762722"
---
# <a name="inventory-visibility-reservations"></a>Készletláthatóság – foglalások

[!include [banner](../includes/banner.md)]

Ez a témakör az olyan tipikus esetről ad le, amely az előzetes foglalásokra jellemző, és bemutatja, hogyan lehet beállítani őket a készlet láthatóságában. Tájékoztatást tartalmaz az kötetlen foglalások létrehozásáról, a tényleges felhasználással kapcsolatos ellentételükről, valamint a megadott készletmennyiségek módosításáról vagy foglalás nélküli foglalásról.

## <a name="sample-use-case-for-soft-reservation"></a>Mintaeset az előzetes foglalás esethez

A köte foglalások segítik a szervezeteket a rendelkezésre álló készlet igaz igaz forrásának elérésében, különösen a rendelés teljesítésének folyamata során. Ez a funkció olyan szervezeteknél hasznos, ahol a következő feltételek teljesülnek:

- A szervezet legalább két különböző rendszerrel rendelkezik, amelyek közvetlenül kimenő rendeléseket szednek be.
- A szervezet nagyon szigorú, és meg kívánja akadályozni a termékkészlet dupla lefoglalását, ami akkor fordulhat elő, ha több rendszer képes az utolsó készlet túlfoglalására. Ez a helyzet megakadályozza, hogy minden rendelési rendszer azonnali, egyszerű foglalási API-hívásokat hozjon létre a Készlet láthatósága számára, amely egyetlen igaz forrást biztosít a készlet rendelkezésre állásához.

[<img src="media/inventory-visibility-soft-reservation.png" alt="Inventory Visibility soft reservation." title=" Készlet láthatóságának előzetes lefoglalása" width="720" />](media/inventory-visibility-soft-reservation.png)

Az előző ábra bemutatja az előzetes foglalások működését, és bemutatja a következő műveleteket:

- A kezdeti készletszint szinkronizálva van a Microsoft készlet láthatóságával Dynamics 365 Supply Chain Management.
- Az egyes rendelési csatornákból vagy rendszerekből az egyes soft foglalások feladása a készlet láthatósága érdekében megszabadul. A készlet láthatósága ellenőrzi a készlet rendelkezésre állását, és megpróbálk egy kis foglalást. Ha sikerült az előzetes foglalás, a készlet láthatósága hozzáadja az előre lefoglalt mennyiséget, levon a rendelkezésre álló foglalási mennyiségből (AFR), és választ ad az soft reservation id azonosítóval.
- Jelenleg a tényleges készletmennyiség változatlan marad.
- Ezt követően vagy egyetlen, vagy összesített, köt nélkül lefoglalt rendeléseket (rendeléssorokat) szinkronizálhat az ellátásilánc-kezelővel, hogy végleges foglalásokat véglegesen lefoglaljon és raktárba kiadjon, vagy frissítse a végső készletmennyiséget.
- Beállítható, hogy a [rendszer](#offset-scm) az ellátásilánc-kezelésben a tényleges készlet frissítése esetén kiegyenlítse az soft foglalásokat.

Az köteként használt foglalásokat általában a Készlet láthatósága szolgáltatás API-hívásával lehet létrehozni, fel használni és törölni.

> [!NOTE]
> Tetszés szerint az Ellátásilánc-kezelés (és más külső fél) rendszerek beállításával automatikusan kiegyenlítheti a készlet láthatóságának használatával lefoglalt mennyiséget. Az eltolt mennyiség törlésre kerül a Készletláthatóságban lévő foglalási rekordokból.
>
> Alapértelmezés szerint az ellenszámla funkció automatikusan bekapcsolódik az előzetes foglalási funkció engedélyezése esetén.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>A foglalási funkció bekapcsolása és beállítása

A foglalási funkció bekapcsolásához kövesse az alábbi lépéseket.

1. Jelentkezzen be, Power Apps és nyissa **meg a készlet láthatóságát**.
1. Nyissa meg a **Konfiguráció** oldalt.
1. A **Funkciókezelés** lapon kapcsolja be az *OnHandReservation* funkciót.
1. Jelentkezzen be az ellátásilánc-kezelési környezetbe.
1. Ugorjon a **[Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** munkaterületre, és engedélyezze a *Készletláthatósági integráció foglaláseltolása* funkciót (a 10.0.22-es vagy újabb verzió szükséges).
1. Ugorjon a **Készletkezelés \> Beállítás \> Készletláthatóság integrációs paraméterek** lapra, nyissa meg a **Foglalások eltolása** lapot, és tegye a következő beállításokat:

    - **Foglalási eltolás engedélyezése** – A funkció engedélyezéséhez állítsa *Igen* értékre.
    - **Foglalási ellenszámla módosítója** – válassza ki azt a készlettranzakció-állapotot, amely kiegyenlíti a készlet láthatóságában megadott foglalásokat. Ez a beállítás határozza meg azt a rendelésfeldolgozási szakaszt, amely az eltolásokat kiváltja. A szakasz nyomon követhető a megrendelés készlettranzakciós státusza alapján. Válasszon a következő értékek közül:

        - *Megrendelt* – a Megrendelt *állapotú* rendelések a létrehozáskor egy ellenigénylést küldenek. Az ellenmennyiség a létrehozott rendelés (sor) mennyisége lesz.
        - *Foglalás* – a *Foglalás* állapotú rendelések ellenigénylést küldenek, amikor vagy a rendelés foglalt, vagy fizikailag le vannak foglalva. Ha a Foglalás *állapotnál* ellentételezést ad meg, a rendelés az esetleges olyan új készletállapotba küld ellenkérést, amely legközelebb áll a kitárolt foglaláshoz (például kitárolt, feladott vagy számlázott). Ez a viselkedés akkor is előfordul, ha kihagyja a foglalást az Ellátásilánc-kezelésben, és folytatja egy másik készletállapotra (például ha kitárol a raktárból a raktárba való kiadást, hogy kitároljon és csomagoljon). A kérelem csak egyszer fog kiváltva. Ha a kicsomagoláskor történt esemény, akkor a csomagjegyzékek feladott ellenszámlája nem ismétlődik. Az ellenszámla mennyisége meg fog egyezést kiváltva a készlettranzakció állapotában szereplő mennyiséggel (*más szóval a Foglalt rendelt*/*foglalás tényleges foglalása*, vagy egy későbbi állapot a megfelelő rendeléssoron).

1. Jelentkezzen be a Készlet láthatósága alkalmazásba, menjen **a** Konfiguráció lapra, **majd az Soft Reservation** lapon ellenőrizze az alapértelmezett soft reservation hierarchiát. Szükség szerint adjon hozzá új dimenziókat a hierarchiához.
1. Az Soft **Reservation Mapping szakaszban** megtekintheti az alapértelmezett beállításokat. A program alapértelmezés szerint az soft lefoglalt készletmennyiségeket `softreservephysical` az adatforrás fizikai mértékéhez rögzíti `iv`. A *Foglalásra elérhető számított* mérték megfeleltetve a következőnek `availabletoreserve`: Ha frissíteni szeretné a `availabletoreserve` számított mértéket, **menjen** a Konfiguráció lapra, **majd** a Számított mérték lapon bontsa ki és módosítsa a számított mértéket.

További információért lásd: [Készlet láthatóságának konfigurálása](inventory-visibility-configuration.md).

> [!NOTE]
> A foglalási hierarchia a foglalások során megadandó dimenziók sorrendjét írja le. Ugyanúgy működik, mint az indexhierarchia az elérhető lekérdezésekben, de egymástól függetlenül használható, így a felhasználók megadhatják a dimenziók részleteit, hogy pontosabb foglalásokat adjanak meg.
>
> Az "soft reservation" hierarchiának `SiteId``LocationId` összetevőként és tartalmazó hierarchiának kell lennie, mivel ezek a készlet láthatóságának partíció-konfigurációját építik fel.

A foglalások konfigurálásával kapcsolatos további tudnivalókat lásd: [Foglalási konfiguráció](inventory-visibility-configuration.md#reservation-configuration).

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Használja a foglalási funkciót a Készletláthatóságban

A foglalási API meghívásakor a rendszer megjelöli a megadott áruk és mennyiségek foglalását.

Példaként adhatja meg az esetet és a minta API-lekérdezés törzsét. A Contoso vállalat a D0002 (Kabinet) terméket értékesíti annak e-commerce webhelyén. Egy vevő értékesítési rendelést ad fel egy kis piros kabinetnek a webhelyen keresztül. A Contoso úgy dönt, hogy a következő dimenziók segítségével teljesíti ezt a rendelést:

- Szervezetazonosító = usmf
- Hely = 1
- Raktár = 11
- Termék = D0002
- Szín = piros
- Méret = kicsi

A Contoso már beállított API-kapcsolatot a készlet láthatóságához a saját e-commerce rendszerből. A rendelés érkezik, és a rendszer azonnal kivált egy API-hívást, hogy egy finom foglalást rendeljen meg a készlet láthatósági rendszerében.

### <a name="create-soft-reservations-using-the-reservation-api"></a>Köte foglalások létrehozása a foglalási API segítségével

A foglalások a Készletláthatóság szolgáltatásban a szolgáltatás URL-jének (például `/api/environment/{environmentId}/onhand/reserve`) küldött POST-kérelemmel történnek.

Foglalás esetén a kérelem testének tartalmaznia kell egy szervezet azonosítóját, egy termék azonosítóját, a lefoglalt mennyiségeket és dimenziókat.

A foglalási API hívása esetén a foglalások érvényességének ellenőrzése a logikai `ifCheckAvailForReserv` paraméter megadásával szabályozható a kérelemtörzsben. A `True` érték azt jelenti, hogy ellenőrzés szükséges, míg a `False` érték azt, hogy az ellenőrzés nem kötelező. Az alapértelmezett érték a `True`.

Ha érvényteleníteni szeretne egy foglalást, vagy le szeretné foglalni a megadott készleten lévő mennyiségeket, állítsa a mennyiséget negatív értékre, és állítsa be a `ifCheckAvailForReserv` paramétert `False` értékre az ellenőrzés kihagyása céljából.

Az előző környezetben az értékesítési rendelésre hivatkozó kérés törzsére mutató példa.

```json
# Url

#Replace {endpoint} with your system endpoint.
    {endpoint}/api/environment/{environmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "Testrequest-0005",
    "organizationId": "usmf",
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "softreservphysical",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

A sikeres, soft foglalási kérések minden egyes *foglalási rekordhoz egy soft reservation azonosítót* ad vissza. Az egyedi foglalásazonosító nem egyedi azonosító egy egyedi foglalási rekordhoz, hanem a termékazonosító és a dimenzióértékek kombinációja, amely az egyedi foglalási kérelemhez társul. A rendelési sorhoz rögzítheti az soft reservation azonosítóját, amikor a sikeresen lefoglalt rendeléseket szinkronizálja az Ellátásilánc-kezelés vagy más ERP-rendszerrel az ellentranzakcióhoz.

### <a name="offset-soft-reservations-in-supply-chain-management"></a><a name="offset-scm"></a> Az ellátásilánc-kezelésben foglalt köte kompenzációs foglalások ellenszámlája

Az egy rendelésen szereplő mennyiségnek az Ellátásilánc-kezelés vagy más ERP rendszerből való fizikai levonása után el lehettózni az esetleg vissza nem foglalt mennyiséget. A készlet láthatósága a készlettranzakciókhoz és az ellátásilánc-kezeléshez való előzetes foglalások ellentételének integrálását kínálja.

A következő lépések szerint kiegyenlíti az egyszerű foglalást.

1. Jelentkezzen be a Supply Chain Management alkalmazásba.
1. Ugrás az Értékesítési **és marketingrendelések \> minden \> értékesítési rendelésre**
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Hozza létre újra a külső értékesítési rendelést, és adjon hozzá egy olyan értékesítési sort, amely pontosan ugyanazt a termékazonosítót, szervezetet, telephelyet, raktárat és dimenzióértékeket használja.
1. Válassza ki **az éppen** beírt értékesítési sort az Értékesítésirendelés-sorok gyorstáblában, **\> majd válassza ki az eszköztár Készletfoglalás-azonosítóját**.
1. Tegye a következők egyikét:

    - Másolja az soft foglalás azonosítóját az soft reservation request válaszba, és másolja be a Foglalásazonosító **mezőbe**.
    - Hagyja üresen **a Foglalásazonosító** mezőt, de jelölje be a **Készletszolgáltatás automatikus ellentranzakciójának** jelölőnégyzetét. A rendszer automatikusan meghatározza, hogy mely termék- és termékdimenziókat kell ellentételként megadni a kijelölt sorban megadott cikkazonosító és dimenzióértékek alapján.

1. Válassza ki az **OK** lehetőséget.
1. Miközben ugyanaz az értékesítési sor még ki van választva, **\>** **ténylegesen** lefoglalhatja a megrendelt mennyiséget az Értékesítésirendelés-sorok gyorspult eszköztárának Készletfoglalás elemét választva.
1. Ha korábban **a** *Foglalás* ellenszámla-módosító mezőjét Foglalt állapotúra beállította, az ellenszámla akkor fog aktiválódni, ha a *rendeléssor Állapota Tényleges* *foglalás vagy Foglalás megrendelve.* A kötegelt feladat percek alatt fut, és szinkronizálja az ellátásilánc-kezeléstől az ellenkéréseket a készlet láthatósága érdekében.

> [!NOTE]
> A megadott tartalék-ellenszámla-módosítót is magában vevő tranzakcióállapotok esetén a tranzakció frissítése a következő feltételek teljesülása esetén kiegyenlíti a megfelelő foglalási rekordot:
>
> - A készlettranzakció foglalásazonosítója megegyezik a készlet láthatósága foglalási rekordjának azonosítójával.
> - A készlettranzakció dimenziói megegyeznek a készlet láthatósága foglalási rekord dimenzióival.
> - A készleti tranzakció státuszában bekövetkező változások akkor váltják ki a foglalások ellentételezését, ha a készleti tranzakció státusza azt tükrözi, hogy egy rendelési folyamat befejeződött vagy kihagyásra került.

Az ellenmennyiségek a megfelelő készlettranzakciókban meghatározott készletmennyiségeket követik. Az ellenszámla csak akkor lép hatályba, ha a foglalt mennyiség megmarad a készlet láthatóságában.

### <a name="cancel-or-revert-a-soft-reservation"></a>Az előzetes foglalás visszavonása vagy visszavonása

Ha egy eredeti rendeléssort visszavonnak vagy törölnek, és a megfelelő nem teljes foglalást vissza kell induklani, akkor az API-lekérdezés törzsében olyan negatív mennyiséget kell feladni, amely pontosan ugyanazt az információt tartalmazza.
