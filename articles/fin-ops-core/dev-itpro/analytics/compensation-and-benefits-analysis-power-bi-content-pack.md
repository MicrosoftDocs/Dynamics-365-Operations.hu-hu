---
title: Kompenzációk és Juttatások Power BI tartalom
description: Ez a témakör a Kompenzáció és juttatások tartalmát Power BI írja le.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bed0e8ffbd23c6793c037bade218f637105734b8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908619"
---
# <a name="compensation-and-benefits-power-bi-content"></a>Kompenzációk és Juttatások Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör a Kompenzáció és juttatások tartalmát Power BI írja le. 

## <a name="reports-that-are-included-in-the-content-pack"></a>A tartalomcsomag által tartalmazott jelentések
Miután csatlakoztatta a tartalmi csomagot a rendszer adataihoz, a jelentések megjelenítik a szervezet adatait. Ha még soha nem használt Microsoft Power BI-t, többet megtudhat róla az [Irányított tanulás oldal a Power BI szolgáltatáshoz](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData) oldalon. A csomag által tartalmazott a jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                     | Tartalom                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Kompenzáció és juttatások elemzése | Órabéres és bérezéses alkalmazottak vállalatonként, átlagos órabér, átlagos bér, alkalmazottak foglalkoztatási típus és tervben való részvétel alapján |
| Alkalmazotti juttatások          | Alkalmazotti részvétel kijelölt juttatás alapján                                                                                               |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lásd: [Irányítópult létrehozása és konfigurálása](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A Kompenzáció és juttatások tartalomcsomag jelentéseinek feltöltésére az alkalmazásadatok szolgálnak. A következő táblázat mutatja az entitásokat, amelyeken a csomag alapul.

| Entitás                            | Tartalom                                                                                                   | Más entitásokkal való kapcsolatok |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Munkaerő\_CalendarOffset         | Naptáreltolások, részletes jelentések                                                                          | Munkaerő\_PastPositionAssignment Munkaerő\_PositionTrend Workorce\_WorkerTrend Munkaerő\_TerminatedWorker |
| Munkaerő\_Vállalat                | Vállalatok a jelentések szűréséhez                                                                             | Munkaerő\_CurrentCompensation Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend |
| Munkaerő\_Kompenzáció           | Fizetési díjalap és időbeli gyakoriság                                                                           | Munkaerő\_CurrentCompensation Munkaerő\_CurrentWorker Munkaerő\_TerminatedWorker Munkaerő\_WorkerTrend |
| Munkaerő\_CurrentCompensation    | Fizetési díjalap és gyakoriságát az aktuális dátum szerint                                                              | Munkaerő\_Vállalat, Munkaerő\_Kompenzáció, Munkaerő\_Demográfia, Munkaerő\_Feladat, Munkaerő\_Beosztás |
| Munkaerő\_CurrentPosition        | Az aktuális dátum szerinti beosztások, teljes munkaidős egyenérték (FTE), nyitott beosztások és betöltésre váró beosztások | Munkaerő\_Feladat, Munkaerő\_Beosztás |
| Munkaerő\_CurrentWorker          | Az aktuális dátum, kor és létszám szerinti dolgozók                                                         | Munkaerő\_Vállalat, Munkaerő\_Kompenzáció, Munkaerő\_GeographicLocation, Munkaerő\_Teljesítmény, Munkaerő\_WorkerName, Munkaerő\_ReportsToWorkerName, Munkaerő\_WorkerTitle, Munkaerő\_Demográfia, Munkaerő\_Feladat, Munkaerő\_Foglalkoztatás, Munkaerő\_Beosztás, Munkaerő\_WorkerBenefit |
| Munkaerő\_Dátum                   | Napok, hetek, hónapok és évek                                                                             | Munkaerő\_PastPositionAssignment, Munkaerő\_PositionTrend, Workorce\_WorkerTrend, Munkaerő\_TerminatedWorker |
| Munkaerő\_Demográfia           | Születési idő, nemek, etnikaum és családi állapot                                                   | Munkaerő\_CurrentWorker, Munkaerő\_TerminatedWorker, Munkaerő\_WorkerTrend |
| Munkaerő\_Foglalkoztatás             | Kezdő dátum, záró dátum és átállási dátum                                                                  | Munkaerő\_CurrentWorker, Munkaerő\_TerminatedWorker, Munkaerő\_WorkerTrend |
| Munkaerő\_GeographicLocation     | Város, megye, irányítószám és állam vagy megye                                                           | Munkaerő\_CurrentWorker, Munkaerő\_TerminatedWorker, Munkaerő\_WorkerTrend |
| Munkaerő\_Feladat                    | Funkció, típus és a cím                                                                                  | Munkaerő\_CurrentPosition, Munkaerő\_CurrentWorker |
| Munkaerő\_PastPositionAssignment | Kijelölés oka, kezdő dátum, záró dátum és feladat                                                           | Munkaerő\_CalendarOffset, Munkaerő\_Dátum, Munkaerő\_Feladat, Munkaerő\_Beosztás |
| Munkaerő\_Teljesítmény            | Minősítési, leírás és minősítési modell                                                                      | Munkaerő\_CurrentWorker, Munkaerő\_TerminatedWorker, Munkaerő\_WorkerTrend |
| Munkaerő\_Beosztás               | Részleg, FTE, beosztás, beosztás típusa és cím                                                        | Munkaerő\_CurrentPosition, Munkaerő\_CurrentWorker |
| Munkaerő\_PositionTrend          | Beosztások az idők során, FTE és feladat                                                                          | Munkaerő\_CalendarOffset, Munkaerő\_Dátum, Munkaerő\_Feladat, Munkaerő\_Beosztás |
| Munkaerő\_ReportsToWorkerName    | Keresztnév, vezetéknév és teljes név                                                                       | Munkaerő\_CurrentWorker, Munkaerő\_TerminatedWorker, Munkaerő\_WorkerTrend |
| Munkaerő\_Szakértelem                  | Szakértelem, szakértelem típusa és minősítés                                                                              | |
| Munkaerő\_TerminatedWorker       | Kilépett dolgozók, kiléptetés dátuma, cím, beosztás és feladat                                             | Munkaerő\_Vállalat, Munkaerő\_Kompenzáció, Munkaerő\_GeographicLocation, Munkaerő\_Teljesítmény, Munkaerő\_WorkerName, Munkaerő\_ReportsToWorkerName, Munkaerő\_CalendarOffset, Munkaerő\_Dátum, Munkaerő\_WorkerTitle, Munkaerő\_Demográfia, Munkaerő\_Foglalkoztatás, Munkaerő\_Feladat, Munkaerő\_Beosztás, Munkaerő\_WorkerBenefit |
| Munkaerő\_WorkerBenefit          | Hatálybalépés, juttatási lehetőség, juttatási konstrukció és juttatási típus                                             | Munkaerő\_CurrentWorker, Munkaerő\_TerminatedWorker, Munkaerő\_WorkerTrend |
| Munkaerő\_WorkerName             | Keresztnév, vezetéknév és teljes név                                                                       | Munkaerő\_CurrentWorker, Munkaerő\_TerminatedWorker, Munkaerő\_WorkerTrend |
| Munkaerő\_WorkerTitle            | Cím és szolgálati idő dátuma                                                                                   | Munkaerő\_CurrentWorker, Munkaerő\_TerminatedWorker, Munkaerő\_WorkerTrend |
| Munkaerő\_WorkerTrend            | Túlórázó dolgozók, létszám, vállalat és beosztás                                                        | Munkaerő\_Vállalat, Munkaerő\_Kompenzáció, Munkaerő\_GeographicLocation, Munkaerő\_Teljesítmény, Munkaerő\_WorkerName, Munkaerő\_ReportsToWorkerName, Munkaerő\_CalendarOffset, Munkaerő\_Dátum, Munkaerő\_WorkerTitle, Munkaerő\_Demográfia, Munkaerő\_Foglalkoztatás, Munkaerő\_Feladat, Munkaerő\_WorkerBenefit |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]