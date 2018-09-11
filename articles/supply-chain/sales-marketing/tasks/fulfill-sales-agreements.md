--- 
title: "Értékesítési szerződések teljesítése"
description: "Ez az eljárás bemutatja, hogyan lehet teljesíteni egy értékesítési szerződés értékesítési rendelések hozzárendelésével."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: e257f04746c0ce9255c14eecff4244b2ea4cd98a
ms.contentlocale: hu-hu
ms.lasthandoff: 09/11/2018

---
# <a name="fulfill-sales-agreements"></a><span data-ttu-id="2ba8f-103">Értékesítési szerződések teljesítése</span><span class="sxs-lookup"><span data-stu-id="2ba8f-103">Fulfill sales agreements</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2ba8f-104">Ez az eljárás bemutatja, hogyan lehet teljesíteni egy értékesítési szerződés értékesítési rendelések hozzárendelésével.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-104">This procedure shows you how to fulfill a sales agreement by associating sales orders with it.</span></span> <span data-ttu-id="2ba8f-105">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="2ba8f-106">Az útmutató megkezdése előtt ellenőrizze, hogy rendelkezik-e érvényes „Termékértékére vonatkozó kötelezettség” típusú értékesítési szerződéssel.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-106">Before starting this guide, make sure you have an effective sales agreement of type "Product value commitment".</span></span> <span data-ttu-id="2ba8f-107">Azt is megteheti, hogy futtathatja az „Értékesítési szerződések létrehozása" nevű feladatútmutatót.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-107">Alternatively, you can run the task guide called "Create sales agreements".</span></span>  




## <a name="release-a-sales-order-from-the-agreement"></a><span data-ttu-id="2ba8f-108">Értékesítési rendelés kiadása a szerződésből</span><span class="sxs-lookup"><span data-stu-id="2ba8f-108">Release a sales order from the agreement</span></span>
1. <span data-ttu-id="2ba8f-109">Lépjen az Értékesítés és marketing > Értékesítési szerződések > Értékesítési szerződések menüpontba.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-109">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="2ba8f-110">Nyissa meg a listában a szerződést, amelyben ellenében ki szeretné adni a rendelést.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-110">In the list, open the agreement against which you want to release the order.</span></span>
3. <span data-ttu-id="2ba8f-111">A Művelet panelen kattintson az Értékesítési szerződés elemre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-111">On the Action Pane, click Sales agreement.</span></span>
4. <span data-ttu-id="2ba8f-112">Kattintson a Rendelés kiadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-112">Click Release order.</span></span>
    * <span data-ttu-id="2ba8f-113">Ahogy a Kiadási rendelés létrehozása lap tetején lévő szöveg is kiemeli, az értékesítési-sorokhoz szükséges részletek eltérők lesznek attól függően, hogy a szerződés mennyiség- vagy értékalapú?</span><span class="sxs-lookup"><span data-stu-id="2ba8f-113">As the text on top of the  Create release order page points out, the details required for the sales order lines will differ depending on whether the agreement is quantity- or value-based.</span></span>  
    * <span data-ttu-id="2ba8f-114">Ez az útmutató a „Termékérték-kötelezettség” típusú szerződést használ.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-114">The agreement in this guide is of type "Product value commitment".</span></span> <span data-ttu-id="2ba8f-115">Ez az oka annak, hogy a lap Sorok szakasza üres.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-115">This is why the Lines section of this page is blank.</span></span> <span data-ttu-id="2ba8f-116">Ha kötelezettség mennyiségalapú lenne, a soradatok a megállapodásból lennének átmásolva.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-116">If the commitment was based on quantity, the line information would be copied from the agreement.</span></span>  
5. <span data-ttu-id="2ba8f-117">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-117">Click Create.</span></span>
    * <span data-ttu-id="2ba8f-118">Az üzenet tájékoztat arról, hogy az értékesítési rendelés létrehozása megtörtént.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-118">The message informs you that a sales order has been created.</span></span> <span data-ttu-id="2ba8f-119">Mivel a rendelés nem tartalmaz sorokat, rendeléssor-adatokat kell hozzáadni a kiadási folyamat befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-119">Since the order does not contain any lines, you must add order line details to complete the release process.</span></span>   
6. <span data-ttu-id="2ba8f-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-120">Close the page.</span></span>
7. <span data-ttu-id="2ba8f-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-121">Close the page.</span></span>
8. <span data-ttu-id="2ba8f-122">Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-122">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
9. <span data-ttu-id="2ba8f-123">A listában keresse meg és nyissa meg a rendelést, amely az előző feladat rendeléskiadása következtében jött létre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-123">In the list, find and open the order that was created as the result of the order release in the previous task.</span></span>
10. <span data-ttu-id="2ba8f-124">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-124">Click Add line.</span></span>
11. <span data-ttu-id="2ba8f-125">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-125">In the Item number field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="2ba8f-126">A Cikkszám mezőben írja be vagy válassza ki a cikket, amely a társított értékesítési szerződésen meg van adva.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-126">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
13. <span data-ttu-id="2ba8f-127">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="2ba8f-128">Győződjön meg arról, hogy olyan mennyiséget írjon be, amely a nettó összeget a hozzárendelt értékesítési megállapodás értéke alá viszi.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-128">Make sure that you enter a quantity that brings the Net amount under the value of the associated sales agreement.</span></span>  
    * <span data-ttu-id="2ba8f-129">Figyelje meg, hogy mivel az értékesítési rendelés a szerződéshez kapcsolódik, a letárgyalt kedvezményszázalék módosítja a rendelési sort.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-129">Notice that because the sales order is linked to the agreement, the negotiated discount percent is applied to the order line.</span></span>  
