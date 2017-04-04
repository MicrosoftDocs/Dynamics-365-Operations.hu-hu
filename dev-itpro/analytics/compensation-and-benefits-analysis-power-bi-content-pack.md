---
title: "Kompenzáció és juttatások kiemelt BI-tartalom"
description: "Ez a témakör ismerteti a Dynamics 365 műveletek - kompenzáció és juttatások kiemelt BI-tartalom. Ismerteti, hogyan lehet elérni a jelentések, amelyek szerepelnek a csomagot, és tájékoztatást nyújt az adatmodell és a csomag létrehozásához használt entitások."
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

# <a name="compensation-and-benefits-power-bi-content"></a>Kompenzáció és juttatások kiemelt BI-tartalom

Ez a témakör ismerteti a Dynamics 365 műveletek - kompenzáció és juttatások kiemelt BI-tartalom. Ismerteti, hogyan lehet elérni a jelentések, amelyek szerepelnek a csomagot, és tájékoztatást nyújt az adatmodell és a csomag létrehozásához használt entitások.

<a name="accessing-the-content-pack"></a>A csomag elérése
--------------------------

A kompenzáció és juttatások csomagot a megosztott eszközök a Microsoft Dynamics életciklus szolgáltatások (LCS) könyvtárban található. Töltse le a csomagot, és csatlakoztassa a Microsoft Dynamics 365 műveletekre vonatkozó további információt lásd: [a Microsoft és a partnerek LCS kiemelt BI-tartalom](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>A csomag található jelentések
A Dynamics 365 műveleti adatok a csomag már csatlakozott, miután a jelentések megjelenítése a szervezet adatait. Ha korábban sosem használta a Microsoft kiemelt BI előtt, többet is megtudhat erről a a [Power BI lap interaktív tanulási](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). A csomag tartalmazza a jelentések további információkat tartalmazó táblázatok és diagramok is rendelkezik. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                     | Tartalom                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Comp és hasznok elemzésére | Vállalat, óránkénti és a fizetett alkalmazottak átlagos órabér, fizetett átlagos fizetés, az alkalmazottak foglalkoztatási típus, és igénylési terv |
| Munkavállalói juttatások          | Alkalmazott tanúsítványigénylő által kijelölt juttatás                                                                                               |

A diagramok és ezeket a jelentéseket a Mozaik szűrő, és rögzítése a diagramok és a mozaikok az irányítópulton. Szűrő és a PIN-kódot a kiemelt BI kapcsolatos további tudnivalókért lásd: [létrehozása és konfigurálása A Dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
365 Dynamics műveleti adatok a kompenzáció és juttatások csomagot a jelentések feltöltésére szolgál. A következő táblázat mutatja az entitások a csomag alapult.

| Entitás                            | Tartalom                                                                                                   | Más entitásokkal való                                                                                                                                                                                                                                                                                                |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Munkaerő\_CalendarOffset         | Naptár eltolja a szelet jelentések                                                                          | Munkaerő\_PastPositionAssignment munkaerő\_PositionTrend Workorce\_WorkerTrend munkaerő\_TerminatedWorker                                                                                                                                                                                                                     |
| Munkaerő\_vállalat                | Vállalatok által a jelentések szűréséhez                                                                             | Munkaerő\_CurrentCompensation munkaerő\_CurrentWorker munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                        |
| Munkaerő\_kompenzáció           | Fizetési díjalap és időbeli gyakorisága                                                                           | Munkaerő\_CurrentCompensation munkaerő\_CurrentWorker munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                        |
| Munkaerő\_CurrentCompensation    | Fizetési díjalap és gyakoriságát, az aktuális dátum szerint                                                              | Munkaerő\_cég munkaerő\_kompenzációs munkaerő\_demográfiai munkaerő\_projekt munkaerő\_beosztás                                                                                                                                                                                                                            |
| Munkaerő\_CurrentPosition        | Az aktuális dátum, teljes munkaidős egyenértékben (FTE), a nyitott pozíciók és a töltött nyitott pozíciók pozíciók | Munkaerő\_projekt munkaerő\_beosztás                                                                                                                                                                                                                                                                                               |
| Munkaerő\_CurrentWorker          | Az aktuális dátum, a kor és a létszám munkavállalók                                                         | Munkaerő\_cég munkaerő\_kompenzációs munkaerő\_GeographicLocation munkaerő\_teljesítmény munkaerő\_WorkerName munkaerő\_ReportsToWorkerName munkaerő\_WorkerTitle munkaerő\_demográfiai munkaerő\_projekt munkaerő\_munkaerő foglalkoztatási\_helyezze a munkaerő\_WorkerBenefit                                            |
| Munkaerő\_dátuma                   | Nap, hét, hónap és év                                                                             | Munkaerő\_PastPositionAssignment munkaerő\_PositionTrend munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                     |
| Munkaerő\_demográfiai adatai           | Születési idő, a nemek, etnikai és családi állapot dátuma                                                   | Munkaerő\_CurrentWorker munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_foglalkoztatási             | Kezdő dátum, záró dátum és átállási dátum                                                                  | Munkaerő\_CurrentWorker munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_GeographicLocation     | Város, megye, postai kód és állam vagy megye                                                           | Munkaerő\_CurrentWorker munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_feladat                    | Függvény, típusa és a cím                                                                                  | Munkaerő\_CurrentPosition munkaerő\_CurrentWorker                                                                                                                                                                                                                                                                              |
| Munkaerő\_PastPositionAssignment | Hozzárendelés oka, kezdő dátum, záró dátum és feldolgozás                                                           | Munkaerő\_CalendarOffset munkaerő\_munkaerő dátum\_projekt munkaerő\_beosztás                                                                                                                                                                                                                                                     |
| Munkaerő\_teljesítmény            | Minősítés, leírás és minősítési modell                                                                      | Munkaerő\_CurrentWorker munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_beosztás               | Részleg, FTE, beosztás, munkakör típusának és a cím                                                        | Munkaerő\_CurrentPosition munkaerő\_CurrentWorker                                                                                                                                                                                                                                                                              |
| Munkaerő\_PositionTrend          | Pozícióinak idő, FTE és feldolgozás                                                                          | Munkaerő\_CalendarOffset munkaerő\_munkaerő dátum\_projekt munkaerő\_beosztás                                                                                                                                                                                                                                                     |
| Munkaerő\_ReportsToWorkerName    | Utónév, Vezetéknév és a teljes név                                                                       | Munkaerő\_CurrentWorker munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_szakértelem                  | Szakértelem, a szakértelem típusát és a minősítés                                                                              |                                                                                                                                                                                                                                                                                                                                  |
| Munkaerő\_TerminatedWorker       | Munkavállalók, Megszűnés dátuma, cím, pozíció és feladat megszakítása                                             | Munkaerő\_cég munkaerő\_kompenzációs munkaerő\_GeographicLocation munkaerő\_teljesítmény munkaerő\_WorkerName munkaerő\_ReportsToWorkerName munkaerő\_CalendarOffset Workforces\_munkaerő dátum\_WorkerTitle munkaerő\_demográfiai munkaerő\_munkaerő foglalkoztatási\_projekt munkaerő\_helyezze a munkaerő\_WorkerBenefit |
| Munkaerő\_WorkerBenefit          | Hatálybalépés, juttatási lehetőség, juttatási és juttatási típus                                             | Munkaerő\_CurrentWorker munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_WorkerName             | Utónév, Vezetéknév és a teljes név                                                                       | Munkaerő\_CurrentWorker munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Munkaerő\_WorkerTitle            | Cím és a szolgálati idő dátuma                                                                                   | Munkaerő\_CurrentWorker munkaerő\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workorce\_WorkerTrend             | Munkavállalók idő, létszám, vállalati és pozíció                                                        | Munkaerő\_cég munkaerő\_kompenzációs munkaerő\_GeographicLocation munkaerő\_teljesítmény munkaerő\_WorkerName munkaerő\_ReportsToWorkerName munkaerő\_CalendarOffset Workforces\_munkaerő dátum\_WorkerTitle munkaerő\_demográfiai munkaerő\_munkaerő foglalkoztatási\_projekt munkaerő\_WorkerBenefit                     |

Ezeknek az entitásoknak az adatmodell számított mértékek létrehozására használták. Ezek kiszámítása intézkedések használata a fő teljesítménymutatók (KPI) kiszámításához és a jelentések, amelyek felhasználhatók a csomagot a. Ha szeretné felvenni a további számításokhoz a jelentések és irányítópultok, töltse le, és módosítsa a CompensationandBenefits.pbix fájlt a LCS. Ez a fájl a csomag létrehozásához használt alapértelmezett adatmodell. Után végrehajtott módosításokat, egy szervezeti csomagot és felvett adatokat tartalmazó irányítópultot hozhat létre.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



