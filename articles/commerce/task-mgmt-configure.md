---
title: Feladatkezelés konfigurálása
description: Ez a témakör azt mutatja be, hogyan kell konfigurálni a feladatkezelési szolgáltatást a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 9a4775c2dba2b9aa8e671ab6c246000303b3a37e
ms.sourcegitcommit: 80cbb7d22267aa6a0ae0568d0063fb95556958a5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036855"
---
# <a name="configure-task-management"></a><span data-ttu-id="cef51-103">Feladatkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="cef51-103">Configure task management</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cef51-104">Ez a témakör azt mutatja be, hogyan kell konfigurálni a feladatkezelési szolgáltatást a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="cef51-104">This topic describes how to configure task management features in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="cef51-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="cef51-105">Overview</span></span>

<span data-ttu-id="cef51-106">Mielőtt a Dynamics 365 Commerce alkalmazásban vezetők és az alkalmazottak használhatják a Commerce feladatkezelési funkcióit, konfigurálni kell a feladatkezelést.</span><span class="sxs-lookup"><span data-stu-id="cef51-106">Before Dynamics 365 Commerce managers and employees can use the task management features in Commerce, task management must be configured.</span></span> <span data-ttu-id="cef51-107">A konfigurálás lépései között szerepelnek a vezetők és az alkalmazottak engedélyei, az engedélyek elosztása a pénztári (POS) kliensekhez, a pénztári értesítések beállítása, valamint a **Feladatok** csempéjének konfigurálása egy pénztári alkalmazás kezdőlapján.</span><span class="sxs-lookup"><span data-stu-id="cef51-107">Configuration steps include granting permissions to managers and employees, distributing permissions to point of sale (POS) clients, setting up POS notifications, and configuring the **Tasks** tile on the home page of a POS application.</span></span>

## <a name="configure-permissions-for-store-managers"></a><span data-ttu-id="cef51-108">Engedélyek konfigurálása az üzletvezetők számára</span><span class="sxs-lookup"><span data-stu-id="cef51-108">Configure permissions for store managers</span></span>

<span data-ttu-id="cef51-109">Minden dolgozó egy adott üzletben megtekintheti az üzlethez rendelt összes feladatot.</span><span class="sxs-lookup"><span data-stu-id="cef51-109">Every worker in a given store can view all tasks that are assigned to that store.</span></span> <span data-ttu-id="cef51-110">A hozzájuk társított feladatok állapotát is frissíteni tudják.</span><span class="sxs-lookup"><span data-stu-id="cef51-110">They can also update the status of the tasks that are assigned to them.</span></span> <span data-ttu-id="cef51-111">Azonban a szereplők, mint például az üzletvezetők számára feladatkezelési jogosultság szükséges az üzlethez rendelt feladatok kezeléséhez és az egyfunkciós feladatok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="cef51-111">However, personas such as store managers must have task management permissions to manage tasks that are assigned to the store and to create single-purpose tasks.</span></span>

<span data-ttu-id="cef51-112">A következő lépésekkel konfigurálhatja az üzletvezetők feladatkezelési engedélyeit.</span><span class="sxs-lookup"><span data-stu-id="cef51-112">To configure task management permissions for store managers, follow these steps.</span></span>

1. <span data-ttu-id="cef51-113">Nyissa meg a következőt: **Retail és Commerce \> Alkalmazottak \> Engedélycsoportok**.</span><span class="sxs-lookup"><span data-stu-id="cef51-113">Go to **Retail and Commerce \> Employees \> Permission groups**.</span></span>
1. <span data-ttu-id="cef51-114">Jelöljön ki egy adott jogosultsági csoportot (például **Vezető**), majd válassza a **Szerkesztés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="cef51-114">Select a specific permission group (for example, **Manager**), and then select **Edit**.</span></span>
1. <span data-ttu-id="cef51-115">Az **Engedélyek** gyorslapon állítsa be a **Feladatkezelés engedélyezése** beállítást **Igen**értékre.</span><span class="sxs-lookup"><span data-stu-id="cef51-115">On the **Permissions** FastTab, set the **Allow task management** option to **Yes**.</span></span>
1. <span data-ttu-id="cef51-116">Az **Értesítések** gyorslapon adja hozzá a **Feladatkezelés** műveletet, és adjon meg egy értéket a **Megjelenítési sorrend** mezőben.</span><span class="sxs-lookup"><span data-stu-id="cef51-116">On the **Notifications** FastTab, add the **Task management** operation, and enter a value in the **Display order** field.</span></span> <span data-ttu-id="cef51-117">Írja be például a **2** értéket, ha a **Rendelés teljesítése** művelethez már tartozik **Megjelenítési sorrend** érték – az **1**.</span><span class="sxs-lookup"><span data-stu-id="cef51-117">For example, enter **2** if the **Order fulfillment** operation already has a **Display order** value of **1**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cef51-118">Ha egy nem vezető személynek a pénztárban rendelkeznie kell feladatkezelési engedélyekkel akkor engedélyt adhat ennek a személynek.</span><span class="sxs-lookup"><span data-stu-id="cef51-118">If a non-manager persona must have task management permissions in the POS, you can grant permission to the individual.</span></span> <span data-ttu-id="cef51-119">Azt is megteheti, hogy létrehoz egy új jogosultsági csoportot a nem vezetőknek, és beállítja a **Feladatkezelés engedélyezése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="cef51-119">Alternatively, you can create a new permission group for non-managers and set the **Allow task management** option to **Yes**.</span></span>

