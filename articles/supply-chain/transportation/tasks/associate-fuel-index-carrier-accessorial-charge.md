---
title: Üzemanyag-mutató társítása egy szállítóhoz kiegészítő díjként
description: Ez az útmutató bemutatja, hogyan lehet létrehozni egy kiegészítő szolgáltatás társítást, szállítmányozó kiegészítő szolgáltatási díjat, kiegészítő alapszolgáltatást üzemanyag-pótdíjhoz, és társítani egy szállítmányozó üzemanyag-mutatót egy szállítmányozóhoz.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
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
ms.openlocfilehash: 0fbd58fb6b03f3c6eb5e54f811d98ad636e65a94
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146376"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a><span data-ttu-id="a43d7-103">Üzemanyag-mutató társítása egy szállítóhoz kiegészítő díjként</span><span class="sxs-lookup"><span data-stu-id="a43d7-103">Associate a fuel index with a carrier as an accessorial charge</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a43d7-104">Ez az útmutató bemutatja, hogyan lehet létrehozni egy kiegészítő szolgáltatás társítást, szállítmányozó kiegészítő szolgáltatási díjat, kiegészítő alapszolgáltatást üzemanyag-pótdíjhoz, és társítani egy szállítmányozó üzemanyag-mutatót egy szállítmányozóhoz.</span><span class="sxs-lookup"><span data-stu-id="a43d7-104">This guide shows how to create an accessorial assignment, carrier accessorial charge, accessorial master for fuel surcharge, and associate a carrier fuel index with a carrier.</span></span> <span data-ttu-id="a43d7-105">Az útmutató futtatása előtt létre kell hoznia egy szállítmányozó üzemanyag-mutatót.</span><span class="sxs-lookup"><span data-stu-id="a43d7-105">You need to have set up a carrier fuel index before you run this guide.</span></span> <span data-ttu-id="a43d7-106">A „Szállítmányozói üzemanyag-mutató létrehozása” útmutatót használhatja ehhez.</span><span class="sxs-lookup"><span data-stu-id="a43d7-106">You can use the "Set up a carrier fuel index" guide to do this.</span></span> <span data-ttu-id="a43d7-107">Általában a logisztikai vezető végzi el ezeket a beállítási feladatokat.</span><span class="sxs-lookup"><span data-stu-id="a43d7-107">These setup tasks are typically done by a Logistics manager.</span></span> <span data-ttu-id="a43d7-108">Az eljárás létrehozásához az USMF bemutatóadatokat használtuk.</span><span class="sxs-lookup"><span data-stu-id="a43d7-108">The demo data used to create this procedure is USMF.</span></span>


## <a name="create-an-accessorial-master"></a><span data-ttu-id="a43d7-109">Kiegészítő szolgáltatások alapadatainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="a43d7-109">Create an accessorial master</span></span>
1. <span data-ttu-id="a43d7-110">Lépjen a Szállításkezelés > Beállítás > Minősítés > Kiegészítő alapszolgáltatások pontra.</span><span class="sxs-lookup"><span data-stu-id="a43d7-110">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="a43d7-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a43d7-111">Click New.</span></span>
3. <span data-ttu-id="a43d7-112">A Kiegészítő alapszolgáltatások mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a43d7-112">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="a43d7-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a43d7-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="a43d7-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a43d7-114">Click Save.</span></span>

## <a name="create-a-carrier-accessorial-charge"></a><span data-ttu-id="a43d7-115">Szállítmányozó kiegészítő költség létrehozása</span><span class="sxs-lookup"><span data-stu-id="a43d7-115">Create a carrier accessorial charge</span></span>
1. <span data-ttu-id="a43d7-116">Lépjen a Szállításkezelés > Beállítás > Minősítés > Szállítmányozó kiegészítő szolgáltatásának díjai pontra.</span><span class="sxs-lookup"><span data-stu-id="a43d7-116">Go to Transportation management > Setup > Rating > Carrier accessorial charges.</span></span>
2. <span data-ttu-id="a43d7-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a43d7-117">Click New.</span></span>
3. <span data-ttu-id="a43d7-118">Írjon be egy értéket a Szállítmányozó kiegészítő szolgáltatása azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a43d7-118">In the Carrier accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="a43d7-119">A Szállítmányozó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a43d7-119">In the Shipping carrier field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="a43d7-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a43d7-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a43d7-121">Ebben a példában válassza a teherautós szállítmányozót.</span><span class="sxs-lookup"><span data-stu-id="a43d7-121">In this example, choose Truck Carrier.</span></span>  
6. <span data-ttu-id="a43d7-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a43d7-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="a43d7-123">A Szállítmányozói szolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a43d7-123">In the Carrier service field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="a43d7-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a43d7-124">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="a43d7-125">A Kiegészítő alapszolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a43d7-125">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="a43d7-126">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a43d7-126">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a43d7-127">Ebben a példában válassza ki az újonnan létrehozott Kiegészítő alapszolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="a43d7-127">In this example, choose the newly created Accessorial master.</span></span>  
11. <span data-ttu-id="a43d7-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a43d7-128">Click Save.</span></span>

