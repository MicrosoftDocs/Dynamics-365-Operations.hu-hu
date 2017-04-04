---
title: "Pénzügyi teljesítmény energiaellátási BI-tartalom"
description: "Ez a témakör ismerteti a Microsoft Dynamics 365 műveletek pénzügyi teljesítmény Microsoft Power BI tartalom csomagjához. Az irányítópult és a jelentések, amelyek szerepelnek a csomag ismerteti, és tájékoztatást nyújt az adatmodell és a csomag létrehozásához használt entitások."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 227285720e7f28beeb135eea081940578531d458
ms.lasthandoff: 03/31/2017


---

# <a name="financial-performance-power-bi-content"></a>Pénzügyi teljesítmény energiaellátási BI-tartalom

Ez a témakör ismerteti a Microsoft Dynamics 365 műveletek pénzügyi teljesítmény Microsoft Power BI tartalom csomagjához. Az irányítópult és a jelentések, amelyek szerepelnek a csomag ismerteti, és tájékoztatást nyújt az adatmodell és a csomag létrehozásához használt entitások.

<a name="accessing-the-content-pack"></a>A csomag elérése
--------------------------

A pénzügyi teljesítmény csomag két változata érhetők el. Egy verziója érhető el a Microsoft Dynamics életciklus szolgáltatások (LCS), és a másik pedig a PowerBI.com.

-   **LCS elérhető verzió:** a pénzügyi teljesítmény LCS elérhető tartalom pack támogatja a Microsoft Dynamics 365 műveletek verzió 1611. A csomag LCS megosztott eszköz könyvtárban található. Töltse le a csomagot, és csatlakoztassa a Microsoft Dynamics 365 műveletekre vonatkozó további információt lásd: [a Microsoft és a partnerek LCS kiemelt BI-tartalom](power-bi-content-microsoft-partners.md).
-   **Elérhető a PowerBI.com verzió:**, amely elérhető a PowerBI.com a pénzügyi teljesítmény csomag támogatja a Microsoft Dynamics AX verziója 7.0 és 7.0.1. Csatlakoztatása és a Dynamics 365 műveleti adatok betöltése kapcsolatos további tudnivalókért lásd: [tartalom Access kiemelt BI PowerBI.com](power-bi-home-page.md).

