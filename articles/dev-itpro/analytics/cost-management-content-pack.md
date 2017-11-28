---
title: "Költségkezelési Power BI-tartalom"
description: "Ez a témakör azt ismerteti, mit tartalmaz a Költségkezelési Power BI-tartalom modul. Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f509852f15b9518d0a01be1f89d4f07c76caf341
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="cost-management-power-bi-content"></a>Költségkezelési Power BI-tartalom

[!include[banner](../includes/banner.md)]


Ez a témakör azt ismerteti, mit tartalmaz a Költségkezelési Power BI-tartalom modul. Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

# <a name="overview"></a>Áttekintés

A **Kezelési költség** Microsoft Power BI tartalom készletkönyvelőknek vagy a szervezet azon dolgozóinak szól, akik a készletért felelősek. A **Költségkezelés** Power BI-tartalom betekintést biztosít a vezetők számára a készletbe és a befejezetlen termelés készletébe, illetve az ezeken belüli, kategóriánkénti költségáramlásba időalapú lebontásban. Az információk pénzügyi kimutatás részletes kiegészítéseként felhasználhatók.

## <a name="key-measures"></a>Fő mérőszámok

+ Nyitó egyenleg
+ Záró egyenleg
+ Nettó változás
+ Nettó változás %-ban
+ Korosítási

## <a name="key-performance-indicators"></a>Fő teljesítménymutatók
+ Készletforgás
+ Készlet pontossága

