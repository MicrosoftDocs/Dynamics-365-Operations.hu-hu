---
title: A cím változásainak megtekintése és kezelése
description: Ez a témakör azt mutatja be, hogyan lehet megtekinteni és kezelni a cím változásait a Dynamics 365 Human Resources rendszerben.
author: andreabichsel
manager: AnnBe
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a69d723b45e834b022491c8eaf2a7fb580e54f1d
ms.sourcegitcommit: 288df4fe766536e51ca9b5306c5bb948b7772ac5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2020
ms.locfileid: "3688321"
---
# <a name="view-and-manage-address-changes"></a><span data-ttu-id="0e48f-103">A cím változásainak megtekintése és kezelése</span><span class="sxs-lookup"><span data-stu-id="0e48f-103">View and manage address changes</span></span>

<span data-ttu-id="0e48f-104">Ez a témakör bemutatja, hogyan lehet megtekinteni és kezelni a cím változásait az Alkalmazotti önkiszolgáló rendszer **Személyi részletek szerkesztése** oldalán, illetve a **Dolgozó** részleteit tartalmazó oldalon a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="0e48f-104">This topic explains how you can view and manage address changes in the Employee self-service **Edit personal details** page or the **Worker** details page in Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="0e48f-105">Számos szervezet azt szeretné, hogy az alkalmazottak saját maguk, saját felületen kezelhessék saját személyes adataikat.</span><span class="sxs-lookup"><span data-stu-id="0e48f-105">Many organizations want employees to manage their own personal details through a self-service experience.</span></span> <span data-ttu-id="0e48f-106">Engedélyezheti a felhasználóknak, hogy frissítsék a címüket az **Alkalmazotti önkiszolgáló rendszer** munkaterületén.</span><span class="sxs-lookup"><span data-stu-id="0e48f-106">You can allow users to update their address in the **Employee self service** workspace.</span></span> <span data-ttu-id="0e48f-107">Ezt követően a változásokat a **Személyzetkezelés** munkaterületen követheti nyomon.</span><span class="sxs-lookup"><span data-stu-id="0e48f-107">You can then monitor these changes in the **Personnel management** workspace.</span></span> <span data-ttu-id="0e48f-108">A funkció használatához meg kell adnia, hogy hány napig kívánja megtekinteni a változásokat az **Emberierőforrás-paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="0e48f-108">To use this feature, you must specify the number of days that you want to view changes in the **Human resources parameters** page.</span></span>

## <a name="configure-address-change-parameters"></a><span data-ttu-id="0e48f-109">A cím módosítására vonatkozó paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0e48f-109">Configure address change parameters</span></span>

<span data-ttu-id="0e48f-110">A következő lépésekkel konfigurálhatja, hogy hány napig legyenek láthatók a cím módosításai a **Személyzetkezelés** munkaterületen:</span><span class="sxs-lookup"><span data-stu-id="0e48f-110">To configure the number of days that you want address changes to appear in the **Personnel management** workspace, follow these steps:</span></span>

1. <span data-ttu-id="0e48f-111">A navigációs panelen válassza ki a **Személyzetkezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e48f-111">On the navigation pane, select **Personnel management**.</span></span>

2. <span data-ttu-id="0e48f-112">Válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e48f-112">Select **Links**.</span></span>

3. <span data-ttu-id="0e48f-113">Válassza az **Emberi erőforrások paramétereinek konfigurálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e48f-113">Select **Human resources parameters**.</span></span>

4. <span data-ttu-id="0e48f-114">A **Napok száma** mezőben, a **Címváltozás** területen, adja meg, hogy hány napig legyenek láthatók a címváltozások a **Személyzetkezelés** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="0e48f-114">In the **Number of days** field under **Address change**, enter the number of days that you want address changes to appear in the **Personnel management** workspace.</span></span>

5. <span data-ttu-id="0e48f-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e48f-115">Close the page.</span></span>

