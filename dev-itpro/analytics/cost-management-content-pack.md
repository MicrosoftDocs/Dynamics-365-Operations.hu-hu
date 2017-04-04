---
title: "Kiemelt BI tartalom kezelés költsége"
description: "Ez a témakör azt ismerteti, mit tartalmaz a költség kezelése kiemelt BI-tartalom. Ismerteti, hogyan lehet elérni a kiemelt BI jelentéseket, és tájékoztatást nyújt az adatmodell és a tartalom létrehozásához használt entitások."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: e4de011e6eeac58643b828b65e24b874d981d5e7
ms.lasthandoff: 03/31/2017


---

# <a name="cost-management-power-bi-content"></a>Kiemelt BI tartalom kezelés költsége

Ez a témakör azt ismerteti, mit tartalmaz a költség kezelése kiemelt BI-tartalom. Ismerteti, hogyan lehet elérni a kiemelt BI jelentéseket, és tájékoztatást nyújt az adatmodell és a tartalom létrehozásához használt entitások.

# <a name="overview"></a>Áttekintés

A **kezelési költség** a Microsoft kiemelt BI tartalom szánt készlet könyvelők vagy a szervezet egyének, akik felelősek a készlet. A **kezelési költség** Power BI-tartalom készlet és befejezetlen folyamatban lévő (Befejezetlen) készlet és hogyan költség átáramlik őket kategóriánként idővel vezetői betekintést biztosít. Az információkat is a pénzügyi kimutatás részletes kiegészítéseként használható.

## <a name="key-measures"></a>Kulcsfontosságú intézkedések

+ Nyitó egyenleg
+ Záró egyenleg
+ Nettó változás
+ Nettó változás %-ban
+ Korosítási

## <a name="key-performance-indicators"></a>Fő teljesítménymutatók
+ Készletforgás
+ Készlet pontossága

