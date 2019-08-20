---
title: Értékesítési szerződések teljesítése
description: Ez az eljárás bemutatja, hogyan lehet teljesíteni egy értékesítési szerződés értékesítési rendelések hozzárendelésével.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7549d0c2a3cfa0feb26a641bbc41702b4b21158
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1833954"
---
# <a name="fulfill-sales-agreements"></a><span data-ttu-id="eb44a-103">Értékesítési szerződések teljesítése</span><span class="sxs-lookup"><span data-stu-id="eb44a-103">Fulfill sales agreements</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eb44a-104">Ez az eljárás bemutatja, hogyan lehet teljesíteni egy értékesítési szerződés értékesítési rendelések hozzárendelésével.</span><span class="sxs-lookup"><span data-stu-id="eb44a-104">This procedure shows you how to fulfill a sales agreement by associating sales orders with it.</span></span> <span data-ttu-id="eb44a-105">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="eb44a-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="eb44a-106">Az útmutató megkezdése előtt ellenőrizze, hogy rendelkezik-e érvényes „Termékértékére vonatkozó kötelezettség” típusú értékesítési szerződéssel.</span><span class="sxs-lookup"><span data-stu-id="eb44a-106">Before starting this guide, make sure you have an effective sales agreement of type "Product value commitment".</span></span> <span data-ttu-id="eb44a-107">Azt is megteheti, hogy futtathatja az „Értékesítési szerződések létrehozása" nevű feladatútmutatót.</span><span class="sxs-lookup"><span data-stu-id="eb44a-107">Alternatively, you can run the task guide called "Create sales agreements".</span></span>  




## <a name="release-a-sales-order-from-the-agreement"></a><span data-ttu-id="eb44a-108">Értékesítési rendelés kiadása a szerződésből</span><span class="sxs-lookup"><span data-stu-id="eb44a-108">Release a sales order from the agreement</span></span>
1. <span data-ttu-id="eb44a-109">Lépjen az Értékesítés és marketing > Értékesítési szerződések > Értékesítési szerződések menüpontba.</span><span class="sxs-lookup"><span data-stu-id="eb44a-109">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="eb44a-110">Nyissa meg a listában a szerződést, amelyben ellenében ki szeretné adni a rendelést.</span><span class="sxs-lookup"><span data-stu-id="eb44a-110">In the list, open the agreement against which you want to release the order.</span></span>
3. <span data-ttu-id="eb44a-111">A Művelet panelen kattintson az Értékesítési szerződés elemre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-111">On the Action Pane, click Sales agreement.</span></span>
4. <span data-ttu-id="eb44a-112">Kattintson a Rendelés kiadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-112">Click Release order.</span></span>
    * <span data-ttu-id="eb44a-113">Ahogy a Kiadási rendelés létrehozása lap tetején lévő szöveg is kiemeli, az értékesítési-sorokhoz szükséges részletek eltérők lesznek attól függően, hogy a szerződés mennyiség- vagy értékalapú?</span><span class="sxs-lookup"><span data-stu-id="eb44a-113">As the text on top of the  Create release order page points out, the details required for the sales order lines will differ depending on whether the agreement is quantity- or value-based.</span></span>  
    * <span data-ttu-id="eb44a-114">Ez az útmutató a „Termékérték-kötelezettség” típusú szerződést használ.</span><span class="sxs-lookup"><span data-stu-id="eb44a-114">The agreement in this guide is of type "Product value commitment".</span></span> <span data-ttu-id="eb44a-115">Ez az oka annak, hogy a lap Sorok szakasza üres.</span><span class="sxs-lookup"><span data-stu-id="eb44a-115">This is why the Lines section of this page is blank.</span></span> <span data-ttu-id="eb44a-116">Ha kötelezettség mennyiségalapú lenne, a soradatok a megállapodásból lennének átmásolva.</span><span class="sxs-lookup"><span data-stu-id="eb44a-116">If the commitment was based on quantity, the line information would be copied from the agreement.</span></span>  
5. <span data-ttu-id="eb44a-117">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-117">Click Create.</span></span>
    * <span data-ttu-id="eb44a-118">Az üzenet tájékoztat arról, hogy az értékesítési rendelés létrehozása megtörtént.</span><span class="sxs-lookup"><span data-stu-id="eb44a-118">The message informs you that a sales order has been created.</span></span> <span data-ttu-id="eb44a-119">Mivel a rendelés nem tartalmaz sorokat, rendeléssor-adatokat kell hozzáadni a kiadási folyamat befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="eb44a-119">Since the order does not contain any lines, you must add order line details to complete the release process.</span></span>   
6. <span data-ttu-id="eb44a-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eb44a-120">Close the page.</span></span>
7. <span data-ttu-id="eb44a-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eb44a-121">Close the page.</span></span>
8. <span data-ttu-id="eb44a-122">Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="eb44a-122">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
9. <span data-ttu-id="eb44a-123">A listában keresse meg és nyissa meg a rendelést, amely az előző feladat rendeléskiadása következtében jött létre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-123">In the list, find and open the order that was created as the result of the order release in the previous task.</span></span>
10. <span data-ttu-id="eb44a-124">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="eb44a-124">Click Add line.</span></span>
11. <span data-ttu-id="eb44a-125">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="eb44a-125">In the Item number field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="eb44a-126">A Cikkszám mezőben írja be vagy válassza ki a cikket, amely a társított értékesítési szerződésen meg van adva.</span><span class="sxs-lookup"><span data-stu-id="eb44a-126">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
13. <span data-ttu-id="eb44a-127">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="eb44a-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="eb44a-128">Győződjön meg arról, hogy olyan mennyiséget írjon be, amely a nettó összeget a hozzárendelt értékesítési megállapodás értéke alá viszi.</span><span class="sxs-lookup"><span data-stu-id="eb44a-128">Make sure that you enter a quantity that brings the Net amount under the value of the associated sales agreement.</span></span>  
    * <span data-ttu-id="eb44a-129">Figyelje meg, hogy mivel az értékesítési rendelés a szerződéshez kapcsolódik, a letárgyalt kedvezményszázalék módosítja a rendelési sort.</span><span class="sxs-lookup"><span data-stu-id="eb44a-129">Notice that because the sales order is linked to the agreement, the negotiated discount percent is applied to the order line.</span></span>  