## <a name="main-account-setup"></a>Fő számla beállítása
Szervezetek szeretné a kötelezettségek és a bevételi összegeket a jelentésekben pozitív összegként jelennek meg, mert a telepítési műveletek Dynamics 365 fő számlák fontos. Ezek pozitív összegként jelennek meg a fő számla, a fő számla típusának meg kell **felelősség** vagy **bevétel**. Ezek a számlatípusokhoz használatakor keresztül a Microsoft kiemelt BI fordított a jelek és megjelenítése a pozitív összegeket.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>Irányítópult és a jelentések, amelyek szerepelnek a csomag
Miután csatlakoztatta a tartalmi csomagot a Dynamics 365 for Operations rendszer adataihoz, az irányítópult és a jelentések megjelenítik a pénzügyi adatait. Ha korábban sosem használta a kiemelt BI előtt, többet is megtudhat erről a a [Power BI lap interaktív tanulási](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Az irányítópult az alacsonyabb szintű jelentéseken alapuló adatok összesített lapjait tartalmazza. Minden egyes lap tartalmazza a folyó év összesített információit a szervezeten belüli összes vállalatnál. Íme néhány követ:

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

Minden szelvény biztonsági igazoló jelentést. Ezek a jelentések diagramokot és táblázatokat tartalmaznak, amelyek további információkat nyújtanak. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                      | A jelentés tartalmazza az információkat                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Készpénz-elemzés               | Jogi személy, készpénz negyedévenként, teljes készpénz és készpénz számla szerint a pénzt **Megjegyzés:** a **negyedévenként pénzbeli** jelentés nem tartalmaz nyitó egyenlegek a teljes első negyedévére. Az összes új minden negyedévben feladott tranzakciókat jeleníti meg.                                                                                |
| Jelenlegi rátaelemzés      | Jogi személy szerinti likviditási ráta, negyedév szerinti, és az aktuális eszközök és a rövid lejáratú kötelezettségek egyenlege szerinti likvidálási ráta                                                                                                                                                                                                                              |
| Gyorsráta-elemzés        | Jogi személy által gyors arány, gyors arány negyedévenként és készpénz egyenlegek a Kinnlevőségek és a jelenlegi kötelezettségek számlák                                                                                                                                                                                                                      |
| Eladott áruk beszerzési érték elemzése | Eladott áruk beszerzési értéke (ELÁBÉ) jogi személy szerint, az idei és az előző évi ELÁBÉ negyedévenként, ELÁBÉ az értékesítéshez a jogi személy szerint , az összes ELÁBÉ és ELÁBÉ az értékesítési százalék szerint                                                                                                                                                                                   |
| Forgótőke-elemzés    | Jogi személy szerinti forgótőke, negyedévenkénti forgótőke, aktuális eszközök, rövid lejáratú kötelezettségek és a teljes forgótőke                                                                                                                                                                                                                   |
| Eszköz- és Tartozás elemzés     | Összes eszköz és tartozás megtérülése a jogi személy szerinti összes eszközhöz, az összes negyedéves eszköz megtérülése a dátumhoz, eszközökhöz, és a kötelezettségekhez                                                                                                                                                                                     |
| Fedezeti mutatóelemzés      | Jogi személy szerinti tényleges és kötlségvetési fedezeti mutató, negyedév, fedezeti mutatószázalék, és fedezeti mutató szerinti haszonkulcs                                                                                                                                                                                                                       |
| Nettó árbevétel-elemzés         | A tényleges és a költségvetés nettó árbevétele jogi személy, az idei és az előző évi nettó árbevétel, és a kiadások szerint a nettó árbevétel-százalékhoz                                                                                                                                                                                                                       |
| Bevételelemzés           | A tényleges és a költségvetési eredmény a kamat és az adók előtt (EBIT) a jogi személy, az idei és az előző évi EBIT, a kiadások szerint az árbevétel-százalékhoz, és a tényleges és költségvetési kiadások az árbevételhez                                                                                                                                                          |
| Bevételelemzés            | A teljes bevétel, a tényleges és a költségvetés teljes árbevétele a jogi személy által, az idei és az előző évi teljes bevétel, az árbevétel kötlségvetés eltérés a jogi személy szerint, és a jelenlegi és az előző időszak összes árbevétele                                                                                                                                                 |
| Költségelemzés            | Az összes költség, a költségvetés összköltsége a jogi személy szerint, a tényleges és a költségvetési összes kiadás negyedénként, az összes kiadás a számlakategória szerint, és a működési költségek aránya                                                                                                                                                                 |
| Számlázott bevételelemzés     | Összes kinnlevőség összes kinnlevőség jogi személy által, összesen kinnlévőségek negyedévenként, és a mérleg Követelések számláinak számlák **Megjegyzés:** a jelentés nem tartalmaz, nyitó egyenlegek a fiókok követelések főkönyvi számlák. Az összes feladott számlákat követelés új tranzakciók mutatnak. |

Az összes ilyen jelentésben szereplő diagramot és a lapot ki lehet szűrni és rögzíteni lehet az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálására](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
Az irányítópult és a pénzügyi teljesítményét content Pack jelentéseket tartalmazó adata Dynamics 365 műveleti adatok. A következő vállalkozások a csomag alapjaként használták: **összesített adatok entitások**

-   **GeneralLedgerActivities** – Ez az entitás főkönyvi egyenlegek aggregátumok fiók kategória szerint.
-   **BudgetActivities** – Ez az entitás költségvetési egyenlegek aggregátumok fiók kategória szerint.

**Data entities**

-   FiscalCalendars
-   MainAccounts
-   LegalEntities
-   Főkönyvek
-   ChartofAccounts

Ezeknek az entitásoknak az adatmodell számított mértékek létrehozására használták. A fő teljesítménymutatók (KPI) számítására szolgálnak a számított mértékek és jelentések a csomagot használt. Alapértelmezés szerint a tartalmi csomag tartalmazza az utolsó három év és a jövő évi adatokat. A jelentésekkel és az irányítópulttal kapcsolatos további számítások felvételéhez módosíthatja a [Microsoft Excel-munkafüzetet](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Ez a munkafüzet azon alapértelmezett adatmodell, amelyet a tartalmi csomag létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmi csomagot és a felvett adatokat tartalmazó irányítópultot hozhat létre.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](..\data-entities\data-entities.md)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](configure-power-bi-integration.md)



