---
title: Olyan igénylés létrehozása, amely ajánlatkérést használ
description: Ez a témakör ismeteti, hogy hogyan lehet egy ajánlatkérési folyamat árral és a szállítóval kapcsolatos információit a beszerzési igényléshez hozzáadni.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e67dafd02a3b2a38832d8a4f0e9809adffcbb80
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211838"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="c0dc6-103">Olyan igénylés létrehozása, amely ajánlatkérést használ</span><span class="sxs-lookup"><span data-stu-id="c0dc6-103">Create a requisition that uses an RFQ</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c0dc6-104">Ez a témakör ismeteti, hogy hogyan lehet egy ajánlatkérési folyamat árral és a szállítóval kapcsolatos információit a beszerzési igényléshez hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-104">This topic explains how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="c0dc6-105">A példában szereplő útmutatót az USMF bemutatócég használhatja, és rendszergazdaként kell bejelentkeznie ahhoz, hogy végrehajthassa az összes lépést.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="c0dc6-106">Általában a beszerzési szakemberek hajtják végre a példában szereplő útmutatót.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="c0dc6-107">Igénylés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c0dc6-107">Create a requisition</span></span>
1. <span data-ttu-id="c0dc6-108">A navigációs panelen ugorjon a **Modulok >Beszerzés és forrás > Beszerzési igénylések > Beszerzési igénylések általam létrehozva pontra**.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-108">In the navigation pane, go to **Modules > Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me**.</span></span>
2. <span data-ttu-id="c0dc6-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-109">Select **New**.</span></span>
3. <span data-ttu-id="c0dc6-110">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="c0dc6-111">Adja meg a dátumot az **Igényelt dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-111">In the **Requested date** field, enter a date.</span></span>
5. <span data-ttu-id="c0dc6-112">Adja meg a dátumot a **Könyvelés dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-112">In the **Accounting date** field, enter a date.</span></span>
6. <span data-ttu-id="c0dc6-113">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-113">Select **OK**.</span></span>
7. <span data-ttu-id="c0dc6-114">Az **Ok** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-114">In the **Reason** field, enter or select a value.</span></span>
8. <span data-ttu-id="c0dc6-115">Válassza a **Sor hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-115">Select **Add line**.</span></span>
9. <span data-ttu-id="c0dc6-116">Válasszon ki egy kategóriát a **Beszerzési kategória** mezőben a fa struktúrában, és kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-116">In the **Procurement category** field, select a category in the tree, and then select **OK**.</span></span>
10. <span data-ttu-id="c0dc6-117">Írjon be egy értéket a **Terméknév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-117">In the **Product name** field, type a value.</span></span>
11. <span data-ttu-id="c0dc6-118">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-118">In the **Quantity** field, enter a number.</span></span>
12. <span data-ttu-id="c0dc6-119">Az **Egység** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-119">In the **Unit** field, enter or select a value.</span></span>
13. <span data-ttu-id="c0dc6-120">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-120">Select **Save**.</span></span>
14. <span data-ttu-id="c0dc6-121">A **Munkafolyamat** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-121">Select **Workflow** to open the drop dialog.</span></span>
15. <span data-ttu-id="c0dc6-122">Válassza a **Beküldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-122">Select **Submit**.</span></span>
16. <span data-ttu-id="c0dc6-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-123">Close the page.</span></span>
17. <span data-ttu-id="c0dc6-124">Válassza a **Beküldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-124">Select **Submit**.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="c0dc6-125">Munkafolyamat-feladat ismételt hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="c0dc6-125">Reassign a workflow task</span></span>
<span data-ttu-id="c0dc6-126">A következő feladat egy Ajánlatkérés létrehozása annak érdekében, hogy ajánlatot kapjon a szállítótól a termékre.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="c0dc6-127">Az USMF bemutató adatokban az igénylési munkafolyamat egy olyan szabály szerint van beállítva, hogy ha a szállító nincs bejelölve, vagy az egységár értéke 0 soronként, akkor a rendszer a feladatot hozzárendeli egy adott dolgozóhoz, azért, hogy az létrehozzon egy Ajánlatkérést.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="c0dc6-128">Az útmutató folytatásához a feladatot ismét hozzá kell rendelni egy másik felhasználóhoz (saját magához).</span><span class="sxs-lookup"><span data-stu-id="c0dc6-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="c0dc6-129">Csak úgy teheti meg ezt, ha Rendszergazdaként jelentkezik be.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-129">You can only do this if you are logged in as an Admin.</span></span>  

1. <span data-ttu-id="c0dc6-130">A **Munkafolyamat** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-130">Select **Workflow** to open the drop dialog.</span></span>
2. <span data-ttu-id="c0dc6-131">Válassza az **Előzmények megtekintése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-131">Select **View history**.</span></span>
3. <span data-ttu-id="c0dc6-132">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="c0dc6-132">Refresh the page.</span></span>
4. <span data-ttu-id="c0dc6-133">Bontsa ki a **Nyomkövetési részletek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-133">Expand the **Tracking details** section.</span></span>
5. <span data-ttu-id="c0dc6-134">Válassza ki a „Sor munkafolyamata aktiválva ekkor:” értékkel kezdődő sort a fa struktúrában.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-134">In the tree, select the line that starts with "Line workflow activated on".</span></span>
6. <span data-ttu-id="c0dc6-135">Válassza a **Munkafolyamat részleteinek megtekintése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-135">Select **View workflow details**.</span></span>
7. <span data-ttu-id="c0dc6-136">Bontsa ki a **Munkatételek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-136">Expand the **Work items** section.</span></span>
8. <span data-ttu-id="c0dc6-137">Válassza ki az **Ismételt hozzárendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-137">Select **Reassign**.</span></span>
9. <span data-ttu-id="c0dc6-138">Válassza ki a **Rendszergazdát** a **Felhasználó** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-138">In the **User** field, select **Admin**.</span></span>
10. <span data-ttu-id="c0dc6-139">Válassza ki az **Ismételt hozzárendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-139">Select **Reassign**.</span></span>
11. <span data-ttu-id="c0dc6-140">Zárja be a két lapot.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-140">Close the two pages.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="c0dc6-141">Ajánlatkérés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c0dc6-141">Create an RFQ</span></span>

