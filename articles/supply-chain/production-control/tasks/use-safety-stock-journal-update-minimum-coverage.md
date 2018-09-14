--- 
title: "Használja a biztonsági készlet naplót, hogy frissítse a minimális fedezetet"
description: "Ez az eljárás bemutatja, hogyan számolja ki a minimális fedezet javaslatokat a már meglévő tranzakciók alapján és ezután frissítse a cikkfedezetet a javaslatokkal."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 7a6e217d476cedc0318c382e12b7dc2036e557c3
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="91112-103">Használja a biztonsági készlet naplót, hogy frissítse a minimális fedezetet</span><span class="sxs-lookup"><span data-stu-id="91112-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="91112-104">Ez az eljárás bemutatja, hogyan számolja ki a minimális fedezet javaslatokat a már meglévő tranzakciók alapján és ezután frissítse a cikkfedezetet a javaslatokkal.</span><span class="sxs-lookup"><span data-stu-id="91112-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="91112-105">Ebben az esetben a biztonsági készlet naplóját használja.</span><span class="sxs-lookup"><span data-stu-id="91112-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="91112-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="91112-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="91112-107">Ez a feladat a termeléstervezőnek van fenntartva, hogy segítse a minimális fedezet fenntartását.</span><span class="sxs-lookup"><span data-stu-id="91112-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="91112-108">Hozzon létre egy új biztonsági készlet napló nevet</span><span class="sxs-lookup"><span data-stu-id="91112-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="91112-109">Menjen a Biztonsági készlet naplók neveihez.</span><span class="sxs-lookup"><span data-stu-id="91112-109">Go to Safety stock journal names.</span></span>
2. <span data-ttu-id="91112-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91112-110">Click New.</span></span>
3. <span data-ttu-id="91112-111">A Név mezőbe írja be: típus „Anyag”.</span><span class="sxs-lookup"><span data-stu-id="91112-111">In the Name field, type 'Material'.</span></span>
4. <span data-ttu-id="91112-112">A Leírás mezőbe írja be: típus „Anyag”.</span><span class="sxs-lookup"><span data-stu-id="91112-112">In the Description field, type 'Material'.</span></span>
5. <span data-ttu-id="91112-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="91112-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="91112-114">Hozzon létre egy biztonsági készlet naplót</span><span class="sxs-lookup"><span data-stu-id="91112-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="91112-115">Menjen a Biztonsági készlet számításához.</span><span class="sxs-lookup"><span data-stu-id="91112-115">Go to Safety stock calculation.</span></span>
2. <span data-ttu-id="91112-116">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91112-116">Click New.</span></span>
3. <span data-ttu-id="91112-117">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="91112-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="91112-118">Válassza ki a létrehozott biztonsági napló nevet, például Anyag.</span><span class="sxs-lookup"><span data-stu-id="91112-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="91112-119">Kattintson a Sorok létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91112-119">Click Create lines.</span></span>
5. <span data-ttu-id="91112-120">Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="91112-120">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="91112-121">Állítsa a dátumot erre: „2015-01-02”.</span><span class="sxs-lookup"><span data-stu-id="91112-121">Set the date to '2015-01-02'.</span></span>  
6. <span data-ttu-id="91112-122">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="91112-122">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="91112-123">Állítsa a dátumot erre: „2015-12-30”.</span><span class="sxs-lookup"><span data-stu-id="91112-123">Set the date to '2015-12-30'.</span></span>  
7. <span data-ttu-id="91112-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91112-124">Click OK.</span></span>
    * <span data-ttu-id="91112-125">Ez hoz létre sorokat a készlettranzakciókkal rendelkező dimenziókhoz.</span><span class="sxs-lookup"><span data-stu-id="91112-125">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="91112-126">Javaslat számítása</span><span class="sxs-lookup"><span data-stu-id="91112-126">Calculate proposal</span></span>
