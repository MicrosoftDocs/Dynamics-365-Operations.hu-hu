---
title: "Gyakorlatvezető Power BI tartalom"
description: "Ez a témakör azt ismerteti, mit tartalmaz a Gyakorlatvezető Power BI-tartalom modul. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
author: knelson
manager: AnnBe
ms.date: 04/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer/IT Pro
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.dyn365.intro: 2017/04/27
ms.dyn365.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0f2a1a9df8e5036c60b74b8a710e606b0b1e312a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="practice-manager-power-bi-content"></a>Gyakorlatvezető Power BI tartalom

[!include[banner](../includes/banner.md)]


Ez a témakör azt ismerteti, mit tartalmaz a **Gyakorlatvezető** Microsoft Power BI-tartalom modul. Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

A **Gyakorlatvezető** Power BI-tartalom gyakorlatvezetők és projektvezetők számára készült. Olyan fontos mutatókat biztosít, amelyek a szervezetnél futó projektekkel kapcsolatosak. Az irányítópult áttekintést nyújt a projektekről és a kapcsolódó ügyfelekről. A jelentésszintű szűrők segítségével jelentés készíthető a meghatározott jogi személyekhez. Ez a Power BI-tartalom adatokat kér le a projektkönyvelés összetett méréseitől a Microsoft Dynamics 365 for Operations számára.

A **Gyakorlatvezető** Power BI-tartalom öt jelentésoldalt tartalmaz: egy áttekintő oldalt és négy olyan oldalt, amely a projekt költségeinek, bevételeinek, jelenérték-kezelésének és órainak mutatóira vonatkozó részleteket tartalmaz, amelyek különböző dimenziók szerint vannak lebontva.

A tartalom minden összege a rendszer pénznemében jelenik meg. Beállíthatja az rendszer alapértelmezett pénznemét a **Rendszerparaméterek** oldalon.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése

A **Gyakorlatvezető** Power BI-tartalom a Microsoft Dynamics Lifecycle Services (LCS) megosztott eszközök könyvtárban található. A tartalomcsomag letöltésére és a Dynamics 365 for Operations adataival való összekapcsolásra vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md).

Ha meg szeretne tekinteni egy demót, amely bemutatja a Power BI-tartalmak megvalósítását, lásd a [Power BI-tartalom a Microsofttól és az Ön partnereitől a Dynamics Lifecycle Services szolgáltatásban](https://mix.office.com/watch/9puyb1b2xs1w) című részt (Office mix).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó jelentések

A következő táblázat ismerteti a **Gyakorlatvezető** Power BI-tartalom egyes jelentésoldalain található mutatókat.

| Jelentéslap                                          | Mutatók               |
|------------------------------------------------------|-----------------------------------------------|
| Irányítópult  | Létrehozott projektek<br>Becsült projektek<br>Folyamatban lévő projektek<br>Projektek száma szakasz szerint<br>Projektek száma város szerint<br>Tényleges bevétel vevő szerint<br>Költségvetés – bruttó nyereség projekt szerint<br>Jelenérték-kezelés áttekintése |
| Költség                                                 | Tényleges és költségvetési költség havonta<br>Tényleges és költségvetési költség évente<br>Tényleges és költségvetési költség kategóriánként<br>Tényleges költség tranzakciótípus szerint       |
| Bevétel                                              | Tényleges bevétel hónap szerint<br>Tényleges bevétel irányítószám szerint<br>Tényleges és költségvetési bevétel kategória szerint<br>Tényleges bevétel vevői iparág szerint        |
| EVM                                                  | Költség- és ütemezésteljesítmény-index projekt szerint                 |
| óra                                                | Tényleges számlázható hasznos órák és tényleges számlázható haszontalan órák és költségvetési órák<br>Tényleges számlázható hasznos órák és tényleges számlázható haszontalan órák projekt szerint<br>Tényleges számlázható hasznos órák és tényleges számlázható haszontalan órák erőforrás szerint<br>Tényleges számlázható órák aránya projekt szerint.<br>Tényleges számlázható órák aránya erőforrás szerint. |

Az összes ilyen jelentésben szereplő diagramot és a lapot ki lehet szűrni és rögzíteni lehet az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozása és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/) lehetőségre. Használhatja a Mögöttes adatok exportálása funkciót is azoknak a mögöttes adatoknak az exportálásához, amelyeknek összegzése egy ábrán látható.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

A **Gyakorlatvezető** Power BI-tartalom jelentési oldalainak feltöltésére a Dynamics 365 for Operations adatai szolgálnak. Ezek az adatok az entitástárban előkészített összesített mérések formájában jelennek meg - az entitástár egy elemzési célra optimalizált Microsoft SQL-adatbázis. További tudnivalókért lásd: [Az entitástár és a Power BI integrációjának áttekintése](power-bi-integration-entity-store.md).

