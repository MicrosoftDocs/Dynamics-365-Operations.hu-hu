---
title: Szállításkezelő kalkulátorok
description: A szállításkezelő programok határozzák meg azt a logikát, amit a Szállításkezelő a szállítási díjak előállítására és feldolgozására használ.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSGenericEngine, TMSMileageEngine, TMSRateEngine, TMSTransitTimeEngine, TMSZoneEngine, TMSFreightBillTypeAssignment, TMSZoneMaster, TMSEngineParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4a49ed7a91ec9a1b89564d40bef38cc4ea45532
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669600"
---
# <a name="transportation-management-engines"></a>Szállításkezelő kalkulátorok

[!include [banner](../includes/banner.md)]

A szállításkezelő programok határozzák meg azt a logikát, amit a Szállításkezelő a szállítási díjak előállítására és feldolgozására használ. 

A szállításkezelő kalkulátor például a szállító szállítmányozási díjához hasonló feladatokat számolja ki. A kalkulátorrendszerrel a Supply Chain Management adatai alapján a számítási stratégiákat futásidőben módosíthatja. A szállításkezelő kalkulátor egy adott szállítmányozó szerződéséhez kapcsolódó, beépülő modulhoz hasonlít.

## <a name="what-engines-are-available"></a>Mely motorok érhetők el?
A következő táblázat az elérhető szállításkezelő kalkulátorokat mutatja be.

| Szállításkezelő kalkulátor | Leírás                                                                                                                                                                                                                                                                                                                 |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Díjkalkulátor**                  | Díjakat számol.                                                                                                                                                                                                                                                                                                           |
| **Általános kalkulátor**               | A többi kalkulátor által használt egyszerű segédkalkulátor, például az arányosító kalkulátor, nem igényel adatot a Supply Chain Management rendszertől. Az arányosító kalkulátorok a térfogathoz vagy a súlyhoz hasonló dimenziók felhasználásával csökkentik a jellemző megrendelések és sorok szállítási költségeit. |
| **Távolságkalkulátor**               | Kiszámolja a szállítási távolságot.                                                                                                                                                                                                                                                                                     |
| **Szállításiidő-kalkulátor**          | Kiszámolja a kezdő- és végállomás közötti út megtételéhez szükséges időt.                                                                                                                                                                                                                                       |
| **Zónakalkulátor**                  | Az aktuális cím alapján kiszámítja a zónát, valamint azoknak a zónáknak a számát, amelyeken az A és B cím közötti szállítás során áthalad.                                                                                                                                                                    |
| **Fuvarlevél típusa**            | Szabványosítja a fuvarszámlát és a fuvarlevél sorait, ezenkívül a fuvarlevél automatikus egyeztetésére is használható.                                                                                                                                                                                                                |


## <a name="what-engines-must-be-configured-to-rate-a-shipment"></a>Mely kalkulátorokat kell konfigurálni egy szállítmány díjának kiszámításához?

Egy adott szállító szállítmányainak díjazásához több szállításkezelő kalkulátort kell konfigurálnia. A **Díjkalkulátor** kötelező, de a **Díjkalkulátor** támogatásához más szállításkezelő kalkulátorra is szükség lehet. Például a **Díjkalkulátor** segítségével rákereshet adatokra a **Távolságkalkulátor** részből a forrás és a cél közötti távolságon alapuló tarifa kiszámításához.

## <a name="whats-required-to-initialize-a-transportation-management-engine"></a>Mi szükséges egy szállításkezelő kalkulátor inicializálásához?
Annak érdekében, hogy a szállításkezelő kalkulátor a meghatározott módon működjön, be kell állítania az inicializálási adatokat. A beállítás a következő típusú adatokat tartalmazhatja:
-   Hivatkozás más szállításkezelő kalkulátorokra. További részletek e szakasz konfigurációs példájában.
-   A szállításkezelő kalkulátor által használt .NET típusú hivatkozások.
-   Egyszerű konfigurációs adatok.

Az inicializációs adatok beállításához a legtöbb esetben elég a szállításkezelő kalkulátor beállítási képernyőin a **Paraméterek** gombra kattintania. **A távolságkalkulátorra hivatkozó díjkalkulátor példája** A következő példa bemutatja, hogy milyen beállítás szükséges egy díjkalkulátor beállításához, amely a .NET kalkulátortípuson Microsoft.Dynamics.Ax.Tms.Bll.MileageRateEngine alapul, és egy távolságkalkulátoron alapszik.

