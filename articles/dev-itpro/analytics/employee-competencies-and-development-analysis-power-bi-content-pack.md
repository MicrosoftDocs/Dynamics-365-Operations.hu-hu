---
title: "Alkalmazotti kompetenciák és fejlődés Power BI-tartalom"
description: "Ez a témakör a következőt ismerteti: Finance and Operations - Alkalmazotti kompetenciák és fejlődés Power BI-tartalom. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b2b3d96a64a552d1f0e0144dcbd809964fdf63c4
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="employee-competencies-and-development-power-bi-content"></a>Alkalmazotti kompetenciák és fejlődés Power BI-tartalom

[!include[banner](../includes/banner.md)]


Ez a témakör a következőt ismerteti: Finance and Operations - Alkalmazotti kompetenciák és fejlődés Power BI-tartalom. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

<a name="accessing-the-content-pack"></a>A tartalmi csomag elérése
--------------------------

Az Alkalmazotti kompetenciák és fejlődés tartalomcsomag a Microsoft Dynamics Lifecycle Services (LCS) Megosztott eszközök könyvtárban található. A tartalomcsomag letöltésére és a Microsoft Dynamics 365 for Finance and Operations adataival való összekapcsolásra vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>A tartalomcsomag által tartalmazott jelentések
Miután csatlakoztatta a tartalmi csomagot a Finance and Operations rendszer adataihoz, a jelentések megjelenítik a szervezet adatait. Ha még soha nem használt Microsoft Power BI-t, többet megtudhat róla az [Irányított tanulás a Power BI-hez oldalon](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). A csomag által tartalmazott a jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                            | Tartalom                                               |
|-----------------------------------|--------------------------------------------------------|
| Kompetenciák és fejlődés elemzése | Csapattag-szakértelemtípusok és csapattag-szaktudások típus szerint |
| Szakértelemprofil                     | Szakértelemprofil kiválasztott alkalmazott számára                |
| Szakértelem-elemzés                    | Szakértelem típus és minősítés alapján                              |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
Az Alkalmazotti kompetenciák és fejlődés tartalomcsomag jelentéseinek feltöltésére a Finance and Operations adatok szolgálnak. A következő táblázat mutatja az entitásokat, amelyeken a csomag alapul.

