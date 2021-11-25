---
title: Foglalkoztatás nélküli dolgozók
description: A jövőbeli, aktív vagy múltbeli foglalkoztatással nem bíró dolgozók a szervezetnél megjelennek a foglalkoztatás nélküli dolgozók oldalon.
author: twheeloc
ms.date: 11/03/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d282c0fac00d6bc410717dd156aef9ffce352c6d
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771290"
---
# <a name="workers-without-employment"></a>Foglalkoztatás nélküli dolgozók

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Azok a dolgozók, akiknek nincs jövőbeli, aktív vagy múltbeli munkaviszonya a szervezettel, megjelennek az alkalmazás nélküli dolgozók **·** oldalon. Az ilyen típusú dolgozók akkor is megjelenhetnek, ha olyan dolgozókat importál, akiknek nincs alkalmazotti rekordja, vagy ha a dolgozók foglalkoztatását törli a dolgozók munkavállalási **\> előzményein keresztül**.

Alapértelmezés szerint az alkalmazás nélküli dolgozók lap a következő **·** szerepkörök számára érhető el:

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

   [![ Jogosultságok listájának szűrése.](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. Válassza a **Hivatkozások** oszlopban a **Megjelenítendő menüelemek** elemet.

4. A **Megjelenítendő menüelemek** közül válassza ki a **HcmWorkersWithoutEmployment** elemet.

   [![ Kiválasztás (képernyő).](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. A **Törlési** engedélyt módosítsa **Engedélyezre**.

6. Válassza ki a **Nem közzétett objektumok** lapot.

7. Válassza az **Összes közzététele** lehetőséget.

   [![ Változások közzététele.](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
