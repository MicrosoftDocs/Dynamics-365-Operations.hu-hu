--- 
title: "Beszerzésirendelés-kiadás létrehozása beszerzési szerződésből"
description: "Ez az eljárás bemutatja, hogyan lehet használni egy beszerzési szerződést, amikor beszerzési rendelést hoz létre."
author: mkirknel
manager: AnnBe
ms.date: 12/04/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cecda03dd4d224d4319f2b0b196560389bb54195
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-release-order-from-a-purchase-agreement"></a><span data-ttu-id="42256-103">Beszerzésirendelés-kiadás létrehozása beszerzési szerződésből</span><span class="sxs-lookup"><span data-stu-id="42256-103">Create a purchase release order from a purchase agreement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="42256-104">Ez az eljárás bemutatja, hogyan lehet használni egy beszerzési szerződést, amikor beszerzési rendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="42256-104">This procedure shows how to use a purchase agreement when you create a purchase order.</span></span> <span data-ttu-id="42256-105">A beszerzési szerződést a beszerzési rendelés létrehozásakor kell alkalmazni, mivel az általános feltételeket át kell másolni a beszerzési rendelés fejlécébe.</span><span class="sxs-lookup"><span data-stu-id="42256-105">The purchase agreement has to be applied when you create the purchase order because there are general terms that should be copied to the purchase order header.</span></span> <span data-ttu-id="42256-106">Általában ez a feladatot egy beszerzési ügynök végzi el.</span><span class="sxs-lookup"><span data-stu-id="42256-106">Typically this task would be carried out by a purchasing agent.</span></span> <span data-ttu-id="42256-107">Az útmutató előfeltétele a szállító és a cikkek hatályos beszerzési megállapodása egy termékmennyiségi kötelezettséggel.</span><span class="sxs-lookup"><span data-stu-id="42256-107">As a prerequisite for this guide, you must have an effective purchase agreement with a product quantity commitment for a vendor and items.</span></span> <span data-ttu-id="42256-108">Ugyanezt az eljárást akkor is használhatja, ha a beszerzési szerződés más típusú kötelezettségvállalásokra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="42256-108">The same procedure can be used if you have a purchase agreement with other types of commitments.</span></span> <span data-ttu-id="42256-109">Ezt az útmutatót lefuttathatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="42256-109">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="42256-110">Az USMF használata esetén az útmutatóhoz szükséges előfeltételek beállításához futtathatja a „Beszerzési szerződés létrehozása” útmutatót.</span><span class="sxs-lookup"><span data-stu-id="42256-110">If you’re using USMF, you can run the “Create a purchase agreement” guide first to set up the necessary preconditions for this guide.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="42256-111">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="42256-111">Create a purchase order</span></span>
1. <span data-ttu-id="42256-112">Nyissa meg a Beszerzési rendelések előkészítési munkaterületét.</span><span class="sxs-lookup"><span data-stu-id="42256-112">Open the purchase order preparation workspace.</span></span>
2. <span data-ttu-id="42256-113">Kattintson az Új beszerzési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="42256-113">Click New purchase order.</span></span>
3. <span data-ttu-id="42256-114">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="42256-114">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="42256-115">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="42256-115">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="42256-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="42256-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="42256-117">Az Általános szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="42256-117">Toggle the expansion of the General section.</span></span>
7. <span data-ttu-id="42256-118">A Beszerzési szerződés mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="42256-118">In the Purchase agreement field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="42256-119">A szállítóhoz rendelt összes rendelkezésre álló megállapodás itt van felsorolva.</span><span class="sxs-lookup"><span data-stu-id="42256-119">All available agreements for the vendor are listed here.</span></span> <span data-ttu-id="42256-120">Keresse meg használni kívánt effektív megállapodást.</span><span class="sxs-lookup"><span data-stu-id="42256-120">Find the effective agreement that you want to use.</span></span>  
8. <span data-ttu-id="42256-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="42256-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="42256-122">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="42256-122">Click Yes.</span></span>
10. <span data-ttu-id="42256-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="42256-123">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="42256-124">Sor hozzáadása</span><span class="sxs-lookup"><span data-stu-id="42256-124">Add a line</span></span>
1. <span data-ttu-id="42256-125">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="42256-125">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="42256-126">Ha adott készlet vagy a helydimenziók vannak a kötelezettségvállaláson, akkor meg kell adni ugyanazokat az értékeket a beszerzésirendelés-soron a megállapodás használatához.</span><span class="sxs-lookup"><span data-stu-id="42256-126">If there are specific inventory or location dimensions on the commitment you must enter the same values on the purchase order line to make use of the agreement.</span></span>  
2. <span data-ttu-id="42256-127">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="42256-127">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="42256-128">A hely már ki lehet töltve az alapértelmezett értékekkel a rendelésből, vagy a szállítótól.</span><span class="sxs-lookup"><span data-stu-id="42256-128">The site may already be populated with the default value from the order, or from the vendor.</span></span> <span data-ttu-id="42256-129">Ha ez a helyzet, hagyja ki ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="42256-129">If this is the case, skip this step.</span></span>  
3. <span data-ttu-id="42256-130">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="42256-130">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="42256-131">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="42256-131">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="42256-132">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="42256-132">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="42256-133">Ellenőrizze, hogy az árat átmásolta-e a kötelezettségvállalásból.</span><span class="sxs-lookup"><span data-stu-id="42256-133">Validate that the price is copied from the commitment.</span></span>  

