---
title: "Értékesítés és nyereségesség teljesítményének kiemelt BI-tartalom"
description: "Ez a témakör azt ismerteti, hogy mi tartozik a Dynamics 365 műveletek - értékesítés és a jövedelmezőség teljesítmény tartalom csomag a Microsoft kiemelt BI. Azt ismerteti, hogyan érhető el a jelentéseket a tartalom található, és tájékoztatást nyújt az adatmodell és a csomag létrehozásához használt entitások."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 3e6b48768bb8e69d46f1555d9300f3b878b01ff1
ms.lasthandoff: 03/31/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Értékesítés és nyereségesség teljesítményének kiemelt BI-tartalom

Ez a témakör azt ismerteti, hogy mi tartozik a Dynamics 365 műveletek - értékesítés és a jövedelmezőség teljesítmény tartalom csomag a Microsoft kiemelt BI. Azt ismerteti, hogyan érhető el a jelentéseket a tartalom található, és tájékoztatást nyújt az adatmodell és a csomag létrehozásához használt entitások.

<a name="overview"></a>Áttekintés
--------

A csomag készült értékesítési igazgatók figyelése kulcsfontosságú értékesítési bevétel, a bruttó profitot és a haszonkulcsok metrikáját. Dynamics 365 értékesítési tranzakciós adatait használja a műveletek, és tartalmaz egy összesített nézetét a vállalati szintű forgalmi adatok, mind az értékesítési teljesítmény részletezése a vevők és a termékek. A bevételek és a nyereség növekedése idővel változások kiemelésével jelentések segítségével riasztási menedzserek pozitív és negatív tendenciák az egyes vevők és termékek. Kategória- és regionális vezetők lesz hasznos van a összehasonlítására, bevétel és a nyereségesség különböző termékkategóriák és vevői csoportok egymáshoz, egyetlen laggards és vezetők számára. Ábra egyes vevői bevétel haszonkulcs ajánlatok kapcsolattartók és az egyes vevők megfelelő profil értékesítési és marketing erőfeszítéseiket attune adatokról biztonsági alapítvány átfogó jelentést. Az értékesítés és a jövedelmezőség teljesítményét content pack lehetővé teszi, hogy az értékesítési vezetők elemzése az értékesítési teljesítmény szerint:

-   Bevétel, év dátumig (által Vevőcsoport és az egyes vevők, értékesítési kategóriák, és az egyes termékek és geographies)
-   Jövedelem változása során éves (kategóriánként vevő régiók és értékesítés)

Jövedelmezőség is elemezni:

-   Bruttó haszon és a haszonkulcs (a vevőcsoportok termékkategóriák eladási)
-   Over-éves bruttó nyereség módosítása
-   Ügyfél jövedelmezősége (szerint a bevétel és a bruttó nyereség)

## <a name="accessing-the-content-pack"></a>A csomag elérése
Az értékesítés és a jövedelmezőség teljesítményét content pack végrehajtása eszközként életciklus-szolgáltatások (LCS) közzé van téve, és elérhető a Dynamics 365 műveletek kiemelt BI. Elérését, és indítsa el az energiagazdálkodási BI jelentések használatáról további információt lásd: [a Microsoft és a partnerek LCS kiemelt BI-tartalom](power-bi-content-microsoft-partners.md).

