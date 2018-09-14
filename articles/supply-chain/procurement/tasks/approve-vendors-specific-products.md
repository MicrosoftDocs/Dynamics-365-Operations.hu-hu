--- 
title: "A meghatározott termékek szállítójának jóváhagyása"
description: "Ez az eljárás bemutatja, hogy hogyan hagyhatja jóvá a szállítókat az adott termékre vonatkozóan."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 8f2cd1badb0b924150ab51ef2efc049e6666562a
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="approve-vendors-for-specific-products"></a><span data-ttu-id="b8d43-103">A meghatározott termékek szállítójának jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="b8d43-103">Approve vendors for specific products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b8d43-104">Ez az eljárás bemutatja, hogy hogyan hagyhatja jóvá a szállítókat az adott termékre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="b8d43-104">This procedure shows you how to approve vendors for specific products.</span></span> <span data-ttu-id="b8d43-105">Ez lehetővé teszi, hogy ellenőrizze, hogy mely szállítókat lehet használni akkor, amikor a termék hozzá van adva a beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="b8d43-105">This allows you to control which vendors can be used when the product is added to a purchase order.</span></span> <span data-ttu-id="b8d43-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="b8d43-106">You can use this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="b8d43-107">Általában ezt a feladatot egy Beszerzési vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="b8d43-107">This task would typically be carried out by a Purchasing manager.</span></span>

1. <span data-ttu-id="b8d43-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8d43-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="b8d43-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b8d43-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="b8d43-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b8d43-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="b8d43-111">Bontsa ki a Beszerzés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="b8d43-111">Expand the Purchase section.</span></span>
    * <span data-ttu-id="b8d43-112">Ha egy elsődleges szállító a szállítói mezőben látható, akkor engedélyezett szállítóként kell hozzáadnia ezt a szállítót az alábbiakban leírt lépésekben.</span><span class="sxs-lookup"><span data-stu-id="b8d43-112">If there is a primary vendor shown in the Vendor field, then you need to add this vendor as an approved vendor in the following steps.</span></span> <span data-ttu-id="b8d43-113">Jegyezze fel a szállító számát, ha legalább egy látható.</span><span class="sxs-lookup"><span data-stu-id="b8d43-113">Make a note of the vendor number, if one is shown.</span></span>  
5. <span data-ttu-id="b8d43-114">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="b8d43-114">On the Action Pane, click Purchase.</span></span>
6. <span data-ttu-id="b8d43-115">Kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="b8d43-115">Click Setup.</span></span>
7. <span data-ttu-id="b8d43-116">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="b8d43-116">Click Add.</span></span>
8. <span data-ttu-id="b8d43-117">A Szállító mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b8d43-117">In the Vendor field, enter or select a value.</span></span>
    * <span data-ttu-id="b8d43-118">Válassza ki a jóváhagyott szállítót.</span><span class="sxs-lookup"><span data-stu-id="b8d43-118">Select the approved vendor.</span></span> <span data-ttu-id="b8d43-119">Legalább egy sornak az elsődleges szállítónak kell lennie, amennyiben volt ilyen termékrekordban.</span><span class="sxs-lookup"><span data-stu-id="b8d43-119">At least one of the lines has to be the primary vendor if there was one in the product record.</span></span> <span data-ttu-id="b8d43-120">Ha korábban már létrehozta a szállító számának megjegyzését, válassza ki itt.</span><span class="sxs-lookup"><span data-stu-id="b8d43-120">If you made a note of the vendor number earlier, select it here.</span></span>  
