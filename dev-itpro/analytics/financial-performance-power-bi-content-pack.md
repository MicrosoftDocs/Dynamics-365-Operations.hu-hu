---
title: "Pénzügyi Teljesítmény Power BI-tartalom"
description: "Ez a témakör a Microsoft Dynamics 365 for Operations Pénzügyi Teljesítmény Microsoft Power BI tartalmi csomagot ismerteti. Leírja, hogyan kell használni az irányítópultot és a tartalmi csomagban szereplő jelentéseket, és információkat nyújt a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9cd1d7e5b7b1fd892034dcca0a0c141363104a45
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="financial-performance-power-bi-content"></a>Pénzügyi Teljesítmény Power BI-tartalom

[!include[banner](../includes/banner.md)]


Ez a témakör a Microsoft Dynamics 365 for Operations Pénzügyi Teljesítmény Microsoft Power BI tartalmi csomagot ismerteti. Leírja, hogyan kell használni az irányítópultot és a tartalmi csomagban szereplő jelentéseket, és információkat nyújt a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

<a name="accessing-the-content-pack"></a>A tartalmi csomag elérése
--------------------------

A Pénzügyi Teljesítmény csomag két változata érhető el. Az egyik verzió a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból, a másik pedig a PowerBI.com-on érhető el.

-   **LCS-ből elérhető verzió:** az LCS-ből elérhető Pénzügyi Teljesítmény tartalmi csomag a Microsoft Dynamics 365 for Operations 1611-es verzióját támogatja. A tartalmi csomag az LCS Megosztott eszközök könyvtárában található. A tartalomcsomag letöltésére és a Microsoft Dynamics 365 for Operations adataival való összekapcsolásra vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md).
-   **A PowerBI.com-ról elérhető verzió:** a PowerBI.com-ról elérhető Pénzügyi Teljesítmény tartalmi csomag a Microsoft Dynamics AX 7.0 és 7.0.1-es verzióját támogatja. A csatlakozással és a Microsoft Dynamics 365 for Operations-adatok betöltésével kapcsolatos további tudnivalókat lásd: [Power BI-tartalom elérése a PowerBI.com webhelyről](power-bi-home-page.md).

