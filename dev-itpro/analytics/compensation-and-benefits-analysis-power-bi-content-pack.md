---
title: "Kompenzáció és juttatások Power BI-tartalom"
description: "Ez a témakör a következőt ismerteti: Dynamics 365 for Operations - Kompenzáció és juttatások Power BI-tartalom. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 557f9218032e2b1160b6ea0631ada951353d2afd
ms.lasthandoff: 03/31/2017


---

# <a name="compensation-and-benefits-power-bi-content"></a>Kompenzáció és juttatások Power BI-tartalom

[!include[banner](../includes/banner.md)]


Ez a témakör a következőt ismerteti: Dynamics 365 for Operations - Kompenzáció és juttatások Power BI-tartalom. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

<a name="accessing-the-content-pack"></a>A tartalmi csomag elérése
--------------------------

A Kompenzáció és juttatások tartalomcsomag a Microsoft Dynamics Lifecycle Services (LCS) Megosztott eszközök könyvtárban található. A tartalomcsomag letöltésére és a Microsoft Dynamics 365 for Operations adataival való összekapcsolásra vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>A tartalomcsomag által tartalmazott jelentések
Miután csatlakoztatta a tartalmi csomagot a Dynamics 365 for Operations rendszer adataihoz, a jelentések megjelenítik a szervezet adatait. Ha még soha nem használt Microsoft Power BI-t, többet megtudhat róla az [Irányított tanulás a Power BI-hez oldalon](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). A csomag által tartalmazott a jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                     | Tartalom                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Kompenzáció és juttatások elemzése | Órabéres és bérezéses alkalmazottak vállalatonként, átlagos órabér, átlagos bér, alkalmazottak foglalkoztatási típus és tervben való részvétel alapján |
| Alkalmazotti juttatások          | Alkalmazotti részvétel kijelölt juttatás alapján                                                                                               |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A Kompenzáció és juttatások tartalomcsomag jelentéseinek feltöltésére a Dynamics 365 for Operations adatok szolgálnak. A következő táblázat mutatja az entitásokat, amelyeken a csomag alapul.

