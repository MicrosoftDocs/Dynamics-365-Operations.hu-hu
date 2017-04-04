---
title: "Szállításkezelő kalkulátorok"
description: "A szállításkezelő programok határozzák meg azt a logikát, amit a Szállításkezelő a szállítási díjak előállítására és feldolgozására használ."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TMSFreightBillType, TMSGenericEngine, TMSMileageEngine, TMSRateEngine, TMSTransitTimeEngine, TMSZoneEngine
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9db73514d71239d75dc63fcf6e9f45923b1272f4
ms.lasthandoff: 03/31/2017


---

# <a name="transportation-management-engines"></a>Szállításkezelő kalkulátorok

A szállításkezelő programok határozzák meg azt a logikát, amit a Szállításkezelő a szállítási díjak előállítására és feldolgozására használ. 

A szállításkezelő kalkulátor például a szállító szállítmányozási díjához hasonló feladatokat számolja ki. A kalkulátorrendszerrel a Microsoft Dynamics 365 for Operations adatai alapján a számítási stratégiákat futásidőben módosíthatja. A szállításkezelő kalkulátor egy adott szállítmányozó szerződéséhez kapcsolódó, beépülő modulhoz hasonlít.

## <a name="what-engines-are-available"></a>Mely motorok érhetők el?
A következő táblázat a Microsoft Dynamics 365 for Operations rendszerben elérhető szállításkezelő kalkulátorokat mutatja be.

| Szállításkezelő kalkulátor | Leírás                                                                                                                                                                                                                                                                                                                 |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Díjkalkulátor**                  | Díjakat számol.                                                                                                                                                                                                                                                                                                           |
| **Általános kalkulátor**               | A többi kalkulátor által használt egyszerű segédkalkulátor, például az arányosító kalkulátor, nem igényel adatot a Microsoft Dynamics 365 for Operations rendszertől. Az arányosító kalkulátorok a térfogathoz vagy a súlyhoz hasonló dimenziók felhasználásával csökkentik a jellemző megrendelések és sorok szállítási költségeit. |
| **Távolságkalkulátor**               | Kiszámolja a szállítási távolságot.                                                                                                                                                                                                                                                                                     |
| **Szállításiidő-kalkulátor**          | Kiszámolja a kezdő- és végállomás közötti út megtételéhez szükséges időt.                                                                                                                                                                                                                                       |
| **Zónakalkulátor**                  | Az aktuális cím alapján kiszámítja a zónát, valamint azoknak a zónáknak a számát, amelyeken az A és B cím közötti szállítás során áthalad.                                                                                                                                                                    |
| **Fuvarlevél típusa**            | Szabványosítja a fuvarszámlát és a fuvarlevél sorait, ezenkívül a fuvarlevél automatikus egyeztetésére is használható.                                                                                                                                                                                                                |

 
<a name="what-engines-must-be-configured-to-rate-a-shipment"></a>Mely kalkulátorokat kell konfigurálni egy szállítmány díjának kiszámításához?
---------------------------------------------------

Egy adott szállító szállítmányainak díjazásához több szállításkezelő kalkulátort kell konfigurálnia. A **Díjkalkulátor** kötelező, de a **Díjkalkulátor** támogatásához más szállításkezelő kalkulátorra is szükség lehet. Például a **Díjkalkulátor** segítségével rákereshet adatokra a **Távolságkalkulátor** részből a forrás és a cél közötti távolságon alapuló tarifa kiszámításához.

## <a name="whats-required-to-initialize-a-transportation-management-engine"></a>Mi szükséges egy szállításkezelő kalkulátor inicializálásához?
Annak érdekében, hogy a szállításkezelő kalkulátor a meghatározott módon működjön, be kell állítania az inicializálási adatokat. A beállítás a következő típusú adatokat tartalmazhatja:
-   Hivatkozás más szállításkezelő kalkulátorokra. További részletek e szakasz konfigurációs példájában.
-   A szállításkezelő kalkulátor által használt .NET típusú hivatkozások.
-   Egyszerű konfigurációs adatok.

Az inicializációs adatok beállításához a legtöbb esetben elég a szállításkezelő kalkulátor beállítási képernyőin a **Paraméterek** gombra kattintania. **A távolságkalkulátorra hivatkozó díjkalkulátor példája** A következő példa bemutatja, hogy milyen beállítás szükséges egy díjkalkulátor beállításához, amely a .NET kalkulátortípuson Microsoft.Dynamics.Ax.Tms.Bll.MileageRateEngine alapul, és egy távolságkalkulátoron alapszik.
| Paraméter             | Leírás                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *RateBaseAssigner*    | Az adott sémához a díjalap-hozzárendelés adatait értelmező .NET típus. A paraméter értéke szintaxisa áll két szegmensek határolja a függőleges sáv ()|). Az első szegmens a hozzárendelés típusát meghatározó összeállítási nevet tartalmazza. A második szegmens a hozzárendelési típus teljes elérési útvonalának nevét határozza meg. Ebbe beletartozik a típus névtere is. |
| *MileageEngineCode*   | A Microsoft Dynamics 365 for Operations adatbázisban a távolságkalkulátor rekordját azonosító távolságkalkulátor-kód.                                                                                                                                                                                                                                                             |
| *ApportionmentEngine* | A Microsoft Dynamics 365 for Operations adatbázisban az arányosító kalkulátort azonosító általános kalkulátorkód.                                                                                                                                                                                                                                                              |

 
<a name="how-is-metadata-used-in-transportation-management-engines"></a>Hogyan használják a szállításkezelő kalkulátorok a metaadatokat?
----------------------------------------------------------