9. <span data-ttu-id="b8d43-121">A Lejárat ideje mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-121">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="b8d43-122">Válasszon ki egy pár hónappal későbbi dátumot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-122">Choose a date a that is a few months ahead.</span></span>  
10. <span data-ttu-id="b8d43-123">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="b8d43-123">Click Add.</span></span>
11. <span data-ttu-id="b8d43-124">A Szállító mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b8d43-124">In the Vendor field, enter or select a value.</span></span>
12. <span data-ttu-id="b8d43-125">A Lejárat ideje mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-125">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="b8d43-126">Válasszon ki egy dátumot, amely nem ugyanaz, mint az előző lejárati dátumot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-126">Choose a date that is different than the previous expiration date.</span></span>  
13. <span data-ttu-id="b8d43-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-127">Close the page.</span></span>
14. <span data-ttu-id="b8d43-128">Kattintson az Engedélyezett szállítók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8d43-128">Click Approved vendors.</span></span>
15. <span data-ttu-id="b8d43-129">A Lejárat ideje mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-129">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="b8d43-130">Ez a dátum szűrőként működik, így láthatja egy bizonyos időpontig azokat a személyeket, akik engedélyezett szállítók.</span><span class="sxs-lookup"><span data-stu-id="b8d43-130">This date acts as a filter so you can see who the approved vendors are, up to a certain date.</span></span>  
16. <span data-ttu-id="b8d43-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-131">Close the page.</span></span>
17. <span data-ttu-id="b8d43-132">Kattintson az Érvényességi időszak lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8d43-132">Click Effective period.</span></span>
18. <span data-ttu-id="b8d43-133">A következő időpontig lejárt szállítók megjelenítése mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-133">In the Show vendors expired by field, enter a date.</span></span>
    * <span data-ttu-id="b8d43-134">Az oldal segítségével azonosíthatja a szállítókat, ahol bizonyos idő elteltével lejár a jóváhagyási állapota.</span><span class="sxs-lookup"><span data-stu-id="b8d43-134">You can use this page to identify vendors where the approval status will expire after a certain date.</span></span>  
19. <span data-ttu-id="b8d43-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-135">Close the page.</span></span>
20. <span data-ttu-id="b8d43-136">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8d43-136">Click Edit.</span></span>
21. <span data-ttu-id="b8d43-137">Az Engedélyezett szállítók ellenőrzési módszere mezőben adjon meg egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8d43-137">In the Approved vendor check method field, select an option.</span></span>
    * <span data-ttu-id="b8d43-138">Ezen mező segítségével válassza ki a házirendet arra vonatkozóan, hogy mi történjen, ha a termék hozzá van rendelve egy beszerzési rendeléssorhoz, ahol a szállító nem egy engedélyezett szállító.</span><span class="sxs-lookup"><span data-stu-id="b8d43-138">This field allows you to select the policy for what should happen if the product is added to a purchase order line where the vendor is not an approved vendor.</span></span>  
22. <span data-ttu-id="b8d43-139">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b8d43-139">Click Save.</span></span>
23. <span data-ttu-id="b8d43-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-140">Close the page.</span></span>
24. <span data-ttu-id="b8d43-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-141">Close the page.</span></span>
25. <span data-ttu-id="b8d43-142">Ugorjon a Beszerzés és forrás > Szállítók > Szállító/cikk-kapcsolatok > Jóváhagyott szállítók listája cikk szerint pontra.</span><span class="sxs-lookup"><span data-stu-id="b8d43-142">Go to Procurement and sourcing > Vendors > Vendor/item relations > Approved vendor list by item.</span></span>
    * <span data-ttu-id="b8d43-143">Ezen lapon áttekintést nyújt az összes termékről és engedélyezett szállítóról.</span><span class="sxs-lookup"><span data-stu-id="b8d43-143">This page gives you an overview of all products and the approved vendors.</span></span>  
26. <span data-ttu-id="b8d43-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-144">Close the page.</span></span>
27. <span data-ttu-id="b8d43-145">Ugrás a Beszerzés és forrás > Beszállítók > Minden szállító pontra.</span><span class="sxs-lookup"><span data-stu-id="b8d43-145">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
    * <span data-ttu-id="b8d43-146">A folyamatot kezdheti a szállítótól, majd ugorjon az engedélyezett termékek listájára a szállítói számlára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="b8d43-146">You can also start from a vendor and then go to the list of approved products for that vendor account.</span></span>  
28. <span data-ttu-id="b8d43-147">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b8d43-147">In the list, find and select the desired record.</span></span>
29. <span data-ttu-id="b8d43-148">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="b8d43-148">On the Action Pane, click Procurement.</span></span>
30. <span data-ttu-id="b8d43-149">Kattintson az Engedélyezett szállítók listája szállító szerint lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8d43-149">Click Approved vendor list by vendor.</span></span>
31. <span data-ttu-id="b8d43-150">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-150">Close the page.</span></span>
32. <span data-ttu-id="b8d43-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b8d43-151">Close the page.</span></span>


