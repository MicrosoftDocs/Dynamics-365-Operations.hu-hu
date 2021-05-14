---
title: Termékszám elnevezési rendszerének létrehozása konfigurált termékváltozatokhoz
description: Ez az eljárás bemutatja, hogyan állítható be termékszámozás-elnevezési rendszer konfigurált termékváltozatok számára, és hogyan rendelhető hozzá konfigurálható alaptermékhez.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ea30dc107213b1a2c6b2a109188066a6ea82159
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921011"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="49d1b-103">Termékszám elnevezési rendszerének létrehozása konfigurált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="49d1b-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="49d1b-104">Ez az eljárás bemutatja, hogyan állítható be termékszámozás-elnevezési rendszer konfigurált termékváltozatok számára, és hogyan rendelhető hozzá konfigurálható alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="49d1b-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="49d1b-105">Az eljárás emellett bemutatja, hogyan készíthető konfigurációelnevezési rendszer termékkonfigurációs modell összetevőjéhez.</span><span class="sxs-lookup"><span data-stu-id="49d1b-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="49d1b-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="49d1b-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="49d1b-107">Az új termékszám-elnevezési rendszer a D0004 alaptermékhez van rendelve.</span><span class="sxs-lookup"><span data-stu-id="49d1b-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="49d1b-108">Ezt a feladatot általában egy terméktervező végzi.</span><span class="sxs-lookup"><span data-stu-id="49d1b-108">This task would typically be done by a product designer.</span></span>

## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="49d1b-109">Termékszámozási rendszer létrehozása</span><span class="sxs-lookup"><span data-stu-id="49d1b-109">Create a product number nomenclature</span></span>

1. <span data-ttu-id="49d1b-110">Ugorjon a **Termékinformációk kezelése \> Beállítás \> Termék elnevezési rendszere** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="49d1b-110">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="49d1b-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-111">Select **New**.</span></span>
1. <span data-ttu-id="49d1b-112">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="49d1b-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="49d1b-113">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="49d1b-113">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="49d1b-114">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-114">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-115">Válassza az **Alaptermék száma** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-115">Select **Product master number**.</span></span>
1. <span data-ttu-id="49d1b-116">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-116">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-117">Válassza a **Szöveges állandó** elemet.</span><span class="sxs-lookup"><span data-stu-id="49d1b-117">Select **Text constant**.</span></span>
1. <span data-ttu-id="49d1b-118">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="49d1b-118">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="49d1b-119">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="49d1b-119">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="49d1b-120">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-120">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-121">**Konfiguráció** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="49d1b-121">Select **Configuration**.</span></span>
1. <span data-ttu-id="49d1b-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="49d1b-122">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="49d1b-123">Termékszámozási rendszer hozzárendelése az alaptermékhez</span><span class="sxs-lookup"><span data-stu-id="49d1b-123">Assign the product number nomenclature to a product master</span></span>

1. <span data-ttu-id="49d1b-124">Ugorjon a **Termékinformációk kezelése \> Termékek \> Alaptermékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="49d1b-124">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="49d1b-125">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="49d1b-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="49d1b-126">Például szűkítsen a **Termékszám** mezőre a „D” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="49d1b-126">For example, filter on the **Product number** field with a value of 'D'.</span></span>
1. <span data-ttu-id="49d1b-127">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="49d1b-127">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="49d1b-128">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="49d1b-128">Select **Edit**.</span></span>
1. <span data-ttu-id="49d1b-129">Válassza az *Igen* lehetőséget az **Elnevezési rendszer használata** mezőben.</span><span class="sxs-lookup"><span data-stu-id="49d1b-129">Select *Yes* in the **Use nomenclature** field.</span></span>
1. <span data-ttu-id="49d1b-130">A **Termékváltozat-számozási rendszer** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="49d1b-130">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
1. <span data-ttu-id="49d1b-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="49d1b-131">Close the page.</span></span>
1. <span data-ttu-id="49d1b-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="49d1b-132">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="49d1b-133">Elnevezési rendszer létrehozása egy termékkonfigurációs modell összetevőjéhez</span><span class="sxs-lookup"><span data-stu-id="49d1b-133">Create nomenclature for a product configuration model component</span></span>

