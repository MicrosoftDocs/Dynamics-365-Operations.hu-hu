---
title: "Költségkezelési Power BI-tartalom"
description: "Ez a témakör azt ismerteti, mit tartalmaz a Költségkezelési Power BI-tartalom modul."
author: ShylaThompson
manager: AnnBe
ms.date: 03/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 88bbc54721f5da94dd811ef155e8d3bcf8c2b53c
ms.openlocfilehash: b06abae184d07cd3b914caf74bdb16a7803919af
ms.contentlocale: hu-hu
ms.lasthandoff: 05/09/2018

---

# <a name="cost-management-power-bi-content"></a>Költségkezelési Power BI-tartalom

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Áttekintés

A **Kezelési költség** Microsoft Power BI-tartalom készletkönyvelők, valamint a szervezeten belül a készletekért és a folyamatban lévő munkákért felelős vagy ez iránt érdeklődő, valamint elszámolóár-különbözetek elemzésével foglalkozó szakemberek számára készült.

> [!Note]
> A jelen témakörben bemutatott **Kezelési költség** Power BI tartalom a Dynamics 365 for Finance and Operations 8.0 verziójára vonatkozik.
> 
> A Power BI **költségkezelési** tartalmi csomag már elavult - az AppSource oldalon érhető el. Az értékcsökkenéssel kapcsolatos további tudnivalókat lásd: [Power BI tartalmi csomagok elérhetők az AppSource-on](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource).

Ez a Power BI-tartalom olyan kategorizált formátumot biztosít, amely segítséget nyújt a készletek teljesítményének figyelemmel kísérésében, és bemutatja a rajtuk átáramló költségeket. Ön vezetői betekintést nyerhet például a forgalom arányába, azon napok számába, amelyeken a készlet rendelkezésre áll, a pontosságba, a kívánt összesítési szinten (vállalat, cikk, cikkcsoport vagy telephely) elérhető „ABC-osztályozásba”. Az elérhető információk pénzügyi kimutatás részletes kiegészítéseként felhasználhatók.

A Power BI-tartalom a **CostObjectStatementCacheMonthly** összesített mérésre épül, amely elsődleges adatforrásként a **CostObjectStatementCache** táblát használja. Ezt a táblát az Adathalmaz-gyorsítótár keretrendszere kezeli. Alapértelmezés szerint a tábla 24 óránként frissül, de a frissítési gyakoriság módosítható, illetve az adatkészlet gyorsítótárának konfigurációjában engedélyezheti a kézi frissítést is. A kézi frissítések a **Költségadminisztráció** munkaterületen vagy a **Költségelemzés** munkaterületen futtathatók.

A **CostObjectStatementCache** tábla minden frissítése után a **CostObjectStatementCacheMonthly** összesített mérést frissíteni kell, mielőtt a Power BI megjelenítések adatai frissülnek.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése

A **Kezelési költség** Power BI-tartalom szerepel a **Költségadminisztráció** és a **Költségelemzés** munkaterületeken.

A **Költségadminisztráció** munkaterület a következő lapokat tartalmazza:

- **Áttekintés** – Ez a lap megjeleníti az alkalmazásadatokat.
- **Könyvelési készletállapot** – Ez a lap Power BI-tartalmat jelenít meg.
- **Gyártási könyvelés állapota** – Ez a lap Power BI-tartalmat jelenít meg.

A **Költségelemzés** munkaterület a következő lapokat tartalmazza:

- **Áttekintés** – Ez a lap megjeleníti az alkalmazásadatokat.
- **Készletkönyvelés elemzése** – Ez a lap Power BI-tartalmat jelenít meg.
- **Gyártási könyvelés elemzése** – Ez a lap Power BI-tartalmat jelenít meg.
- **Elszámolóár-különbözet elemzése** – Ez a lap Power BI-tartalmat jelenít meg.

## <a name="report-pages-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó jelentési oldalak

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

### <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