## <a name="create-or-change-an-employee-address"></a><span data-ttu-id="0e48f-116">Alkalmazott címének létrehozása vagy módosítása</span><span class="sxs-lookup"><span data-stu-id="0e48f-116">Create or change an employee address</span></span>

<span data-ttu-id="0e48f-117">Az alkalmazottak frissíthetik a saját címüket az **Alkalmazotti önkiszolgáló rendszer** munkaterületén.</span><span class="sxs-lookup"><span data-stu-id="0e48f-117">Employees can update their own address in the **Employee self service** workspace.</span></span> <span data-ttu-id="0e48f-118">Cím létrehozásához vagy módosításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="0e48f-118">Follow these steps to create or change an address:</span></span>

1. <span data-ttu-id="0e48f-119">Válassza ki az **Alkalmazotti önkiszolgáló rendszer** csempét a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="0e48f-119">Select the **Employee self-service** tile on your home page.</span></span>

2. <span data-ttu-id="0e48f-120">Válassza a **Személyes adatok szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="0e48f-120">Select **Edit personal details**.</span></span>

3. <span data-ttu-id="0e48f-121">Cím hozzáadásához kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="0e48f-121">To add an address, select **Add**.</span></span> <span data-ttu-id="0e48f-122">Meglévő cím frissítéséhez jelölje ki a címet a listában, majd válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e48f-122">To update an existing address, select the address from the list and then select **Edit**.</span></span>

4. <span data-ttu-id="0e48f-123">Adja meg a **nevet vagy a leírást**.</span><span class="sxs-lookup"><span data-stu-id="0e48f-123">Enter the **Name or description**.</span></span>

5. <span data-ttu-id="0e48f-124">Válassza ki a **Cél** legördülő mezőt, majd válassza ki a cím típusát.</span><span class="sxs-lookup"><span data-stu-id="0e48f-124">Select the **Purpose** drop-down box and then select the type of address.</span></span>

6. <span data-ttu-id="0e48f-125">Írja be az **Ország/régió** nevét.</span><span class="sxs-lookup"><span data-stu-id="0e48f-125">Enter the **Country/region**.</span></span>

7. <span data-ttu-id="0e48f-126">Írja be az **Irányítószám** értékét.</span><span class="sxs-lookup"><span data-stu-id="0e48f-126">Enter the **ZIP/postal code**.</span></span>

8. <span data-ttu-id="0e48f-127">Adja meg az **Utcát**.</span><span class="sxs-lookup"><span data-stu-id="0e48f-127">Enter the **Street**.</span></span>

9. <span data-ttu-id="0e48f-128">Írja be a **Várost**, az **Államot**és a **Megyét**.</span><span class="sxs-lookup"><span data-stu-id="0e48f-128">Enter the **City**, **State**, and **County**.</span></span> <span data-ttu-id="0e48f-129">Ezeket a mezőket a rendszer általában automatikusan beállítja az **Irányítószám** mező alapján.</span><span class="sxs-lookup"><span data-stu-id="0e48f-129">Typically, these fields are automatically set based on the **ZIP/postal code** field.</span></span>

10. <span data-ttu-id="0e48f-130">Lehetőség van az **Elsődleges** mező kiválasztására, amely elsődleges címet jelez.</span><span class="sxs-lookup"><span data-stu-id="0e48f-130">Optionally, select the **Primary** field to indicate a primary address.</span></span> <span data-ttu-id="0e48f-131">Csak egy címet lehet elsődlegesként megjelölni.</span><span class="sxs-lookup"><span data-stu-id="0e48f-131">Only one address can be marked as the primary.</span></span> <span data-ttu-id="0e48f-132">Ha egy másik cím már meg van jelölve elsődleges címként, meg kell erősítenie, hogy a megadott címet szeretné elsődlegesként használni.</span><span class="sxs-lookup"><span data-stu-id="0e48f-132">If another address is already marked as the primary address, you'll need to confirm that you want to use this address as the primary.</span></span>

