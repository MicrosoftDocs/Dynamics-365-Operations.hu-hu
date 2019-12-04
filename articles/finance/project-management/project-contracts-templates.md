---
title: Projektszerződések és projektek közvetlen szinkronizálása a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Project Service Automation projektszerződéseinek és projektjeinek közvetlenül a Microsoft Dynamics 365 Finance szolgáltatásba történő szinkronizálására használatosak.
author: KimANelson
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: b44fc116f1dcaa1275b2262487ef9114bce639c6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773854"
---
# <a name="synchronize-project-contracts-and-projects-directly-from-project-service-automation-to-finance-and-operations"></a>Projektszerződések és projektek közvetlen szinkronizálása a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Project Service Automation projektszerződéseinek és projektjeinek közvetlenül a Dynamics 365 Finance szolgáltatásba történő szinkronizálására használatosak.

> [!NOTE] 
> Az Enterprise Edition 7.3.0 használata esetén telepítenie kell a KB 4074835 csomagot.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Adatáramlás a Project Service Automation és a Finance között

> [!NOTE]
> Mielőtt használhatná a Project Service Automation és Finance integrációs megoldást, meg kell ismerkednie a Dynamics 365 adatintegrációs funkciójával.

A Project Service Automation és a Finance közötti integrációs megoldás az adatintegrációs funkciót használja a Project Service Automation és Finance példányok közötti szinkronizáláshoz. Az integrációs sablon, mely az adatintegráció funkcióban érhető el lehetővé teszi, hogy a projektszerződések, projektek, a projektszerződéssorok és projektszerződéssor mérföldkövek áramoltatását a Project Service Automation és a Finance között.

A következő ábra bemutatja a Project Service Automation és a Finance közötti adatszinkronizálást.

[![Adatáramlás a Project Service Automation és a Finance integrációjához](./media/ProjectsAndContractsFlow_upd.JPG)](./media/ProjectsAndContractsFlow.JPG)

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok eléréséhez a Microsoft Power Apps adminisztrációs központban válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.

A következő sablonok és alapul szolgáló feladatok használhatók a projektszerződések és projektek szinkronizálásához a Project Service Automation és Finance között:

### <a name="integrating-with-dynamics-365-project-service-automation-v2x"></a>Integráció a Dynamics 365 Project Service Automation 2.x verzióval
- **Sablon neve az adatintegrációban:** Projektek és szerződések (PSA to Fin and Ops)
- **A projekt tevékenységeinek nevei:**

    - Projektszerződések PSA to Fin and Ops
    - Projektek PSA to Fin and Ops
    - Projektszerződéssorok PSA to Fin and Ops
    - Projektszerződéssor mérföldkövek PSA to Fin and Ops
  
### <a name="integrating-with-dynamics-365-project-service-automation-v3x"></a>Integráció a Dynamics 365 Project Service Automation 3.x verzióval
A Project Service Automation olyan sémamódosítást tartalmaz, amely hatással van a projektterv mérföldkősablonra, és a sablon 2 verziójának használatát igényli a Project Service Automation 3.x a Dynamics 365 integrálásához.

- **Sablon neve az adatintegrációban:** Projektek és szerződések (PSA 3.x – Fin and Ops) – 2 verzió
- **A projekt tevékenységeinek nevei:**

    - Projektszerződések PSA to Fin and Ops
    - Projektek PSA to Fin and Ops
    - Projektszerződéssorok PSA to Fin and Ops
    - Projektszerződéssor mérföldkövek PSA to Fin and Ops

Projektek és projektszerződések szinkronizálása előtt szinkronizálnia kell a fiókokat.

## <a name="entity-set"></a>Entitás beállítása

| Project Service Automation       | Pénzügy                                                |
|----------------------------------|--------------------------------------------------------|
| Rendelések                           | Integrációs entitás a projektszerződéshez                |
| Projektek                         | Integrációs entitás a projekthez                         |
| Rendeléssorok                      | Integrációs entitás a projektszerződéssorhoz           |
| Projektszerződéssor mérföldkövek | Integrációs entitás a projektszerződéssor mérföldkövéhez |

## <a name="entity-flow"></a>Entitás folyamata

Projektszerződések kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance alkalmazásba projektszerződésként. Az integrációs sablon részeként állíthatja be az integráció forrását a Finance alkalmazásban a projektszerződéshez.

A munkaidő- és anyagprojekt, illetve a Fix árú projektek kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance alkalmazásba projektként. Az integrációs sablon részeként állíthatja be az integráció forrását a Finance alkalmazásban a projekthez.

Projektszerződéssorok a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance alkalmazásba projektszerződés számlázási szabályként. Ha a számlázási módszer eltér az alapértelmezett projekttípustól, a szinkronizálás frissíti a projekttípust a szerződéssor projekthez és a projektcsoporthoz.

Projektszerződéssor mérföldkövek kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance alkalmazásba projektszerződés számlázási szabály mérföldkőként.

## <a name="project-service-automation-to-finance-integration-solution"></a>Project Service Automation és a Finance integrációs megoldás

A **Projekt szerződésazonosító** mező a **Projektszerződések** oldalon érhető el. Ez a mező egy természetes és egyedi kulcs az integráció támogatásához.

Új projektszerződés létrehozása esetén, ha egy **Projektszerződés azonosító** értéke nem létezik, egy számsorozat alapján automatikusan generálva lesz. Az érték **ORD**-ből áll, amelyet egy növekvő számsorozat és egy hat karakterből álló utótag követ. Egy példa: **ORD-01022-Z4M9Q0**.