14. <span data-ttu-id="2ba8f-130">Kattintson a Sor frissítése elemre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-130">Click Update line.</span></span>
15. <span data-ttu-id="2ba8f-131">Kattintson a Csatolt elemre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-131">Click Attached.</span></span>
    * <span data-ttu-id="2ba8f-132">A Csatolt szerződés lap mutatja azon szerződés azonosítóját és feltételeit, amelyből a sor ki lett adva.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-132">The Attached agreement page shows the ID and terms of the agreement from which the line is released.</span></span>  
16. <span data-ttu-id="2ba8f-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-133">Close the page.</span></span>
17. <span data-ttu-id="2ba8f-134">A Művelet panelen kattintson az Általános elemre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-134">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="2ba8f-135">Kattintson a Csatolt értékesítési szerződés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-135">Click Attached sales agreement.</span></span>
19. <span data-ttu-id="2ba8f-136">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-136">Expand the Line details section.</span></span>
20. <span data-ttu-id="2ba8f-137">Kattintson a Teljesítés fülre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-137">Click the Fulfillment tab.</span></span>
    * <span data-ttu-id="2ba8f-138">A Teljesítés lap összegzi az összes értékesítésirendelés-sort, amely hozzá van rendelve ehhez a kötelezettséghez, valamint a teljesítési állapotukat és a még ki nem adott összeget vagy mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-138">The Fulfillment tab shows a summary of all the sales order lines that are associated with this commitment, and their fulfillment state, as well as the amount or quantity that has not yet been released.</span></span>   
21. <span data-ttu-id="2ba8f-139">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-139">Close the page.</span></span>
22. <span data-ttu-id="2ba8f-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-140">Close the page.</span></span>
23. <span data-ttu-id="2ba8f-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-141">Close the page.</span></span>

## <a name="apply-sales-agreement-in-the-order-process"></a><span data-ttu-id="2ba8f-142">Értékesítési szerződés használata a rendelési folyamatban</span><span class="sxs-lookup"><span data-stu-id="2ba8f-142">Apply sales agreement in the order process</span></span>
1. <span data-ttu-id="2ba8f-143">Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-143">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="2ba8f-144">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-144">Click New.</span></span>
3. <span data-ttu-id="2ba8f-145">A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-145">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="2ba8f-146">A listában keresse meg és válassza ki az értékesítési szerződésen megadott vevőt.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-146">In the list, find and select the customer specified on the sales agreement.</span></span>
5. <span data-ttu-id="2ba8f-147">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-147">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2ba8f-148">Bontsa ki az Általános szakaszt.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-148">Expand the General section.</span></span>
7. <span data-ttu-id="2ba8f-149">Az Értékesítési szerződés azonosítója mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-149">In the Sales agreement ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="2ba8f-150">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-150">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2ba8f-151">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-151">Click Yes.</span></span>
10. <span data-ttu-id="2ba8f-152">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-152">Click OK.</span></span>
11. <span data-ttu-id="2ba8f-153">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-153">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="2ba8f-154">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-154">In the Item number field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="2ba8f-155">A Cikkszám mezőben írja be vagy válassza ki a cikket, amely a társított értékesítési szerződésen meg van adva.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-155">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
14. <span data-ttu-id="2ba8f-156">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-156">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="2ba8f-157">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-157">Click Save.</span></span>
16. <span data-ttu-id="2ba8f-158">A Művelet panelen kattintson a Kitárolás és csomagolás elemre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-158">On the Action Pane, click Pick and pack.</span></span>
17. <span data-ttu-id="2ba8f-159">Kattintson A szállítólevél feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-159">Click Post packing slip.</span></span>
18. <span data-ttu-id="2ba8f-160">Bontsa ki a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-160">Expand the Parameters section.</span></span>
19. <span data-ttu-id="2ba8f-161">Válassza ki az Igen lehetőséget a Feladás mezőben.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-161">Select Yes in the Posting field.</span></span>
20. <span data-ttu-id="2ba8f-162">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-162">Click OK.</span></span>
21. <span data-ttu-id="2ba8f-163">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-163">Click OK.</span></span>
22. <span data-ttu-id="2ba8f-164">A Művelet panelen kattintson az Általános elemre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-164">On the Action Pane, click General.</span></span>
23. <span data-ttu-id="2ba8f-165">Kattintson a Csatolt értékesítési szerződés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-165">Click Attached sales agreement.</span></span>
24. <span data-ttu-id="2ba8f-166">Kattintson a Teljesítés fülre.</span><span class="sxs-lookup"><span data-stu-id="2ba8f-166">Click the Fulfillment tab.</span></span>