A **Kezelési költség** Power BI-tartalom jelentési oldalainak adatai a Microsoft Dynamics 365 for Finance and Operations rendszerből származnak. Ezek az adatok az entitástárban előkészített összesített mérések formájában jelennek meg - az entitástár egy elemzési célra optimalizált Microsoft SQL Server-adatbázis. További tudnivalókért lásd: [A Power BI integrációja az entitástárral](power-bi-integration-entity-store.md).

A következő objektumok a kulcsfontosságú összesítő mértékei a Power BI-tartalom alapjául szolgálnak.

| Objektum                          | Kulcs összesítő mértékek | Adatforrás a Finance and Operationsnél | Mező               |
|---------------------------------|----------------------------|----------------------------------------|---------------------|
| CostObjectStatementCacheMonthly | Összeg                     | CostObjectStatementCache               | Összeg              |
| CostObjectStatementCacheMonthly | Mennyiség                   | CostObjectStatementCache               | Mennyiség                 |
| CostInventoryAccountingKPIGoal  | AnnualInventoryTurn        | CostInventoryAccountingKPIGoal         | AnnualInventoryTurn |
| CostInventoryAccountingKPIGoal  | InventoryAccuracy          | CostInventoryAccountingKPIGoal         | InventoryAccuracy   |

Az alábbi táblázat bemutatja a legfontosabb számított mértékeket a Power BI-tartalomban.

| Méret                            | Számítás |
|------------------------------------|-------------|
| Nyitó egyenleg                  | Nyitó egyenleg = [Záró egyenleg]-[Nettó változás] |
| Nyitó egyenleg menny.             | Nyitó egyenleg menny. = [Záró egyenleg menny.]-[Nettó változás menny.] |
| Záró egyenleg                     | Záró egyenleg = (CALCULATE(SUM([Amount]), FILTER(ALL(FiscalCalendar) ,FiscalCalendar[MONTHSTARTDATE] \<= MAX(FiscalCalendar[MONTHSTARTDATE])))) |
| Záró egyenleg menny.                | Záró egyenleg menny. = CALCULATE(SUM([QTY]), FILTER(ALL(FiscalCalendar),FiscalCalendar[MONTHSTARTDATE] \<= MAX(FiscalCalendar[MONTHSTARTDATE]))) |
| Nettó változás                         | Nettó változás = SUM([AMOUNT]) |
| Nettó változás menny.                    | Nettó változás menny. = SUM([QTY]) |
| Készletforgalom aránya összegenként | Készletforgalom aránya összegenként = if(OR([Készlet átlagos egyenlege] \<= 0, [Értékesített vagy felhasznált készlet problémák] \>= 0), 0, ABS([Értékesített vagy felhasznált készlet problémák])/[Készlet átlagos egyenlege]) |
| Készlet átlagos egyenlege          | Készlet átlagos egyenlege = (([Záró egyenleg] + [Nyitó egyenleg]) / 2) |
| Napok száma, amióta a készlet rendelkezésre áll             | Napok száma, amióta a készlet rendelkezésre áll = 365 / CostObjectStatementEntries[Készletforgalom aránya összegenként] |
| Készlet pontossága                 | Készletpontosság összeg alapján = IF([Záró egyenleg] \<= 0, IF(OR([Készlet leltározott mennyisége] \<\> 0, [Záró egyenleg] \< 0), 0, 1), MAX(0, ([Záró egyenleg] - ABS([Készlet leltározott mennyisége]))/[Záró egyenleg])) |

Az alábbi táblázat megjeleníti azokat a fő dimenziókat, amelyek szűrőként szolgálnak az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.


|                         Entitás                          |             Példák az attribútumok              |
|---------------------------------------------------------|-------------------------------------------------|
|                        Termékek                         | Termékszám, Termék neve, Egység, Cikkcsoportok |
| Kategóriahierarchiák (Költségkezelői szerepkörhöz rendelve) |       Kategóriahierarchia, Kategória szintje        |
|                     Jogi személyek                      |               Jogi személyek nevei                |
|                    Pénzügyi naptárak                     |  Pénzügyi naptár, év, negyedév, időszak, hónap  |
|                          Telephely                           |        Azonosító, név, cím, állam, ország        |


