---
title: Hívásközpont csatorna beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy új hívásközpont csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6ec42ab920868f541eeac54556f4f24cb1efaa3a
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002450"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="9e634-103">Hívásközpont csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="9e634-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9e634-104">Ez a témakör azt mutatja be, hogyan lehet egy új hívásközpont csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="9e634-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9e634-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="9e634-105">Overview</span></span>

<span data-ttu-id="9e634-106">A Dynamics 365 Commerce szolgáltatásban a hívásközpont egyfajta kiskereskedelmi csatorna, amelyet az alkalmazásban lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="9e634-106">In Dynamics 365 Commerce, a call center is a type of retail channel that can be defined in the application.</span></span> <span data-ttu-id="9e634-107">Ha meghatároz egy csatornát a hívásközpont entitások számára, azzal a rendszer képes lesz specifikus adatok és megrendelések feldolgozásához tartozó alapértelmezéseket értékesítési rendelésekhez kötni.</span><span class="sxs-lookup"><span data-stu-id="9e634-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="9e634-108">A vállalat több hívásközponti csatornát is meghatározhat a Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="9e634-108">A company can define multiple call center channels in Commerce.</span></span> 

<span data-ttu-id="9e634-109">Új hívásközpont-csatorna létrehozása előtt győződjön meg arról, hogy végrehajtotta a [Csatornbeállítás előfeltételeit](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="9e634-109">Before you create a new call center channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="9e634-110">Új hívásközpont csatorna létrehozása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9e634-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="9e634-111">Új hívásközpont csatorna létrehozásához és konfigurálásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9e634-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="9e634-112">A navigációs ablaktáblán lépjen a **Modulok \> Csatornák \> Hívásközpontok \> Minden hívásközpont** részhez.</span><span class="sxs-lookup"><span data-stu-id="9e634-112">In the navigation pane, go to **Modules \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="9e634-113">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9e634-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9e634-114">A **Név** mezőben adja meg az új csatorna nevét.</span><span class="sxs-lookup"><span data-stu-id="9e634-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="9e634-115">Válassza ki a megfelelő **Jogi személyt** a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="9e634-115">Select the appropriate **Legal entity** from the drop down.</span></span>
1. <span data-ttu-id="9e634-116">Válassza ki a megfelelő **Raktár** helyet a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="9e634-116">Select the appropriate **Warehouse** location from the drop down.</span></span>
1. <span data-ttu-id="9e634-117">Az **Alapértelmezett ügyfél** mezőben adjon meg egy érvényes alapértelmezett ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="9e634-117">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="9e634-118">Az **E-mail értesítési profilja** mezőben adjon meg egy érvényes e-mail-értesítési profilt.</span><span class="sxs-lookup"><span data-stu-id="9e634-118">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="9e634-119">Adja meg az **Ár-felülbírálás** infókódot.</span><span class="sxs-lookup"><span data-stu-id="9e634-119">Provide a **Price override** info code.</span></span> <span data-ttu-id="9e634-120">Ne feledje: elképzelhető, hogy először létre kell hoznia egy információs kódot.</span><span class="sxs-lookup"><span data-stu-id="9e634-120">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="9e634-121">Adja meg a **Várakoztatási kód** infókódot.</span><span class="sxs-lookup"><span data-stu-id="9e634-121">Provide a **Hold code** info code.</span></span> <span data-ttu-id="9e634-122">Ne feledje: elképzelhető, hogy először létre kell hoznia egy információs kódot.</span><span class="sxs-lookup"><span data-stu-id="9e634-122">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="9e634-123">Adja meg a **Hitel** infókódot.</span><span class="sxs-lookup"><span data-stu-id="9e634-123">Provide a **Credit** info code.</span></span> <span data-ttu-id="9e634-124">Ne feledje: elképzelhető, hogy először létre kell hoznia egy információs kódot.</span><span class="sxs-lookup"><span data-stu-id="9e634-124">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="9e634-125">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e634-125">Select **Save**.</span></span>

<span data-ttu-id="9e634-126">A következő kép bemutatja egy új hívásközpont csatorna létrehozását.</span><span class="sxs-lookup"><span data-stu-id="9e634-126">The following image shows the creation of a new call center channel.</span></span>

![Új hívásközponti csatorna](media/channel-setup-callcenter-1.png)

<span data-ttu-id="9e634-128">A következő kép egy példát mutat a hívásközpont csatornára.</span><span class="sxs-lookup"><span data-stu-id="9e634-128">The following image shows an example call center channel.</span></span>

![Hívásközponti csatorna – példa](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="9e634-130">További csatornák beállítása</span><span class="sxs-lookup"><span data-stu-id="9e634-130">Additional channel setup</span></span>

<span data-ttu-id="9e634-131">A hívásközpont csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok és szállítási módok beállítása.</span><span class="sxs-lookup"><span data-stu-id="9e634-131">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="9e634-132">A következő képen láthatók a **Szállítási módok** és a **Fizetési módok** beállított lehetőségei a **Beállítás** lapon.</span><span class="sxs-lookup"><span data-stu-id="9e634-132">The following image shows **Modes of delivery** and **Payment methods** set up options on the **Set up** tab.</span></span>

![További hívásközpont-csatorna-beállítási műveletek](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="9e634-134">Fizetési módok beállítása</span><span class="sxs-lookup"><span data-stu-id="9e634-134">Set up payment methods</span></span>

<span data-ttu-id="9e634-135">A fizetési módok beállításához a csatornán támogatott valamennyi fizetési típusnál kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9e634-135">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="9e634-136">A műveleti ablaktáblán válassza a **Beállítás** lapot, majd válassza ki a **Fizetési módokat**.</span><span class="sxs-lookup"><span data-stu-id="9e634-136">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="9e634-137">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9e634-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9e634-138">A navigációs ablakban válassza ki a kívánt fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="9e634-138">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="9e634-139">Az **általános** szakaszban adjon meg egy **művelet nevét**, és adja meg a kívánt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="9e634-139">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="9e634-140">Adja meg a fizetési típushoz szükséges további beállításokat.</span><span class="sxs-lookup"><span data-stu-id="9e634-140">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="9e634-141">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e634-141">On the action pane, select **Save**.</span></span>

<span data-ttu-id="9e634-142">A következő kép egy példát mutat a készpénzfizetési módra.</span><span class="sxs-lookup"><span data-stu-id="9e634-142">The following image shows an example of a cash payment method.</span></span>

![Fizetési módok – példa](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="9e634-144">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="9e634-144">Set up modes of delivery</span></span>

<span data-ttu-id="9e634-145">A konfigurált szállítási módokat a **Szállítási módok** kiválasztásával tekintheti meg a **Beállítás** lapon a **Műveleti ablaktáblán**.</span><span class="sxs-lookup"><span data-stu-id="9e634-145">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="9e634-146">Szállítási mód módosításához vagy hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9e634-146">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="9e634-147">A navigációs ablakban nyissa meg a **Modulok \> Készletkezelés \> Szállítási módok** elemet.</span><span class="sxs-lookup"><span data-stu-id="9e634-147">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="9e634-148">A műveleti ablaktáblán válassza az **Új** elemet új szállítási mód létrehozásához, vagy válasszon meglévő módot.</span><span class="sxs-lookup"><span data-stu-id="9e634-148">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="9e634-149">A **kiskereskedelmi csatornák** területen válassza a **sor hozzáadása** parancsot a csatorna hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="9e634-149">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="9e634-150">Csatornák hozzáadása a szervezeti csomópontok használatával, nem pedig az egyes csatornák hozzáadásával egyszerűsítheti a csatornák hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="9e634-150">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="9e634-151">A következő kép egy példát mutat a szállítási módra.</span><span class="sxs-lookup"><span data-stu-id="9e634-151">The following image shows an example of a mode of delivery.</span></span>

![Szállítási módok beállítása](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a><span data-ttu-id="9e634-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9e634-153">Additional resources</span></span>

[<span data-ttu-id="9e634-154">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="9e634-154">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="9e634-155">Hívásközpont értékesítési funkciói</span><span class="sxs-lookup"><span data-stu-id="9e634-155">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="9e634-156">Hívásközpont rendelésfeldolgozási beállításainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="9e634-156">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="9e634-157">Hívásközpont-katalógusok</span><span class="sxs-lookup"><span data-stu-id="9e634-157">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="9e634-158">Csalással kapcsolatos figyelmeztetések beállítása és használata</span><span class="sxs-lookup"><span data-stu-id="9e634-158">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="9e634-159">Folytonossági programok beállítása hívásközpontok számára</span><span class="sxs-lookup"><span data-stu-id="9e634-159">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
