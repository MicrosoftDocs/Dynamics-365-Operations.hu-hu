---
title: Foglalkoztatás nélküli dolgozók
description: A jövőbeli, aktív vagy múltbeli Munkanélküli dolgozók a szervezetnél megjelennek a Munkanélküli dolgozók űrlapon.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71cb119e533e64b14badf65f55e8c4d5aa4c4b2f
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356584"
---
# <a name="workers-without-employment"></a>Foglalkoztatás nélküli dolgozók

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A jövőbeli, aktív vagy múltbeli Munkanélküli dolgozók a szervezetnél megjelennek a **Munkanélküli dolgozók** űrlapon. Az ilyen állapotú dolgozók akkor is megjelenhetnek, ha alkalmazásrekord nélküli dolgozókat importál, vagy ha a dolgozók munkaviszonyát a **Dolgozók > Foglalkoztatási előzmények** segítségével törli.

Alapértelmezés szerint a **Munkanélküli dolgozók** űrlap a következő szerepkörök számára érhető el:

- Emberi erőforrás asszisztens
- Emberi erőforrás vezető
- Toborzó
- Kompenzáció és juttatások vezető
- Bérszámfejtő
- Bérszámfejtési vezető
- Képzési vezető

A **Munkanélküli dolgozók** listájáról törölheti a felsorolt személyeket. Alapértelmezés szerint ez a jogosultság az Emberi erőforrások asszisztens szerepköre. Ezt a jogosultságot a következő lépésekkel más szerepköröknek adhatja át:

1. Válassza a **Rendszerfelügyelet** elemet, majd a **Biztonság konfigurálása** lapot.

2. A **Jogosultságok** lapon szűrje a **Jogosultságok** listáját a **Dolgozók karbantartása** céljából.

   [![Jogosultságok listájának szűrése.](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. Válassza a **Hivatkozások** oszlopban a **Megjelenítendő menüelemek** elemet.

4. A **Megjelenítendő menüelemek** közül válassza ki a **HcmWorkersWithoutEmployment** elemet.

   [![Kiválasztás (képernyő).](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. A **Törlési** engedélyt módosítsa **Engedélyezre**.

6. Válassza ki a **Nem közzétett objektumok** lapot.

7. Válassza az **Összes közzététele** lehetőséget.

   [![Változások közzététele.](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]