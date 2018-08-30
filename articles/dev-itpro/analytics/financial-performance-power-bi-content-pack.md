---
title: "Pénzügyi teljesítmény PowerBI.com megoldás"
description: "Ez a témakör ismerteti a pénzügyi teljesítmény PowerBI.com megoldást."
author: kweekley
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cf531c3a8f3bdb17314d1de436b98249169f82a3
ms.openlocfilehash: b70d470da2160670848d2dca9c97f6d7a2d6cf60
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="financial-performance-powerbicom-solution"></a>Pénzügyi teljesítmény PowerBI.com megoldás

[!include [banner](../includes/banner.md)]

> [!Note]
> Ez a PowerBI.com megoldás elavult a következő dokumentációban ismertetettek szerint [Power BI-tartalmak csomagjai állnak rendelkezésre az AppSource-on](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource).

Ez a témakör ismerteti a **Pénzügyi teljesítmény** PowerBI.com megoldást. Leírja, hogyan kell használni az irányítópultot és a megoldásban szereplő jelentéseket, és információkat nyújt a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="main-account-setup"></a>Fő számla beállítása
Mivel a szervezetek szeretik, ha a kötelezettségeik és a bevételeik összegei pozitív összegként jelennek meg a jelentésekben, a fő számlák beállítása fontos szerepet játszik. Ugyanis ezen fő számlák pozitív összegként való megjelenítéséhez a fő számla típusaként **Kötelezettség** vagy **Bevétel** értéket kell megadni. E számlatípusok használatakor a Power BI szolgáltatáson keresztüli jelentéstétel megfordítja az előjeleket, és az összegeket pozitívként jeleníti meg.

## <a name="dashboard-and-reports-that-are-included-in-the-powerbicom-solution"></a>A PowerBI.com megoldás által tartalmazott irányítópult és a jelentések
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
| Készpénz-elemzés               | Készpénz jogi személyként, negyedévenkénti készpénz, teljes készpénz és készpénz számlánként<br><br>**Megjegyzés:** A készpénz negyedév szerinti adatai nem tartalmaznak nyitó egyenlegeket az első negyedév összegében. Az egyes negyedévekben feladott tranzakciók összegét jeleníti meg.|
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
| Számlázott bevételelemzés     | Kinnlevőségek összesen, az összes kinnlevőség jogi személy szerint, az összes kinnlevőség negyedévenként és a kinnlevőségek számlák egyenlege<br><br>**Megjegyzés:** Az adatok nem tartalmaznak nyitó egyenlegeket a kinnlevőségek főkönyvi számlákhoz. A kinnlevőségek közé feladott új tranzakciók összegét mutatja. |

Az összes ilyen jelentésben szereplő diagramot és a lapot ki lehet szűrni és rögzíteni lehet az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálására](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A következő entitásokat használták **Pénzügyi teljesítmény** PowerBI.com megoldás alapjaként:

**Összesített adatentitások**

- **GeneralLedgerActivities** – Ez az entitás a főkönyvi számla egyenlegeit összesíti számlakategória szerint.
- **BudgetActivities** – Ez az entitás a költségvetési egyenlegeket összesíti számlakategória szerint.

**Adatentitások**

- FiscalCalendars
- MainAccounts
- LegalEntities
- Főkönyvek
- ChartofAccounts

Ezeket az entitásokat számított mértékek létrehozására használták az adatmodellben. A kiszámított mértékek a fő teljesítménymutatók (KPI-k) és a tartalomban használt jelentések kiszámításához használatosak. Alapértelmezés szerint a tartalom tartalmazza az utolsó három év és a jövő évi adatokat. A jelentésekkel és az irányítópulttal kapcsolatos további számítások felvételéhez módosíthatja a [Microsoft Excel-munkafüzetet](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Ez a munkafüzet azon alapértelmezett adatmodell, amelyet a tartalom létrehozásához használtak. 