11. <span data-ttu-id="0e48f-133">Lehetőség van a **Privát** mező kiválasztására, amely privát címet jelez.</span><span class="sxs-lookup"><span data-stu-id="0e48f-133">Optionally, select the **Private** field to indicate that the address is private.</span></span> <span data-ttu-id="0e48f-134">Csak azok a felhasználók tekinthetik meg ezt a címet, akiknél kifejezetten engedélyezve van a privát címek megtekintése.</span><span class="sxs-lookup"><span data-stu-id="0e48f-134">Only users with explicit permission to view private address information can view this address.</span></span>

12. <span data-ttu-id="0e48f-135">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e48f-135">Select **OK**.</span></span>

## <a name="create-or-change-a-worker-address"></a><span data-ttu-id="0e48f-136">Dolgozó címének létrehozása vagy módosítása</span><span class="sxs-lookup"><span data-stu-id="0e48f-136">Create or change a worker address</span></span>

<span data-ttu-id="0e48f-137">A cím a **Személyzetkezelés** munkaterületen frissíthető.</span><span class="sxs-lookup"><span data-stu-id="0e48f-137">You can update an address in the **Personnel management** workspace.</span></span> <span data-ttu-id="0e48f-138">Cím létrehozásához vagy módosításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="0e48f-138">Follow these steps to create or change an address:</span></span>

1. <span data-ttu-id="0e48f-139">A **Személyzetkezelés** munkaterületen válassza a **Hivatkozások**, majd a **Dolgozók** elemet.</span><span class="sxs-lookup"><span data-stu-id="0e48f-139">In the **Personnel management** workspace, select **Links**, and then select **Workers**.</span></span>

3. <span data-ttu-id="0e48f-140">Válassza ki a dolgozót, majd kattintson az **Címek** gombra.</span><span class="sxs-lookup"><span data-stu-id="0e48f-140">Select the worker, and then select **Addresses**.</span></span>

3. <span data-ttu-id="0e48f-141">Cím hozzáadásához kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="0e48f-141">To add an address, select **Add**.</span></span> <span data-ttu-id="0e48f-142">Meglévő cím frissítéséhez jelölje ki a címet a listában, majd válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e48f-142">To update an existing address, select the address from the list and then select **Edit**.</span></span>

4. <span data-ttu-id="0e48f-143">Adja meg a **nevet vagy a leírást**.</span><span class="sxs-lookup"><span data-stu-id="0e48f-143">Enter the **Name or description**.</span></span>

5. <span data-ttu-id="0e48f-144">Válassza ki a **Cél** legördülő mezőt, majd válassza ki a cím típusát.</span><span class="sxs-lookup"><span data-stu-id="0e48f-144">Select the **Purpose** drop-down box and then select the type of address.</span></span>

6. <span data-ttu-id="0e48f-145">Írja be az **Ország/régió** nevét.</span><span class="sxs-lookup"><span data-stu-id="0e48f-145">Enter the **Country/region**.</span></span>

7. <span data-ttu-id="0e48f-146">Írja be az **Irányítószám** értékét.</span><span class="sxs-lookup"><span data-stu-id="0e48f-146">Enter the **ZIP/postal code**.</span></span>

8. <span data-ttu-id="0e48f-147">Adja meg az **Utcát**.</span><span class="sxs-lookup"><span data-stu-id="0e48f-147">Enter the **Street**.</span></span>

9. <span data-ttu-id="0e48f-148">Írja be a **Várost**, az **Államot**és a **Megyét**.</span><span class="sxs-lookup"><span data-stu-id="0e48f-148">Enter the **City**, **State**, and **County**.</span></span> <span data-ttu-id="0e48f-149">Ezeket a mezőket a rendszer általában automatikusan beállítja az **Irányítószám** mező alapján.</span><span class="sxs-lookup"><span data-stu-id="0e48f-149">Typically, these fields are automatically set based on the **ZIP/postal code** field.</span></span>

