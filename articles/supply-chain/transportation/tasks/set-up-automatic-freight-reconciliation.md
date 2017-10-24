--- 
title: "Automatikus fuvarlevél-egyeztetés beállítása"
description: "Ez az eljárás bemutatja, hogyan lehet beállítani az adatokat az automatikus fuvaregyeztetéshez."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 97f0c4d8fe06ab2fc252b9543cb688306214c79f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-automatic-freight-reconciliation"></a><span data-ttu-id="f1e03-103">Automatikus fuvarlevél-egyeztetés beállítása</span><span class="sxs-lookup"><span data-stu-id="f1e03-103">Set up automatic freight reconciliation</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f1e03-104">Ez az eljárás bemutatja, hogyan lehet beállítani az adatokat az automatikus fuvaregyeztetéshez.</span><span class="sxs-lookup"><span data-stu-id="f1e03-104">This procedure shows how to set up data for automatic freight reconciliation.</span></span> <span data-ttu-id="f1e03-105">Ezt általában a raktár vezetője végzi el.</span><span class="sxs-lookup"><span data-stu-id="f1e03-105">This is typically done by a warehouse manager.</span></span> <span data-ttu-id="f1e03-106">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="f1e03-106">You can use this procedure in demo data company USMF.</span></span>


## <a name="set-up-the-freight-bill-type"></a><span data-ttu-id="f1e03-107">Fuvarlevél típusának beállítása</span><span class="sxs-lookup"><span data-stu-id="f1e03-107">Set up the freight bill type</span></span>
1. <span data-ttu-id="f1e03-108">Ugrás a Szállításkezelés > Beállítás > Fuvaregyeztetés > Fuvarlevél típusa elemhez.</span><span class="sxs-lookup"><span data-stu-id="f1e03-108">Go to Transportation management > Setup > Freight reconciliation > Freight bill type.</span></span>
    * <span data-ttu-id="f1e03-109">A fuvarlevél típusa határozza meg, hogyan kell egyeztetni a fuvarleveleket és a szállítói számlákat.</span><span class="sxs-lookup"><span data-stu-id="f1e03-109">The freight bill type defines how freight bills and carrier invoices  should be matched.</span></span>  
2. <span data-ttu-id="f1e03-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f1e03-110">Click New.</span></span>
3. <span data-ttu-id="f1e03-111">Adjon meg egy értéket a Fuvarlevél típusa mezőben.</span><span class="sxs-lookup"><span data-stu-id="f1e03-111">In the Freight bill type field, type a value.</span></span>
4. <span data-ttu-id="f1e03-112">A Kalkulátorszerelvény mezőbe írja be a következőt: Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer.</span><span class="sxs-lookup"><span data-stu-id="f1e03-112">In the Engine assembly field, type 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'.</span></span>
    * <span data-ttu-id="f1e03-113">Ez a szabványos szállításkezelés-egyeztetési kalkulátorkódtár.</span><span class="sxs-lookup"><span data-stu-id="f1e03-113">This is the standard Transportation management matching engine code library.</span></span>  
5. <span data-ttu-id="f1e03-114">A Kalkulátorosztály mezőbe írja be a következőt: Microsoft.Dynamics.Ax.Tms.dll.</span><span class="sxs-lookup"><span data-stu-id="f1e03-114">In the Engine class field, type 'Microsoft.Dynamics.Ax.Tms.dll'.</span></span>
    * <span data-ttu-id="f1e03-115">Ez a szabványos szállításkezelés-egyeztetési kalkulátorosztály.</span><span class="sxs-lookup"><span data-stu-id="f1e03-115">This is the standard Transportation management matching engine class.</span></span>  
6. <span data-ttu-id="f1e03-116">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f1e03-116">Click New.</span></span>
7. <span data-ttu-id="f1e03-117">A Leírás mezőben válassza ki az értéket, amelynek egyeznie kell a fuvarlevélen és a szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="f1e03-117">In the Description field, choose the value that should match on the freight bill and the carrier invoice.</span></span>  
8. <span data-ttu-id="f1e03-118">Válassza az Igen lehetőséget az Egyezés szükséges mezőben.</span><span class="sxs-lookup"><span data-stu-id="f1e03-118">In the Match required field, select 'Yes'.</span></span>
    * <span data-ttu-id="f1e03-119">Ha ebben a mezőben az Igen értéket állítja be, ez azt jelenti, hogy a Leírás mezőben kiválasztott értéknek egyeznie kell mind a fuvarlevélen, mind a szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="f1e03-119">If you set this field to Yes this means that the value selected in the Description field needs to match on both the freight bill and the carrier invoice.</span></span> <span data-ttu-id="f1e03-120">Ha a beállítása Nem, a mező üres lehet ezek egyikén.</span><span class="sxs-lookup"><span data-stu-id="f1e03-120">If you set it to No, the field can be blank on one of these.</span></span>  
9. <span data-ttu-id="f1e03-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f1e03-121">Click Save.</span></span>

