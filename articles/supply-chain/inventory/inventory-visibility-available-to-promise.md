---
title: A készlet láthatósága – az aktuális készlet változásának ütemezése, amely ígérethez rendelkezésre áll
description: Ez a témakör ismerteti, hogyan lehet ütemezni a jövőbeli készletváltozásokat, és kiszámítani az ígérethez rendelkezésre álló mennyiségeket.
author: yufeihuang
ms.date: 05/11/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-04
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: f831c5d5719bbbd72c7cff37b8b35826f48ce6e4
ms.sourcegitcommit: ce58bb883cd1b54026cbb9928f86cb2fee89f43d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/25/2022
ms.locfileid: "9719291"
---
# <a name="inventory-visibility-on-hand-change-schedules-and-available-to-promise"></a>A készlet láthatósága – az aktuális készlet változásának ütemezése, amely ígérethez rendelkezésre áll

[!include [banner](../includes/banner.md)]

Ez a cikk azt ismerteti, *hogyan* lehet beállítani az ígérethez rendelkezésre álló mennyiségek ütemezését az elérhető készlet változásainak ütemezésére és az ígérethez rendelkezésre álló mennyiségek kiszámítására. Az ígérethez rendelkezésre álló cikk mennyisége, amely a következő időszakban ígérhető a vevőnek. A számítás használata nagy mértékben megnövelheti a rendelés teljesítését.

Számos gyártó, kiskereskedő vagy eladó számára nem elég csak tudni, hogy mi van aktuálisan elérhető. A jövőbeli elérhetőségüknek teljes rálátással kell lennie. Ennek a jövőbeli elérhetőségnek figyelembe kell vennie a jövőbeli készletet, a jövőbeli igényt és az ATP-t.

## <a name="enable-and-set-up-the-features"></a><a name="setup"></a> A funkciók engedélyezése és beállítása

Az "ATP" használata előtt az "ATP" mennyiségek kiszámításához egy vagy több számított mennyiséget kell beállítania. Ezenkívül be kell kapcsolnia a funkciót, és konfigurálnia kell az "ATP" beállításait a következőben:Microsoft Power Apps

### <a name="set-up-calculated-measures-for-atp-quantities"></a>Az "Egyen rendelkezésre álló mennyiségre" vonatkozó számított mennyiségek beállítása

Az *"Elérhető* mennyiség" számított mértéke egy előre meghatározott számított mérték, amely jellemzően az aktuálisan rendelkezésre álló mennyiség megkeresére használható. A *szállítási mennyiség azoknak a* *fizikai intézkedéseknek az összege, amelyekhez a kiegészítés módosító típusa van megszava, és az igény mennyisége azoknak a* fizikai mértéknek az összege, *amelyek* módosító típusú kivonással vannak *.*

Több számított mennyiséget is hozzá lehet adni az egyenérték-mennyiség kiszámításához. Az egyedi fizikai intézkedések teljes száma azonban az összes számításban rendelkezésre álló mennyiségnél kisebbnek kell lennie.

> [!IMPORTANT]
> A számított mérték a fizikai mértékek egy összeállítása. Képlete csak ismétlődés nélküli fizikai intézkedéseket tartalmazhat, számított intézkedéseket nem.

Például a következő számított mértéket állíthatja be:

**Elérhető elérhető** tényleges = (*PhysicalInvent* + *OnHand* + *–* + *korlátlan QualityInservion* + *Bejövő*) – (*ReservPhysical* + *SoftReservePhysical* + *Outbound*)

Az összeg (PhysicalInvent *OnHand* + *nem korlátozott QualityInservion* + *Bejövő* + *) a készletet, az összeget (* + *ReservPhysical* *SoftReservePhysical* + *Outbound* + *) pedig* az igényt képviseli. Ebből következően a számított mérték a következőképpen érthető:

**Elérhető készlet –** = *·* *igény*

A tényleges fizikai mennyiség **kiszámításához** hozzáadhat egy másik számított mértéket.

**Tényleges- és** tényleges érték = (*PhysicalInvent* + *OnHand* + *–* + *korlátlan QualityInékonyion* + *bejövő*) – (*Kimenő*)