Az elsődleges adatforrás CostAggregatedCostStatementEntryEntity a CostStatementCache táblában. Ez a tábla adathalmaz gyorsítótár keretében kezeli. Alapértelmezés szerint a tábla 24 óránként frissül, de engedélyezheti az adatok cache beállítás kézi frissítést. Kézi frissítés a majd teheti a **kezelési költség** vagy **-elemzés** munkaterület. CostStatementCache frissítés futtatása után frissítenie kell a frissített adatok megtekintéséhez a helyszínen BI.com kiemelt OData kapcsolatán. A kiemelt BI tartalom eltérése (beszerzés, termelés) intézkedések csak az Elszámolóár leltározási módszer szerint vannak valuated cikkek vonatkoznak. Termelési különbözet számítása és aktív realizált költsége közötti különbség. Ha a gyártási rendelés állapota a termelési különbözet számítása **befejezve**. További információt a gyártási eltérés típusát és az egyes kiszámítási módját lásd a [kapcsolatos eltérések a befejezett gyártási rendelés elemzése](https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>A kiemelt BI-tartalom elérése
A **kezelési költség** Power BI tartalom érhető el a PowerBI.com. Csatlakoztatása és a Microsoft Dynamics 365 műveleti adatok betöltése kapcsolatos további tudnivalókért lásd: [tartalom Access kiemelt BI PowerBI.com](power-bi-home-page.md).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>A kiemelt BI tartalom található metrikák
A tartalom jelentés oldalak készletét tartalmazza. Minden oldal metrikák láthatóvá tehetők, mozaikok, táblázatok és diagramok, amelyek összessége alkotja. A következő táblázat áttekintést nyújt az a képi megjelenítések a a **kezelési költség** Power BI-tartalom.

| Jelentés lap | Diagramok | Beosztások |
|---|---|---|
|Teljes készlet (alapértelmezés szerint az aktuális időszakra) |Pontosság |Készlet intézkedések:<br>Készlet, záró egyenleg<br>Leltár forgalom<br>Készlet-forgalom %<br>|
| |Készletforgás | |
| |Záró egyenleg erőforráscsoport készlet | |
| |Leltár forgalom kategória neve szintje 1 és 2. kategória neve szint| |
| |Beszerzési eltérés erőforráscsoportot és a kategória neve a 3-as szintű | |
|Készlet a webhely (alapértelmezés szerint az aktuális időszakra) |Záró egyenleg hely neve és az erőforráscsoport készlet | |
| |Készletforgalom-hely nevét és az erőforrás csoport | |
| |Készlet a város és az erőforrás csoport, záró egyenleg | |
|Készlet erőforrás csoport (alapértelmezés szerint az aktuális időszakra) |Készlet intézkedések | |
| |Erőforráscsoport összeggel készlet pontosság | |
| |Készletforgalom erőforráscsoport összeggel | |
|Készlet Műhelykapacitás (alapértelmezett folyó év vs előző év) |Készlet intézkedések | |
| |Készlet KPI-k:<br>Készletforgás<br>Készlet pontossága | |
| |Záró egyenleg, év és az erőforrás csoport készlet | |
| |Beszerzési eltérés, év és a kategória neve szinttel 3 | |
|Készletdimenzió korosítási (alapértelmezés szerint a folyó év) |Készletdimenzió korosítási negyedév és az erőforrás csoport | |
| |Készletdimenzió korosítási negyedév és a webhely neve | |
|Folyamatban lévő munka általános (alapértelmezés szerint az aktuális időszakra) |Folyamatban lévő munka nettó kategória neve szintje 1 és 2. kategória neve szint módosítása |Befejezetlen termelésként intézkedések:<br>Folyamatban lévő munka záró egyenlege<br>Folyamatban lévő munka nettó változás<br>Folyamatban lévő munka nettó változás %<br> |
| |Erőforrás csoport és a kategória neve a 3-as szintű termelési eltérések | |
| |Folyamatban lévő munka nettó változás erőforráscsoport | |
|Folyamatban lévő munka webhely (alapértelmezés szerint az aktuális időszakra) |A folyamatban lévő munka folyamatban lévő munka intézkedések | |
| |Folyamatban lévő munka nettó hely nevét és a kategória neve 2 szint módosítása | |
| |Hely neve és a kategória neve a 3-as szintű termelési eltérések | |

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
365 Dynamics műveleti adatok jelentés oldalainak feltöltéséhez használja a **kezelési költség** Power BI-tartalom. Összesített mérések előkészítettek ki ezeket az adatokat az entitás üzlet Ez az analytics optimalizált Microsoft SQL adatbázis. További tudnivalókért lásd: [tároló entitás integráció kiemelt BI áttekintése](power-bi-integration-entity-store.md). A következő kulcs összesített mérések a tartalom alapjául szolgálnak.

| Entitás            | Kulcs összesített támogatottsági mutató | Adatforrás Dynamics 365 műveletek | Mező             | Leírás                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Utasítás tételek | Nettó változás                | CostAggregatedCostStatementEntryEntity      | összeg (\[összeg\])   | Összeg az alapértelmezett pénznemben |
| Utasítás tételek | Forgalom-mennyiség       | CostAggregatedCostStatementEntryEntity      | összeg (\[mennyiség\]) |                                   |

A következő táblázat a kulcs összesített mérések használata a tartalom dataset több számított mértékek létrehozására.

| Méret                                 | Az intézkedés kiszámításának módjáról                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nyitó egyenleg                       | \[Záró egyenleg\]-\[forgalom\]                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Kezdő egyenleg mennyisége              | \[Záró egyenleg mennyisége\]-\[nettó mennyiség módosítása\]                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Záró egyenleg                          | SZÁMÍTÁS (összege (\[összeg\]), szűrő (ALLEXCEPT ("Pénzügyi naptárak", "Pénzügyi naptárak"\[LedgerRecId\], "személyek"\[ID\], "személyek"\[neve\], "Főkönyvek"\[pénznem\], "Főkönyvek"\[leírás\], "Főkönyvek"\[neve\]), "Pénzügyi naptárak"\[dátum\]&lt;= MAX ("Pénzügyi naptárak"\[dátum\])))                                                                                                                                                                                           |
| Záró egyenleg mennyisége                 | SZÁMÍTÁS (összege (\[mennyiség\]), szűrő (ALLEXCEPT ("Pénzügyi naptárak", "Pénzügyi naptárak"\[LedgerRecId\], "személyek"\[ID\], "személyek"\[neve\], "Főkönyvek"\[pénznem\], "Főkönyvek"\[leírás\], "Főkönyvek"\[neve\]), "Pénzügyi naptárak"\[dátum\]&lt;= MAX ("Pénzügyi naptárak"\[dátum\])))                                                                                                                                                                                         |
| Készlet, nyitó egyenleg             | SZÁMÍTÁS (\[nyitó egyenleg\], "Utasítás bejegyzések"\[utasítás típusa\] = "Készlet")                                                                                                                                                                                                                                                                                                                                                                                      |
| Készlet, záró egyenleg                | SZÁMÍTÁS (\[záró egyenleg\], "Utasítás bejegyzések"\[utasítás típusa\] = "Készlet")                                                                                                                                                                                                                                                                                                                                                                                         |
| Leltár forgalom                    | SZÁMÍTÁS (\[forgalom\], "Utasítás bejegyzések"\[utasítás típusa\] = "Készlet")                                                                                                                                                                                                                                                                                                                                                                                             |
| Készletmennyiség nettó változás           | SZÁMÍTÁS (\[nettó mennyiség módosítható,\], "Utasítás bejegyzések"\[utasítás típusa\] = "Készlet")                                                                                                                                                                                                                                                                                                                                                                                    |
| Készlet-forgalom %                  | IF (\[záró egyenlege készlet\] = 0, 0, \[forgalom készlet\] / \[záró egyenlege készlet\])                                                                                                                                                                                                                                                                                                                                                                           |
| Készletforgalom-összeg                | Ha (vagy (\[készlet átlagos egyenleg\]&lt;= 0, \[készlet értékesített vagy felhasznált problémák\]&gt;= 0), 0, ABS (\[készlet értékesített vagy felhasznált problémák\]) /\[készlet átlagos egyenleg\])                                                                                                                                                                                                                                                                                                  |
| Átlagos készlet egyenleg               | (\[Záró egyenlege készlet\] + \[kezdő egyenleg készlet\]) / 2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Készlet értékesített vagy felhasznált problémák       | \[Eladott készlet\] + \[készlet felhasznált anyagköltség\]                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Készlet felhasznált anyagköltség        | SZÁMÍTÁS (\[forgalom készlet\], "Utasítás bejegyzések"\[kategória neve – 2. szint\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Eladott készlet                          | SZÁMÍTÁS (\[forgalom készlet\], "Utasítás bejegyzések"\[kategória neve – 2. szint\_\] = "Eladó")                                                                                                                                                                                                                                                                                                                                                                             |
| Készlet pontosság összeggel            | Ha (\[záró egyenlege készlet\]&lt;= 0, ha (vagy (\[készlet Leszámolt összeg\]&lt;&gt; 0, \[záró egyenlege készlet\]&lt; 0), 0, 1), MAX (0, (\[záró egyenlege készlet\] -ABS (\[készlet Leszámolt összeg\])) /\[záró egyenlege készlet\]))                                                                                                                                                                                                                              |
| Leszámolt összeg készlet                | SZÁMÍTÁS (\[forgalom készlet\], "Utasítás bejegyzések"\[kategória neve - 3-as szintű\_\] = "Counting")                                                                                                                                                                                                                                                                                                                                                                         |
| Készlet korosítása                         | Ha (üres (max ("Pénzügyi naptárak"\[dátum\])), blank(), MAX (0, MIN (\[készletdimenzió korosítási bevételezési mennyiség\], \[készlet, záró egyenleg mennyisége az elévülés\] - \[készletdimenzió korosítási bevételezési mennyiség a jövőben\]))) \*\[készlet átlagos önköltségi\]                                                                                                                                                                                                                                |
| Készletdimenzió korosítási bevételezési mennyiség       | Ha (\[minDate\] = \[minDateAllSelected\], számítás (\[forgalom mennyiség készlet\], "Utasítás bejegyzések"\[mennyiség\]&gt; 0, szűrő (ALLEXCEPT ("Pénzügyi naptárak", "Pénzügyi naptárak"\[LedgerRecId\], "személyek"\[azonosító\], "személyek"\[neve\], "Főkönyvek"\[pénznem\], "Főkönyvek"\[leírás\], "Főkönyvek"\[neve\]), "Pénzügyi naptárak"\[dátum\]&lt;= MAX ("Pénzügyi naptárak"\[dátum\]))), számítás (\[forgalom mennyiség készlet\], "Utasítás bejegyzések"\[mennyiség\]&gt; 0)) |
| Készletdimenzió korosítási záró egyenleg mennyisége | \[Záró egyenleg mennyisége készlet\] + számítás (\[forgalom mennyiség készlet\], szűrő (ALLEXCEPT ("Pénzügyi naptárak", "Pénzügyi naptárak"\[LedgerRecId\], "személyek"\[azonosító\], "személyek"\[neve\], "Főkönyvek"\[pénznem\], "Főkönyvek"\[leírás\], "Főkönyvek"\[neve\]), "Pénzügyi naptárak"\[dátum\]&gt; max ("Pénzügyi naptárak"\[dátum\])))                                                                                                                                 |
| Az elévülés készletbevételek a jövőben  | SZÁMÍTÁS (\[forgalom készlet\], "Utasítás bejegyzések"\[összeg\]&gt; 0, szűrő (ALLEXCEPT ("Pénzügyi naptárak", "Pénzügyi naptárak"\[LedgerRecId\], "személyek"\[ID\], "személyek"\[neve\], "Főkönyvek"\[pénznem\], "Főkönyvek"\[leírás\], "Főkönyvek"\[neve\]), "Pénzügyi naptárak"\[dátum\]&gt; MAX ("Pénzügyi naptárak"\[dátum\])))                                                                                                                                             |
| Készlet átlagos önköltségi                 | SZÁMÍTÁS (\[záró egyenlege készlet\] / \[készlet a záró egyenleg mennyisége\], ALLEXCEPT ("Pénzügyi naptárak", "Pénzügyi naptárak"\[LedgerRecId\], "személyek"\[azonosító\], "személyek"\[neve\], "Főkönyvek"\[pénznem\], "Főkönyvek"\[leírás\], "Főkönyvek"\[neve\]))                                                                                                                                                                                                                 |
| Beszerzési eltérés                      | SZÁMÍTÁS (SUM (\[összeg\]), "Utasítás bejegyzések"\[kategória neve – 2. szint\_\] = "Procured", "Utasítás bejegyzések"\[utasítás típusa\] = "Eltérés")                                                                                                                                                                                                                                                                                                                              |
| Folyamatban lévő munka kezdő egyenleg                   | SZÁMÍTÁS (\[nyitó egyenleg\], "Utasítás bejegyzések"\[utasítás típusa\] = "Folyamatban")                                                                                                                                                                                                                                                                                                                                                                                            |
| Folyamatban lévő munka záró egyenlege                      | SZÁMÍTÁS (\[záró egyenleg\], "Utasítás bejegyzések"\[utasítás típusa\] = "Folyamatban")                                                                                                                                                                                                                                                                                                                                                                                               |
| Folyamatban lévő munka nettó változás                          | SZÁMÍTÁS (\[forgalom\], "Utasítás bejegyzések"\[utasítás típusa\] = "Folyamatban")                                                                                                                                                                                                                                                                                                                                                                                                   |
| Folyamatban lévő munka nettó változás %                        | IF (\[záró egyenleg folyamatban lévő munka\] = 0, 0, \[folyamatban lévő munka nettó változás\] / \[záró egyenleg folyamatban lévő munka\])                                                                                                                                                                                                                                                                                                                                                                                             |
| Termelési eltérések                    | SZÁMÍTÁS (SUM (\[összeg\]), "Utasítás bejegyzések"\[kategória neve – 2. szint\_\] = "ManufacturedCost", "Utasítás bejegyzések"\[utasítás típusa\] = "Eltérés")                                                                                                                                                                                                                                                                                                                      |
| Kategória neve - 1. szint                 | Váltás (\[kategória neve - 1. szint\_\], "None", "None", "NetSourcing", "Forrás nettó", "NetUsage", "Nettó kihasználtsága", "NetConversionCost", "Nettó átalakítási költségeinek", "NetCostOfGoodsManufactured", "Előállított áruk nettó", "BeginningBalance", "Nyitó egyenleg")                                                                                                                                                                                                         |
| Kategória neve – 2. szint                 | Váltás (\[kategória neve – 2. szint\_\], "None", "None", "Procured", "Procured", "Disposed", "Disposed", "Az átutalt", "Az átutalt", "Eladó", "Eladó", "ConsumedMaterialsCost", "Felhasznált anyagok költsége", "ConsumedManufacturingCost", "Felhasznált gyártási költség", "ConsumedOutsourcingCost", "Felhasznált kiszervezési költség", "ConsumedIndirectCost", "Felhasznált közvetett költség", "ManufacturedCost", "Gyártó költség", "Eltérések", "Eltérések")                            |
| Kategória neve - 3. szint                 | Váltás (\[kategória neve - 3-as szintű\_\], "None", "None", "Leltár", "None", "ProductionPriceVariance", "Termelési ár", "QuantityVariance", "Mennyiség", "SubstitutionVariance", "Helyettesítés", "ScrapVariance", "Hulladék", "LotSizeVariance", "Adag mérete", "RevaluationVariance", "Átértékelési", "PurchasePriceVariance", "Vételár", "CostChangeVariance", "Költség változása", "RoundingVariance", "Kerekítési különbözet")                                                   |

A következő főbb dimenziókra használják szűrőként nagyobb részletesség elérése és mélyebb analitikai elképzelések összesített mérések szeletelhetők.

| Entitás           | Példák az attribútumok                       |
|------------------|----------------------------------------------|
| Entitások         | Azonosítója, neve                                     |
| Pénzügyi naptárak | A naptár, a hónap, időszak, negyedév, év       |
| KPI-célok        | Készlet pontosság cél, a készletforgalom cél |
| Főkönyvek          | Pénznem, név, leírás                  |
| Telephelyek            | Azonosító, név, ország, város                      |

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](..\data-entities\data-entities.md)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](configure-power-bi-integration.md)



