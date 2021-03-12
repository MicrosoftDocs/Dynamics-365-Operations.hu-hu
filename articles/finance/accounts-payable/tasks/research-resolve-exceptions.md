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
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 727676d060b77633d4ff4f31dabbd7825ca19aca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971778"
---
# <a name="research-or-resolve-exceptions"></a><span data-ttu-id="bf846-103">Kivételek kivizsgálása/feloldása</span><span class="sxs-lookup"><span data-stu-id="bf846-103">Research or resolve exceptions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bf846-104">A Szállítói számlára vonatkozó irányelvek akkor futnak, amikor a szállítói számla oldal használatával ad fel egy szállítói számlát, és amikor megnyitja a szállítói számlára vonatkozó irányelv megszegéseinek lapját.</span><span class="sxs-lookup"><span data-stu-id="bf846-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="bf846-105">A szállítói számla munkafolyamatát is beállíthatja úgy, hogy a valahányszor számlát küld egy munkafolyamathoz, futtatja a szállítói számlára vonatkozó irányelveket.</span><span class="sxs-lookup"><span data-stu-id="bf846-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="bf846-106">A szállítói számla irányelvek nem vonatkoznak azokra a számlákra, amelyek a számlajegyzékben vagy a számlanaplóban jöttek létre.</span><span class="sxs-lookup"><span data-stu-id="bf846-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="bf846-107">A számlaegyeztetés érvényesítése nem használja a szállítói számla irányelveket, ehelyett egy Kötelezettségek paraméterei oldalt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="bf846-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="bf846-108">Ez a felvétel az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="bf846-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="bf846-109">A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="bf846-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="bf846-110">Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva.</span><span class="sxs-lookup"><span data-stu-id="bf846-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="bf846-111">Felkészülés a szállítói számlára vonatkozó irányelvek létrehozására</span><span class="sxs-lookup"><span data-stu-id="bf846-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="bf846-112">Ugorjon a Kötelezettségek > Beállítás > Kötelezettségek paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="bf846-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="bf846-113">Kattintson a Számlaegyeztetés fülre.</span><span class="sxs-lookup"><span data-stu-id="bf846-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="bf846-114">Válassza ki vagy állítsa alaphelyzetbe a Számlafejléc állapotának automatikus frissítése jelölőnégyzetét.</span><span class="sxs-lookup"><span data-stu-id="bf846-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="bf846-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="bf846-115">Click OK.</span></span>
5. <span data-ttu-id="bf846-116">A Számlafeladás eltérésekkel mezőben válasszon a lehetőségek közül.</span><span class="sxs-lookup"><span data-stu-id="bf846-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="bf846-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bf846-117">Close the page.</span></span>
7. <span data-ttu-id="bf846-118">Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvek pontra.</span><span class="sxs-lookup"><span data-stu-id="bf846-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="bf846-119">Kattintson a Paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bf846-119">Click Parameters.</span></span>
9. <span data-ttu-id="bf846-120">Majd a btnAdd lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bf846-120">Click btnAdd.</span></span>
10. <span data-ttu-id="bf846-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bf846-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="bf846-122">Szállítói számla irányelvszabály-típusainak létrehozása szállítói számlákhoz</span><span class="sxs-lookup"><span data-stu-id="bf846-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="bf846-123">Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvszabály típusok pontra.</span><span class="sxs-lookup"><span data-stu-id="bf846-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="bf846-124">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bf846-124">Click New.</span></span>
3. <span data-ttu-id="bf846-125">Írjon be egy értéket a Szabály neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bf846-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="bf846-126">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bf846-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="bf846-127">A Lekérdezés neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="bf846-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="bf846-128">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="bf846-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="bf846-129">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="bf846-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="bf846-130">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bf846-130">Click Save.</span></span>
9. <span data-ttu-id="bf846-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bf846-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="bf846-132">Adjon meg egy Szállítói számlára vonatkozó irányelvet</span><span class="sxs-lookup"><span data-stu-id="bf846-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="bf846-133">Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvek pontra.</span><span class="sxs-lookup"><span data-stu-id="bf846-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="bf846-134">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bf846-134">Click New.</span></span>
3. <span data-ttu-id="bf846-135">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bf846-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="bf846-136">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bf846-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="bf846-137">Csukja be vagy bontsa ki az Irányelv szervezetei szakaszt.</span><span class="sxs-lookup"><span data-stu-id="bf846-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="bf846-138">A fán válassza ki a „Contoso Szórakozás rendszer USA” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bf846-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="bf846-139">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="bf846-139">Click Add.</span></span>
8. <span data-ttu-id="bf846-140">Csukja be vagy bontsa ki az Irányelvszabályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="bf846-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="bf846-141">Kattintson az Irányelvszabályra.</span><span class="sxs-lookup"><span data-stu-id="bf846-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="bf846-142">Írjon be egy értéket a Irányelvszabály leírása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bf846-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="bf846-143">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="bf846-143">Click Filter.</span></span>
12. <span data-ttu-id="bf846-144">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="bf846-144">Click Add.</span></span>
13. <span data-ttu-id="bf846-145">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="bf846-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="bf846-146">A Táblázat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="bf846-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="bf846-147">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="bf846-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="bf846-148">A Származtatott tábla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="bf846-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="bf846-149">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="bf846-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="bf846-150">A Mező mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="bf846-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="bf846-151">Érték beírása a Mező mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bf846-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="bf846-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bf846-152">Close the page.</span></span>
21. <span data-ttu-id="bf846-153">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bf846-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="bf846-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="bf846-154">Click OK.</span></span>
23. <span data-ttu-id="bf846-155">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="bf846-155">Click OK.</span></span>
24. <span data-ttu-id="bf846-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bf846-156">Close the page.</span></span>
25. <span data-ttu-id="bf846-157">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bf846-157">Close the page.</span></span>

