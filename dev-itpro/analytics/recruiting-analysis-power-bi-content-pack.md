---
title: "Kiemelt BI tartalom felvétele"
description: "Ez a témakör ismerteti a Dynamics 365 műveletek - felvételi teljesítmény BI-tartalom. Ismerteti, hogyan lehet elérni a jelentések, amelyek szerepelnek a csomagot, és tájékoztatást nyújt az adatmodell és a csomag létrehozásához használt entitások."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: d307733193b388149f83dd420cc7003edcf7749a
ms.lasthandoff: 03/31/2017


---

# <a name="recruiting-power-bi-content"></a>Kiemelt BI tartalom felvétele

Ez a témakör ismerteti a Dynamics 365 műveletek - felvételi teljesítmény BI-tartalom. Ismerteti, hogyan lehet elérni a jelentések, amelyek szerepelnek a csomagot, és tájékoztatást nyújt az adatmodell és a csomag létrehozásához használt entitások.

<a name="accessing-the-content-pack"></a>A csomag elérése
--------------------------

A munkaerő-toborzás csomagot a megosztott eszközök a Microsoft Dynamics életciklus szolgáltatások (LCS) könyvtárban található. Töltse le a csomagot, és csatlakoztassa a Microsoft Dynamics 365 műveletekre vonatkozó további információt lásd: [a Microsoft és a partnerek LCS kiemelt BI-tartalom](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>A csomag található jelentések
A Dynamics 365 műveleti adatok a csomag már csatlakozott, miután a jelentések megjelenítése a szervezet adatait. Ha korábban sosem használta a Microsoft kiemelt BI előtt, többet is megtudhat erről a a [Power BI lap interaktív tanulási](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). A csomag tartalmazza a jelentések további információkat tartalmazó táblázatok és diagramok is rendelkezik. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                       | Tartalom                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Kérelmező elemzés           | A kérelmezők feladat, a kérelmező források, kérelmezők helyét, és a pályázók száma összesen           |
| Pályázó állapota             | Pályázók típusa és állapota és a Pályázó állapota                                                    |
| Kérelmező demográfiai adatai       | Kérelmezők életkora és neme, és a kérelmezők végzettségi szint és állapot                             |
| Toborzás-elemzés          | NET felvételi arány, a rossz hires és toborzási költségek százalékos felvenni napok átlagos száma                    |
| Toborzási projekt elemzés | Toborzási projektek, a toborzási projekt által nyílások és a kérelmező által a toborzási projekt száma |

A diagramok és ezeket a jelentéseket a Mozaik szűrő, és rögzítése a diagramok és a mozaikok az irányítópulton. Szűrő és a PIN-kódot a kiemelt BI kapcsolatos további tudnivalókért lásd: [létrehozása és konfigurálása A Dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
365 Dynamics műveleti adatok a munkaerő-toborzás csomagot a jelentések feltöltésére szolgál. A következő táblázat mutatja az entitások a csomag alapult.

| Entitás                          | Tartalom                                                         | Más entitásokkal való                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Felvételi\_kérelmező           | A kérelmezők, felvett pályázók, nettó bérleti arány és költségek          | Felvételi\_ApplicantName felvételi\_társaság, Recruiting\_CalendarOffset Recuriting\_felvételi dátum\_GeographicLocation felvételi\_felvételi demográfiai\_toborzási projekt\_Media toborzási\_RecruitmentProject                                |
| Felvételi\_ApplicantName       | Kérelmező Utónév, Vezetéknév és a teljes név                   | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_CalendarOffset      | Naptár eltolja a szelet jelentések                                | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_vállalat             | Vállalatok által a jelentések szűréséhez                                   | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_dátuma                | Nap, hét, hónap és év                                   | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_demográfiai adatai        | Születési idő, a nemek, etnikai és családi állapot dátuma         | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_EmployedApplicant   | Kérelmező, teljesítmény, Kezdődátum és pályázó típusa           | Felvételi\_társaság, Recruiting\_CalendarOffset felvételi\_felvételi dátum\_felvételi GeographicLocation\_ApplicantName felvételi\_foglalkoztatási felvételi\_felvételi teljesítmény\_toborzási projekt\_Media toborzási\_RecruitmentProject          |
| Felvételi\_foglalkoztatási          | Kezdő dátum, záró dátum és átállási dátum                        | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_GeographicLocation  | Város, megye, postai kód és állam vagy megye                 | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_feladat                 | Függvény, típusa és a cím                                        | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_Media               | A kérelmezők forrás                                             | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_teljesítmény         | Minősítés, leírás és minősítési modell                            | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_RecruitmentProject  | Projekt leírása, a projekt állapotának és a nyílások                | Felvételi\_kérelmező felvételi\_EmployedApplicant felvételi\_TerminatedApplicant                                                                                                                                                               |
| Felvételi\_TerminatedApplicant | Leállt a kérelmezők, ezért, teljesítmény és a Megszűnés dátuma | Felvételi\_társaság, Recruiting\_CalendarOffset felvételi\_felvételi dátum\_GeographicLocation felvételi\_felvételi teljesítmény\_felvételi demográfiai\_foglalkoztatási felvételi\_Media toborzási\_felvételi RecruitmentProject\_ApplicantName |

Ezek az entitások számított mértékek létrehozására használták. Ezek kiszámítása intézkedések használata a fő teljesítménymutatók (KPI) kiszámításához és a jelentések, amelyek felhasználhatók a csomagot a. Ha szeretné felvenni a további számításokhoz a jelentések és irányítópultok, töltse le, és módosítsa a Recruiting.pbix fájlt a LCS. Ez a fájl a csomag létrehozásához használt alapértelmezett adatmodell. Után végrehajtott módosításokat, egy szervezeti csomagot és felvett adatokat tartalmazó irányítópultot hozhat létre.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



