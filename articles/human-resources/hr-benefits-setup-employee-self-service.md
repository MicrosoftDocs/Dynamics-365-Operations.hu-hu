---
title: Alkalmazotti önkiszolgálás konfigurálása
description: A Microsoft Dynamics 365 Human Resources alkalmazásban lehetősége van csempéket konfigurálni az Alkalmazotti önkiszolgáló rendszer felső szintű navigációjához.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 17918fc7b894929c92c54b59b7440ab8aef980bd
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092660"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="18d98-103">Alkalmazotti önkiszolgálás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="18d98-103">Configure employee self service</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="18d98-104">A Microsoft Dynamics 365 Human Resources alkalmazásban lehetősége van csempéket konfigurálni az Alkalmazotti önkiszolgáló rendszer felső szintű navigációjához.</span><span class="sxs-lookup"><span data-stu-id="18d98-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="18d98-105">A juttatási terv csempék a felhasználókat olyan juttatási konstrukciókhoz irányítják, amelyekre jogosultak regisztrálni.</span><span class="sxs-lookup"><span data-stu-id="18d98-105">Benefit plan tiles direct users to benefit plans that they are eligible to enroll in.</span></span>

## <a name="set-up-a-role-center-tile"></a><span data-ttu-id="18d98-106">Szerepkörfőoldal-csempe beállítása</span><span class="sxs-lookup"><span data-stu-id="18d98-106">Set up a role center tile</span></span>

