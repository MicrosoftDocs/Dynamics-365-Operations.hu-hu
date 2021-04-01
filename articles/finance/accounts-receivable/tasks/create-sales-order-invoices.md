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
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d2e1dd552f529d09756c1ddeec39fc54a1f073a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241586"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="cb599-103">Értékesítési rendelési számlák létrehozása</span><span class="sxs-lookup"><span data-stu-id="cb599-103">Create sales order invoices</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cb599-104">Ez a feladat-útmutató az értékesítési rendelés számlázását írja le, beleértve a számlákat és a kötegfeldolgozást.</span><span class="sxs-lookup"><span data-stu-id="cb599-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="cb599-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="cb599-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="cb599-106">Értékesítési rendelés számlájának létrehozása.</span><span class="sxs-lookup"><span data-stu-id="cb599-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="cb599-107">Válassza a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Kiszállított de nem számlázott értékesítési rendelések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb599-107">Go to **Navigation pane > Modules > Accounts receivable > Orders > Shipped but not invoiced sales orders**.</span></span>
2. <span data-ttu-id="cb599-108">Válasszon ki a listából egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="cb599-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="cb599-109">A **Művelet panelen** kattintson a **Számla > Generálás > Számla** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb599-109">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span> <span data-ttu-id="cb599-110">Ne feledje, hogy ehhez az értékesítési rendeléshez több csomagjegyzék van társítva.</span><span class="sxs-lookup"><span data-stu-id="cb599-110">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="cb599-111">A szállítólevél száma helyett csak a <multiple> szó látszik.</span><span class="sxs-lookup"><span data-stu-id="cb599-111">It will only show the word <multiple> instead of the packing slip number.</span></span>  
4. <span data-ttu-id="cb599-112">Bontsa ki a **Paraméterek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cb599-112">Expand the **Parameters** section.</span></span>
    - <span data-ttu-id="cb599-113">A számla feladásához a Feladásnál az Igent kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="cb599-113">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="cb599-114">De ki is kapcsolhatja a feladást, és csak kinyomtathatja a számlát.</span><span class="sxs-lookup"><span data-stu-id="cb599-114">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="cb599-115">Azonban ugyanazt az eredményt a számla létrehozása helyett egy Pro forma számla létrehozásával is elérheti.</span><span class="sxs-lookup"><span data-stu-id="cb599-115">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    - <span data-ttu-id="cb599-116">Ezt a beállítást a kötegelt feladatokhoz szokás használni.</span><span class="sxs-lookup"><span data-stu-id="cb599-116">This option is used for batch jobs.</span></span> <span data-ttu-id="cb599-117">A kötegelt feladat futtatása alkalmával a lekérdezés futtatása.</span><span class="sxs-lookup"><span data-stu-id="cb599-117">The query is run when the batch job is run.</span></span>
