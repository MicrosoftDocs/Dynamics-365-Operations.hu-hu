---
title: Biztonsági diagnosztika feladatrögzítésekhez
description: Ez a témakör azt mutatja be, hogyan lehet elemezni és kezelni a biztonsági engedélykövetelményeket a feladatrögzítés alapján.
author: Peakerbl
manager: AnnBe
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: fada3abb9362426c7c9ec33f5d25552edf3ef630
ms.sourcegitcommit: 71fec2553158c332ce4d4bfcedc2c1ab58c1a1a5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2020
ms.locfileid: "3340675"
---
# <a name="security-diagnostics-for-task-recordings"></a><span data-ttu-id="10e86-103">Biztonsági diagnosztika feladatrögzítésekhez</span><span class="sxs-lookup"><span data-stu-id="10e86-103">Security diagnostics for task recordings</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a><span data-ttu-id="10e86-104">Előzetes feladatok</span><span class="sxs-lookup"><span data-stu-id="10e86-104">Before you begin</span></span>

<span data-ttu-id="10e86-105">Ez a témakör azt mutatja be, hogyan lehet elemezni és kezelni a biztonsági engedélykövetelményeket a feladatrögzítés alapján.</span><span class="sxs-lookup"><span data-stu-id="10e86-105">This topic provides information about how to analyze and manage security permission requirements based on a task recording.</span></span> <span data-ttu-id="10e86-106">A témakör lépéseinek elvégzése előtt rendelkeznie kell a elemezni kívánt üzleti folyamat feladatrögzítésével.</span><span class="sxs-lookup"><span data-stu-id="10e86-106">Before you complete the steps in this topic, you must have a task recording of the business process that you want to analyze.</span></span> <span data-ttu-id="10e86-107">Üzleti folyamat rögzítéséhez lásd: [Feladatrögzítő erőforrásai](../../user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="10e86-107">To record a business process, see [Task recorder resources](../../user-interface/task-recorder.md).</span></span> 

## <a name="manage-security-for-a-task-recording"></a><span data-ttu-id="10e86-108">Biztonság kezelése a feladatrögzítéshez</span><span class="sxs-lookup"><span data-stu-id="10e86-108">Manage security for a task recording</span></span>

1. <span data-ttu-id="10e86-109">Nyissa meg a **Rendszerfelügyelet** > **Biztonság** > **Biztonsági diagnosztika feladatrögzítésekhez** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10e86-109">Go to **System administration** > **Security** > **Security diagnostic for task recording**.</span></span>
2. <span data-ttu-id="10e86-110">Nyissa meg a feladatrögzítést a helyéről.</span><span class="sxs-lookup"><span data-stu-id="10e86-110">Open the task recording from its location.</span></span> <span data-ttu-id="10e86-111">Válassza a **Megnyitás erről a számítógépről** vagy a **Megnyitás a Lifecycle Services-ből** lehetőséget, majd válassza a **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10e86-111">Select **Open from this PC** or **Open from Lifecycle Services**, and then select **Close**.</span></span>
3. <span data-ttu-id="10e86-112">Ez megnyitja a **Biztonsági menüelem részletei** lapot, amely felsorolja a folyamathoz szükséges biztonsági objektumokat.</span><span class="sxs-lookup"><span data-stu-id="10e86-112">This will open the **Security menu item details** page that lists the security objects required for the process.</span></span>

 > [!NOTE]
 > <span data-ttu-id="10e86-113">A **Művelet** és a **Kimenet** menüelemek nem szerepelnek a listában.</span><span class="sxs-lookup"><span data-stu-id="10e86-113">The **Action** and **Output** menu items are not included in the list.</span></span>

4. <span data-ttu-id="10e86-114">Az **Felhasználóazonosító** mezőben válasszon ki egy felhasználót.</span><span class="sxs-lookup"><span data-stu-id="10e86-114">In the **User ID** field, select a user.</span></span> <span data-ttu-id="10e86-115">Ha a felhasználó néhány menüelemhez nem rendelkezik jogosultsággal, akkor a **Hiányzó engedélyek** mező az **Igen** értékre frissül.</span><span class="sxs-lookup"><span data-stu-id="10e86-115">If the user does not have permissions for some menu items, the **Missing permissions** field will update to **Yes**.</span></span>
  
  ![Biztonsági menüelem részletei lap](../media/Security-Menu-Item-Details.png)

5. <span data-ttu-id="10e86-117">A **Hivatkozás hozzáadása** lehetőséggel megjelenítheti a biztonsági objektumok listáját, többek között a szerepeket, kötelezettségeket és jogosultságokat, amelyek megadják a hiányzó engedélyt.</span><span class="sxs-lookup"><span data-stu-id="10e86-117">Select **Add Reference** to see a list of the security objects, including roles, duties, and privileges that grant the missing permission.</span></span>
6. <span data-ttu-id="10e86-118">Válasszon ki egy biztonsági objektumot a listából:</span><span class="sxs-lookup"><span data-stu-id="10e86-118">Select a security object from the list:</span></span>

    - <span data-ttu-id="10e86-119">Ha a **Szerepkör** be van jelölve, akkor válassza a **Szerepkör hozzáadása a felhasználóhoz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10e86-119">If **Role** is selected, select **Add role to user**.</span></span> <span data-ttu-id="10e86-120">Ez megnyitja a **Felhasználók társítása a szerepkörökhöz** oldalt.</span><span class="sxs-lookup"><span data-stu-id="10e86-120">This will open the **Assign users to roles** page.</span></span> <span data-ttu-id="10e86-121">További információt a [Felhasználók hozzárendelése biztonsági szerepkörökhöz](assign-users-security-roles.md) oldalon talál.</span><span class="sxs-lookup"><span data-stu-id="10e86-121">For more information, see [Assign users to security roles](assign-users-security-roles.md) page.</span></span>
    - <span data-ttu-id="10e86-122">Ha a **Feladat** van kiválasztva, válassza a **Feladat hozzáadása a szerepkörhöz** lehetőséget , válassza ki azokat a szerepköröket, amelyekhez fel kell adni a feladatot, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="10e86-122">If **Duty** is selected, select **Add duty to role**, select the roles that the duty should be added to, and then select **OK**.</span></span>
    - <span data-ttu-id="10e86-123">Ha a **Jogosultság** van kiválasztva, válassza a **Jogosultság hozzáadása feladatokhoz** lehetőséget , válassza ki azokat a szerepköröket, amelyekhez fel kell adni a feladatot, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="10e86-123">If **Privilege** is selected, select **Add privilege to duties**, select the roles that the duty should be added to, and then select **OK**.</span></span>