## <a name="main-account-setup"></a>Fő számla beállítása
Mivel a szervezetek szeretik, ha a kötelezettségeik és a bevételeik összegei pozitív összegként jelennek meg a jelentésekben, a Dynamics 365 for Operations fő számláinak beállítása fontos szerepet játszik. Ugyanis ezen fő számlák pozitív összegként való megjelenítéséhez a fő számla típusaként **Kötelezettség** vagy **Bevétel** értéket kell megadni. E számlatípusok használatakor a Microsoft Power BI szolgáltatáson keresztüli jelentéstétel megfordítja az előjeleket, és az összegeket pozitívként jeleníti meg.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>A tartalomcsomag által tartalmazott irányítópult és a jelentések
Miután csatlakoztatta a tartalmi csomagot a Dynamics 365 for Operations rendszer adataihoz, az irányítópult és a jelentések megjelenítik a pénzügyi adatait. Ha még soha nem használt Power BI-t, többet megtudhat róla az [Irányított tanulás a Power BI-hez oldalon](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Az irányítópult az alacsonyabb szintű jelentéseken alapuló adatok összesített lapjait tartalmazza. Minden egyes lap tartalmazza a folyó év összesített információit a szervezeten belüli összes vállalatnál. Az alábbiakban látható néhány ilyen lap:

-   Készpénz
-   Az idei teljes bevétel
-   Az idei teljes kiadás
-   Az idei nettó bevétel
-   Likvidálási gyorsráta
-   A számla-kategória szerinti összes idei költség
-   Likviditási ráta
-   Tartozás az eszközállományhoz képest
-   A tényleges vagy az előrejelzett bevétel
-   Az idei számlázott bevétel
-   Működési költségeket idei aránya
-   Az idei fedezeti mutató
-   Tényleges vagy költségvetési költségek – Összes vállalat

Minden egyes lapot jelentés támaszt alá. Ezek a jelentések diagramokot és táblázatokat tartalmaznak, amelyek további információkat nyújtanak. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                      | A jelentés tartalmazza az információkat                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Készpénz-elemzés               | Készpénz jogi személyként, negyedévenkénti készpénz, teljes készpénz és készpénz számlánként **Megjegyzés:** A **Negyedévenkénti készpénz** jelentés nem tartalmaz nyitó egyenlegeket a teljes első negyedévére. Az egyes negyedévekben feladott tranzakciók összegét jeleníti meg.                                                                                |
| Jelenlegi rátaelemzés      | Jogi személy szerinti likviditási ráta, negyedév szerinti, és az aktuális eszközök és a rövid lejáratú kötelezettségek egyenlege szerinti likvidálási ráta                                                                                                                                                                                                                              |
| Gyorsráta-elemzés        | Jogi személy szerinti likvidálási gyorsráta, negyedév szerinti likvidálási gyorsráta, és a készpénz, kinnlevőségek egyenlege és a rövid lejáratú kötelezettségek egyenlege szerinti likvidálási ráta                                                                                                                                                                                                                      |
| Eladott áruk beszerzési érték elemzése | Eladott áruk beszerzési értéke (ELÁBÉ) jogi személy szerint, az idei és az előző évi ELÁBÉ negyedévenként, ELÁBÉ az értékesítéshez a jogi személy szerint , az összes ELÁBÉ és ELÁBÉ az értékesítési százalék szerint                                                                                                                                                                                   |
| Forgótőke-elemzés    | Jogi személy szerinti forgótőke, negyedévenkénti forgótőke, aktuális eszközök, rövid lejáratú kötelezettségek és a teljes forgótőke                                                                                                                                                                                                                   |
| Eszköz- és Tartozás elemzés     | Összes eszköz és tartozás megtérülése a jogi személy szerinti összes eszközhöz, az összes negyedéves eszköz megtérülése a dátumhoz, eszközökhöz, és a kötelezettségekhez                                                                                                                                                                                     |
| Fedezeti mutatóelemzés      | Jogi személy szerinti tényleges és kötlségvetési fedezeti mutató, negyedév, fedezeti mutatószázalék, és fedezeti mutató szerinti haszonkulcs                                                                                                                                                                                                                       |
| Nettó árbevétel-elemzés         | A tényleges és a költségvetés nettó árbevétele jogi személy, az idei és az előző évi nettó árbevétel, és a kiadások szerint a nettó árbevétel-százalékhoz                                                                                                                                                                                                                       |
| Bevételelemzés           | A tényleges és a költségvetési eredmény a kamat és az adók előtt (EBIT) a jogi személy, az idei és az előző évi EBIT, a kiadások szerint az árbevétel-százalékhoz, és a tényleges és költségvetési kiadások az árbevételhez                                                                                                                                                          |
| Bevételelemzés            | A teljes bevétel, a tényleges és a költségvetés teljes árbevétele a jogi személy által, az idei és az előző évi teljes bevétel, az árbevétel kötlségvetés eltérés a jogi személy szerint, és a jelenlegi és az előző időszak összes árbevétele                                                                                                                                                 |
| Költségelemzés            | Az összes költség, a költségvetés összköltsége a jogi személy szerint, a tényleges és a költségvetési összes kiadás negyedénként, az összes kiadás a számlakategória szerint, és a működési költségek aránya                                                                                                                                                                 |
| Számlázott bevételelemzés     | Összes kinnlevőség, az összes kinnlevőség jogi személy szerint, összes kinnlevőség negyedévenként, a kinnlevőségek számlák egyenlege **Megjegyzés:** A jelentések nem tartalmaznak nyitó egyenlegeket a kinnlevőségek főkönyvi számlákhoz. A Kinnlevőségek közé feladott új tranzakciók összegét mutatják. |

Az összes ilyen jelentésben szereplő diagramot és a lapot ki lehet szűrni és rögzíteni lehet az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálására](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
Az irányítópult és a Pénzügyi Teljesítmény tartalmi csomag jelentéseinek kitöltésére a Dynamics 365 for Operations rendszer adatai szolgálnak. A következő entitásokat használták a tartalmi csomag alapjaként: **Összesített adatentitások**

-   **GeneralLedgerActivities** – Ez az entitás a főkönyvi számla egyenlegeit összesíti számlakategória szerint.
-   **BudgetActivities** – Ez az entitás a költségvetési egyenlegeket összesíti számlakategória szerint.

**Adatentitások**

-   FiscalCalendars
-   MainAccounts
-   LegalEntities
-   Főkönyvek
-   ChartofAccounts

Ezeket az entitásokat számított mértékek létrehozására használták az adatmodellben. A kiszámított mértékek a fő teljesítménymutatók (KPI-k) és a tartalmi csomagban használt jelentések kiszámításához használatosak. Alapértelmezés szerint a tartalmi csomag tartalmazza az utolsó három év és a jövő évi adatokat. A jelentésekkel és az irányítópulttal kapcsolatos további számítások felvételéhez módosíthatja a [Microsoft Excel-munkafüzetet](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Ez a munkafüzet azon alapértelmezett adatmodell, amelyet a tartalmi csomag létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmi csomagot és a felvett adatokat tartalmazó irányítópultot hozhat létre.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](..\data-entities\data-entities.md)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](configure-power-bi-integration.md)





