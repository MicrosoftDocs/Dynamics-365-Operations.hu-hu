---
title: Kivételek kivizsgálása/feloldása
description: A Szállítói számlára vonatkozó irányelvek akkor futnak, amikor a szállítói számla oldal használatával ad fel egy szállítói számlát, és amikor megnyitja a szállítói számlára vonatkozó irányelv megszegéseinek lapját.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 995d68f6224b6dfbb1928c907ad991b86fc47668
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443921"
---
# <a name="research-or-resolve-exceptions"></a><span data-ttu-id="7f74f-103">Kivételek kivizsgálása/feloldása</span><span class="sxs-lookup"><span data-stu-id="7f74f-103">Research or resolve exceptions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7f74f-104">A Szállítói számlára vonatkozó irányelvek akkor futnak, amikor a szállítói számla oldal használatával ad fel egy szállítói számlát, és amikor megnyitja a szállítói számlára vonatkozó irányelv megszegéseinek lapját.</span><span class="sxs-lookup"><span data-stu-id="7f74f-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="7f74f-105">A szállítói számla munkafolyamatát is beállíthatja úgy, hogy a valahányszor számlát küld egy munkafolyamathoz, futtatja a szállítói számlára vonatkozó irányelveket.</span><span class="sxs-lookup"><span data-stu-id="7f74f-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="7f74f-106">A szállítói számla irányelvek nem vonatkoznak azokra a számlákra, amelyek a számlajegyzékben vagy a számlanaplóban jöttek létre.</span><span class="sxs-lookup"><span data-stu-id="7f74f-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="7f74f-107">A számlaegyeztetés érvényesítése nem használja a szállítói számla irányelveket, ehelyett egy Kötelezettségek paraméterei oldalt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="7f74f-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="7f74f-108">Ez a felvétel az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="7f74f-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="7f74f-109">A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="7f74f-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="7f74f-110">Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva.</span><span class="sxs-lookup"><span data-stu-id="7f74f-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="7f74f-111">Felkészülés a szállítói számlára vonatkozó irányelvek létrehozására</span><span class="sxs-lookup"><span data-stu-id="7f74f-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="7f74f-112">Ugorjon a Kötelezettségek > Beállítás > Kötelezettségek paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="7f74f-113">Kattintson a Számlaegyeztetés fülre.</span><span class="sxs-lookup"><span data-stu-id="7f74f-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="7f74f-114">Válassza ki vagy állítsa alaphelyzetbe a Számlafejléc állapotának automatikus frissítése jelölőnégyzetét.</span><span class="sxs-lookup"><span data-stu-id="7f74f-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="7f74f-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-115">Click OK.</span></span>
5. <span data-ttu-id="7f74f-116">A Számlafeladás eltérésekkel mezőben válasszon a lehetőségek közül.</span><span class="sxs-lookup"><span data-stu-id="7f74f-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="7f74f-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7f74f-117">Close the page.</span></span>
7. <span data-ttu-id="7f74f-118">Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvek pontra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="7f74f-119">Kattintson a Paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7f74f-119">Click Parameters.</span></span>
9. <span data-ttu-id="7f74f-120">Majd a btnAdd lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7f74f-120">Click btnAdd.</span></span>
10. <span data-ttu-id="7f74f-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7f74f-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="7f74f-122">Szállítói számla irányelvszabály-típusainak létrehozása szállítói számlákhoz</span><span class="sxs-lookup"><span data-stu-id="7f74f-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="7f74f-123">Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvszabály típusok pontra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="7f74f-124">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7f74f-124">Click New.</span></span>
3. <span data-ttu-id="7f74f-125">Írjon be egy értéket a Szabály neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7f74f-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="7f74f-126">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7f74f-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7f74f-127">A Lekérdezés neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7f74f-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7f74f-128">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7f74f-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="7f74f-129">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7f74f-130">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-130">Click Save.</span></span>
9. <span data-ttu-id="7f74f-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7f74f-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="7f74f-132">Adjon meg egy Szállítói számlára vonatkozó irányelvet</span><span class="sxs-lookup"><span data-stu-id="7f74f-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="7f74f-133">Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvek pontra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="7f74f-134">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7f74f-134">Click New.</span></span>
3. <span data-ttu-id="7f74f-135">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7f74f-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="7f74f-136">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7f74f-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7f74f-137">Csukja be vagy bontsa ki az Irányelv szervezetei szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7f74f-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="7f74f-138">A fán válassza ki a „Contoso Szórakozás rendszer USA” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7f74f-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="7f74f-139">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-139">Click Add.</span></span>
8. <span data-ttu-id="7f74f-140">Csukja be vagy bontsa ki az Irányelvszabályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7f74f-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="7f74f-141">Kattintson az Irányelvszabályra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="7f74f-142">Írjon be egy értéket a Irányelvszabály leírása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7f74f-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="7f74f-143">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-143">Click Filter.</span></span>
12. <span data-ttu-id="7f74f-144">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-144">Click Add.</span></span>
13. <span data-ttu-id="7f74f-145">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="7f74f-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="7f74f-146">A Táblázat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7f74f-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="7f74f-147">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="7f74f-148">A Származtatott tábla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7f74f-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="7f74f-149">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="7f74f-150">A Mező mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7f74f-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="7f74f-151">Érték beírása a Mező mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7f74f-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="7f74f-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7f74f-152">Close the page.</span></span>
21. <span data-ttu-id="7f74f-153">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7f74f-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="7f74f-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-154">Click OK.</span></span>
23. <span data-ttu-id="7f74f-155">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7f74f-155">Click OK.</span></span>
24. <span data-ttu-id="7f74f-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7f74f-156">Close the page.</span></span>
25. <span data-ttu-id="7f74f-157">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7f74f-157">Close the page.</span></span>

