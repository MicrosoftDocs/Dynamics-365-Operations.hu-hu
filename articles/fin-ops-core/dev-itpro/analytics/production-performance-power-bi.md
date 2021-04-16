---
title: Termelési teljesítmény Power BI tartalom
description: Ez a témakör azt ismerteti, mit tartalmaz a Termelési teljesítmény Power BI tartalom modul.
author: AndersGirke
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProductionPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4118d8f5e147d27e1620d236dbe0e0bd40dc3068
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753064"
---
# <a name="production-performance-power-bi-content"></a>Termelési teljesítmény Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, mit tartalmaz a **Termelési teljesítmény** Microsoft Power BI-tartalom modul. Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

A **Termelési teljesítmény** Power BI-tartalom a szervezeten belül a termelésirányításért felelős vezetők vagy egyének számára hasznos.

A benne levő jelentések lehetővé teszik, hogy a Power BI nyomon kövesse a gyártási műveletek teljesítményét az időben történő végrehajtás, a minőség és a költség szem előtt tartásával. A jelentések termelési rendelések és kötegrendelések tranzakciós adatait használják, és egyaránt megjeleníti a vállalat egészére kiterjedő termelési mutatókat és a mutatók termékekre és erőforrásokra történő lebontását.

A Power BI-tartalom kiemeli a szervezet azon képességét, hogy időben és egészében teljesítse a termelést. A jövőbeli teljesítést a termelési tervek alapján vetíti előre. Az átfogó jelentések részletesen ismertetik a termelés okozta termékhibákat, valamint az erőforrások és a műveletek hibaarányait.

Ez a Power BI-tartalom lehetővé teszi a termelési eltérések elemzését is. A termelési eltérések számítása a becsült és a realizált költség közötti különbség formájában történik. A termelési különbözetek számítása a termelési rendelések vagy kötegelt rendelések **Befejezve** állapotba kerülnek.

A **Termelési teljesítmény** Power BI-tartalom a termelési rendelésekből és a kötegelt rendelésekből származó adatokat tartalmazza. A jelentések nem tartalmazzák a kanban termelésekkel kapcsolatos adatokat.

