---
title: "Szervezeti képzés Power BI-tartalom"
description: "Ez a témakör a következőt ismerteti: Finance and Operations - Szervezeti képzés Power BI-tartalom. Elmagyarázza, hogy hogyan kell hozzáférni a tartalmi csomaghoz, és leírja a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 26499bf5423bc3711d110bd7e548eda238162b7a
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017

---

# <a name="organizational-training-power-bi-content"></a>Szervezeti képzés Power BI-tartalom

[!include[banner](../includes/banner.md)]


Ez a témakör a következőt ismerteti: Finance and Operations - Szervezeti képzés Power BI-tartalom. Elmagyarázza, hogy hogyan kell hozzáférni a tartalmi csomaghoz, és leírja a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

<a name="accessing-the-content-pack"></a>A tartalmi csomag elérése
--------------------------

A Szervezeti képzés tartalomcsomag a Microsoft Dynamics Lifecycle Services (LCS) megosztott eszközök könyvtárban található. A tartalomcsomag letöltésére és a Microsoft Dynamics 365 for Finance and Operations adataival való összekapcsolásra vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>A tartalomcsomag által tartalmazott jelentések
Miután csatlakoztatta a tartalmi csomagot a Finance and Operations rendszer adataihoz, a jelentések megjelenítik a szervezet adatait. Ha még soha nem használt Microsoft Power BI-t, többet megtudhat róla az [Irányított tanulás a Power BI-hez oldalon](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). A csomag által tartalmazott a jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés          | Tartalom                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Tanfolyamelemzés | Regisztráció hely alapján, tanfolyami résztvevők állapot szerint és regisztrációs lista |
| Tanfolyamtípusok    | Tanfolyamtípusok szakértelem szerint                                                       |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A Szervezeti képzés tartalomcsomag jelentéseinek feltöltésére a Finance and Operations adatok szolgálnak. A következő táblázat mutatja az entitásokat, amelyeken a csomag alapul.

| Entitás                    | Tartalom                                                         | Más entitásokkal való kapcsolatok                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Képzés\_CalendarOffset  | Naptáreltolások, részletes jelentések                                | Képzés\_CourseAgenda Képzés\_CourseAttendees                                                                                                                                                   |
| Képzés\_Vállalat         | Vállalatok a jelentések szűréséhez                                   | Képzés\_CourseAgenda Képzés\_CourseAttendees                                                                                                                                                   |
| Képzés\_Tanfolyam          | Tanfolyam, leírás, oktató neve, hely, szoba és állapot | Képzés\_CourseAgenda Training\_CourseAttendees Képzés\_CourseSkill                                                                                                                             |
| Képzés\_CourseAgenda    | Napirend, tanfolyam, kezdő és záró időpontok                          | Képzés\_Vállalat Képzés\_CalendarOffset Képzés\_Dátum Képzés\_Tanfolyam                                                                                                                         |
| Képzés\_CourseAttendees | Név, állapot, feladat és regisztráció dátuma                         | Képzés\_Vállalat Képzés\_CalendarOffset Training\_Dátum Képzés\_Demográfia Képzés\_Foglalkoztatás Képzés\_Tanfolyam Képzés\_WorkerName Képzés\_WorkerTitle Képzés\_Feladat Képzés\_Beosztás |
| Képzés\_CourseSkill     | Szakértelem, szakértelem típusa és szintje                                     | Képzés\_Tanfolyam                                                                                                                                                                                   |
| Képzés\_Dátum            | Napok, hetek, hónapok és évek                                   | Képzés\_CourseAgenda Képzés\_CourseAttendees                                                                                                                                                   |
| Képzés\_Demográfia    | Születési idő, nemek, etnikaum és családi állapot         | Képzés\_CourseAgenda Képzés\_CourseAttendees                                                                                                                                                   |
| Képzés\_Foglalkoztatás      | Kezdő dátum, záró dátum és átállási dátum                        | Képzés\_CourseAgenda Képzés\_CourseAttendees                                                                                                                                                   |
| Képzés\_Feladat             | Funkció, típus és a cím                                        | Képzés\_CourseAgenda Képzés\_CourseAttendees                                                                                                                                                   |
| Képzés\_Beosztás        | Beosztás, cím és teljes munkaidős egyenérték (FTE)                  | Képzés\_CourseAgenda Képzés\_CourseAttendees                                                                                                                                                   |
| Képzés\_WorkerName      | Keresztnév, vezetéknév és teljes név                             | Képzés\_CourseAttendees                                                                                                                                                                          |
| Képzés\_WorkerTitle     | Cím és szolgálati idő dátuma                                         | Képzés\_CourseAttendees                                                                                                                                                                          |

Ezeket az entitásokat számított mértékek létrehozására használták az adatmodellben. E kiszámított mértékek aztán a fő teljesítménymutatók (KPI-k) és a tartalmi csomagban használt jelentések kiszámításához használatosak. Ha szeretné felvenni a további számításokat a jelentésekbe és irányítópultokba, töltse le és módosítsa a Training.pbix fájlt a LCS-ből. Ez a fájl azon alapértelmezett adatmodell, amelyet a tartalmi csomag létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmi csomagot és a felvett adatokat tartalmazó irányítópultot hozhat létre.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