| Entitás                            | Tartalom                                                                                                   | Más entitásokkal való kapcsolatok                                                                                                                                                                                                                                                                       |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Munkaerő\_CalendarOffset         | Naptáreltolások, részletes jelentések                                                                          |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_Vállalat                | Vállalatok a jelentések szűréséhez                                                                             |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_Kompenzáció           | Fizetési díjalap és időbeli gyakoriság                                                                           |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_CurrentCompensation    | Fizetési díjalap és gyakoriságát az aktuális dátum szerint                                                              | Munkaerő\_Vállalat Munkaerő\_CurrentCompensation Munkaerő\_Demográfia Munkaerő\_Feladat Munkaerő\_Beosztás                                                                                                                                                                                            |
| Munkaerő\_CurrentPosition        | Az aktuális dátum szerinti beosztások, teljes munkaidős egyenérték (FTE), nyitott beosztások és betöltésre váró beosztások | Munkaerő\_Feladat Munkaerő\_Beosztás                                                                                                                                                                                                                                                                      |
| Munkaerő\_CurrentWorker          | Az aktuális dátum, kor és létszám szerinti dolgozók                                                         | Munkaerő\_Vállalat Munkaerő\_Kompenzáció Munkaerő\_GeographicLocation Munkaerő\_Teljesítmény Munkaerő\_PersonSkill Munkaerő\_WorkerName Munkaerő\_ReportsToWorkerName Munkaerő\_WorkerTitle Munkaerő\_Demográfia Munkaerő\_Feladat Munkaerő\_Foglalkoztatás Munkaerő\_Beosztás                     |
| Munkaerő\_Dátum                   | Napok, hetek, hónapok és évek                                                                             |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_Demográfia           | Születési idő, nemek, etnikaum és családi állapot                                                   |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_Foglalkoztatás             | Kezdő dátum, záró dátum és átállási dátum                                                                  |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_GeographicLocation     | Város, megye, irányítószám és állam vagy megye                                                           |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_Feladat                    | Funkció, típus és a cím                                                                                  |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_JobPreferredSkill      | Fontosság, minősítés, szakértelem és szakértelem szintje                                                                 | Munkaerő\_Szakértelem Munkaerő\_Feladat                                                                                                                                                                                                                                                                         |
| Munkaerő\_PastPositionAssignment | Kijelölés oka, kezdő dátum, záró dátum és feladat                                                           | Munkaerő\_CalendarOffset Munkaerő\_Dátum Munkaerő\_Feladat Munkaerő\_Beosztás                                                                                                                                                                                                                            |
| Munkaerő\_Teljesítmény            | Minősítési, leírás és minősítési modell                                                                      |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_PersonSkill            | Szint, szint dátuma és szakértelem                                                                               | Munkaerő\_Szakértelem                                                                                                                                                                                                                                                                                        |
| Munkaerő\_PersonSkillAnalysis    | Tanúsított, szint, szint dátuma és szakértelem                                                                    | Munkaerő\_WorkerName Munkaerő\_Szakértelem                                                                                                                                                                                                                                                                  |
| Munkaerő\_Beosztás               | Részleg, FTE, beosztás, beosztás típusa és cím                                                        |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_PositionTrend          | Beosztások az idők során, FTE és feladat                                                                          | Munkaerő\_CalendarOffset Munkaerő\_Dátum Munkaerő\_Feladat Munkaerő\_Beosztás                                                                                                                                                                                                                            |
| Munkaerő\_ReportsToWorkerName    | Keresztnév, vezetéknév és teljes név                                                                       |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_Szakértelem                  | Szakértelem, szakértelem típusa és minősítés                                                                              |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_TerminatedWorker       | Kilépett dolgozók, kiléptetés dátuma, cím, beosztás és feladat                                             | Munkaerő\_Vállalat Munkaerő\_Kompenzáció Munkaerő\_GeographicLocation Munkaerő\_Teljesítmény Munkaerő\_WorkerName Munkaerő\_ReportsToWorkerName Munkaerő\_CalendarOffset Munkaerő\_Dátum Munkaerő\_WorkerTitle Munkaerő\_Demográfia Munkaerő\_Foglalkoztatás Munkaerő\_Feladat Munkaerő\_Beosztás |
| Munkaerő\_WorkerName             | Keresztnév, vezetéknév és teljes név                                                                       |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_WorkerTitle            | Cím és szolgálati idő dátuma                                                                                   |                                                                                                                                                                                                                                                                                                         |
| Munkaerő\_WorkerTrend             | Túlórázó dolgozók, létszám, vállalat és beosztás                                                        | Munkaerő\_Vállalat Munkaerő\_Kompenzáció Munkaerő\_GeographicLocation Munkaerő\_Teljesítmény Munkaerő\_WorkerName Munkaerő\_ReportsToWorkerName Munkaerő\_CalendarOffset Munkaerő\_Dátum Munkaerő\_WorkerTitle Munkaerő\_Demográfia Munkaerő\_Foglalkoztatás Munkaerő\_Feladat                     |

Ezeket az entitásokat számított mértékek létrehozására használták az adatmodellben. E kiszámított mértékek aztán a fő teljesítménymutatók (KPI-k) és a tartalmi csomagban használt jelentések kiszámításához használatosak. Ha szeretné felvenni a további számításokat a jelentésekbe és irányítópultokba, töltse le és módosítsa a CompetenciesandDevelopment.pbix fájlt a LCS-ből. Ez a fájl azon alapértelmezett adatmodell, amelyet a tartalmi csomag létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmi csomagot és a felvett adatokat tartalmazó irányítópultot hozhat létre.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





