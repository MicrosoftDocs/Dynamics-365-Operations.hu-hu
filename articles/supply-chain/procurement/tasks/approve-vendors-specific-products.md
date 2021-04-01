---
title: A meghatározott termékek szállítójának jóváhagyása
description: Ez az eljárás bemutatja, hogy hogyan hagyhatja jóvá a szállítókat az adott termékre vonatkozóan.
author: RichardLuan
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d08791caba34908903ce330df0f91e44fbdfcaea
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237275"
---
# <a name="approve-vendors-for-specific-products"></a><span data-ttu-id="ef924-103">A meghatározott termékek szállítójának jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="ef924-103">Approve vendors for specific products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ef924-104">Ez az eljárás bemutatja, hogy hogyan hagyhatja jóvá a szállítókat az adott termékre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="ef924-104">This procedure shows you how to approve vendors for specific products.</span></span> <span data-ttu-id="ef924-105">Ez lehetővé teszi, hogy ellenőrizze, hogy mely szállítókat lehet használni akkor, amikor a termék hozzá van adva a beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="ef924-105">This allows you to control which vendors can be used when the product is added to a purchase order.</span></span> <span data-ttu-id="ef924-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="ef924-106">You can use this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="ef924-107">Általában ezt a feladatot egy Beszerzési vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="ef924-107">This task would typically be carried out by a Purchasing manager.</span></span>

