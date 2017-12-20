---
title: "Értékesítési és nyereségességi teljesítmény Power BI-tartalom"
description: "Ez a témakör azt ismerteti, mit tartalmaz az Értékesítési és a jövedelmezőségi teljesítmény Power BI-tartalom modul. Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
author: YuyuScheller
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: c065eb2f19bbbd553e070f06c29f73114e3efad5
ms.contentlocale: hu-hu
ms.lasthandoff: 12/01/2017

---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Értékesítési és nyereségességi teljesítmény Power BI-tartalom

[!include[banner](../includes/banner.md)]

Ez a témakör azt ismerteti, mit tartalmaz az **Értékesítési és a jövedelmezőségi teljesítmény** Microsoft Power BI-tartalom modul. Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

Az **Értékesítési és a jövedelmezőségi teljesítmény** Power BI-tartalmat az értékesítési vezetők számára hozták létre a bevétel, a bruttó nyereség és a fedezeti mutató kulcsfontosságú értékesítési mutatóinak figyelemmel kísérésére. Értékesítési tranzakciós adatokat használ, és egyaránt bemutatja a vállalat egészére kiterjedő eladási adatokat és az ügyfelek és termékek értékesítési teljesítményének lebontását.

A jelentések kiemelik a bevételek és a profitnövekedés időbeli változásait. Ezért a jelentések riasztásra használhatók a menedzserek számára a pozitív és negatív trendjekről az egyes ügyfelekre és termékekre nézve. Ezenkívül a diagramok összehasonlítják a különböző termékkategóriák és ügyfélcsoportok bevételét és jövedelmezőségét egymással. Ezek segítségével a kategória- és regionális vezetők azonosíthatják a lemaradókat és a vezetőket. Végül pedig egy átfogó jelentés egymás mellé rendezi az egyéni ügyfelek bevételét és és a fedezeti mutatót. Ez a számlavezetők számára egy adatvédelemmel ellátott alapot biztosít, hogy értékesítési és marketingerőfeszítéseiket az egyes ügyfelek profiljához igazítsák. 

Az **Értékesítési és a jövedelmezőségi teljesítmény** tartalom a következő módokon teszi lehetővé az értékesítési vezetők számára az értékesítési teljesítmény elemzését:

-   Bevétel, éves (ügyfélkategória és egyedi ügyfelek, értékesítési kategóriák, egyedi termékek és földrajzi adatok szerint)
-   Bevételváltozás, évről évre (az ügyfélkör és az értékesítési kategóriák szerint)

A jövedelmezőség elemzése a következő módokon történhet:

-   Bruttó nyereség és fedezeti mutató (ügyfélcsoportok és termékértékesítési kategóriák szerint)
-   Bruttó nyereségváltozás, évről évre
-   Ügyfél jövedelmezősége (bevétel és bruttó nyereség szerint)

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése
Az **Értékesítési és jövedelmezőségi teljesítmény** Power BI-tartalom az **Értékesítési és jövedelmezőségi teljesítmény** oldalon látható (**Értékesítés és marketing** > **Lekérdezések és jelentések** > **Értékesítési teljesítményelemzés** > **Értékesítési és jövedelmezőségi teljesítmény**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó metrikák
Az **Értékesítési és jövedelmezőségi teljesítmény** Power BI-tartalom tartalmaz egy jelentést, amely metrikák készletéből áll. Ezek a metrikák mozaikok, táblázatok és diagramok formájában jelennek meg. Az alábbi táblázatban a tartalom megjelenítési formáinak áttekintése található.

| Jelentéslap            | Diagramok                                     | Mozaik                                                   |
|------------------------|--------------------------------------------|---------------------------------------------------------|
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

## <a name="extending-the-power-bi-content"></a>Power BI-tartalom kibővítése
A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban található tartalomcsomagok révén nagyszerű elemzési lehetőségeket nyújthat azoknak a személyeknek, akik nem jelentkeztek be a Microsoft Dynamics 365 szolgáltatásba. Ezek a tartalomcsomagok módosíthatók, hogy más jelentéseket vagy megjelenítéseket is tartalmazhassanak, majd a tartalomcsomagok elemzés céljából közzétehetők a Power BI.com-bérlőjénél.

Az **Értékesítési és jövedelmezőségi teljesítmény** Power BI-tartalmat az LCS Megosztott eszközök könyvtárában találja. A tartalom letöltésére és szervezeténél való megvalósítására vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md). Ha meg szeretne tekinteni egy demót, amely bemutatja a Power BI-tartalmak megvalósítását, lásd a [Power BI-tartalom a Microsofttól és az Ön partnereitől a Dynamics Lifecycle Services szolgáltatásban](https://mix.office.com/watch/9puyb1b2xs1w) című részt (Office Mix).

Ügyeljen arra, hogy azt az **Értékesítési és jövedelmezőségi teljesítmény** tartalmat töltse le, amely a Dynamics 365 ön által használt verziójára vonatkozik.

> [!NOTE]
> Amennyiben a Microsoft Dynamics 365 for Finance and Operations Enterprise edition 1611-es verzióját használja, a KB 4011327 a Power BI-tartalom előfeltétele. A Lifecycle Services szolgáltatásba való bejelentkezést követően itt férhet hozzá a tudásbázishoz: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
Az **Értékesítési és jövedelmezőségi teljesítmény** Power BI-tartalom jelentésének feltöltésére a következő adatok szolgálnak. Ezeket az adatokat az Entitástárban lebonyolított összesített mérések jelenítik meg. Az entitástár a Microsoft analitikai célokra optimalizált SQL-szerveradatbázisa. További tudnivalókért lásd: [Az entitástár és a Power BI integrációjának áttekintése](power-bi-integration-entity-store.md). 

A tartalom összesítő mértékek a következőkben rendelkezésre álló összesítő mértékek részhalmazát alkotják: Sales Cube in Microsoft Dynamics AX 2012 és Microsoft Dynamics AX 2012 R3. A kocka összesítő mértékeinek előkészítéséhez az entitástárban, a mértékeket központilag telepíthetővé kell tenni. További információért lásd a következő blogbejegyzést az összesítő mértékek előkészítésének eljárásáról az entitástárban: [A Power BI és az entitástár integrálása a Dynamics programban](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). 

A következő kulcsfontosságú összesítő mértékek közvetlenül a számla sorai entitásból érhetők el, és a tartalom alapjául szolgálnak.

| Entitás        | Kulcs összesítő mértékek                   | Adatforrás a Dynamics 365 szolgáltatáshoz                    | Mező                                        | Leírás                                   |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|----------------------------------------------|
| Számlasorok | Bevétel                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Összeg a könyvelési pénznemben.            |
|               | Eladott áruk beszerzési értéke                           | InventTrans                                     | SUM(CostAmountPosted + CostAmountAdjustment) | A költségösszeg és a helyesbítés összege.    |
|               | Jutaléksor összege – könyvelési pénznem | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | A jutalék összege a könyvelési pénznemben. |

A következő táblázat azt mutatja, hogyan használjuk a Számlasorok entitásának fő összesített mértékeit számos számított mérték létrehozására a tartalom adathalmazában.

| Méret           | Számítás                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| Bruttó nyereség      | SZUM(Bevétel – ELÁBÉ – Jutalék – (a vevői számlasor összegének áfatartalma) - könyvelési pénznem)          |
| Bruttó nyereség      | SZUM(Bruttó nyereség/(Bevétel – áfa (a vevői számlasor összegének áfatartalma)))             |
| Tavalyi bevétel | Tavalyi év bevételei = CALCULATE(SUM('Számlasorok'\[Bevétel\]), SAMEPERIODLASTYEAR(Dátumok\[Dátum\])) |

Az alábbi táblázat megjeleníti azokat a fő dimenziókat az Értékesítés kockában, amelyek szűrőként szolgálnak az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.

| Entitás           | Példák az attribútumok                               |
|------------------|------------------------------------------------------|
| Vevők        | Vevőcsoportok, vevőrégiók, cím, iparág |
| Termékek         | Termékszám, Termék neve, Cikkcsoportok neve       |
| Értékesítési kategóriák | Értékesítési kategóriák nevei                                 |
| Jogi személyek   | Jogi személyek nevei                                   |
| Dátumok            | Dátumok                                                |

Alapértelmezés szerint a tartalom a folyó naptári év adatait jeleníti meg. Azonban módosíthatja a dátumszűrőt a jelentésszűrők szakaszban. A vállalatszűrőt is módosíthatja.