## <a name="set-up-the-freight-bill-type-assignment"></a><span data-ttu-id="f1e03-122">Fuvarlevéltípus-hozzárendelés beállítása</span><span class="sxs-lookup"><span data-stu-id="f1e03-122">Set up the freight bill type assignment</span></span>
1. <span data-ttu-id="f1e03-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f1e03-123">Close the page.</span></span>
2. <span data-ttu-id="f1e03-124">Ugrás a Szállításkezelés > Beállítás > Fuvaregyeztetés > Fuvarlevéltípus-hozzárendelések elemhez.</span><span class="sxs-lookup"><span data-stu-id="f1e03-124">Go to Transportation management > Setup > Freight reconciliation > Freight bill type assignments.</span></span>
    * <span data-ttu-id="f1e03-125">A fuvarlevél típusú hozzárendelés segítségével megadhatja, hogy melyik fuvarlevéltípus használatos egy adott szállítóhoz.</span><span class="sxs-lookup"><span data-stu-id="f1e03-125">The freight bill type assignment is used to specify which freight bill type is used for a particular carrier.</span></span>   
3. <span data-ttu-id="f1e03-126">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f1e03-126">Click New.</span></span>
4. <span data-ttu-id="f1e03-127">A Mód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f1e03-127">In the Mode field, enter or select a value.</span></span>
5. <span data-ttu-id="f1e03-128">A Szállítmányozó mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f1e03-128">In the Shipping carrier field, enter or select a value.</span></span>
6. <span data-ttu-id="f1e03-129">A Fuvarlevél típusa mezőben válassza ki a korábban létrehozott fuvarlevéltípust.</span><span class="sxs-lookup"><span data-stu-id="f1e03-129">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
7. <span data-ttu-id="f1e03-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f1e03-130">Close the page.</span></span>

## <a name="set-up-the-audit-master"></a><span data-ttu-id="f1e03-131">Alapvizsgálat beállítása</span><span class="sxs-lookup"><span data-stu-id="f1e03-131">Set up the audit master</span></span>
1. <span data-ttu-id="f1e03-132">Ugrás a Szállításkezelés > Beállítás > Fuvaregyeztetés > Alapvizsgálat elemhez.</span><span class="sxs-lookup"><span data-stu-id="f1e03-132">Go to Transportation management > Setup > Freight reconciliation > Audit master.</span></span>
    * <span data-ttu-id="f1e03-133">Az alapvizsgálati beállítás adja meg az automatikus szállítási egyeztetés tűréshatárait.</span><span class="sxs-lookup"><span data-stu-id="f1e03-133">The audit master defines the tolerance limits for automatic freight reconciliation.</span></span> <span data-ttu-id="f1e03-134">Itt adható meg, mekkora pénzösszegeltérés lehet a fuvarlevélen és a szállítói számlán ahhoz, hogy továbbra is megtörténjen az egyeztetés.</span><span class="sxs-lookup"><span data-stu-id="f1e03-134">It specifies by how much the monetary amounts on the freight bill and the carrier invoice can differ and still allow reconciliation to occur.</span></span> <span data-ttu-id="f1e03-135">Továbbá az eltérések kezelésének módját is meghatározza.</span><span class="sxs-lookup"><span data-stu-id="f1e03-135">It also defines how to handle discrepancies.</span></span>  
2. <span data-ttu-id="f1e03-136">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f1e03-136">Click New.</span></span>
3. <span data-ttu-id="f1e03-137">Az Alapvizsgálat azonosítója mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f1e03-137">In the Audit master ID field, type a value.</span></span>
4. <span data-ttu-id="f1e03-138">A Szállítmányozó mezőben válassza ki ugyanazt a szállítmányozót, amelyet korábban már kiválasztott.</span><span class="sxs-lookup"><span data-stu-id="f1e03-138">In the Shipping carrier  field, select the same shipping carrier as you did earlier.</span></span>
5. <span data-ttu-id="f1e03-139">A Fuvarlevél típusa mezőben válassza ki a korábban létrehozott fuvarlevéltípust.</span><span class="sxs-lookup"><span data-stu-id="f1e03-139">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
6. <span data-ttu-id="f1e03-140">Bontsa ki a Tűréshatár szakaszt.</span><span class="sxs-lookup"><span data-stu-id="f1e03-140">Expand the Tolerance section.</span></span>
7. <span data-ttu-id="f1e03-141">A Minimális tűrési szint mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="f1e03-141">In the Minimum tolerance level field, enter a number.</span></span>
8. <span data-ttu-id="f1e03-142">A Maximális tűrési szint mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="f1e03-142">In the Maximum tolerance level field, enter a number.</span></span>
9. <span data-ttu-id="f1e03-143">Bontsa ki az Eredmény szakaszt.</span><span class="sxs-lookup"><span data-stu-id="f1e03-143">Expand the Result section.</span></span>
10. <span data-ttu-id="f1e03-144">A Túlfizetés okkódja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f1e03-144">In the Overpayment reason code field, enter or select a value.</span></span>
    * <span data-ttu-id="f1e03-145">Ha a pénzösszegek különböznek a fuvarlevélen és a szállítói számlán, a túl- és alulfizetés okkódok megadják a számlákat, ahol nyilvántartásba kell venni a különbséget, amennyiben a különbség a tűrési szinteken belül van.</span><span class="sxs-lookup"><span data-stu-id="f1e03-145">If the monetary amounts differ on the freight bill and the carrier invoice, the overpayment and underpayment reason codes specify the accounts that the difference should be registered on, as long as the difference is within the tolerance levels.</span></span>  
11. <span data-ttu-id="f1e03-146">Az Alulfizetés okkódja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f1e03-146">In the Underpayment reason code field, enter or select a value.</span></span>
12. <span data-ttu-id="f1e03-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f1e03-147">Close the page.</span></span>