5. <span data-ttu-id="cb599-118">A **Nyomtatás** mezőben válassza az „Utána” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb599-118">In the **Print** field, select 'After'.</span></span>
6. <span data-ttu-id="cb599-119">Válassza az **Igen** beállítást a **Számla nyomtatásához**.</span><span class="sxs-lookup"><span data-stu-id="cb599-119">Select **Yes** for **Print invoice**.</span></span> <span data-ttu-id="cb599-120">A nyomtatáskezelés a számlát több példányban is ki tudja nyomtatni és e-mailben, PDF-fájlként is el tudja küldeni.</span><span class="sxs-lookup"><span data-stu-id="cb599-120">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
7. <span data-ttu-id="cb599-121">A **Költségek nyomtatása** mezőben válassza az „Összesítés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb599-121">In the **Print charges** field, select 'Summarize'.</span></span>
8. <span data-ttu-id="cb599-122">A **Hitelkeret ellenőrzése** mezőben válassza ki az „Egyenleg” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb599-122">In the **Check credit limit** field, select 'Balance'.</span></span>
9. <span data-ttu-id="cb599-123">Kattintson a **Mégse** gombra.</span><span class="sxs-lookup"><span data-stu-id="cb599-123">Click **Cancel**.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="cb599-124">Rendelések egyesítése egyetlen számlában.</span><span class="sxs-lookup"><span data-stu-id="cb599-124">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="cb599-125">Ugorjon a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Minden értékesítési megrendelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb599-125">Go to **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="cb599-126">Keresse meg azt a vevőt, akinek több megnyitott számlája van.</span><span class="sxs-lookup"><span data-stu-id="cb599-126">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="cb599-127">Több nyitott értékesítési rendelés kiválasztása ugyanabból a vevőből.</span><span class="sxs-lookup"><span data-stu-id="cb599-127">Select multiple open sales orders from the same customer.</span></span>
4. <span data-ttu-id="cb599-128">A **Művelet panelen** kattintson a **Számla > Generálás > Számla** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb599-128">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span>
5. <span data-ttu-id="cb599-129">Bontsa ki a **Paraméterek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cb599-129">Expand the **Parameters** section.</span></span>
6. <span data-ttu-id="cb599-130">A **Mennyiség** mezőben válassza a 'Mind' lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb599-130">In the **Quantity** field, select 'All'.</span></span> <span data-ttu-id="cb599-131">Vegye figyelembe, hogy az Áttekintés részben két számla van felsorolva.</span><span class="sxs-lookup"><span data-stu-id="cb599-131">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="cb599-132">Most egyesítsük őket egy számlába.</span><span class="sxs-lookup"><span data-stu-id="cb599-132">Now let's merge them into a single invoice.</span></span>  
7. <span data-ttu-id="cb599-133">Az **Összegzés frissítése a következőhöz:** mezőben a „Számlafogadó” kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="cb599-133">In the **Summary update for** field, select 'Invoice account'.</span></span>
8. <span data-ttu-id="cb599-134">Kattintson az **Elrendezés** elemre az értékesítési megrendelések egy számlában való egyesítésére.</span><span class="sxs-lookup"><span data-stu-id="cb599-134">Click **Arrange** to merge the sales orders into a single invoice.</span></span> <span data-ttu-id="cb599-135">A két értékesítési megrendelés egy számlába került.</span><span class="sxs-lookup"><span data-stu-id="cb599-135">The two sales orders are now merged into a single invoice.</span></span>   
9. <span data-ttu-id="cb599-136">Kattintson a **Mégse** gombra.</span><span class="sxs-lookup"><span data-stu-id="cb599-136">Click **Cancel**.</span></span>
10. <span data-ttu-id="cb599-137">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="cb599-137">Click **Yes**.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="cb599-138">Számlák feladása kötegben</span><span class="sxs-lookup"><span data-stu-id="cb599-138">Post invoices in a batch</span></span>
1. <span data-ttu-id="cb599-139">Ugorjon a következőre: **Navigációs panel > Kinnlévőségek > Számlák > Kötegelt számlázás > Számla**.</span><span class="sxs-lookup"><span data-stu-id="cb599-139">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Batch invoicing > Invoice**.</span></span>
2. <span data-ttu-id="cb599-140">Kattintson a **Kiválasztás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb599-140">Click **Select**.</span></span>
3. <span data-ttu-id="cb599-141">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cb599-141">Click **OK**.</span></span>
4. <span data-ttu-id="cb599-142">Kattintson a **Kötegre** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb599-142">Click **Batch**.</span></span>
5. <span data-ttu-id="cb599-143">A **Kötegelt feldolgozás** alatt válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb599-143">Select **Yes** in **Batch processing**.</span></span>
6. <span data-ttu-id="cb599-144">Kattintson az **Ismétlődésre**.</span><span class="sxs-lookup"><span data-stu-id="cb599-144">Click **Recurrence**.</span></span>
7. <span data-ttu-id="cb599-145">Válassza a **Napok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb599-145">Select **Days**.</span></span>
8. <span data-ttu-id="cb599-146">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cb599-146">Click **OK**.</span></span>
9. <span data-ttu-id="cb599-147">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cb599-147">Click **OK**.</span></span>
10. <span data-ttu-id="cb599-148">Kattintson a **Mégse** gombra.</span><span class="sxs-lookup"><span data-stu-id="cb599-148">Click **Cancel**.</span></span>
11. <span data-ttu-id="cb599-149">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="cb599-149">Click **Yes**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]