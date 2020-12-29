---
title: Használja a biztonsági készlet naplót, hogy frissítse a minimális fedezetet
description: Ez az eljárás bemutatja, hogyan számolja ki a minimális fedezet javaslatokat a már meglévő tranzakciók alapján és ezután frissítse a cikkfedezetet a javaslatokkal.
author: ChristianRytt
manager: tfehr
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d69daf3d307ba72ff6017d91849e3d22bd0bd85
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429748"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="9ca04-103">Használja a biztonsági készlet naplót, hogy frissítse a minimális fedezetet</span><span class="sxs-lookup"><span data-stu-id="9ca04-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9ca04-104">Ez az eljárás bemutatja, hogyan számolja ki a minimális fedezet javaslatokat a már meglévő tranzakciók alapján és ezután frissítse a cikkfedezetet a javaslatokkal.</span><span class="sxs-lookup"><span data-stu-id="9ca04-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="9ca04-105">Ebben az esetben a biztonsági készlet naplóját használja.</span><span class="sxs-lookup"><span data-stu-id="9ca04-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="9ca04-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="9ca04-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="9ca04-107">Ez a feladat a termeléstervezőnek van fenntartva, hogy segítse a minimális fedezet fenntartását.</span><span class="sxs-lookup"><span data-stu-id="9ca04-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="9ca04-108">Hozzon létre egy új biztonsági készlet napló nevet</span><span class="sxs-lookup"><span data-stu-id="9ca04-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="9ca04-109">A **Navigációs ablaktáblán** lépjen az **Alaptervezés > Beálítás > Biztonsági készlet naplójának nevei** elemre.</span><span class="sxs-lookup"><span data-stu-id="9ca04-109">In the **Navigation pane**, go to **Master planning > Setup > Safety stock journal names**.</span></span>
2. <span data-ttu-id="9ca04-110">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9ca04-110">Click **New**.</span></span>
3. <span data-ttu-id="9ca04-111">A **Név** mezőbe írja be: „Anyag”.</span><span class="sxs-lookup"><span data-stu-id="9ca04-111">In the **Name** field, type 'Material'.</span></span>
4. <span data-ttu-id="9ca04-112">A **Leírás** mezőbe írja be: „Anyag”.</span><span class="sxs-lookup"><span data-stu-id="9ca04-112">In the **Description** field, type 'Material'.</span></span>
5. <span data-ttu-id="9ca04-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9ca04-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="9ca04-114">Hozzon létre egy biztonsági készlet naplót</span><span class="sxs-lookup"><span data-stu-id="9ca04-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="9ca04-115">A **Navigációs ablaktáblán** lépjen az **Alaptervezés > Alaptervezés > Futtatás > Biztonsági készlet számítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="9ca04-115">In the **Navigation pane**, go to **Master planning > Master planning > Run > Safety stock calculation**.</span></span>
2. <span data-ttu-id="9ca04-116">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9ca04-116">Click **New**.</span></span>
3. <span data-ttu-id="9ca04-117">A **Név** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9ca04-117">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="9ca04-118">Válassza ki a létrehozott biztonsági napló nevet, például Anyag.</span><span class="sxs-lookup"><span data-stu-id="9ca04-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="9ca04-119">Kattintson a **Sorok létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ca04-119">Click **Create lines**.</span></span>
5. <span data-ttu-id="9ca04-120">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ca04-120">In the **From date** field, enter a date.</span></span>  
6. <span data-ttu-id="9ca04-121">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ca04-121">In the **To date** field, enter a date.</span></span>
7. <span data-ttu-id="9ca04-122">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9ca04-122">Click **OK**.</span></span> <span data-ttu-id="9ca04-123">Ez hoz létre sorokat a készlettranzakciókkal rendelkező dimenziókhoz.</span><span class="sxs-lookup"><span data-stu-id="9ca04-123">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="9ca04-124">Javaslat számítása</span><span class="sxs-lookup"><span data-stu-id="9ca04-124">Calculate proposal</span></span>
1. <span data-ttu-id="9ca04-125">Kattintson a **Javaslat számítása** pontra.</span><span class="sxs-lookup"><span data-stu-id="9ca04-125">Click **Calculate proposal**.</span></span>
2. <span data-ttu-id="9ca04-126">Válassza az **Átlagos kiadás használata az átfutási idő alatt** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ca04-126">Select the **Use average issue during lead time** option.</span></span>
3. <span data-ttu-id="9ca04-127">A **Szorzótényező** értékét állítsa „10”-re.</span><span class="sxs-lookup"><span data-stu-id="9ca04-127">Set **Multiplication factor** to '10'.</span></span> <span data-ttu-id="9ca04-128">A Multiply tényező a javaslat beállításához használható.</span><span class="sxs-lookup"><span data-stu-id="9ca04-128">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="9ca04-129">Mivel a bemutató adatokban csak néhány tranzakció van, Önnek kell majd beállítania a tényezőt, hogy reális javaslatot kapjon.</span><span class="sxs-lookup"><span data-stu-id="9ca04-129">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="9ca04-130">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9ca04-130">Click **OK**.</span></span> <span data-ttu-id="9ca04-131">Görgessen le, hogy megtalálja M0002 és M0003 értékeket.</span><span class="sxs-lookup"><span data-stu-id="9ca04-131">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="9ca04-132">Tekintse meg a **Kiszámított minimum** mennyiségoszlopot.</span><span class="sxs-lookup"><span data-stu-id="9ca04-132">View the **Calculated minimum** quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="9ca04-133">Frissítse a minimum mennyiséget</span><span class="sxs-lookup"><span data-stu-id="9ca04-133">Update minimum quantity</span></span>
1. <span data-ttu-id="9ca04-134">Az **Új minimális mennyiség** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="9ca04-134">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="9ca04-135">Frissítse az Új minimum mennyiségét, hogy az megegyezzen a Számított minimális mennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="9ca04-135">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="9ca04-136">Ha a Számított minimum értéke nulla, megadhatja jövőbeli kívánt értékét.</span><span class="sxs-lookup"><span data-stu-id="9ca04-136">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="9ca04-137">Például megadhatja a Kiszámított minimum mennyiséget ebbe a mezőbe az M0002-höz, akié a 12-es raktár.</span><span class="sxs-lookup"><span data-stu-id="9ca04-137">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="9ca04-138">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9ca04-138">In the list, find and select the desired record.</span></span> <span data-ttu-id="9ca04-139">Például kiválaszthatja az M0002-őt, akié a 12-es raktár.</span><span class="sxs-lookup"><span data-stu-id="9ca04-139">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="9ca04-140">Az **Új minimális mennyiség** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="9ca04-140">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="9ca04-141">Frissítse az Új minimum mennyiségét, hogy az megegyezzen a Számított minimális mennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="9ca04-141">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="9ca04-142">Ha a Számított minimum értéke nulla, megadhatja jövőbeli kívánt értékét.</span><span class="sxs-lookup"><span data-stu-id="9ca04-142">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="9ca04-143">Vigye fel az új minimum mennyiséget és ellenőrizze az eredményt</span><span class="sxs-lookup"><span data-stu-id="9ca04-143">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="9ca04-144">Kattintson a **Bejegyzés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ca04-144">Click **Post**.</span></span>
2. <span data-ttu-id="9ca04-145">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9ca04-145">Click **OK**.</span></span>
3. <span data-ttu-id="9ca04-146">Kattintson a **Cikkszám** mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9ca04-146">Click to follow the link in the **Item number** field.</span></span>
4. <span data-ttu-id="9ca04-147">Kattintson a **Cikkszám** mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9ca04-147">Click to follow the link in the **Item number** field.</span></span>
5. <span data-ttu-id="9ca04-148">A **Művelet panelen** kattintson a Tervezés elemre.</span><span class="sxs-lookup"><span data-stu-id="9ca04-148">On the **Action Pane**, click Plan.</span></span>
6. <span data-ttu-id="9ca04-149">Kattintson a **Cikkfedezet** elemre.</span><span class="sxs-lookup"><span data-stu-id="9ca04-149">Click **Item coverage**.</span></span> <span data-ttu-id="9ca04-150">Fontos megjegyezni, hogy a **Minimális mennyiség** frissült, így most már a biztonsági készlet naplójában szereplő minimum mennyiséget tükrözi.</span><span class="sxs-lookup"><span data-stu-id="9ca04-150">Notice that the **Minimum quantity** has been updated with the new minimum quantity from the safety stock journal.</span></span>  

