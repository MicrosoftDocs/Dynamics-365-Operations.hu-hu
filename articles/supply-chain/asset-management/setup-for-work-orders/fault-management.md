---
title: Hibakezelés
description: Ez a témakör az Eszközkezelésben történő hibakezelést ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 43f996921ccac0b3c85ecea2460cb9e4614f8c04
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226809"
---
# <a name="fault-management"></a><span data-ttu-id="8a57f-103">Hibakezelés</span><span class="sxs-lookup"><span data-stu-id="8a57f-103">Fault management</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="8a57f-104">Az Eszközkezelés modulban használhatja a hibatervezőt hibatünetek, a meghibásodási területeket és a hibatípusok beállításához az eszköztípusokhoz.</span><span class="sxs-lookup"><span data-stu-id="8a57f-104">In Asset Management, you can use the fault designer to set up fault symptoms, fault areas, and fault types on asset types.</span></span> <span data-ttu-id="8a57f-105">Ily módon az eszközökön észlelt hibák kezelhetők lesznek.</span><span class="sxs-lookup"><span data-stu-id="8a57f-105">In this way, you can manage faults that are detected on assets.</span></span> <span data-ttu-id="8a57f-106">Ezenkívül a hibák oka és a hibák elhárításával kapcsolatos javaslatok a munkarendelésen regisztrálhatók.</span><span class="sxs-lookup"><span data-stu-id="8a57f-106">Additionally, fault causes and suggestions for fixing faults can be registered on a work order.</span></span>

<span data-ttu-id="8a57f-107">A hibák regisztrálásának és kezelésének folyamata a következő lépésekből áll.</span><span class="sxs-lookup"><span data-stu-id="8a57f-107">The process for fault registration and management consists of these steps.</span></span>

1. <span data-ttu-id="8a57f-108">A tárgyieszköz-típusokon esetleg előforduló hibatünetek, hibás területek és hibatípusok listájának létrehozása.</span><span class="sxs-lookup"><span data-stu-id="8a57f-108">Create a list of fault symptoms, fault areas, and fault types that might occur on your asset types.</span></span>
2. <span data-ttu-id="8a57f-109">A hibatervező modulban állítsa be a tüneteket, a hibaterületeket és a hibatípusokat.</span><span class="sxs-lookup"><span data-stu-id="8a57f-109">In the fault designer, set up symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="8a57f-110">A következőkben néhány példával seítünk megérteni a hibatünetek, hibaterületek és a hibatípusok közötti különbségét.</span><span class="sxs-lookup"><span data-stu-id="8a57f-110">Here are some examples to help you understand the difference between fault symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="8a57f-111">**Hibatünetek:**</span><span class="sxs-lookup"><span data-stu-id="8a57f-111">**Fault symptoms:**</span></span>

- <span data-ttu-id="8a57f-112">Feszültségingadozások</span><span class="sxs-lookup"><span data-stu-id="8a57f-112">Unbalanced voltages</span></span>
- <span data-ttu-id="8a57f-113">Rövidzárlat</span><span class="sxs-lookup"><span data-stu-id="8a57f-113">Short circuit</span></span>
- <span data-ttu-id="8a57f-114">Zaj</span><span class="sxs-lookup"><span data-stu-id="8a57f-114">Noise</span></span>
- <span data-ttu-id="8a57f-115">Szivárgás</span><span class="sxs-lookup"><span data-stu-id="8a57f-115">Leak</span></span>
- <span data-ttu-id="8a57f-116">Vibrációk</span><span class="sxs-lookup"><span data-stu-id="8a57f-116">Vibrations</span></span>

<span data-ttu-id="8a57f-117">**Hibaterületek:**</span><span class="sxs-lookup"><span data-stu-id="8a57f-117">**Fault areas:**</span></span>

- <span data-ttu-id="8a57f-118">Elektromos</span><span class="sxs-lookup"><span data-stu-id="8a57f-118">Electrical</span></span>
- <span data-ttu-id="8a57f-119">Mechanikai</span><span class="sxs-lookup"><span data-stu-id="8a57f-119">Mechanical</span></span>
- <span data-ttu-id="8a57f-120">Hidraulikus</span><span class="sxs-lookup"><span data-stu-id="8a57f-120">Hydraulic</span></span>
- <span data-ttu-id="8a57f-121">Pneumatikus</span><span class="sxs-lookup"><span data-stu-id="8a57f-121">Pneumatic</span></span>

<span data-ttu-id="8a57f-122">**Hibatípusok:**</span><span class="sxs-lookup"><span data-stu-id="8a57f-122">**Fault types:**</span></span>

- <span data-ttu-id="8a57f-123">Hibás fő stator tekercselés</span><span class="sxs-lookup"><span data-stu-id="8a57f-123">Faulty main stator winding</span></span>
- <span data-ttu-id="8a57f-124">Hibás dióda</span><span class="sxs-lookup"><span data-stu-id="8a57f-124">Faulty diode</span></span>
- <span data-ttu-id="8a57f-125">Szennyezett tekercselések</span><span class="sxs-lookup"><span data-stu-id="8a57f-125">Dirty windings</span></span>
- <span data-ttu-id="8a57f-126">Hibás generátor</span><span class="sxs-lookup"><span data-stu-id="8a57f-126">Defective generator</span></span>
- <span data-ttu-id="8a57f-127">Hibás érzékelő</span><span class="sxs-lookup"><span data-stu-id="8a57f-127">Defective sensor</span></span>

