---
title: Alkalmazotti önkiszolgálás konfigurálása
description: A Microsoft Dynamics 365 Human Resources alkalmazásban lehetősége van csempéket konfigurálni az Alkalmazotti önkiszolgáló rendszer felső szintű navigációjához.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d1534e37e83e22dd9860de54165c062935db3798
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418900"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="147b9-103">Alkalmazotti önkiszolgálás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="147b9-103">Configure employee self service</span></span>

<span data-ttu-id="147b9-104">A Microsoft Dynamics 365 Human Resources alkalmazásban lehetősége van csempéket konfigurálni az Alkalmazotti önkiszolgáló rendszer felső szintű navigációjához.</span><span class="sxs-lookup"><span data-stu-id="147b9-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="147b9-105">A juttatási terv csempék a felhasználókat olyan juttatási konstrukciókhoz irányítják, amelyekre jogosultak.</span><span class="sxs-lookup"><span data-stu-id="147b9-105">Benefit plan tiles direct users to benefit plans that they're eligible for.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="147b9-106">Juttatásikonstrukció-csempe beállítása</span><span class="sxs-lookup"><span data-stu-id="147b9-106">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="147b9-107">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="147b9-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="147b9-108">Válassza ki a **Juttatásikonstrukció-csempe beállítása** lapot, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="147b9-108">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="147b9-109">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="147b9-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="147b9-110">Mező</span><span class="sxs-lookup"><span data-stu-id="147b9-110">Field</span></span> | <span data-ttu-id="147b9-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="147b9-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="147b9-112">**Csempe azonosítója**</span><span class="sxs-lookup"><span data-stu-id="147b9-112">**Tile ID**</span></span> | <span data-ttu-id="147b9-113">A mozaik egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="147b9-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="147b9-114">**CSempecímke felirata**</span><span class="sxs-lookup"><span data-stu-id="147b9-114">**Tile label text**</span></span> | <span data-ttu-id="147b9-115">Az önkiszolgáló rendszer csempéjén megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="147b9-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="147b9-116">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="147b9-116">**Description**</span></span> | <span data-ttu-id="147b9-117">A csempe leírása.</span><span class="sxs-lookup"><span data-stu-id="147b9-117">A description of the tile.</span></span> |
   | <span data-ttu-id="147b9-118">**Internetcím**</span><span class="sxs-lookup"><span data-stu-id="147b9-118">**Internet address**</span></span> | <span data-ttu-id="147b9-119">Adja meg az alkalmazotti önkiszolgáló rendszer oldalának URL-jét.</span><span class="sxs-lookup"><span data-stu-id="147b9-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="147b9-120">**Csempeméret**</span><span class="sxs-lookup"><span data-stu-id="147b9-120">**Tile size**</span></span> | <span data-ttu-id="147b9-121">A csempe mérete: kis, közepes vagy nagy.</span><span class="sxs-lookup"><span data-stu-id="147b9-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="147b9-122">**Cél**</span><span class="sxs-lookup"><span data-stu-id="147b9-122">**Target**</span></span> | <span data-ttu-id="147b9-123">Megadja, hogy a lapnak új ablakban vagy az aktuális ablakban kell-e megnyílnia.</span><span class="sxs-lookup"><span data-stu-id="147b9-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="147b9-124">**Csempeháttérkép**</span><span class="sxs-lookup"><span data-stu-id="147b9-124">**Tile background image**</span></span> | <span data-ttu-id="147b9-125">A csempéhez használandó kép URL-címe (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="147b9-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="147b9-126">**Kezdete**</span><span class="sxs-lookup"><span data-stu-id="147b9-126">**Start**</span></span> | <span data-ttu-id="147b9-127">A csempe elérhetőségének kezdő dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="147b9-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="147b9-128">**End**</span><span class="sxs-lookup"><span data-stu-id="147b9-128">**End**</span></span> | <span data-ttu-id="147b9-129">A csempe elérhetőségének befejező dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="147b9-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="147b9-130">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="147b9-130">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="147b9-131">Rugalmas hitelkonstrukció csempe beállítása</span><span class="sxs-lookup"><span data-stu-id="147b9-131">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="147b9-132">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="147b9-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="147b9-133">Válassza ki a **Rugalmas hitelkonstrukció csempe beállítása** lapot, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="147b9-133">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="147b9-134">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="147b9-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="147b9-135">Mező</span><span class="sxs-lookup"><span data-stu-id="147b9-135">Field</span></span> | <span data-ttu-id="147b9-136">Leírás</span><span class="sxs-lookup"><span data-stu-id="147b9-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="147b9-137">**Csempe azonosítója**</span><span class="sxs-lookup"><span data-stu-id="147b9-137">**Tile ID**</span></span> | <span data-ttu-id="147b9-138">A mozaik egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="147b9-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="147b9-139">**CSempecímke felirata**</span><span class="sxs-lookup"><span data-stu-id="147b9-139">**Tile label text**</span></span> | <span data-ttu-id="147b9-140">Az önkiszolgáló rendszer csempéjén megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="147b9-140">The text that will appear for the tile on Self service.</span></span> |
   | <span data-ttu-id="147b9-141">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="147b9-141">**Description**</span></span> | <span data-ttu-id="147b9-142">A csempe leírása.</span><span class="sxs-lookup"><span data-stu-id="147b9-142">A description of the tile.</span></span> |
   | <span data-ttu-id="147b9-143">**Internetcím**</span><span class="sxs-lookup"><span data-stu-id="147b9-143">**Internet address**</span></span> | <span data-ttu-id="147b9-144">Adja meg az alkalmazotti önkiszolgáló rendszer oldalának URL-jét.</span><span class="sxs-lookup"><span data-stu-id="147b9-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="147b9-145">**Csempeméret**</span><span class="sxs-lookup"><span data-stu-id="147b9-145">**Tile size**</span></span> | <span data-ttu-id="147b9-146">A csempe mérete: kis, közepes vagy nagy.</span><span class="sxs-lookup"><span data-stu-id="147b9-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="147b9-147">**Cél**</span><span class="sxs-lookup"><span data-stu-id="147b9-147">**Target**</span></span> | <span data-ttu-id="147b9-148">Megadja, hogy a lapnak új ablakban vagy az aktuális ablakban kell-e megnyílnia.</span><span class="sxs-lookup"><span data-stu-id="147b9-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="147b9-149">**Csempeháttérkép**</span><span class="sxs-lookup"><span data-stu-id="147b9-149">**Tile background image**</span></span> | <span data-ttu-id="147b9-150">A csempéhez használandó kép URL-címe (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="147b9-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="147b9-151">**Kezdete**</span><span class="sxs-lookup"><span data-stu-id="147b9-151">**Start**</span></span> | <span data-ttu-id="147b9-152">A csempe elérhetőségének kezdő dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="147b9-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="147b9-153">**End**</span><span class="sxs-lookup"><span data-stu-id="147b9-153">**End**</span></span> | <span data-ttu-id="147b9-154">A csempe elérhetőségének befejező dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="147b9-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="147b9-155">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="147b9-155">Select **Save**.</span></span>
