---
title: Alkalmazotti önkiszolgáló rendszer konfigurálása
description: ''
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
ms.openlocfilehash: e44a35071b8d0987e6c949fb11312204317b44a1
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009289"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="39d19-102">Alkalmazotti önkiszolgáló rendszer konfigurálása</span><span class="sxs-lookup"><span data-stu-id="39d19-102">Configure employee self service</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="39d19-103">A Microsoft Dynamics 365 Human Resources alkalmazásban lehetősége van csempéket konfigurálni az Alkalmazotti önkiszolgáló rendszer felső szintű navigációjához.</span><span class="sxs-lookup"><span data-stu-id="39d19-103">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="39d19-104">A juttatási terv csempék a felhasználókat olyan juttatási konstrukciókhoz irányítják, amelyekre jogosultak regisztrálni.</span><span class="sxs-lookup"><span data-stu-id="39d19-104">Benefit plan tiles direct users to benefit plans that they are eligible to enroll in.</span></span>

## <a name="set-up-a-role-center-tile"></a><span data-ttu-id="39d19-105">Szerepkörfőoldal-csempe beállítása</span><span class="sxs-lookup"><span data-stu-id="39d19-105">Set up a role center tile</span></span>

1. <span data-ttu-id="39d19-106">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="39d19-106">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="39d19-107">Válassza ki a **Szerepkörfőoldal-mozaik beállítása** lapot, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39d19-107">Select the **Role center tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="39d19-108">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="39d19-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="39d19-109">Mező</span><span class="sxs-lookup"><span data-stu-id="39d19-109">Field</span></span> | <span data-ttu-id="39d19-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="39d19-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="39d19-111">Csempe azonosítója</span><span class="sxs-lookup"><span data-stu-id="39d19-111">Tile ID</span></span> | <span data-ttu-id="39d19-112">A mozaik egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="39d19-112">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="39d19-113">CSempecímke felirata</span><span class="sxs-lookup"><span data-stu-id="39d19-113">Tile label text</span></span> | <span data-ttu-id="39d19-114">Az önkiszolgáló rendszer csempéjén megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="39d19-114">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="39d19-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="39d19-115">Description</span></span> | <span data-ttu-id="39d19-116">A csempe leírása.</span><span class="sxs-lookup"><span data-stu-id="39d19-116">A description of the tile.</span></span> |
   | <span data-ttu-id="39d19-117">Internetcím</span><span class="sxs-lookup"><span data-stu-id="39d19-117">Internet address</span></span> | <span data-ttu-id="39d19-118">Adja meg az alkalmazotti önkiszolgáló rendszer oldalának URL-jét.</span><span class="sxs-lookup"><span data-stu-id="39d19-118">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="39d19-119">Csempeméret</span><span class="sxs-lookup"><span data-stu-id="39d19-119">Tile size</span></span> | <span data-ttu-id="39d19-120">A csempe mérete: kis, közepes vagy nagy.</span><span class="sxs-lookup"><span data-stu-id="39d19-120">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="39d19-121">Cél</span><span class="sxs-lookup"><span data-stu-id="39d19-121">Target</span></span> | <span data-ttu-id="39d19-122">Megadja, hogy a lapnak új ablakban vagy az aktuális ablakban kell-e megnyílnia.</span><span class="sxs-lookup"><span data-stu-id="39d19-122">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="39d19-123">Csempeháttérkép</span><span class="sxs-lookup"><span data-stu-id="39d19-123">Tile background image</span></span> | <span data-ttu-id="39d19-124">A csempéhez használandó kép URL-címe (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="39d19-124">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="39d19-125">Kezdete</span><span class="sxs-lookup"><span data-stu-id="39d19-125">Start</span></span> | <span data-ttu-id="39d19-126">A csempe elérhetőségének kezdő dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="39d19-126">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="39d19-127">End</span><span class="sxs-lookup"><span data-stu-id="39d19-127">End</span></span> | <span data-ttu-id="39d19-128">A csempe elérhetőségének befejező dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="39d19-128">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="39d19-129">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39d19-129">Select **Save**.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="39d19-130">Juttatásikonstrukció-csempe beállítása</span><span class="sxs-lookup"><span data-stu-id="39d19-130">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="39d19-131">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="39d19-131">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="39d19-132">Válassza ki a **Juttatásikonstrukció-csempe beállítása** lapot, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39d19-132">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="39d19-133">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="39d19-133">Specify values for the following fields:</span></span>

   | <span data-ttu-id="39d19-134">Mező</span><span class="sxs-lookup"><span data-stu-id="39d19-134">Field</span></span> | <span data-ttu-id="39d19-135">Leírás</span><span class="sxs-lookup"><span data-stu-id="39d19-135">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="39d19-136">Csempe azonosítója</span><span class="sxs-lookup"><span data-stu-id="39d19-136">Tile ID</span></span> | <span data-ttu-id="39d19-137">A mozaik egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="39d19-137">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="39d19-138">CSempecímke felirata</span><span class="sxs-lookup"><span data-stu-id="39d19-138">Tile label text</span></span> | <span data-ttu-id="39d19-139">Az önkiszolgáló rendszer csempéjén megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="39d19-139">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="39d19-140">Leírás</span><span class="sxs-lookup"><span data-stu-id="39d19-140">Description</span></span> | <span data-ttu-id="39d19-141">A csempe leírása.</span><span class="sxs-lookup"><span data-stu-id="39d19-141">A description of the tile.</span></span> |
   | <span data-ttu-id="39d19-142">Internetcím</span><span class="sxs-lookup"><span data-stu-id="39d19-142">Internet address</span></span> | <span data-ttu-id="39d19-143">Adja meg az alkalmazotti önkiszolgáló rendszer oldalának URL-jét.</span><span class="sxs-lookup"><span data-stu-id="39d19-143">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="39d19-144">Csempeméret</span><span class="sxs-lookup"><span data-stu-id="39d19-144">Tile size</span></span> | <span data-ttu-id="39d19-145">A csempe mérete: kis, közepes vagy nagy.</span><span class="sxs-lookup"><span data-stu-id="39d19-145">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="39d19-146">Cél</span><span class="sxs-lookup"><span data-stu-id="39d19-146">Target</span></span> | <span data-ttu-id="39d19-147">Megadja, hogy a lapnak új ablakban vagy az aktuális ablakban kell-e megnyílnia.</span><span class="sxs-lookup"><span data-stu-id="39d19-147">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="39d19-148">Csempeháttérkép</span><span class="sxs-lookup"><span data-stu-id="39d19-148">Tile background image</span></span> | <span data-ttu-id="39d19-149">A csempéhez használandó kép URL-címe (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="39d19-149">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="39d19-150">Kezdete</span><span class="sxs-lookup"><span data-stu-id="39d19-150">Start</span></span> | <span data-ttu-id="39d19-151">A csempe elérhetőségének kezdő dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="39d19-151">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="39d19-152">End</span><span class="sxs-lookup"><span data-stu-id="39d19-152">End</span></span> | <span data-ttu-id="39d19-153">A csempe elérhetőségének befejező dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="39d19-153">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="39d19-154">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39d19-154">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="39d19-155">Rugalmas hitelkonstrukció csempe beállítása</span><span class="sxs-lookup"><span data-stu-id="39d19-155">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="39d19-156">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="39d19-156">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="39d19-157">Válassza ki a **Rugalmas hitelkonstrukció csempe beállítása** lapot, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39d19-157">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="39d19-158">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="39d19-158">Specify values for the following fields:</span></span>

   | <span data-ttu-id="39d19-159">Mező</span><span class="sxs-lookup"><span data-stu-id="39d19-159">Field</span></span> | <span data-ttu-id="39d19-160">Leírás</span><span class="sxs-lookup"><span data-stu-id="39d19-160">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="39d19-161">Csempe azonosítója</span><span class="sxs-lookup"><span data-stu-id="39d19-161">Tile ID</span></span> | <span data-ttu-id="39d19-162">A mozaik egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="39d19-162">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="39d19-163">CSempecímke felirata</span><span class="sxs-lookup"><span data-stu-id="39d19-163">Tile label text</span></span> | <span data-ttu-id="39d19-164">Az önkiszolgáló rendszer csempéjén megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="39d19-164">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="39d19-165">Leírás</span><span class="sxs-lookup"><span data-stu-id="39d19-165">Description</span></span> | <span data-ttu-id="39d19-166">A csempe leírása.</span><span class="sxs-lookup"><span data-stu-id="39d19-166">A description of the tile.</span></span> |
   | <span data-ttu-id="39d19-167">Internetcím</span><span class="sxs-lookup"><span data-stu-id="39d19-167">Internet address</span></span> | <span data-ttu-id="39d19-168">Adja meg az alkalmazotti önkiszolgáló rendszer oldalának URL-jét.</span><span class="sxs-lookup"><span data-stu-id="39d19-168">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="39d19-169">Csempeméret</span><span class="sxs-lookup"><span data-stu-id="39d19-169">Tile size</span></span> | <span data-ttu-id="39d19-170">A csempe mérete: kis, közepes vagy nagy.</span><span class="sxs-lookup"><span data-stu-id="39d19-170">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="39d19-171">Cél</span><span class="sxs-lookup"><span data-stu-id="39d19-171">Target</span></span> | <span data-ttu-id="39d19-172">Megadja, hogy a lapnak új ablakban vagy az aktuális ablakban kell-e megnyílnia.</span><span class="sxs-lookup"><span data-stu-id="39d19-172">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="39d19-173">Csempeháttérkép</span><span class="sxs-lookup"><span data-stu-id="39d19-173">Tile background image</span></span> | <span data-ttu-id="39d19-174">A csempéhez használandó kép URL-címe (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="39d19-174">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="39d19-175">Kezdete</span><span class="sxs-lookup"><span data-stu-id="39d19-175">Start</span></span> | <span data-ttu-id="39d19-176">A csempe elérhetőségének kezdő dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="39d19-176">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="39d19-177">End</span><span class="sxs-lookup"><span data-stu-id="39d19-177">End</span></span> | <span data-ttu-id="39d19-178">A csempe elérhetőségének befejező dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="39d19-178">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="39d19-179">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39d19-179">Select **Save**.</span></span>