|          Paraméter           |                                                                                  Leírás                                                                                  |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <em>RateBaseAssigner</em>   | Az adott sémához a díjalap-hozzárendelés adatait értelmező .NET típus. A paraméterérték szintaxisa két függőleges vonallal (|) elválasztott szegmensből áll ( |
|  <em>MileageEngineCode</em>  |                       Az adatbázisban a távolságkalkulátor rekordját azonosító távolságkalkulátor-kód.                        |
| <em>ApportionmentEngine</em> |                        Az általános kalkulátor kódja, amely beazonosítja az arányosító kalkulátort az adatbázisban.                        |

## <a name="how-is-metadata-used-in-transportation-management-engines"></a>Hogyan használják a szállításkezelő kalkulátorok a metaadatokat?

A Supply Chain Management részben meghatározott adatokat használó szállításkezelő kalkulátorok más adatsémákat használhatnak. A szállításkezelő rendszer lehetővé teszi, hogy különböző szállításkezelő kalkulátorok ugyanazokat az általános, tényleges adatbázistáblákat használhassák. Annak érdekében, hogy a futási idő alatti kalkulátoradatok értelmezése megfelelő legyen, az adatbázis tábláihoz metaadatokat határozhat meg. Ezzel csökkenthetők egy új szállításkezelő kalkulátor felépítésének költségei, mivel az Operations rendszerben nincs szükség további tábla- és képernyőstruktúrákra.

## <a name="what-can-be-used-as-search-data-in-rate-calculations"></a>Mit lehet keresési adatként használni a díjszámításokhoz?
A díjszámításhoz használt adatokat a metaadat-konfiguráció szabályozza. Ha például irányítószámon alapuló díjakra szeretne keresni, a beállított metaadatnak irányítószámon alapuló keresési típusnak kell lennie.

## <a name="do-all-engine-configurations-require-metadata"></a>Minden kalkulátorkonfigurációnak szüksége van metaadatokra?
Nem. Nincs szükségük metaadatra azoknak a szállításkezelő kalkulátoroknak, amelyeket külső rendszerből származó díjkalkulációkhoz szükséges adatok beolvasására használnak. Az ezekhez szükséges díjadatok külső szállítmányozó rendszerekből érkezhetnek, amelyeket általában webszolgáltatással töltenek be. Például használhat olyan távolságkalkulátort, amely közvetlenül Bing térképekről tölti le az adatokat, így ehhez a kalkulátorhoz nincs szükség metaadatra.

| **Megjegyzés**                                                                                                                                                                                                                                                                                                                                                                     |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A Supply Chain Management rendszeréhez tartozó szállításkezelő kalkulátorok alkalmazásról letöltött adatokra támaszkodnak. A külső rendszerekhez csatlakozó kalkulátorok nem részei az Operations rendszernek. Azonban a kalkulátoralapú bővítési modell lehetővé teszi, hogy a Visual Studio Tools segítségével bővítményeket hozzon létre. |

## <a name="how-do-i-configure-metadata-for-a-transportation-management-engine"></a>Hogyan tudok a szállításkezelő kalkulátorhoz metaadatot konfigurálni?
A szállításkezelő kalkulátorok metaadatai a különböző kalkulátortípusokhoz különféleképpen vannak beállítva.

| Szállításkezelő kalkulátor               | Metaadat konfiguráció:                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Díjkalkulátor**                                | **Díjalap típusa** szükséges A díjalap típusa a díj alapadatainak és az alapdíj-hozzárendelés adatainak metaadatait tartalmazza. A díjalap metaadatainak szerkezetét a díjkalkulátor típusa határozza meg. A díjalap-hozzárendelés metaadatainak szerkezetét a díjkalkulátorhoz társított díjalap-hozzárendelő típusa határozza meg. Egy díjkalkulátor alapdíjtípusát a **Díjkalkulátor** oldalon és a **Díjnyilvántartás** képernyőn állíthatja be. |
| **Zónakalkulátor**                                | A metaadatokat közvetlenül a zóna alapadatainál kell beállítani.                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Szállításiidő-kalkulátor** és **Távolságkalkulátor** | A metaadatokat közvetlenül olvassa be a távolságkalkulátor konfigurációs beállítási képernyőjéről.                                                                                                                                                                                                                                                                                                                                                                                  |

  **Metaadat-példa egy díjkalkulátor esetében** A szállításkezelő kalkulátor számára azonosítani kell a kiindulási címet, a célállamot és a célországot vagy a célrégiót, valamint a szállítás kezdő- és végpontját. A fenti követelmények használatával a metaadatok a következő táblázat adataihoz hasonlóan néznének ki. A táblázat arról is tájékoztat, hogy milyen típusú bemenő adatokra van szükség.
-   Határozza meg ezeket az információkat a **Szállításkezelés** &gt; **Beállítás** pontnál a **Díjalap típusa** lapon.

| Szekvencia | Név                          | Mezőtípus | Adattípus | Keresés típusa    | Kötelező |
|----------|-------------------------------|------------|-----------|----------------|-----------|
| 1        | Kiindulási irányítószám            | Hozzárendelés | Karakterlánc    | Irányítószám    | Kijelölve  |
| 2        | Célállam             | Hozzárendelés | Karakterlánc    | Állami          |           |
| 3        | Kezdőállomás irányítószáma | Hozzárendelés | Karakterlánc    | Irányítószám    | Kijelölve  |
| 4        | Célállomás irányítószáma   | Hozzárendelés | Karakterlánc    | Irányítószám    | Kiválasztott  |
| 5        | Célország           | Hozzárendelés | Sztring    | Ország/régió |           |

### <a name="whitepaper"></a>Tanulmány

További tudnivalókért töltse le a következő (az AX 2012 támogatásához készült, de még a Dynamics 365 Supply Chain Management esetében is érvényes) tanulmányt

- [Szállításkezelési motorok](https://download.microsoft.com/download/e/0/9/e0957665-c12f-43c7-94c0-611cc49d7d61/TransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]