## <a name="accessing-the-power-bi-content"></a>A Power BI tartalom elérése
A **Termelési teljesítmény** Power BI-tartalom a **Termelési teljesítmény** oldalon látható (**Gyártásvezérlés** \> **Lekérdezések és jelentések** \> **Termelési teljesítmény elemzése** \> **Termelési teljesítmény**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mérőszámok, amelyek a Power BI tartalomban szerepelnek

A **Termelési teljesítmény** Power BI-tartalom jelentési oldalak készletét tartalmazza. Minden oldal több metrikát tartalmaz, amelyek diagramok, mozaikok, táblázatok formájában jeleníthetők meg.

Az alábbi táblázat tartalmazza a tartalomban szereplő megjelenítéseket.

| Jelentéslap                                | Diagramok | Mozaik |
|--------------------------------------------|--------|-------|
| Termelési teljesítmény                     | <ul><li>Termelési sorok száma dátum szerint</li><li>Termelések száma termék és cikkcsoport szerint</li><li>Tervezett termelések száma dátum szerint</li><li>A legalsó 10 termék időben és teljes egészében teljesítve</li></ul> | <ul><li>Összes rendelés</li><li>Időben és teljes egészében teljesítve százalékban kifejezve</li><li>Nem teljes százalékban kifejezve</li><li>Korán százalékban kifejezve</li><li>Késve százalékban kifejezve</li></ul> |
| Hibák termékek szerint                         | <ul><li>Hibás ráta (db/hó) dátum szerint</li><li>Hibás ráta (db/hó) termékenként és cikkcsoportonként</li><li>Előállított mennyiség dátum szerint</li><li>Első 10 termék tényleges arány szerint</li></ul> | <ul><li>Hibás ráta (db/hó)</li><li>Hibás mennyiség</li><li>Összes mennyiség</li></ul> |
| Hibatrend termékek szerint                   | Hibaarány (db/hó) az előállított mennyiség szerint | Hibaarány (db/hó) |
| Hibák erőforrások szerint                        | <ul><li>Hibás ráta (db/hó) dátum szerint</li><li>Hibaarány (db/hó) erőforrások és hely szerint</li><li>Hibás ráta (db/hó) művelet szerint</li><li>Első 10 erőforrás hibaarány szerint</li></ul> | Hibás mennyiség |
| Hibatrend erőforrás szerint                  | Hibaarány (db/hó) a feldolgozott mennyiség szerint | |
| Feladatrendeléses költségelszámolás termelési különbözetei | <ul><li>Termelési különbözet dátum és költségcsoport típusa szerint</li><li>Termelési különbözet hely és költségcsoport típusa szerint</li><li>Első 10, kedvezőtlen termelési különbözettel rendelkező termék</li><li>Első 10 kedvezőtlen termelési különbözet erőforrások szerint</li></ul> | <ul><li>Realizált költség</li><li>Termelési különbözet</li><li>Termelési különbözet százalékban kifejezve</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

A **Termelési teljesítmény** Power BI-tartalom jelentési oldalaihoz a következő adatokat használja a rendszer. Ezeket az adatokat az Entitástárban lebonyolított összesített mérések jelenítik meg. Az entitástár az analitikai célokra optimalizált Microsoft SQL Server adatbázisa. Az entitástárral kapcsolatos további tudnivalókért lásd: [Power BI integrálása entitástárral](power-bi-integration-entity-store.md).

A következő táblázat megjeleníti azokat a kulcsfontosságú összesítő mértékeket, amelyek a Power BI-tartalom alapjául szolgálnak.

| Entitás                   | Kulcs összesítő mértékek  | A Finance and Operations alkalmazások adatforrása | Mező              |
|--------------------------|-----------------------------|----------------------------------------|--------------------|
| CostCalculation          | CostAmount                  | ProdCalcTransExpanded                  | CostAmount         |
| CostCalculation          | CostMarkup                  | ProdCalcTransExpanded                  | CostMarkup         |
| CostCalculation          | ActualCostAmount            | ProdCalcTransExpanded                  | RealCostAmount     |
| CostCalculation          | RealCostAdjustment          | ProdCalcTransExpanded                  | RealCostAdjustment |
| RouteTransactions        | ErrorQuantity               | ProdRouteTransExpanded                 | QtyError           |
| RouteTransactions        | GoodQuantity                | ProdRouteTransExpanded                 | QtyGood            |
| ProductionOrder          | DaysDelayed                 | ProdTableExpanded                      | DaysDelayed        |
| ProductionOrder          | LeadTime                    | ProdTableExpanded                      | LeadTime           |
| ProductionOrder          | PlannedLeadTime             | ProdTableExpanded                      | PlannedLeadTime    |
| ProductionOrder          | ProductionOrderCount        | ProdTableExpanded                      |                    |
| CoproductCostCalculation | CoproductCostAmount         | PmfCoByProdCalcTransExpanded           | CostAmount         |
| CoproductCostCalculation | CoproductCostMarkup         | PmfCoByProdCalcTransExpanded           | CostMarkup         |
| CoproductCostCalculation | CoproductRealCostAdjustment | PmfCoByProdCalcTransExpanded           | RealCostAdjustment |
| CoproductCostCalculation | CoproductActualCostAmount   | PmfCoByProdCalcTransExpanded           | RealCostAmount     |

A következő táblázat azt mutatja, hogyan használjuk a fő összesített mértékeket számos számított mérték létrehozására a tartalom adathalmazában.

| Méret                  | A mérőszám kiszámításának módja |
|--------------------------|-------------------------------|
| Termelési különbözet százalékban kifejezve   | SUM('Termelési különbözet'\[Termelési különbözet\]) / SUM('Termelési különbözet'\[[Becsült költség\]]) |
| Összes tervezett rendelés       | COUNTROWS('Tervezett termelési rendelés') |
| Korán                    | COUNTROWS(FILTER('Tervezett termelési rendelés', 'Tervezett termelési rendelés'\[Ütemezett befejezési dátum\] \< 'Tervezett termelési rendelés'\[Igénylés dátuma\])) |
| Késve                     | COUNTROWS(FILTER('Tervezett termelési rendelés', 'Tervezett termelési rendelés'\[Ütemezett befejezési dátum\] \> 'Tervezett termelési rendelés'\[Igénylés dátuma\])) |
| Időben                  | COUNTROWS(FILTER('Tervezett termelési rendelés', 'Tervezett termelési rendelés'\[Ütemezett befejezési dátum\] = 'Tervezett termelési rendelés'\[Igénylés dátuma\])) |
| Időben százalékban kifejezve                | IF (Tervezett termelési rendelés'\[Időben\] \<\> 0, 'Tervezett termelési rendelés'\[Időben\], IF ('Tervezett termelési rendelés'\[Összes tervezett rendelés\] \<\> 0, 0, BLANK()) ) / 'Tervezett termelési rendelés'\[Összes tervezett rendelés\] |
| Befejezve                | COUNTROWS(FILTER ('Termelési rendelés', 'Termelési rendelés'\[RAF'ed van\] = IGAZ)) |
| Hibás ráta (db/hó)     | IF ('Termelési rendelés'\[Összmennyiség\] = 0, BLANK(), (SUM('Termelési rendelés'\[Hibás mennyiség\]) / 'Termelési rendelés'\[Összmennyiség\]) \* 1000000) |
| Késleltetett termelési arány  | 'Termelési rendelés'\[Késve \#\] / 'Termelési rendelés'\[Befejeződött\] |
| Korán és teljes egészében          | COUNTROWS (FILTER('Termelési rendelés', 'Termelési rendelés'\[Teljes\] = IGAZ & & 'Termelési rendelés'\[Korai\] = IGAZ)) |
| Korán \#                 | COUNTROWS(FILTER ('Termelési rendelés', 'Termelési rendelés'\[Korai\] = IGAZ)) |
| Korán százalékban kifejezve                  | IFERROR (IF('Termelési rendelés'\[Korai \#\] \<\> 0, 'Termelési rendelés'\[Korai \#\], IF ('Termelési rendelés'\[Összes rendelés\] = 0, BLANK(), 0)) / 'Termelési rendelés'\[Összes rendelés\], BLANK()) |
| Hiányos               | COUNTROWS (FILTER('Termelési rendelés', 'Termelési rendelés'\[Teljes\] = IGAZ & & 'Termelési rendelés'\[Korai\] = IGAZ)) |
| Nem teljes százalékban kifejezve             | IFERROR (IF('Termelési rendelés'\[Nem teljes\] \<\> 0, 'Termelési rendelés'\[Nem teljes\], IF ('Termelési rendelés'\[Összes rendelés\] = 0, BLANK(), 0)) / 'Termelési rendelés'\[Összes rendelés\], BLANK()) |
| Késleltetve van               | 'Termelési rendelés'\[RAF'ed van\] = IGAZ && 'Termelési rendelés'\[Késleltetett érték\] = 1 |
| Korai                 | 'Termelési rendelés'\[RAF'ed van\] = IGAZ && 'Termelési rendelés'\[Késés napjainak száma\] \< 0 |
| Teljes egészében               | 'Termelési rendelés'\[Hibátlan mennyiség\] \>= 'Termelési rendelés'\[Ütemezett mennyiség\] |
| RAF'ed van                | 'Termelési rendelés'\[Termelési állapot értéke\] = 5 \|\| 'Termelési rendelés'\[Termelési állapot értéke\] = 7 |
| Késve és teljes egészében           | COUNTROWS (FILTER('Termelési rendelés', 'Termelési rendelés'\[Teljes\] = IGAZ & & 'Termelési rendelés'\[Késik\] = IGAZ)) |
| Késve \#                  | COUNTROWS(FILTER ('Termelési rendelés', 'Termelési rendelés'\[Késik\] = IGAZ)) |
| Késve százalékban kifejezve                   | IFERROR (IF('Termelési rendelés'\[Késve \#\] \<\> 0, 'Termelési rendelés'\[Késve \#\], IF ('Termelési rendelés'\[Összes rendelés\] = 0, BLANK(), 0)) / 'Termelési rendelés'\[Összes rendelés\], BLANK()) |
| Időben és teljes egészében        | COUNTROWS (FILTER('Termelési rendelés', 'Termelési rendelés'\[Teljes\] = TRUE & & 'Termelési rendelés'\[Késik\] = FALSE & & 'Termelési rendelés'\[Korai\] = FALSE)) |
| Időben és teljes egészében teljesítve százalékban kifejezve      | IFERROR( IF('Termelési rendelés'\[Időben és teljes egészében\] \<\> 0, 'Termelési rendelés'\[Időben és teljes egészében\], IF ('Termelési rendelés'\[Befejeződött\] = 0, BLANK(), 0)) / 'Termelési rendelés'\[Befejeződött\], BLANK()) |
| Összes rendelés             | COUNTROWS('Termelési rendelés') |
| Összes mennyiség           | SUM('Termelési rendelés'\[Hibátlan mennyiség\]) + SUM('Termelési rendelés'\[Hibás mennyiség\]) |
| Hibaarány (db/hó)        | IF( 'Útvonal-tranzakciók'\[Feldolgozott mennyiség\] = 0, BLANK(), (SUM('Útvonal-tranzakciók'\[Hibás mennyiség\]) / 'Útvonal-tranzakciók\[Feldolgozott mennyiség\]) \* 1000000) |
| Vegyes hibaarány (db/hó) | IF( 'Útvonal-tranzakciók'\[Összes vegyes mennyiség\] = 0, BLANK(), (SUM('Útvonal-tranzakciók'\[Hibás mennyiség\]) / 'Útvonal-tranzakciók\[Összes vegyes mennyiség\]) \* 1000000) |
| Feldolgozott mennyiség       | SUM('Útvonal-tranzakciók'\[Hibátlan mennyiség\]) + SUM('Útvonal-tranzakciók'\[Hibás mennyiség\]) |
| Teljes vegyes mennyiség     | SUM('Termelési rendelés'\[Hibátlan mennyiség\]) + SUM('Útvonal-tranzakciók'\[Hibás mennyiség\]) |

Az alábbi táblázat megjeleníti azokat a fő dimenziókat, amelyek szűrőként szolgálnak az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.

| Entitás                    | Példák az attribútumok                                        |
|---------------------------|---------------------------------------------------------------|
| Készként történő jelentés dátuma | Befejezés (RAF) dátuma, a hónap és év eltolása                 |
| Befejezési dátum                | Befejezett hónap eltolása és hónap                                  |
| Igény dátuma          | Igénylési dátum hónap eltolása és igénylési dátum            |
| Útvonal-tranzakció dátuma    | Útvonal-tranzakció hónap eltolása és dátum                       |
| Telephelyek                     | Helyek azonosítója, a hely neve, állam és város                          |
| Entitások                  | Azonosító és név                                                   |
| Erőforrások                 | Erőforrás-azonosító, erőforrás neve, erőforrástípus és erőforráscsoport |
| Termékek                  | Termékszám, termék neve, cikkazonosító és cikkcsoport         |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]