10. <span data-ttu-id="0e48f-150">Lehetőség van az **Elsődleges** mező kiválasztására, amely elsődleges címet jelez.</span><span class="sxs-lookup"><span data-stu-id="0e48f-150">Optionally, select the **Primary** field to indicate a primary address.</span></span> <span data-ttu-id="0e48f-151">Csak egy címet lehet elsődlegesként megjelölni.</span><span class="sxs-lookup"><span data-stu-id="0e48f-151">Only one address can be marked as the primary.</span></span> <span data-ttu-id="0e48f-152">Ha egy másik cím már meg van jelölve elsődleges címként, meg kell erősítenie, hogy a megadott címet szeretné elsődlegesként használni.</span><span class="sxs-lookup"><span data-stu-id="0e48f-152">If another address is already marked as the primary address, you'll need to confirm that you want to use this address as the primary.</span></span>

11. <span data-ttu-id="0e48f-153">Lehetőség van a **Privát** mező kiválasztására, amely privát címet jelez.</span><span class="sxs-lookup"><span data-stu-id="0e48f-153">Optionally, select the **Private** field to indicate that the address is private.</span></span> <span data-ttu-id="0e48f-154">Csak azok a felhasználók tekinthetik meg ezt a címet, akiknél kifejezetten engedélyezve van a privát címek megtekintése.</span><span class="sxs-lookup"><span data-stu-id="0e48f-154">Only users with explicit permission to view private address information can view this address.</span></span>

12. <span data-ttu-id="0e48f-155">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e48f-155">Select **OK**.</span></span>
 
## <a name="create-a-future-change-for-an-address"></a><span data-ttu-id="0e48f-156">Cím jövőbeli módosításának megadása</span><span class="sxs-lookup"><span data-stu-id="0e48f-156">Create a future change for an address</span></span>

<span data-ttu-id="0e48f-157">Bizonyos esetekben előfordulhat, hogy valamikor a jövőben szeretné módosítani a címet.</span><span class="sxs-lookup"><span data-stu-id="0e48f-157">In some cases, you might want to update an address to change in the future.</span></span> <span data-ttu-id="0e48f-158">Ez például akkor lehet hasznos, ha egy alkalmazott a következő hónap 15-én költözik.</span><span class="sxs-lookup"><span data-stu-id="0e48f-158">For example, this would be useful if an employee is moving on the 15th of the following month.</span></span>

1. <span data-ttu-id="0e48f-159">Nyissa meg a **Címek kezelése** oldalt az egyik címrács **További beállítások > Speciális** elemére kattintva.</span><span class="sxs-lookup"><span data-stu-id="0e48f-159">Open the **Manage addresses** page by selecting **More options > Advanced** from any address grid.</span></span>

2. <span data-ttu-id="0e48f-160">Válassza ki az **Új** lehetőséget egy új cím létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="0e48f-160">Select **New** to create a new address.</span></span>

3. <span data-ttu-id="0e48f-161">Adja meg a cím részleteit.</span><span class="sxs-lookup"><span data-stu-id="0e48f-161">Enter the details of the address.</span></span>

4. <span data-ttu-id="0e48f-162">Lépjen az **Általános** gyorslapra.</span><span class="sxs-lookup"><span data-stu-id="0e48f-162">Select the **General** FastTab.</span></span>

5. <span data-ttu-id="0e48f-163">Az **Érvényesség dátuma** mezőben válassza ki azt a dátumot, amikor az új cím érvénybe lép.</span><span class="sxs-lookup"><span data-stu-id="0e48f-163">In the **Effective date** field, select the date the new address will be effective.</span></span>

6. <span data-ttu-id="0e48f-164">A **Lejárat dátuma** mezőben kiválaszthatja, hogy a cím mikortól nem lesz érvényes.</span><span class="sxs-lookup"><span data-stu-id="0e48f-164">In the **Expiration date** field, optionally select when the address will no longer be effective.</span></span>

7. <span data-ttu-id="0e48f-165">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="0e48f-165">Close the pages.</span></span>

