--- 
title: "A szállítmányozók beállítása"
description: "Ez az eljárás bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni a részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e27be049bebd63c9266029b8981874417a9f0a8c
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="e7412-103">A szállítmányozók beállítása</span><span class="sxs-lookup"><span data-stu-id="e7412-103">Set up shipping carriers</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e7412-104">Ez az eljárás bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni a részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj.</span><span class="sxs-lookup"><span data-stu-id="e7412-104">This procedure shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="e7412-105">A szállítási koordinátor ezután hozzárendelheti a szállítmányozót egy bejövő vagy kimenő rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="e7412-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="e7412-106">Új szállítmányozó létrehozása</span><span class="sxs-lookup"><span data-stu-id="e7412-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="e7412-107">Ugorjon a Szállításkezelés > Beállítás > Szállítmányozók > Szállítmányozók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7412-107">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="e7412-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7412-108">Click New.</span></span>
3. <span data-ttu-id="e7412-109">Írjon be egy értéket a Szállítmányozók mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e7412-109">In the Shipping carrier field, type a value.</span></span>
4. <span data-ttu-id="e7412-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e7412-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="e7412-111">A Mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7412-111">In the Mode field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="e7412-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e7412-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="e7412-113">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7412-113">In the list, click the link in the selected row.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="e7412-114">A szállítmányozóra vonatkozó általános információk kitöltése</span><span class="sxs-lookup"><span data-stu-id="e7412-114">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="e7412-115">Bontsa ki az Áttekintés részt.</span><span class="sxs-lookup"><span data-stu-id="e7412-115">Toggle the expansion of the Overview section.</span></span>
2. <span data-ttu-id="e7412-116">Jelölje be a Szállítmányozó aktiválása jelölőnégyzetet, vagy törölje a kijelölést.</span><span class="sxs-lookup"><span data-stu-id="e7412-116">Check or uncheck the Activate shipping carrier checkbox.</span></span>
3. <span data-ttu-id="e7412-117">A Szállító mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7412-117">In the Vendor field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e7412-118">Válassza ki a szállítmányozóhoz hozzárendelendő szállítókódot.</span><span class="sxs-lookup"><span data-stu-id="e7412-118">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="e7412-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e7412-119">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e7412-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7412-120">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e7412-121">A Szállítási ajánlat típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7412-121">In the Transportation tender type field, select an option.</span></span>
    * <span data-ttu-id="e7412-122">Válassza ki a Kézi lehetőséget a Szállítási ajánlat oldal használatához, vagy válassza ki az EDI lehetőséget az ajánlat frissítéséhez az Electronic Data Interchange (EDI) szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="e7412-122">Select Manual to use the Transportation Tender page, or select EDI to update the tender by using Electronic Data Interchange (EDI).</span></span>  
7. <span data-ttu-id="e7412-123">Jelölje be a Szállítmányozóminősítés engedélyezése jelölőnégyzetet, vagy törölje a kijelölést.</span><span class="sxs-lookup"><span data-stu-id="e7412-123">Check or uncheck the Activate carrier rating checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="e7412-124">A szállítmányozó számára szükséges szolgáltatások létrehozása</span><span class="sxs-lookup"><span data-stu-id="e7412-124">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="e7412-125">Bontsa ki a Szolgáltatások részt.</span><span class="sxs-lookup"><span data-stu-id="e7412-125">Toggle the expansion of the Services section.</span></span>
2. <span data-ttu-id="e7412-126">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7412-126">Click New.</span></span>
3. <span data-ttu-id="e7412-127">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="e7412-127">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="e7412-128">Írjon be egy értéket a Szállítmányozói szolgáltatás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e7412-128">In the Carrier service field, type a value.</span></span>
5. <span data-ttu-id="e7412-129">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e7412-129">In the Name field, type a value.</span></span>
6. <span data-ttu-id="e7412-130">A Szállítási mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7412-130">In the Transportation method field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="e7412-131">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e7412-131">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="e7412-132">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7412-132">In the list, click the link in the selected row.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="e7412-133">A szállítmányozó címének beállítása (opcionális)</span><span class="sxs-lookup"><span data-stu-id="e7412-133">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="e7412-134">A Címek szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="e7412-134">Toggle the expansion of the Addresses section.</span></span>
2. <span data-ttu-id="e7412-135">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7412-135">Click New.</span></span>
3. <span data-ttu-id="e7412-136">A „Név vagy leírás” mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e7412-136">In the Name or description field, type a value.</span></span>
4. <span data-ttu-id="e7412-137">Az Ország/régió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7412-137">In the Country/region field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="e7412-138">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7412-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e7412-139">Az Irányítószámok záró értéke mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7412-139">In the ZIP/postal code field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="e7412-140">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="e7412-140">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="e7412-141">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7412-141">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="e7412-142">Érték beírása az Utcanév mezőbe</span><span class="sxs-lookup"><span data-stu-id="e7412-142">In the Street field, type a value.</span></span>
10. <span data-ttu-id="e7412-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e7412-143">Click OK.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="e7412-144">A szállítmányozó díjazási profil beállítása.</span><span class="sxs-lookup"><span data-stu-id="e7412-144">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="e7412-145">Bontsa ki a Díjazási profilok részt.</span><span class="sxs-lookup"><span data-stu-id="e7412-145">Toggle the expansion of the Rating profiles section.</span></span>
2. <span data-ttu-id="e7412-146">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7412-146">Click New.</span></span>
3. <span data-ttu-id="e7412-147">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="e7412-147">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="e7412-148">Írjon egy értéket a Díjazási profil mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e7412-148">In the Rating profile field, type a value.</span></span>
5. <span data-ttu-id="e7412-149">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e7412-149">In the Name field, type a value.</span></span>
6. <span data-ttu-id="e7412-150">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7412-150">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="e7412-151">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="e7412-151">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="e7412-152">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7412-152">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="e7412-153">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7412-153">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="e7412-154">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="e7412-154">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="e7412-155">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7412-155">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="e7412-156">A Díjkalkulátor mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7412-156">In the Rate engine field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e7412-157">Válassza ki a szállítmányozóval kötött szerződésnek megfelelő díjkalkulátort.</span><span class="sxs-lookup"><span data-stu-id="e7412-157">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
13. <span data-ttu-id="e7412-158">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e7412-158">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="e7412-159">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7412-159">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="e7412-160">A Díjjegyzék mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7412-160">In the Rate master field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="e7412-161">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="e7412-161">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="e7412-162">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7412-162">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="e7412-163">A Szállításiidő-kalkulátor mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7412-163">In the Transit time engine field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="e7412-164">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7412-164">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="e7412-165">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e7412-165">Click Save.</span></span>


