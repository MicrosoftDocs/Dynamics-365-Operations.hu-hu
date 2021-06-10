---
title: Lépésikonok és -címek hozzárendelése a Warehouse Management mobilalkalmazáshoz
description: Ez a témakör azt ismerteti, hogyan lehet lépésikonokat és -címeket hozzárendelni a Warehouse Management mobilalkalmazás új vagy testre szabott feladatfolyamataihoz.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9523492d766669e6c38579fba7b5ddd6b3d282fc
ms.sourcegitcommit: c53de2c09b9296b41653e739178edf29f79e0679
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049364"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="6e20e-103">Lépésikonok és -címek hozzárendelése a Warehouse Management mobilalkalmazáshoz</span><span class="sxs-lookup"><span data-stu-id="6e20e-103">Assign step icons and titles for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e20e-104">Ez a témakör azt ismerteti, hogyan lehet lépésikonokat és lépéscímeket hozzárendelni a Warehouse Management mobilalkalmazás új vagy testre szabott feladatfolyamataihoz.</span><span class="sxs-lookup"><span data-stu-id="6e20e-104">This topic describes how to assign step icons and step titles for new or customized task flows for the Warehouse Management mobile app.</span></span>

<span data-ttu-id="6e20e-105">A következő ábrákon az látható, hogyan jelennek meg a lépésikonok és -címek a Warehouse Management mobilalkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="6e20e-105">The following illustrations shows how step icons and titles appear in the Warehouse Management mobile app.</span></span>

<span data-ttu-id="6e20e-106">![Példa lépésikonra és lépéscímre a Warehouse Management mobilalkalmazásban](media/step-icon-example.png "Példa lépésikonra és lépéscímre a Warehouse Management mobilalkalmazásban")</span><span class="sxs-lookup"><span data-stu-id="6e20e-106">![Example of a step icon and a step title in the Warehouse Management mobile app](media/step-icon-example.png "Example of a step icon and a step title in the Warehouse Management mobile app")</span></span>

## <a name="turn-on-this-feature-in-your-system"></a><span data-ttu-id="6e20e-107">A funkció bekapcsolása a rendszerben</span><span class="sxs-lookup"><span data-stu-id="6e20e-107">Turn on this feature in your system</span></span>

<span data-ttu-id="6e20e-108">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="6e20e-108">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="6e20e-109">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításait a funkció állapotának ellenőrzéséhez, és bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="6e20e-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="6e20e-110">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="6e20e-110">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6e20e-111">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="6e20e-111">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6e20e-112">**Funkciónév:** *Felhasználói beállítások, ikonok és lépéscímek az új raktári alkalmazáshoz*</span><span class="sxs-lookup"><span data-stu-id="6e20e-112">**Feature name:** *User settings, icons, and step titles for the new warehouse app*</span></span>

## <a name="standard-step-ids-classes-and-icons"></a><span data-ttu-id="6e20e-113">Szabványos lépések azonosítói, osztályai és ikonjai</span><span class="sxs-lookup"><span data-stu-id="6e20e-113">Standard step IDs, classes, and icons</span></span>

<span data-ttu-id="6e20e-114">Egy feladatfolyamat mindegyik lépését egy lépésazonosító azonosítja, és mindegyik lépésazonosítóhoz egy adott lépésosztály tartozik.</span><span class="sxs-lookup"><span data-stu-id="6e20e-114">Each step in a task flow is identified by a step ID, and each step ID has a corresponding step class.</span></span> <span data-ttu-id="6e20e-115">A lépésikon és -cím minden lépésosztályban meg van határozva.</span><span class="sxs-lookup"><span data-stu-id="6e20e-115">The step icon and title are specified in each step class.</span></span>

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a><span data-ttu-id="6e20e-116">Lépésazonosítók és lépésosztályok</span><span class="sxs-lookup"><span data-stu-id="6e20e-116">Step IDs and step classes</span></span>

<span data-ttu-id="6e20e-117">A következő táblázatban az aktuálisan elérhető összes lépésazonosító és a hozzá tartozó lépésosztály látható.</span><span class="sxs-lookup"><span data-stu-id="6e20e-117">The following table lists every step ID that is currently available, and its corresponding step class.</span></span> <span data-ttu-id="6e20e-118">Az elsődleges beviteli mező vezérlőneve használatos lépésazonosítóként.</span><span class="sxs-lookup"><span data-stu-id="6e20e-118">The control name of the primary input field is used as the step ID.</span></span>

