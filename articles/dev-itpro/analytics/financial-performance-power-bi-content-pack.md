---
title: "Pénzügyi teljesítmény Power BI-tartalom"
description: "Ez a témakör ismerteti a pénzügyi teljesítmény Power BI-tartalmat. Leírja, hogyan kell használni az irányítópultot és a csomagban szereplő jelentéseket, és információkat nyújt a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
author: kweekley
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2a501fcb851f1c201e03b59bb3ea951684c6e552
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="financial-performance-power-bi-content"></a>Pénzügyi teljesítmény Power BI-tartalom

[!include[banner](../includes/banner.md)]

Ez a témakör ismerteti a **Pénzügyi teljesítmény** Microsoft Power BI-tartalmat. Leírja, hogyan kell használni az irányítópultot és a csomagban szereplő jelentéseket, és információkat nyújt a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése

A **Pénzügyi teljesítmény** Power BI a Microsoft Dynamics Lifecycle Services (LCS), valamint PowerBI.com használatával érhető el.

### <a name="available-from-lcs"></a>LCS elérhetőség
Az LCS-szolgáltatásokból elérhető **Pénzügyi teljesítmény** Power BI-tartalom a következő verziókat támogatja:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (2017. július)
- Microsoft Dynamics 365 for Operations 1611-es verzió 