## <a name="look-up-the-commitment"></a><span data-ttu-id="42256-134">A kötelezettségvállalás megkeresése</span><span class="sxs-lookup"><span data-stu-id="42256-134">Look up the commitment</span></span>
1. <span data-ttu-id="42256-135">Kattintson a Sor frissítése elemre.</span><span class="sxs-lookup"><span data-stu-id="42256-135">Click Update line.</span></span>
2. <span data-ttu-id="42256-136">Kattintson a Csatolt elemre.</span><span class="sxs-lookup"><span data-stu-id="42256-136">Click Attached.</span></span>
    * <span data-ttu-id="42256-137">Itt kaphat részleteket a beszerzési szerződésről.</span><span class="sxs-lookup"><span data-stu-id="42256-137">Here you can get details for the purchase agreement.</span></span> <span data-ttu-id="42256-138">Például láthatja az árat, és azt, hogy az ár és engedmény rögzített-e, azaz ha az árat és az engedményt a beszerzési rendelésen egy másik értékre módosítja, mint a kötelezettségvállaláson, a rendszer eltávolítja a hivatkozást, hogy a beszerzésirendelés-sor ne feleljen meg a kötelezettségvállalásnak.</span><span class="sxs-lookup"><span data-stu-id="42256-138">For example, you can see the price and whether the price and discount are fixed, which means that if you change price or discount on the purchase order to a different value than on the commitment, the system will remove the link so the purchase order line does not fulfill the commitment.</span></span> <span data-ttu-id="42256-139">Látható az is, hogy a Maximum betartatása beállítás meg van-e adva, ami azt jelenti, hogy a kötelezettségvállaláson szereplő mennyiség nem lépheti túl a kötelezettségvállalást teljesítő beszerzések összegét.</span><span class="sxs-lookup"><span data-stu-id="42256-139">You can also see if the Max is enforced option is selected, which means that the quantity on the commitment cannot be exceeded by summing all of the purchases that fulfill the commitment.</span></span>  
3. <span data-ttu-id="42256-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42256-140">Close the page.</span></span>

## <a name="look-up-the-purchase-agreement"></a><span data-ttu-id="42256-141">Beszerzési szerződés megkeresése</span><span class="sxs-lookup"><span data-stu-id="42256-141">Look up the purchase agreement</span></span>
1. <span data-ttu-id="42256-142">A Művelet panelen kattintson az Általános elemre.</span><span class="sxs-lookup"><span data-stu-id="42256-142">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="42256-143">Kattintson a Beszerzési szerződés elemre.</span><span class="sxs-lookup"><span data-stu-id="42256-143">Click Purchase agreement.</span></span>
3. <span data-ttu-id="42256-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42256-144">Close the page.</span></span>
4. <span data-ttu-id="42256-145">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42256-145">Close the page.</span></span>

