---
title: Foglalkoztatás nélküli dolgozók
description: Azok a munkavállalók, akiknek nincs jövőbeli, aktív vagy múltbeli állása a szervezeténél, megjelennek az Alkalmazottak nélkül oldalon.
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
ms.openlocfilehash: d0b8fe7dd0818fa1c3cc4224e73035849f9dadfe
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070551"
---
# <a name="workers-without-employment"></a>Foglalkoztatás nélküli dolgozók


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Azok a munkavállalók, akiknek nincs jövőbeli, aktív vagy történelmi munkaviszonyuk az Ön szervezeténél, megjelennek az oldalon **Munkavállalás nélkül dolgozók** oldalon. Az ilyen típusú munkavállalók akkor jelenhetnek meg, ha olyan munkavállalókat importál, akiknek nincs munkaügyi nyilvántartása, vagy ha törli egy munkavállaló foglalkoztatását a következőn keresztül: **Munkások \> Foglalkoztatási előzmények**.

Alapértelmezés szerint a **Munkavállalás nélkül dolgozók** oldal a következő szerepkörök számára érhető el:

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
