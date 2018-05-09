--- 
title: "Olyan igénylés létrehozása, amely ajánlatkérést használ"
description: "Ez az útmutató bemutatja, hogy hogyan lehet egy ajánlatkérési folyamat árral és a szállítóval kapcsolatos információit a beszerzési igényléshez hozzáadni."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 590ac360f0cc317f16d223e979b084ac2d331b9a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="8e3d2-103">Olyan igénylés létrehozása, amely ajánlatkérést használ</span><span class="sxs-lookup"><span data-stu-id="8e3d2-103">Create a requisition that uses an RFQ</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8e3d2-104">Ez az útmutató bemutatja, hogy hogyan lehet egy ajánlatkérési folyamat árral és a szállítóval kapcsolatos információit a beszerzési igényléshez hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-104">This guide shows how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="8e3d2-105">A példában szereplő útmutatót az USMF bemutatócég használhatja, és rendszergazdaként kell bejelentkeznie ahhoz, hogy végrehajthassa az összes lépést.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="8e3d2-106">Általában a beszerzési szakemberek hajtják végre a példában szereplő útmutatót.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="8e3d2-107">Igénylés létrehozása</span><span class="sxs-lookup"><span data-stu-id="8e3d2-107">Create a requisition</span></span>
1. <span data-ttu-id="8e3d2-108">Ugrás a Beszerzés és forrás > Beszerzési igénylések > Beszerzési igénylések általam létrehozva elemre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-108">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="8e3d2-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-109">Click New.</span></span>
3. <span data-ttu-id="8e3d2-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="8e3d2-111">Adja meg a dátumot az Igényelt dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-111">In the Requested date field, enter a date.</span></span>
5. <span data-ttu-id="8e3d2-112">Adja meg a dátumot a Könyvelés dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-112">In the Accounting date field, enter a date.</span></span>
6. <span data-ttu-id="8e3d2-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-113">Click OK.</span></span>
7. <span data-ttu-id="8e3d2-114">A Ok mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-114">In the Reason field, enter or select a value.</span></span>
8. <span data-ttu-id="8e3d2-115">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-115">Click Add line.</span></span>
9. <span data-ttu-id="8e3d2-116">Válasszon ki egy kategóriát a Beszerzési kategória mezőben a fa struktúrában, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-116">In the Procurement category field, select a category in the tree, and then click OK.</span></span>
10. <span data-ttu-id="8e3d2-117">Írjon be egy értéket a Terméknév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-117">In the Product name field, type a value.</span></span>
11. <span data-ttu-id="8e3d2-118">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="8e3d2-119">Az Egység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-119">In the Unit field, enter or select a value.</span></span>
13. <span data-ttu-id="8e3d2-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-120">Click Save.</span></span>
14. <span data-ttu-id="8e3d2-121">A Munkafolyamat gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-121">Click Workflow to open the drop dialog.</span></span>
15. <span data-ttu-id="8e3d2-122">Kattintson a Küldés hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-122">Click Submit.</span></span>
16. <span data-ttu-id="8e3d2-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-123">Close the page.</span></span>
17. <span data-ttu-id="8e3d2-124">Kattintson a Küldés hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-124">Click Submit.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="8e3d2-125">Munkafolyamat-feladat ismételt hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="8e3d2-125">Reassign a workflow task</span></span>
    * <span data-ttu-id="8e3d2-126">A következő feladat egy Ajánlatkérés létrehozása annak érdekében, hogy ajánlatot kapjon a szállítótól a termékre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="8e3d2-127">Az USMF bemutató adatokban az igénylési munkafolyamat egy olyan szabály szerint van beállítva, hogy ha a szállító nincs bejelölve, vagy az egységár értéke 0 soronként, akkor a rendszer a feladatot hozzárendeli egy adott dolgozóhoz, azért, hogy az létrehozzon egy Ajánlatkérést.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="8e3d2-128">Az útmutató folytatásához a feladatot ismét hozzá kell rendelni egy másik felhasználóhoz (saját magához).</span><span class="sxs-lookup"><span data-stu-id="8e3d2-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="8e3d2-129">Csak úgy teheti meg ezt, ha Rendszergazdaként jelentkezik be.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-129">You can only do this if you are logged in as an Admin.</span></span>  
1. <span data-ttu-id="8e3d2-130">A Munkafolyamat gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-130">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="8e3d2-131">Kattintson az Előzmények megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-131">Click View history.</span></span>
3. <span data-ttu-id="8e3d2-132">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="8e3d2-132">Refresh the page.</span></span>
4. <span data-ttu-id="8e3d2-133">Bontsa ki a Nyomkövetési részletek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-133">Expand the Tracking details section.</span></span>
5. <span data-ttu-id="8e3d2-134">Válassza ki a „Sor munkafolyamata aktiválva” értékkel kezdődő sort a fa struktúrában.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-134">In the tree, select 'the line that starts with “Line workflow activated on”'.</span></span>
6. <span data-ttu-id="8e3d2-135">Kattintson a Munkafolyamat részleteinek megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-135">Click View workflow details.</span></span>
7. <span data-ttu-id="8e3d2-136">Bontsa ki a Munkatételek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-136">Expand the Work items section.</span></span>
8. <span data-ttu-id="8e3d2-137">Kattintson az Hozzárendelés ismét lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-137">Click Reassign.</span></span>
9. <span data-ttu-id="8e3d2-138">Válassza ki a Rendszergazdát a Felhasználó mezőben.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-138">In the User field, select Admin.</span></span>
10. <span data-ttu-id="8e3d2-139">Kattintson az Hozzárendelés ismét lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-139">Click Reassign.</span></span>
11. <span data-ttu-id="8e3d2-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-140">Close the page.</span></span>
12. <span data-ttu-id="8e3d2-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-141">Close the page.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="8e3d2-142">Ajánlatkérés létrehozása</span><span class="sxs-lookup"><span data-stu-id="8e3d2-142">Create an RFQ</span></span>
1. <span data-ttu-id="8e3d2-143">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="8e3d2-143">Refresh the page.</span></span>
2. <span data-ttu-id="8e3d2-144">Kattintson az Ajánlatkérés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-144">Click Request for quotation.</span></span>
3. <span data-ttu-id="8e3d2-145">Válassza ki az USMF lehetőséget a Vevő jogi személy mezőben.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-145">In the Buying legal entity field, select USMF.</span></span>
    * <span data-ttu-id="8e3d2-146">Ugyanazt a jogi személyt kell kiválasztania, mint aki az igénylés sorában szerepel.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-146">You must select the same legal entity that’s on the requisition line.</span></span>  
