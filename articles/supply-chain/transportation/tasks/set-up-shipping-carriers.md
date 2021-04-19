---
title: A szállítmányozók beállítása
description: Ez a témakör bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni az olyan részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj.
author: ShylaThompson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c292470e6c70af4dfe11bbe324ebcf93438e29d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840461"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="95401-103">A szállítmányozók beállítása</span><span class="sxs-lookup"><span data-stu-id="95401-103">Set up shipping carriers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="95401-104">Ez a témakör bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni az olyan részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj.</span><span class="sxs-lookup"><span data-stu-id="95401-104">This topic shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="95401-105">A szállítási koordinátor ezután hozzárendelheti a szállítmányozót egy bejövő vagy kimenő rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="95401-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="95401-106">Új szállítmányozó létrehozása</span><span class="sxs-lookup"><span data-stu-id="95401-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="95401-107">Ugorjon a **Navigációs ablaktábla > Modulok > Szállításkezelés > Beállítás > Szállítmányozók > Szállítmányozók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="95401-107">Go to **Navigation pane > Modules > Transportation management > Setup > Carriers > Shipping carriers**.</span></span>
2. <span data-ttu-id="95401-108">A Művelet panelen válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95401-108">Select **New** on the Action Pane.</span></span>
3. <span data-ttu-id="95401-109">Adjon meg egy értéket a **Szállítmányozók** mezőben.</span><span class="sxs-lookup"><span data-stu-id="95401-109">In the **Shipping carrier** field, type a value.</span></span>
4. <span data-ttu-id="95401-110">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="95401-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="95401-111">A **Mód** mezőben válasszon ki egy opciót a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="95401-111">In the **Mode** field, select an option from the drop-down menu.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="95401-112">A szállítmányozóra vonatkozó általános információk kitöltése</span><span class="sxs-lookup"><span data-stu-id="95401-112">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="95401-113">Bontsa ki az **Áttekintés** részt.</span><span class="sxs-lookup"><span data-stu-id="95401-113">Toggle the expansion of the **Overview** section.</span></span>
2. <span data-ttu-id="95401-114">Jelölje be a **Szállítmányozó aktiválása** jelölőnégyzetet, vagy törölje a kijelölést.</span><span class="sxs-lookup"><span data-stu-id="95401-114">Check or uncheck the **Activate shipping carrier** checkbox.</span></span>
3. <span data-ttu-id="95401-115">A **Szállítói számla** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="95401-115">In the **Vendor account** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="95401-116">Válassza ki a szállítmányozóhoz hozzárendelendő szállítókódot.</span><span class="sxs-lookup"><span data-stu-id="95401-116">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="95401-117">A **Szállítási ajánlat típusa** mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95401-117">In the **Transportation tender type** field, select an option.</span></span> <span data-ttu-id="95401-118">Válassza ki a **Kézi** lehetőséget a Szállítási ajánlat oldal használatához, vagy válassza ki az **EDI** lehetőséget az ajánlat frissítéséhez az Electronic Data Interchange (EDI) szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="95401-118">Select **Manual** to use the Transportation Tender page, or select **EDI** to update the tender by using Electronic Data Interchange (EDI).</span></span>  
5. <span data-ttu-id="95401-119">Jelölje be a **Szállítmányozóminősítés engedélyezése** jelölőnégyzetet, vagy törölje a kijelölést.</span><span class="sxs-lookup"><span data-stu-id="95401-119">Check or uncheck the **Activate carrier rating** checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="95401-120">A szállítmányozó számára szükséges szolgáltatások létrehozása</span><span class="sxs-lookup"><span data-stu-id="95401-120">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="95401-121">Bontsa ki a **Szolgáltatások** részt.</span><span class="sxs-lookup"><span data-stu-id="95401-121">Toggle the expansion of the **Services** section.</span></span>
2. <span data-ttu-id="95401-122">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95401-122">Select **New**.</span></span>
3. <span data-ttu-id="95401-123">Adjon meg egy értéket a **Szállítmányozói szolgáltatás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="95401-123">In the **Carrier service** field, type a value.</span></span>
4. <span data-ttu-id="95401-124">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="95401-124">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="95401-125">A **Szállítási mód** mezőben válasszon ki egy opciót a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="95401-125">In the **Transportation method** field, select an option from the drop-down menu.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="95401-126">A szállítmányozó címének beállítása (opcionális)</span><span class="sxs-lookup"><span data-stu-id="95401-126">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="95401-127">Bontsa ki a **Címek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="95401-127">Toggle the expansion of the **Addresses** section.</span></span>
2. <span data-ttu-id="95401-128">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95401-128">Select **New**.</span></span>
3. <span data-ttu-id="95401-129">Adjon meg egy értéket a **Név vagy leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="95401-129">In the **Name or description** field, type a value.</span></span>
4. <span data-ttu-id="95401-130">Az **Ország/régió** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="95401-130">In the **Country/region** field, select an option from the drop-down menu.</span></span>
5. <span data-ttu-id="95401-131">A **Záró irányítószám** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="95401-131">In the **ZIP/postal code** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="95401-132">Adjon meg egy értéket az **Utca** mezőben.</span><span class="sxs-lookup"><span data-stu-id="95401-132">In the **Street** field, type a value.</span></span>
7. <span data-ttu-id="95401-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95401-133">Select **OK**.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="95401-134">A szállítmányozó díjazási profil beállítása.</span><span class="sxs-lookup"><span data-stu-id="95401-134">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="95401-135">Bontsa ki a **Díjazási profilok** részt.</span><span class="sxs-lookup"><span data-stu-id="95401-135">Toggle the expansion of the **Rating profiles** section.</span></span>
2. <span data-ttu-id="95401-136">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95401-136">Select **New**.</span></span>
3. <span data-ttu-id="95401-137">Adjon meg egy értéket a **Díjazási profilok** mezőben.</span><span class="sxs-lookup"><span data-stu-id="95401-137">In the **Rating profile** field, type a value.</span></span>
4. <span data-ttu-id="95401-138">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="95401-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="95401-139">A **Hely** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="95401-139">In the **Site** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="95401-140">A **Raktár** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="95401-140">In the **Warehouse** field, select an option from the drop-down menu.</span></span>
7. <span data-ttu-id="95401-141">A **Díjkalkulátor** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="95401-141">In the **Rate engine** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="95401-142">Válassza ki a szállítmányozóval kötött szerződésnek megfelelő díjkalkulátort.</span><span class="sxs-lookup"><span data-stu-id="95401-142">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
8. <span data-ttu-id="95401-143">A **Díjjegyzék** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="95401-143">In the **Rate master** field, select an option from the drop-down menu.</span></span>
9. <span data-ttu-id="95401-144">A **Szállításiidő-kalkulátor** mezőben válasszon ki egy lehetőséget a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="95401-144">In the **Transit time engine** field, select an option from the drop-down menu.</span></span>
10. <span data-ttu-id="95401-145">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95401-145">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]