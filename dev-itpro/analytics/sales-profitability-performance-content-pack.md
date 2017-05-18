---
title: "Értékesítési és nyereségességi teljesítmény Power BI-tartalma"
description: "Ez a témakör leírja, hogy mit tartalmaz a Dynamics 365 for Operations - Értékesítési és a jövedelmezőségi teljesítmény csomag a Microsoft Power BI számára. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 35d34f9a356f8a041f2abf0aa8d6c3a6d9ca4a46
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Értékesítési és nyereségességi teljesítmény Power BI-tartalma

[!include[banner](../includes/banner.md)]


Ez a témakör leírja, hogy mit tartalmaz a Dynamics 365 for Operations - Értékesítési és a jövedelmezőségi teljesítmény csomag a Microsoft Power BI számára. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

<a name="overview"></a>Áttekintés
--------

Ezt a tartalomcsomagot az értékesítési vezetők számára hozták létre a bevétel, a bruttó nyereség és a fedezeti mutató kulcsfontosságú értékesítési mutatóinak figyelemmel kísérésére. A Dynamics 365 for Operations értékesítési tranzakciós adatait használja, és egyaránt bemutatja a vállalat egészére kiterjedő eladási adatokat és az ügyfelek és termékek értékesítési teljesítményének lebontását. A bevételek és a profitnövekedés időbeli változásainak kiemelésével a jelentések felhasználhatók arra, hogy figyelmeztessék a vezetőket az egyes ügyfelek és termékek pozitív és negatív trendjeire. A kategória- és regionális vezetők hasznosnak találják azokat a diagramokat, amelyek összehasonlítják a különböző termékkategóriák és ügyfélcsoportok bevételét és nyereségességét egymással, hogy kimutassák a lemaradókat és a vezetőket. Az egyéni ügyfelek bevételének és fedezeti mutatójának egyaránt átfogó jelentése a számlavezetők számára egy adatvédelemmel ellátott alapot biztosít, hogy értékesítési és marketingerőfeszítéseiket az egyes ügyfelek profiljához igazítsa. Az Értékesítési és a jövedelmezőségi teljesítmény csomag lehetővé teszi az értékesítési vezetők számára az értékesítési teljesítmény elemzését:

-   Bevétel, éves (ügyfélkategória és egyedi ügyfelek, értékesítési kategóriák, egyedi termékek és földrajzi adatok szerint)
-   Bevételváltozás, évről évre (az ügyfélkör és az értékesítési kategóriák szerint)

A nyereségesség elemezhető az alábbiak szerint:

-   Bruttó nyereség és fedezeti mutató (ügyfélcsoportok és termékértékesítési kategóriák szerint)
-   Bruttó nyereségváltozás, évről évre
-   Ügyfél jövedelmezősége (bevétel és bruttó nyereség szerint)

## <a name="accessing-the-content-pack"></a>A tartalmi csomag elérése
Az Értékesítési és nyereségességi teljesítmény Power BI-tartalomcsomag a Microsoft Dynamics Lifecycle Services (LCS) végrehajtási eszközeként van közzétéve, és a Microsoft Dynamics 365 for Operations programból férhető hozzá. A Power BI jelentések elérésével és elindításával kapcsolatos további tudnivalókért lásd: [Power BI-tartalom az LCS megoldásban a Microsoft vállalattól és a partnerektől](power-bi-content-microsoft-partners.md).
**Megjegyzés:** A KB 4011327 ezen Power BI-tartalom előfeltétele. A Lifecycle Servicesbe való bejelentkezést követően itt férhet hozzá a tudásbázishoz: <a href="https://fix.lcs.dynamics.com/issue/results/?q=kb4011327">https://fix.lcs.dynamics.com/issue/results/?q=kb4011327</a>.

