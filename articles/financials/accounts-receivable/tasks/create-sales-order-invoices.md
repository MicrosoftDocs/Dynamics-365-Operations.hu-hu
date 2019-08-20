---
title: Értékesítési rendelési számlák létrehozása
description: Ez a feladat-útmutató az értékesítési rendelés számlázását írja le, beleértve a számlákat és a kötegfeldolgozást.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba8e0f02f2d1eb12cecc2c434fbca1e198cddbe9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842953"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="a6f5e-103">Értékesítési rendelési számlák létrehozása</span><span class="sxs-lookup"><span data-stu-id="a6f5e-103">Create sales order invoices</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a6f5e-104">Ez a feladat-útmutató az értékesítési rendelés számlázását írja le, beleértve a számlákat és a kötegfeldolgozást.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="a6f5e-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="a6f5e-106">Értékesítési rendelés számlájának létrehozása.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="a6f5e-107">Ugrás a Kinnlevőségek > Rendelések > Leszállított, de még ki nem számlázott értékesítési rendelésekre.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-107">Go to Accounts receivable > Orders > Shipped but not invoiced sales orders.</span></span>
2. <span data-ttu-id="a6f5e-108">Válasszon ki a listából egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="a6f5e-109">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-109">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="a6f5e-110">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-110">Click Invoice.</span></span>
    * <span data-ttu-id="a6f5e-111">Ne feledje, hogy ehhez az értékesítési rendeléshez több csomagjegyzék van társítva.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-111">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="a6f5e-112">A szállítólevél száma helyett csak a <multiple> szó látszik.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-112">It will only show the word <multiple> instead of the packing slip number.</span></span>  
5. <span data-ttu-id="a6f5e-113">Bontsa ki a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-113">Expand the Parameters section.</span></span>
    * <span data-ttu-id="a6f5e-114">A számla feladásához a Feladásnál az Igent kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-114">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="a6f5e-115">De ki is kapcsolhatja a feladást, és csak kinyomtathatja a számlát.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-115">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="a6f5e-116">Azonban ugyanazt az eredményt a számla létrehozása helyett egy Pro forma számla létrehozásával is elérheti.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-116">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    * <span data-ttu-id="a6f5e-117">Ezt a beállítást a kötegelt feladatokhoz szokás használni.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-117">This option is used for batch jobs.</span></span> <span data-ttu-id="a6f5e-118">A kötegelt feladat futtatása alkalmával a lekérdezés futtatása.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-118">The query is run when the batch job is run.</span></span>    
6. <span data-ttu-id="a6f5e-119">A Nyomtatás mezőben válassza az „Utána” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-119">In the Print field, select 'After'.</span></span>
7. <span data-ttu-id="a6f5e-120">Válassza az Igen beállítást a számla nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-120">Select Yes for Print invoice.</span></span>
    * <span data-ttu-id="a6f5e-121">A nyomtatáskezelés a számlát több példányban is ki tudja nyomtatni és e-mailben, PDF-fájlként is el tudja küldeni.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-121">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
8. <span data-ttu-id="a6f5e-122">A Költségek nyomtatása mezőben válassza az „Összesítés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-122">In the Print charges field, select 'Summarize'.</span></span>
9. <span data-ttu-id="a6f5e-123">A Hitelkeret ellenőrzése mezőben válassza ki az „Egyenleg” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-123">In the Check credit limit field, select 'Balance'.</span></span>
10. <span data-ttu-id="a6f5e-124">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-124">Click Cancel.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="a6f5e-125">Rendelések egyesítése egyetlen számlában.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-125">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="a6f5e-126">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="a6f5e-127">Keresse meg azt a vevőt, akinek több megnyitott számlája van.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-127">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="a6f5e-128">Válasszon ki egy nyitott értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-128">Select an open sales order.</span></span>
4. <span data-ttu-id="a6f5e-129">Válasszon ki még egy nyitott értékesítési rendelést ugyanahhoz a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-129">Select another open sales order for the same customer.</span></span>
5. <span data-ttu-id="a6f5e-130">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-130">On the Action Pane, click Invoice.</span></span>
6. <span data-ttu-id="a6f5e-131">Kattintson a Számlára.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-131">Click Invoice.</span></span>
7. <span data-ttu-id="a6f5e-132">Bontsa ki a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-132">Expand the Parameters section.</span></span>
8. <span data-ttu-id="a6f5e-133">A Mennyiség mezőben válassza a „Mind” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-133">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="a6f5e-134">Vegye figyelembe, hogy az Áttekintés részben két számla van felsorolva.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-134">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="a6f5e-135">Most egyesítsük őket egy számlába.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-135">Now let's merge them into a single invoice.</span></span>  
9. <span data-ttu-id="a6f5e-136">Az Összegzés frissítése mezőben a „Számlafogadó” kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-136">In the Summary update for field, select 'Invoice account'.</span></span>
10. <span data-ttu-id="a6f5e-137">Kattintson az Elrendezésre az értékesítési megrendelések egy számlában való egyesítésére.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-137">Click Arrange to merge the sales orders into a single invoice.</span></span>
    * <span data-ttu-id="a6f5e-138">A két értékesítési megrendelés egy számlába került.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-138">The two sales orders are now merged into a single invoice.</span></span>   
11. <span data-ttu-id="a6f5e-139">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-139">Click Cancel.</span></span>
12. <span data-ttu-id="a6f5e-140">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-140">Click Yes.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="a6f5e-141">Számlák feladása kötegben</span><span class="sxs-lookup"><span data-stu-id="a6f5e-141">Post invoices in a batch</span></span>
1. <span data-ttu-id="a6f5e-142">Ugorjon a következőre: Kinnlévőségek > Számlák > Kötegelt számlák > Számla.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-142">Go to Accounts receivable > Invoices > Batch invoicing > Invoice.</span></span>
2. <span data-ttu-id="a6f5e-143">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-143">Click Select.</span></span>
3. <span data-ttu-id="a6f5e-144">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-144">Click OK.</span></span>
4. <span data-ttu-id="a6f5e-145">Kattintson a Kötegre.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-145">Click Batch.</span></span>
5. <span data-ttu-id="a6f5e-146">Kattintson az Igen gombra a kötegelt feldolgozás engedélyezéséhez..</span><span class="sxs-lookup"><span data-stu-id="a6f5e-146">Click on Yes to turn on batch processing.</span></span>
6. <span data-ttu-id="a6f5e-147">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-147">Click Recurrence.</span></span>
7. <span data-ttu-id="a6f5e-148">Napok kiválasztása</span><span class="sxs-lookup"><span data-stu-id="a6f5e-148">Select Days</span></span>
8. <span data-ttu-id="a6f5e-149">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-149">Click OK.</span></span>
9. <span data-ttu-id="a6f5e-150">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-150">Click OK.</span></span>
10. <span data-ttu-id="a6f5e-151">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-151">Click Cancel.</span></span>
11. <span data-ttu-id="a6f5e-152">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="a6f5e-152">Click Yes.</span></span>

