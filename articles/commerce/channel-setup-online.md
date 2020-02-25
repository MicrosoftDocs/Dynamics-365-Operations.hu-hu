---
title: Online csatorna beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy új online csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: 9b7a2b8fd157df8b39e9e227d188a3802cacb4e3
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002427"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="83313-103">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="83313-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="83313-104">Ez a témakör azt mutatja be, hogyan lehet egy új online csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="83313-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="83313-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="83313-105">Overview</span></span>

<span data-ttu-id="83313-106">A Dynamics 365 Commerce rendszer támogatja a többszörös kiskereskedelmi csatornák használatát.</span><span class="sxs-lookup"><span data-stu-id="83313-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="83313-107">Ezek a kiskereskedelmi csatornák lehetnek online áruházak, hívásközpontok és kiskereskedelmi áruházak (más néven rendes, nem online üzletek).</span><span class="sxs-lookup"><span data-stu-id="83313-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="83313-108">Az online áruházak segítségével a vevők a kiskereskedelmi üzletek mellett a kiskereskedőtől online is vásárolhatnak termékeket.</span><span class="sxs-lookup"><span data-stu-id="83313-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="83313-109">A Commerce online áruház létrehozásához először létre kell hoznia egy online csatornát.</span><span class="sxs-lookup"><span data-stu-id="83313-109">To create an online store in Commerce, you must first create an online channel.</span></span> 

