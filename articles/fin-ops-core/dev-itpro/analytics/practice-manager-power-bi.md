---
title: Gyakorlatkezelés Power BI tartalom
description: Ez a cikk a gyakorlatvezető tartalmának tartalmát írja Power BI le.
author: sericks007
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.assetid: ''
ms.search.form: ProjManagementWorkspace
ms.openlocfilehash: 92c2881c89da0b23e3a66c0f8bbcafd91c38c6e3
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206504"
---
# <a name="practice-manager-power-bi-content"></a>Gyakorlatkezelés Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a cikk a gyakorlatvezető **tartalmának tartalmát írja** Microsoft Power BI le. Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához korábban használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

A **Gyakorlatvezető** Power BI tartalom gyakorlatvezetők és projektvezetők számára készült. Olyan fontos mutatókat biztosít, amelyek a szervezetnél futó projektekkel kapcsolatosak. Az irányítópult áttekintést nyújt a projektekről és a kapcsolódó ügyfelekről. A jelentésszintű szűrők segítségével jelentés készíthető a meghatározott jogi személyekhez. Ez a Power BI tartalom adatokat kér le a projektkönyvelés összetett méréseitől.

A **Gyakorlatvezető** Power BI tartalom öt jelentésoldalt tartalmaz: egy áttekintő oldalt és négy olyan oldalt, amely a projekt költségeinek, bevételeinek, jelenérték-kezelésének és órainak mutatóira vonatkozó részleteket tartalmaz, amelyek különböző dimenziók szerint vannak lebontva.

A tartalom minden összege a rendszer pénznemében jelenik meg. Beállíthatja az rendszer alapértelmezett pénznemét a **Rendszerparaméterek** oldalon.

## <a name="accessing-the-power-bi-content"></a>A Power BI tartalom elérése

A **Gyakorlatkezelés** Power BI tartalom a **Projektvezetés** munkaterületen látható.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Jelentések, amelyek a Power BI-tartalomban szerepelnek

A következő táblázat ismerteti a **Gyakorlatvezető** Power BI-tartalom egyes jelentésoldalain található mutatókat.

| Jelentéslap       | Mutatók |
|-------------------|---------|
| Projektek áttekintése | <ul><li>Létrehozott projektek</li><li>Becsült projektek</li><li>Folyamatban lévő projektek</li><li>Tényleges bevétel vevő szerint</li><li>Költségvetés – bruttó nyereség projekt szerint</li><li>Jelenérték-kezelés áttekintése</li></ul> |
| Költség              | <ul><li>Tényleges és költségvetési költség havonta</li><li>Tényleges és költségvetési költség évente</li><li>Tényleges és költségvetési költség kategóriánként</li><li>Tényleges költség tranzakciótípus szerint</li></ul> |
| Bevétel           | <ul><li>Tényleges bevétel hónap szerint</li><li>Tényleges bevétel irányítószám szerint</li><li>Tényleges és költségvetési bevétel kategória szerint</li><li>Tényleges bevétel vevői iparág szerint</li></ul> |
| EVM               | Költség- és ütemezésteljesítmény-index projekt szerint |
| óra             | <ul><li>Tényleges számlázható hasznos órák és tényleges számlázható haszontalan órák és költségvetési órák</li><li>Tényleges számlázható hasznos órák és tényleges számlázható haszontalan órák projekt szerint</li><li>Tényleges számlázható hasznos órák és tényleges számlázható haszontalan órák erőforrás szerint</li><li>Tényleges számlázható órák aránya projekt szerint.</li><li>Tényleges számlázható órák aránya erőforrás szerint.</li></ul> |

