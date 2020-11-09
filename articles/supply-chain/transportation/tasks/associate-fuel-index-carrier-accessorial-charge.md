---
title: Üzemanyag-mutató társítása egy szállítóhoz kiegészítő díjként
description: Ez az útmutató bemutatja, hogyan lehet létrehozni egy kiegészítő szolgáltatás társítást, szállítmányozó kiegészítő szolgáltatási díjat, kiegészítő alapszolgáltatást üzemanyag-pótdíjhoz, és társítani egy szállítmányozó üzemanyag-mutatót egy szállítmányozóhoz.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c91d49c2ccdc274632e3acf94b836e19dc6cdaa8
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017000"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a><span data-ttu-id="e1194-103">Üzemanyag-mutató társítása egy szállítóhoz kiegészítő díjként</span><span class="sxs-lookup"><span data-stu-id="e1194-103">Associate a fuel index with a carrier as an accessorial charge</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e1194-104">Ez az útmutató bemutatja, hogyan lehet létrehozni egy kiegészítő szolgáltatás társítást, szállítmányozó kiegészítő szolgáltatási díjat, kiegészítő alapszolgáltatást üzemanyag-pótdíjhoz, és társítani egy szállítmányozó üzemanyag-mutatót egy szállítmányozóhoz.</span><span class="sxs-lookup"><span data-stu-id="e1194-104">This guide shows how to create an accessorial assignment, carrier accessorial charge, accessorial master for fuel surcharge, and associate a carrier fuel index with a carrier.</span></span> <span data-ttu-id="e1194-105">Az útmutató futtatása előtt létre kell hoznia egy szállítmányozó üzemanyag-mutatót.</span><span class="sxs-lookup"><span data-stu-id="e1194-105">You need to have set up a carrier fuel index before you run this guide.</span></span> <span data-ttu-id="e1194-106">A „Szállítmányozói üzemanyag-mutató létrehozása” útmutatót használhatja ehhez.</span><span class="sxs-lookup"><span data-stu-id="e1194-106">You can use the "Set up a carrier fuel index" guide to do this.</span></span> <span data-ttu-id="e1194-107">Általában a logisztikai vezető végzi el ezeket a beállítási feladatokat.</span><span class="sxs-lookup"><span data-stu-id="e1194-107">These setup tasks are typically done by a Logistics manager.</span></span> <span data-ttu-id="e1194-108">Az eljárás létrehozásához az USMF bemutatóadatokat használtuk.</span><span class="sxs-lookup"><span data-stu-id="e1194-108">The demo data used to create this procedure is USMF.</span></span>


## <a name="create-an-accessorial-master"></a><span data-ttu-id="e1194-109">Kiegészítő szolgáltatások alapadatainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="e1194-109">Create an accessorial master</span></span>
1. <span data-ttu-id="e1194-110">Lépjen a Szállításkezelés > Beállítás > Minősítés > Kiegészítő alapszolgáltatások pontra.</span><span class="sxs-lookup"><span data-stu-id="e1194-110">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="e1194-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1194-111">Click New.</span></span>
3. <span data-ttu-id="e1194-112">A Kiegészítő alapszolgáltatások mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e1194-112">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="e1194-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e1194-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="e1194-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e1194-114">Click Save.</span></span>

## <a name="create-a-carrier-accessorial-charge"></a><span data-ttu-id="e1194-115">Szállítmányozó kiegészítő költség létrehozása</span><span class="sxs-lookup"><span data-stu-id="e1194-115">Create a carrier accessorial charge</span></span>
1. <span data-ttu-id="e1194-116">Lépjen a Szállításkezelés > Beállítás > Minősítés > Szállítmányozó kiegészítő szolgáltatásának díjai pontra.</span><span class="sxs-lookup"><span data-stu-id="e1194-116">Go to Transportation management > Setup > Rating > Carrier accessorial charges.</span></span>
2. <span data-ttu-id="e1194-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1194-117">Click New.</span></span>
3. <span data-ttu-id="e1194-118">Írjon be egy értéket a Szállítmányozó kiegészítő szolgáltatása azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e1194-118">In the Carrier accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="e1194-119">A Szállítmányozó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e1194-119">In the Shipping carrier field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="e1194-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e1194-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e1194-121">Ebben a példában válassza a teherautós szállítmányozót.</span><span class="sxs-lookup"><span data-stu-id="e1194-121">In this example, choose Truck Carrier.</span></span>  
6. <span data-ttu-id="e1194-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e1194-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="e1194-123">A Szállítmányozói szolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e1194-123">In the Carrier service field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="e1194-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e1194-124">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="e1194-125">A Kiegészítő alapszolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e1194-125">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="e1194-126">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e1194-126">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e1194-127">Ebben a példában válassza ki az újonnan létrehozott Kiegészítő alapszolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="e1194-127">In this example, choose the newly created Accessorial master.</span></span>  
11. <span data-ttu-id="e1194-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e1194-128">Click Save.</span></span>

