---
title: Értékesítési rendelési számlák létrehozása
description: Ez a feladat-útmutató az értékesítési rendelés számlázását írja le, beleértve a számlákat és a kötegfeldolgozást.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
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
ms.openlocfilehash: c504ef36f61613c7aa7db5a1e5ddba6e69cd7285
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140270"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="f9907-103">Értékesítési rendelési számlák létrehozása</span><span class="sxs-lookup"><span data-stu-id="f9907-103">Create sales order invoices</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f9907-104">Ez a feladat-útmutató az értékesítési rendelés számlázását írja le, beleértve a számlákat és a kötegfeldolgozást.</span><span class="sxs-lookup"><span data-stu-id="f9907-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="f9907-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="f9907-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="f9907-106">Értékesítési rendelés számlájának létrehozása.</span><span class="sxs-lookup"><span data-stu-id="f9907-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="f9907-107">Válassza a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Kiszállított de nem számlázott értékesítési rendelések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9907-107">Go to **Navigation pane > Modules > Accounts receivable > Orders > Shipped but not invoiced sales orders**.</span></span>
2. <span data-ttu-id="f9907-108">Válasszon ki a listából egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="f9907-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="f9907-109">A **Művelet panelen** kattintson a **Számla > Generálás > Számla** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9907-109">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span> <span data-ttu-id="f9907-110">Ne feledje, hogy ehhez az értékesítési rendeléshez több csomagjegyzék van társítva.</span><span class="sxs-lookup"><span data-stu-id="f9907-110">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="f9907-111">A szállítólevél száma helyett csak a <multiple> szó látszik.</span><span class="sxs-lookup"><span data-stu-id="f9907-111">It will only show the word <multiple> instead of the packing slip number.</span></span>  
4. <span data-ttu-id="f9907-112">Bontsa ki a **Paraméterek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="f9907-112">Expand the **Parameters** section.</span></span>
    - <span data-ttu-id="f9907-113">A számla feladásához a Feladásnál az Igent kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="f9907-113">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="f9907-114">De ki is kapcsolhatja a feladást, és csak kinyomtathatja a számlát.</span><span class="sxs-lookup"><span data-stu-id="f9907-114">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="f9907-115">Azonban ugyanazt az eredményt a számla létrehozása helyett egy Pro forma számla létrehozásával is elérheti.</span><span class="sxs-lookup"><span data-stu-id="f9907-115">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    - <span data-ttu-id="f9907-116">Ezt a beállítást a kötegelt feladatokhoz szokás használni.</span><span class="sxs-lookup"><span data-stu-id="f9907-116">This option is used for batch jobs.</span></span> <span data-ttu-id="f9907-117">A kötegelt feladat futtatása alkalmával a lekérdezés futtatása.</span><span class="sxs-lookup"><span data-stu-id="f9907-117">The query is run when the batch job is run.</span></span>