A **Projektszám** a mező a **Projektek** oldalon érhető el. Ez a mező egy természetes és egyedi kulcs az integráció támogatásához.

Új projekt létrehozása esetén, ha egy **Projektszám** értéke még nem létezik, egy számsorozat alapján automatikusan generálva lesz. Az érték **PRJ**-ből áll, amelyet egy növekvő számsorozat és egy hat karakterből álló utótag követ. Egy példa: **PRJ-01049-CCNID0**.

Project Service Automation és Finance közötti integrációs megoldás alkalmazása esetén egy frissítési parancsprogram állítja be a **Projektszerződés azonosítót** és a **Projektszám mezőt** a Project Service Automation meglévő projektjeiben.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

- Projektek és projektszerződések szinkronizálása előtt szinkronizálnia kell a fiókokat.
- A kapcsolatbeállításában adjon hozzá egy integráció kulcsmező hozzárendelést a következőhöz: **msdyn\_organizationalunits**, **msdyn\_name \[Name\]**. Előfordulhat, hogy először egy projektet kell hozzáadnia a kapcsolatkészlethez. További információkért tekintse át az [Adatok integrálása a Common Data Service for Apps alkalmazásba](https://docs.microsoft.com/powerapps/administrator/data-integrator) részt.
- A kapcsolatbeállításában adjon hozzá egy integráció kulcsmező hozzárendelést a következőhöz: **msdyn\_projects**, **msdynce\_projectnumber \[Project Number\]**. Előfordulhat, hogy először egy projektet kell hozzáadnia a kapcsolatkészlethez. További információkért tekintse át az [Adatok integrálása a Common Data Service for Apps alkalmazásba](https://docs.microsoft.com/powerapps/administrator/data-integrator) részt.
- **SourceDataID** projekt szerződések és projektek frissíthetők egy másik értékre, vagy eltávolíthatók a hozzárendelésből. Az alapértelmezett sablonérték **Project Service Automation**.
- A **PaymentTerms** hozzárendelést frissíteni kell, hogy az megfeleljenek Finance alkalmazásban érvényes fizetési feltételeknek. A hozzárendelést el is távolíthatja a projektfeladatból. Az alapértelmezett értékhozzárendelés alapértelmezett értékeket tartalmaz a bemutató adatokból. Az alábbi táblázat bemutatja a Project Service Automation értékeit.

    | Érték | Leírás   |
    |-------|---------------|
    | 1     | Nettó 30        |
    | 2     | 2% 10, nettó 30 |
    | 3     | Nettó 45        |
    | 4     | Nettó 60        |

## <a name="power-query"></a>Power Query

Microsoft Power Query for Excelt kell használnia az adatok szűréséhez, ha teljesülnek a következő feltételek:

- A Dynamics 365 Sales értékesítési rendeléseket tartalmaz.
- Több szervezeti egységre van a Project Service Automation alkalmazásban, és ezen szervezeti egységeket több jogi személyhez lesznek rendelve a Finance alkalmazásban.

Ha a Power Query-t kell használnia, kövesse az alábbiakat:

- A Projektek és szerződések (PSA to Fin and Ops) sablonjának van egy alapértelmezett szűrője, mely csak a következőhöz tartalmaz értékesítési rendeléseket: **Munkaelem (msdyn\_ordertype = 192350001)** típus. Ezzel a szűrővel gondoskoshat arról, hogy ne legyenek létrehozva projektszerződések az értékesítési rendelésekhez a Finance alkalmazásban. Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt.
- Létre kell hoznia egy Power Query szűrőt, mely csak azon szerződéses szervezetek tartalmazza melyeket az integrációs kapcsolati készlet jogi személyéhez kell szinkronizálni. Ha például azon projektszerződéseket, melyek szerződéses szervezeti egysége Contoso US az USSI a jogi személyhez kell szinkronizálni de a projektszerződéseket, amelyek a Contoso Global szerződéses szervezeti egységhez tartoznak az USMF jogi személyhez kell szinkronizálni. Ha nem adja hozzá ezt a szűrőt a feladat-hozzárendeléshez, az összes projektszerződés a kapcsolati készletben meghatározott jogi személyhez lesz szinkronizálva, függetlenül a szerződés szervezeti egységtől.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

> [!NOTE] 
> A **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState**, és **AddressZipCode** mezők nem szerepelnek a projektszerződések az alapértelmezett hozzárendeléseiben. A hozzárendelésekhez adhat meg, ha szükséges, hogy ezek az adatok szinkronizálva legyenek a projektszerződésekhez.
>
> A **Description**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber**, és **ProjectType** mezők nem szerepelnek a projektek alapértelmezett hozzárendeléseiben. A hozzárendelésekhez adhat meg, ha szükséges, hogy ezek az adatok szinkronizálva legyenek a projektekhez.

Az alábbi ábrán példákat láthat sablonfeladatok hozzárendelésére az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance irányban.

[![Sablon-hozzárendelés](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)

[![Sablon-hozzárendelés](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)

[![Sablon-hozzárendelés](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)

[![Sablon-hozzárendelés](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)

#### <a name="project-contract-line-milestone-mapping-in-the-projects-and-contracts-psa-3x-to-dynamics---v2-template"></a>A projekt-szerződésisor mérföldkő-feltérképezése a projektekben és szerződésekben (PSA 3.x – Dynamics) – v2 sablon:

[![Sablon-hozzárendelés](./media/ProjectContractLineMilestoneMapping_v2.jpg)](./media/ProjectContractLineMilestoneMapping_v2.jpg)
