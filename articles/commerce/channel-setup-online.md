---
title: Online csatorna beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy új online csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 07/02/2020
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
ms.openlocfilehash: 07225d97af76ea665fa28362cc205c6e8dc4fdf4
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2020
ms.locfileid: "4413013"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="85b12-103">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="85b12-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="85b12-104">Ez a témakör azt mutatja be, hogyan lehet egy új online csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="85b12-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="85b12-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="85b12-105">Overview</span></span>

<span data-ttu-id="85b12-106">A Dynamics 365 Commerce rendszer támogatja a többszörös kiskereskedelmi csatornák használatát.</span><span class="sxs-lookup"><span data-stu-id="85b12-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="85b12-107">Ezek a kiskereskedelmi csatornák lehetnek online áruházak, hívásközpontok és kiskereskedelmi áruházak (más néven rendes, nem online üzletek).</span><span class="sxs-lookup"><span data-stu-id="85b12-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="85b12-108">Az online áruházak segítségével a vevők a kiskereskedelmi üzletek mellett a kiskereskedőtől online is vásárolhatnak termékeket.</span><span class="sxs-lookup"><span data-stu-id="85b12-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="85b12-109">A Commerce online áruház létrehozásához először létre kell hoznia egy online csatornát.</span><span class="sxs-lookup"><span data-stu-id="85b12-109">To create an online store in Commerce, you must first create an online channel.</span></span> <span data-ttu-id="85b12-110">Új online csatorna létrehozása előtt győződjön meg arról, hogy végrehajtotta a [Csatornbeállítás előfeltételeit](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="85b12-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