## <a name="create-fault-symptoms"></a><span data-ttu-id="8a57f-128">Hibatünetek létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a57f-128">Create fault symptoms</span></span>

<span data-ttu-id="8a57f-129">Hajtsa végre a következő lépéseket a hibatervezőben használható tünetlista létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a57f-129">Follow these steps to create a list of symptoms that can be used in the fault designer.</span></span>

1. <span data-ttu-id="8a57f-130">Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibatünetek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-130">Select **Asset management** \> **Setup** \> **Fault** \> **Fault symptoms**.</span></span>
2. <span data-ttu-id="8a57f-131">Válassza az **Új** lehetőséget egy rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a57f-131">Select **New** to create a record.</span></span>
3. <span data-ttu-id="8a57f-132">A **Hibatünet** mezőbe írjon be egy nevet a hibatünethez.</span><span class="sxs-lookup"><span data-stu-id="8a57f-132">In the **Fault symptom** field, enter a name for the fault symptom.</span></span>
4. <span data-ttu-id="8a57f-133">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a57f-133">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="8a57f-134">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-134">Select **Save**.</span></span>

## <a name="create-fault-areas"></a><span data-ttu-id="8a57f-135">Hibaterületek létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a57f-135">Create fault areas</span></span>

<span data-ttu-id="8a57f-136">Hajtsa végre a következő lépéseket a hibatervezőben használható területek vagy helyek listájának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a57f-136">Follow these steps to create a list of areas or locations that can be used in the fault designer.</span></span>

1. <span data-ttu-id="8a57f-137">Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibaterületek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-137">Select **Asset management** \> **Setup** \> **Fault** \> **Fault areas**.</span></span>
2. <span data-ttu-id="8a57f-138">Válassza az **Új** lehetőséget egy rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a57f-138">Select **New** to create a record.</span></span>
3. <span data-ttu-id="8a57f-139">A **Hibaterület** mezőbe írjon be egy nevet a hibaterülethez.</span><span class="sxs-lookup"><span data-stu-id="8a57f-139">In the **Fault area** field, enter a name for the fault area.</span></span>
4. <span data-ttu-id="8a57f-140">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a57f-140">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="8a57f-141">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-141">Select **Save**.</span></span>

## <a name="create-fault-types"></a><span data-ttu-id="8a57f-142">Hibatípusok létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a57f-142">Create fault types</span></span>

<span data-ttu-id="8a57f-143">Hajtsa végre a következő lépéseket a hibatervezőben használható hibatípusok listájának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a57f-143">Follow these steps to create a list of fault types that can be used in the fault designer.</span></span>

1. <span data-ttu-id="8a57f-144">Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibatípusok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-144">Select **Asset management** \> **Setup** \> **Fault** \> **Fault types**.</span></span>
2. <span data-ttu-id="8a57f-145">Válassza az **Új** lehetőséget egy rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a57f-145">Select **New** to create a record.</span></span>
3. <span data-ttu-id="8a57f-146">A **Hibatípus** mezőben adja meg a hibatípus nevét.</span><span class="sxs-lookup"><span data-stu-id="8a57f-146">In the **Fault type** field, enter a name for the fault type.</span></span>
4. <span data-ttu-id="8a57f-147">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a57f-147">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="8a57f-148">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-148">Select **Save**.</span></span>

## <a name="set-up-the-fault-designer"></a><span data-ttu-id="8a57f-149">A hibatervező beállítása</span><span class="sxs-lookup"><span data-stu-id="8a57f-149">Set up the fault designer</span></span>

<span data-ttu-id="8a57f-150">A hibatervezőben be lehet állítani a tárgyieszköz-típusokra vonatkozó hibaadatokat.</span><span class="sxs-lookup"><span data-stu-id="8a57f-150">In the fault designer, you set up fault data on asset types.</span></span>

