---
title: A meghatározott termékek szállítójának jóváhagyása
description: Ez az eljárás bemutatja, hogy hogyan hagyhatja jóvá a szállítókat az adott termékre vonatkozóan.
author: kamaybac
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45f6942c99e03a5abf6de736f1adb0b4e232783f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812494"
---
# <a name="approve-vendors-for-specific-products"></a><span data-ttu-id="7566b-103">A meghatározott termékek szállítójának jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="7566b-103">Approve vendors for specific products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7566b-104">Ez az eljárás bemutatja, hogy hogyan hagyhatja jóvá a szállítókat az adott termékre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="7566b-104">This procedure shows you how to approve vendors for specific products.</span></span> <span data-ttu-id="7566b-105">Ez lehetővé teszi, hogy ellenőrizze, hogy mely szállítókat lehet használni akkor, amikor a termék hozzá van adva a beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="7566b-105">This allows you to control which vendors can be used when the product is added to a purchase order.</span></span> <span data-ttu-id="7566b-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="7566b-106">You can use this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="7566b-107">Általában ezt a feladatot egy Beszerzési vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="7566b-107">This task would typically be carried out by a Purchasing manager.</span></span>

1. <span data-ttu-id="7566b-108">A Navigációs ablaktáblán ugorjon a **Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7566b-108">In Navigation Pane, go to **Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="7566b-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7566b-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7566b-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7566b-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7566b-111">Bontsa ki a **Vásárlás** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="7566b-111">Expand the **Purchase** fastTab.</span></span> <span data-ttu-id="7566b-112">Ha egy elsődleges szállító a **Szállító** mezőben látható, akkor engedélyezett szállítóként kell hozzáadnia ezt a szállítót az alábbiakban leírt lépésekben.</span><span class="sxs-lookup"><span data-stu-id="7566b-112">If there is a primary vendor shown in the **Vendor** field, then you need to add this vendor as an approved vendor in the following steps.</span></span> <span data-ttu-id="7566b-113">Jegyezze fel a szállító számát, ha legalább egy látható.</span><span class="sxs-lookup"><span data-stu-id="7566b-113">Make a note of the vendor number, if one is shown.</span></span>  
5. <span data-ttu-id="7566b-114">A Művelet panelen kattintson a **Beszerzés** elemre.</span><span class="sxs-lookup"><span data-stu-id="7566b-114">On the Action Pane, click **Purchase**.</span></span>
6. <span data-ttu-id="7566b-115">Kattintson a **Beállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="7566b-115">Click **Setup**.</span></span>
7. <span data-ttu-id="7566b-116">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="7566b-116">Click **Add**.</span></span>
8. <span data-ttu-id="7566b-117">A Szállító mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7566b-117">In the Vendor field, enter or select a value.</span></span> <span data-ttu-id="7566b-118">Válassza ki a jóváhagyott szállítót.</span><span class="sxs-lookup"><span data-stu-id="7566b-118">Select the approved vendor.</span></span> <span data-ttu-id="7566b-119">Legalább egy sornak az elsődleges szállítónak kell lennie, amennyiben volt ilyen termékrekordban.</span><span class="sxs-lookup"><span data-stu-id="7566b-119">At least one of the lines has to be the primary vendor if there was one in the product record.</span></span> <span data-ttu-id="7566b-120">Ha korábban már létrehozta a szállító számának megjegyzését, válassza ki itt.</span><span class="sxs-lookup"><span data-stu-id="7566b-120">If you made a note of the vendor number earlier, select it here.</span></span>  
9. <span data-ttu-id="7566b-121">A **Lejárat ideje** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="7566b-121">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="7566b-122">Válasszon ki egy pár hónappal későbbi dátumot.</span><span class="sxs-lookup"><span data-stu-id="7566b-122">Choose a date a that is a few months ahead.</span></span>  
10. <span data-ttu-id="7566b-123">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="7566b-123">Click **Add**.</span></span>
11. <span data-ttu-id="7566b-124">A **Szállító** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7566b-124">In the **Vendor** field, enter or select a value.</span></span>
12. <span data-ttu-id="7566b-125">A **Lejárat ideje** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="7566b-125">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="7566b-126">Válasszon ki egy dátumot, amely nem ugyanaz, mint az előző lejárati dátumot.</span><span class="sxs-lookup"><span data-stu-id="7566b-126">Choose a date that is different than the previous expiration date.</span></span>  
13. <span data-ttu-id="7566b-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7566b-127">Close the page.</span></span>
14. <span data-ttu-id="7566b-128">A Művelet panelen kattintson a **Jóváhagyott beszállítók** elemre.</span><span class="sxs-lookup"><span data-stu-id="7566b-128">On the Action Pane, click **Approved vendors**.</span></span>
15. <span data-ttu-id="7566b-129">A **Lejárat ideje** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="7566b-129">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="7566b-130">Ez a dátum szűrőként működik, így láthatja egy bizonyos időpontig azokat a személyeket, akik engedélyezett szállítók.</span><span class="sxs-lookup"><span data-stu-id="7566b-130">This date acts as a filter so you can see who the approved vendors are, up to a certain date.</span></span>  
16. <span data-ttu-id="7566b-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7566b-131">Close the page.</span></span>
17. <span data-ttu-id="7566b-132">A Művelet panelen kattintson **Hatályosság időszaka** elemre.</span><span class="sxs-lookup"><span data-stu-id="7566b-132">On the Action Pane, click **Effective period**.</span></span>
18. <span data-ttu-id="7566b-133">A **Következő időpontig lejárt szállítók megjelenítése** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="7566b-133">In the **Show vendors expired by** field, enter a date.</span></span> <span data-ttu-id="7566b-134">Az oldal segítségével azonosíthatja a szállítókat, ahol bizonyos idő elteltével lejár a jóváhagyási állapota.</span><span class="sxs-lookup"><span data-stu-id="7566b-134">You can use this page to identify vendors where the approval status will expire after a certain date.</span></span>  
19. <span data-ttu-id="7566b-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7566b-135">Close the page.</span></span>
20. <span data-ttu-id="7566b-136">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7566b-136">Click **Edit**.</span></span>
21. <span data-ttu-id="7566b-137">Az **Engedélyezett szállítók ellenőrzési módszere** mezőben adjon meg egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7566b-137">In the **Approved vendor check method** field, select an option.</span></span> <span data-ttu-id="7566b-138">Ezen mező segítségével válassza ki a házirendet arra vonatkozóan, hogy mi történjen, ha a termék hozzá van rendelve egy beszerzési rendeléssorhoz, ahol a szállító nem egy engedélyezett szállító.</span><span class="sxs-lookup"><span data-stu-id="7566b-138">This field allows you to select the policy for what should happen if the product is added to a purchase order line where the vendor is not an approved vendor.</span></span>  
22. <span data-ttu-id="7566b-139">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="7566b-139">Click **Save**.</span></span>
23. <span data-ttu-id="7566b-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7566b-140">Close the page.</span></span>
24. <span data-ttu-id="7566b-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7566b-141">Close the page.</span></span>
25. <span data-ttu-id="7566b-142">A Navigációs panelen Ugorjon a **Modulok > Beszerzés és forrás > Szállítók > Szállító/cikk-kapcsolatok > Jóváhagyott szállítók listája cikk szerint** pontra.</span><span class="sxs-lookup"><span data-stu-id="7566b-142">In Navigation Pane, go to **Modules > Procurement and sourcing > Vendors > Vendor/item relations > Approved vendor list by item**.</span></span> <span data-ttu-id="7566b-143">Ezen lapon áttekintést nyújt az összes termékről és engedélyezett szállítóról.</span><span class="sxs-lookup"><span data-stu-id="7566b-143">This page gives you an overview of all products and the approved vendors.</span></span>  
26. <span data-ttu-id="7566b-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7566b-144">Close the page.</span></span>
27. <span data-ttu-id="7566b-145">A Navigációs ablaktáblán válasssza a **Modulok > Beszerzés és forrás > Szállítók > Összes beszállító** menübe.</span><span class="sxs-lookup"><span data-stu-id="7566b-145">In Navigation Pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span> <span data-ttu-id="7566b-146">A folyamatot kezdheti a szállítótól, majd ugorjon az engedélyezett termékek listájára a szállítói számlára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="7566b-146">You can also start from a vendor and then go to the list of approved products for that vendor account.</span></span>  
28. <span data-ttu-id="7566b-147">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7566b-147">In the list, find and select the desired record.</span></span>
29. <span data-ttu-id="7566b-148">A Művelet panelen kattintson a **Beszerzés** elemre.</span><span class="sxs-lookup"><span data-stu-id="7566b-148">On the Action Pane, click **Procurement**.</span></span>
30. <span data-ttu-id="7566b-149">Kattintson az **Engedélyezett szállítók listája szállító szerint** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7566b-149">Click **Approved vendor list by vendor**.</span></span>
31. <span data-ttu-id="7566b-150">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7566b-150">Close the page.</span></span>
32. <span data-ttu-id="7566b-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7566b-151">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]