## <a name="create-an-accessorial-assignment"></a><span data-ttu-id="e1194-129">Kiegészítő szolgáltatási megbízás létrehozása</span><span class="sxs-lookup"><span data-stu-id="e1194-129">Create an accessorial assignment</span></span>
1. <span data-ttu-id="e1194-130">Kattintson a Kiegészítő szolgáltatások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1194-130">Click Accessorial assignments.</span></span>
2. <span data-ttu-id="e1194-131">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1194-131">Click New.</span></span>
3. <span data-ttu-id="e1194-132">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e1194-132">In the Name field, type a value.</span></span>
4. <span data-ttu-id="e1194-133">Bontsa ki a Feltételek részt.</span><span class="sxs-lookup"><span data-stu-id="e1194-133">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="e1194-134">A feltételek között választhat úgy, hogy mindig az üzemanyag-pótdíjat alkalmazza, vagy ebben a példában válassza ki, hogy csak bizonyos régión belül legyen alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="e1194-134">In the criteria, you can choose to always apply the fuel surcharge or for this example choose that it only applies within a certain region.</span></span>  
5. <span data-ttu-id="e1194-135">Írjon be egy értéket a Kezdő irányítószám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e1194-135">In the ZIP/postal code from field, type a value.</span></span>
6. <span data-ttu-id="e1194-136">Írjon be egy értéket a Záró irányítószám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e1194-136">In the ZIP/postal code to field, type a value.</span></span>
7. <span data-ttu-id="e1194-137">Bontsa ki a Számítás részt.</span><span class="sxs-lookup"><span data-stu-id="e1194-137">Toggle the expansion of the Calculation section.</span></span>
    * <span data-ttu-id="e1194-138">A számítás szakaszban megadhatja az üzemanyag-pótdíj számítását.</span><span class="sxs-lookup"><span data-stu-id="e1194-138">In the calculation section you can specify how to calculate the fuel surcharge.</span></span> <span data-ttu-id="e1194-139">Ez a számítás a Kiegészítő szolgáltatás egységtől függ, amelyet a számítás alapjaként kiválasztott.</span><span class="sxs-lookup"><span data-stu-id="e1194-139">This calculation depends on the Accessorial unit that you chose as the base for your calculation.</span></span>  
8. <span data-ttu-id="e1194-140">A Kiegészítő díj típusa mezőben válassza ki az „Üzemanyag-pótdíj” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e1194-140">In the Accessorial fee type field, select 'Fuel surcharge'.</span></span>
9. <span data-ttu-id="e1194-141">A Kiegészítő szolgáltatás egysége mezőben válassza ki a „Futásteljesítmény” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e1194-141">In the Accessorial unit field, select 'Mileage'.</span></span>
10. <span data-ttu-id="e1194-142">A Régió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e1194-142">In the Region field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e1194-143">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e1194-143">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="e1194-144">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e1194-144">Click Save.</span></span>

## <a name="update-the-carrier-rating-profile"></a><span data-ttu-id="e1194-145">Szállítmányozó minősítési profiljának frissítése</span><span class="sxs-lookup"><span data-stu-id="e1194-145">Update the carrier rating profile</span></span>
1. <span data-ttu-id="e1194-146">Ugorjon a Szállításkezelés > Beállítás > Szállítmányozók > Szállítmányozók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1194-146">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="e1194-147">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e1194-147">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e1194-148">Bontsa ki a Díjazási profilok részt.</span><span class="sxs-lookup"><span data-stu-id="e1194-148">Toggle the expansion of the Rating profiles section.</span></span>
4. <span data-ttu-id="e1194-149">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1194-149">Click Edit.</span></span>
5. <span data-ttu-id="e1194-150">A Szállítmányozói üzemanyag-mutató mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e1194-150">In the Carrier fuel index field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="e1194-151">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e1194-151">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="e1194-152">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e1194-152">Click Save.</span></span>

