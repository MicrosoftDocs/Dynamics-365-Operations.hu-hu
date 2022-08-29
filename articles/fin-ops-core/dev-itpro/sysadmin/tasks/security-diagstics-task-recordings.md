---
title: Biztonsági diagnosztika feladatrögzítésekhez
description: Ez a cikk a feladatrögzítésen alapuló biztonsági engedélykövetelmények elemzésével és kezelésével kapcsolatban tartalmaz tájékoztatást.
author: Peakerbl
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.search.form: ''
ms.openlocfilehash: e564a0499cb1a5dc00fc027c20a027f9b454600c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272520"
---
# <a name="security-diagnostics-for-task-recordings"></a>Biztonsági diagnosztika feladatrögzítésekhez

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>Előzetes feladatok

Ez a cikk a feladatrögzítésen alapuló biztonsági engedélykövetelmények elemzésével és kezelésével kapcsolatban tartalmaz tájékoztatást. A cikk lépéseit csak azt megelőzően lehet végrehajtani, hogy rögzítenének egy feladatrögzítést az elemezni kívánt üzleti folyamatról. Üzleti folyamat rögzítéséhez lásd: [Feladatrögzítő erőforrásai](../../user-interface/task-recorder.md). 

## <a name="manage-security-for-a-task-recording"></a>Biztonság kezelése a feladatrögzítéshez

1. Nyissa meg a **Rendszerfelügyelet** > **Biztonság** > **Biztonsági diagnosztika feladatrögzítésekhez** lehetőséget.
2. Nyissa meg a feladatrögzítést a helyéről. Válassza a **Megnyitás erről a számítógépről** vagy a **Megnyitás a Lifecycle Services-ből** lehetőséget, majd válassza a **Bezárás** lehetőséget.
3. Ez megnyitja a **Biztonsági menüelem részletei** lapot, amely felsorolja a folyamathoz szükséges biztonsági objektumokat.

 > [!NOTE]
 > A **Művelet** és a **Kimenet** menüelemek nem szerepelnek a listában.

4. Az **Felhasználóazonosító** mezőben válasszon ki egy felhasználót. Ha a felhasználó néhány menüelemhez nem rendelkezik jogosultsággal, akkor a **Hiányzó engedélyek** mező az **Igen** értékre frissül.
  
  ![Biztonsági menüelem részletei lap.](../media/Security-Menu-Item-Details.png)

5. A **Hivatkozás hozzáadása** lehetőséggel megjelenítheti a biztonsági objektumok listáját, többek között a szerepeket, kötelezettségeket és jogosultságokat, amelyek megadják a hiányzó engedélyt.
6. Válasszon ki egy biztonsági objektumot a listából:

    - Ha a **Szerepkör** be van jelölve, akkor válassza a **Szerepkör hozzáadása a felhasználóhoz** lehetőséget. Ez megnyitja a **Felhasználók társítása a szerepkörökhöz** oldalt. További információt a [Felhasználók hozzárendelése biztonsági szerepkörökhöz](assign-users-security-roles.md) oldalon talál.
    - Ha a **Feladat** van kiválasztva, válassza a **Feladat hozzáadása a szerepkörhöz** lehetőséget , válassza ki azokat a szerepköröket, amelyekhez fel kell adni a feladatot, majd kattintson az **OK** gombra.
    - Ha a **Jogosultság** van kiválasztva, válassza a **Jogosultság hozzáadása feladatokhoz** lehetőséget , válassza ki azokat a szerepköröket, amelyekhez fel kell adni a feladatot, majd kattintson az **OK** gombra.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