1. <span data-ttu-id="91112-127">Kattintson a Javaslat számítására.</span><span class="sxs-lookup"><span data-stu-id="91112-127">Click Calculate proposal.</span></span>
2. <span data-ttu-id="91112-128">Válassza az Átlagos kiadás használata az átfutási idő alatt lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91112-128">Select the Use average issue during lead time option.</span></span>
3. <span data-ttu-id="91112-129">A szorzótényezőt állítsa „10”-re.</span><span class="sxs-lookup"><span data-stu-id="91112-129">Set Multiplication factor to '10'.</span></span>
    * <span data-ttu-id="91112-130">A Multiply tényező a javaslat beállításához használható.</span><span class="sxs-lookup"><span data-stu-id="91112-130">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="91112-131">Mivel a bemutató adatokban csak néhány tranzakció van, Önnek kell majd beállítania a tényezőt, hogy reális javaslatot kapjon.</span><span class="sxs-lookup"><span data-stu-id="91112-131">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="91112-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91112-132">Click OK.</span></span>
    * <span data-ttu-id="91112-133">Görgessen le, hogy megtalálja M0002 és M0003 értékeket.</span><span class="sxs-lookup"><span data-stu-id="91112-133">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="91112-134">Tekintse meg a Kiszámított minimum mennyiség oszlopot.</span><span class="sxs-lookup"><span data-stu-id="91112-134">View the Calculated minimum quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="91112-135">Frissítse a minimum mennyiséget</span><span class="sxs-lookup"><span data-stu-id="91112-135">Update minimum quantity</span></span>
1. <span data-ttu-id="91112-136">Az Új minimum mennyiség mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="91112-136">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="91112-137">Frissítse az Új minimum mennyiségét, hogy az megegyezzen a Számított minimális mennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="91112-137">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="91112-138">Ha a Számított minimum értéke nulla, megadhatja jövőbeli kívánt értékét.</span><span class="sxs-lookup"><span data-stu-id="91112-138">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="91112-139">Például megadhatja a Kiszámított minimum mennyiséget ebbe a mezőbe az M0002-höz, akié a 12-es raktár.</span><span class="sxs-lookup"><span data-stu-id="91112-139">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="91112-140">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="91112-140">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="91112-141">Például kiválaszthatja az M0002-őt, akié a 12-es raktár.</span><span class="sxs-lookup"><span data-stu-id="91112-141">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="91112-142">Az Új minimum mennyiség mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="91112-142">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="91112-143">Frissítse az Új minimum mennyiségét, hogy az megegyezzen a Számított minimális mennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="91112-143">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="91112-144">Ha a Számított minimum értéke nulla, megadhatja jövőbeli kívánt értékét.</span><span class="sxs-lookup"><span data-stu-id="91112-144">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="91112-145">Vigye fel az új minimum mennyiséget és ellenőrizze az eredményt</span><span class="sxs-lookup"><span data-stu-id="91112-145">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="91112-146">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91112-146">Click Post.</span></span>
2. <span data-ttu-id="91112-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91112-147">Click OK.</span></span>
3. <span data-ttu-id="91112-148">Kattintson a Cikkszám mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="91112-148">Click to follow the link in the Item number field.</span></span>
4. <span data-ttu-id="91112-149">Kattintson a Cikkszám mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="91112-149">Click to follow the link in the Item number field.</span></span>
5. <span data-ttu-id="91112-150">A Művelet panelen kattintson a Terv elemre.</span><span class="sxs-lookup"><span data-stu-id="91112-150">On the Action Pane, click Plan.</span></span>
6. <span data-ttu-id="91112-151">Kattintson a cikkfedezet elemre.</span><span class="sxs-lookup"><span data-stu-id="91112-151">Click Item coverage.</span></span>
    * <span data-ttu-id="91112-152">Fontos megjegyezni, hogy a minimum mennyiséget frissítettük, így most már a biztonsági készlet naplójában szereplő minimum mennyiséget tükrözi.</span><span class="sxs-lookup"><span data-stu-id="91112-152">Notice that the Minimum quantity has been updated with the new minimum quantity from the safety stock journal.</span></span>  


