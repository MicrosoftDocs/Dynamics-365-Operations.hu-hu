--- 
title: "Értékesítési rendelések megerősítése"
description: "Ez az eljárás bemutatja, hogyan kell az értékesítési rendeléseket megerősíteni."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7cab69222c5004e6a62c632a9e85085403434ffd
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="confirm-sales-orders"></a><span data-ttu-id="26efd-103">Értékesítési rendelések megerősítése</span><span class="sxs-lookup"><span data-stu-id="26efd-103">Confirm sales orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="26efd-104">Ez az eljárás bemutatja, hogyan kell az értékesítési rendeléseket megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="26efd-104">This procedure demonstrates how to confirm sales orders.</span></span> <span data-ttu-id="26efd-105">Megjelenik, hogyan lehet megerősíteni egyetlen rendelést, illetve egyszerre több rendelést.</span><span class="sxs-lookup"><span data-stu-id="26efd-105">You’ll be shown how to confirm a single order, and how to confirm multiple orders at once.</span></span> <span data-ttu-id="26efd-106">Ezeket a feladatokat jellemzően egy értékesítési rendelés feldolgozó végzi el.</span><span class="sxs-lookup"><span data-stu-id="26efd-106">These tasks would typically be carried out by a sales order processor.</span></span> <span data-ttu-id="26efd-107">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="26efd-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="26efd-108">Mielőtt elkezdené, ellenőrizze, hogy van-e ugyanannak a vevőnek több nyitott értékesítési rendelése.</span><span class="sxs-lookup"><span data-stu-id="26efd-108">Before you start, make sure there are several open sales orders for the same customer.</span></span> <span data-ttu-id="26efd-109">Ha USMF-et használ, használhatja az US-027 vevőt.</span><span class="sxs-lookup"><span data-stu-id="26efd-109">If you’re using USMF, you can use customer US-027.</span></span>


## <a name="confirm-a-single-sales-order"></a><span data-ttu-id="26efd-110">Egy értékesítési rendelés megerősítése</span><span class="sxs-lookup"><span data-stu-id="26efd-110">Confirm a single sales order</span></span>
1. <span data-ttu-id="26efd-111">Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="26efd-111">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="26efd-112">A listában keresse meg és válassza ki a jóváhagyni kívánt rendelést.</span><span class="sxs-lookup"><span data-stu-id="26efd-112">In the list, find and select the order that you want to confirm.</span></span>
3. <span data-ttu-id="26efd-113">Kattintson a hivatkozásra az értékesítési rendelés számán a kiválasztott rendelés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="26efd-113">Click the link on the sales order number to open the selected order.</span></span>
4. <span data-ttu-id="26efd-114">A Művelet panelen kattintson az Értékesítés elemre.</span><span class="sxs-lookup"><span data-stu-id="26efd-114">On the Action Pane, click Sell.</span></span>
5. <span data-ttu-id="26efd-115">Kattintson az Értékesítési rendelés megerősítése gombra.</span><span class="sxs-lookup"><span data-stu-id="26efd-115">Click Confirm sales order.</span></span>
6. <span data-ttu-id="26efd-116">Bontsa ki vagy csukja össze a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="26efd-116">Expand or collapse the Parameters section.</span></span>
    * <span data-ttu-id="26efd-117">Győződjön meg arról, hogy a Feladás Igen mező aktív.</span><span class="sxs-lookup"><span data-stu-id="26efd-117">Make sure that the Posting Yes field is active.</span></span>  
7. <span data-ttu-id="26efd-118">Állítsa a Nyomtatás megerősítése pontot Igen-re.</span><span class="sxs-lookup"><span data-stu-id="26efd-118">Set the Print confirmation option to Yes.</span></span>
    * <span data-ttu-id="26efd-119">A Hitelkeret ellenőrzése mező megadja a vevő fennmaradó hitelkeretének kiszámításához használt módszert.</span><span class="sxs-lookup"><span data-stu-id="26efd-119">The Check credit limit field specifies the method that’s used to calculate a customer's remaining credit.</span></span> <span data-ttu-id="26efd-120">Alapértelmezésben ez a Kinnlevőségek paraméterei oldalról van átmásolva.</span><span class="sxs-lookup"><span data-stu-id="26efd-120">By default, it’s copied from the Accounts receivable parameters page.</span></span> <span data-ttu-id="26efd-121">Ha szeretné kihagyni a hitelkeret-ellenőrzést egy adott értékesítési rendelés megerősítésekor, állítsa Ne értékre a Hitelkeret-ellenőrzés elemet.</span><span class="sxs-lookup"><span data-stu-id="26efd-121">If you want to skip the credit limit check when confirming a specific sales order, set the Check credit limit to None.</span></span> <span data-ttu-id="26efd-122">Azonban tartsa szem előtt, hogy még akkor is, ha ez a mező beállítása Ne, a hitelkeret-ellenőrzés akkor is megtörténik, ha a Kötelező hitelkeret-korlát beállítást kiválasztotta a vevői alapadatokban.</span><span class="sxs-lookup"><span data-stu-id="26efd-122">However, you should be aware that even with if this field is set to None, the credit limit check will still be performed if the Mandatory credit limit option is selected on the customer master data.</span></span>  
8. <span data-ttu-id="26efd-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="26efd-123">Click OK.</span></span>
9. <span data-ttu-id="26efd-124">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="26efd-124">Click Yes.</span></span>
10. <span data-ttu-id="26efd-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="26efd-125">Close the page.</span></span>
11. <span data-ttu-id="26efd-126">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="26efd-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="26efd-127">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="26efd-127">Click Change view.</span></span>
13. <span data-ttu-id="26efd-128">Kattintson a Fejlécnézet gombra.</span><span class="sxs-lookup"><span data-stu-id="26efd-128">Click Header view.</span></span>
    * <span data-ttu-id="26efd-129">Ha egy rendelést megerősít, a Dokumentumállapot Visszaigazolás értékű lesz.</span><span class="sxs-lookup"><span data-stu-id="26efd-129">When an order is confirmed, the Document status is set to Confirmation.</span></span>  
