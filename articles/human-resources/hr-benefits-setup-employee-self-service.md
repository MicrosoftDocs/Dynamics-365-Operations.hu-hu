---
title: Alkalmazotti önkiszolgálás konfigurálása
description: A Microsoft Dynamics 365 Human Resources alkalmazásban lehetősége van csempéket konfigurálni az Alkalmazotti önkiszolgáló rendszer felső szintű navigációjához.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 3e763a09e0a0f13eb7222a6ffbcb31b6230b83f4
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797935"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="d36f4-103">Alkalmazotti önkiszolgálás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d36f4-103">Configure employee self service</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d36f4-104">A Microsoft Dynamics 365 Human Resources alkalmazásban lehetősége van csempéket konfigurálni az Alkalmazotti önkiszolgáló rendszer felső szintű navigációjához.</span><span class="sxs-lookup"><span data-stu-id="d36f4-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="d36f4-105">A juttatási terv csempék a felhasználókat olyan juttatási konstrukciókhoz irányítják, amelyekre jogosultak.</span><span class="sxs-lookup"><span data-stu-id="d36f4-105">Benefit plan tiles direct users to benefit plans that they're eligible for.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="d36f4-106">Juttatásikonstrukció-csempe beállítása</span><span class="sxs-lookup"><span data-stu-id="d36f4-106">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="d36f4-107">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="d36f4-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="d36f4-108">Válassza ki a **Juttatásikonstrukció-csempe beállítása** lapot, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d36f4-108">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="d36f4-109">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="d36f4-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="d36f4-110">Mező</span><span class="sxs-lookup"><span data-stu-id="d36f4-110">Field</span></span> | <span data-ttu-id="d36f4-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="d36f4-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d36f4-112">**Csempe azonosítója**</span><span class="sxs-lookup"><span data-stu-id="d36f4-112">**Tile ID**</span></span> | <span data-ttu-id="d36f4-113">A mozaik egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="d36f4-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="d36f4-114">**CSempecímke felirata**</span><span class="sxs-lookup"><span data-stu-id="d36f4-114">**Tile label text**</span></span> | <span data-ttu-id="d36f4-115">Az önkiszolgáló rendszer csempéjén megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="d36f4-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="d36f4-116">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="d36f4-116">**Description**</span></span> | <span data-ttu-id="d36f4-117">A csempe leírása.</span><span class="sxs-lookup"><span data-stu-id="d36f4-117">A description of the tile.</span></span> |
   | <span data-ttu-id="d36f4-118">**Internetcím**</span><span class="sxs-lookup"><span data-stu-id="d36f4-118">**Internet address**</span></span> | <span data-ttu-id="d36f4-119">Adja meg az alkalmazotti önkiszolgáló rendszer oldalának URL-jét.</span><span class="sxs-lookup"><span data-stu-id="d36f4-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="d36f4-120">**Csempeméret**</span><span class="sxs-lookup"><span data-stu-id="d36f4-120">**Tile size**</span></span> | <span data-ttu-id="d36f4-121">A csempe mérete: kis, közepes vagy nagy.</span><span class="sxs-lookup"><span data-stu-id="d36f4-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="d36f4-122">**Cél**</span><span class="sxs-lookup"><span data-stu-id="d36f4-122">**Target**</span></span> | <span data-ttu-id="d36f4-123">Megadja, hogy a lapnak új ablakban vagy az aktuális ablakban kell-e megnyílnia.</span><span class="sxs-lookup"><span data-stu-id="d36f4-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="d36f4-124">**Csempeháttérkép**</span><span class="sxs-lookup"><span data-stu-id="d36f4-124">**Tile background image**</span></span> | <span data-ttu-id="d36f4-125">A csempéhez használandó kép URL-címe (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="d36f4-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="d36f4-126">**Kezdete**</span><span class="sxs-lookup"><span data-stu-id="d36f4-126">**Start**</span></span> | <span data-ttu-id="d36f4-127">A csempe elérhetőségének kezdő dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="d36f4-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="d36f4-128">**End**</span><span class="sxs-lookup"><span data-stu-id="d36f4-128">**End**</span></span> | <span data-ttu-id="d36f4-129">A csempe elérhetőségének befejező dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="d36f4-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="d36f4-130">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d36f4-130">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="d36f4-131">Rugalmas hitelkonstrukció csempe beállítása</span><span class="sxs-lookup"><span data-stu-id="d36f4-131">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="d36f4-132">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="d36f4-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="d36f4-133">Válassza ki a **Rugalmas hitelkonstrukció csempe beállítása** lapot, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d36f4-133">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="d36f4-134">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="d36f4-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="d36f4-135">Mező</span><span class="sxs-lookup"><span data-stu-id="d36f4-135">Field</span></span> | <span data-ttu-id="d36f4-136">Leírás</span><span class="sxs-lookup"><span data-stu-id="d36f4-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d36f4-137">**Csempe azonosítója**</span><span class="sxs-lookup"><span data-stu-id="d36f4-137">**Tile ID**</span></span> | <span data-ttu-id="d36f4-138">A mozaik egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="d36f4-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="d36f4-139">**CSempecímke felirata**</span><span class="sxs-lookup"><span data-stu-id="d36f4-139">**Tile label text**</span></span> | <span data-ttu-id="d36f4-140">Az önkiszolgáló rendszer csempéjén megjelenő szöveg.</span><span class="sxs-lookup"><span data-stu-id="d36f4-140">The text that will appear for the tile on Self service.</span></span> |
   | <span data-ttu-id="d36f4-141">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="d36f4-141">**Description**</span></span> | <span data-ttu-id="d36f4-142">A csempe leírása.</span><span class="sxs-lookup"><span data-stu-id="d36f4-142">A description of the tile.</span></span> |
   | <span data-ttu-id="d36f4-143">**Internetcím**</span><span class="sxs-lookup"><span data-stu-id="d36f4-143">**Internet address**</span></span> | <span data-ttu-id="d36f4-144">Adja meg az alkalmazotti önkiszolgáló rendszer oldalának URL-jét.</span><span class="sxs-lookup"><span data-stu-id="d36f4-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="d36f4-145">**Csempeméret**</span><span class="sxs-lookup"><span data-stu-id="d36f4-145">**Tile size**</span></span> | <span data-ttu-id="d36f4-146">A csempe mérete: kis, közepes vagy nagy.</span><span class="sxs-lookup"><span data-stu-id="d36f4-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="d36f4-147">**Cél**</span><span class="sxs-lookup"><span data-stu-id="d36f4-147">**Target**</span></span> | <span data-ttu-id="d36f4-148">Megadja, hogy a lapnak új ablakban vagy az aktuális ablakban kell-e megnyílnia.</span><span class="sxs-lookup"><span data-stu-id="d36f4-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="d36f4-149">**Csempeháttérkép**</span><span class="sxs-lookup"><span data-stu-id="d36f4-149">**Tile background image**</span></span> | <span data-ttu-id="d36f4-150">A csempéhez használandó kép URL-címe (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="d36f4-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="d36f4-151">**Kezdete**</span><span class="sxs-lookup"><span data-stu-id="d36f4-151">**Start**</span></span> | <span data-ttu-id="d36f4-152">A csempe elérhetőségének kezdő dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="d36f4-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="d36f4-153">**End**</span><span class="sxs-lookup"><span data-stu-id="d36f4-153">**End**</span></span> | <span data-ttu-id="d36f4-154">A csempe elérhetőségének befejező dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="d36f4-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="d36f4-155">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d36f4-155">Select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]