---
title: "Szervezeti képzés kiemelt BI-tartalom"
description: "Ez a témakör ismerteti a Dynamics 365 műveletek - szervezeti képzés kiemelt BI-tartalom. Ismerteti, hogyan érhető el a csomagot, és a csomag létrehozásához használt entitások és adatmodell mutatja be."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 104164f8ffd0d2bc3a64bf15d2fb5213234046ce
ms.lasthandoff: 03/31/2017


---

# <a name="organizational-training-power-bi-content"></a>Szervezeti képzés kiemelt BI-tartalom

Ez a témakör ismerteti a Dynamics 365 műveletek - szervezeti képzés kiemelt BI-tartalom. Ismerteti, hogyan érhető el a csomagot, és a csomag létrehozásához használt entitások és adatmodell mutatja be.

<a name="accessing-the-content-pack"></a>A csomag elérése
--------------------------

A szervezeti képzési csomagot a megosztott eszközök a Microsoft Dynamics életciklus szolgáltatások (LCS) könyvtárban található. Töltse le a csomagot, és csatlakoztassa a Microsoft Dynamics 365 műveletekre vonatkozó további információt lásd: [a Microsoft és a partnerek LCS kiemelt BI-tartalom](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>A csomag található jelentések
A Dynamics 365 műveleti adatok a csomag már csatlakozott, miután a jelentések megjelenítése a szervezet adatait. Ha korábban sosem használta a Microsoft kiemelt BI előtt, többet is megtudhat erről a a [Power BI lap interaktív tanulási](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). A csomag tartalmazza a jelentések további információkat tartalmazó táblázatok és diagramok is rendelkezik. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés          | Tartalom                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Tanfolyam-elemzés | Nyilvántartási helye, tanfolyami résztvevők állapotának és regisztráció |
| Tanfolyamtípusok    | Tanfolyamtípusok szakértelem szerint                                                       |

A diagramok és ezeket a jelentéseket a Mozaik szűrő, és rögzítése a diagramok és a mozaikok az irányítópulton. Szűrő és a PIN-kódot a kiemelt BI kapcsolatos további tudnivalókért lásd: [létrehozása és konfigurálása A Dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
365 Dynamics műveleti adatok a szervezeti képzési csomagot a jelentések feltöltésére szolgál. A következő táblázat mutatja az entitások a csomag alapult.

| Entitás                    | Tartalom                                                         | Más entitásokkal való                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Képzési\_CalendarOffset  | Naptár eltolja a szelet jelentések                                | Képzési\_CourseAgenda oktatási\_CourseAttendees                                                                                                                                                   |
| Képzési\_vállalat         | Vállalatok által a jelentések szűréséhez                                   | Képzési\_CourseAgenda oktatási\_CourseAttendees                                                                                                                                                   |
| Képzési\_tanfolyam          | Tanfolyam, leírás, oktató neve, hely, hely és állapot | Képzési\_CourseAgenda oktatási\_CourseAttendees oktatási\_CourseSkill                                                                                                                             |
| Képzési\_CourseAgenda    | Napirend, a tanfolyam és a kezdő és záró időpontokat                          | Képzési\_vállalat képzési\_CalendarOffset oktatási\_képzés dátum\_tanfolyam                                                                                                                         |
| Képzési\_CourseAttendees | Neve, állapota, feladat és regisztráció dátuma                         | Képzési\_vállalat képzési\_CalendarOffset képzés\_képzés dátum\_demográfiai képzési\_foglalkoztatási, képzési\_tanfolyam képzési\_WorkerName képzés\_WorkerTitle képzés\_képzési projekt\_pozíció |
| Képzési\_CourseSkill     | Szakértelem, szakértelem típusát és szintjét                                     | Képzési\_tanfolyam                                                                                                                                                                                   |
| Képzési\_dátuma            | Nap, hét, hónap és év                                   | Képzési\_CourseAgenda oktatási\_CourseAttendees                                                                                                                                                   |
| Képzési\_demográfiai adatai    | Születési idő, a nemek, etnikai és családi állapot dátuma         | Képzési\_CourseAgenda oktatási\_CourseAttendees                                                                                                                                                   |
| Képzési\_foglalkoztatási      | Kezdő dátum, záró dátum és átállási dátum                        | Képzési\_CourseAgenda oktatási\_CourseAttendees                                                                                                                                                   |
| Képzési\_feladat             | Függvény, típusa és a cím                                        | Képzési\_CourseAgenda oktatási\_CourseAttendees                                                                                                                                                   |
| Képzési\_beosztás        | Helyzet, a cím és a teljes munkaidős egyenértékben (FTE)                  | Képzési\_CourseAgenda oktatási\_CourseAttendees                                                                                                                                                   |
| Képzési\_WorkerName      | Utónév, Vezetéknév és a teljes név                             | Képzési\_CourseAttendees                                                                                                                                                                          |
| Képzési\_WorkerTitle     | Cím és a szolgálati idő dátuma                                         | Képzési\_CourseAttendees                                                                                                                                                                          |

Ezeknek az entitásoknak az adatmodell számított mértékek létrehozására használták. Ezek kiszámítása intézkedések használata a fő teljesítménymutatók (KPI) kiszámításához és a jelentések, amelyek felhasználhatók a csomagot a. Ha szeretné felvenni a további számításokhoz a jelentések és irányítópultok, töltse le, és módosítsa a Training.pbix fájlt a LCS. Ez a fájl a csomag létrehozásához használt alapértelmezett adatmodell. Után végrehajtott módosításokat, egy szervezeti csomagot és felvett adatokat tartalmazó irányítópultot hozhat létre.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