A Dynamics 365 for Operations részben meghatározott adatokat használó szállításkezelő kalkulátorok más adatsémákat használhatnak. A szállításkezelő rendszer lehetővé teszi, hogy különböző szállításkezelő kalkulátorok ugyanazokat az általános, tényleges adatbázistáblákat használhassák. Annak érdekében, hogy a futási idő alatti kalkulátoradatok értelmezése megfelelő legyen, az adatbázis tábláihoz metaadatokat határozhat meg. Ezzel csökkenthetők egy új szállításkezelő kalkulátor felépítésének költségei, mivel az Operations rendszerben nincs szükség további tábla- és képernyőstruktúrákra.

## <a name="what-can-be-used-as-search-data-in-rate-calculations"></a>Mit lehet keresési adatként használni a díjszámításokhoz?
A Microsoft Dynamics 365 for Operations rendszerében történő díjszámításhoz használt adatokat a metaadat-konfiguráció szabályozza. Ha például irányítószámon alapuló díjakra szeretne keresni, a beállított metaadatnak irányítószámon alapuló keresési típusnak kell lennie.

## <a name="do-all-engine-configurations-require-metadata"></a>Minden kalkulátorkonfigurációnak szüksége van metaadatokra?
Nem. Nincs szükségük metaadatra azoknak a szállításkezelő kalkulátoroknak, amelyeket külső rendszerből származó díjkalkulációkhoz szükséges adatok beolvasására használnak. Az ezekhez szükséges díjadatok külső szállítmányozó rendszerekből érkezhetnek, amelyeket általában webszolgáltatással töltenek be. Például használhat olyan távolságkalkulátort, amely közvetlenül Bing térképekről tölti le az adatokat, így ehhez a kalkulátorhoz nincs szükség metaadatra.
| **Megjegyzés **                                                                                                                                                                                                                                                                                                                                                                     |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A Microsoft Dynamics 365 for Operations rendszeréhez tartozó szállításkezelő kalkulátorok alkalmazásról letöltött adatokra támaszkodnak. A külső rendszerekhez csatlakozó kalkulátorok nem részei az Operations rendszernek. Azonban a kalkulátoralapú bővítési modell lehetővé teszi, hogy a Microsoft Dynamics 365 for Operations Visual Studio Tools segítségével bővítményeket hozzon létre. |

## <a name="how-do-i-configure-metadata-for-a-transportation-management-engine"></a>Hogyan tudok a szállításkezelő kalkulátorhoz metaadatot konfigurálni?
A szállításkezelő kalkulátorok metaadatai a különböző kalkulátortípusokhoz különféleképpen vannak beállítva.

| Szállításkezelő kalkulátor               | Metaadat konfiguráció:                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Díjkalkulátor**                                | **Díjalap típusa** szükséges A díjalap típusa a díj alapadatainak és az alapdíj-hozzárendelés adatainak metaadatait tartalmazza. A díjalap metaadatainak szerkezetét a díjkalkulátor típusa határozza meg. A díjalap-hozzárendelés metaadatainak szerkezetét a díjkalkulátorhoz társított díjalap-hozzárendelő típusa határozza meg. Egy díjkalkulátor alapdíjtípusát a **Díjkalkulátor** oldalon és a **Díjnyilvántartás** képernyőn állíthatja be. |
| **Zónakalkulátor**                                | A metaadatokat közvetlenül a zóna alapadatainál kell beállítani.                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Szállításiidő-kalkulátor** és **Távolságkalkulátor** | A metaadatokat közvetlenül olvassa be a távolságkalkulátor konfigurációs beállítási képernyőjéről.                                                                                                                                                                                                                                                                                                                                                                                  |

  **Metaadat-példa egy díjkalkulátor esetében** A szállításkezelő kalkulátor számára azonosítani kell a kiindulási címet, a célállamot és a célországot vagy a célrégiót, valamint a szállítás kezdő- és végpontját. A fenti követelmények használatával a metaadatok a következő táblázat adataihoz hasonlóan néznének ki. A táblázat arról is tájékoztat, hogy milyen típusú bemenő adatokra van szükség.
-   Adja meg ezt az információt a **szállítás kezelése**&gt;**telepítő** meg a **minősítse az alaptípus** lap.

| Szekvencia | Név                          | Mezőtípus | Adattípus | Keresés típusa    | Kötelező |
|----------|-------------------------------|------------|-----------|----------------|-----------|
| 1        | Kiindulási irányítószám            | Hozzárendelés | Karakterlánc    | Irányítószám    | Kijelölve  |
| 2        | Célállam             | Hozzárendelés | Karakterlánc    | Állami          |           |
| 3        | Kezdőállomás irányítószáma | Hozzárendelés | Karakterlánc    | Irányítószám    | Kijelölve  |
| 4        | Célállomás irányítószáma   | Hozzárendelés | Karakterlánc    | Irányítószám    | Kijelölve  |
| 5        | Célország           | Hozzárendelés | Karakterlánc    | Ország/régió |           |