<span data-ttu-id="85b12-111">Új webhely létrehozása előtt legalább egy online áruházat létre kell hoznia a Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="85b12-111">Before you can create a new site, at least one online store must be created in Commerce.</span></span> <span data-ttu-id="85b12-112">További információért lásd: [E-kereskedelmi webhely létrehozása](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="85b12-112">For more information, see [Create an e-Commerce site](create-ecommerce-site.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="85b12-113">Új online csatorna létrehozása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="85b12-113">Create and configure a new online channel</span></span>

<span data-ttu-id="85b12-114">Új online csatorna létrehozásához és konfigurálásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="85b12-114">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="85b12-115">A navigációs ablaktáblán lépjen a **Modulok \> Csatornák \> Online áruházak** részhez.</span><span class="sxs-lookup"><span data-stu-id="85b12-115">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="85b12-116">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="85b12-116">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="85b12-117">A **Név** mezőben adja meg az új csatorna nevét.</span><span class="sxs-lookup"><span data-stu-id="85b12-117">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="85b12-118">A **jogi személy** legördülő listában adja meg a megfelelő jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="85b12-118">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="85b12-119">A **raktár** legördülő listában adja meg a megfelelő raktárat.</span><span class="sxs-lookup"><span data-stu-id="85b12-119">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="85b12-120">Az **Üzlet időzónája** mezőből válasszon egy megfelelő időzónát.</span><span class="sxs-lookup"><span data-stu-id="85b12-120">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="85b12-121">A **Pénznem** mezőben válassza ki a megfelelő pénznemet.</span><span class="sxs-lookup"><span data-stu-id="85b12-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="85b12-122">Az **Alapértelmezett ügyfél** mezőben adjon meg egy érvényes alapértelmezett ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="85b12-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="85b12-123">Az **Ügyfél címjegyzéke** mezőben adjon meg érvényes címjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="85b12-123">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="85b12-124">A **Funkcióprofil** mezőben válasszon ki egy funkcióprofilt, ha van ilyen.</span><span class="sxs-lookup"><span data-stu-id="85b12-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="85b12-125">Az **E-mail értesítési profilja** mezőben adjon meg egy érvényes e-mail-értesítési profilt.</span><span class="sxs-lookup"><span data-stu-id="85b12-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="85b12-126">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="85b12-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="85b12-127">A következő kép bemutatja egy új online csatorna létrehozását.</span><span class="sxs-lookup"><span data-stu-id="85b12-127">The following image shows the creation of a new online channel.</span></span>

![Új online csatorna](media/channel-setup-online-1.png)

<span data-ttu-id="85b12-129">A következő kép egy példát mutat a online csatornára.</span><span class="sxs-lookup"><span data-stu-id="85b12-129">The following image shows an example online channel.</span></span>

![Online csatorna – példa](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="85b12-131">Nyelvek beállítása</span><span class="sxs-lookup"><span data-stu-id="85b12-131">Set up languages</span></span>

<span data-ttu-id="85b12-132">Ha az e-kereskedelmi webhely több nyelvet is támogat, bontsa ki a **Nyelvek** szakaszt, és szükség esetén adja meg a további nyelveket.</span><span class="sxs-lookup"><span data-stu-id="85b12-132">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="85b12-133">Fizetési számla beállítása</span><span class="sxs-lookup"><span data-stu-id="85b12-133">Set up payment account</span></span>

<span data-ttu-id="85b12-134">A **fizetési számla** szakaszból kiválaszthatja azt a külső fél fizetési szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="85b12-134">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="85b12-135">Az Adyen fizetési összekötő beállításával kapcsolatos tudnivalókat lásd: [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](../retail/dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="85b12-135">For information on setting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](../retail/dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-setup"></a><span data-ttu-id="85b12-136">További csatornák beállítása</span><span class="sxs-lookup"><span data-stu-id="85b12-136">Additional channel setup</span></span>

<span data-ttu-id="85b12-137">Az online csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok, szállítási módok és a teljesítési csoport hozzárendelésének beállítása.</span><span class="sxs-lookup"><span data-stu-id="85b12-137">Additional tasks that are required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="85b12-138">A következő képen láthatók a **Szállítási módok**, a **Fizetési módok** és a **Teljesítési csoport hozzárendelése** beállított lehetőségei a **Beállítás** lapon.</span><span class="sxs-lookup"><span data-stu-id="85b12-138">The following image shows **Modes of delivery**, **Payment methods**, and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![További online csatorna-beállítási műveletek](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="85b12-140">Fizetési módok beállítása</span><span class="sxs-lookup"><span data-stu-id="85b12-140">Set up payment methods</span></span>

<span data-ttu-id="85b12-141">A fizetési módok beállításához a csatornán támogatott valamennyi fizetési típusnál kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="85b12-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="85b12-142">A műveleti ablaktáblán válassza a **Beállítás** lapot, majd válassza ki a **Fizetési módokat**.</span><span class="sxs-lookup"><span data-stu-id="85b12-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="85b12-143">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="85b12-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="85b12-144">A navigációs ablakban válassza ki a kívánt fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="85b12-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="85b12-145">Az **általános** szakaszban adjon meg egy **művelet nevét**, és adja meg a kívánt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="85b12-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="85b12-146">Adja meg a fizetési típushoz szükséges további beállításokat.</span><span class="sxs-lookup"><span data-stu-id="85b12-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="85b12-147">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="85b12-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="85b12-148">A következő kép egy példát mutat a készpénzfizetési módra.</span><span class="sxs-lookup"><span data-stu-id="85b12-148">The following image shows an example of a cash payment method.</span></span>

![Fizetési módok – példa](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="85b12-150">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="85b12-150">Set up modes of delivery</span></span>

<span data-ttu-id="85b12-151">A konfigurált szállítási módokat a **Szállítási módok** kiválasztásával tekintheti meg a **Beállítás** lapon a **Műveleti ablaktáblán**.</span><span class="sxs-lookup"><span data-stu-id="85b12-151">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="85b12-152">Szállítási mód módosításához vagy hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="85b12-152">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="85b12-153">A navigációs ablakban nyissa meg a **Modulok \> Készletkezelés \> Szállítási módok** elemet.</span><span class="sxs-lookup"><span data-stu-id="85b12-153">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="85b12-154">A műveleti ablaktáblán válassza az **Új** elemet új szállítási mód létrehozásához, vagy válasszon meglévő módot.</span><span class="sxs-lookup"><span data-stu-id="85b12-154">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="85b12-155">A **kiskereskedelmi csatornák** területen válassza a **sor hozzáadása** parancsot a csatorna hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="85b12-155">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="85b12-156">Csatornák hozzáadása a szervezeti csomópontok használatával, nem pedig az egyes csatornák hozzáadásával egyszerűsítheti a csatornák hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="85b12-156">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="85b12-157">A következő kép egy példát mutat a szállítási módra.</span><span class="sxs-lookup"><span data-stu-id="85b12-157">The following image shows an example of a mode of delivery.</span></span>

![Szállítási módok beállítása](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="85b12-159">Teljesítési csoport hozzárendelésének beállítása</span><span class="sxs-lookup"><span data-stu-id="85b12-159">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="85b12-160">A teljesítési csoport hozzárendelésének beállításához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="85b12-160">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="85b12-161">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Teljesítési csoport hozzárendelése**.</span><span class="sxs-lookup"><span data-stu-id="85b12-161">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="85b12-162">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="85b12-162">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="85b12-163">A **teljesítési csoport** legördülő listából válassza ki a teljesítési csoportot.</span><span class="sxs-lookup"><span data-stu-id="85b12-163">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="85b12-164">Ha a **Leírás** legördülő listában adjon meg egy leírást.</span><span class="sxs-lookup"><span data-stu-id="85b12-164">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="85b12-165">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="85b12-165">On the action pane, select **Save**.</span></span>

<span data-ttu-id="85b12-166">A következő kép egy példát mutat be a teljesítési csoport hozzárendelésének beállítására.</span><span class="sxs-lookup"><span data-stu-id="85b12-166">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Teljesítési csoport hozzárendelésének beállítása](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="85b12-168">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="85b12-168">Additional resources</span></span>

[<span data-ttu-id="85b12-169">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="85b12-169">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="85b12-170">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="85b12-170">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="85b12-171">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="85b12-171">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="85b12-172">Hívásközpont csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="85b12-172">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="85b12-173">Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="85b12-173">Dynamics 365 Payment Connector for Adyen</span></span>](../retail/dev-itpro/adyen-connector.md)
