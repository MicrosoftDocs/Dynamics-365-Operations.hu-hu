---
title: A szállítmányozók beállítása
description: Ez a témakör bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni az olyan részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj.
author: ShylaThompson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a43a99e10b915f1265be14f2442069dae3a22e5
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867027"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="3f1d1-103">A szállítmányozók beállítása</span><span class="sxs-lookup"><span data-stu-id="3f1d1-103">Set up shipping carriers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3f1d1-104">Ez a témakör bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni az olyan részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-104">This topic shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="3f1d1-105">A szállítási koordinátor ezután hozzárendelheti a szállítmányozót egy bejövő vagy kimenő rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="3f1d1-106">Új szállítmányozó létrehozása</span><span class="sxs-lookup"><span data-stu-id="3f1d1-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="3f1d1-107">Ugorjon a **Navigációs ablaktábla > Modulok > Szállításkezelés > Beállítás > Szállítmányozók > Szállítmányozók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-107">Go to **Navigation pane > Modules > Transportation management > Setup > Carriers > Shipping carriers**.</span></span>
2. <span data-ttu-id="3f1d1-108">A műveleti ablaktáblán válassza ki az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-108">Select **New** in the Action pane.</span></span>
3. <span data-ttu-id="3f1d1-109">Adjon meg egy értéket a **Szállítmányozók** mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-109">In the **Shipping carrier** field, type a value.</span></span>
4. <span data-ttu-id="3f1d1-110">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="3f1d1-111">A **Mód** mezőben válasszon ki egy opciót a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-111">In the **Mode** field, select an option from the drop-down menu.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="3f1d1-112">A szállítmányozóra vonatkozó általános információk kitöltése</span><span class="sxs-lookup"><span data-stu-id="3f1d1-112">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="3f1d1-113">Bontsa ki az **Áttekintés** részt.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-113">Toggle the expansion of the **Overview** section.</span></span>
2. <span data-ttu-id="3f1d1-114">Jelölje be a **Szállítmányozó aktiválása** jelölőnégyzetet, vagy törölje a kijelölést.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-114">Check or uncheck the **Activate shipping carrier** checkbox.</span></span>
3. <span data-ttu-id="3f1d1-115">A **Szállítói számla** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-115">In the **Vendor account** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="3f1d1-116">Válassza ki a szállítmányozóhoz hozzárendelendő szállítókódot.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-116">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="3f1d1-117">A **Szállítási ajánlat típusa** mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-117">In the **Transportation tender type** field, select an option.</span></span> <span data-ttu-id="3f1d1-118">Válassza ki a **Kézi** lehetőséget a Szállítási ajánlat oldal használatához, vagy válassza ki az **EDI** lehetőséget az ajánlat frissítéséhez az Electronic Data Interchange (EDI) szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-118">Select **Manual** to use the Transportation Tender page, or select **EDI** to update the tender by using Electronic Data Interchange (EDI).</span></span>  
5. <span data-ttu-id="3f1d1-119">Jelölje be a **Szállítmányozóminősítés engedélyezése** jelölőnégyzetet, vagy törölje a kijelölést.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-119">Check or uncheck the **Activate carrier rating** checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="3f1d1-120">A szállítmányozó számára szükséges szolgáltatások létrehozása</span><span class="sxs-lookup"><span data-stu-id="3f1d1-120">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="3f1d1-121">Bontsa ki a **Szolgáltatások** részt.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-121">Toggle the expansion of the **Services** section.</span></span>
2. <span data-ttu-id="3f1d1-122">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-122">Select **New**.</span></span>
3. <span data-ttu-id="3f1d1-123">Adjon meg egy értéket a **Szállítmányozói szolgáltatás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-123">In the **Carrier service** field, type a value.</span></span>
4. <span data-ttu-id="3f1d1-124">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-124">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="3f1d1-125">A **Szállítási mód** mezőben válasszon ki egy opciót a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-125">In the **Transportation method** field, select an option from the drop-down menu.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="3f1d1-126">A szállítmányozó címének beállítása (opcionális)</span><span class="sxs-lookup"><span data-stu-id="3f1d1-126">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="3f1d1-127">Bontsa ki a **Címek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-127">Toggle the expansion of the **Addresses** section.</span></span>
2. <span data-ttu-id="3f1d1-128">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-128">Select **New**.</span></span>
3. <span data-ttu-id="3f1d1-129">Adjon meg egy értéket a **Név vagy leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-129">In the **Name or description** field, type a value.</span></span>
4. <span data-ttu-id="3f1d1-130">Az **Ország/régió** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-130">In the **Country/region** field, select an option from the drop-down menu.</span></span>
5. <span data-ttu-id="3f1d1-131">A **Záró irányítószám** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-131">In the **ZIP/postal code** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="3f1d1-132">Adjon meg egy értéket az **Utca** mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-132">In the **Street** field, type a value.</span></span>
7. <span data-ttu-id="3f1d1-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-133">Select **OK**.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="3f1d1-134">A szállítmányozó díjazási profil beállítása.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-134">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="3f1d1-135">Bontsa ki a **Díjazási profilok** részt.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-135">Toggle the expansion of the **Rating profiles** section.</span></span>
2. <span data-ttu-id="3f1d1-136">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-136">Select **New**.</span></span>
3. <span data-ttu-id="3f1d1-137">Adjon meg egy értéket a **Díjazási profilok** mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-137">In the **Rating profile** field, type a value.</span></span>
4. <span data-ttu-id="3f1d1-138">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="3f1d1-139">A **Hely** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-139">In the **Site** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="3f1d1-140">A **Raktár** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-140">In the **Warehouse** field, select an option from the drop-down menu.</span></span>
7. <span data-ttu-id="3f1d1-141">A **Díjkalkulátor** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-141">In the **Rate engine** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="3f1d1-142">Válassza ki a szállítmányozóval kötött szerződésnek megfelelő díjkalkulátort.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-142">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
8. <span data-ttu-id="3f1d1-143">A **Díjjegyzék** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-143">In the **Rate master** field, select an option from the drop-down menu.</span></span>
9. <span data-ttu-id="3f1d1-144">A **Szállításiidő-kalkulátor** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-144">In the **Transit time engine** field, select an option from the drop-down menu.</span></span>
10. <span data-ttu-id="3f1d1-145">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f1d1-145">Select **Save**.</span></span>

