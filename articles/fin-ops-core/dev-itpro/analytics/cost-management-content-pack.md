---
title: Költségkezelés Power BI tartalom
description: Ez a témakör ismerteti, hogy mi szerepel a Költséggazdálkodási tartalomban Power BI.
author: JennySong-SH
ms.date: 03/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.industry: Manufacturing
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, CostObjectWithLowestAccuracy, CostVarianceChart, CostObjectWithLowestTurn
ms.openlocfilehash: 11b414c8c352ac0a6307584ef14bcc13122f4573
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267348"
---
# <a name="cost-management-power-bi-content"></a>Költségkezelés Power BI tartalom

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Áttekintés

A **Költségkezelés** Microsoft Power BI-tartalom készletkönyvelők, valamint a szervezeten belül a készletekért és a folyamatban lévő munkákért felelős vagy ez iránt érdeklődő, valamint elszámolóár-különbözetek elemzésével foglalkozó szakemberek számára készült.

Ez a Power BI-tartalom olyan kategorizált formátumot biztosít, amely segítséget nyújt a készletek teljesítményének figyelemmel kísérésében, és bemutatja a rajtuk átáramló költségeket. Ön vezetői betekintést nyerhet például a forgalom arányába, azon napok számába, amelyeken a készlet rendelkezésre áll, a pontosságba, a kívánt összesítési szinten (vállalat, cikk, cikkcsoport vagy telephely) elérhető „ABC-osztályozásba”. Az elérhető információk pénzügyi kimutatás részletes kiegészítéseként felhasználhatók.

A Power BI-tartalom a **CostObjectStatementCacheMonthly** összesített mérésre épül, amely elsődleges adatforrásként a **CostObjectStatementCache** táblát használja. Ezt a táblát az Adathalmaz-gyorsítótár keretrendszere kezeli. Alapértelmezés szerint a tábla 24 óránként frissül, de a frissítési gyakoriság módosítható, illetve az adatkészlet gyorsítótárának konfigurációjában engedélyezheti a kézi frissítést is. A kézi frissítések a **Költségadminisztráció** munkaterületen vagy a **Költségelemzés** munkaterületen futtathatók.

A **CostObjectStatementCache** tábla minden frissítése után a **CostObjectStatementCacheMonthly** összesített mérést frissíteni kell, mielőtt a Power BI megjelenítések adatai frissülnek.

## <a name="accessing-the-power-bi-content"></a>A Power BI tartalom elérése

A **Költségkezelés** Power BI-tartalom szerepel a **Költségadminisztráció** és a **Költségelemzés** munkaterületeken.

A **Költségadminisztráció** munkaterület a következő lapokat tartalmazza:

- **Áttekintés** – Ez a lap megjeleníti az alkalmazásadatokat.
- **Készletkönyvelés állapota** – Ez a lap Power BI-tartalmat jelenít meg.
- **Gyártási könyvelés állapota** – Ez a lap Power BI-tartalmat jelenít meg.

A **Költségelemzés** munkaterület a következő lapokat tartalmazza:

- **Áttekintés** – Ez a lap megjeleníti az alkalmazásadatokat.
- **Készletkönyvelés elemzése** – Ez a lap Power BI-tartalmat jelenít meg.
- **Gyártási könyvelés elemzése** – Ez a lap Power BI-tartalmat jelenít meg.
- **Elszámolóár-különbözet elemzése** – Ez a lap Power BI-tartalmat jelenít meg.

## <a name="report-pages-that-are-included-in-the-power-bi-content"></a>Jelentési oldalak, amelyek a Power BI-tartalomban szerepelnek

A **Költségkezelés** Power BI-tartalom jelentési oldalakat is tartalmaz, amelyben mutatók sora található meg. Ezek a metrikák mozaikok, táblázatok és diagramok formájában jelennek meg. 

Az alábbi táblázatokban megtalálható a **Költségkezelés** Power BI-tartalom megjelenítési formáinak áttekintése.

### <a name="inventory-accounting-status"></a>Készletkönyvelés állapota