<span data-ttu-id="cef51-120">A következő ábra megmutatja, hogyan konfigurálhatja az üzletvezetők feladatkezelési engedélyeit.</span><span class="sxs-lookup"><span data-stu-id="cef51-120">The following illustration shows how to configure task management permissions for store managers.</span></span>

![Az üzletvezetők feladatkezelési engedélyeinek konfigurálása](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a><span data-ttu-id="cef51-122">Alkalmazottak engedélyeinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="cef51-122">Configure permissions for employees</span></span>

<span data-ttu-id="cef51-123">Az alkalmazottaknak rendelkezniük kell a feladatlisták létrehozásához szükséges engedélyekkel, a hozzárendelési feltételek kezelésével és bármely feladatlista ismétlődésének beállításával kapcsolatos engedélyekkel.</span><span class="sxs-lookup"><span data-stu-id="cef51-123">Employees must have permissions to create task lists, manage assignment criteria, and configure the recurrence of any task list.</span></span> <span data-ttu-id="cef51-124">Az engedélyek konfigurálásához az alkalmazottakat a **Retail feladatkezelő** szerepkörhöz kell rendelni.</span><span class="sxs-lookup"><span data-stu-id="cef51-124">To configure these permissions, you assign employees to the **Retail task manager** role.</span></span>

<span data-ttu-id="cef51-125">Egy munkavállaló engedélyeinek konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cef51-125">To configure permissions for an employee, follow these steps.</span></span>

1. <span data-ttu-id="cef51-126">Nyissa meg a következőt: **Retail és Commerce \> Alkalmazottak \> Felhasználók**.</span><span class="sxs-lookup"><span data-stu-id="cef51-126">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="cef51-127">Válasszon egy alkalmazottat.</span><span class="sxs-lookup"><span data-stu-id="cef51-127">Select an employee.</span></span>
1. <span data-ttu-id="cef51-128">A **Felhasználó szerepkörei** gyorslapon válassza a **Szerepkörök hozzárendelése** elemet.</span><span class="sxs-lookup"><span data-stu-id="cef51-128">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="cef51-129">A **Szerepkörök társítása a felhasználóhoz** párbeszédpanelen válassza ki a **Retail feladatkezelő** szerepkört, majd kattintsonaz **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cef51-129">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

## <a name="distribute-permissions-to-pos-clients"></a><span data-ttu-id="cef51-130">Jogosultságok elosztása a POS-ügyfeleknek</span><span class="sxs-lookup"><span data-stu-id="cef51-130">Distribute permissions to POS clients</span></span>

<span data-ttu-id="cef51-131">Mielőtt az alkalmazottak felhasználhatnák a POS-ügyfeleket, az engedélyeket meg kell osztani és szinkronizálni kell ezekhez az ügyfelekhez.</span><span class="sxs-lookup"><span data-stu-id="cef51-131">Before employees can use POS clients, permissions must be distributed and synced to those clients.</span></span>

<span data-ttu-id="cef51-132">Az engedélyek terjesztéséhez a POS-ügyfelekhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cef51-132">To distribute permissions to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="cef51-133">Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="cef51-133">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="cef51-134">Válassza ki az **1060** (**Személyzet**) elosztási ütemezést, majd válassza a **Futtatás most** parancsot.</span><span class="sxs-lookup"><span data-stu-id="cef51-134">Select the **1060** (**Staff**) distribution schedule, and then select **Run now**.</span></span>
1. <span data-ttu-id="cef51-135">Válassza ki az **1070** (**Csatorna konfigurációja**) elosztási ütemezést, majd válassza a **Futtatás most** parancsot.</span><span class="sxs-lookup"><span data-stu-id="cef51-135">Select the **1070** (**Channel configuration**) distribution schedule, and then select **Run now**.</span></span>

## <a name="configure-pos-notifications-for-tasks"></a><span data-ttu-id="cef51-136">POS-értesítések konfigurálása a feladatokhoz</span><span class="sxs-lookup"><span data-stu-id="cef51-136">Configure POS notifications for tasks</span></span>

<span data-ttu-id="cef51-137">A Feladatkezelést úgy kell konfigurálni, hogy a POS-alkalmazásban az értesítések elérhetők legyenek.</span><span class="sxs-lookup"><span data-stu-id="cef51-137">Task management must be configured so that notifications are available in the POS application.</span></span>

<span data-ttu-id="cef51-138">A POS-értesítések konfigurálásához a feladatokhoz kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cef51-138">To configure POS notifications for tasks, follow these steps.</span></span>

1. <span data-ttu-id="cef51-139">Lépjen a **Retail és Commerce \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Pénztárműveletek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cef51-139">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="cef51-140">Keresse meg az **1400** műveletet (**Feladatkezelés**), és jelölje be az **Értesítések engedélyezése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="cef51-140">Find operation **1400** (**Task management**), and select the **Enable notifications** check box for it.</span></span>

<span data-ttu-id="cef51-141">A következő ábra a **Feladatkezelő** műveletet jeleníti meg a **Pénztári műveletek** lapon.</span><span class="sxs-lookup"><span data-stu-id="cef51-141">The following illustration shows the **Task management** operation on the **POS operations** page.</span></span>

![Feladatkezelő működése a POS-műveletek lapon](media/HQ-POS-Tasks-Notifications.png)

<span data-ttu-id="cef51-143">A POS-értesítések konfigurálásával kapcsolatos további tudnivalókat lásd: [Rendelési értesítések megjelenítése a pénztárnál (POS)](notifications-pos.md).</span><span class="sxs-lookup"><span data-stu-id="cef51-143">For more information about how to configure POS notifications, see [Show order notifications in the point of sale (POS)](notifications-pos.md).</span></span>

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a><span data-ttu-id="cef51-144">A Feladatok csempe konfigurálása a Pénztáralkalmazás kezdőlapján</span><span class="sxs-lookup"><span data-stu-id="cef51-144">Configure the Tasks tile on a POS application home page</span></span>

<span data-ttu-id="cef51-145">Mielőtt egy Pénztáralkalmazás kezdőlapján beállítja a **Feladatok** csempéjét:, lásd: [Képernyő-elrendezések a pénztár (POS) számára](pos-screen-layouts.md), ahol megtudhatja, hogy hogyan lehet beállítani és új gombokat hozzáadni a pénztár képernyő elrendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="cef51-145">Before you configure the **Tasks** tile on the home page of a POS application, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information about how to configure and add new buttons to a POS screen layout.</span></span>

<span data-ttu-id="cef51-146">A **Feladatok** csempe konfigurálásához a Pénztáralkalmazás kezdőlapján kövesse az alábbi lépéseket,</span><span class="sxs-lookup"><span data-stu-id="cef51-146">To configure the **Tasks** tile on a POS application home page, follow these steps.</span></span>

1. <span data-ttu-id="cef51-147">Lépjen a **Retail és Commerce \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Képernyő-elrendezések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cef51-147">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> Screen layouts**.</span></span>
1. <span data-ttu-id="cef51-148">Válasszon ki egy képernyő-elrendezést, válasszon egy elrendezési méretet, majd válassza ki egy gombrácsot.</span><span class="sxs-lookup"><span data-stu-id="cef51-148">Select a screen layout, select a layout size, and select a button grid.</span></span>
1. <span data-ttu-id="cef51-149">A **Gombrácsok** gyorslapján a kiválasztott gombrács szerkesztéséhez válassza a **Tervező** elemet.</span><span class="sxs-lookup"><span data-stu-id="cef51-149">On the **Button grids** FastTab, select **Designer** to edit the selected button grid.</span></span>
1. <span data-ttu-id="cef51-150">Adjon hozzá egy **Feladatok** csempét a Kezdőlap megfelelő szakaszához.</span><span class="sxs-lookup"><span data-stu-id="cef51-150">Add a **Tasks** tile to the appropriate section of the home page.</span></span>

<span data-ttu-id="cef51-151">A következő ábra a pénztár kezdőlapján található **Feladatok** csempére mutat be egy példát.</span><span class="sxs-lookup"><span data-stu-id="cef51-151">The following illustration shows an example of a **Tasks** tile on a POS home page.</span></span>

![A Feladatok mozaikja a pénztár kezdőlapján](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a><span data-ttu-id="cef51-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cef51-153">Additional resources</span></span>

[<span data-ttu-id="cef51-154">Feladatkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="cef51-154">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="cef51-155">Feladatlisták létrehozása és feladatok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cef51-155">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="cef51-156">Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz</span><span class="sxs-lookup"><span data-stu-id="cef51-156">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="cef51-157">Feladatkezelés a pénztárban</span><span class="sxs-lookup"><span data-stu-id="cef51-157">Task management in POS</span></span>](task-mgmt-POS.md)
