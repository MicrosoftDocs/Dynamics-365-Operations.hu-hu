---
title: Szállítói számla irányelveinek beállítása
description: Ez a témakör ismerteti a szállítói számlákkal kapcsolatos irányelvek beállítását.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72f017294c976dcd1b7ddda01ac9e39252f036d6
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250279"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="1b616-103">Szállítói számla irányelveinek beállítása</span><span class="sxs-lookup"><span data-stu-id="1b616-103">Set up vendor invoice policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1b616-104">Ez a témakör ismerteti a szállítói számlákkal kapcsolatos irányelvek beállítását.</span><span class="sxs-lookup"><span data-stu-id="1b616-104">This topic explains how to set up vendor invoice policies.</span></span> <span data-ttu-id="1b616-105">A Szállítói számlára vonatkozó irányelvek akkor futnak, amikor a szállítói számla oldal használatával ad fel egy szállítói számlát, és amikor megnyitja a szállítói számlára vonatkozó irányelv megszegéseinek lapját.</span><span class="sxs-lookup"><span data-stu-id="1b616-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="1b616-106">A szállítói számla munkafolyamatát is beállíthatja úgy, hogy a valahányszor számlát küld egy munkafolyamathoz, futtatja a szállítói számlára vonatkozó irányelveket.</span><span class="sxs-lookup"><span data-stu-id="1b616-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="1b616-107">A szállítói számla irányelvek nem vonatkoznak azokra a számlákra, amelyek a számlajegyzékben vagy a számlanaplóban jöttek létre.</span><span class="sxs-lookup"><span data-stu-id="1b616-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="1b616-108">A számlaegyeztetés érvényesítése nem használja a szállítói számla irányelveket, ehelyett egy Kötelezettségek paraméterei oldalt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="1b616-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="1b616-109">Ez a felvétel az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="1b616-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="1b616-110">A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="1b616-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="1b616-111">Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva.</span><span class="sxs-lookup"><span data-stu-id="1b616-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="1b616-112">Felkészülés a szállítói számlára vonatkozó irányelvek létrehozására</span><span class="sxs-lookup"><span data-stu-id="1b616-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="1b616-113">Ugorjon a **Navigációs ablaktábla > Modulok > Kötelezettségek > Beállítás > Kötelezettségek paraméterei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1b616-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="1b616-114">Kattintson a **Számlaegyeztetés** fülre.</span><span class="sxs-lookup"><span data-stu-id="1b616-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="1b616-115">Válassza ki vagy állítsa alaphelyzetbe a **Számlafejléc automatikus frissítése** állapot jelölőnégyzetét.</span><span class="sxs-lookup"><span data-stu-id="1b616-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="1b616-116">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-116">Select **OK**.</span></span>
5. <span data-ttu-id="1b616-117">A **Számlafeladás eltérésekkel** mezőben válasszon a lehetőségek közül.</span><span class="sxs-lookup"><span data-stu-id="1b616-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="1b616-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1b616-118">Close the page.</span></span>
7. <span data-ttu-id="1b616-119">Ugorjon a **Navigációs ablaktábla > Modulok > Kötelezettségek > Irányelv beállítása > Szállítói számla irányelvei** elemre.</span><span class="sxs-lookup"><span data-stu-id="1b616-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="1b616-120">Válassza ki a **Paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="1b616-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="1b616-121">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-121">Select **Add**.</span></span>
10. <span data-ttu-id="1b616-122">A kezdőlaphoz való visszatéréshez zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="1b616-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="1b616-123">Szállítói számla irányelvszabály-típusainak létrehozása szállítói számlákhoz</span><span class="sxs-lookup"><span data-stu-id="1b616-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="1b616-124">Ugorjon a **Navigációs ablaktábla > Modulok > Kötelezettségek > Irányelv beállítása > Szállítói számla irányelvszabály-típusai** elemre.</span><span class="sxs-lookup"><span data-stu-id="1b616-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="1b616-125">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-125">Select **New**.</span></span>
3. <span data-ttu-id="1b616-126">Töltse ki a **Szabály neve** és a **Leírás** mezőt.</span><span class="sxs-lookup"><span data-stu-id="1b616-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="1b616-127">A **Lekérdezés neve** mezőben válassza ki a legördülő gombot a keresés megnyitásához, majd válassza ki a kívánt rekordot.</span><span class="sxs-lookup"><span data-stu-id="1b616-127">In the **Query name** field, select the drop-down button to open the lookup, then selec the desired record.</span></span>
5. <span data-ttu-id="1b616-128">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-128">Select **Save**.</span></span>
6. <span data-ttu-id="1b616-129">A kezdőlaphoz való visszatéréshez zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="1b616-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="1b616-130">Adjon meg egy Szállítói számlára vonatkozó irányelvet</span><span class="sxs-lookup"><span data-stu-id="1b616-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="1b616-131">Ugorjon a **Navigációs ablaktábla > Modulok > Kötelezettségek > Irányelv beállítása > Szállítói számla irányelvei** elemre.</span><span class="sxs-lookup"><span data-stu-id="1b616-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="1b616-132">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-132">Select **New**.</span></span>
3. <span data-ttu-id="1b616-133">Töltse ki a **Név** és a **Leírás** mezőt.</span><span class="sxs-lookup"><span data-stu-id="1b616-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="1b616-134">Csukja be vagy bontsa ki az **Irányelv szervezetei** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="1b616-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="1b616-135">A fán válassza ki a **Contoso Entertainment System USA** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="1b616-136">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-136">Select **Add**.</span></span>
7. <span data-ttu-id="1b616-137">Csukja be vagy bontsa ki az **Irányelvszabályok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="1b616-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="1b616-138">Válassza ki az **Irányelvszabály létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="1b616-139">Írjon be egy értéket az **Irányelvszabály leírása** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1b616-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="1b616-140">Válassza ki a **Szűrő** elemet.</span><span class="sxs-lookup"><span data-stu-id="1b616-140">Select **Filter**.</span></span>
11. <span data-ttu-id="1b616-141">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-141">Select **Add**.</span></span> <span data-ttu-id="1b616-142">Válassza ki a kívánt rekordot.</span><span class="sxs-lookup"><span data-stu-id="1b616-142">Select the desired record.</span></span>
12. <span data-ttu-id="1b616-143">A **Táblában**, a **Származtatott táblában**és a **Mező** mezőben válassza ki vagy adja meg a beállításokat a legördülő menükből.</span><span class="sxs-lookup"><span data-stu-id="1b616-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="1b616-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1b616-144">Close the page.</span></span>
14. <span data-ttu-id="1b616-145">Adjon meg egy értéket a **Feltétel** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1b616-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="1b616-146">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-146">Select **OK**.</span></span>
16. <span data-ttu-id="1b616-147">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b616-147">Select **OK**.</span></span>
17. <span data-ttu-id="1b616-148">A kezdőlaphoz való visszatéréshez zárja be az oldalakat.</span><span class="sxs-lookup"><span data-stu-id="1b616-148">Close the pages to return to the home page.</span></span>

