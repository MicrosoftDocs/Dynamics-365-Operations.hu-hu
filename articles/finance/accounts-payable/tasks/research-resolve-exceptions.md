---
title: Kivételek kivizsgálása/feloldása
description: A Szállítói számlára vonatkozó irányelvek akkor futnak, amikor a szállítói számla oldal használatával ad fel egy szállítói számlát, és amikor megnyitja a szállítói számlára vonatkozó irányelv megszegéseinek lapját.
author: abruer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abc8dc112ab577ddcbd208f898a8d4e487bc2998
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827770"
---
# <a name="research-or-resolve-exceptions"></a><span data-ttu-id="6a615-103">Kivételek kivizsgálása/feloldása</span><span class="sxs-lookup"><span data-stu-id="6a615-103">Research or resolve exceptions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6a615-104">A Szállítói számlára vonatkozó irányelvek akkor futnak, amikor a szállítói számla oldal használatával ad fel egy szállítói számlát, és amikor megnyitja a szállítói számlára vonatkozó irányelv megszegéseinek lapját.</span><span class="sxs-lookup"><span data-stu-id="6a615-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="6a615-105">A szállítói számla munkafolyamatát is beállíthatja úgy, hogy a valahányszor számlát küld egy munkafolyamathoz, futtatja a szállítói számlára vonatkozó irányelveket.</span><span class="sxs-lookup"><span data-stu-id="6a615-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="6a615-106">A szállítói számla irányelvek nem vonatkoznak azokra a számlákra, amelyek a számlajegyzékben vagy a számlanaplóban jöttek létre.</span><span class="sxs-lookup"><span data-stu-id="6a615-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="6a615-107">A számlaegyeztetés érvényesítése nem használja a szállítói számla irányelveket, ehelyett egy Kötelezettségek paraméterei oldalt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="6a615-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="6a615-108">Ez a felvétel az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="6a615-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="6a615-109">A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="6a615-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="6a615-110">Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva.</span><span class="sxs-lookup"><span data-stu-id="6a615-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="6a615-111">Felkészülés a szállítói számlára vonatkozó irányelvek létrehozására</span><span class="sxs-lookup"><span data-stu-id="6a615-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="6a615-112">Ugorjon a Kötelezettségek > Beállítás > Kötelezettségek paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="6a615-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="6a615-113">Kattintson a Számlaegyeztetés fülre.</span><span class="sxs-lookup"><span data-stu-id="6a615-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="6a615-114">Válassza ki vagy állítsa alaphelyzetbe a Számlafejléc állapotának automatikus frissítése jelölőnégyzetét.</span><span class="sxs-lookup"><span data-stu-id="6a615-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="6a615-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6a615-115">Click OK.</span></span>
5. <span data-ttu-id="6a615-116">A Számlafeladás eltérésekkel mezőben válasszon a lehetőségek közül.</span><span class="sxs-lookup"><span data-stu-id="6a615-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="6a615-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6a615-117">Close the page.</span></span>
7. <span data-ttu-id="6a615-118">Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvek pontra.</span><span class="sxs-lookup"><span data-stu-id="6a615-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="6a615-119">Kattintson a Paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6a615-119">Click Parameters.</span></span>
9. <span data-ttu-id="6a615-120">Majd a btnAdd lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6a615-120">Click btnAdd.</span></span>
10. <span data-ttu-id="6a615-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6a615-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="6a615-122">Szállítói számla irányelvszabály-típusainak létrehozása szállítói számlákhoz</span><span class="sxs-lookup"><span data-stu-id="6a615-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="6a615-123">Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvszabály típusok pontra.</span><span class="sxs-lookup"><span data-stu-id="6a615-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="6a615-124">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6a615-124">Click New.</span></span>
3. <span data-ttu-id="6a615-125">Írjon be egy értéket a Szabály neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6a615-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="6a615-126">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6a615-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6a615-127">A Lekérdezés neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6a615-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="6a615-128">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="6a615-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="6a615-129">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6a615-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="6a615-130">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6a615-130">Click Save.</span></span>
9. <span data-ttu-id="6a615-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6a615-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="6a615-132">Adjon meg egy Szállítói számlára vonatkozó irányelvet</span><span class="sxs-lookup"><span data-stu-id="6a615-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="6a615-133">Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvek pontra.</span><span class="sxs-lookup"><span data-stu-id="6a615-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="6a615-134">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6a615-134">Click New.</span></span>
3. <span data-ttu-id="6a615-135">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6a615-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="6a615-136">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6a615-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6a615-137">Csukja be vagy bontsa ki az Irányelv szervezetei szakaszt.</span><span class="sxs-lookup"><span data-stu-id="6a615-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="6a615-138">A fán válassza ki a „Contoso Szórakozás rendszer USA” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a615-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="6a615-139">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6a615-139">Click Add.</span></span>
8. <span data-ttu-id="6a615-140">Csukja be vagy bontsa ki az Irányelvszabályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="6a615-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="6a615-141">Kattintson az Irányelvszabályra.</span><span class="sxs-lookup"><span data-stu-id="6a615-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="6a615-142">Írjon be egy értéket a Irányelvszabály leírása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6a615-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="6a615-143">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="6a615-143">Click Filter.</span></span>
12. <span data-ttu-id="6a615-144">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6a615-144">Click Add.</span></span>
13. <span data-ttu-id="6a615-145">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="6a615-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="6a615-146">A Táblázat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6a615-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="6a615-147">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6a615-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="6a615-148">A Származtatott tábla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6a615-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="6a615-149">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6a615-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="6a615-150">A Mező mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6a615-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="6a615-151">Érték beírása a Mező mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6a615-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="6a615-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6a615-152">Close the page.</span></span>
21. <span data-ttu-id="6a615-153">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6a615-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="6a615-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6a615-154">Click OK.</span></span>
23. <span data-ttu-id="6a615-155">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6a615-155">Click OK.</span></span>
24. <span data-ttu-id="6a615-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6a615-156">Close the page.</span></span>
25. <span data-ttu-id="6a615-157">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6a615-157">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]