<span data-ttu-id="6e20e-119">A lépésazonosítók és -osztályok használatát bemutató példára vonatkozóan tekintse meg a `WHSMobileAppStepInfoBuilder.stepId()` metódus implementációját a cikk későbbi részében: [Példa: Lépésikonok és -címek hozzárendelése egyéni folyamatokhoz](#example).</span><span class="sxs-lookup"><span data-stu-id="6e20e-119">For an example that shows how these step IDs and classes are used, see the implementation of the `WHSMobileAppStepInfoBuilder.stepId()` method in the [Example: Assign step icons and titles for a custom flow](#example) section later in this topic.</span></span>

| <span data-ttu-id="6e20e-120">Lépésazonosító</span><span class="sxs-lookup"><span data-stu-id="6e20e-120">Step ID</span></span> | <span data-ttu-id="6e20e-121">Lépés osztálya</span><span class="sxs-lookup"><span data-stu-id="6e20e-121">Step Class</span></span> |
|-|-|
| <span data-ttu-id="6e20e-122">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="6e20e-122">BatchDisposition</span></span> | <span data-ttu-id="6e20e-123">WHSMobileAppStepBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="6e20e-123">WHSMobileAppStepBatchDisposition</span></span> |
| <span data-ttu-id="6e20e-124">Fuvarozó</span><span class="sxs-lookup"><span data-stu-id="6e20e-124">Carrier</span></span> | <span data-ttu-id="6e20e-125">WHSMobileAppStepCarrier</span><span class="sxs-lookup"><span data-stu-id="6e20e-125">WHSMobileAppStepCarrier</span></span> |
| <span data-ttu-id="6e20e-126">CatchWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-126">CatchWeight</span></span> | <span data-ttu-id="6e20e-127">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-127">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="6e20e-128">CatchWeightQtyOutboundWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-128">CatchWeightQtyOutboundWeight</span></span> | <span data-ttu-id="6e20e-129">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-129">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="6e20e-130">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="6e20e-130">CatchWeightTag</span></span> | <span data-ttu-id="6e20e-131">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="6e20e-131">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="6e20e-132">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-132">CatchWeightTagWeight</span></span> | <span data-ttu-id="6e20e-133">WHSMobileAppStepCatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-133">WHSMobileAppStepCatchWeightTagWeight</span></span> |
| <span data-ttu-id="6e20e-134">ChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="6e20e-134">ChangeWarehouseSuccess</span></span> | <span data-ttu-id="6e20e-135">WHSMobileAppStepChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="6e20e-135">WHSMobileAppStepChangeWarehouseSuccess</span></span> |
| <span data-ttu-id="6e20e-136">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="6e20e-136">CheckDigit</span></span> | <span data-ttu-id="6e20e-137">WHSMobileAppStepCheckDigit</span><span class="sxs-lookup"><span data-stu-id="6e20e-137">WHSMobileAppStepCheckDigit</span></span> |
| <span data-ttu-id="6e20e-138">ClusterId</span><span class="sxs-lookup"><span data-stu-id="6e20e-138">ClusterId</span></span> | <span data-ttu-id="6e20e-139">WHSMobileAppStepClusterId</span><span class="sxs-lookup"><span data-stu-id="6e20e-139">WHSMobileAppStepClusterId</span></span> |
| <span data-ttu-id="6e20e-140">ClusterPickQtyVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-140">ClusterPickQtyVerification</span></span> | <span data-ttu-id="6e20e-141">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-141">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="6e20e-142">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="6e20e-142">ClusterPosition</span></span> | <span data-ttu-id="6e20e-143">WHSMobileAppStepClusterPosition</span><span class="sxs-lookup"><span data-stu-id="6e20e-143">WHSMobileAppStepClusterPosition</span></span> |
| <span data-ttu-id="6e20e-144">ConfigId</span><span class="sxs-lookup"><span data-stu-id="6e20e-144">ConfigId</span></span> | <span data-ttu-id="6e20e-145">WHSMobileAppStepConfigId</span><span class="sxs-lookup"><span data-stu-id="6e20e-145">WHSMobileAppStepConfigId</span></span> |
| <span data-ttu-id="6e20e-146">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="6e20e-146">Confirmation</span></span> | <span data-ttu-id="6e20e-147">WHSMobileAppStepConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-147">WHSMobileAppStepConfirmation</span></span> |
| <span data-ttu-id="6e20e-148">ConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-148">ConsolidateFromLicensePlateId</span></span> | <span data-ttu-id="6e20e-149">WHSMobileAppStepConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-149">WHSMobileAppStepConsolidateFromLicensePlateId</span></span> |
| <span data-ttu-id="6e20e-150">ConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-150">ConsolidateLPConfirmation</span></span> | <span data-ttu-id="6e20e-151">WHSMobileAppStepConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-151">WHSMobileAppStepConsolidateLPConfirmation</span></span> |
| <span data-ttu-id="6e20e-152">ConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-152">ConsolidateToLicensePlateId</span></span> | <span data-ttu-id="6e20e-153">WHSMobileAppStepConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-153">WHSMobileAppStepConsolidateToLicensePlateId</span></span> |
| <span data-ttu-id="6e20e-154">ContainerType</span><span class="sxs-lookup"><span data-stu-id="6e20e-154">ContainerType</span></span> | <span data-ttu-id="6e20e-155">WHSMobileAppStepContainerType</span><span class="sxs-lookup"><span data-stu-id="6e20e-155">WHSMobileAppStepContainerType</span></span> |
| <span data-ttu-id="6e20e-156">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="6e20e-156">CountingReasonCode</span></span> | <span data-ttu-id="6e20e-157">WHSMobileAppStepCountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="6e20e-157">WHSMobileAppStepCountingReasonCode</span></span> |
| <span data-ttu-id="6e20e-158">CycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="6e20e-158">CycleCountingAddLPOrFinish</span></span> | <span data-ttu-id="6e20e-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="6e20e-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span></span> |
| <span data-ttu-id="6e20e-160">CycleCountQty1</span><span class="sxs-lookup"><span data-stu-id="6e20e-160">CycleCountQty1</span></span> | <span data-ttu-id="6e20e-161">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-161">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="6e20e-162">CycleCountQty2</span><span class="sxs-lookup"><span data-stu-id="6e20e-162">CycleCountQty2</span></span> | <span data-ttu-id="6e20e-163">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-163">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="6e20e-164">CycleCountQty3</span><span class="sxs-lookup"><span data-stu-id="6e20e-164">CycleCountQty3</span></span> | <span data-ttu-id="6e20e-165">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-165">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="6e20e-166">CycleCountQty4</span><span class="sxs-lookup"><span data-stu-id="6e20e-166">CycleCountQty4</span></span> | <span data-ttu-id="6e20e-167">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-167">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="6e20e-168">Disposition</span><span class="sxs-lookup"><span data-stu-id="6e20e-168">Disposition</span></span> | <span data-ttu-id="6e20e-169">WHSMobileAppStepDisposition</span><span class="sxs-lookup"><span data-stu-id="6e20e-169">WHSMobileAppStepDisposition</span></span> |
| <span data-ttu-id="6e20e-170">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-170">DriverCheckInConfirmation</span></span> | <span data-ttu-id="6e20e-171">WHSMobileAppStepDriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-171">WHSMobileAppStepDriverCheckInConfirmation</span></span> |
| <span data-ttu-id="6e20e-172">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="6e20e-172">DriverCheckInId</span></span> | <span data-ttu-id="6e20e-173">WHSMobileAppStepDriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="6e20e-173">WHSMobileAppStepDriverCheckInId</span></span> |
| <span data-ttu-id="6e20e-174">DriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-174">DriverCheckOutConfirmation</span></span> | <span data-ttu-id="6e20e-175">WHSMobileAppStepDriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-175">WHSMobileAppStepDriverCheckOutConfirmation</span></span> |
| <span data-ttu-id="6e20e-176">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="6e20e-176">DriverCheckOutId</span></span> | <span data-ttu-id="6e20e-177">WHSMobileAppStepDriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="6e20e-177">WHSMobileAppStepDriverCheckOutId</span></span> |
| <span data-ttu-id="6e20e-178">ExpDate</span><span class="sxs-lookup"><span data-stu-id="6e20e-178">ExpDate</span></span> | <span data-ttu-id="6e20e-179">WHSMobileAppStepExpDate</span><span class="sxs-lookup"><span data-stu-id="6e20e-179">WHSMobileAppStepExpDate</span></span> |
| <span data-ttu-id="6e20e-180">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="6e20e-180">FromBatchDisposition</span></span> | <span data-ttu-id="6e20e-181">WHSMobileAppStepFromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="6e20e-181">WHSMobileAppStepFromBatchDisposition</span></span> |
| <span data-ttu-id="6e20e-182">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="6e20e-182">FromInventoryStatus</span></span> | <span data-ttu-id="6e20e-183">WHSMobileAppStepInventoryStatusFrom</span><span class="sxs-lookup"><span data-stu-id="6e20e-183">WHSMobileAppStepInventoryStatusFrom</span></span> |
| <span data-ttu-id="6e20e-184">FullQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-184">FullQty</span></span> | <span data-ttu-id="6e20e-185">WHSMobileAppStepFullQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-185">WHSMobileAppStepFullQty</span></span> |
| <span data-ttu-id="6e20e-186">InboundPut</span><span class="sxs-lookup"><span data-stu-id="6e20e-186">InboundPut</span></span> | <span data-ttu-id="6e20e-187">WHSMobileAppStepInboundPut</span><span class="sxs-lookup"><span data-stu-id="6e20e-187">WHSMobileAppStepInboundPut</span></span> |
| <span data-ttu-id="6e20e-188">InventBatchId</span><span class="sxs-lookup"><span data-stu-id="6e20e-188">InventBatchId</span></span> | <span data-ttu-id="6e20e-189">WHSMobileAppStepBatch</span><span class="sxs-lookup"><span data-stu-id="6e20e-189">WHSMobileAppStepBatch</span></span> |
| <span data-ttu-id="6e20e-190">InventColorId</span><span class="sxs-lookup"><span data-stu-id="6e20e-190">InventColorId</span></span> | <span data-ttu-id="6e20e-191">WHSMobileAppStepInventColorId</span><span class="sxs-lookup"><span data-stu-id="6e20e-191">WHSMobileAppStepInventColorId</span></span> |
| <span data-ttu-id="6e20e-192">InventLocation</span><span class="sxs-lookup"><span data-stu-id="6e20e-192">InventLocation</span></span> | <span data-ttu-id="6e20e-193">WHSMobileAppStepInventLocation</span><span class="sxs-lookup"><span data-stu-id="6e20e-193">WHSMobileAppStepInventLocation</span></span> |
| <span data-ttu-id="6e20e-194">InventLocationId</span><span class="sxs-lookup"><span data-stu-id="6e20e-194">InventLocationId</span></span> | <span data-ttu-id="6e20e-195">WHSMobileAppStepWarehouse</span><span class="sxs-lookup"><span data-stu-id="6e20e-195">WHSMobileAppStepWarehouse</span></span> |
| <span data-ttu-id="6e20e-196">InventSerialId</span><span class="sxs-lookup"><span data-stu-id="6e20e-196">InventSerialId</span></span> | <span data-ttu-id="6e20e-197">WHSMobileAppStepInventSerialId</span><span class="sxs-lookup"><span data-stu-id="6e20e-197">WHSMobileAppStepInventSerialId</span></span> |
| <span data-ttu-id="6e20e-198">InventSizeId</span><span class="sxs-lookup"><span data-stu-id="6e20e-198">InventSizeId</span></span> | <span data-ttu-id="6e20e-199">WHSMobileAppStepInventSizeId</span><span class="sxs-lookup"><span data-stu-id="6e20e-199">WHSMobileAppStepInventSizeId</span></span> |
| <span data-ttu-id="6e20e-200">InventStatusId</span><span class="sxs-lookup"><span data-stu-id="6e20e-200">InventStatusId</span></span> | <span data-ttu-id="6e20e-201">WHSMobileAppStepInventStatus</span><span class="sxs-lookup"><span data-stu-id="6e20e-201">WHSMobileAppStepInventStatus</span></span> |
| <span data-ttu-id="6e20e-202">InventStyleId</span><span class="sxs-lookup"><span data-stu-id="6e20e-202">InventStyleId</span></span> | <span data-ttu-id="6e20e-203">WHSMobileAppStepInventStyleId</span><span class="sxs-lookup"><span data-stu-id="6e20e-203">WHSMobileAppStepInventStyleId</span></span> |
| <span data-ttu-id="6e20e-204">InventVersionId</span><span class="sxs-lookup"><span data-stu-id="6e20e-204">InventVersionId</span></span> | <span data-ttu-id="6e20e-205">WHSMobileAppStepInventVersionId</span><span class="sxs-lookup"><span data-stu-id="6e20e-205">WHSMobileAppStepInventVersionId</span></span> |
| <span data-ttu-id="6e20e-206">ItemId</span><span class="sxs-lookup"><span data-stu-id="6e20e-206">ItemId</span></span> | <span data-ttu-id="6e20e-207">WHSMobileAppStepItem</span><span class="sxs-lookup"><span data-stu-id="6e20e-207">WHSMobileAppStepItem</span></span> |
| <span data-ttu-id="6e20e-208">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="6e20e-208">ITMContainerID</span></span> | <span data-ttu-id="6e20e-209">ITMMobileAppStepContainerId</span><span class="sxs-lookup"><span data-stu-id="6e20e-209">ITMMobileAppStepContainerId</span></span> |
| <span data-ttu-id="6e20e-210">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="6e20e-210">ITMShipmentID</span></span> | <span data-ttu-id="6e20e-211">ITMMobileAppStepShipmentId</span><span class="sxs-lookup"><span data-stu-id="6e20e-211">ITMMobileAppStepShipmentId</span></span> |
| <span data-ttu-id="6e20e-212">KanbanCardId</span><span class="sxs-lookup"><span data-stu-id="6e20e-212">KanbanCardId</span></span> | <span data-ttu-id="6e20e-213">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="6e20e-213">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="6e20e-214">KanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="6e20e-214">KanbanCardToEmpty</span></span> | <span data-ttu-id="6e20e-215">WHSMobileAppStepKanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="6e20e-215">WHSMobileAppStepKanbanCardToEmpty</span></span> |
| <span data-ttu-id="6e20e-216">KanbanOrCardId</span><span class="sxs-lookup"><span data-stu-id="6e20e-216">KanbanOrCardId</span></span> | <span data-ttu-id="6e20e-217">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="6e20e-217">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="6e20e-218">LicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-218">LicensePlateId</span></span> | <span data-ttu-id="6e20e-219">WHSMobileAppStepLicensePlate</span><span class="sxs-lookup"><span data-stu-id="6e20e-219">WHSMobileAppStepLicensePlate</span></span> |
| <span data-ttu-id="6e20e-220">LoadId</span><span class="sxs-lookup"><span data-stu-id="6e20e-220">LoadId</span></span> | <span data-ttu-id="6e20e-221">WHSMobileAppStepLoadId</span><span class="sxs-lookup"><span data-stu-id="6e20e-221">WHSMobileAppStepLoadId</span></span> |
| <span data-ttu-id="6e20e-222">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="6e20e-222">LocationLicensePlatePosition</span></span> | <span data-ttu-id="6e20e-223">WHSMobileAppStepLocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="6e20e-223">WHSMobileAppStepLocationLicensePlatePosition</span></span> |
| <span data-ttu-id="6e20e-224">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-224">LocOrLP</span></span> | <span data-ttu-id="6e20e-225">WHSMobileAppStepLocOrLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-225">WHSMobileAppStepLocOrLP</span></span> |
| <span data-ttu-id="6e20e-226">LocOrLP_From</span><span class="sxs-lookup"><span data-stu-id="6e20e-226">LocOrLP_From</span></span> | <span data-ttu-id="6e20e-227">WHSMobileAppStepLocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="6e20e-227">WHSMobileAppStepLocOrLPFrom</span></span> |
| <span data-ttu-id="6e20e-228">LocOrLP_To</span><span class="sxs-lookup"><span data-stu-id="6e20e-228">LocOrLP_To</span></span> | <span data-ttu-id="6e20e-229">WHSMobileAppStepLocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="6e20e-229">WHSMobileAppStepLocOrLPTo</span></span> |
| <span data-ttu-id="6e20e-230">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="6e20e-230">LocOrLPCheck</span></span> | <span data-ttu-id="6e20e-231">WHSMobileAppStepLocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="6e20e-231">WHSMobileAppStepLocOrLPCheck</span></span> |
| <span data-ttu-id="6e20e-232">LocVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-232">LocVerification</span></span> | <span data-ttu-id="6e20e-233">WHSMobileAppStepLocVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-233">WHSMobileAppStepLocVerification</span></span> |
| <span data-ttu-id="6e20e-234">LPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="6e20e-234">LPAdjustIn</span></span> | <span data-ttu-id="6e20e-235">WHSMobileAppStepLPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="6e20e-235">WHSMobileAppStepLPAdjustIn</span></span> |
| <span data-ttu-id="6e20e-236">LPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-236">LPBreakChildLP</span></span> | <span data-ttu-id="6e20e-237">WHSMobileAppStepLPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-237">WHSMobileAppStepLPBreakChildLP</span></span> |
| <span data-ttu-id="6e20e-238">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-238">LPBreakParentLP</span></span> | <span data-ttu-id="6e20e-239">WHSMobileAppStepLPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-239">WHSMobileAppStepLPBreakParentLP</span></span> |
| <span data-ttu-id="6e20e-240">LPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-240">LPBuildChildLP</span></span> | <span data-ttu-id="6e20e-241">WHSMobileAppStepLPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-241">WHSMobileAppStepLPBuildChildLP</span></span> |
| <span data-ttu-id="6e20e-242">LPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-242">LPBuildParentLP</span></span> | <span data-ttu-id="6e20e-243">WHSMobileAppStepLPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-243">WHSMobileAppStepLPBuildParentLP</span></span> |
| <span data-ttu-id="6e20e-244">LPVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-244">LPVerification</span></span> | <span data-ttu-id="6e20e-245">WHSMobileAppStepLPVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-245">WHSMobileAppStepLPVerification</span></span> |
| <span data-ttu-id="6e20e-246">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="6e20e-246">MergeContainerId</span></span> | <span data-ttu-id="6e20e-247">WHSMobileAppStepMergeContainerId</span><span class="sxs-lookup"><span data-stu-id="6e20e-247">WHSMobileAppStepMergeContainerId</span></span> |
| <span data-ttu-id="6e20e-248">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="6e20e-248">MixedLPLineNum</span></span> | <span data-ttu-id="6e20e-249">WHSMobileAppStepMixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="6e20e-249">WHSMobileAppStepMixedLPLineNum</span></span> |
| <span data-ttu-id="6e20e-250">MobileDeviceQueueMessageCollectionIdentifierId</span><span class="sxs-lookup"><span data-stu-id="6e20e-250">MobileDeviceQueueMessageCollectionIdentifierId</span></span> | <span data-ttu-id="6e20e-251">WHSMobileAppStepSelectOrder</span><span class="sxs-lookup"><span data-stu-id="6e20e-251">WHSMobileAppStepSelectOrder</span></span> |
| <span data-ttu-id="6e20e-252">MovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="6e20e-252">MovementConfirmCancel</span></span> | <span data-ttu-id="6e20e-253">WHSMobileAppStepMovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="6e20e-253">WHSMobileAppStepMovementConfirmCancel</span></span> |
| <span data-ttu-id="6e20e-254">NewCaptureWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-254">NewCaptureWeight</span></span> | <span data-ttu-id="6e20e-255">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-255">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="6e20e-256">NewQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-256">NewQty</span></span> | <span data-ttu-id="6e20e-257">WHSMobileAppStepNewQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-257">WHSMobileAppStepNewQty</span></span> |
| <span data-ttu-id="6e20e-258">OutboundCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="6e20e-258">OutboundCatchWeightTag</span></span> | <span data-ttu-id="6e20e-259">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="6e20e-259">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="6e20e-260">OutboundPut</span><span class="sxs-lookup"><span data-stu-id="6e20e-260">OutboundPut</span></span> | <span data-ttu-id="6e20e-261">WHSMobileAppStepOutboundPut</span><span class="sxs-lookup"><span data-stu-id="6e20e-261">WHSMobileAppStepOutboundPut</span></span> |
| <span data-ttu-id="6e20e-262">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-262">OutboundWeight</span></span> | <span data-ttu-id="6e20e-263">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-263">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="6e20e-264">OverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="6e20e-264">OverridePutNewLocation</span></span> | <span data-ttu-id="6e20e-265">WHSMobileAppStepOverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="6e20e-265">WHSMobileAppStepOverridePutNewLocation</span></span> |
| <span data-ttu-id="6e20e-266">PieceByPieceConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-266">PieceByPieceConfirmation</span></span> | <span data-ttu-id="6e20e-267">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-267">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="6e20e-268">POLineNum</span><span class="sxs-lookup"><span data-stu-id="6e20e-268">POLineNum</span></span> | <span data-ttu-id="6e20e-269">WHSMobileAppStepPOLineNum</span><span class="sxs-lookup"><span data-stu-id="6e20e-269">WHSMobileAppStepPOLineNum</span></span> |
| <span data-ttu-id="6e20e-270">BRszám</span><span class="sxs-lookup"><span data-stu-id="6e20e-270">PONum</span></span> | <span data-ttu-id="6e20e-271">WHSMobileAppStepPONum</span><span class="sxs-lookup"><span data-stu-id="6e20e-271">WHSMobileAppStepPONum</span></span> |
| <span data-ttu-id="6e20e-272">PositionFull</span><span class="sxs-lookup"><span data-stu-id="6e20e-272">PositionFull</span></span> | <span data-ttu-id="6e20e-273">WHSMobileAppStepPositionFull</span><span class="sxs-lookup"><span data-stu-id="6e20e-273">WHSMobileAppStepPositionFull</span></span> |
| <span data-ttu-id="6e20e-274">PositionFullQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-274">PositionFullQty</span></span> | <span data-ttu-id="6e20e-275">WHSMobileAppStepPositionFullQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-275">WHSMobileAppStepPositionFullQty</span></span> |
| <span data-ttu-id="6e20e-276">Hatóanyag-tartalom</span><span class="sxs-lookup"><span data-stu-id="6e20e-276">Potency</span></span> | <span data-ttu-id="6e20e-277">WHSMobileAppStepPotency</span><span class="sxs-lookup"><span data-stu-id="6e20e-277">WHSMobileAppStepPotency</span></span> |
| <span data-ttu-id="6e20e-278">PrinterName</span><span class="sxs-lookup"><span data-stu-id="6e20e-278">PrinterName</span></span> | <span data-ttu-id="6e20e-279">WHSMobileAppStepPrinterName</span><span class="sxs-lookup"><span data-stu-id="6e20e-279">WHSMobileAppStepPrinterName</span></span> |
| <span data-ttu-id="6e20e-280">ProdId</span><span class="sxs-lookup"><span data-stu-id="6e20e-280">ProdId</span></span> | <span data-ttu-id="6e20e-281">WHSMobileAppStepProdId</span><span class="sxs-lookup"><span data-stu-id="6e20e-281">WHSMobileAppStepProdId</span></span> |
| <span data-ttu-id="6e20e-282">ProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-282">ProdLastPalletConfirmation</span></span> | <span data-ttu-id="6e20e-283">WHSMobileAppStepProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-283">WHSMobileAppStepProdLastPalletConfirmation</span></span> |
| <span data-ttu-id="6e20e-284">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-284">ProductConfirmation</span></span> | <span data-ttu-id="6e20e-285">WHSMobileAppStepProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-285">WHSMobileAppStepProductConfirmation</span></span> |
| <span data-ttu-id="6e20e-286">ProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-286">ProductionScrapConfirmation</span></span> | <span data-ttu-id="6e20e-287">WHSMobileAppStepProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-287">WHSMobileAppStepProductionScrapConfirmation</span></span> |
| <span data-ttu-id="6e20e-288">Eltárolás</span><span class="sxs-lookup"><span data-stu-id="6e20e-288">Put</span></span> | <span data-ttu-id="6e20e-289">WHSMobileAppStepPut</span><span class="sxs-lookup"><span data-stu-id="6e20e-289">WHSMobileAppStepPut</span></span> |
| <span data-ttu-id="6e20e-290">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="6e20e-290">PutawayClusterId</span></span> | <span data-ttu-id="6e20e-291">WHSMobileAppStepPutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="6e20e-291">WHSMobileAppStepPutawayClusterId</span></span> |
| <span data-ttu-id="6e20e-292">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="6e20e-292">Qty</span></span> | <span data-ttu-id="6e20e-293">WHSMobileAppStepQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-293">WHSMobileAppStepQty</span></span> |
| <span data-ttu-id="6e20e-294">QtyAdjust</span><span class="sxs-lookup"><span data-stu-id="6e20e-294">QtyAdjust</span></span> | <span data-ttu-id="6e20e-295">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="6e20e-295">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="6e20e-296">QtyShort</span><span class="sxs-lookup"><span data-stu-id="6e20e-296">QtyShort</span></span> | <span data-ttu-id="6e20e-297">WHSMobileAppStepQtyShort</span><span class="sxs-lookup"><span data-stu-id="6e20e-297">WHSMobileAppStepQtyShort</span></span> |
| <span data-ttu-id="6e20e-298">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="6e20e-298">QtyToConsume</span></span> | <span data-ttu-id="6e20e-299">WHSMobileAppStepQtyToConsume</span><span class="sxs-lookup"><span data-stu-id="6e20e-299">WHSMobileAppStepQtyToConsume</span></span> |
| <span data-ttu-id="6e20e-300">QtyToPick</span><span class="sxs-lookup"><span data-stu-id="6e20e-300">QtyToPick</span></span> | <span data-ttu-id="6e20e-301">WHSMobileAppStepQtyToPick</span><span class="sxs-lookup"><span data-stu-id="6e20e-301">WHSMobileAppStepQtyToPick</span></span> |
| <span data-ttu-id="6e20e-302">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="6e20e-302">QtyToPut</span></span> | <span data-ttu-id="6e20e-303">WHSMobileAppStepQtyToPut</span><span class="sxs-lookup"><span data-stu-id="6e20e-303">WHSMobileAppStepQtyToPut</span></span> |
| <span data-ttu-id="6e20e-304">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="6e20e-304">QtyToScrap</span></span> | <span data-ttu-id="6e20e-305">WHSMobileAppStepQtyToScrap</span><span class="sxs-lookup"><span data-stu-id="6e20e-305">WHSMobileAppStepQtyToScrap</span></span> |
| <span data-ttu-id="6e20e-306">QtyVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-306">QtyVerification</span></span> | <span data-ttu-id="6e20e-307">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-307">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="6e20e-308">QtyWithScanningLimit</span><span class="sxs-lookup"><span data-stu-id="6e20e-308">QtyWithScanningLimit</span></span> | <span data-ttu-id="6e20e-309">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="6e20e-309">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="6e20e-310">ReasonString</span><span class="sxs-lookup"><span data-stu-id="6e20e-310">ReasonString</span></span> | <span data-ttu-id="6e20e-311">WHSMobileAppStepReasonString</span><span class="sxs-lookup"><span data-stu-id="6e20e-311">WHSMobileAppStepReasonString</span></span> |
| <span data-ttu-id="6e20e-312">RecvLocationId</span><span class="sxs-lookup"><span data-stu-id="6e20e-312">RecvLocationId</span></span> | <span data-ttu-id="6e20e-313">WHSMobileAppStepRecvLocationId</span><span class="sxs-lookup"><span data-stu-id="6e20e-313">WHSMobileAppStepRecvLocationId</span></span> |
| <span data-ttu-id="6e20e-314">RemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="6e20e-314">RemoveContainerId</span></span> | <span data-ttu-id="6e20e-315">WHSMobileAppStepRemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="6e20e-315">WHSMobileAppStepRemoveContainerId</span></span> |
| <span data-ttu-id="6e20e-316">ReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-316">ReprintLabelConfirmation</span></span> | <span data-ttu-id="6e20e-317">WHSMobileAppStepReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-317">WHSMobileAppStepReprintLabelConfirmation</span></span> |
| <span data-ttu-id="6e20e-318">RMANum</span><span class="sxs-lookup"><span data-stu-id="6e20e-318">RMANum</span></span> | <span data-ttu-id="6e20e-319">WHSMobileAppStepRMANum</span><span class="sxs-lookup"><span data-stu-id="6e20e-319">WHSMobileAppStepRMANum</span></span> |
| <span data-ttu-id="6e20e-320">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="6e20e-320">ShortPickReason</span></span> | <span data-ttu-id="6e20e-321">WHSMobileAppStepShortPickReason</span><span class="sxs-lookup"><span data-stu-id="6e20e-321">WHSMobileAppStepShortPickReason</span></span> |
| <span data-ttu-id="6e20e-322">SortConOrLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-322">SortConOrLP</span></span> | <span data-ttu-id="6e20e-323">WHSMobileAppStepSortConOrLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-323">WHSMobileAppStepSortConOrLP</span></span> |
| <span data-ttu-id="6e20e-324">SortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-324">SortLicensePlateId</span></span> | <span data-ttu-id="6e20e-325">WHSMobileAppStepSortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-325">WHSMobileAppStepSortLicensePlateId</span></span> |
| <span data-ttu-id="6e20e-326">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="6e20e-326">SortPositionId</span></span> | <span data-ttu-id="6e20e-327">WHSMobileAppStepSortPositionId</span><span class="sxs-lookup"><span data-stu-id="6e20e-327">WHSMobileAppStepSortPositionId</span></span> |
| <span data-ttu-id="6e20e-328">SortVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-328">SortVerification</span></span> | <span data-ttu-id="6e20e-329">WHSMobileAppStepSortVerification</span><span class="sxs-lookup"><span data-stu-id="6e20e-329">WHSMobileAppStepSortVerification</span></span> |
| <span data-ttu-id="6e20e-330">StartLocationId</span><span class="sxs-lookup"><span data-stu-id="6e20e-330">StartLocationId</span></span> | <span data-ttu-id="6e20e-331">WHSMobileAppStepStartLocationId</span><span class="sxs-lookup"><span data-stu-id="6e20e-331">WHSMobileAppStepStartLocationId</span></span> |
| <span data-ttu-id="6e20e-332">StartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-332">StartProdOrderConfirmation</span></span> | <span data-ttu-id="6e20e-333">WHSMobileAppStepStartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-333">WHSMobileAppStepStartProdOrderConfirmation</span></span> |
| <span data-ttu-id="6e20e-334">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-334">TargetLicensePlateId</span></span> | <span data-ttu-id="6e20e-335">WHSMobileAppStepTargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-335">WHSMobileAppStepTargetLicensePlateId</span></span> |
| <span data-ttu-id="6e20e-336">TOLineNum</span><span class="sxs-lookup"><span data-stu-id="6e20e-336">TOLineNum</span></span> | <span data-ttu-id="6e20e-337">WHSMobileAppStepTOLineNum</span><span class="sxs-lookup"><span data-stu-id="6e20e-337">WHSMobileAppStepTOLineNum</span></span> |
| <span data-ttu-id="6e20e-338">ToLocation</span><span class="sxs-lookup"><span data-stu-id="6e20e-338">ToLocation</span></span> | <span data-ttu-id="6e20e-339">WHSMobileAppStepToLocation</span><span class="sxs-lookup"><span data-stu-id="6e20e-339">WHSMobileAppStepToLocation</span></span> |
| <span data-ttu-id="6e20e-340">TONum</span><span class="sxs-lookup"><span data-stu-id="6e20e-340">TONum</span></span> | <span data-ttu-id="6e20e-341">WHSMobileAppStepTONum</span><span class="sxs-lookup"><span data-stu-id="6e20e-341">WHSMobileAppStepTONum</span></span> |
| <span data-ttu-id="6e20e-342">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="6e20e-342">ToWarehouse</span></span> | <span data-ttu-id="6e20e-343">WHSMobileAppStepWarehouseTo</span><span class="sxs-lookup"><span data-stu-id="6e20e-343">WHSMobileAppStepWarehouseTo</span></span> |
| <span data-ttu-id="6e20e-344">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="6e20e-344">TransportLoadId</span></span> | <span data-ttu-id="6e20e-345">WHSMobileAppStepTransportLoadId</span><span class="sxs-lookup"><span data-stu-id="6e20e-345">WHSMobileAppStepTransportLoadId</span></span> |
| <span data-ttu-id="6e20e-346">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="6e20e-346">WaveLabelId</span></span> | <span data-ttu-id="6e20e-347">WHSMobileAppStepWaveLabelId</span><span class="sxs-lookup"><span data-stu-id="6e20e-347">WHSMobileAppStepWaveLabelId</span></span> |
| <span data-ttu-id="6e20e-348">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-348">WaveLblQty</span></span> | <span data-ttu-id="6e20e-349">WHSMobileAppStepWaveLblQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-349">WHSMobileAppStepWaveLblQty</span></span> |
| <span data-ttu-id="6e20e-350">Betűvastagság</span><span class="sxs-lookup"><span data-stu-id="6e20e-350">Weight</span></span> | <span data-ttu-id="6e20e-351">WHSMobileAppStepWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-351">WHSMobileAppStepWeight</span></span> |
| <span data-ttu-id="6e20e-352">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="6e20e-352">WeightToConsume</span></span> | <span data-ttu-id="6e20e-353">WHSMobileAppStepWeightToConsume</span><span class="sxs-lookup"><span data-stu-id="6e20e-353">WHSMobileAppStepWeightToConsume</span></span> |
| <span data-ttu-id="6e20e-354">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="6e20e-354">WHSAdjustmentType</span></span> | <span data-ttu-id="6e20e-355">WHSMobileAppStepWHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="6e20e-355">WHSMobileAppStepWHSAdjustmentType</span></span> |
| <span data-ttu-id="6e20e-356">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="6e20e-356">WHSReceivingException</span></span> | <span data-ttu-id="6e20e-357">WHSMobileAppStepWHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="6e20e-357">WHSMobileAppStepWHSReceivingException</span></span> |
| <span data-ttu-id="6e20e-358">WHSWorkException</span><span class="sxs-lookup"><span data-stu-id="6e20e-358">WHSWorkException</span></span> | <span data-ttu-id="6e20e-359">WHSMobileAppStepWHSWorkException</span><span class="sxs-lookup"><span data-stu-id="6e20e-359">WHSMobileAppStepWHSWorkException</span></span> |
| <span data-ttu-id="6e20e-360">WHSWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-360">WHSWorkLicensePlateId</span></span> | <span data-ttu-id="6e20e-361">WHSMobileAppStepWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-361">WHSMobileAppStepWorkLicensePlateId</span></span> |
| <span data-ttu-id="6e20e-362">WMSLocationId</span><span class="sxs-lookup"><span data-stu-id="6e20e-362">WMSLocationId</span></span> | <span data-ttu-id="6e20e-363">WHSMobileAppStepLocation</span><span class="sxs-lookup"><span data-stu-id="6e20e-363">WHSMobileAppStepLocation</span></span> |
| <span data-ttu-id="6e20e-364">WorkId</span><span class="sxs-lookup"><span data-stu-id="6e20e-364">WorkId</span></span> | <span data-ttu-id="6e20e-365">WHSMobileAppStepWorkId</span><span class="sxs-lookup"><span data-stu-id="6e20e-365">WHSMobileAppStepWorkId</span></span> |
| <span data-ttu-id="6e20e-366">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="6e20e-366">WorkIdToCancel</span></span> | <span data-ttu-id="6e20e-367">WHSMobileAppStepWorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="6e20e-367">WHSMobileAppStepWorkIdToCancel</span></span> |
| <span data-ttu-id="6e20e-368">WorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="6e20e-368">WorkLPIdPutawayCluster</span></span> | <span data-ttu-id="6e20e-369">WHSMobileAppStepWorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="6e20e-369">WHSMobileAppStepWorkLPIdPutawayCluster</span></span> |
| <span data-ttu-id="6e20e-370">WorkPoolId</span><span class="sxs-lookup"><span data-stu-id="6e20e-370">WorkPoolId</span></span> | <span data-ttu-id="6e20e-371">WHSMobileAppStepWorkPoolId</span><span class="sxs-lookup"><span data-stu-id="6e20e-371">WHSMobileAppStepWorkPoolId</span></span> |
| <span data-ttu-id="6e20e-372">ZoneId</span><span class="sxs-lookup"><span data-stu-id="6e20e-372">ZoneId</span></span> | <span data-ttu-id="6e20e-373">WHSMobileAppStepZoneId</span><span class="sxs-lookup"><span data-stu-id="6e20e-373">WHSMobileAppStepZoneId</span></span> |

### <a name="available-step-icons"></a><a name="step-icons"></a><span data-ttu-id="6e20e-374">Elérhető lépésikonok</span><span class="sxs-lookup"><span data-stu-id="6e20e-374">Available step icons</span></span>

<span data-ttu-id="6e20e-375">A rendszer standard lépésikonok gyűjteményét tartalmazza, amelyeket egyéni lépésekhez is lehet használni.</span><span class="sxs-lookup"><span data-stu-id="6e20e-375">The system includes a collection of standard step icons that you can also use for your custom steps.</span></span> <span data-ttu-id="6e20e-376">Jelenleg nem lehet feltölteni egyéni ikonokat a lépésekhez.</span><span class="sxs-lookup"><span data-stu-id="6e20e-376">You can't currently upload custom step icons.</span></span> <span data-ttu-id="6e20e-377">Ez azt jelenti, hogy mindig ki kell választania a standard lépésikonok valamelyikét.</span><span class="sxs-lookup"><span data-stu-id="6e20e-377">Therefore, you must always select one of the standard step icons.</span></span>

<span data-ttu-id="6e20e-378">A következő táblázatban megtekintheti az aktuálisan elérhető összes szabványos lépésikont és az ikon nevét.</span><span class="sxs-lookup"><span data-stu-id="6e20e-378">The following table shows every standard step icon that is currently available, and its name.</span></span>

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="A lépésikonok"><br><span data-ttu-id="6e20e-380">Névjegy</span><span class="sxs-lookup"><span data-stu-id="6e20e-380">About</span></span></td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Azonosítótábla vagy cikk lépésikonjának hozzáadása"><br><span data-ttu-id="6e20e-382">AddLpOrItem</span><span class="sxs-lookup"><span data-stu-id="6e20e-382">AddLpOrItem</span></span></td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Kötegrendelkezés lépésikon"><br><span data-ttu-id="6e20e-384">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="6e20e-384">BatchDisposition</span></span></td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Szolgáltató lépésikon"><br><span data-ttu-id="6e20e-386">Fuvarozó</span><span class="sxs-lookup"><span data-stu-id="6e20e-386">Carrier</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Tényleges súly címkéjének lépésikon"><br><span data-ttu-id="6e20e-388">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="6e20e-388">CatchWeightTag</span></span></td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Tényleges súly címkéjével megjelölt súly lépésikon"><br><span data-ttu-id="6e20e-390">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-390">CatchWeightTagWeight</span></span></td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Ellenőrző számjegy lépésikon"><br><span data-ttu-id="6e20e-392">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="6e20e-392">CheckDigit</span></span></td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Azonosító beadása vagy kivétele lépésikon"><br><span data-ttu-id="6e20e-394">CheckInOutId</span><span class="sxs-lookup"><span data-stu-id="6e20e-394">CheckInOutId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Gyermek-azonosítótábla lépésikon"><br><span data-ttu-id="6e20e-396">ChildLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-396">ChildLP</span></span></td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Fürtazonosító lépésikon"><br><span data-ttu-id="6e20e-398">ClusterId</span><span class="sxs-lookup"><span data-stu-id="6e20e-398">ClusterId</span></span></td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Fürtpozíció lépésikon"><br><span data-ttu-id="6e20e-400">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="6e20e-400">ClusterPosition</span></span></td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Konfigurációazonosító lépésikon"><br><span data-ttu-id="6e20e-402">ConfigId</span><span class="sxs-lookup"><span data-stu-id="6e20e-402">ConfigId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Konfigurált mező lépésikon"><br><span data-ttu-id="6e20e-404">ConfiguredField</span><span class="sxs-lookup"><span data-stu-id="6e20e-404">ConfiguredField</span></span></td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Megerősítés vagy azonosítótábla lépésikon"><br><span data-ttu-id="6e20e-406">ConOrLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-406">ConOrLP</span></span></td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Konszolidálás az azonosítótábla azonosítójából lépésikon"><br><span data-ttu-id="6e20e-408">ConsolidateFromLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="6e20e-408">ConsolidateFromLicensePlateID</span></span></td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Konszolidálás az azonosítótábla azonosítójába lépésikon"><br><span data-ttu-id="6e20e-410">ConsolidateToLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="6e20e-410">ConsolidateToLicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Tárolótípus lépésikon"><br><span data-ttu-id="6e20e-412">ContainerType</span><span class="sxs-lookup"><span data-stu-id="6e20e-412">ContainerType</span></span></td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Leltár lépésikon"><br><span data-ttu-id="6e20e-414">Leltár</span><span class="sxs-lookup"><span data-stu-id="6e20e-414">Counting</span></span></td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Leltározási okkód lépésikon"><br><span data-ttu-id="6e20e-416">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="6e20e-416">CountingReasonCode</span></span></td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Származási ország kódjának lépésikon"><br><span data-ttu-id="6e20e-418">CountryOfOrigin</span><span class="sxs-lookup"><span data-stu-id="6e20e-418">CountryOfOrigin</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Intézkedés lépésikon"><br><span data-ttu-id="6e20e-420">Disposition</span><span class="sxs-lookup"><span data-stu-id="6e20e-420">Disposition</span></span></td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Kész lépésikon"><br><span data-ttu-id="6e20e-422">Kész</span><span class="sxs-lookup"><span data-stu-id="6e20e-422">Done</span></span></td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Járművezető bejelentkezésének megerősítése lépésikon"><br><span data-ttu-id="6e20e-424">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-424">DriverCheckInConfirmation</span></span></td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Járművezető bejelentkezésének azonosítója lépésikon"><br><span data-ttu-id="6e20e-426">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="6e20e-426">DriverCheckInId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Járművezető kijelentkezésének azonosítója lépésikon"><br><span data-ttu-id="6e20e-428">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="6e20e-428">DriverCheckOutId</span></span></td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Lejárati dátum lépésikon"><br><span data-ttu-id="6e20e-430">ExpDate</span><span class="sxs-lookup"><span data-stu-id="6e20e-430">ExpDate</span></span></td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Mező lépésikon"><br><span data-ttu-id="6e20e-432">Mező</span><span class="sxs-lookup"><span data-stu-id="6e20e-432">Field</span></span></td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Kötegrendelkezésből lépésikon"><br><span data-ttu-id="6e20e-434">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="6e20e-434">FromBatchDisposition</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Készletállapotból lépésikon"><br><span data-ttu-id="6e20e-436">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="6e20e-436">FromInventoryStatus</span></span></td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Azonosítóattribútum lépésikon"><br><span data-ttu-id="6e20e-438">IdAttribute</span><span class="sxs-lookup"><span data-stu-id="6e20e-438">IdAttribute</span></span></td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Azonosító kötegazonosítója lépésikon"><br><span data-ttu-id="6e20e-440">InventBatchID</span><span class="sxs-lookup"><span data-stu-id="6e20e-440">InventBatchID</span></span></td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Készlet színazonosítója lépésikon"><br><span data-ttu-id="6e20e-442">InventColorID</span><span class="sxs-lookup"><span data-stu-id="6e20e-442">InventColorID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Készlet helye lépésikon"><br><span data-ttu-id="6e20e-444">InventLocation</span><span class="sxs-lookup"><span data-stu-id="6e20e-444">InventLocation</span></span></td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Készlet sorozatazonosítója lépésikon"><br><span data-ttu-id="6e20e-446">InventSerialID</span><span class="sxs-lookup"><span data-stu-id="6e20e-446">InventSerialID</span></span></td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Készlet méretazonosítója lépésikon"><br><span data-ttu-id="6e20e-448">InventSizeID</span><span class="sxs-lookup"><span data-stu-id="6e20e-448">InventSizeID</span></span></td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Készlet állapotazonosítója lépésikon"><br><span data-ttu-id="6e20e-450">InventStatusID</span><span class="sxs-lookup"><span data-stu-id="6e20e-450">InventStatusID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Készlet stílusazonosítója lépésikon"><br><span data-ttu-id="6e20e-452">InventStyleID</span><span class="sxs-lookup"><span data-stu-id="6e20e-452">InventStyleID</span></span></td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Készlet verzióazonosítója lépésikon"><br><span data-ttu-id="6e20e-454">InventVersionID</span><span class="sxs-lookup"><span data-stu-id="6e20e-454">InventVersionID</span></span></td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Cikkazonosító lépésikon"><br><span data-ttu-id="6e20e-456">ItemID</span><span class="sxs-lookup"><span data-stu-id="6e20e-456">ItemID</span></span></td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="ITM tárolóazonosító lépésikon"><br><span data-ttu-id="6e20e-458">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="6e20e-458">ITMContainerID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="ITM szállítmányazonosító lépésikon"><br><span data-ttu-id="6e20e-460">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="6e20e-460">ITMShipmentID</span></span></td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Kanbankártya-azonosító lépésikon"><br><span data-ttu-id="6e20e-462">KanbanCardID</span><span class="sxs-lookup"><span data-stu-id="6e20e-462">KanbanCardID</span></span></td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Kanban vagy kártyaazonosító lépésikon"><br><span data-ttu-id="6e20e-464">KanbanOrCardID</span><span class="sxs-lookup"><span data-stu-id="6e20e-464">KanbanOrCardID</span></span></td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Azonosítótábla azonosítója lépésikon"><br><span data-ttu-id="6e20e-466">LicensePlateID</span><span class="sxs-lookup"><span data-stu-id="6e20e-466">LicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Rakományazonosító lépésikon"><br><span data-ttu-id="6e20e-468">LoadId</span><span class="sxs-lookup"><span data-stu-id="6e20e-468">LoadId</span></span></td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Hely azonosítótáblájának helye lépésikon"><br><span data-ttu-id="6e20e-470">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="6e20e-470">LocationLicensePlatePosition</span></span></td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Hely vagy azonosítótábla lépésikon"><br><span data-ttu-id="6e20e-472">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-472">LocOrLP</span></span></td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Hely vagy azonosítótábla ellenőrzése lépésikon"><br><span data-ttu-id="6e20e-474">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="6e20e-474">LocOrLPCheck</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Hely vagy azonosítótábla innen lépésikon"><br><span data-ttu-id="6e20e-476">LocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="6e20e-476">LocOrLPFrom</span></span></td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Hely vagy azonosítótábla ide lépésikon"><br><span data-ttu-id="6e20e-478">LocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="6e20e-478">LocOrLPTo</span></span></td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Hosszú folyamat befejeződött lépésikon"><br><span data-ttu-id="6e20e-480">LongProcessCompleted</span><span class="sxs-lookup"><span data-stu-id="6e20e-480">LongProcessCompleted</span></span></td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Azonosítótábla szünet, szülő azonosítótábla lépésikon"><br><span data-ttu-id="6e20e-482">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-482">LPBreakParentLP</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Tárolóazonosító egyesítése lépésikon"><br><span data-ttu-id="6e20e-484">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="6e20e-484">MergeContainerId</span></span></td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Vegyes azonosítótábla sorszáma lépésikon"><br><span data-ttu-id="6e20e-486">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="6e20e-486">MixedLPLineNum</span></span></td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Kimenő súly lépésikon"><br><span data-ttu-id="6e20e-488">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="6e20e-488">OutboundWeight</span></span></td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Tulajdonos lépésikon"><br><span data-ttu-id="6e20e-490">Tulajdonos</span><span class="sxs-lookup"><span data-stu-id="6e20e-490">Owner</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Szülő-azonosítótábla lépésikon"><br><span data-ttu-id="6e20e-492">ParentLP</span><span class="sxs-lookup"><span data-stu-id="6e20e-492">ParentLP</span></span></td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Erősítse meg lépésikon"><br><span data-ttu-id="6e20e-494">PleaseConfirm</span><span class="sxs-lookup"><span data-stu-id="6e20e-494">PleaseConfirm</span></span></td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Beszerzési rendelés sorszáma lépésikon"><br><span data-ttu-id="6e20e-496">POLineNum</span><span class="sxs-lookup"><span data-stu-id="6e20e-496">POLineNum</span></span></td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Beszerzési rendelés száma lépésikon"><br><span data-ttu-id="6e20e-498">BRszám</span><span class="sxs-lookup"><span data-stu-id="6e20e-498">PONum</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Pozíció tele lépésikon"><br><span data-ttu-id="6e20e-500">PositionFull</span><span class="sxs-lookup"><span data-stu-id="6e20e-500">PositionFull</span></span></td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Tartalom lépésikon"><br><span data-ttu-id="6e20e-502">Hatóanyag-tartalom</span><span class="sxs-lookup"><span data-stu-id="6e20e-502">Potency</span></span></td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Nyomtató neve lépésikon"><br><span data-ttu-id="6e20e-504">PrinterName</span><span class="sxs-lookup"><span data-stu-id="6e20e-504">PrinterName</span></span></td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Gyártási azonosító lépésikon"><br><span data-ttu-id="6e20e-506">ProdId</span><span class="sxs-lookup"><span data-stu-id="6e20e-506">ProdId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Termék visszaigazolása lépésikon"><br><span data-ttu-id="6e20e-508">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-508">ProductConfirmation</span></span></td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Eltárolás lépésikon"><br><span data-ttu-id="6e20e-510">Eltárolás</span><span class="sxs-lookup"><span data-stu-id="6e20e-510">Put</span></span></td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Betárolási fürtazonosító lépésikon"><br><span data-ttu-id="6e20e-512">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="6e20e-512">PutawayClusterId</span></span></td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Mennyiség lépésikon"><br><span data-ttu-id="6e20e-514">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="6e20e-514">Qty</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Mennyiség módosítása lépésikon"><br><span data-ttu-id="6e20e-516">QtyAdjustIn</span><span class="sxs-lookup"><span data-stu-id="6e20e-516">QtyAdjustIn</span></span></td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Mennyiség kevés lépésikon"><br><span data-ttu-id="6e20e-518">QtyShort</span><span class="sxs-lookup"><span data-stu-id="6e20e-518">QtyShort</span></span></td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Felhasználandó mennyiség lépésikon"><br><span data-ttu-id="6e20e-520">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="6e20e-520">QtyToConsume</span></span></td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Elhelyezendő mennyiség lépésikon"><br><span data-ttu-id="6e20e-522">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="6e20e-522">QtyToPut</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Leselejtezendő mennyiség lépésikon"><br><span data-ttu-id="6e20e-524">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="6e20e-524">QtyToScrap</span></span></td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Mennyiség megerősítése lépésikon"><br><span data-ttu-id="6e20e-526">QuantityConfirmation</span><span class="sxs-lookup"><span data-stu-id="6e20e-526">QuantityConfirmation</span></span></td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Befejezettként jelentett feladat lépésikon"><br><span data-ttu-id="6e20e-528">RAFEndJob</span><span class="sxs-lookup"><span data-stu-id="6e20e-528">RAFEndJob</span></span></td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Fogadási hely azonosítója lépésikon"><br><span data-ttu-id="6e20e-530">RecvLocationID</span><span class="sxs-lookup"><span data-stu-id="6e20e-530">RecvLocationID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Tárolóazonosító eltávolítása lépésikon"><br><span data-ttu-id="6e20e-532">RemoveContainerID</span><span class="sxs-lookup"><span data-stu-id="6e20e-532">RemoveContainerID</span></span></td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="RMA-szám lépésikonja"><br><span data-ttu-id="6e20e-534">RMANum</span><span class="sxs-lookup"><span data-stu-id="6e20e-534">RMANum</span></span></td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Rendelés kiválasztása lépésikon"><br><span data-ttu-id="6e20e-536">SelectOrder</span><span class="sxs-lookup"><span data-stu-id="6e20e-536">SelectOrder</span></span></td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Rövid ok kiválasztása lépésikon"><br><span data-ttu-id="6e20e-538">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="6e20e-538">ShortPickReason</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Pozícióazonosító rendezése lépésikon"><br><span data-ttu-id="6e20e-540">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="6e20e-540">SortPositionId</span></span></td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Cél azonosítótábla azonosítója lépésikon"><br><span data-ttu-id="6e20e-542">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-542">TargetLicensePlateId</span></span></td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Sorszámba lépésikon"><br><span data-ttu-id="6e20e-544">ToLineNum</span><span class="sxs-lookup"><span data-stu-id="6e20e-544">ToLineNum</span></span></td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Helyre lépésikon"><br><span data-ttu-id="6e20e-546">ToLocation</span><span class="sxs-lookup"><span data-stu-id="6e20e-546">ToLocation</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Számba lépésikon"><br><span data-ttu-id="6e20e-548">ToNum</span><span class="sxs-lookup"><span data-stu-id="6e20e-548">ToNum</span></span></td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Raktárba lépésikon"><br><span data-ttu-id="6e20e-550">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="6e20e-550">ToWarehouse</span></span></td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Szállítás rakományazonosítója lépésikon"><br><span data-ttu-id="6e20e-552">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="6e20e-552">TransportLoadId</span></span></td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Szállító kötegazonosítója lépésikon"><br><span data-ttu-id="6e20e-554">VendBatchId</span><span class="sxs-lookup"><span data-stu-id="6e20e-554">VendBatchId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Hullám címkeazonosítója lépésikon"><br><span data-ttu-id="6e20e-556">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="6e20e-556">WaveLabelId</span></span></td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Hullám címkemennyisége lépésikon"><br><span data-ttu-id="6e20e-558">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="6e20e-558">WaveLblQty</span></span></td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Súly lépésikon"><br><span data-ttu-id="6e20e-560">Betűvastagság</span><span class="sxs-lookup"><span data-stu-id="6e20e-560">Weight</span></span></td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Felhasználandó súly lépésikon"><br><span data-ttu-id="6e20e-562">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="6e20e-562">WeightToConsume</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="WHS-korrekció típusa lépésikon"><br><span data-ttu-id="6e20e-564">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="6e20e-564">WHSAdjustmentType</span></span></td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="WHS-bevételezési kivétel lépésikonja"><br><span data-ttu-id="6e20e-566">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="6e20e-566">WHSReceivingException</span></span></td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="WMS-helyazonosító lépésikon"><br><span data-ttu-id="6e20e-568">WMSLocationID</span><span class="sxs-lookup"><span data-stu-id="6e20e-568">WMSLocationID</span></span></td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Munkaazonosító lépésikon"><br><span data-ttu-id="6e20e-570">WorkId</span><span class="sxs-lookup"><span data-stu-id="6e20e-570">WorkId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Visszavonandó munkaazonosító lépésikon"><br><span data-ttu-id="6e20e-572">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="6e20e-572">WorkIdToCancel</span></span></td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Munka szonosítótáblájának azonosítója lépésikon"><br><span data-ttu-id="6e20e-574">WorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="6e20e-574">WorkLicensePlateId</span></span></td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Munka szonosítótáblájának azonosítójához tartozó betárolási fürt lépésikon"><br><span data-ttu-id="6e20e-576">WorkLPIDPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="6e20e-576">WorkLPIDPutawayCluster</span></span></td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Munkakészlet azonosítója lépésikon"><br><span data-ttu-id="6e20e-578">WorkPoolID</span><span class="sxs-lookup"><span data-stu-id="6e20e-578">WorkPoolID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Zónaazonosító lépésikon"><br><span data-ttu-id="6e20e-580">ZoneID</span><span class="sxs-lookup"><span data-stu-id="6e20e-580">ZoneID</span></span></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a><span data-ttu-id="6e20e-581">Példa: Lépésikonok és -címek hozzárendelése egyéni folyamatokhoz</span><span class="sxs-lookup"><span data-stu-id="6e20e-581">Example: Assign step icons and titles for a custom flow</span></span>

<span data-ttu-id="6e20e-582">Az alábbi példa bemutatja, hogyan állíthatók be lépésikonok és -címek egyéni feladatfolyamathoz.</span><span class="sxs-lookup"><span data-stu-id="6e20e-582">This example explains how to set up step icons and titles for a custom task flow.</span></span> <span data-ttu-id="6e20e-583">Az eset olyan egyéni feladatfolyamat példájára épül fel, amely a következő blogbejegyzésben részletesen is elérhető és áttekinthető: [A Warehousing mobilalkalmazás testreszabása](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span><span class="sxs-lookup"><span data-stu-id="6e20e-583">The scenario is built on an example of a custom task flow that is presented and explored in more detail in the following blog post: [Customizing the Warehousing Mobile App](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span></span> <span data-ttu-id="6e20e-584">A feladatfolyamat a következő módon működik:</span><span class="sxs-lookup"><span data-stu-id="6e20e-584">The task flow works in the following way:</span></span>

1. <span data-ttu-id="6e20e-585">Az alkalmazás megjelenít egy olyan lapot, amely azt kéri a dolgozót, hogy adjon meg tárolóazonosítót (például vonalkód beolvasásával).</span><span class="sxs-lookup"><span data-stu-id="6e20e-585">The app shows a page that prompts the worker to provide a container ID (for example, by scanning a bar code).</span></span>
1. <span data-ttu-id="6e20e-586">Ha a tároló azonosítója érvényes, akkor az alkalmazás egy olyan új oldalt nyit meg, amely a súly megadására kéri a dolgozót.</span><span class="sxs-lookup"><span data-stu-id="6e20e-586">If the container ID is valid, the app opens a new page that prompts the worker for the weight.</span></span> <span data-ttu-id="6e20e-587">(Ha a tárolóazonosító nem érvényes, a dolgozó az első oldalra kerül vissza.)</span><span class="sxs-lookup"><span data-stu-id="6e20e-587">(If the container ID isn't valid, the worker is returned to the first page.)</span></span>
1. <span data-ttu-id="6e20e-588">Amikor a dolgozó érvényes súlyt ír be, a rendszer eltárolja a súlyt, és visszairányítja az első oldalra a dolgozót.</span><span class="sxs-lookup"><span data-stu-id="6e20e-588">When the worker enters a valid weight, the system stores the weight and returns the worker to the first page.</span></span>

<span data-ttu-id="6e20e-589">Ez a feladatfolyamat a következő ábrán látható.</span><span class="sxs-lookup"><span data-stu-id="6e20e-589">The following illustration shows this task flow.</span></span>

<span data-ttu-id="6e20e-590">![Feladatfolyamat ábrája](media/step-icons-example-task-flow.png "Feladatfolyamat ábrája")</span><span class="sxs-lookup"><span data-stu-id="6e20e-590">![Task flow diagram](media/step-icons-example-task-flow.png "Task flow diagram")</span></span>

### <a name="create-a-step-class-for-the-container-input-page"></a><span data-ttu-id="6e20e-591">Lépésosztály létrehozása a tároló beviteli oldalához</span><span class="sxs-lookup"><span data-stu-id="6e20e-591">Create a step class for the container input page</span></span>

<span data-ttu-id="6e20e-592">A tároló beviteli oldalán a dolgozó beolvashatja vagy beírhatja a tároló azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="6e20e-592">The container input page lets the worker scan or enter a container ID.</span></span>

<span data-ttu-id="6e20e-593">![Tároló beviteli oldala](media/step-icons-example-container-input.png "Tároló beviteli oldala")</span><span class="sxs-lookup"><span data-stu-id="6e20e-593">![Container input page](media/step-icons-example-container-input.png "Container input page")</span></span>

<span data-ttu-id="6e20e-594">A tároló beviteli oldalán a beviteli mező vezérlőneve `ContainerId`.</span><span class="sxs-lookup"><span data-stu-id="6e20e-594">On the container input page, the control name of the input field is `ContainerId`.</span></span> <span data-ttu-id="6e20e-595">Mivel ez a vezérlőnév nem szerepel a [lépésazonosítók listájában](#step-ids-classes), nem található rajta alapuló lépés.</span><span class="sxs-lookup"><span data-stu-id="6e20e-595">Because this control name isn't in the [list of step IDs](#step-ids-classes), you won't find an existing step that is based on it.</span></span> <span data-ttu-id="6e20e-596">Ezért létre kell hoznia egy olyan lépésosztályt, amely a lépést képviseli.</span><span class="sxs-lookup"><span data-stu-id="6e20e-596">Therefore, you must create a step class that represents the step.</span></span> <span data-ttu-id="6e20e-597">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="6e20e-597">Here is an example.</span></span>

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

<span data-ttu-id="6e20e-598">A lépésikon azonosítója a `defaultStepIcon` osztálytagban, a lépés címe pedig a `defaultStepTitle` osztálytagban van tárolva.</span><span class="sxs-lookup"><span data-stu-id="6e20e-598">The identifier of the step icon is stored in the `defaultStepIcon` class member, and the step title is stored in the `defaultStepTitle` class member.</span></span>

<span data-ttu-id="6e20e-599">Lépésikon hozzárendeléséhez állítsa be a témakör korábbi részén, az [Elérhető lépésikonok](#step-icons) szakaszban lévő ikonok valamelyikére a `defaultStepIcon` tagot.</span><span class="sxs-lookup"><span data-stu-id="6e20e-599">To assign a step icon, set `defaultStepIcon` to one of the icon IDs that are listed in the [Available step icons](#step-icons) section earlier in this topic.</span></span>

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a><span data-ttu-id="6e20e-600">Standard vagy egyéni lépésikon és -cím használata a súly beviteléhez</span><span class="sxs-lookup"><span data-stu-id="6e20e-600">Use a standard or custom step icon and title for the weight input</span></span>

<span data-ttu-id="6e20e-601">A súlybeviteli oldalon a dolgozó súlyt adhat meg.</span><span class="sxs-lookup"><span data-stu-id="6e20e-601">The weight input page lets the worker enter a weight.</span></span>

<span data-ttu-id="6e20e-602">![Súlybeviteli oldal](media/step-icons-example-weight-input.png "Súlybeviteli oldal")</span><span class="sxs-lookup"><span data-stu-id="6e20e-602">![Weight input page](media/step-icons-example-weight-input.png "Weight input page")</span></span>

<span data-ttu-id="6e20e-603">A súlybeviteli oldalon a beviteli mező vezérlőneve `Weight`, amely szerepel a [lépésazonosítók listájában](#step-ids-classes).</span><span class="sxs-lookup"><span data-stu-id="6e20e-603">On the weight input page, the control name of the input field is `Weight`, which is in the [list of step IDs](#step-ids-classes).</span></span> <span data-ttu-id="6e20e-604">Ezért ha a `WHSMobileAppStepWeight` osztályban meghatározott lépésikon és -cím elfogadható Önnek, akkor ennél a lépésnél semmit nem kell módosítania.</span><span class="sxs-lookup"><span data-stu-id="6e20e-604">Therefore, if the step icon and title that are defined in the `WHSMobileAppStepWeight` class are acceptable to you, you don't have to change anything for this step.</span></span>

<span data-ttu-id="6e20e-605">Ha azonban másik ikont vagy címet szeretne használni ehhez a lépéshez, felülbírálhatja a `stepId()` vagy a `stepInfo()` metódust a készítő osztályában.</span><span class="sxs-lookup"><span data-stu-id="6e20e-605">However, if you prefer to use a different icon or title for this step, you can override either the `stepId()` method or the `stepInfo()` method in the builder class.</span></span> <span data-ttu-id="6e20e-606">Minden feladatfolyamatnak saját lépésinformáció-készítője van.</span><span class="sxs-lookup"><span data-stu-id="6e20e-606">Each task flow has its own step info builder.</span></span>

#### <a name="override-the-stepid-method"></a><span data-ttu-id="6e20e-607">A stepId() metódus felülbírálása</span><span class="sxs-lookup"><span data-stu-id="6e20e-607">Override the stepId() method</span></span>

<span data-ttu-id="6e20e-608">A következő példa arra mutat módot, hogy a `stepId()` metódus felülbírálásával módosíthatók a szerkesztőosztályok.</span><span class="sxs-lookup"><span data-stu-id="6e20e-608">The following example shows one way that you can modify a builder class by overriding the `stepId()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

<span data-ttu-id="6e20e-609">Ezután létre kell hoznia egy lépésosztályt a `NewWeight` lépéshez.</span><span class="sxs-lookup"><span data-stu-id="6e20e-609">You then create a step class for the `NewWeight` step.</span></span> <span data-ttu-id="6e20e-610">A kódnak hasonlítania kell a témakörben korábban bemutatott `ContainerId` példa kódjához.</span><span class="sxs-lookup"><span data-stu-id="6e20e-610">The code should resemble the code for the `ContainerId` example that was shown earlier in this topic.</span></span>

#### <a name="override-the-stepinfo-method"></a><span data-ttu-id="6e20e-611">A stepInfo() metódus felülbírálása</span><span class="sxs-lookup"><span data-stu-id="6e20e-611">Override the stepInfo() method</span></span>

<span data-ttu-id="6e20e-612">A következő példa arra mutat módot, hogy a `stepInfo()` metódus felülbírálásával módosíthatók a szerkesztőosztályok.</span><span class="sxs-lookup"><span data-stu-id="6e20e-612">The following example shows one way that you can modify a builder class by overriding the `stepInfo()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

<span data-ttu-id="6e20e-613">Ezt követően létrehoz egy `WHSMobileAppStepInfo` objektumot, és közvetlenül beállítja az ikont és/vagy a címet.</span><span class="sxs-lookup"><span data-stu-id="6e20e-613">You then construct a `WHSMobileAppStepInfo` object, and set the icon and/or title directly.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6e20e-614">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6e20e-614">Additional resources</span></span>

- [<span data-ttu-id="6e20e-615">A Raktárkezelés mobilalkalmazás telepítése és csatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="6e20e-615">Install and connect the Warehouse Management mobile app</span></span>](install-configure-warehouse-management-app.md)
- [<span data-ttu-id="6e20e-616">Mobileszköz felhasználói beállításai</span><span class="sxs-lookup"><span data-stu-id="6e20e-616">Mobile device user settings</span></span>](mobile-device-user-settings.md)