1. <span data-ttu-id="18d98-107">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="18d98-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="18d98-108">Válassza ki a **Szerepkörfőoldal-mozaik beállítása** lapot, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18d98-108">Select the **Role center tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="18d98-109">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="18d98-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="18d98-110">Mező</span><span class="sxs-lookup"><span data-stu-id="18d98-110">Field</span></span> | <span data-ttu-id="18d98-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="18d98-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="18d98-112">Csempe azonosítója</span><span class="sxs-lookup"><span data-stu-id="18d98-112">Tile ID</span></span> | <span data-ttu-id="18d98-113">A mozaik egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="18d98-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="18d98-114">CSempecímke felirata</span><span class="sxs-lookup"><span data-stu-id="18d98-114">Tile label text</span></span> | <span data-ttu-id="18d98-115">Az önkiszolgáló rendszer csempéjén megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="18d98-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="18d98-116">Leírás</span><span class="sxs-lookup"><span data-stu-id="18d98-116">Description</span></span> | <span data-ttu-id="18d98-117">A csempe leírása.</span><span class="sxs-lookup"><span data-stu-id="18d98-117">A description of the tile.</span></span> |
   | <span data-ttu-id="18d98-118">Internetcím</span><span class="sxs-lookup"><span data-stu-id="18d98-118">Internet address</span></span> | <span data-ttu-id="18d98-119">Adja meg az alkalmazotti önkiszolgáló rendszer oldalának URL-jét.</span><span class="sxs-lookup"><span data-stu-id="18d98-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="18d98-120">Csempeméret</span><span class="sxs-lookup"><span data-stu-id="18d98-120">Tile size</span></span> | <span data-ttu-id="18d98-121">A csempe mérete: kis, közepes vagy nagy.</span><span class="sxs-lookup"><span data-stu-id="18d98-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="18d98-122">Cél</span><span class="sxs-lookup"><span data-stu-id="18d98-122">Target</span></span> | <span data-ttu-id="18d98-123">Megadja, hogy a lapnak új ablakban vagy az aktuális ablakban kell-e megnyílnia.</span><span class="sxs-lookup"><span data-stu-id="18d98-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="18d98-124">Csempeháttérkép</span><span class="sxs-lookup"><span data-stu-id="18d98-124">Tile background image</span></span> | <span data-ttu-id="18d98-125">A csempéhez használandó kép URL-címe (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="18d98-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="18d98-126">Kezdete</span><span class="sxs-lookup"><span data-stu-id="18d98-126">Start</span></span> | <span data-ttu-id="18d98-127">A csempe elérhetőségének kezdő dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="18d98-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="18d98-128">End</span><span class="sxs-lookup"><span data-stu-id="18d98-128">End</span></span> | <span data-ttu-id="18d98-129">A csempe elérhetőségének befejező dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="18d98-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="18d98-130">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18d98-130">Select **Save**.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="18d98-131">Juttatásikonstrukció-csempe beállítása</span><span class="sxs-lookup"><span data-stu-id="18d98-131">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="18d98-132">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="18d98-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="18d98-133">Válassza ki a **Juttatásikonstrukció-csempe beállítása** lapot, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18d98-133">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="18d98-134">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="18d98-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="18d98-135">Mező</span><span class="sxs-lookup"><span data-stu-id="18d98-135">Field</span></span> | <span data-ttu-id="18d98-136">Leírás</span><span class="sxs-lookup"><span data-stu-id="18d98-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="18d98-137">Csempe azonosítója</span><span class="sxs-lookup"><span data-stu-id="18d98-137">Tile ID</span></span> | <span data-ttu-id="18d98-138">A mozaik egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="18d98-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="18d98-139">CSempecímke felirata</span><span class="sxs-lookup"><span data-stu-id="18d98-139">Tile label text</span></span> | <span data-ttu-id="18d98-140">Az önkiszolgáló rendszer csempéjén megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="18d98-140">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="18d98-141">Leírás</span><span class="sxs-lookup"><span data-stu-id="18d98-141">Description</span></span> | <span data-ttu-id="18d98-142">A csempe leírása.</span><span class="sxs-lookup"><span data-stu-id="18d98-142">A description of the tile.</span></span> |
   | <span data-ttu-id="18d98-143">Internetcím</span><span class="sxs-lookup"><span data-stu-id="18d98-143">Internet address</span></span> | <span data-ttu-id="18d98-144">Adja meg az alkalmazotti önkiszolgáló rendszer oldalának URL-jét.</span><span class="sxs-lookup"><span data-stu-id="18d98-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="18d98-145">Csempeméret</span><span class="sxs-lookup"><span data-stu-id="18d98-145">Tile size</span></span> | <span data-ttu-id="18d98-146">A csempe mérete: kis, közepes vagy nagy.</span><span class="sxs-lookup"><span data-stu-id="18d98-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="18d98-147">Cél</span><span class="sxs-lookup"><span data-stu-id="18d98-147">Target</span></span> | <span data-ttu-id="18d98-148">Megadja, hogy a lapnak új ablakban vagy az aktuális ablakban kell-e megnyílnia.</span><span class="sxs-lookup"><span data-stu-id="18d98-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="18d98-149">Csempeháttérkép</span><span class="sxs-lookup"><span data-stu-id="18d98-149">Tile background image</span></span> | <span data-ttu-id="18d98-150">A csempéhez használandó kép URL-címe (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="18d98-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="18d98-151">Kezdete</span><span class="sxs-lookup"><span data-stu-id="18d98-151">Start</span></span> | <span data-ttu-id="18d98-152">A csempe elérhetőségének kezdő dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="18d98-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="18d98-153">End</span><span class="sxs-lookup"><span data-stu-id="18d98-153">End</span></span> | <span data-ttu-id="18d98-154">A csempe elérhetőségének befejező dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="18d98-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="18d98-155">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18d98-155">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="18d98-156">Rugalmas hitelkonstrukció csempe beállítása</span><span class="sxs-lookup"><span data-stu-id="18d98-156">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="18d98-157">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="18d98-157">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="18d98-158">Válassza ki a **Rugalmas hitelkonstrukció csempe beállítása** lapot, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18d98-158">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="18d98-159">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="18d98-159">Specify values for the following fields:</span></span>

   | <span data-ttu-id="18d98-160">Mező</span><span class="sxs-lookup"><span data-stu-id="18d98-160">Field</span></span> | <span data-ttu-id="18d98-161">Leírás</span><span class="sxs-lookup"><span data-stu-id="18d98-161">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="18d98-162">Csempe azonosítója</span><span class="sxs-lookup"><span data-stu-id="18d98-162">Tile ID</span></span> | <span data-ttu-id="18d98-163">A mozaik egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="18d98-163">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="18d98-164">CSempecímke felirata</span><span class="sxs-lookup"><span data-stu-id="18d98-164">Tile label text</span></span> | <span data-ttu-id="18d98-165">Az önkiszolgáló rendszer csempéjén megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="18d98-165">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="18d98-166">Leírás</span><span class="sxs-lookup"><span data-stu-id="18d98-166">Description</span></span> | <span data-ttu-id="18d98-167">A csempe leírása.</span><span class="sxs-lookup"><span data-stu-id="18d98-167">A description of the tile.</span></span> |
   | <span data-ttu-id="18d98-168">Internetcím</span><span class="sxs-lookup"><span data-stu-id="18d98-168">Internet address</span></span> | <span data-ttu-id="18d98-169">Adja meg az alkalmazotti önkiszolgáló rendszer oldalának URL-jét.</span><span class="sxs-lookup"><span data-stu-id="18d98-169">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="18d98-170">Csempeméret</span><span class="sxs-lookup"><span data-stu-id="18d98-170">Tile size</span></span> | <span data-ttu-id="18d98-171">A csempe mérete: kis, közepes vagy nagy.</span><span class="sxs-lookup"><span data-stu-id="18d98-171">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="18d98-172">Cél</span><span class="sxs-lookup"><span data-stu-id="18d98-172">Target</span></span> | <span data-ttu-id="18d98-173">Megadja, hogy a lapnak új ablakban vagy az aktuális ablakban kell-e megnyílnia.</span><span class="sxs-lookup"><span data-stu-id="18d98-173">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="18d98-174">Csempeháttérkép</span><span class="sxs-lookup"><span data-stu-id="18d98-174">Tile background image</span></span> | <span data-ttu-id="18d98-175">A csempéhez használandó kép URL-címe (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="18d98-175">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="18d98-176">Kezdete</span><span class="sxs-lookup"><span data-stu-id="18d98-176">Start</span></span> | <span data-ttu-id="18d98-177">A csempe elérhetőségének kezdő dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="18d98-177">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="18d98-178">End</span><span class="sxs-lookup"><span data-stu-id="18d98-178">End</span></span> | <span data-ttu-id="18d98-179">A csempe elérhetőségének befejező dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="18d98-179">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="18d98-180">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18d98-180">Select **Save**.</span></span>