A CostAggregatedCostStatementEntryEntity elsődleges adatforrása a CostStatementCache táblában található. Ezt a táblát az Adathalmaz-gyorsítótár keretrendszere kezeli. Alapértelmezés szerint a tábla 24 óránként frissül, de az adatgyorsítótár konfigurációjában engedélyezheti a kézi frissítést is. Ezután a **Költségkezelés** vagy a **Költségelemzés** munkaterületen végezhet kézi frissítést. A CostStatementCache frissítésének futtatása után a frissített adatok a webhelyen történő megtekintéséhez frissítenie kell az OData kapcsolatot a Power BI.com-on. Az eltérési (beszerzés, termelés) mérőszámok ebben a Power BI-tartalomban csak azon elemekre vonatkoznak, amelyek értékelése Normál elszámolóár szerint történik. A termelési eltérés számítása az aktív és a realizált költség közötti különbség formájában történik. A gyártási eltérés kiszámítására akkor kerül sor, amikor a termelési rendelés állapota **Befejezve** lesz. További információért az eltérési típusokkal és az egyes típusok kiszámítási módját illetően lásd: [Befejezett termelési rendelés eltéréseinek elemzése](https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése
A **költségkezelés** Power BI-tartalom elérhető a PowerBI.com webhelyről. A csatlakozással és a Microsoft Dynamics 365 for Finance and Operations-adatok betöltésével kapcsolatos további tudnivalókat lásd: [Power BI-tartalom elérése a PowerBI.com webhelyről](power-bi-home-page.md).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó metrikák
A tartalom jelentési oldalak készletét tartalmazza. Minden oldal több metrikát tartalmaz, amelyek diagramok, mozaikok, táblázatok formájában jeleníthetők meg. Az alábbi táblázatban a **Költségkezelés** Power BI-tartalom megjelenítési formáinak áttekintése található.

| Jelentéslap | Diagramok | Beosztások |
|---|---|---|
|Teljes készlet (alapértelmezés szerint az aktuális időszakra) |Pontosság |Készlet mérőszámai:<br>Készlet záróegyenlege<br>Készlet nettó változása<br>Készlet nettó változása %<br>|
| |Készletforgás | |
| |Készlet záró egyenlege erőforráscsoportonként | |
| |Készlet nettó változása 1. Kategórianév-szint és 2. Kategórianév-szint alapján| |
| |Beszerzési eltérések Erőforráscsoportonként és 3. Kategórianév-szint alapján | |
|Készlet telephelyenként (alapértelmezés szerint az aktuális időszakra) |Készlet záró egyenlege Telephely neve és Erőforráscsoport alapján | |
| |Készletforgás Telephely neve és Erőforráscsoport alapján | |
| |Készlet záró egyenlege Városonként és Erőforráscsoportonként | |
|Készlet erőforráscsoportonként (alapértelmezés szerint az aktuális időszakra) |Készlet mérőszámai | |
| |Készlet összegszerű pontossága erőforráscsoportonként | |
| |Készletforgás összegszerűen erőforráscsoportonként | |
|Készlet egy éves időszak szerint (alapértelmezetten folyó év vs előző év) |Készlet mérőszámai | |
| |Készlet teljesítménymutatói:<br>Készletforgás<br>Készlet pontossága | |
| |Készlet záró egyenlege Évenként és Erőforráscsoportonként | |
| |Beszerzési eltérések Évenként és 3. Kategórianév-szint alapján | |
|Készlet korosítás (alapértelmezés szerint a folyó évre) |Készlet korosítása Negyedévenként és Erőforrás-csoportonként | |
| |Készlet korosítása Negyedévenként és Telephelynevenként | |
|Teljes befejezetlen termelés (alapértelmezés szerint az aktuális időszakra) |Befejezetlen termelés nettó változása 1. Kategórianév-szint és 2. Kategórianév-szint alapján |Folyamatban lévő munka befejezetlen termelés mérőszámai:<br>Befejezetlen termelés záró egyenlege<br>Befejezetlen termelés nettó változása<br>Befejezetlen termelés nettó változása %<br> |
| |Termelési eltérések Erőforráscsoportonként és 3. Kategórianév-szint alapján | |
| |Befejezetlen termelés nettó változása Erőforráscsoportonként | |
|Befejezetlen termelés telephelyenként (alapértelmezés szerint az aktuális időszakra) |Folyamatban lévő munka befejezetlen termelés mérőszámai | |
| |Befejezetlen termelés nettó változása Telephelynevenként és 2. Kategórianév-szint alapján | |
| |Termelési eltérések Telephelynevenként és 3. Kategórianév-szint alapján | |

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A **Költségkezelés** Power BI-tartalom jelentési oldalainak feltöltésére a Finance and Operations adatai szolgálnak. Ezek az adatok az entitástárban előkészített összesített mérések formájában jelennek meg - az entitástár egy elemzési célra optimalizált Microsoft SQL-adatbázis. További tudnivalókért lásd: [Az entitástár és a Power BI integrációjának áttekintése](power-bi-integration-entity-store.md). A következő fő összesítő mértékek szolgálnak a tartalom alapjaként.

| Entitás            | Fő összesítő mérték | Adatforrás a Finance and Operationsnél | Mező             | Leírás                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Kimutatási bejegyzések | Nettó változás                | CostAggregatedCostStatementEntryEntity      | sum(\[Összeg\])   | Összeg a könyvelési pénznemben |
| Kimutatási bejegyzések | Nettó változás mennyisége       | CostAggregatedCostStatementEntryEntity      | sum(\[Mennyiség\]) |                                   |

A következő táblázat azt mutatja, hogyan használjuk a fő összesített mértékeket számos számított mérték létrehozására a tartalom adathalmazában.

| Méret                                 | A mérőszám kiszámításának módja                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nyitó egyenleg                       | \[Záró egyenleg\]-\[Nettó változás\]                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Nyitóegyenleg mennyisége              | \[Záró egyenleg mennyisége\]-\[Nettó változás mennyisége\]                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Záró egyenleg                          | CALCULATE(SUM(\[Összeg\]), FILTER(ALLEXCEPT('Pénzügyi naptárak', 'Pénzügyi naptárak'\[LedgerRecId\], 'entitások'\[Azonosító\], 'entitások'\[Név\], 'Főkönyvek'\[Pénznem\], 'Főkönyvek'\[Leírás\], 'Főkönyvek'\[Név\]), 'Pénzügyi naptárak'\[Dátum\] &lt;= MAX('Pénzügyi naptárak'\[Dátum\])))                                                                                                                                                                                           |
| Záró egyenleg mennyisége                 | CALCULATE(SUM(\[Mennyiség\]), FILTER(ALLEXCEPT('Pénzügyi naptárak', 'Pénzügyi naptárak'\[LedgerRecId\], 'entitások'\[Azonosító\], 'entitások'\[Név\], 'Főkönyvek'\[Pénznem\], 'Főkönyvek'\[Leírás\], 'Főkönyvek'\[Név\]), 'Pénzügyi naptárak'\[Dátum\] &lt;= MAX('Pénzügyi naptárak'\[Dátum\])))                                                                                                                                                                                         |
| Készlet nyitóegyenlege             | CALCULATE(\[Nyitóegyenleg\], 'Kimutatási bejegyzések'\[Kimutatási típus\] = "Készlet")                                                                                                                                                                                                                                                                                                                                                                                      |
| Készlet záróegyenlege                | CALCULATE(\[Záróegyenleg\], 'Kimutatási bejegyzések'\[Kimutatási típus\] = "Készlet")                                                                                                                                                                                                                                                                                                                                                                                         |
| Készlet nettó változása                    | CALCULATE(\[Nettó változás\], 'Kimutatási bejegyzések'\[Kimutatási típus\] = "Készlet")                                                                                                                                                                                                                                                                                                                                                                                             |
| Nettó készletváltozás mennyisége           | CALCULATE(\[Nettó változás mennyisége\], 'Kimutatási bejegyzések'\[Kimutatási típus\] = "Készlet")                                                                                                                                                                                                                                                                                                                                                                                    |
| Készlet nettó változása %                  | IF (\[Készlet záróegyenlege\] = 0, 0, \[Készlet nettó változása\] / \[Készlet záróegyenlege\])                                                                                                                                                                                                                                                                                                                                                                           |
| Készletforgás összeg alapján                | if(OR(\[Készlet átlagos egyenlege\] &lt;= 0, \[Értékesített vagy felhasznált készlet problémák\] &gt;= 0), 0, ABS(\[Értékesített vagy felhasznált készlet problémák\])/\[Készlet átlagos egyenlege\])                                                                                                                                                                                                                                                                                                  |
| Készlet átlagos egyenlege               | (\[Készlet záróegyenlege\] + \[Készlet nyitóegyenlege\]) / 2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Értékesített vagy felhasznált készlet problémák       | \[Eladott készlet\] + \[Készletből felhasznált anyagköltség\]                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Készletből felhasznált anyagköltség        | CALCULATE(\[Készlet nettó változása\], 'Kimutatási bejegyzések'\[Kategórianév - 2. szint\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Értékesített készlet                          | CALCULATE(\[Készlet nettó változása\], 'Kimutatási bejegyzések'\[Kategórianév - 2. szint\_\] = "Értékesítve")                                                                                                                                                                                                                                                                                                                                                                             |
| Készletpontosság összeg alapján            | IF(\[Készlet záróegyenlege\] &lt;= 0, IF(OR(\[Készlet leltározott mennyisége\] &lt;&gt; 0, \[Készlet záróegyenlege\] &lt; 0), 0, 1), MAX(0, (\[Készlet záróegyenlege\] - ABS(\[Készlet leltározott mennyisége\]))/\[Készlet záróegyenlege\]))                                                                                                                                                                                                                              |
| Készlet leltározott mennyisége                | CALCULATE(\[Készlet nettó változása\], 'Kimutatási bejegyzések'\[Kategórianév - 3. szint\_\] = "Leltár")                                                                                                                                                                                                                                                                                                                                                                         |
| Készlet korosítása                         | if(ISBLANK(max('Pénzügyi naptárak'\[Dátum\])), blank(), MAX(0, MIN(\[Készletkorosítási bevételezések mennyisége\], \[Készletkorosítási záróegyenleg mennyisége\] - \[Jövőbeli készletkorosítási bevételezések mennyisége\]))) \* \[Készlet átlagos egységköltsége\]                                                                                                                                                                                                                                |
| Készletkorosítási bevételezések mennyisége       | IF(\[minDate\] = \[minDateAllSelected\], CALCULATE(\[Nettó készletváltozás mennyisége\], 'Kimutatási bejegyzések'\[Mennyiség\] &gt; 0, FILTER(ALLEXCEPT('Pénzügyi naptárak', 'Pénzügyi naptárak'\[LedgerRecId\], 'entitások'\[Azonosító\], 'entitások'\[Név\], 'Főkönyvek'\[Pénznem\], 'Főkönyvek'\[Leírás\], 'Főkönyvek'\[Név\]), 'Pénzügyi naptárak'\[Dátum\] &lt;= MAX('Pénzügyi naptárak'\[Dátum\]))), CALCULATE(\[Nettó készletváltozás mennyisége\], 'Kimutatási bejegyzések'\[Mennyiség\] &gt; 0)) |
| Készletkorosítási záróegyenleg mennyisége | \[Készletkorosítási záróegyenleg mennyisége\] + CALCULATE(\[Nettó készletváltozás mennyisége\], FILTER(ALLEXCEPT('Pénzügyi naptárak', 'Pénzügyi naptárak'\[LedgerRecId\], 'entitások'\[ID\], 'entitások'\[Név\], 'Főkönyvek'\[Pénznem\], 'Főkönyvek'\[Leírás\], 'Főkönyvek'\[Név\]), 'Pénzügyi naptárak'\[Dátum\] &gt; max('Pénzügyi naptárak'\[Dátum\]) ))                                                                                                                                 |
| Jövőbeli készletkorosítási bevételezések  | CALCULATE(\[Készlet nettó változása\], 'Kimutatási bejegyzések'\[Összeg\] &gt; 0, FILTER(ALLEXCEPT('Pénzügyi naptárak', 'Pénzügyi naptárak'\[LedgerRecId\], 'entitások'\[ID\], 'entitások'\[Név\], 'Főkönyvek'\[Pénznem\], 'Főkönyvek'\[Description\], 'Főkönyvek'\[Név\]), 'Pénzügyi naptárak'\[Dátum\] &gt; MAX('Pénzügyi naptárak'\[Dátum\])))                                                                                                                                             |
| Készlet átlagos egységköltsége                 | CALCULATE(\[Készlet záróegyenlege\] / \[Készletkorosítási záróegyenleg mennyisége\],ALLEXCEPT('Pénzügyi naptárak', 'Pénzügyi naptárak'\[LedgerRecId\], 'entitások'\[Azonosító\], 'entitások'\[Név\], 'Főkönyvek'\[Pénznem\], 'Főkönyvek'\[Leírás\], 'Főkönyvek'\[Név\]))                                                                                                                                                                                                                 |
| Beszerzési eltérések                      | CALCULATE(SUM(\[Összeg\]), 'Kimutatási bejegyzések'\[Kategórianév - 2. szint\_\] = "Beszerezve", 'Kimutatási bejegyzések'\[Kimutatás típusa\] = "Eltérés")                                                                                                                                                                                                                                                                                                                              |
| Befejezetlen termelés nyitóegyenlege                   | CALCULATE(\[Nyitóegyenleg\], 'Kimutatási bejegyzések'\[Kimutatási típus\] = "Befejezetlen termelés")                                                                                                                                                                                                                                                                                                                                                                                            |
| Befejezetlen termelés záróegyenlege                      | CALCULATE(\[Záróegyenleg\], 'Kimutatási bejegyzések'\[Kimutatási típus\] = "Befejezetlen termelés")                                                                                                                                                                                                                                                                                                                                                                                               |
| Befejezetlen termelés nettó változása                          | CALCULATE(\[Nettó változás\], 'Kimutatási bejegyzések'\[Kimutatási típus\] = "Befejezetlen termelés")                                                                                                                                                                                                                                                                                                                                                                                                   |
| Befejezetlen termelés nettó változása %                        | IF(\[Befejezetlen termelés záróegyenlege\] = 0, 0, \[Befejezetlen termelés nettó változása\] / \[Befejezetlen termelés záróegyenlege\])                                                                                                                                                                                                                                                                                                                                                                                             |
| Termelési különbözetek                    | CALCULATE(SUM(\[Összeg\]), 'Kimutatási bejegyzések'\[Kategórianév - 2. szint\_\] = "ManufacturedCost", 'Kimutatási bejegyzések'\[Kimutatás típusa\] = "Eltérés")                                                                                                                                                                                                                                                                                                                      |
| Kategórianév - 1. szint                 | switch(\[Kategórianév - 1. szint\_\], "Nincs", "Nincs", "NetSourcing", "Nettó forrás", "NetUsage", "Nettó forrás", "NetConversionCost", "Nettó átalakítási költség", "NetCostOfGoodsManufactured", "Gyártott áruk nettó költsége", "BeginningBalance", "Nyitóegyenleg")                                                                                                                                                                                                         |
| Kategórianév - 2. szint                 | switch(\[Kategórianév - 2. szint\_\], "None", "Nincs", "Procured", "Beszerezve", "Disposed", "Kivezetve", "Transferred", "Átvive", "Sold", "Eladva", "ConsumedMaterialsCost", "Felhasznált anyagköltség", "ConsumedManufacturingCost", "Felhasznált gyártási költség", "ConsumedOutsourcingCost", "Felhasznált kiszervezési költség", "ConsumedIndirectCost", "Felhasznált közvetett költség", "ManufacturedCost", "Gyártási költség", "Variances", "Eltérések")                            |
| Kategórianév - 3. szint                 | switch(\[Kategórianév - 3. szint\_\], "None", "Nincs", "Counting", "Nincs", "ProductionPriceVariance", "Előállítási ár", "QuantityVariance", "Mennyiség", "SubstitutionVariance", "Helyettesítés", "ScrapVariance", "Selejt", "LotSizeVariance", "Adagméret", "RevaluationVariance", "Átértékelés", "PurchasePriceVariance", "Beszerzési ár", "CostChangeVariance", "Költségváltozás", "RoundingVariance", "Kerekítési különbözet")                                                   |

A következő fő dimenziók szolgálnak szűrőként az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.

| Entitás           | Példák attribútumokra                       |
|------------------|----------------------------------------------|
| Entitások         | Azonosító, név                                     |
| Pénzügyi naptárak | Naptár, hónap, időszak, negyedév, év       |
| KPI-célok        | Készletpontossági cél, készletforgási cél |
| Főkönyvek          | Pénznem, név, leírás                  |
| Telephelyek            | Azonosító, név, ország, város                      |

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](..\data-entities\data-entities.md)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](configure-power-bi-integration.md)





