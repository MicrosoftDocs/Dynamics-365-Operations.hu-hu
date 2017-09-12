--- 
title: "A dimenzión alapuló alaptermékre vonatkozó anyagjegyzék létrehozása"
description: "Ehhez az eljáráshoz el kellett végeznie az előző 4 útmutatót a nyolc rögzítés sorrendjében."
author: YuyuScheller
manager: AnnBe
ms.date: 06/21/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4f9f9473d0872d68571b87409b93e0cf5455364c
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="c3118-103">A dimenzión alapuló alaptermékre vonatkozó anyagjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="c3118-103">Create a bill of materials for a dimension-based product master</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c3118-104">Ehhez az eljáráshoz el kellett végeznie az előző 4 útmutatót a nyolc rögzítés sorrendjében.</span><span class="sxs-lookup"><span data-stu-id="c3118-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="c3118-105">Az első 4 rögzítés beállítja azt az adatot, ami szükséges az eljárás végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="c3118-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="c3118-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="c3118-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c3118-107">Ezt a feladatot általában a termék tervező kezeli.</span><span class="sxs-lookup"><span data-stu-id="c3118-107">This task is typically handled by the product designer.</span></span>


## <a name="select-the-product"></a><span data-ttu-id="c3118-108">Válassza ki a terméket</span><span class="sxs-lookup"><span data-stu-id="c3118-108">Select the product</span></span>
1. <span data-ttu-id="c3118-109">Kattintson a Kiadott termék karbantartása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3118-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="c3118-110">Kattintson a Kibocsátott termék lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3118-110">Click Released products.</span></span>
3. <span data-ttu-id="c3118-111">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c3118-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c3118-112">Keresse meg azt a dimenzión alapuló konfiguráció technológiájával kiadott alapterméket, amelyet az itt látható sorrendben hozott létre az első feladat útmutatójában.</span><span class="sxs-lookup"><span data-stu-id="c3118-112">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
4. <span data-ttu-id="c3118-113">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="c3118-113">On the Action Pane, click Engineer.</span></span>
5. <span data-ttu-id="c3118-114">Kattintson az Anyagjegyzék verziókra.</span><span class="sxs-lookup"><span data-stu-id="c3118-114">Click BOM versions.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="c3118-115">Hozzon létre új anyagjegyzéket és anyagjegyzék-verziót</span><span class="sxs-lookup"><span data-stu-id="c3118-115">Create new BOM and BOM version</span></span>
1. <span data-ttu-id="c3118-116">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3118-116">Click New.</span></span>
2. <span data-ttu-id="c3118-117">Kattintson az Anyagjegyzék és az Anyagjegyzék verzió elemre.</span><span class="sxs-lookup"><span data-stu-id="c3118-117">Click BOM and BOM version.</span></span>
3. <span data-ttu-id="c3118-118">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c3118-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="c3118-119">Hely beállítása</span><span class="sxs-lookup"><span data-stu-id="c3118-119">Setting a site</span></span>  
    * <span data-ttu-id="c3118-120">Ebben az eljárásban nem állítunk be egy adott helyet az anyagjegyzékre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="c3118-120">In this procedure we don't set a specific site for the BOM.</span></span>  
4. <span data-ttu-id="c3118-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c3118-121">Click OK.</span></span>
5. <span data-ttu-id="c3118-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3118-122">Click New.</span></span>
    * <span data-ttu-id="c3118-123">Ebben az eljárásban négy sort adunk az Anyagjegyzékhez.</span><span class="sxs-lookup"><span data-stu-id="c3118-123">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="c3118-124">Két sor a kábel beállításokat és két sor pedig kabinetfájl beállításokat jelöli.</span><span class="sxs-lookup"><span data-stu-id="c3118-124">Two lines represent cable options and two lines represent cabinet options.</span></span>  
6. <span data-ttu-id="c3118-125">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c3118-125">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="c3118-126">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c3118-126">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="c3118-127">Válassza ki a A0001 -es cikkszámot, HDMI 6'-os kábelt.</span><span class="sxs-lookup"><span data-stu-id="c3118-127">Select item number A0001, HDMI 6' Cables.</span></span>  
8. <span data-ttu-id="c3118-128">A Konfigurációs csoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c3118-128">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="c3118-129">Válassza ki a 4-es útmutatóban létrehozott Kábel konfigurációs csoportot ebben a sorozatban.</span><span class="sxs-lookup"><span data-stu-id="c3118-129">Select the Cable configuration group created in guide 4 in this sequence.</span></span>  
9. <span data-ttu-id="c3118-130">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3118-130">Click New.</span></span>
    * <span data-ttu-id="c3118-131">Válassza ki a A0002-es cikkszámot, HDMI 12'-os kábelt.</span><span class="sxs-lookup"><span data-stu-id="c3118-131">Select item number A0002, HDMI 12' Cables.</span></span>  
10. <span data-ttu-id="c3118-132">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c3118-132">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="c3118-133">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c3118-133">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="c3118-134">A Konfigurációs csoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c3118-134">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="c3118-135">Válassza ki újból a Kábel konfigurációs csoportot.</span><span class="sxs-lookup"><span data-stu-id="c3118-135">Select the Cable configuration group again.</span></span>  
13. <span data-ttu-id="c3118-136">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3118-136">Click New.</span></span>
14. <span data-ttu-id="c3118-137">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c3118-137">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="c3118-138">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c3118-138">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="c3118-139">Válassza ki a D0002 cikkszámú kabinetfájlt.</span><span class="sxs-lookup"><span data-stu-id="c3118-139">Select item number D0002 Cabinet.</span></span>  
16. <span data-ttu-id="c3118-140">A Konfigurációs csoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c3118-140">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="c3118-141">Válassza ki a Kabinetfájl konfigurációs csoportot ezen anyagjegyzék sorára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="c3118-141">Select the Cabinet configuration group for this BOM line.</span></span>  
17. <span data-ttu-id="c3118-142">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3118-142">Click New.</span></span>
18. <span data-ttu-id="c3118-143">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c3118-143">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="c3118-144">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c3118-144">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="c3118-145">Válassza ki az M0007 cikkszámú StandardCabinet elemet az utolsó Anyagjegyzék soraként.</span><span class="sxs-lookup"><span data-stu-id="c3118-145">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
20. <span data-ttu-id="c3118-146">A Konfigurációs csoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c3118-146">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="c3118-147">Válassza ki a Kabinetfájl konfigurációs csoportot az utolsó anyagjegyzék sorára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="c3118-147">Select the Cabinet configuration group for the laste BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="c3118-148">Jóváhagyás és aktiválás</span><span class="sxs-lookup"><span data-stu-id="c3118-148">Approve and activate</span></span>
1. <span data-ttu-id="c3118-149">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c3118-149">Close the page.</span></span>
2. <span data-ttu-id="c3118-150">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3118-150">Click Approve.</span></span>
3. <span data-ttu-id="c3118-151">A Jóváhagyó mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c3118-151">In the Approved by field, enter or select a value.</span></span>
4. <span data-ttu-id="c3118-152">A „Szeretné az anyagjegyzéket is jóváhagyni?” kérdésre válaszolva válassza ki az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c3118-152">Select Yes in the Do you also want to approve the bill of materials? field.</span></span>
5. <span data-ttu-id="c3118-153">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c3118-153">Click OK.</span></span>
6. <span data-ttu-id="c3118-154">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="c3118-154">Click Activate.</span></span>


