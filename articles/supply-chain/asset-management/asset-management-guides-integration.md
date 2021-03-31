---
title: A Dynamics 365 Supply Chain Management (Eszközkezelés) integrálása a Dynamics 365 Guides alkalmazással
description: Ez a témakör azt mutatja be, hogyan lehet integrálni a Microsoft Dynamics 365 Supply Chain Management Eszközkezelő modulját a Dynamics 365 Guides alkalmazással annak érdekében, hogy kihasználhassa a vegyes valóság útmutatókat a mindennapos szolgáltatási és karbantartási feladatokban.
author: kamaybac
manager: tfehr
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: e3e9e74397faec12f6eecff1f562fd9d731ac5e2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230152"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a><span data-ttu-id="9417c-103">A Dynamics 365 Supply Chain Management (Eszközkezelés) integrálása a Dynamics 365 Guides alkalmazással</span><span class="sxs-lookup"><span data-stu-id="9417c-103">Integrate Dynamics 365 Supply Chain Management (Asset management) with Dynamics 365 Guides</span></span>

<span data-ttu-id="9417c-104">Integrálhatja a Microsoft Dynamics 365 Supply Chain Management **Eszközkezelő modulját** a Dynamics 365 Guides alkalmazással annak érdekében, hogy kihasználhassa a vegyes valóság útmutatókat a mindennapos szolgáltatási és karbantartási feladatokban.</span><span class="sxs-lookup"><span data-stu-id="9417c-104">You can integrate the **Asset management** module in Microsoft Dynamics 365 Supply Chain Management with Dynamics 365 Guides to take advantage of mixed-reality guides in your day-to-day service and maintenance workflows.</span></span> <span data-ttu-id="9417c-105">Ha egy útmutató egy Eszközkezelési munkarendeléshez van társítva, akkor egy dolgozó, aki megnyitja a munkarendelés karbantartási ellenőrzőlistáját a Supply Chain Management (Dynamics 365) alkalmazásban, azt látja, hogy rendelkezésre áll egy útmutató.</span><span class="sxs-lookup"><span data-stu-id="9417c-105">If a guide is associated with an Asset Management work order, a worker who opens the work order's maintenance checklist in the Supply Chain Management (Dynamics 365) mobile app sees that a guide is available.</span></span> <span data-ttu-id="9417c-106">A dolgozó ezután megkeresheti és megnyithatja az útmutatót a Dynamics 365 Guides HoloLens alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="9417c-106">The worker can then find and open the guide in the Dynamics 365 Guides HoloLens app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9417c-107">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="9417c-107">Prerequisites</span></span>

<span data-ttu-id="9417c-108">Mielőtt útmutatókat csatolhat a Eszközkezelési munkarendelésekhez, ezeket az előfeltételeket kell elvégeznie:</span><span class="sxs-lookup"><span data-stu-id="9417c-108">Before you can attach guides to Asset management work orders, you must complete these prerequisites:</span></span>