## <a name="metrics-included-in-the-content-pack"></a>A tartalom található metrikák
A csomag tartalmaz egy jelentést, amely bizonyos mérőszámok, mozaikok, táblázatok és diagramok formájában jelenik meg. A következő táblázat áttekintést a content Pack visualisations.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| **Jelentés lap**        | **Charts**                                 | **Mozaik**                                               |
| Vevő bevétel    | TOP 10 vevők a bevétel alapján                | Összes bevétel                                           |
|                        | Vevői csoport összes bevétel            | Műhelykapacitás bevétel növekedés                                      |
|                        | Vevői csoport átlagos vevői bevétel | Bruttó nyereség                                            |
|                        | Bevétel és a bruttó nyereség vevő csoport   |                                                         |
| Termék bevétel     | Bevétel és a bruttó haszon értékesítési kategória szerint   | Teljes \#termékek                                    |
|                        | TOP 10 termékek bevétel                 | Aktív termékek és az összes százalékában száma |
|                        | Összes bevétel értékesítési kategória szerint            | 80 %-os bevétel elszámolása termékek száma           |
| Bevétel időszak szerint\*    | Árbevétel havonta                           | Műhelykapacitás bevétel növekedés                                      |
|                        | Variancia bevétel, Műhelykapacitás záró             | Műhelykapacitás bevétel növekedés %                                    |
|                        | Teljes értékesítési eltérés vevő régiónként    |                                                         |
| Bevétel hely szerint    | Értékesítési bevétel település szerint                      |                                                         |
|                        | Műhelykapacitás bevétel növekedés %                       |                                                         |
|                        | Értékesítési bevétel régiónként                    |                                                         |
| Ügyfél jövedelmezősége | Bruttó nyereség és a bevétel, vevő   | Bruttó nyereség, bruttó nyereség, Műhelykapacitás bevétel növekedés          |
| Nyereségességi elemzés | Bevételek és a bruttó nyereség hónap szerint          |                                                         |
|                        | A legjobb 15 vevők a bruttó nyereség alapján           |                                                         |
|                        | Bruttó nyereség havonta Műhelykapacitás                 |                                                         |

\*Bevétel ez utolsó év és a növekedés értékesítési kategória szerint.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
365 Dynamics műveleti adatok feltöltése a jelentést az értékesítés és a jövedelmezőség teljesítmény csomag szolgál. Összesített mérések előkészítettek ki ez az entitás üzlet Ez az analytics optimalizált Microsoft SQL adatbázis. További információ a blog az olvasás [kiemelt BI integrálása a Dynamics entitás tároló](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). A csomag összesített méréseket az összesített mérések használható a Dynamics AX 2012 és AX 2012 R3 értékesítés kocka részét. A kocka az entitás tároló összesített mérések előkészítése ügyelnie kell azok központilag telepíthető. További információért tekintse át a előkészítése a blogjában entitás tárolóba összesített mérések [kiemelt BI integrálása a Dynamics entitás tároló](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). A következő kulcs összesített mérések számla sorai entitás a csomag alapjául szolgálnak.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entity**    | **Kulcs összesített mérések**               | **Adatforrás Dynamics 365 műveletek** | **Field**                                    | **Description**                          |
| Számlasorok | Bevétel                                      | A CustInvoiceTrans                                | Sum(LineAmountMST)                           | Összeg könyvelési pénznemben            |
|               | Eladott áruk beszerzési értéke                           | InventTrans                                     | ÖSSZEG (CostAmountPosted + CostAmountAdjustment) | Költség összeg + helyesbítés                 |
|               | A Bizottság összege-könyvelési pénznem | A CustInvoiceTrans                                | Sum(CommissAmountMST)                        | Jutalék összege alapértelmezett pénznemben |

A következő táblázat a kulcs összesített mérések számla sorai entitás a content pack dataset több számított mértékek létrehozására használt.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Measure**       | **Képlettel számítható ki:**                                                                                |
| Bruttó nyereség      | SZUM (árbevétel – ELÁBÉ – a Bizottság – a forgalmi adó (vevői számlasor összege szerepel))          |
| Bruttó nyereség      | ÖSSZEG (bruttó nyereség / (bevétel - forgalmi adó (vevői számlasor összege szerepel)))             |
| Tavalyi bevétel | Bevétel tavaly számítás = (SZUM ("Számlasorokban"\[bevétel\]), SAMEPERIODLASTYEAR (dátumok\[dátum\]) |

A következő kulcs méretek a **a Beszerzés kocka** nagyobb részletesség és mélyebb analitikai elképzelések eléréséhez összesített mérések szeletelése szűrőként használt.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entity**       | **Példák az attribútumok**                           |
| Vevők        | Vevőcsoportok, vevő régiók, cím, az ipar |
| Termékek         | Termékszám, a termék neve, a cikk csoportok neve       |
| Értékesítési kategóriák | Értékesítési kategória neve                                 |
| Jogi személyek   | Jogi személy neve                                   |
| Dátumok            | Dátumok                                                |

Alapértelmezés szerint a csomagot a folyó naptári év adatait jeleníti meg, de a szűrők jelentésszakasz megnyithatja és módosíthatja a dátum szűrő. A vállalat szűrőt is módosíthatja.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](..\data-entities\data-entities.md)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](configure-power-bi-integration.md)