1. <span data-ttu-id="ef924-108">A Navigációs ablaktáblán ugorjon a **Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ef924-108">In Navigation Pane, go to **Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="ef924-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ef924-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ef924-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ef924-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ef924-111">Bontsa ki a **Vásárlás** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="ef924-111">Expand the **Purchase** fastTab.</span></span> <span data-ttu-id="ef924-112">Ha egy elsődleges szállító a **Szállító** mezőben látható, akkor engedélyezett szállítóként kell hozzáadnia ezt a szállítót az alábbiakban leírt lépésekben.</span><span class="sxs-lookup"><span data-stu-id="ef924-112">If there is a primary vendor shown in the **Vendor** field, then you need to add this vendor as an approved vendor in the following steps.</span></span> <span data-ttu-id="ef924-113">Jegyezze fel a szállító számát, ha legalább egy látható.</span><span class="sxs-lookup"><span data-stu-id="ef924-113">Make a note of the vendor number, if one is shown.</span></span>  
5. <span data-ttu-id="ef924-114">A Művelet panelen kattintson a **Beszerzés** elemre.</span><span class="sxs-lookup"><span data-stu-id="ef924-114">On the Action Pane, click **Purchase**.</span></span>
6. <span data-ttu-id="ef924-115">Kattintson a **Beállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="ef924-115">Click **Setup**.</span></span>
7. <span data-ttu-id="ef924-116">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="ef924-116">Click **Add**.</span></span>
8. <span data-ttu-id="ef924-117">A Szállító mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ef924-117">In the Vendor field, enter or select a value.</span></span> <span data-ttu-id="ef924-118">Válassza ki a jóváhagyott szállítót.</span><span class="sxs-lookup"><span data-stu-id="ef924-118">Select the approved vendor.</span></span> <span data-ttu-id="ef924-119">Legalább egy sornak az elsődleges szállítónak kell lennie, amennyiben volt ilyen termékrekordban.</span><span class="sxs-lookup"><span data-stu-id="ef924-119">At least one of the lines has to be the primary vendor if there was one in the product record.</span></span> <span data-ttu-id="ef924-120">Ha korábban már létrehozta a szállító számának megjegyzését, válassza ki itt.</span><span class="sxs-lookup"><span data-stu-id="ef924-120">If you made a note of the vendor number earlier, select it here.</span></span>  
9. <span data-ttu-id="ef924-121">A **Lejárat ideje** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="ef924-121">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="ef924-122">Válasszon ki egy pár hónappal későbbi dátumot.</span><span class="sxs-lookup"><span data-stu-id="ef924-122">Choose a date a that is a few months ahead.</span></span>  
10. <span data-ttu-id="ef924-123">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="ef924-123">Click **Add**.</span></span>
11. <span data-ttu-id="ef924-124">A **Szállító** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ef924-124">In the **Vendor** field, enter or select a value.</span></span>
12. <span data-ttu-id="ef924-125">A **Lejárat ideje** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="ef924-125">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="ef924-126">Válasszon ki egy dátumot, amely nem ugyanaz, mint az előző lejárati dátumot.</span><span class="sxs-lookup"><span data-stu-id="ef924-126">Choose a date that is different than the previous expiration date.</span></span>  
13. <span data-ttu-id="ef924-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ef924-127">Close the page.</span></span>
14. <span data-ttu-id="ef924-128">A Művelet panelen kattintson a **Jóváhagyott beszállítók** elemre.</span><span class="sxs-lookup"><span data-stu-id="ef924-128">On the Action Pane, click **Approved vendors**.</span></span>
15. <span data-ttu-id="ef924-129">A **Lejárat ideje** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="ef924-129">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="ef924-130">Ez a dátum szűrőként működik, így láthatja egy bizonyos időpontig azokat a személyeket, akik engedélyezett szállítók.</span><span class="sxs-lookup"><span data-stu-id="ef924-130">This date acts as a filter so you can see who the approved vendors are, up to a certain date.</span></span>  
16. <span data-ttu-id="ef924-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ef924-131">Close the page.</span></span>
17. <span data-ttu-id="ef924-132">A Művelet panelen kattintson **Hatályosság időszaka** elemre.</span><span class="sxs-lookup"><span data-stu-id="ef924-132">On the Action Pane, click **Effective period**.</span></span>
18. <span data-ttu-id="ef924-133">A **Következő időpontig lejárt szállítók megjelenítése** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="ef924-133">In the **Show vendors expired by** field, enter a date.</span></span> <span data-ttu-id="ef924-134">Az oldal segítségével azonosíthatja a szállítókat, ahol bizonyos idő elteltével lejár a jóváhagyási állapota.</span><span class="sxs-lookup"><span data-stu-id="ef924-134">You can use this page to identify vendors where the approval status will expire after a certain date.</span></span>  
19. <span data-ttu-id="ef924-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ef924-135">Close the page.</span></span>
20. <span data-ttu-id="ef924-136">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ef924-136">Click **Edit**.</span></span>
21. <span data-ttu-id="ef924-137">Az **Engedélyezett szállítók ellenőrzési módszere** mezőben adjon meg egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ef924-137">In the **Approved vendor check method** field, select an option.</span></span> <span data-ttu-id="ef924-138">Ezen mező segítségével válassza ki a házirendet arra vonatkozóan, hogy mi történjen, ha a termék hozzá van rendelve egy beszerzési rendeléssorhoz, ahol a szállító nem egy engedélyezett szállító.</span><span class="sxs-lookup"><span data-stu-id="ef924-138">This field allows you to select the policy for what should happen if the product is added to a purchase order line where the vendor is not an approved vendor.</span></span>  
22. <span data-ttu-id="ef924-139">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="ef924-139">Click **Save**.</span></span>
23. <span data-ttu-id="ef924-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ef924-140">Close the page.</span></span>
24. <span data-ttu-id="ef924-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ef924-141">Close the page.</span></span>
25. <span data-ttu-id="ef924-142">A Navigációs panelen Ugorjon a **Modulok > Beszerzés és forrás > Szállítók > Szállító/cikk-kapcsolatok > Jóváhagyott szállítók listája cikk szerint** pontra.</span><span class="sxs-lookup"><span data-stu-id="ef924-142">In Navigation Pane, go to **Modules > Procurement and sourcing > Vendors > Vendor/item relations > Approved vendor list by item**.</span></span> <span data-ttu-id="ef924-143">Ezen lapon áttekintést nyújt az összes termékről és engedélyezett szállítóról.</span><span class="sxs-lookup"><span data-stu-id="ef924-143">This page gives you an overview of all products and the approved vendors.</span></span>  
26. <span data-ttu-id="ef924-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ef924-144">Close the page.</span></span>
27. <span data-ttu-id="ef924-145">A Navigációs ablaktáblán válasssza a **Modulok > Beszerzés és forrás > Szállítók > Összes beszállító** menübe.</span><span class="sxs-lookup"><span data-stu-id="ef924-145">In Navigation Pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span> <span data-ttu-id="ef924-146">A folyamatot kezdheti a szállítótól, majd ugorjon az engedélyezett termékek listájára a szállítói számlára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="ef924-146">You can also start from a vendor and then go to the list of approved products for that vendor account.</span></span>  
28. <span data-ttu-id="ef924-147">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ef924-147">In the list, find and select the desired record.</span></span>
29. <span data-ttu-id="ef924-148">A Művelet panelen kattintson a **Beszerzés** elemre.</span><span class="sxs-lookup"><span data-stu-id="ef924-148">On the Action Pane, click **Procurement**.</span></span>
30. <span data-ttu-id="ef924-149">Kattintson az **Engedélyezett szállítók listája szállító szerint** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ef924-149">Click **Approved vendor list by vendor**.</span></span>
31. <span data-ttu-id="ef924-150">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ef924-150">Close the page.</span></span>
32. <span data-ttu-id="ef924-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ef924-151">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]