- <span data-ttu-id="9417c-109">[A Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) 10.0.9 vagy újabb verziójának beállítása.</span><span class="sxs-lookup"><span data-stu-id="9417c-109">[Set up Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 or later.</span></span>
- <span data-ttu-id="9417c-110">[A kettős írás funkció bekapcsolása a Supply Chain Management alkalmazásokhoz](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="9417c-110">[Turn on dual-write for Supply Chain Management apps](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span></span>
- <span data-ttu-id="9417c-111">[Tesztcsomag bekapcsolása](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) az **MRGuidesFeature** funkcióhoz.</span><span class="sxs-lookup"><span data-stu-id="9417c-111">[Turn on flight](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) for the **MRGuidesFeature** feature.</span></span> <span data-ttu-id="9417c-112">(Termelési környezetek esetében először egy támogatási jegyet kell elküldenie, hogy a bérlője bekerüljön a tesztelési csoportba.)</span><span class="sxs-lookup"><span data-stu-id="9417c-112">(For production environments, you must first submit a support ticket to have your tenant added to the flighting group.)</span></span>
- <span data-ttu-id="9417c-113">[Kapcsolja be a következő konfigurációs kulcsokat](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) a **Licenckonfiguráció** oldalon:</span><span class="sxs-lookup"><span data-stu-id="9417c-113">[Turn on the following configuration keys](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) on the **License configuration** page:</span></span>

    - <span data-ttu-id="9417c-114">Eszközkezelés \> Eszközkezelés vegyes valóságban</span><span class="sxs-lookup"><span data-stu-id="9417c-114">Asset management \> Asset management mixed reality</span></span>
    - <span data-ttu-id="9417c-115">Vegyes valóság \> Vegyes valóság útmutató</span><span class="sxs-lookup"><span data-stu-id="9417c-115">Mixed reality \> Mixed reality guide</span></span>

- <span data-ttu-id="9417c-116">[A Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) 200.0.0.96 vagy újabb verziójának beállítása.</span><span class="sxs-lookup"><span data-stu-id="9417c-116">[Set up Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 or later.</span></span>

## <a name="use-dynamics-365-guides-with-asset-management"></a><span data-ttu-id="9417c-117">A Dynamics 365 Guides használata az Eszközkezeléssel</span><span class="sxs-lookup"><span data-stu-id="9417c-117">Use Dynamics 365 Guides with Asset management</span></span>

<span data-ttu-id="9417c-118">Egy útmutató társításához a Eszközkezelés modulban egy karbantartás ellenőrzőlista sora használható.</span><span class="sxs-lookup"><span data-stu-id="9417c-118">To associate a guide, you use a maintenance checklist line in Asset management.</span></span> <span data-ttu-id="9417c-119">A társítást karbantartási ellenőrzőlista sablonnal, egy karbantartási feladattípussal vagy egy munkarendeléssel lehet létrehozni, mivel mindhárom tartalmaz karbantartási ellenőrzőlista sorokat.</span><span class="sxs-lookup"><span data-stu-id="9417c-119">You can create the association through a maintenance checklist template, a maintenance job type, or a work order, because all three contain maintenance checklist lines.</span></span> <span data-ttu-id="9417c-120">Időt takaríthat meg egy sablon használatával, mert a sablon minden olyan karbantartási feladattípushoz társítható, amely használja azt.</span><span class="sxs-lookup"><span data-stu-id="9417c-120">You can save time by using a template, because a template can be associated with all the maintenance job types that use it.</span></span> <span data-ttu-id="9417c-121">Például egy karbantartási feladattípushoz kapcsolódó útmutató automatikusan az összes olyan munkarendeléshez társítva van, amely előírja azt a feladattípust.</span><span class="sxs-lookup"><span data-stu-id="9417c-121">For example, a guide that is associated with a maintenance job type is automatically associated with all work orders that specify that job type.</span></span> <span data-ttu-id="9417c-122">Másfelől viszont a közvetlenül a munkarendeléshez kapcsolódó útmutató csak ahhoz a munkarendeléshez létezik.</span><span class="sxs-lookup"><span data-stu-id="9417c-122">On the other hand, a guide that is associated directly with a work order exists only for that work order.</span></span>

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a><span data-ttu-id="9417c-123">Útmutató társítása karbantartásiellenőrzőlista-sablonhoz</span><span class="sxs-lookup"><span data-stu-id="9417c-123">Associate a guide with a maintenance checklist template</span></span>

<span data-ttu-id="9417c-124">Útmutató társításához egy karbantartásiellenőrzőlista-sablonhoz kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9417c-124">To associate a guide with a maintenance checklist template, follow these steps.</span></span>

1. <span data-ttu-id="9417c-125">Hozzon létre egy útmutatót a Dynamics 365 Guides PC és HoloLens alkalmazásokkal.</span><span class="sxs-lookup"><span data-stu-id="9417c-125">Create a guide by using the Dynamics 365 Guides PC and HoloLens apps.</span></span> <span data-ttu-id="9417c-126">Ha szeretne többet megtudni útmutatók készítéséről, tekintse át az alábbi témaköröket:</span><span class="sxs-lookup"><span data-stu-id="9417c-126">For information about how to create a guide, see the following topics:</span></span>

    - [<span data-ttu-id="9417c-127">A számítógépes alkalmazás használata útmutató létrehozásához</span><span class="sxs-lookup"><span data-stu-id="9417c-127">Use the PC app to create a guide</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/pc-app-overview)
    - [<span data-ttu-id="9417c-128">A hologramok elhelyezése a HoloLens alkalmazás segítségével</span><span class="sxs-lookup"><span data-stu-id="9417c-128">Use the HoloLens app to place your holograms</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-overview)

1. <span data-ttu-id="9417c-129">Az Supply Chain Management alkalmazásban [hozzon létre egy karbantartásiellenőrzőlista-sablont](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span><span class="sxs-lookup"><span data-stu-id="9417c-129">In Supply Chain Management, [create a maintenance checklist template](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span></span>
1. <span data-ttu-id="9417c-130">A létrehozott útmutatót társítsa egy karbantartásiellenőrzőlista-sorhoz az új karbantartásiellenőrzőlista-sablonban:</span><span class="sxs-lookup"><span data-stu-id="9417c-130">Associate the guide that you created with a maintenance checklist line in the new maintenance checklist template:</span></span>

    1. <span data-ttu-id="9417c-131">A **Karbantartásiellenőrzőlista-sorok** gyorslapon válassza ki azt a sort, amelyhez társítani szeretné az útmutatót.</span><span class="sxs-lookup"><span data-stu-id="9417c-131">On the **Maintenance checklist lines** FastTab, select the line that you want to associate the guide with.</span></span>
    1. <span data-ttu-id="9417c-132">Válassza a **Társított útmutatók** gyorslap **Útmutató hozzáadása** elemét.</span><span class="sxs-lookup"><span data-stu-id="9417c-132">On the **Associated guides** FastTab, select **Add Guide**.</span></span>

        <span data-ttu-id="9417c-133">![Útmutató társítása karbantartásiellenőrzőlista-sorhoz](media/am-guides-integration-add-guide.png "Útmutató társítása karbantartásiellenőrzőlista-sorhoz")</span><span class="sxs-lookup"><span data-stu-id="9417c-133">![Associate a guide with a maintenance checklist line](media/am-guides-integration-add-guide.png "Associate a guide with a maintenance checklist line")</span></span>

    1. <span data-ttu-id="9417c-134">A **Név** mezőben válasszon ki egy segédvonalat, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="9417c-134">In the **Name** field, select a guide, and then select **Save**.</span></span>

        <span data-ttu-id="9417c-135">![A Név mezőben válasszon egy útmutatót](media/am-guides-integration-select-guide.png "A Név mezőben válasszon egy útmutatót")</span><span class="sxs-lookup"><span data-stu-id="9417c-135">![Select a guide in the Name field](media/am-guides-integration-select-guide.png "Select a guide in the Name field")</span></span>

1. <span data-ttu-id="9417c-136">A karbantartásiellenőrzőlista-sablon társítása egy feladattípushoz:</span><span class="sxs-lookup"><span data-stu-id="9417c-136">Associate the maintenance checklist template with a job type:</span></span>

    1. <span data-ttu-id="9417c-137">[Hozzon létre egy karbantartásifeladat-típust](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type), vagy válasszon egy meglévő karbantartásifeladat-típust.</span><span class="sxs-lookup"><span data-stu-id="9417c-137">[Create a maintenance job type](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type), or select an existing maintenance job type.</span></span>
    1. <span data-ttu-id="9417c-138">A Művelet ablaktáblán válassza a **Karbantartási feladattípus alapértelmezései** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9417c-138">On the Action Pane, select **Maintenance job type defaults**.</span></span>

        <span data-ttu-id="9417c-139">![Karbantartási feladattípus alapértelmezések gomb](media/am-guides-integration-job-defaults.png "Karbantartási feladattípus alapértelmezések gomb")</span><span class="sxs-lookup"><span data-stu-id="9417c-139">![Maintenance job type defaults button](media/am-guides-integration-job-defaults.png "Maintenance job type defaults button")</span></span>

    1. <span data-ttu-id="9417c-140">Hozzon létre egy sort, majd kattintson a **Mentés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9417c-140">Create a line, and then select **Save**.</span></span>

        <span data-ttu-id="9417c-141">![Egy sor létrehozása](media/am-guides-integration-add-line.png "Egy sor létrehozása")</span><span class="sxs-lookup"><span data-stu-id="9417c-141">![Create a line](media/am-guides-integration-add-line.png "Create a line")</span></span>

    1. <span data-ttu-id="9417c-142">A Művelet panelen válassza a **Karbantartási ellenőrzőlista** elemet.</span><span class="sxs-lookup"><span data-stu-id="9417c-142">On the Action Pane, select **Maintenance checklist**.</span></span>

        <span data-ttu-id="9417c-143">![Karbantartási ellenőrzőlista gombja](media/am-guides-integration-maintenance-checklist.png "Karbantartási ellenőrzőlista gombja")</span><span class="sxs-lookup"><span data-stu-id="9417c-143">![Maintenance checklist button](media/am-guides-integration-maintenance-checklist.png "Maintenance checklist button")</span></span>

    1. <span data-ttu-id="9417c-144">A **Karbantartásellenőrzőlista-sorok** gyorslapján vegyen fel egy sort, majd módosítsa a **Típus** mező értékét **Sablon** értékre.</span><span class="sxs-lookup"><span data-stu-id="9417c-144">On the **Maintenance checklist lines** FastTab, add a line, and then change the value of the **Type** field to **Template**.</span></span>

        <span data-ttu-id="9417c-145">![A Típus érték módosítása](media/am-guides-integration-checklist-lines.png "A Típus érték módosítása")</span><span class="sxs-lookup"><span data-stu-id="9417c-145">![Change the Type value](media/am-guides-integration-checklist-lines.png "Change the Type value")</span></span>

    1. <span data-ttu-id="9417c-146">Válassza ki a **Sor részletei** gyorslap **Sablon** mezőjében azt a sablont, amelyhez az útmutatót társította, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="9417c-146">On the **Line details** FastTab, in the **Template** field, select the template that you associated the guide with, and then select **Save**.</span></span>

        <span data-ttu-id="9417c-147">![Sablon kijelölése](media/am-guides-integration-checklist-line-details.png "Sablon kijelölése")</span><span class="sxs-lookup"><span data-stu-id="9417c-147">![Select the template](media/am-guides-integration-checklist-line-details.png "Select the template")</span></span>

1. <span data-ttu-id="9417c-148">[Hozzon létre egy munkarendelést](work-orders/manually-created-workorders.md#create-work-order), majd válassza ki azt a karbantartási feladattípust, amely az útmutatóhoz társított karbantartásiellenőrzőlista-sablont használja.</span><span class="sxs-lookup"><span data-stu-id="9417c-148">[Create a work order](work-orders/manually-created-workorders.md#create-work-order), and then select the maintenance job type that uses the maintenance checklist template that you associated the guide with.</span></span> <span data-ttu-id="9417c-149">A program automatikusan a munkarendeléshez rendeli az útmutatót.</span><span class="sxs-lookup"><span data-stu-id="9417c-149">The guide is automatically associated with the work order.</span></span>

    <span data-ttu-id="9417c-150">![Válassza ki a karbantartási feladat típusát](media/am-guides-integration-create-work-order.png "Válassza ki a karbantartási feladat típusát")</span><span class="sxs-lookup"><span data-stu-id="9417c-150">![Select a maintenance job type](media/am-guides-integration-create-work-order.png "Select a maintenance job type")</span></span>

1. <span data-ttu-id="9417c-151">A munkarendeléshez és a dolgozókhoz kapcsolódó útmutató megtekintése:</span><span class="sxs-lookup"><span data-stu-id="9417c-151">View the guide that is associated with the work order and workers:</span></span>

    1. <span data-ttu-id="9417c-152">A munkarendelés eléréséhez nyissa meg az [Eszközkezelési mobil munkaterületet](asset-management-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="9417c-152">Open the [Asset management mobile workspace](asset-management-mobile-workspace.md) to access the work order.</span></span>
    1. <span data-ttu-id="9417c-153">Nyissa meg a munkarendeléshez tartozó [Karbantartási ellenőrzőlistát](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job).</span><span class="sxs-lookup"><span data-stu-id="9417c-153">[Open the maintenance checklist](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) for the work order.</span></span>
    1. <span data-ttu-id="9417c-154">Jelöljön ki egy ellenőrzőlista-sort a kapcsolódó útmutató megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="9417c-154">Select a checklist line to see the associated guide.</span></span>

        <span data-ttu-id="9417c-155">![Az ellenőrzőlista-sorhoz társított útmutató](media/am-guides-integration-show-guide.png "Az ellenőrzőlista-sorhoz társított útmutató")</span><span class="sxs-lookup"><span data-stu-id="9417c-155">![Guide associated with a checklist line](media/am-guides-integration-show-guide.png "Guide associated with a checklist line")</span></span>

    1. <span data-ttu-id="9417c-156">Nyissa meg az útmutatót a HoloLens eszközön.</span><span class="sxs-lookup"><span data-stu-id="9417c-156">Open the guide on HoloLens.</span></span>

        <span data-ttu-id="9417c-157">![Az útmutatót megnyitása a HoloLens eszközön](media/am-guides-integration-hololens-select.png "Nyissa meg az útmutatót a HoloLens eszközön")</span><span class="sxs-lookup"><span data-stu-id="9417c-157">![Open the guide on HoloLens](media/am-guides-integration-hololens-select.png "Open the guide on HoloLens")</span></span>

> [!NOTE]
> <span data-ttu-id="9417c-158">Az útmutatók közvetlenül is társíthatók egy munkarendelés vagy egy feladattípus karbantartási ellenőrzőlistájához.</span><span class="sxs-lookup"><span data-stu-id="9417c-158">You can also associate a guide directly in the maintenance checklist of a work order or a job type.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9417c-159">Létezik egy ismert probléma, amikor egy karbantartásiellenőrzőlista-sablont egy alapértelmezett karbantartási feladattípushoz társít, a sablonhoz csatolt útmutató nem jelenik meg a **Karbantartási feladattípus alapértelmezései** gyorslapjának **Társított útmutatók** lapján.</span><span class="sxs-lookup"><span data-stu-id="9417c-159">There is a known issue where, when you associate a maintenance checklist template with a default maintenance job type, the guide that is linked to the template doesn't appear on the **Associated guides** FastTab of the **Maintenance job type defaults** page.</span></span> <span data-ttu-id="9417c-160">Az útmutató azonban azt követően megjelenik, hogy a feladattípus egy munkarendelésre lesz alkalmazva a **Társított útmutatók** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="9417c-160">However, the guide will appear after that job type is applied to a work order on the **Associated guides** FastTab.</span></span>

## <a name="see-also"></a><span data-ttu-id="9417c-161">Lásd még</span><span class="sxs-lookup"><span data-stu-id="9417c-161">See also</span></span>

- [<span data-ttu-id="9417c-162">Kettős írás – áttekintés</span><span class="sxs-lookup"><span data-stu-id="9417c-162">Dual-write overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [<span data-ttu-id="9417c-163">Eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="9417c-163">Asset management overview</span></span>](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]