5. <span data-ttu-id="f9907-118">A **Nyomtatás** mezőben válassza az „Utána” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f9907-118">In the **Print** field, select 'After'.</span></span>
6. <span data-ttu-id="f9907-119">Válassza az **Igen** beállítást a **Számla nyomtatásához**.</span><span class="sxs-lookup"><span data-stu-id="f9907-119">Select **Yes** for **Print invoice**.</span></span> <span data-ttu-id="f9907-120">A nyomtatáskezelés a számlát több példányban is ki tudja nyomtatni és e-mailben, PDF-fájlként is el tudja küldeni.</span><span class="sxs-lookup"><span data-stu-id="f9907-120">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
7. <span data-ttu-id="f9907-121">A **Költségek nyomtatása** mezőben válassza az „Összesítés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f9907-121">In the **Print charges** field, select 'Summarize'.</span></span>
8. <span data-ttu-id="f9907-122">A **Hitelkeret ellenőrzése** mezőben válassza ki az „Egyenleg” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f9907-122">In the **Check credit limit** field, select 'Balance'.</span></span>
9. <span data-ttu-id="f9907-123">Kattintson a **Mégse** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9907-123">Click **Cancel**.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="f9907-124">Rendelések egyesítése egyetlen számlában.</span><span class="sxs-lookup"><span data-stu-id="f9907-124">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="f9907-125">Ugorjon a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Minden értékesítési megrendelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9907-125">Go to **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="f9907-126">Keresse meg azt a vevőt, akinek több megnyitott számlája van.</span><span class="sxs-lookup"><span data-stu-id="f9907-126">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="f9907-127">Több nyitott értékesítési rendelés kiválasztása ugyanabból a vevőből.</span><span class="sxs-lookup"><span data-stu-id="f9907-127">Select multiple open sales orders from the same customer.</span></span>
4. <span data-ttu-id="f9907-128">A **Művelet panelen** kattintson a **Számla > Generálás > Számla** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9907-128">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span>
5. <span data-ttu-id="f9907-129">Bontsa ki a **Paraméterek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="f9907-129">Expand the **Parameters** section.</span></span>
6. <span data-ttu-id="f9907-130">A **Mennyiség** mezőben válassza a 'Mind' lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f9907-130">In the **Quantity** field, select 'All'.</span></span> <span data-ttu-id="f9907-131">Vegye figyelembe, hogy az Áttekintés részben két számla van felsorolva.</span><span class="sxs-lookup"><span data-stu-id="f9907-131">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="f9907-132">Most egyesítsük őket egy számlába.</span><span class="sxs-lookup"><span data-stu-id="f9907-132">Now let's merge them into a single invoice.</span></span>  
7. <span data-ttu-id="f9907-133">Az **Összegzés frissítése a következőhöz:** mezőben a „Számlafogadó” kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="f9907-133">In the **Summary update for** field, select 'Invoice account'.</span></span>
8. <span data-ttu-id="f9907-134">Kattintson az **Elrendezés** elemre az értékesítési megrendelések egy számlában való egyesítésére.</span><span class="sxs-lookup"><span data-stu-id="f9907-134">Click **Arrange** to merge the sales orders into a single invoice.</span></span> <span data-ttu-id="f9907-135">A két értékesítési megrendelés egy számlába került.</span><span class="sxs-lookup"><span data-stu-id="f9907-135">The two sales orders are now merged into a single invoice.</span></span>   
9. <span data-ttu-id="f9907-136">Kattintson a **Mégse** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9907-136">Click **Cancel**.</span></span>
10. <span data-ttu-id="f9907-137">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9907-137">Click **Yes**.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="f9907-138">Számlák feladása kötegben</span><span class="sxs-lookup"><span data-stu-id="f9907-138">Post invoices in a batch</span></span>
1. <span data-ttu-id="f9907-139">Ugorjon a következőre: **Navigációs panel > Kinnlévőségek > Számlák > Kötegelt számlázás > Számla**.</span><span class="sxs-lookup"><span data-stu-id="f9907-139">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Batch invoicing > Invoice**.</span></span>
2. <span data-ttu-id="f9907-140">Kattintson a **Kiválasztás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9907-140">Click **Select**.</span></span>
3. <span data-ttu-id="f9907-141">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9907-141">Click **OK**.</span></span>
4. <span data-ttu-id="f9907-142">Kattintson a **Kötegre** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9907-142">Click **Batch**.</span></span>
5. <span data-ttu-id="f9907-143">A **Kötegelt feldolgozás** alatt válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f9907-143">Select **Yes** in **Batch processing**.</span></span>
6. <span data-ttu-id="f9907-144">Kattintson az **Ismétlődésre**.</span><span class="sxs-lookup"><span data-stu-id="f9907-144">Click **Recurrence**.</span></span>
7. <span data-ttu-id="f9907-145">Válassza a **Napok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f9907-145">Select **Days**.</span></span>
8. <span data-ttu-id="f9907-146">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9907-146">Click **OK**.</span></span>
9. <span data-ttu-id="f9907-147">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9907-147">Click **OK**.</span></span>
10. <span data-ttu-id="f9907-148">Kattintson a **Mégse** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9907-148">Click **Cancel**.</span></span>
11. <span data-ttu-id="f9907-149">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9907-149">Click **Yes**.</span></span>