1. <span data-ttu-id="8a57f-151">Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibatervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-151">Select **Asset management** \> **Setup** \> **Fault** \> **Fault designer**.</span></span>
2. <span data-ttu-id="8a57f-152">A bal oldali ablakban válassza ki, hogy melyik eszköztípushoz szeretné beállítani a hibarekordot.</span><span class="sxs-lookup"><span data-stu-id="8a57f-152">In the left pane, select the type of asset to set up a fault record for.</span></span>
3. <span data-ttu-id="8a57f-153">A **Hibatünet** gyorslapon válassza ki a **Sorhozzáadása** elemet, majd a **Hibatünet** mezőben válassza ki a hiba tünetét.</span><span class="sxs-lookup"><span data-stu-id="8a57f-153">On the **Fault symptom** FastTab, select **Add line**, and then, in the **Fault symptom** field, select a fault symptom.</span></span>
4. <span data-ttu-id="8a57f-154">A **Hibaterület** gyorslapon válassza ki a **Sorhozzáadása** elemet, majd a **Hibaterület** mezőben válassza ki a hiba területét.</span><span class="sxs-lookup"><span data-stu-id="8a57f-154">On the **Fault area** FastTab, select **Add line**, and then, in the **Fault area** field select a fault area.</span></span>
5. <span data-ttu-id="8a57f-155">A **Hibatípus** gyorslapon válassza ki a **Sor hozzáadása** elemet, majd a **Hiba típusa** mezőben válassza ki a hiba típusát.</span><span class="sxs-lookup"><span data-stu-id="8a57f-155">On the **Fault type** FastTab, select **Add line**, and then, in the **Fault type** field, select a fault type.</span></span>
6. <span data-ttu-id="8a57f-156">Ha gyorsan létre kívánja hozni az összes meglévő hibatünet, -területet és -típus kombinációit a kiválasztott eszköztípushoz, válassza a **Hibakombinációk létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-156">To quickly create combinations of all existing fault symptoms, areas, and types for the selected asset type, select **Create fault combinations**.</span></span> <span data-ttu-id="8a57f-157">Ez a funkció akkor hasznos, ha sok hibatünetet, -területet és -típust adott hozzá.</span><span class="sxs-lookup"><span data-stu-id="8a57f-157">This function is useful if you've added many fault symptoms, areas, and types.</span></span> <span data-ttu-id="8a57f-158">Könnyebb törölni azokat a sorokat azon kombinációkhoz, amelyek nem relevánsak az eszköztípushoz, mint az új sorokat manuálisan létrehozni.</span><span class="sxs-lookup"><span data-stu-id="8a57f-158">It's easier to delete the lines for any combinations that aren't relevant to the asset type than to create new lines manually.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a57f-159">Ha azt szeretné, hogy a rendszer egy eszköztípusról a hibás tünetek, területek és típusok beállításait a kiválasztott eszköztípusra másolja, válassza a **Másolás eszköztípusból** parancsot.</span><span class="sxs-lookup"><span data-stu-id="8a57f-159">To copy the setup of fault symptoms, areas, and types from one asset type to the selected asset type, select **Copy from asset type**.</span></span>

7. <span data-ttu-id="8a57f-160">A változtatások mentéséhez válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="8a57f-160">Select **Save** to save your changes.</span></span>

![Hibatervező oldal](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a><span data-ttu-id="8a57f-162">Hibaokok létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a57f-162">Create fault causes</span></span>

<span data-ttu-id="8a57f-163">Hajtsa végre az alábbi lépéseket a munkarendeléshez vagy a karbantartási kérelemhez adható ismert hibaokok listájának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a57f-163">Follow these steps to create a list of known fault causes that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="8a57f-164">Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibaokok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-164">Select **Asset management** \> **Setup** \> **Fault** \> **Fault causes**.</span></span>
2. <span data-ttu-id="8a57f-165">Válassza az **Új** lehetőséget egy rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a57f-165">Select **New** to create a record.</span></span>
3. <span data-ttu-id="8a57f-166">A **Hibaok** mezőben adja meg a hibaok nevét.</span><span class="sxs-lookup"><span data-stu-id="8a57f-166">In the **Fault cause** field, enter a name for the fault cause.</span></span>
4. <span data-ttu-id="8a57f-167">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a57f-167">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="8a57f-168">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-168">Select **Save**.</span></span>

## <a name="create-fault-remedies"></a><span data-ttu-id="8a57f-169">Hibajavítások létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a57f-169">Create fault remedies</span></span>

<span data-ttu-id="8a57f-170">Hajtsa végre az alábbi lépéseket a munkarendeléshez vagy a karbantartási kérelemhez adható megoldások vagy javítások listájának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a57f-170">Follow these steps to create a list of suggestions for remedy and repair that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="8a57f-171">Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibajavítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-171">Select **Asset management** \> **Setup** \> **Fault** \> **Fault remedies**.</span></span>
2. <span data-ttu-id="8a57f-172">Válassza az **Új** lehetőséget egy rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a57f-172">Select **New** to create a record.</span></span>
3. <span data-ttu-id="8a57f-173">A **Hibajavítás** mezőbe írjon be egy nevet a hibajavításhoz.</span><span class="sxs-lookup"><span data-stu-id="8a57f-173">In the **Fault remedy** field, enter a name for the fault remedy.</span></span>
4. <span data-ttu-id="8a57f-174">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a57f-174">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="8a57f-175">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a57f-175">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="8a57f-176">Igény esetén a hibák, területek, típusok, okok és javítások nevei módosíthatók.</span><span class="sxs-lookup"><span data-stu-id="8a57f-176">You can change the names of your fault symptoms, areas, types, causes, and remedies as you require.</span></span> <span data-ttu-id="8a57f-177">A névmódosítások automatikusan tükröződnek kapcsolódó hibaregisztrációkban.</span><span class="sxs-lookup"><span data-stu-id="8a57f-177">The name changes are automatically reflected in the related fault registrations.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]