| Jelentéslap                               | Megjelenítés                                   |
|-------------------------------------------|-------------------------------------------------|
| Készlet – áttekintés                        | Nyitó egyenleg                               |
|                                           | Nettó változás                                      |
|                                           | Nettó változás %                                    |
|                                           | Záró egyenleg                                  |
|                                           | Készlet pontossága                              |
|                                           | Készletforgalom aránya                        |
|                                           | Napok száma, amióta a készlet rendelkezésre áll                          |
|                                           | Aktív termék az időszakban                        |
|                                           | Aktív költségobjektumok az időszakban                   |
|                                           | Egyenleg cikkcsoportonként                           |
|                                           | Egyenleg telephelyenként                                 |
|                                           | Kimutatás kategóriánként                           |
|                                           | Nettó változás negyedévenként                           |
| Készlet áttekintése telephelyenként és cikkcsoportonként | Készlet pontossága telephely szerint                      |
|                                           | Készletforgalom aránya telephelyenként                |
|                                           | Készlet záróegyenlege telephelyenként                |
|                                           | Készletpontosság cikkcsoportonként                |
|                                           | Készletforgalom aránya cikkcsoportonként          |
|                                           | Készlet záróegyenlege telephelyenként és cikkcsoportonként |
| Készletkimutatás                       | Készletkimutatás                             |
| Készletkimutatás telephelyenként               | Készletkimutatás telephelyenként                     |
| Készletkimutatás termékhierarchia szerint  | Készletkimutatás                             |
| Készletkimutatás termékhierarchia szerint  | Készletkimutatás telephelyenként                     |

### <a name="manufacturing-accounting-status"></a>Gyártási könyvelés állapota

| Jelentéslap                | Megjelenítés                       |
|----------------------------|-------------------------------------|
| Folyó évi befejezetlen termelés áttekintése           | Nyitó egyenleg                   |
|                            | Nettó változás                          |
|                            | Nettó változás %                        |
|                            | Záró egyenleg                      |
|                            | Befejezetlen termelés forgalmi aránya                  |
|                            | Napok száma - rendelkezésre befejezetlen termelés                    |
|                            | Aktív költségobjektum az időszakban        |
|                            | Nettó változása erőforráscsoportonként        |
|                            | Egyenleg telephelyenként                     |
|                            | Kimutatás kategóriánként               |
|                            | Nettó változás negyedévenként               |
| folyamatban lévő munka kimutatás              | Nyitó egyenleg                   |
|                            | Záró egyenleg                      |
|                            | Befejezetlen termelési kimutatás kategóriánként           |
| Befejezetlen termelési kimutatás telephelyenként      | Nyitó egyenleg                   |
|                            | Záró egyenleg                      |
|                            | Befejezetlen termelési kimutatás kategóriánként és telephelyenként  |
| Befejezetlen termelési kimutatás hierarchiánként | Nyitó egyenleg                   |
|                            | Záró egyenleg                      |
|                            | Befejezetlen termelési kimutatás kategóriahierarchiánként |

### <a name="inventory-accounting-analysis"></a>Készletkönyvelés elemzése

| Jelentéslap        | Megjelenítés                                                                |
|--------------------|------------------------------------------------------------------------------|
| Készlet részletei  | A legjobb 10 erőforrás záróegyenleg szerint                                           |
|                    | A legjobb 10 erőforrás nettó változásnövekedés szerint                                      |
|                    | A legjobb 10 erőforrás nettó változáscsökkenés szerint                                      |
|                    | A legjobb 10 erőforrás készletforgalom aránya szerint                                 |
|                    | Erőforrások alacsony készletforgalmi arány és küszöbértéket meghaladó záróegyenleg szerint |
|                    | Legjobb 10 erőforrás alacsony pontosság szerint                                             |
| ABC-osztályozás | Készlet záróegyenlege                                                     |
|                    | Felhasznált anyagok                                                            |
|                    | Eladva (ELÁBÉ)                                                                  |
| Készlettrendek   | Készlet záróegyenlege                                                     |
|                    | Készlet nettó változása                                                         |
|                    | Készletforgalom aránya                                                     |
|                    | Készlet pontossága                                                           |

### <a name="manufacturing-accounting-analysis"></a>Gyártási könyvelés elemzése

| Jelentéslap | Megjelenítés      |
|-------------|--------------------|
| Befejezetlen termelési trendek  | Befejezetlen termelés záró egyenlege |
|             | Befejezetlen termelés nettó változása     |
|             | Befejezetlen termelés forgalmi aránya |

### <a name="std-cost-variance-analysis"></a>Elszámolóár-különbözet elemzése

| Jelentéslap                             | Megjelenítés                                        |
|-----------------------------------------|------------------------------------------------------|
| Folyó évi beszerzési árkülönbözet (elszámolóár) | Beszerzett egyenleg                                     |
|                                         | Beszerzési árkülönbözet                              |
|                                         | Beszerzési árkülönbözeti arány                        |
|                                         | Eltérés cikkcsoportonként                               |
|                                         | Eltérés telephelyenként                                     |
|                                         | Beszerzési ár negyedévenként                            |
|                                         | Beszerzési ár negyedévenként és cikkcsoportonként             |
|                                         | A legjobb 10 erőforrás kedvezőtlen beszerzésiár-arány szerint |
|                                         | A legjobb 10 erőforrás kedvező beszerzésiár-arány szerint   |
| Folyó évi termelési különbözet (elszámolóár)     | Gyártási költség                                    |
|                                         | Termelési különbözet                                  |
|                                         | Termelési különbözeti arány                            |
|                                         | Eltérés cikkcsoportonként                               |
|                                         | Eltérés telephelyenként                                     |
|                                         | Termelési különbözet negyedévenként                       |
|                                         | Termelési különbözet negyedévenként és eltéréstípus szerint     |
|                                         | A legjobb 10 erőforrás kedvezőtlen termelési különbözet szerint  |
|                                         | A legjobb 10 erőforrás kedvező termelési különbözet szerint    |

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