| Entitás                            | Tartalom                                                                                                   | Más entitásokkal való kapcsolatok                                                                                                                                                                                                                                                                                                |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Munkaerő\_CalendarOffset         | Naptáreltolások, részletes jelentések                                                                          | Munkaerő\_PastPositionAssignment Munkaerő\_PositionTrend Workorce\_WorkerTrend Munkaerő\_TerminatedWorker                                                                                                                                                                                                                     |
| Munkaerő\_Vállalat                | Vállalatok a jelentések szűréséhez                                                                             | Munkaerő\_CurrentCompensation Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                        |
| Munkaerő\_Kompenzáció           | Fizetési díjalap és időbeli gyakoriság                                                                           | Munkaerő\_CurrentCompensation Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                        |
| Munkaerő\_CurrentCompensation    | Fizetési díjalap és gyakoriságát az aktuális dátum szerint                                                              | Munkaerő\_Vállalat Munkaerő\_Kompenzáció Munkaerő\_Demográfia Munkaerő\_Feladat Munkaerő\_Beosztás                                                                                                                                                                                                                            |
| Munkaerő\_CurrentPosition        | Az aktuális dátum szerinti beosztások, teljes munkaidős egyenérték (FTE), nyitott beosztások és betöltésre váró beosztások | Munkaerő\_Feladat Munkaerő\_Beosztás                                                                                                                                                                                                                                                                                               |
| Munkaerő\_CurrentWorker          | Az aktuális dátum, kor és létszám szerinti dolgozók                                                         | Munkaerő\_Vállalat Munkaerő\_Kompenzáció Munkaerő\_GeographicLocation Munkaerő\_Teljesítmény Munkaerő\_WorkerName Munkaerő\_ReportsToWorkerName Munkaerő\_WorkerTitle Munkaerő\_Demográfia Munkaerő\_Feladat Munkaerő\_Foglalkoztatás Munkaerő\_Beosztás Munkaerő\_WorkerBenefit                                            |
| Munkaerő\_Dátum                   | Napok, hetek, hónapok és évek                                                                             | Munkaerő\_PastPositionAssignment Munkaerő\_PositionTrend Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                     |
| Munkaerő\_Demográfia           | Születési idő, nemek, etnikaum és családi állapot                                                   | Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_Foglalkoztatás             | Kezdő dátum, záró dátum és átállási dátum                                                                  | Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_GeographicLocation     | Város, megye, irányítószám és állam vagy megye                                                           | Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_Feladat                    | Funkció, típus és a cím                                                                                  | Munkaerő\_CurrentPosition Munkaerő\_CurrentWorker                                                                                                                                                                                                                                                                              |
| Munkaerő\_PastPositionAssignment | Kijelölés oka, kezdő dátum, záró dátum és feladat                                                           | Munkaerő\_CalendarOffset Munkaerő\_Dátum Munkaerő\_Feladat Munkaerő\_Beosztás                                                                                                                                                                                                                                                     |
| Munkaerő\_Teljesítmény            | Minősítési, leírás és minősítési modell                                                                      | Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_Beosztás               | Részleg, FTE, beosztás, beosztás típusa és cím                                                        | Munkaerő\_CurrentPosition Munkaerő\_CurrentWorker                                                                                                                                                                                                                                                                              |
| Munkaerő\_PositionTrend          | Beosztások az idők során, FTE és feladat                                                                          | Munkaerő\_CalendarOffset Munkaerő\_Dátum Munkaerő\_Feladat Munkaerő\_Beosztás                                                                                                                                                                                                                                                     |
| Munkaerő\_ReportsToWorkerName    | Keresztnév, vezetéknév és teljes név                                                                       | Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_Szakértelem                  | Szakértelem, szakértelem típusa és minősítés                                                                              |                                                                                                                                                                                                                                                                                                                                  |
| Munkaerő\_TerminatedWorker       | Kilépett dolgozók, kiléptetés dátuma, cím, beosztás és feladat                                             | Munkaerő\_Vállalat Munkaerő\_Kompenzáció Munkaerő\_GeographicLocation Munkaerő\_Teljesítmény Munkaerő\_WorkerName Munkaerő\_ReportsToWorkerName Munkaerő\_CalendarOffset Munkaerő\_Dátum Munkaerő\_WorkerTitle Munkaerő\_Demográfia Munkaerő\_Foglalkoztatás Munkaerő\_Feladat Munkaerő\_Beosztás Munkaerő\_WorkerBenefit |
| Munkaerő\_WorkerBenefit          | Hatálybalépés, juttatási lehetőség, juttatási konstrukció és juttatási típus                                             | Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_WorkerName             | Keresztnév, vezetéknév és teljes név                                                                       | Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_WorkerTitle            | Cím és szolgálati idő dátuma                                                                                   | Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_WorkerTrend             | Túlórázó dolgozók, létszám, vállalat és beosztás                                                        | Munkaerő\_Vállalat Munkaerő\_Kompenzáció Munkaerő\_GeographicLocation Munkaerő\_Teljesítmény Munkaerő\_WorkerName Munkaerő\_ReportsToWorkerName Munkaerő\_CalendarOffset Munkaerő\_Dátum Munkaerő\_WorkerTitle Munkaerő\_Demográfia Munkaerő\_Foglalkoztatás Munkaerő\_Feladat Munkaerő\_WorkerBenefit                     |

Ezeket az entitásokat számított mértékek létrehozására használták az adatmodellben. E kiszámított mértékek aztán a fő teljesítménymutatók (KPI-k) és a tartalmi csomagban használt jelentések kiszámításához használatosak. Ha szeretné felvenni a további számításokat a jelentésekbe és irányítópultokba, töltse le és módosítsa a CompensationandBenefits.pbix fájlt a LCS-ből. Ez a fájl azon alapértelmezett adatmodell, amelyet a tartalmi csomag létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmi csomagot és a felvett adatokat tartalmazó irányítópultot hozhat létre.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