1. <span data-ttu-id="c0dc6-142">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="c0dc6-142">Refresh the page.</span></span>
2. <span data-ttu-id="c0dc6-143">Válassza az **Ajánlatkérés** elemet.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-143">Select **Request for quotation**.</span></span>
3. <span data-ttu-id="c0dc6-144">Válassza ki az **USMF** lehetőséget a **Vevő jogi személy** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-144">In the **Buying legal entity** field, select **USMF**.</span></span> <span data-ttu-id="c0dc6-145">Ugyanazt a jogi személyt kell kiválasztania, mint aki az igénylés sorában szerepel.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-145">You must select the same legal entity that's on the requisition line.</span></span>  
4. <span data-ttu-id="c0dc6-146">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-146">In the list, mark the selected row.</span></span> <span data-ttu-id="c0dc6-147">Ha a beszerzési igénylésben több sorral rendelkezett, válassza ki az összes olyan sort, amelyet hozzá kíván adni az ajánlatkéréshez.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-147">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="c0dc6-148">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-148">Select **OK**.</span></span>
6. <span data-ttu-id="c0dc6-149">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="c0dc6-149">Refresh the page.</span></span>
7. <span data-ttu-id="c0dc6-150">Nyissa meg az Adatterület lehetőséget, majd bontsa ki a **Kapcsolódó dokumentumok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-150">Ensure that the FactBox is open, then expand the **Related documents** section.</span></span>
8. <span data-ttu-id="c0dc6-151">Kattintson az Ajánlatkérés mezőben szereplő hivatkozásra az újonnan létrehozott **Ajánlatkérés** megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-151">Select the link in the **Request for quotation** field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="c0dc6-152">Válassza ki a **Fejléc** elemet.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-152">Select **Header**.</span></span>
10. <span data-ttu-id="c0dc6-153">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-153">Select **Add**.</span></span>
11. <span data-ttu-id="c0dc6-154">A **Szállítószámla** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-154">In the **Vendor account** field, enter or select a value.</span></span>
12. <span data-ttu-id="c0dc6-155">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-155">Select **Add**.</span></span>
13. <span data-ttu-id="c0dc6-156">A **Szállítószámla** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-156">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="c0dc6-157">Válassza a **Küldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-157">Select **Send**.</span></span>
15. <span data-ttu-id="c0dc6-158">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-158">Select **OK**.</span></span>
16. <span data-ttu-id="c0dc6-159">Válassza a **Válasz megadása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-159">Select **Enter reply**.</span></span>
17. <span data-ttu-id="c0dc6-160">A Műveleti ablaktáblán kattintson a **Válasz** elemre.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-160">On the Action Pane, select **Reply**.</span></span>
18. <span data-ttu-id="c0dc6-161">Válassza az **Adatok másolása a válaszba** elemet.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-161">Select **Copy data to reply**.</span></span> <span data-ttu-id="c0dc6-162">Ez olyan adatokat másol a válaszhoz az ajánlatkérésből, mint például a mennyiség vagy a dátumok.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-162">This copies data, such as the quantity and dates, from the RFQ to the reply.</span></span>  
19. <span data-ttu-id="c0dc6-163">Adjon meg egy számot az **Egységár** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-163">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="c0dc6-164">Ez a szállítótól kapott ár.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-164">This is the price that you've received from the vendor.</span></span> <span data-ttu-id="c0dc6-165">További információkat is meg kell adnia a szállítóról.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-165">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="c0dc6-166">Válassza az **Elfogadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-166">Select **Accept**.</span></span>
21. <span data-ttu-id="c0dc6-167">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-167">Select **OK**.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="c0dc6-168">Győződjön meg arról, hogy átkerült az ár és a szállító az igényléshez.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-168">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="c0dc6-169">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-169">Close the page.</span></span>
2. <span data-ttu-id="c0dc6-170">**Sorok** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-170">Select **Lines**.</span></span>
3. <span data-ttu-id="c0dc6-171">Válassza ki a **Kapcsolódó információ** elemet.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-171">Select **Related information**.</span></span>
4. <span data-ttu-id="c0dc6-172">Válassza a **Beszerzési igénylés** elemet.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-172">Select **Purchase requisition**.</span></span>
5. <span data-ttu-id="c0dc6-173">Válassza ki azt a sort, amelyet a rendszer átvitt az Ajánlatkéréshez.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-173">Select the line that was transferred to the RFQ.</span></span> <span data-ttu-id="c0dc6-174">Győződjön meg arról, hogy átmásolták az árat és a szállítót az igényléshez.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-174">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="c0dc6-175">A **Munkafolyamat** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-175">Select **Workflow** to open the drop dialog.</span></span>
7. <span data-ttu-id="c0dc6-176">Válassza a Kész lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c0dc6-176">Select Complete.</span></span>
8. <span data-ttu-id="c0dc6-177">Válassza az oldalt.</span><span class="sxs-lookup"><span data-stu-id="c0dc6-177">Select the page.</span></span>
9. <span data-ttu-id="c0dc6-178">Válassza a Kész lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c0dc6-178">Select Complete.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]