1. <span data-ttu-id="49d1b-134">Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.</span><span class="sxs-lookup"><span data-stu-id="49d1b-134">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="49d1b-135">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="49d1b-135">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="49d1b-136">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="49d1b-136">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="49d1b-137">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="49d1b-137">Select **Edit**.</span></span>
1. <span data-ttu-id="49d1b-138">Válassza az *Igen* lehetőséget a **Konfiguráció elnevezési rendszerének használata** mezőben.</span><span class="sxs-lookup"><span data-stu-id="49d1b-138">Select *Yes* in the **Use configuration nomenclature** field.</span></span>
1. <span data-ttu-id="49d1b-139">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-139">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-140">Válassza az **Attribútumérték** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-140">Select **Attribute value**.</span></span>
1. <span data-ttu-id="49d1b-141">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="49d1b-141">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="49d1b-142">Az **Attribútum** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="49d1b-142">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="49d1b-143">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-143">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-144">Válassza a **Szöveges állandó** elemet.</span><span class="sxs-lookup"><span data-stu-id="49d1b-144">Select **Text constant**.</span></span>
1. <span data-ttu-id="49d1b-145">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="49d1b-145">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="49d1b-146">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="49d1b-146">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="49d1b-147">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-147">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-148">Válassza az **Attribútumérték** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-148">Select **Attribute value**.</span></span>
1. <span data-ttu-id="49d1b-149">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="49d1b-149">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="49d1b-150">Az **Attribútum** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="49d1b-150">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="49d1b-151">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-151">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-152">Válassza a **Szöveges állandó** elemet.</span><span class="sxs-lookup"><span data-stu-id="49d1b-152">Select **Text constant**.</span></span>
1. <span data-ttu-id="49d1b-153">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="49d1b-153">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="49d1b-154">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="49d1b-154">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="49d1b-155">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-155">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-156">Válassza az **Attribútumérték** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-156">Select **Attribute value**.</span></span>
1. <span data-ttu-id="49d1b-157">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="49d1b-157">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="49d1b-158">Az **Attribútum** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="49d1b-158">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="49d1b-159">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-159">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-160">Válassza a **Szöveges állandó** elemet.</span><span class="sxs-lookup"><span data-stu-id="49d1b-160">Select **Text constant**.</span></span>
1. <span data-ttu-id="49d1b-161">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="49d1b-161">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="49d1b-162">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="49d1b-162">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="49d1b-163">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-163">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-164">Válassza az **Attribútumérték** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-164">Select **Attribute value**.</span></span>
1. <span data-ttu-id="49d1b-165">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="49d1b-165">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="49d1b-166">Az **Attribútum** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="49d1b-166">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="49d1b-167">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-167">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-168">Válassza a **Szöveges állandó** elemet.</span><span class="sxs-lookup"><span data-stu-id="49d1b-168">Select **Text constant**.</span></span>
1. <span data-ttu-id="49d1b-169">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="49d1b-169">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="49d1b-170">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="49d1b-170">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="49d1b-171">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49d1b-171">Select **Add**.</span></span>
1. <span data-ttu-id="49d1b-172">Válassza ki a **Számsorozat értéke** elemet.</span><span class="sxs-lookup"><span data-stu-id="49d1b-172">Select **Number sequence value**.</span></span>
1. <span data-ttu-id="49d1b-173">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="49d1b-173">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="49d1b-174">A **Számsorrend** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="49d1b-174">In the **Number sequence** field, enter or select a value.</span></span>
1. <span data-ttu-id="49d1b-175">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="49d1b-175">Close the page.</span></span>
1. <span data-ttu-id="49d1b-176">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="49d1b-176">Close the page.</span></span>
1. <span data-ttu-id="49d1b-177">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="49d1b-177">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]