4. <span data-ttu-id="8e3d2-147">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-147">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8e3d2-148">Ha a beszerzési igénylésben több sorral rendelkezett, válassza ki az összes olyan sort, amelyet hozzá kíván adni az ajánlatkéréshez.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-148">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="8e3d2-149">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-149">Click OK.</span></span>
6. <span data-ttu-id="8e3d2-150">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="8e3d2-150">Refresh the page.</span></span>
7. <span data-ttu-id="8e3d2-151">Nyissa meg az Adatterület lehetőséget, majd bontsa ki a kapcsolódó dokumentumok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-151">Open the FactBox and then expand the Related documents section.</span></span>
    * <span data-ttu-id="8e3d2-152">Előfordulhat, hogy már megnyitotta az Adatterület lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-152">You may already have the FactBox open.</span></span> <span data-ttu-id="8e3d2-153">Keresse meg a nyíllal ellátott ikont, a Sorok/Fejléc váltógombok jobb oldalán.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-153">Look for the icon with an arrow on it, to the right of the Lines/Header toggle buttons.</span></span> <span data-ttu-id="8e3d2-154">Ha jobbra mutat a nyíl, az Adatterület már meg van nyitva.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-154">If the arrow is pointing to the right, the FactBox is already open.</span></span> <span data-ttu-id="8e3d2-155">Ha balra mutat a nyíl, kattintson rá, az Adatterület megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-155">If the arrow points to the left, click it to open the FactBox.</span></span>  
8. <span data-ttu-id="8e3d2-156">Kattintson az Ajánlatkérés mezőben szereplő hivatkozásra az újonnan létrehozott Ajánlatkérés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-156">Click the link in the Request for quotation field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="8e3d2-157">Kattintson a Fejléc gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-157">Click Header.</span></span>
10. <span data-ttu-id="8e3d2-158">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-158">Click Add.</span></span>
11. <span data-ttu-id="8e3d2-159">A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-159">In the Vendor account field, enter or select a value.</span></span>
12. <span data-ttu-id="8e3d2-160">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-160">Click Add.</span></span>
13. <span data-ttu-id="8e3d2-161">A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-161">In the Vendor account field, enter or select a value.</span></span>
14. <span data-ttu-id="8e3d2-162">Kattintson a Küldés gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-162">Click Send.</span></span>
15. <span data-ttu-id="8e3d2-163">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-163">Click OK.</span></span>
16. <span data-ttu-id="8e3d2-164">Kattintson a Válasz beírása gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-164">Click Enter reply.</span></span>
17. <span data-ttu-id="8e3d2-165">A Művelet panelen kattintson a Válasz elemre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-165">On the Action Pane, click Reply.</span></span>
18. <span data-ttu-id="8e3d2-166">Kattintson az Adatok másolása a válaszba elemre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-166">Click Copy data to reply.</span></span>
    * <span data-ttu-id="8e3d2-167">Ez olyan adatokat másol a válaszhoz az ajánlatkérésből, mint például a mennyiség vagy a dátumok.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-167">This copies data, such as the quantity and dates, from the RFQ to the reply .</span></span>  
19. <span data-ttu-id="8e3d2-168">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-168">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="8e3d2-169">Ez a szállítótól kapott ár.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-169">This is the price that you’ve received from the vendor.</span></span> <span data-ttu-id="8e3d2-170">További információkat is meg kell adnia a szállítóról.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-170">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="8e3d2-171">Kattintson az Elfogadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-171">Click Accept.</span></span>
21. <span data-ttu-id="8e3d2-172">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-172">Click OK.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="8e3d2-173">Győződjön meg arról, hogy átkerült az ár és a szállító az igényléshez.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-173">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="8e3d2-174">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-174">Close the page.</span></span>
2. <span data-ttu-id="8e3d2-175">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-175">Click Lines.</span></span>
3. <span data-ttu-id="8e3d2-176">Kattintson a Kapcsolódó információ lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-176">Click Related information.</span></span>
4. <span data-ttu-id="8e3d2-177">Kattintson a Beszerzési igénylés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-177">Click Purchase requisition.</span></span>
5. <span data-ttu-id="8e3d2-178">Válassza ki azt a sort, amelyet a rendszer átvitt az Ajánlatkéréshez.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-178">Select the line that was transferred to the RFQ.</span></span>
    * <span data-ttu-id="8e3d2-179">Győződjön meg arról, hogy átmásolták az árat és a szállítót az igényléshez.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-179">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="8e3d2-180">A Munkafolyamat gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-180">Click Workflow to open the drop dialog.</span></span>
7. <span data-ttu-id="8e3d2-181">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-181">Click Complete.</span></span>
8. <span data-ttu-id="8e3d2-182">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-182">Close the page.</span></span>
9. <span data-ttu-id="8e3d2-183">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="8e3d2-183">Click Complete.</span></span>


