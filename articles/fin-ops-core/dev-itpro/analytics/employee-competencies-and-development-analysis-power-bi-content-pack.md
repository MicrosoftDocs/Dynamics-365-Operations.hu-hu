---
title: Alkalmazotti kompetenciák és fejlődés Power BI-tartalom
description: Ez a témakör az alkalmazott kompetenciáit és fejlesztési tartalmát írja Power BI le.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.openlocfilehash: 1ddc117c83e551374bc8da6872429e3bb9eeee58
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280958"
---
# <a name="employee-competencies-and-development-power-bi-content"></a>Alkalmazotti kompetenciák és fejlődés Power BI-tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör az alkalmazott kompetenciáit és fejlesztési tartalmát írja Power BI le. 

## <a name="reports-that-are-included-in-the-content-pack"></a>A tartalomcsomag által tartalmazott jelentések
Miután csatlakoztatta a tartalmi csomagot a rendszer adataihoz, a jelentések megjelenítik a szervezet adatait. Ha még soha nem használt Microsoft Power BI-t, többet megtudhat róla az [Irányított tanulás oldal a Power BI szolgáltatáshoz](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData) oldalon. A csomag által tartalmazott a jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                            | Tartalom                                               |
|-----------------------------------|--------------------------------------------------------|
| Kompetenciák és fejlődés elemzése | Csapattag-szakértelemtípusok és csapattag-szaktudások típus szerint |
| Szakértelemprofil                     | Szakértelemprofil kiválasztott alkalmazott számára                |
| Szakértelem-elemzés                    | Szakértelem típus és minősítés alapján                              |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lásd: [Irányítópult létrehozása és konfigurálása](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
Az Alkalmazotti kompetenciák és fejlődés tartalomcsomag jelentéseinek kitöltésére az alkalmazásadatok szolgálnak. A következő táblázat mutatja az entitásokat, amelyeken a csomag alapul.

| Entitás                            | Tartalom                                                                                                   | Más entitásokkal való kapcsolatok |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Munkaerő\_CalendarOffset         | Naptáreltolások, részletes jelentések                                                                          | |
| Munkaerő\_Vállalat                | Vállalatok a jelentések szűréséhez                                                                             | |
| Munkaerő\_Kompenzáció           | Fizetési díjalap és időbeli gyakoriság                                                                           | |
| Munkaerő\_CurrentCompensation    | Fizetési díjalap és gyakoriságát az aktuális dátum szerint                                                              | Munkaerő\_Vállalat, Munkaerő\_CurrentCompensation, Munkaerő\_Demográfia, Munkaerő\_Feladat, Munkaerő\_Beosztás |
| Munkaerő\_CurrentPosition        | Az aktuális dátum szerinti beosztások, teljes munkaidős egyenérték (FTE), nyitott beosztások és betöltésre váró beosztások | Munkaerő\_Feladat Munkaerő\_Beosztás |
| Munkaerő\_CurrentWorker          | Az aktuális dátum, kor és létszám szerinti dolgozók                                                         | Munkaerő\_Vállalat, Munkaerő\_Kompenzáció, Munkaerő\_GeographicLocation, Munkaerő\_Teljesítmény, Munkaerő\_PersonSkill, Munkaerő\_WorkerName, Munkaerő\_ReportsToWorkerName, Munkaerő\_WorkerTitle, Munkaerő\_Demográfia, Munkaerő\_Feladat, Munkaerő\_Foglalkoztatás, Munkaerő\_Beosztás |
| Munkaerő\_Dátum                   | Napok, hetek, hónapok és évek                                                                             | |
| Munkaerő\_Demográfia           | Születési idő, nemek, etnikaum és családi állapot                                                   | |
| Munkaerő\_Foglalkoztatás             | Kezdő dátum, záró dátum és átállási dátum                                                                  | |
| Munkaerő\_GeographicLocation     | Város, megye, irányítószám és állam vagy megye                                                           | |
| Munkaerő\_Feladat                    | Funkció, típus és a cím                                                                                  | |
| Munkaerő\_JobPreferredSkill      | Fontosság, minősítés, szakértelem és szakértelem szintje                                                                 | Munkaerő\_Szakértelem, Munkaerő\_Feladat |
| Munkaerő\_PastPositionAssignment | Kijelölés oka, kezdő dátum, záró dátum és feladat                                                           | Munkaerő\_CalendarOffset, Munkaerő\_Dátum, Munkaerő\_Feladat, Munkaerő\_Beosztás |
| Munkaerő\_Teljesítmény            | Minősítési, leírás és minősítési modell                                                                      | |
| Munkaerő\_PersonSkill            | Szint, szint dátuma és szakértelem                                                                               | Munkaerő\_Szakértelem |
| Munkaerő\_PersonSkillAnalysis    | Tanúsított, szint, szint dátuma és szakértelem                                                                    | Munkaerő\_WorkerName Munkaerő\_Szakértelem |
| Munkaerő\_Beosztás               | Részleg, FTE, beosztás, beosztás típusa és cím                                                        | |
| Munkaerő\_PositionTrend          | Beosztások az idők során, FTE és feladat                                                                          | Munkaerő\_CalendarOffset, Munkaerő\_Dátum, Munkaerő\_Feladat, Munkaerő\_Beosztás |
| Munkaerő\_ReportsToWorkerName    | Keresztnév, vezetéknév és teljes név                                                                       | |
| Munkaerő\_Szakértelem                  | Szakértelem, szakértelem típusa és minősítés                                                                              | |
| Munkaerő\_TerminatedWorker       | Kilépett dolgozók, kiléptetés dátuma, cím, beosztás és feladat                                             | Munkaerő\_Vállalat, Munkaerő\_Kompenzáció, Munkaerő\_GeographicLocation, Munkaerő\_Teljesítmény, Munkaerő\_WorkerName, Munkaerő\_ReportsToWorkerName, Munkaerő\_CalendarOffset, Munkaerő\_Dátum, Munkaerő\_WorkerTitle, Munkaerő\_Demográfia, Munkaerő\_Foglalkoztatás, Munkaerő\_Feladat, Munkaerő\_Beosztás |
| Munkaerő\_WorkerName             | Keresztnév, vezetéknév és teljes név                                                                       | |
| Munkaerő\_WorkerTitle            | Cím és szolgálati idő dátuma                                                                                   | |
| Munkaerő\_WorkerTrend             | Túlórázó dolgozók, létszám, vállalat és beosztás                                                        | Munkaerő\_Vállalat, Munkaerő\_Kompenzáció, Munkaerő\_GeographicLocation, Munkaerő\_Teljesítmény, Munkaerő\_WorkerName, Munkaerő\_ReportsToWorkerName, Munkaerő\_CalendarOffset, Munkaerő\_Dátum, Munkaerő\_WorkerTitle, Munkaerő\_Demográfia, Munkaerő\_Foglalkoztatás, Munkaerő\_Feladat |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