Ebben a két számításban egyedi fizikai mérőművelet van: PhysicalInvent, OnHand *,* Unrestricted *,* QualityInservion *, Inbound*, *ReservPhysical* *,* SoftReservePhysical *és* Outbound.*·* *·*

További tájékoztatás a számított intézkedésekről: Számított [intézkedések](inventory-visibility-configuration.md#calculated-measures).

### <a name="turn-on-the-on-hand-change-schedule-feature-and-configure-atp-settings"></a>A rendelkezésre álló mennyiség módosítására használható ütemezési funkció bekapcsolás és az "ATP" beállítások konfigurálása

A következő lépések szerint kapcsolhatja be az *"ATP" beállításokat az"On-hand change schedule"* Power Apps funkcióhoz, és konfigurálhatja.

1. Jelentkezzen be, Power Apps és nyissa meg a készlet láthatóságát.
1. Nyissa meg a **Konfiguráció** oldalt.
1. A Szolgáltatáskezelés **lapon** kapcsolja be az *OnhandChangeSchedule szolgáltatást*.
1. Válassza az **"ATP beállítás" fület**.
1. A készlet láthatóságának lekérdezésekor az eredmény az összes itt hozzáadt, kiszámított, mennyiséggel számított mértéket tartalmazza. A **Hozzáadás** gombra választva új számított mértéket adhat hozzá az "Egy mennyiséghez" (ATP).
1. Állítsa be a következő mezőket:

    - **Adatforrás** – a számított mértékhez társított adatforrás kiválasztása.
    - **Számított mérték** – a kiválasztott adatforráshoz társított számított mérték kiválasztása, és az aktuálisan elérhető aktuális mennyiség kereséséhez használni kívánt mérték.
    - **Ütemezési időszak** – annak a napoknak a száma, a felhasználók megtekinthetik és elküldhetik az ütemezett, az adott időpontban végrehajtott módosításokat a kiválasztott számított mérték használata esetén. A készletadatokat lekérdező felhasználók az aktuális dátumtól kezdve az aktuális készletmennyiséget, az ütemezett aktuális készletváltozásokat és az ehhez az időszakban szereplő minden naphoz rendelkezésre álló mennyiséget kapják. Egy 1 és 7 közötti egész szám kiválasztása.

    > [!IMPORTANT]
    > Az ütemezési időszak tartalmazza az aktuális dátumot. Ennek megfelelően a felhasználók az aktuális dátumtól (a módosítás elküldését követően) bármely jövőbeli időpontban ütemezhetnek aktuálisan végrehajtott aktuális módosításokat (ütemezési időszak – 1) napon belül.

1. Válassza a **Mentés** lehetőséget.
1. Ismételje meg az 5–7. lépést addig, amíg fel nem adott minden kiszámított értéket az "ATP" mennyiséghez.
1. Ha végzett az összes szükséges beállítás konfigurálásával, válassza a Konfiguráció frissítése **lehetőséget**.

A további tudnivalókat lásd [a Konfiguráció befejezése és frissítése oldalon](inventory-visibility-configuration.md).

## <a name="how-the-on-hand-change-schedule-and-atp-calculations-work"></a>A rendelkezésre álló mennyiség változásának ütemezése és az "ATP" számítások munkája

Az *ütemezett készletváltozások várható* dátumának és mennyiségének megfelelő, az ütemezés szerinti változás ütemezése. Az aktuális készletre vonatkozó módosítási ütemezést be lehet nyújtani a készlet láthatósága érdekében, feltéve, **hogy** a dátumok az Ütemezési időszak beállítása által meghatározott időszakon belül vannak ([lásd](#setup) a Szolgáltatások engedélyezése és beállítása szakaszt). A készletadatokat lekérdező felhasználók az adott időszak minden egyes napjában meg fogják kapni az készletmennyiséget, az ütemezett tényleges készletváltozásokat és az ATP-mennyiséget.

Az ütemezett módosítások kezdetben nem véglegesítettek, ezért nem befolyásolják a rendszerben aktuálisan rendelkezésre álló mennyiségeket. A módosítások véglegesítéséhez *el* kell küldenének egy aktuális módosítási eseményt, amely frissíti a tényleges elérhető aktuális mennyiséget. Ezt követően az ütemezett változtatást úgy kell visszaállítani, hogy egyező negatív mennyiségre vonatkozó tényleges módosítási ütemezést ad meg.

Tegyük fel például, hogy 1000 forintos rendelést ad fel, és azt várja, hogy a rendelés holnap megérkezzen. Ezért olyan készletváltozási ütemezést küld el, amely bejövő mennyisége 10, és a dátum a holnapi dátum. Amikor a rendelés megérkezik a következő napra, a mennyiségeket hozzá kell adni az aktuális fizikai készlethez. Ezt követően a módosítás véglegesítésével kell frissítenie a rendszeren a tényleges aktuális készletmennyiséget. A módosítás véglegesítésére olyan készletváltozási eseményt kell benyújtani, amely 10 bejövő mennyiséggel rendelkezik. Ezt követően az ütemezett változtatást egy -10 mennyiségű bejövő mennyiséget is benyújtó tényleges készlet változási ütemezésének küldési művelete visszaállítja.

Ha az aktuális készlet és az "ATP" mennyiségek készlet-láthatóságát lekérdezésekor az ütemezési időszak egyes napjaira vonatkozóan a következő adatokat adja eredményül:

- **Dátum** – az a dátum, amelyre az eredmény vonatkozik. Az időzóna egyezményes világidő (UTC).
- **Aktuális mennyiség** – a megadott dátumon aktuális készletmennyiség. Ez a számítás a készlet láthatósága beállításhoz beállított, az "Egy rendelkezésre álló mennyiség" számításának megfelelően történik.
- **Ütemezett ellátás** – az ütemezett bejövő mennyiségek összege, amelyek ténylegesen nem állnak rendelkezésre azonnali felhasználásra vagy szállítmányra a megadott dátumon.
- **Ütemezett igény** – az összes olyan ütemezett kimenő mennyiség összege, amely még nem lett felhasználva vagy leszállítva a megadott dátumon.
- **Mennyiség -** a megadott dátumtól az ütemezési időszak végéig rendelkezésre álló minimális, tervezett aktuális készletmennyiség. Ez a mennyiség tartalmazza az összes ütemezett mennyiséghelyesbítást. Ez az a maximális mennyiség, amely az adott napon történő szállításra vagy felhasználásra az aktuális napon ígérható.

Ha például az aktuális dátum 2022. február 1., és az ütemezési időszak 7, akkor a felhasználók olyan ütemezett aktuális módosításokat küldhetnek be, amelyek 2022. február 1-től február 7-ig várhatók. Ebben az esetben február 3-i mennyiségének számítása például az adott napra aktuális készletmennyiség, február 3-tól február 7-ig ütemezett mennyiségek alapján történik.

## <a name="example"></a>Példa

A következő példa bemutatja, hogy az ütemezett mennyiségváltozások sorozata hogyan befolyásolja a készlet láthatósága által jelentésekben szereplő aktuális készlet- és az ATP-mennyiségeket. Azt is bemutatja, hogyan lehet véglegesítést ütemezni, hogyan befolyásolja az eredményt a vállalt ütemezés változtatása, és mi történhet, ha nem véglegesítési ütemezés szerinti változtatást.

A példában az eredmények egy tervezett, az *ön által elért értékeket mutatják*. Ez az érték az összes ütemezett frissítést illusztrálja, de a készlet láthatóságának lekérdezése során ténylegesen nem jelenthető.

1. A következő beállítások vannak konfigurálva a rendszeren az **"Egyhez rendelkezésre áll" beállítási lapon**:Power Apps

    - **Az "Egy rendelkezésre álló** mennyiség" kiszámított mértéke – van egy Kiszámított mértékegysége, amely az *"On-hand" nevet adja*. Számítása: készlet *= Készlet – Igény*. Itt kell kiválasztani a mértéket.
    - **Ütemezési időszak** – 7-et *választ*.

1. A következő feltételek is érvényesek:

    - Az aktuális dátum 2022. február 1.
    - Az aktuális aktuális mennyiség 20.

1. Az aktuális dátumra (2022. február 1.) egy 3-as ütemezett igénymennyiséget küld el a készlet láthatósága érdekében. Az tervezett készletmennyiség tehát 17 lesz. A következő táblázat bemutatja az eredményt.

    | Dátum | Aktuális készlet | Ütemezett ellátás | Ütemezett igény | Tervezetten kivetve | Ígérethez rendelkezésre áll |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 17 |
    | 2022-02-02 | 20 | | | 17 | 17 |
    | 2022-02-03 | 20 | | | 17 | 17 |
    | 2022-02-04 | 20 | | | 17 | 17 |
    | 2022-02-05 | 20 | | | 17 | 17 |
    | 2022-02-06 | 20 | | | 17 | 17 |
    | 2022-02-07 | 20 | | | 17 | 17 |

1. Az aktuális dátumon (2022. február 1.) benyújt egy 10-es készletmennyiséget 2022. február 3-ra. A következő táblázat bemutatja az eredményt.

    | Dátum | Aktuális készlet | Ütemezett ellátás | Ütemezett igény | Tervezetten kivetve | Ígérethez rendelkezésre áll |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 17 |
    | 2022-02-02 | 20 | | | 17 | 17 |
    | 2022-02-03 | 20 | 10 | | 27 | 27 |
    | 2022-02-04 | 20 | | | 27 | 27 |
    | 2022-02-05 | 20 | | | 27 | 27 |
    | 2022-02-06 | 20 | | | 27 | 27 |
    | 2022-02-07 | 20 | | | 27 | 27 |

1. Az aktuális dátumon (2022. február 1.) benyújtja a következő ütemezett mennyiségi módosításokat:

    - 2022. február 4-15-ei igénymennyiség
    - 2022. február 5-1-jén szállítandó mennyiség
    - 3. ellátási mennyiség 2022. február 6-ra

    A következő táblázat bemutatja az eredményt.

    | Dátum | Aktuális készlet | Ütemezett ellátás | Ütemezett igény | Tervezetten kivetve | Ígérethez rendelkezésre áll |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 12 |
    | 2022-02-02 | 20 | | | 17 | 12 |
    | 2022-02-03 | 20 | 10 | | 27 | 12 |
    | 2022-02-04 | 20 | | 15 | 12 | 12 |
    | 2022-02-05 | 20 | 1 | | 13 | 13 |
    | 2022-02-06 | 20 | 3 | | 16 | 16 |
    | 2022-02-07 | 20 | | | 16 | 16 |

1. Az aktuális dátumon (2022. február 1.) az ütemezett 3 igénymennyiség lesz szállítva. Ennek megfelelően a változtatást véglegesnek kell lennie, hogy az tükröződni tudja a tényleges aktuális készletben. A módosítás véglegesítésére olyan készletváltozási eseményt kell beküldni, amely kimenő mennyisége 3. Ezt követően az ütemezett változtatás visszaállítható egy -3 kimenő mennyiséget leadó, tényleges készlet változási ütemezésének küldésvel. A következő táblázat bemutatja az eredményt.

    | Dátum | Aktuális készlet | Ütemezett ellátás | Ütemezett igény | Tervezetten kivetve | Ígérethez rendelkezésre áll |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 17 | | 0 | 17 | 12 |
    | 2022-02-02 | 17 | | | 17 | 12 |
    | 2022-02-03 | 17 | 10 | | 27 | 12 |
    | 2022-02-04 | 17 | | 15 | 12 | 12 |
    | 2022-02-05 | 17 | 1 | | 13 | 13 |
    | 2022-02-06 | 17 | 3 | | 16 | 16 |
    | 2022-02-07 | 17 | | | 16 | 16 |

1. A következő napon (2022. február 2.) az ütemezési időszak egy nappal előretol. A következő táblázat bemutatja az eredményt.

    | Dátum | Aktuális készlet | Ütemezett ellátás | Ütemezett igény | Tervezetten kivetve | Ígérethez rendelkezésre áll |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-02 | 17 | | | 17 | 12 |
    | 2022-02-03 | 17 | 10 | | 27 | 12 |
    | 2022-02-04 | 17 | | 15 | 12 | 12 |
    | 2022-02-05 | 17 | 1 | | 13 | 13 |
    | 2022-02-06 | 17 | 3 | | 16 | 16 |
    | 2022-02-07 | 17 | | | 16 | 16 |
    | 2022-02-08 | 17 | | | 16 | 16 |

1. Két nappal később (2022. február 4.) azonban a február 3-án beütemezett 10 mennyiség még nem érkezett meg. A következő táblázat bemutatja az eredményt.

    | Dátum | Aktuális készlet | Ütemezett ellátás | Ütemezett igény | Tervezetten kivetve | Ígérethez rendelkezésre áll |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-04 | 17 | | 15 | 2 | 2 |
    | 2022-02-05 | 17 | 1 | | 3 | 3 |
    | 2022-02-06 | 17 | 3 | | 6 | 6 |
    | 2022-02-07 | 17 | | | 6 | 6 |
    | 2022-02-08 | 17 | | | 6 | 6 |
    | 2022-02-09 | 17 | | | 6 | 6 |
    | 2022-02-10 | 17 | | | 6 | 6 |

    Amint látható, az ütemezett (de még nem vállalt) aktuális készletváltozások nincsenek hatással a tényleges aktuális készletre.

## <a name="submit-change-schedules-change-events-and-atp-queries-through-the-api"></a><a name="api-urls"></a> Módosítási ütemezések, események és az ATP-lekérdezések elküldése az API-n keresztül

A következő ALKALMAZÁSprogramozási felület (API) URL-címekkel küldheti el az elérhető változási ütemezéseket, az eseményeket és a lekérdezéseket.

| Elérési út | Metódus | Leírás |
| --- | --- | --- |
| `/api/environment/{environmentId}/onhand/changeschedule` | `POST` | Egyetlen ütemezett, időpontban ütemezett módosítás létrehozása. |
| `/api/environment/{environmentId}/onhand/changeschedule/bulk` | `POST` | Több ütemezett, időpontban történő módosítás létrehozása. |
| `/api/environment/{environmentId}/onhand` | `POST` | Hozzon létre egy esemény az esethez való módosítási eseményt. |
| `/api/environment/{environmentId}/onhand/bulk` | `POST` | Több módosítási esemény létrehozása |
| `/api/environment/{environmentId}/onhand/indexquery` | `POST` | Lekérdezés a metódus `POST` használatával. |
| `/api/environment/{environmentId}/onhand` | `GET` | Lekérdezés a metódus `GET` használatával. |
| `/api/environment/{environmentId}/onhand/exactquery` | `POST` | Pontos lekérdezés a metódus `POST` használatával. |

A további tudnivalókat lásd [a Készlet láthatósága nyilvános API-kban](inventory-visibility-api.md).

### <a name="create-one-on-hand-change-schedule"></a>Egy,akkreta szerinti módosítási ütemezés létrehozása

Az aktuális készletre vonatkozó módosítási ütemezés úgy jön létre, hogy a rendszer elküldi a kérést a `POST` készlet láthatósága szolgáltatás megfelelő URL-címéhez (lásd [a Módosítási ütemezések elküldése, az események módosítása és az ATP-lekérdezések elküldése az API](#api-urls) szakaszon keresztül). Tömeges kéréseket is küldhet.

Aktuális módosítási ütemezést csak akkor lehet létrehozni, ha az ütemezett dátum az aktuális dátum és az aktuális ütemezési időszak vége között van. A dátum-idő formátumnak az év *és a hónap* formátumának kell lennie (**például 2022-02-01**). Az időformátumnak csak a mai napig kell pontosnak lennie.

Ez az API egyetlen, az elérhető változás ütemezését hozza létre.

```txt
Path:
    /api/environment/{environmentId}/onhand/changeschedule
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string, # optional
        dimensions: {
            [key:string]: string,
        },
        quantitiesByDate: {
            [datetime:datetime]: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
    }
```

A következő példa a `dimensionDataSource` nélküli törzstartalom mintáját mutatja.

```json
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    },
    "quantitiesByDate":
    {
        "2022-02-01": // today
        {
            "pos":{
                "inbound": 10
            }
        }
    }
}
```

### <a name="create-multiple-on-hand-change-schedules"></a>Több, az eszköz által használt módosítási ütemezés létrehozása

Ez az API egyszerre több rekordot is létrehozhat. Az API és az egyeseményes API `Path` között az és az értékek az eltérések`Body`. Ehhez az API-hoz a `Body` egy rekordtömböt biztosít. A rekordok maximális száma 512. A tömegesen ütemezett, az elérhető módosítási ütemezés API tehát egyszerre legfeljebb 512 ütemezett módosítást támogathat.

```txt
Path:
    /api/environment/{environmentId}/onhand/changeschedule/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string,
            dimensions: {
                [key:string]: string,
            },
            quantityDataSource: string, # optional
            quantitiesByDate: {
                [datetime:datetime]: {
                    [dataSourceName:string]: {
                        [key:string]: number,
                    },
                },
            },
        },
        ...
    ]
```

A következő példa a törzs tartalmának mintáját mutatja.

```json
[
    {
        "id": "id-bike-0001",
        "organizationId": "usmf",
        "productId": "Bike",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId&quot;: &quot;Small"
        },
        "quantitiesByDate":
        {
            "2022-02-01": // today
            {
                "pos":{
                    "inbound": 10
                }
            }
        }
    },
    {
        "id": "id-car-0002",
        "organizationId": "usmf",
        "productId": "Car",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId&quot;: &quot;Small"
        },
        "quantitiesByDate":
        {
            "2022-02-05":
            {
                "pos":{
                    "outbound": 10
                }
            }
        }
    }
]
```

### <a name="create-on-hand-change-events"></a>Kézben lévő változtatási események létrehozása

Az aktuális készlet módosítási eseményei úgy történnek, hogy a rendszer egy kérést küld el a `POST` készlet láthatósága szolgáltatás megfelelő URL-címére (lásd [a Módosítási ütemezések elküldése, az események módosítása és az ATP-lekérdezések elküldése az API](#api-urls) szakaszon keresztül). Tömeges kéréseket is küldhet.

> [!NOTE]
> Az aktuális készlet módosítási eseményei nem egyediek az "ATP" funkciókban, de a készlet láthatósági API-jának részei. Ez a példa azért szerepel a példában, mert az "ATP" (mennyiség) munkához kapcsolódó események fontosak. Az elérhető módosítási események hasonlítanak az elérhető foglalások módosítási eseményeire, de az eseményüzeneteket más API-címre kell küldeni, `quantities``quantityByDate` és az eseményeket nem az üzenet törzsében kell használni. A készlet láthatósági API-ja és az aktuális készlet láthatósága API [egyéb szolgáltatásaival kapcsolatos további tudnivalókat lásd a Készlet láthatósága nyilvános API-kban](inventory-visibility-api.md#create-one-onhand-change-event).

A következő példa egy olyan kérés szöveg törzsét mutatja be, amely egyetlen, az oldalon található változási eseményt tartalmaz.

```json
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "SizeId": "Big",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 10.0
        }
    }
}
```

## <a name="query-the-scheduled-on-hand-changes-and-atp-results"></a>Az ütemezett rendelkezésre álló mennyiség változásainak és az "ATP" eredményeknek a lekérdezése

Az ütemezetten végrehajtott módosításokról és az "ATP" eredményekről úgy lehet lekérdezni, hogy egy kérést vagy egy kérést küld el a `POST``GET` megfelelő API-url-címnek ([lásd a Módosítási ütemezések elküldése, az események módosítása és az ATP-lekérdezések elküldése az API](#api-urls) szakaszon keresztül).

A kérésben állítsa igazra, `QueryATP`*ha* az ütemezett készletváltozások és az ATP-eredmények lekérdezésére van szükség.

- Ha a metódus használatával adja `GET` meg a kérést, állítsa be ezt a paramétert az URL-címben.
- Ha a kérést ezzel a módszerrel elküldése, `POST` állítsa be ezt a paramétert a kérelem törzsében.

> [!NOTE]
> Attól függetlenül, `returnNegative`*·* *hogy* igaz vagy hamis a paraméter a kérés törzsében, az eredmény negatív értékeket fog tartalmazni az ütemezett készletváltozások és az ATP-eredmények lekérdezése során. Ezeket a negatív értékeket fogja tartalmazni a program, mivel ha csak az igényrendelések vannak ütemezve, vagy ha a szállítási mennyiségek kisebbek, mint az igény mennyisége, az ütemezett készletváltozási mennyiségek negatívak lesznek. Ha nem szerepelnek negatív értékek, akkor az eredmény megfelelő lenne. Ezzel a beállítással [és a más típusú lekérdezések esetén való használatával kapcsolatos további tudnivalókat lásd a Készlet láthatósága nyilvános API-kban](inventory-visibility-api.md#query-with-post-method).

### <a name="query-by-using-the-post-method"></a>Lekérdezés a POST metódus használatával

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            siteId: string[],
            locationId: string[],
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

A következő példa bemutatja, hogyan lehet létrehozni egy indexlekérdezés törzsét, amely a metódus segítségével elküldhető a készlet láthatósága `POST` számára.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "SiteId": ["1"],
        "LocationId": ["11"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true
}
```

### <a name="query-by-using-the-get-method"></a>Lekérdezés a GET metódus használatával

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Get
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Query(Url Parameters):
    groupBy
    returnNegative
    [Filters]
```

A következő példa bemutatja, hogyan lehet kérésként létrehozni egy indexlekérdezés URL-címét`GET`.

```txt
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand?organizationId=usmf&productId=Bike&SiteId=1&LocationId=11&groupBy=ColorId,SizeId&returnNegative=true&QueryATP=true
```

A kérelem eredménye `GET` pontosan megegyezik az előző `POST` példában történt kérés eredményének hasonlóval.

### <a name="exact-query-by-using-the-post-method"></a>Pontos lekérdezés a POST metódus használatával

```txt
Path:
    /api/environment/{environmentId}/onhand/exactquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            dimensions: string[],
            values: string[][],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

A következő példa bemutatja, hogyan lehet létrehozni egy olyan pontos lekérdezéskérési törzset, amely a módszerrel a készlet láthatósága számára benyújtható`POST`.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "dimensions": ["SiteId", "LocationId"],
        "values": [
            ["1", "11"]
        ]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true
}
```

### <a name="query-result-example"></a>Példa a lekérdezés eredményére

Az előző lekérdezési példák bármelyike a következő választ hozhatja létre. Ebben a példában a rendszer a következő beállításokra van konfigurálva:

- **Az ATP számított mértéke:** *iv.onhand = pos.inbound – pos.outbound*
- **Ütemezési időszak:** *7*

Példa a válasz törzsére.

```json
[
    {
        "quantitiesByDate": {
            "2022-02-02T00:00:00": {
                "pos": {
                    "outbound": 5,
                    "inbound": 0,
                },
                "iv": {
                    "onhand": -5,
                },
            },
            "2022-02-06T00:00:00": {
                "pos": {
                    "inbound": 7,
                    "outbound": 0,
                },
                "iv": {
                    "onhand": 7,
                },
            }
        },
        "atpQuantities": {
            "2022-02-01T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-02T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-03T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-04T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-05T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-06T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            },
            "2022-02-07T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            }
        },
        "productId": "Bike ",
        "dimensions": {
            "ColorId": "Red",
            "SizeId": "Big",
            "siteid": "1",
            "locationid": "11"
        },
        "quantities": {
            "pos": {
                "inbound": 10.0,
                "outbound": 0,
            },
            "iv": {
                "onhand": 10.0,
            }
        }
    }
]
```
