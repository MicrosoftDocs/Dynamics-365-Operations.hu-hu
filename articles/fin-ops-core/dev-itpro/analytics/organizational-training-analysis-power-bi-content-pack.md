---
title: Szervezeti képzés Power BI tartalom
description: Ez a témakör a pénzügyeket és műveleteket írja le – szervezeti képzési Power BI tartalom.
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
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.openlocfilehash: 2e80810dbeb536dccf6e13b5fca6a85f4858d8da
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267242"
---
# <a name="organizational-training-power-bi-content"></a>Szervezeti képzés Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör a pénzügyeket és műveleteket írja le – szervezeti képzési Power BI tartalom.

## <a name="reports-that-are-included-in-the-content-pack"></a>A tartalomcsomag által tartalmazott jelentések
Miután csatlakoztatta a tartalmi csomagot a rendszer adataihoz, a jelentések megjelenítik a szervezet adatait. Ha még soha nem használt Microsoft Power BI-t, többet megtudhat róla az [Irányított tanulás oldal a Power BI szolgáltatáshoz](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData) oldalon. A csomag által tartalmazott a jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés          | Tartalom                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Tanfolyamelemzés | Regisztráció hely alapján, tanfolyami résztvevők állapot szerint és regisztrációs lista |
| Tanfolyamtípusok    | Tanfolyamtípusok szakértelem szerint                                                       |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lásd: [Irányítópult létrehozása és konfigurálása](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A Szervezeti képzés tartalomcsomag jelentéseinek kitöltésére az alkalmazásadatok szolgálnak. A következő táblázat mutatja az entitásokat, amelyeken a csomag alapul.

| Entitás                    | Tartalom                                                         | Más entitásokkal való kapcsolatok |
|---------------------------|------------------------------------------------------------------|-----------------------------------|
| Képzés\_CalendarOffset  | Naptáreltolások, részletes jelentések                                | Képzés\_CourseAgenda, Képzés\_CourseAttendees |
| Képzés\_Vállalat         | Vállalatok a jelentések szűréséhez                                   | Képzés\_CourseAgenda, Képzés\_CourseAttendees |
| Képzés\_Tanfolyam          | Tanfolyam, leírás, oktató neve, hely, szoba és állapot | Képzés\_CourseAgenda, Képzés\_CourseAttendees, Képzés\_CourseSkill |
| Képzés\_CourseAgenda    | Napirend, tanfolyam, kezdő és záró időpontok                          | Képzés\_Vállalat, Képzés\_CalendarOffset, Képzés\_Dátum, Képzés\_Tanfolyam |
| Képzés\_CourseAttendees | Név, állapot, feladat és regisztráció dátuma                         | Képzés\_Vállalat, Képzés\_CalendarOffset, Training\_Dátum, Képzés\_Demográfia, Képzés\_Foglalkoztatás, Képzés\_Tanfolyam, Képzés\_WorkerName, Képzés\_WorkerTitle, Képzés\_Feladat, Képzés\_Beosztás |
| Képzés\_CourseSkill     | Szakértelem, szakértelem típusa és szintje                                     | Képzés\_Tanfolyam |
| Képzés\_Dátum            | Napok, hetek, hónapok és évek                                   | Képzés\_CourseAgenda, Képzés\_CourseAttendees |
| Képzés\_Demográfia    | Születési idő, nemek, etnikaum és családi állapot         | Képzés\_CourseAgenda, Képzés\_CourseAttendees |
| Képzés\_Foglalkoztatás      | Kezdő dátum, záró dátum és átállási dátum                        | Képzés\_CourseAgenda, Képzés\_CourseAttendees |
| Képzés\_Feladat             | Funkció, típus és a cím                                        | Képzés\_CourseAgenda, Képzés\_CourseAttendees |
| Képzés\_Beosztás        | Beosztás, cím és teljes munkaidős egyenérték (FTE)                  | Képzés\_CourseAgenda, Képzés\_CourseAttendees |
| Képzés\_WorkerName      | Keresztnév, vezetéknév és teljes név                             | Képzés\_CourseAttendees |
| Képzés\_WorkerTitle     | Cím és szolgálati idő dátuma                                         | Képzés\_CourseAttendees |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