## <a name="view-and-monitor-address-changes"></a><span data-ttu-id="0e48f-166">A cím változásainak megtekintése és nyomon követése</span><span class="sxs-lookup"><span data-stu-id="0e48f-166">View and monitor address changes</span></span>

<span data-ttu-id="0e48f-167">A HR munkatársai a **Személyzetkezelés** munkaterületen megtekinthetik és nyomon követik a címeket.</span><span class="sxs-lookup"><span data-stu-id="0e48f-167">HR personnel can view and monitor address changes from the **Personnel management** workspace.</span></span> <span data-ttu-id="0e48f-168">A cím változásainak megtekintéséhez nyissa meg a **Személyzetkezelés** csempét a **Kezdőlapon**.</span><span class="sxs-lookup"><span data-stu-id="0e48f-168">To view the address changes, open the **Personnel management** tile from the **Home** page.</span></span> <span data-ttu-id="0e48f-169">A cím változása a jobb felső sarokban lévő csempén látható.</span><span class="sxs-lookup"><span data-stu-id="0e48f-169">The address changes display on a tile in the upper-right corner.</span></span> <span data-ttu-id="0e48f-170">A **Címváltozások** rész fölött látható, hogy hányszor módosult a cím az **Emberi erőforrások paraméterei** oldalon megadott számú nap alatt.</span><span class="sxs-lookup"><span data-stu-id="0e48f-170">The number above **Address changes** shows how many address changes occurred in the number of days specified in the **Human resources parameters** page.</span></span> 

<span data-ttu-id="0e48f-171">Amikor kiválasztja a **Címváltozások** csempét, egy új lapon megjelennek az esetleges címváltozások részletei.</span><span class="sxs-lookup"><span data-stu-id="0e48f-171">When you select the **Address changes** tile, a new page displays the details of any address changes.</span></span> <span data-ttu-id="0e48f-172">Lehetősége van arra, hogy a jobb felső sarokban lévő **Jövőbeli címváltozásokkal** kiválasztásával megjelenítse a jövőbeli dátumú címváltozásokat.</span><span class="sxs-lookup"><span data-stu-id="0e48f-172">You can optionally select **Include future address changes** in the upper-right corner to display address changes with a future date.</span></span>

> [!NOTE]
> <span data-ttu-id="0e48f-173">Ha figyelmeztetést vagy e-mailt szeretne kapni ezekről a címváltozásokról, akkor létrehozhat egy új riasztási szabályt a Művelet panel **Beállítások** lapján.</span><span class="sxs-lookup"><span data-stu-id="0e48f-173">If you want to receive an alert or email about these address changes, you can create a new alert rule on the **Options** tab in the Action Pane.</span></span> <span data-ttu-id="0e48f-174">További információ a riasztási szabályokról: [Figyelmeztetési szabályok létrehozása](/fin-ops-core/fin-ops/get-started/create-alert-rules.md).</span><span class="sxs-lookup"><span data-stu-id="0e48f-174">For more information about alert rules, see [Create alert rules](/fin-ops-core/fin-ops/get-started/create-alert-rules.md).</span></span><br><br>

> <span data-ttu-id="0e48f-175">Ha munkafolyamatot kíván konfigurálni a címváltozásokhoz, akkor a riasztási szabály **Külső küldés** beállításának kiválasztása után használhatja a Power Automate szolgáltatást az üzleti esemény aktiválásra és a munkafolyamat konfigurálására.</span><span class="sxs-lookup"><span data-stu-id="0e48f-175">If you want to configure a workflow for the address changes, you can select the **Send externally** option on your alert rule, and then use Power Automate to trigger the business event and configure a workflow.</span></span> <span data-ttu-id="0e48f-176">További tájékoztatás: [Figyelmeztetések üzleti eseményekként](/fin-ops-core/dev-itpro/business-events/alerts-business-events.md).</span><span class="sxs-lookup"><span data-stu-id="0e48f-176">For more information, see [Alerts as business events](/fin-ops-core/dev-itpro/business-events/alerts-business-events.md).</span></span>