14. <span data-ttu-id="26efd-130">A Művelet panelen kattintson az Értékesítés elemre.</span><span class="sxs-lookup"><span data-stu-id="26efd-130">On the Action Pane, click Sell.</span></span>
15. <span data-ttu-id="26efd-131">Kattintson az Értékesítési rendelés visszaigazolására.</span><span class="sxs-lookup"><span data-stu-id="26efd-131">Click Sales order confirmation.</span></span>
16. <span data-ttu-id="26efd-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="26efd-132">Close the page.</span></span>

## <a name="confirm-multiple-sales-orders-at-once"></a><span data-ttu-id="26efd-133">Több értékesítési rendelés egyszerre történő megerősítése</span><span class="sxs-lookup"><span data-stu-id="26efd-133">Confirm multiple sales orders at once</span></span>
1. <span data-ttu-id="26efd-134">Ugorjon az Értékesítés és marketing > Értékesítési rendelések > Értékesítés megerősítése > Értékesítési rendelés-visszaigazolás elemre.</span><span class="sxs-lookup"><span data-stu-id="26efd-134">Go to Sales and marketing > Sales orders > Order confirmation > Confirm sales order.</span></span>
2. <span data-ttu-id="26efd-135">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="26efd-135">Click Select.</span></span>
3. <span data-ttu-id="26efd-136">A Tartomány lap listáján keresse meg és válassza ki a rekordot, amely a Vevőfiók mezőre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="26efd-136">In the list on the Range tab, find and select the record that references the Customer account field.</span></span>
4. <span data-ttu-id="26efd-137">A Kritériumok mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="26efd-137">In the Criteria field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="26efd-138">A listában keresse meg és válassza ki a vevőfiókot, amelyben a tömegesen jóváhagyandó több rendelés található.</span><span class="sxs-lookup"><span data-stu-id="26efd-138">In the list, find and select the customer account that has multiple orders which you want to mass confirm.</span></span>
    * <span data-ttu-id="26efd-139">Az USMF használata esetén választhatja az „US-027” számlát.</span><span class="sxs-lookup"><span data-stu-id="26efd-139">If you’re using USMF, you can select account US-027.</span></span>  
6. <span data-ttu-id="26efd-140">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="26efd-140">Click OK.</span></span>
    * <span data-ttu-id="26efd-141">Az Áttekintés lapon a lekérdezési feltételeknek megfelelő rendelések listája jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="26efd-141">The Overview tab displays a list of the orders that match the query criteria.</span></span> <span data-ttu-id="26efd-142">Ezek a visszaigazolásban fognak szerepelni.</span><span class="sxs-lookup"><span data-stu-id="26efd-142">These will be included in the confirmation.</span></span>  
    * <span data-ttu-id="26efd-143">Az Összegző frissítés mező meghatározza azt a paramétert, amellyel több rendelés összegzése történik egy visszaigazoló dokumentumba.</span><span class="sxs-lookup"><span data-stu-id="26efd-143">The Summary update for field specifies the parameter by which multiple orders are to be summarized into one confirmation document.</span></span> <span data-ttu-id="26efd-144">Alapértelmezés szerint az opció a Kinnlevőségek paraméterei oldal összesítő frissítés beállítás alapértékeiből lesz átmásolva.</span><span class="sxs-lookup"><span data-stu-id="26efd-144">By default, the option is copied from the Default values for summary update setting on the Accounts receivable parameters page.</span></span>  
7. <span data-ttu-id="26efd-145">Az Összegzés frissítése mezőben válassza ki a Rendelés elemet.</span><span class="sxs-lookup"><span data-stu-id="26efd-145">In the Summary update for field, select 'Order'.</span></span>
    * <span data-ttu-id="26efd-146">Az összesítő frissítések létrehozásához szükséges minimális paraméterek a Számlafiók és a Pénznem.</span><span class="sxs-lookup"><span data-stu-id="26efd-146">The minimum parameters that are required to create summary updates are Invoice account and Currency.</span></span> <span data-ttu-id="26efd-147">Ez azt jelenti, hogy olyan összesítő frissítések nem megengedettek, amelyeknek eltérő a számlafiókjuk és a pénznemük.</span><span class="sxs-lookup"><span data-stu-id="26efd-147">This means that summary updates that have different invoice accounts and different currencies are not allowed.</span></span> <span data-ttu-id="26efd-148">Az Összesítő frissítések paramétereinek oldalán beállíthatók további paraméterek is, amely a Kinnlevőségek paraméterei oldalról érhető el.</span><span class="sxs-lookup"><span data-stu-id="26efd-148">Additional parameters can be set up in the Summary update parameters page which is accessible from the Accounts receivable parameters page.</span></span>  
8. <span data-ttu-id="26efd-149">Az Értékesítési rendelés mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="26efd-149">In the Sales order field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="26efd-150">A listában válassza ki a rendelésszámot, amely az összesítő rendelés lesz.</span><span class="sxs-lookup"><span data-stu-id="26efd-150">In the list, select the order number that you want to be the summary order.</span></span>
10. <span data-ttu-id="26efd-151">Kattintson az Elrendezésre.</span><span class="sxs-lookup"><span data-stu-id="26efd-151">Click Arrange.</span></span>
11. <span data-ttu-id="26efd-152">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="26efd-152">Click OK.</span></span>
12. <span data-ttu-id="26efd-153">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="26efd-153">Click OK.</span></span>