A következő szakaszok az egyes entitás által használt összesített mértékeket mutatják be.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Entitás: ProjectAccountingCube_ActualHourUtilization
**Adatforrás**: ProjEmplTrans

| Fő összesítő mérték                | Mező                                | Leírás                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualBillableUtilizedHours              | Sum(ActualUtilizationBillableRate)   | A ténylegesen számlázható felhasznált órák száma |
| ActualBillableBurdenHours                | Sum(ActualBurdenBillableRate)        | Összes tényleges haszontalan idő aránya             |

### <a name="entity-projectaccountingcubeactuals"></a>Entitás: ProjectAccountingCube_Actuals
**Adatforrás**: ProjTransPosting

| Fő összesítő mérték                | Mező                                | Leírás                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualRevenue                            |     Sum(ActualRevenue)               |  Az összes tranzakció összes feladott bevétele |   
| ActualCost   |                             Sum(ActualCost)           |    Az összes tranzakciótípus összes feladott költsége    |

### <a name="entity-projectaccountingcubecustomer"></a>Entitás: ProjectAccountingCube_Customer
**Adatforrás**: CustTable

| Fő összesítő mérték                | Mező                                | Leírás                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    Projektek száma        |   COUNTA(ProjectAccountingCube_Projects[PROJECTS])       |         Elérhető projektek száma    |


### <a name="entity-projectaccountingcubeforecasts"></a>Entitás: ProjectAccountingCube_Forecasts
**Adatforrás**: ProjTransBudget

| Fő összesítő mérték                | Mező                                | Leírás                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    BudgetCost    |       Sum(BudgetCost)  |       Az összes tranzakciótípus összes előrejelzett költsége     |
|     BudgetRevenue    |         Sum(BudgetRevenue)    |    A megvalósult/számlázott bevétel előrejelzett összege         |
|BudgetGrossMargin | Sum(BudgetGrossMargin) |Különbség az összes előrejelzett bevétel összege és az összes előrejelzett költség összege között

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Entitás: ProjectAccountingCube_ProjectPlanCostsView
**Adatforrás**: Projekt

| Fő összesítő mérték                | Mező                                | Leírás                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|      PlannedCost      |        Sum(SumOfTotalCostPrice)   | Tervezett feladatok minden projekttranzakció-típus becsléseinél, teljes önköltségi ár |

### <a name="entity-projectaccountingcubeprojects"></a>Entitás: ProjectAccountingCube_Projects
**Adatforrás**: Projekt

| Fő összesítő mérték                | Mező                                | Leírás                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|   Költségteljesítmény-index  |ProjectAccountingCube_Projects[Earned value] / ProjectAccountingCube_Projects[A végrehajtott feladatok összes tényleges költsége] |     Az összes bevétel osztva az összes tényleges költséggel|
|  Teljesítményindex ütemezése |ProjectAccountingCube_Projects[Earned value] / ProjectAccountingCube_Projects[A végrehajtott feladatok összes tervezett költsége]|Az összes bevétel osztva az összes tervezett költséggel |
|A már befejezett munka százaléka. |Befejezett munka százaléka = ProjectAccountingCube_Projects[A végrehajtott feladatok összes tényleges költsége] / (ProjectAccountingCube_Projects[A végrehajtott feladatok összes tényleges költsége] + ProjectAccountingCube_Projects[Projekt összes tervezett költsége] - ProjectAccountingCube_Projects[A végrehajtott feladatok összes tervezett költsége])|A végrehajtott munka összesített százaléka a végrehajtott feladat tényleges költsége és a projekt tervezett költsége alapján|
|Projekt tényleges számlázható óráinak aránya|ProjectAccountingCube_Projects[Projekt összes ténylegesen számlázható hasznos ideje] / (ProjectAccountingCube_Projects[Projekt összes ténylegesen számlázható hasznos ideje] + ProjectAccountingCube_Projects[Projekt összes ténylegesen számlázható haszontalan ideje])|Tényleges számlázható órák összesen a kihasználtság + terhelés alapján|
|Jelenérték|ProjectAccountingCube_Projects[Projekt összes tervezett költsége] * ProjectAccountingCube_Projects[A már befejezett munka százaléka]|Összes tervezett költség szorozva a végrehajtott munka százalékával|

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Entitás: ProjectAccountingCube_TotalEstimatedCosts 
**Adatforrás**: ProjTable

| Fő összesítő mérték                | Mező                                | Leírás                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| CompletedActivityPlannedCost  |  Sum(TotalCostPrice)  |   Végrehajtott feladatok minden projekttranzakció-típus becsléseinél, teljes önköltségi ár|

## <a name="additional-resources"></a>További erőforrások

Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

- [Adatentitások](/dynamics365/operations/dev-itpro/data-entities/data-entities)
- [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [A munkaterületek Power BI-integrációjának beállítása](configure-power-bi-integration.md)