Az összes ilyen jelentésben szereplő diagramot és a lapot ki lehet szűrni és rögzíteni lehet az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lásd: [Irányítópult létrehozása és konfigurálása](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Használhatja a Mögöttes adatok exportálása funkciót is azoknak a mögöttes adatoknak az exportálásához, amelyeknek összegzése egy ábrán látható.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

A **Gyakorlatvezető** Power BI tartalom jelentési oldalainak feltöltésére a következő adatok szolgálnak. Ezeket az adatokat az Entitástárban lebonyolított összesített mérések jelenítik meg. Az entitástár az analitikai célokra optimalizált Microsoft SQL Server adatbázisa. További tudnivalókért lásd: [Power BI integrációja az entitástárral](power-bi-integration-entity-store.md).

A következő szakaszok leírják az egyes entitások által használt összesített mértékeket.

### <a name="entity-projectaccountingcube_actualhourutilization"></a>Entitás: ProjectAccountingCube\_ActualHourUtilization
**Adatforrás:** ProjEmplTrans

| Fő összesítő mérték      | Mező                              | Leírás |
|--------------------------------|------------------------------------|-------------|
| Tényleges számlázható hasznos órák száma | Sum(ActualUtilizationBillableRate) | A ténylegesen számlázható felhasznált órák száma. |
| Tényleges számlázható haszontalan idő   | Sum(ActualBurdenBillableRate)      | Összes tényleges haszontalan idő aránya. |

### <a name="entity-projectaccountingcube_actuals"></a>Entitás: ProjectAccountingCube\_Actuals
**Adatforrás:** ProjTransPosting

| Fő összesítő mérték | Mező              | Leírás |
|---------------------------|--------------------|-------------|
| Tényleges bevétel            | Sum(ActualRevenue) | Az összes tranzakció összes feladott bevétele. |
| Tényleges költség               | Sum(ActualCost)    | Az összes tranzakciótípus összes feladott költsége. |

### <a name="entity-projectaccountingcube_customer"></a>Entitás: ProjectAccountingCube\_Customer
**Adatforrás:** CustTable

| Fő összesítő mérték | Mező                                             | Leírás |
|---------------------------|---------------------------------------------------|-------------|
| Projektek száma        | COUNTA(ProjectAccountingCube\_Projects\[PROJECTS\]) | Elérhető projektek száma. |

### <a name="entity-projectaccountingcube_forecasts"></a>Entitás: ProjectAccountingCube\_Forecasts
**Adatforrás:** ProjTransBudget

| Fő összesítő mérték | Mező                  | Leírás |
|---------------------------|------------------------|-------------|
| Előirányzott költség               | Sum(BudgetCost)        | Az összes tranzakciótípus összes előrejelzett költsége. |
| Tényleges bevétel            | Sum(BudgetRevenue)     | A megvalósult/számlázott bevétel előrejelzett összege. |
| Előirányzott bruttó nyereség       | Sum(BudgetGrossMargin) | Különbség az összes előrejelzett bevétel összege és az összes előrejelzett költség összege között. |

### <a name="entity-projectaccountingcube_projectplancostsview"></a>Entitás: ProjectAccountingCube\_ProjectPlanCostsView
**Adatforrás:** Projekt

| Fő összesítő mérték | Mező                    | Leírás |
|---------------------------|--------------------------|-------------|
| Tervezett költség              | Sum(SumOfTotalCostPrice) | Tervezett feladatokkal rendelkező projekttranzakció-típus becsléseinek teljes önköltségi ára. |

### <a name="entity-projectaccountingcube_projects"></a>Entitás: ProjectAccountingCube\_Projects
**Adatforrás:** Projekt

| Fő összesítő mérték    | Mező | Leírás |
|------------------------------|-------|-------------|
| Költségteljesítmény-index       | ProjectAccountingCube\_Projects\[Jelenérték\] ÷ ProjectAccountingCube\_Projects\[A végrehajtott feladatok összes tényleges költsége\] | Az összes bevétel osztva az összes tényleges költséggel. |
| Teljesítményindex ütemezése   | ProjectAccountingCube\_Projects\[Jelenérték\] ÷ ProjectAccountingCube\_Projects\[A végrehajtott feladatok összes tervezett költsége\] | Az összes bevétel osztva az összes tervezett költséggel. |
| A már befejezett munka százaléka. | Befejezett munka százaléka = ProjectAccountingCube\_Projects\[A végrehajtott feladatok összes tényleges költsége\] / (ProjectAccountingCube\_Projects\[A végrehajtott feladatok összes tényleges költsége\] + ProjectAccountingCube\_Projects\[Projekt összes tervezett költsége\] - ProjectAccountingCube\_Projects\[A végrehajtott feladatok összes tervezett költsége\]) | A végrehajtott munka összesített százaléka a végrehajtott feladat tényleges költsége és a projekt tervezett költsége alapján. |
| Tényleges számlázható órák aránya  | ProjectAccountingCube\_Projects\[Projekt összes ténylegesen számlázható hasznos ideje\] / (ProjectAccountingCube\_Projects\[Projekt összes ténylegesen számlázható hasznos ideje\] + ProjectAccountingCube\_Projects\[Projekt összes ténylegesen számlázható haszontalan ideje\]) | Tényleges számlázható órák összesen a hasznos órák és a haszontalan idő alapján. |
| Jelenérték                 | ProjectAccountingCube\_Projects\[Projekt összes tervezett költsége\] * ProjectAccountingCube\_Projects\[A már befejezett munka százaléka\] | Összes tervezett költség szorozva a végrehajtott munka százalékával. |

### <a name="entity-projectaccountingcube_totalestimatedcosts"></a>Entity: ProjectAccountingCube\_TotalEstimatedCosts 
**Adatforrás:** ProjTable

| Fő összesítő mérték       | Mező               | Leírás |
|---------------------------------|---------------------|-------------|
| Befejeződött tevékenység tervezett költsége | Sum(TotalCostPrice) | Befejeződött feladatokkal rendelkező projekttranzakció-típus becsléseinek teljes önköltségi ára. |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