<span data-ttu-id="83313-110">Új online csatorna létrehozása előtt győződjön meg arról, hogy végrehajtotta a [Csatornbeállítás előfeltételeit](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="83313-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="83313-111">Új online csatorna létrehozása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="83313-111">Create and configure a new online channel</span></span>

<span data-ttu-id="83313-112">Új online csatorna létrehozásához és konfigurálásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="83313-112">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="83313-113">A navigációs ablaktáblán lépjen a **Modulok \> Csatornák \> Online áruházak** részhez.</span><span class="sxs-lookup"><span data-stu-id="83313-113">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="83313-114">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="83313-114">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="83313-115">A **Név** mezőben adja meg az új csatorna nevét.</span><span class="sxs-lookup"><span data-stu-id="83313-115">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="83313-116">A **jogi személy** legördülő listában adja meg a megfelelő jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="83313-116">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="83313-117">A **raktár** legördülő listában adja meg a megfelelő raktárat.</span><span class="sxs-lookup"><span data-stu-id="83313-117">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="83313-118">Az **Üzlet időzónája** mezőből válasszon egy megfelelő időzónát.</span><span class="sxs-lookup"><span data-stu-id="83313-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="83313-119">A **Pénznem** mezőben válassza ki a megfelelő pénznemet.</span><span class="sxs-lookup"><span data-stu-id="83313-119">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="83313-120">Az **Alapértelmezett ügyfél** mezőben adjon meg egy érvényes alapértelmezett ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="83313-120">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="83313-121">Az **Ügyfél címjegyzéke** mezőben adjon meg érvényes címjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="83313-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="83313-122">A **Funkcióprofil** mezőben válasszon ki egy funkcióprofilt, ha van ilyen.</span><span class="sxs-lookup"><span data-stu-id="83313-122">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="83313-123">Az **E-mail értesítési profilja** mezőben adjon meg egy érvényes e-mail-értesítési profilt.</span><span class="sxs-lookup"><span data-stu-id="83313-123">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="83313-124">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83313-124">On the action pane, select **Save**.</span></span>

<span data-ttu-id="83313-125">A következő kép bemutatja egy új online csatorna létrehozását.</span><span class="sxs-lookup"><span data-stu-id="83313-125">The following image shows the creation of a new online channel.</span></span>

![Új online csatorna](media/channel-setup-online-1.png)

<span data-ttu-id="83313-127">A következő kép egy példát mutat a online csatornára.</span><span class="sxs-lookup"><span data-stu-id="83313-127">The following image shows an example online channel.</span></span>

![Online csatorna – példa](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="83313-129">Nyelvek beállítása</span><span class="sxs-lookup"><span data-stu-id="83313-129">Set up languages</span></span>

<span data-ttu-id="83313-130">Ha az e-kereskedelmi webhely több nyelvet is támogat, bontsa ki a **Nyelvek** szakaszt, és szükség esetén adja meg a további nyelveket.</span><span class="sxs-lookup"><span data-stu-id="83313-130">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="83313-131">Fizetési számla beállítása</span><span class="sxs-lookup"><span data-stu-id="83313-131">Set up payment account</span></span>

<span data-ttu-id="83313-132">A **fizetési számla** szakaszból kiválaszthatja azt a külső fél fizetési szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="83313-132">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="83313-133">Az Adyen fizetési összekötő beállításával kapcsolatos tudnivalókat lásd: [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](../retail/dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="83313-133">For information on settting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](../retail/dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-set-up"></a><span data-ttu-id="83313-134">További csatornák beállítása</span><span class="sxs-lookup"><span data-stu-id="83313-134">Additional channel set up</span></span>

<span data-ttu-id="83313-135">Az online csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok, szállítási módok és a teljesítési csoport hozzárendelésének beállítása.</span><span class="sxs-lookup"><span data-stu-id="83313-135">Additional tasks required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="83313-136">A következő képen láthatók a **Szállítási módok**, a **Fizetési módok** és a **Teljesítési csoport hozzárendelése** beállított lehetőségei a **Beállítás** lapon.</span><span class="sxs-lookup"><span data-stu-id="83313-136">The following image shows **Modes of delivery**, **Payment methods**, and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![További online csatorna-beállítási műveletek](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="83313-138">Fizetési módok beállítása</span><span class="sxs-lookup"><span data-stu-id="83313-138">Set up payment methods</span></span>

<span data-ttu-id="83313-139">A fizetési módok beállításához a csatornán támogatott valamennyi fizetési típusnál kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="83313-139">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="83313-140">A műveleti ablaktáblán válassza a **Beállítás** lapot, majd válassza ki a **Fizetési módokat**.</span><span class="sxs-lookup"><span data-stu-id="83313-140">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="83313-141">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="83313-141">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="83313-142">A navigációs ablakban válassza ki a kívánt fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="83313-142">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="83313-143">Az **általános** szakaszban adjon meg egy **művelet nevét**, és adja meg a kívánt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="83313-143">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="83313-144">Adja meg a fizetési típushoz szükséges további beállításokat.</span><span class="sxs-lookup"><span data-stu-id="83313-144">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="83313-145">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83313-145">On the action pane, select **Save**.</span></span>

<span data-ttu-id="83313-146">A következő kép egy példát mutat a készpénzfizetési módra.</span><span class="sxs-lookup"><span data-stu-id="83313-146">The following image shows an example of a cash payment method.</span></span>

![Fizetési módok – példa](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="83313-148">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="83313-148">Set up modes of delivery</span></span>

<span data-ttu-id="83313-149">A konfigurált szállítási módokat a **Szállítási módok** kiválasztásával tekintheti meg a **Beállítás** lapon a **Műveleti ablaktáblán**.</span><span class="sxs-lookup"><span data-stu-id="83313-149">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="83313-150">Szállítási mód módosításához vagy hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="83313-150">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="83313-151">A navigációs ablakban nyissa meg a **Modulok \> Készletkezelés \> Szállítási módok** elemet.</span><span class="sxs-lookup"><span data-stu-id="83313-151">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="83313-152">A műveleti ablaktáblán válassza az **Új** elemet új szállítási mód létrehozásához, vagy válasszon meglévő módot.</span><span class="sxs-lookup"><span data-stu-id="83313-152">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="83313-153">A **kiskereskedelmi csatornák** területen válassza a **sor hozzáadása** parancsot a csatorna hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="83313-153">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="83313-154">Csatornák hozzáadása a szervezeti csomópontok használatával, nem pedig az egyes csatornák hozzáadásával egyszerűsítheti a csatornák hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="83313-154">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="83313-155">A következő kép egy példát mutat a szállítási módra.</span><span class="sxs-lookup"><span data-stu-id="83313-155">The following image shows an example of a mode of delivery.</span></span>

![Szállítási módok beállítása](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="83313-157">Teljesítési csoport hozzárendelésének beállítása</span><span class="sxs-lookup"><span data-stu-id="83313-157">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="83313-158">A teljesítési csoport hozzárendelésének beállításához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="83313-158">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="83313-159">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Teljesítési csoport hozzárendelése**.</span><span class="sxs-lookup"><span data-stu-id="83313-159">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="83313-160">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="83313-160">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="83313-161">A **teljesítési csoport** legördülő listából válassza ki a teljesítési csoportot.</span><span class="sxs-lookup"><span data-stu-id="83313-161">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="83313-162">Ha a **Leírás** legördülő listában adjon meg egy leírást.</span><span class="sxs-lookup"><span data-stu-id="83313-162">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="83313-163">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83313-163">On the action pane, select **Save**.</span></span>

<span data-ttu-id="83313-164">A következő kép egy példát mutat be a teljesítési csoport hozzárendelésének beállítására.</span><span class="sxs-lookup"><span data-stu-id="83313-164">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Teljesítési csoport hozzárendelésének beállítása](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="83313-166">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="83313-166">Additional resources</span></span>

[<span data-ttu-id="83313-167">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="83313-167">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="83313-168">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="83313-168">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="83313-169">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="83313-169">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="83313-170">Hívásközpont csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="83313-170">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="83313-171">Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="83313-171">Dynamics 365 Payment Connector for Adyen</span></span>](../retail/dev-itpro/adyen-connector.md)
