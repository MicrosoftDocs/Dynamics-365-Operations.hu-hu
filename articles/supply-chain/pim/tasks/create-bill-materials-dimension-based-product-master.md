---
title: A dimenzión alapuló alaptermékre vonatkozó anyagjegyzék létrehozása
description: Ehhez az eljáráshoz el kellett végeznie az előző 4 útmutatót a nyolc rögzítés sorrendjében.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13053dd87242963586678b46c64493feb3383c4c
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920705"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="feb08-103">A dimenzión alapuló alaptermékre vonatkozó anyagjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="feb08-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="feb08-104">Ehhez az eljáráshoz el kellett végeznie az előző 4 útmutatót a nyolc rögzítés sorrendjében.</span><span class="sxs-lookup"><span data-stu-id="feb08-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="feb08-105">Az első 4 rögzítés beállítja azt az adatot, ami szükséges az eljárás végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="feb08-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="feb08-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="feb08-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="feb08-107">Ezt a feladatot általában a termék tervező kezeli.</span><span class="sxs-lookup"><span data-stu-id="feb08-107">This task is typically handled by the product designer.</span></span>

## <a name="select-the-product"></a><span data-ttu-id="feb08-108">Válassza ki a terméket</span><span class="sxs-lookup"><span data-stu-id="feb08-108">Select the product</span></span>

1. <span data-ttu-id="feb08-109">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="feb08-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="feb08-110">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="feb08-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="feb08-111">Keresse meg azt a dimenzión alapuló konfiguráció technológiájával kiadott alapterméket, amelyet az itt látható sorrendben hozott létre az első feladat útmutatójában.</span><span class="sxs-lookup"><span data-stu-id="feb08-111">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
1. <span data-ttu-id="feb08-112">A Műveleti ablaktáblán kattintson a **Mérnök** elemre.</span><span class="sxs-lookup"><span data-stu-id="feb08-112">On the Action Pane, select **Engineer**.</span></span>
1. <span data-ttu-id="feb08-113">**DBJ-verziók** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="feb08-113">Select **BOM versions**.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="feb08-114">Hozzon létre új anyagjegyzéket és anyagjegyzék-verziót</span><span class="sxs-lookup"><span data-stu-id="feb08-114">Create new BOM and BOM version</span></span>

1. <span data-ttu-id="feb08-115">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="feb08-115">Select **New**.</span></span>
1. <span data-ttu-id="feb08-116">Válassza ki a **DBJ és DBJ-verzió** elemet.</span><span class="sxs-lookup"><span data-stu-id="feb08-116">Select **BOM and BOM version**.</span></span>
1. <span data-ttu-id="feb08-117">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="feb08-117">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="feb08-118">Hely beállítása</span><span class="sxs-lookup"><span data-stu-id="feb08-118">Setting a site</span></span>  
    * <span data-ttu-id="feb08-119">Ebben az eljárásban nem állítunk be egy adott helyet az anyagjegyzékre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="feb08-119">In this procedure we don't set a specific site for the BOM.</span></span>  
1. <span data-ttu-id="feb08-120">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="feb08-120">Select **OK**.</span></span>
1. <span data-ttu-id="feb08-121">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="feb08-121">Select **New**.</span></span>
    * <span data-ttu-id="feb08-122">Ebben az eljárásban négy sort adunk az Anyagjegyzékhez.</span><span class="sxs-lookup"><span data-stu-id="feb08-122">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="feb08-123">Két sor a kábel beállításokat és két sor pedig kabinetfájl beállításokat jelöli.</span><span class="sxs-lookup"><span data-stu-id="feb08-123">Two lines represent cable options and two lines represent cabinet options.</span></span>  
1. <span data-ttu-id="feb08-124">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="feb08-124">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="feb08-125">Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="feb08-125">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="feb08-126">Válassza ki a A0001 -es cikkszámot, HDMI 6'-os kábelt.</span><span class="sxs-lookup"><span data-stu-id="feb08-126">Select item number A0001, HDMI 6' Cables.</span></span>  
1. <span data-ttu-id="feb08-127">A **Konfigurációs csoport** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="feb08-127">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="feb08-128">Válassza ki a 4-es útmutatóban létrehozott Kábel konfigurációs csoportot ebben a sorozatban.</span><span class="sxs-lookup"><span data-stu-id="feb08-128">Select the cable configuration group created in guide 4 in this sequence.</span></span>  
1. <span data-ttu-id="feb08-129">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="feb08-129">Select **New**.</span></span>
    * <span data-ttu-id="feb08-130">Válassza ki a A0002-es cikkszámot, HDMI 12'-os kábelt.</span><span class="sxs-lookup"><span data-stu-id="feb08-130">Select item number A0002, HDMI 12' Cables.</span></span>  
1. <span data-ttu-id="feb08-131">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="feb08-131">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="feb08-132">Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="feb08-132">In the **Item number** field, enter or select a value.</span></span>
1. <span data-ttu-id="feb08-133">A **Konfigurációs csoport** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="feb08-133">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="feb08-134">Válassza ki újból a Kábel konfigurációs csoportot.</span><span class="sxs-lookup"><span data-stu-id="feb08-134">Select the cable configuration group again.</span></span>  
1. <span data-ttu-id="feb08-135">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="feb08-135">Select **New**.</span></span>
1. <span data-ttu-id="feb08-136">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="feb08-136">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="feb08-137">Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="feb08-137">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="feb08-138">Válassza ki a D0002 cikkszámú kabinetfájlt.</span><span class="sxs-lookup"><span data-stu-id="feb08-138">Select item number D0002 Cabinet.</span></span>  
1. <span data-ttu-id="feb08-139">A **Konfigurációs csoport** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="feb08-139">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="feb08-140">Válassza ki a kabinetfájl konfigurációs csoportot ezen anyagjegyzék sorára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="feb08-140">Select the cabinet configuration group for this BOM line.</span></span>  
1. <span data-ttu-id="feb08-141">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="feb08-141">Select **New**.</span></span>
1. <span data-ttu-id="feb08-142">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="feb08-142">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="feb08-143">Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="feb08-143">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="feb08-144">Válassza ki az M0007 cikkszámú StandardCabinet elemet az utolsó Anyagjegyzék soraként.</span><span class="sxs-lookup"><span data-stu-id="feb08-144">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
1. <span data-ttu-id="feb08-145">A **Konfigurációs csoport** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="feb08-145">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="feb08-146">Válassza ki a Kabinetfájl konfigurációs csoportot az utolsó anyagjegyzék sorára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="feb08-146">Select the Cabinet configuration group for the last BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="feb08-147">Jóváhagyás és aktiválás</span><span class="sxs-lookup"><span data-stu-id="feb08-147">Approve and activate</span></span>

1. <span data-ttu-id="feb08-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="feb08-148">Close the page.</span></span>
1. <span data-ttu-id="feb08-149">Válassza a **Jóváhagyás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="feb08-149">Select **Approve**.</span></span>
1. <span data-ttu-id="feb08-150">A **Jóváhagyó** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="feb08-150">In the **Approved by** field, enter or select a value.</span></span>
1. <span data-ttu-id="feb08-151">A **Szeretné az anyagjegyzéket is jóváhagyni?** kérdésre válaszolva válassza ki az *Igen* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="feb08-151">Select *Yes* in the **Do you also want to approve the bill of materials?** field.</span></span>
1. <span data-ttu-id="feb08-152">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="feb08-152">Select **OK**.</span></span>
1. <span data-ttu-id="feb08-153">Válassza az **Aktiválás** lehetõséget.</span><span class="sxs-lookup"><span data-stu-id="feb08-153">Select **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]