A Power BI-tartalom az LCS Megosztott eszközök könyvtárában található. A tartalmi csomag letöltésére és a szervezetben való implementálására vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md). Ha meg szeretne tekinteni egy demót, amely bemutatja a Power BI-tartalmak megvalósítását, lásd a [Power BI-tartalom a Microsofttól és az Ön partnereitől a Dynamics Lifecycle Services szolgáltatásban](https://mix.office.com/watch/9puyb1b2xs1w) című részt (Office Mix).

### <a name="available-from-powerbicom"></a>Elérhető PowerBI.com webhelyen
A PowerBI.com webhelyről elérhető **Pénzügyi teljesítmény** Power BI-tartalom a Microsoft Dynamics AX 7.0 és 7.0.1-es verzióját támogatja. A csatlakozással és a Dynamics AX-adatok betöltésével kapcsolatos további tudnivalókat lásd: [Power BI-tartalom elérése a PowerBI.com webhelyről](power-bi-home-page.md).

## <a name="main-account-setup"></a>Fő számla beállítása
Mivel a szervezetek szeretik, ha a kötelezettségeik és a bevételeik összegei pozitív összegként jelennek meg a jelentésekben, a fő számlák beállítása fontos szerepet játszik. Ugyanis ezen fő számlák pozitív összegként való megjelenítéséhez a fő számla típusaként **Kötelezettség** vagy **Bevétel** értéket kell megadni. E számlatípusok használatakor a Power BI szolgáltatáson keresztüli jelentéstétel megfordítja az előjeleket, és az összegeket pozitívként jeleníti meg.

## <a name="dashboard-and-reports-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalom által tartalmazott irányítópult és a jelentések
Az irányítópult az alacsonyabb szintű jelentéseken alapuló adatok összesített lapjait tartalmazza. Minden egyes lap tartalmazza a folyó év összesített információit a szervezeten belüli összes vállalatnál. Az alábbiakban látható néhány ilyen lap:

- Készpénz
- Az idei teljes bevétel
- Az idei teljes kiadás
- Az idei nettó bevétel
- Likvidálási gyorsráta
- A számla-kategória szerinti összes idei költség
- Likviditási ráta
- Tartozás az eszközállományhoz képest
- A tényleges vagy az előrejelzett bevétel
- Az idei számlázott bevétel
- Működési költségeket idei aránya
- Az idei fedezeti mutató
- Tényleges vagy költségvetési költségek – Összes vállalat

Minden egyes lapot jelentés támaszt alá. Ezek a jelentések diagramokot és táblázatokat tartalmaznak, amelyek további információkat nyújtanak. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                      | A jelentés tartalmazza az információkat |
|-----------------------------|--------------------------------------|
| Készpénz-elemzés               | Készpénz jogi személyként, negyedévenkénti készpénz, teljes készpénz és készpénz számlánként<blockquote>[!NOTE]<br>A készpénz negyedév szerinti adatai nem tartalmaznak nyitó egyenlegeket az első negyedév összegében. Az egyes negyedévekben feladott tranzakciók összegét jeleníti meg.</blockquote> |
| Jelenlegi rátaelemzés      | Jogi személy szerinti likviditási ráta, negyedév szerinti, és az aktuális eszközök és a rövid lejáratú kötelezettségek egyenlege szerinti likvidálási ráta |
| Gyorsráta-elemzés        | Jogi személy szerinti likvidálási gyorsráta, negyedév szerinti likvidálási gyorsráta, és a készpénz, kinnlevőségek egyenlege és a rövid lejáratú kötelezettségek egyenlege szerinti likvidálási ráta |
| Eladott áruk beszerzési érték elemzése | Eladott áruk beszerzési értéke (ELÁBÉ) jogi személy szerint, az idei és az előző évi ELÁBÉ negyedévenként, ELÁBÉ az értékesítéshez a jogi személy szerint , az összes ELÁBÉ és ELÁBÉ az értékesítési százalék szerint |
| Forgótőke-elemzés    | Jogi személy szerinti forgótőke, negyedévenkénti forgótőke, aktuális eszközök, rövid lejáratú kötelezettségek és a teljes forgótőke |
| Eszköz- és Tartozás elemzés     | Összes eszköz és tartozás megtérülése a jogi személy szerinti összes eszközhöz, az összes negyedéves eszköz megtérülése a dátumhoz, eszközökhöz, és a kötelezettségekhez |
| Fedezeti mutatóelemzés      | Jogi személy szerinti tényleges és kötlségvetési fedezeti mutató, negyedév, fedezeti mutatószázalék, és fedezeti mutató szerinti haszonkulcs |
| Nettó árbevétel-elemzés         | A tényleges és a költségvetés nettó árbevétele jogi személy, az idei és az előző évi nettó árbevétel, és a kiadások szerint a nettó árbevétel-százalékhoz |
| Bevételelemzés           | A tényleges és a költségvetési eredmény a kamat és az adók előtt (EBIT) a jogi személy, az idei és az előző évi EBIT, a kiadások szerint az árbevétel-százalékhoz, és a tényleges és költségvetési kiadások az árbevételhez |
| Bevételelemzés            | A teljes bevétel, a tényleges és a költségvetés teljes árbevétele a jogi személy által, az idei és az előző évi teljes bevétel, az árbevétel kötlségvetés eltérés a jogi személy szerint, és a jelenlegi és az előző időszak összes árbevétele |
| Költségelemzés            | Az összes költség, a költségvetés összköltsége a jogi személy szerint, a tényleges és a költségvetési összes kiadás negyedénként, az összes kiadás a számlakategória szerint, és a működési költségek aránya |
| Számlázott bevételelemzés     | Kinnlevőségek összesen, az összes kinnlevőség jogi személy szerint, az összes kinnlevőség negyedévenként és a kinnlevőségek számlák egyenlege<blockquote>[!NOTE]<br>Az adatok nem tartalmaznak nyitó egyenlegeket a kinnlevőségek főkönyvi számlákhoz. A kinnlevőségek közé feladott új tranzakciók összegét mutatja.</blockquote> |

Az összes ilyen jelentésben szereplő diagramot és a lapot ki lehet szűrni és rögzíteni lehet az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálására](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A következő entitásokat használták **Pénzügyi teljesítmény** Power BI-tartalom alapjaként:

**Összesített adatentitások**

- **GeneralLedgerActivities** – Ez az entitás a főkönyvi számla egyenlegeit összesíti számlakategória szerint.
- **BudgetActivities** – Ez az entitás a költségvetési egyenlegeket összesíti számlakategória szerint.

**Adatentitások**

- FiscalCalendars
- MainAccounts
- LegalEntities
- Főkönyvek
- ChartofAccounts

Ezeket az entitásokat számított mértékek létrehozására használták az adatmodellben. A kiszámított mértékek a fő teljesítménymutatók (KPI-k) és a tartalomban használt jelentések kiszámításához használatosak. Alapértelmezés szerint a tartalom tartalmazza az utolsó három év és a jövő évi adatokat. A jelentésekkel és az irányítópulttal kapcsolatos további számítások felvételéhez módosíthatja a [Microsoft Excel-munkafüzetet](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Ez a munkafüzet azon alapértelmezett adatmodell, amelyet a tartalom létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmi csomagot és a felvett adatokat tartalmazó irányítópultot hozhat létre.