14. <span data-ttu-id="eb44a-130">Kattintson a Sor frissítése elemre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-130">Click Update line.</span></span>
15. <span data-ttu-id="eb44a-131">Kattintson a Csatolt elemre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-131">Click Attached.</span></span>
    * <span data-ttu-id="eb44a-132">A Csatolt szerződés lap mutatja azon szerződés azonosítóját és feltételeit, amelyből a sor ki lett adva.</span><span class="sxs-lookup"><span data-stu-id="eb44a-132">The Attached agreement page shows the ID and terms of the agreement from which the line is released.</span></span>  
16. <span data-ttu-id="eb44a-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eb44a-133">Close the page.</span></span>
17. <span data-ttu-id="eb44a-134">A Művelet panelen kattintson az Általános elemre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-134">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="eb44a-135">Kattintson a Csatolt értékesítési szerződés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-135">Click Attached sales agreement.</span></span>
19. <span data-ttu-id="eb44a-136">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="eb44a-136">Expand the Line details section.</span></span>
20. <span data-ttu-id="eb44a-137">Kattintson a Teljesítés fülre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-137">Click the Fulfillment tab.</span></span>
    * <span data-ttu-id="eb44a-138">A Teljesítés lap összegzi az összes értékesítésirendelés-sort, amely hozzá van rendelve ehhez a kötelezettséghez, valamint a teljesítési állapotukat és a még ki nem adott összeget vagy mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="eb44a-138">The Fulfillment tab shows a summary of all the sales order lines that are associated with this commitment, and their fulfillment state, as well as the amount or quantity that has not yet been released.</span></span>   
21. <span data-ttu-id="eb44a-139">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eb44a-139">Close the page.</span></span>
22. <span data-ttu-id="eb44a-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eb44a-140">Close the page.</span></span>
23. <span data-ttu-id="eb44a-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eb44a-141">Close the page.</span></span>

## <a name="apply-sales-agreement-in-the-order-process"></a><span data-ttu-id="eb44a-142">Értékesítési szerződés használata a rendelési folyamatban</span><span class="sxs-lookup"><span data-stu-id="eb44a-142">Apply sales agreement in the order process</span></span>
1. <span data-ttu-id="eb44a-143">Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="eb44a-143">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="eb44a-144">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-144">Click New.</span></span>
3. <span data-ttu-id="eb44a-145">A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="eb44a-145">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="eb44a-146">A listában keresse meg és válassza ki az értékesítési szerződésen megadott vevőt.</span><span class="sxs-lookup"><span data-stu-id="eb44a-146">In the list, find and select the customer specified on the sales agreement.</span></span>
5. <span data-ttu-id="eb44a-147">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="eb44a-147">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="eb44a-148">Bontsa ki az Általános szakaszt.</span><span class="sxs-lookup"><span data-stu-id="eb44a-148">Expand the General section.</span></span>
7. <span data-ttu-id="eb44a-149">Az Értékesítési szerződés azonosítója mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="eb44a-149">In the Sales agreement ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="eb44a-150">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="eb44a-150">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="eb44a-151">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="eb44a-151">Click Yes.</span></span>
10. <span data-ttu-id="eb44a-152">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="eb44a-152">Click OK.</span></span>
11. <span data-ttu-id="eb44a-153">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="eb44a-153">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="eb44a-154">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="eb44a-154">In the Item number field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="eb44a-155">A Cikkszám mezőben írja be vagy válassza ki a cikket, amely a társított értékesítési szerződésen meg van adva.</span><span class="sxs-lookup"><span data-stu-id="eb44a-155">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
14. <span data-ttu-id="eb44a-156">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="eb44a-156">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="eb44a-157">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="eb44a-157">Click Save.</span></span>
16. <span data-ttu-id="eb44a-158">A Művelet panelen kattintson a Kitárolás és csomagolás elemre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-158">On the Action Pane, click Pick and pack.</span></span>
17. <span data-ttu-id="eb44a-159">Kattintson A szállítólevél feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-159">Click Post packing slip.</span></span>
18. <span data-ttu-id="eb44a-160">Bontsa ki a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="eb44a-160">Expand the Parameters section.</span></span>
19. <span data-ttu-id="eb44a-161">Válassza ki az Igen lehetőséget a Feladás mezőben.</span><span class="sxs-lookup"><span data-stu-id="eb44a-161">Select Yes in the Posting field.</span></span>
20. <span data-ttu-id="eb44a-162">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="eb44a-162">Click OK.</span></span>
21. <span data-ttu-id="eb44a-163">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="eb44a-163">Click OK.</span></span>
22. <span data-ttu-id="eb44a-164">A Művelet panelen kattintson az Általános elemre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-164">On the Action Pane, click General.</span></span>
23. <span data-ttu-id="eb44a-165">Kattintson a Csatolt értékesítési szerződés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-165">Click Attached sales agreement.</span></span>
24. <span data-ttu-id="eb44a-166">Kattintson a Teljesítés fülre.</span><span class="sxs-lookup"><span data-stu-id="eb44a-166">Click the Fulfillment tab.</span></span>