## <a name="metrics-included-in-the-content-pack"></a>A tartalomcsomag által tartalmazott metrikák
A tartalomcsomag tartalmaz egy jelentést, amely metrikák diagramok, mozaikok és táblák formájában megjelenített készletéből áll. Az alábbi táblázatban a tartalomcsomag megjelenítési formáinak áttekintése található.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| **Jelentéslap**        | **Diagramok**                                 | **Mozaik**                                               |
| Bevétel vevő szerint    | 10 vezető vevő bevétel alapján                | Összes bevétel                                           |
|                        | Vevői csoport összes bevétele            | Éves bevételnövekedés                                      |
|                        | Vevői csoport átlagos vevői bevétele | Bruttó nyereség                                            |
|                        | Bevétel és a bruttó nyereség vevőcsoport szerint   |                                                         |
| Bevétel termék szerint     | Bevétel és a bruttó nyereség értékesítési kategória szerint   | Termékek összes száma (\#)                                    |
|                        | 10 vezető termék bevétel alapján                 | Összes aktív termék száma és a teljes termékszám százaléka |
|                        | Összes bevétel értékesítési kategória szerint            | A bevételek 80%-át lefedő termékek száma           |
| Időszak bevétele\*    | Bevétel hónap szerint                           | Éves bevételnövekedés                                      |
|                        | Záró bevétel eltérése, éves             | Éves bevételnövekedés %                                    |
|                        | Teljes értékesítési eltérés vevői régiónként    |                                                         |
| Bevétel hely szerint    | Értékesítési bevétel település szerint                      |                                                         |
|                        | Éves bevételnövekedés %                       |                                                         |
|                        | Értékesítési bevételek régiónként                    |                                                         |
| Ügyfél jövedelmezősége | Bruttó nyereség és bevétel, vevő szerint   | Bruttó nyereség, bruttó nyereség, éves bevételnövekedés          |
| Nyereségességi elemzés | Bevétel és a bruttó nyereség hónap szerint          |                                                         |
|                        | 15 vezető ügyfél bruttó nyereség szerint           |                                                         |
|                        | Bruttó nyereség havonta, éves adat                 |                                                         |

\* Erre az évre és az előző évre eső bevétel és növekedés értékesítési kategória szerint.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
Az Értékesítési és a jövedelmezőségi teljesítmény tartalomcsomag jelentésének feltöltésére a Dynamics 365 for Operations adatok szolgálnak. Ezek az adatok az entitástárban előkészített összesített mérések formájában jelennek meg – az entitástár egy elemzési célra optimalizált Microsoft SQL-adatbázis. További információért olvassa el a következő blogot: [A Power BI és az entitástár integrálása a Dynamics programban](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). A tartalomcsomag összesítő mértékek a következőkben rendelkezésre álló összesítő mértékek részhalmazát alkotják: Sales Cube in Dynamics AX 2012 és az AX 2012 R3. A kocka összesítő mértékeinek előkészítéséhez az entitástárban, a mértékeket központilag telepíthetővé kell tenni. További információért lásd a következő blogot az összesítő mértékek előkészítésének eljárásáról az entitástárban: [A Power BI és az entitástár integrálása a Dynamics programban](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). A következő kulcsfontosságú összesítő mértékek közvetlenül a számla sorai entitásból érhetők el, és a tartalomcsomag alapjául szolgálnak.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entitás**    | **Kulcs összesítő mértékek**               | **A Dynamics 365 for Operations adatforrása** | **Mező**                                    | **Leírás**                          |
| Számlasorok | Bevétel                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Összeg könyvelési pénznemben            |
|               | Eladott áruk beszerzési értéke                           | InventTrans                                     | SUM(CostAmountPosted + CostAmountAdjustment) | Költségösszeg + kiigazítás                 |
|               | Jutaléksor összege – könyvelési pénznem | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | Jutalék összege a könyvelési pénznemben |

A következő táblázat azt mutatja, hogyan használjuk a számlasorok entitásának fő összesített mértékeit számos számított mérték létrehozására a tartalomcsomag adathalmazában.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Méret**       | **Számítás**                                                                                |
| Bruttó nyereség      | SZUM(Bevétel – ELÁBÉ – Jutalék – (a vevői számlasor összegének áfatartalma) - könyvelési pénznem)          |
| Bruttó nyereség      | SZUM(Bruttó nyereség/(Bevétel – áfa (a vevői számlasor összegének áfatartalma)))             |
| Tavalyi bevétel | Tavalyi év bevételei = CALCULATE(SUM('Számlasorok'\[Bevétel\]), SAMEPERIODLASTYEAR(Dátumok\[Dátum\])) |

Az **Értékesítés kocka** következő fő dimenziói szolgálnak szűrőként az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entitás**       | **Példák attribútumokra**                           |
| Vevők        | Vevőcsoportok, vevőrégiók, cím, iparág |
| Termékek         | Termékszám, Termék neve, Cikkcsoportok neve       |
| Értékesítési kategóriák | Értékesítési kategóriák nevei                                 |
| Jogi személyek   | Jogi személyek nevei                                   |
| Dátumok            | Dátumok                                                |

Alapértelmezés szerint a tartalomcsomag az aktuális naptári év adatait jeleníti meg, de megnyithatja a jelentésszűrőket, és módosíthatja a dátumszűrőt. A vállalatszűrőt is módosíthatja.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](..\data-entities\data-entities.md)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](configure-power-bi-integration.md)