## <a name="create-an-accessorial-assignment"></a><span data-ttu-id="a43d7-129">Kiegészítő szolgáltatási megbízás létrehozása</span><span class="sxs-lookup"><span data-stu-id="a43d7-129">Create an accessorial assignment</span></span>
1. <span data-ttu-id="a43d7-130">Kattintson a Kiegészítő szolgáltatások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a43d7-130">Click Accessorial assignments.</span></span>
2. <span data-ttu-id="a43d7-131">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a43d7-131">Click New.</span></span>
3. <span data-ttu-id="a43d7-132">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a43d7-132">In the Name field, type a value.</span></span>
4. <span data-ttu-id="a43d7-133">Bontsa ki a Feltételek részt.</span><span class="sxs-lookup"><span data-stu-id="a43d7-133">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="a43d7-134">A feltételek között választhat úgy, hogy mindig az üzemanyag-pótdíjat alkalmazza, vagy ebben a példában válassza ki, hogy csak bizonyos régión belül legyen alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="a43d7-134">In the criteria, you can choose to always apply the fuel surcharge or for this example choose that it only applies within a certain region.</span></span>  
5. <span data-ttu-id="a43d7-135">Írjon be egy értéket a Kezdő irányítószám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a43d7-135">In the ZIP/postal code from field, type a value.</span></span>
6. <span data-ttu-id="a43d7-136">Írjon be egy értéket a Záró irányítószám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a43d7-136">In the ZIP/postal code to field, type a value.</span></span>
7. <span data-ttu-id="a43d7-137">Bontsa ki a Számítás részt.</span><span class="sxs-lookup"><span data-stu-id="a43d7-137">Toggle the expansion of the Calculation section.</span></span>
    * <span data-ttu-id="a43d7-138">A számítás szakaszban megadhatja az üzemanyag-pótdíj számítását.</span><span class="sxs-lookup"><span data-stu-id="a43d7-138">In the calculation section you can specify how to calculate the fuel surcharge.</span></span> <span data-ttu-id="a43d7-139">Ez a számítás a Kiegészítő szolgáltatás egységtől függ, amelyet a számítás alapjaként kiválasztott.</span><span class="sxs-lookup"><span data-stu-id="a43d7-139">This calculation depends on the Accessorial unit that you chose as the base for your calculation.</span></span>  
8. <span data-ttu-id="a43d7-140">A Kiegészítő díj típusa mezőben válassza ki az „Üzemanyag-pótdíj” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a43d7-140">In the Accessorial fee type field, select 'Fuel surcharge'.</span></span>
9. <span data-ttu-id="a43d7-141">A Kiegészítő szolgáltatás egysége mezőben válassza ki a „Futásteljesítmény” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a43d7-141">In the Accessorial unit field, select 'Mileage'.</span></span>
10. <span data-ttu-id="a43d7-142">A Régió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a43d7-142">In the Region field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="a43d7-143">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a43d7-143">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="a43d7-144">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a43d7-144">Click Save.</span></span>

## <a name="update-the-carrier-rating-profile"></a><span data-ttu-id="a43d7-145">Szállítmányozó minősítési profiljának frissítése</span><span class="sxs-lookup"><span data-stu-id="a43d7-145">Update the carrier rating profile</span></span>
1. <span data-ttu-id="a43d7-146">Ugorjon a Szállításkezelés > Beállítás > Szállítmányozók > Szállítmányozók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a43d7-146">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="a43d7-147">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a43d7-147">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a43d7-148">Bontsa ki a Díjazási profilok részt.</span><span class="sxs-lookup"><span data-stu-id="a43d7-148">Toggle the expansion of the Rating profiles section.</span></span>
4. <span data-ttu-id="a43d7-149">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a43d7-149">Click Edit.</span></span>
5. <span data-ttu-id="a43d7-150">A Szállítmányozói üzemanyag-mutató mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a43d7-150">In the Carrier fuel index field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a43d7-151">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a43d7-151">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="a43d7-152">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a43d7-152">Click Save.</span></span>