Az alkalmazás adatai segítségével kitölthetők a jelentési oldalak a **Költségkezelés** Power BI-tartalomban. Ezek az adatok az entitástárban előkészített összesített mérések formájában jelennek meg - az entitástár egy elemzési célra optimalizált Microsoft SQL Server-adatbázis. További tudnivalókért lásd: [Power BI integrációja az entitástárral](power-bi-integration-entity-store.md).

A következő objektumok kulcsfontosságú összesítő mértékei a Power BI-tartalom alapjául szolgálnak.

| Objektum                          | Kulcs összesítő mértékek | A pénzügy és a műveletek adatforrása | Mező               |
|---------------------------------|----------------------------|----------------------------------------|---------------------|
| CostObjectStatementCacheMonthly | Összeg                     | CostObjectStatementCache               | Összeg              |
| CostObjectStatementCacheMonthly | Mennyiség                   | CostObjectStatementCache               | Mennyiség                 |
| CostInventoryAccountingKPIGoal  | AnnualInventoryTurn        | CostInventoryAccountingKPIGoal         | AnnualInventoryTurn |
| CostInventoryAccountingKPIGoal  | InventoryAccuracy          | CostInventoryAccountingKPIGoal         | InventoryAccuracy   |

Az alábbi táblázat bemutatja a legfontosabb számított mértékeket a Power BI-tartalomban.

| Méret                            | Számítás |
|------------------------------------|-------------|
| Nyitó egyenleg                  | Nyitó egyenleg = \[[Záró egyenleg\]-\[Nettó változás\]] |
| Nyitó egyenleg menny.             | Nyitó egyenleg menny. = \[Záró egyenleg menny.\]-\[Nettó változás menny.\] |
| Záró egyenleg                     | Záró egyenleg = (CALCULATE(SUM(\[Amount\]), FILTER(ALL(FiscalCalendar) ,FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\])))) |
| Záró egyenleg menny.                | Záró egyenleg menny. = CALCULATE(SUM(\[QTY\]), FILTER(ALL(FiscalCalendar),FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\]))) |
| Nettó változás                         | Nettó változás = SUM(\[AMOUNT\]) |
| Nettó változás menny.                    | Nettó változás menny. = SUM(\[QTY\]) |
| Készletforgalom aránya összegenként | Készletforgalom aránya összegenként = if(\[OR(Készlet átlagos egyenlege\] \<= 0, \[Inventory sold or consumed issues\] \>= 0), 0, ABS(\[Értékesített vagy felhasznált készlet problémák\])/\[Készlet átlagos egyenlege\]) |
| Készlet átlagos egyenlege          | Készlet átlagos egyenlege = ((\[Záró egyenleg\] + \[Nyitó egyenleg\]) / 2) |
| Napok száma, amióta a készlet rendelkezésre áll             | Napok száma, amióta a készlet rendelkezésre áll = 365 / CostObjectStatementEntries\[Készletforgalom aránya összegenként\] |
| Készlet pontossága                 | Készlet pontossága összeg = IF (\[záró egyenleg\] \<= 0, IF(OR(\[Inventory counted amount\] \<\> 0, \[záró egyenleg\] \< 0), 0, 1), MAX(0, (\[záró egyenleg\] -ABS (\[készletként számított összeg\]))/\[záró egyenleg\])) |

Az alábbi táblázat megjeleníti azokat a fő dimenziókat, amelyek szűrőként szolgálnak az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.


| Entitás                                                  | Példák az attribútumok                          |
|---------------------------------------------------------|-------------------------------------------------|
| Termékek                                                | Termékszám, Termék neve, Egység, Cikkcsoportok |
| Kategóriahierarchiák (Költségkezelői szerepkörhöz rendelve) | Kategóriahierarchia, Kategória szintje              |
| Jogi személyek                                          | Jogi személyek nevei                              |
| Pénzügyi naptárak                                        | Pénzügyi naptár, év, negyedév, időszak, hónap   |
| Telephely                                                    | Azonosító, név, cím, állam, ország               |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

