---
title: Biztonsági diagnosztika feladatrögzítésekhez
description: Ez a témakör azt mutatja be, hogyan lehet elemezni és kezelni a biztonsági engedélykövetelményeket a feladatrögzítés alapján.
author: Peakerbl
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: cb4d544d8d74ad10432901381253f84ec9331ae7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745765"
---
# <a name="security-diagnostics-for-task-recordings"></a>Biztonsági diagnosztika feladatrögzítésekhez

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>Előzetes feladatok

Ez a témakör azt mutatja be, hogyan lehet elemezni és kezelni a biztonsági engedélykövetelményeket a feladatrögzítés alapján. A témakör lépéseinek elvégzése előtt rendelkeznie kell a elemezni kívánt üzleti folyamat feladatrögzítésével. Üzleti folyamat rögzítéséhez lásd: [Feladatrögzítő erőforrásai](../../user-interface/task-recorder.md). 

## <a name="manage-security-for-a-task-recording"></a>Biztonság kezelése a feladatrögzítéshez

1. Nyissa meg a **Rendszerfelügyelet** > **Biztonság** > **Biztonsági diagnosztika feladatrögzítésekhez** lehetőséget.
2. Nyissa meg a feladatrögzítést a helyéről. Válassza a **Megnyitás erről a számítógépről** vagy a **Megnyitás a Lifecycle Services-ből** lehetőséget, majd válassza a **Bezárás** lehetőséget.
3. Ez megnyitja a **Biztonsági menüelem részletei** lapot, amely felsorolja a folyamathoz szükséges biztonsági objektumokat.

 > [!NOTE]
 > A **Művelet** és a **Kimenet** menüelemek nem szerepelnek a listában.

4. Az **Felhasználóazonosító** mezőben válasszon ki egy felhasználót. Ha a felhasználó néhány menüelemhez nem rendelkezik jogosultsággal, akkor a **Hiányzó engedélyek** mező az **Igen** értékre frissül.
  
  ![Biztonsági menüelem részletei lap](../media/Security-Menu-Item-Details.png)

5. A **Hivatkozás hozzáadása** lehetőséggel megjelenítheti a biztonsági objektumok listáját, többek között a szerepeket, kötelezettségeket és jogosultságokat, amelyek megadják a hiányzó engedélyt.
6. Válasszon ki egy biztonsági objektumot a listából:

    - Ha a **Szerepkör** be van jelölve, akkor válassza a **Szerepkör hozzáadása a felhasználóhoz** lehetőséget. Ez megnyitja a **Felhasználók társítása a szerepkörökhöz** oldalt. További információt a [Felhasználók hozzárendelése biztonsági szerepkörökhöz](assign-users-security-roles.md) oldalon talál.
    - Ha a **Feladat** van kiválasztva, válassza a **Feladat hozzáadása a szerepkörhöz** lehetőséget , válassza ki azokat a szerepköröket, amelyekhez fel kell adni a feladatot, majd kattintson az **OK** gombra.
    - Ha a **Jogosultság** van kiválasztva, válassza a **Jogosultság hozzáadása feladatokhoz** lehetőséget , válassza ki azokat a szerepköröket, amelyekhez fel kell adni a feladatot, majd kattintson az **OK** gombra.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]