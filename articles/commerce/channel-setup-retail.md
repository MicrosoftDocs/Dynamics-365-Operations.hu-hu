---
title: Kiskereskedelmi csatorna beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy új kiskereskedelmi csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3f1f5dc2c8402d9b6b68a049f804932812eb74c0
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937534"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="9af71-103">Retail-csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-103">Set up a retail channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9af71-104">Ez a témakör azt mutatja be, hogyan lehet egy új kiskereskedelmi csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="9af71-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9af71-105">A Dynamics 365 Commerce rendszer támogatja a többszörös kiskereskedelmi csatornák használatát.</span><span class="sxs-lookup"><span data-stu-id="9af71-105">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="9af71-106">Ezek a kiskereskedelmi csatornák lehetnek online áruházak, hívásközpontok és kiskereskedelmi áruházak (más néven rendes, nem online üzletek).</span><span class="sxs-lookup"><span data-stu-id="9af71-106">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="9af71-107">A kiskereskedelmi üzletek csatornái saját fizetési módokkal, árcsoportokkal, (POS) pénztárgépekkel, bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="9af71-107">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="9af71-108">Az összes ilyen elemet be kell állítania, kiskereskedelmi üzlet csatornájának létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="9af71-108">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="9af71-109">A kiskereskedelmi csatorna létrehozása előtt győződjön meg arról, hogy követi a [csatorna előfeltételeit](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="9af71-109">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="9af71-110">Új kiskereskedelmi csatorna létrehozása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9af71-110">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="9af71-111">A navigációs ablaktáblán lépjen a **Modulok \> Csatornák \> Áruházak \> Minden áruház** részhez.</span><span class="sxs-lookup"><span data-stu-id="9af71-111">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="9af71-112">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9af71-112">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9af71-113">A **Név** mezőben adja meg az új csatorna nevét.</span><span class="sxs-lookup"><span data-stu-id="9af71-113">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="9af71-114">Az **Üzlet száma** mezőben adjon meg egy egyedi üzletszámot.</span><span class="sxs-lookup"><span data-stu-id="9af71-114">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="9af71-115">A számnak alfanumerikusnak kell lennie, legfeljebb 10 karakterrel.</span><span class="sxs-lookup"><span data-stu-id="9af71-115">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="9af71-116">A **jogi személy** legördülő listában adja meg a megfelelő jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="9af71-116">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="9af71-117">A **raktár** legördülő listában adja meg a megfelelő raktárat.</span><span class="sxs-lookup"><span data-stu-id="9af71-117">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="9af71-118">Az **Üzlet időzónája** mezőből válasszon egy megfelelő időzónát.</span><span class="sxs-lookup"><span data-stu-id="9af71-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="9af71-119">Az **Áfacsoport** legördülő listából válassza ki az üzlethez megfelelő áfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="9af71-119">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="9af71-120">A **Pénznem** mezőben válassza ki a megfelelő pénznemet.</span><span class="sxs-lookup"><span data-stu-id="9af71-120">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="9af71-121">Az **Ügyfél címjegyzéke** mezőben adjon meg érvényes címjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="9af71-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="9af71-122">Az **Alapértelmezett ügyfél** mezőben adjon meg egy érvényes alapértelmezett ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="9af71-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="9af71-123">A **Funkcióprofil** mezőben válasszon ki egy funkcióprofilt, ha van ilyen.</span><span class="sxs-lookup"><span data-stu-id="9af71-123">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="9af71-124">Az **E-mail értesítési profilja** mezőben adjon meg egy érvényes e-mail-értesítési profilt.</span><span class="sxs-lookup"><span data-stu-id="9af71-124">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="9af71-125">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9af71-125">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9af71-126">A következő kép bemutatja egy új kiskereskedelmi csatorna létrehozását.</span><span class="sxs-lookup"><span data-stu-id="9af71-126">The following image shows the creation of a new retail channel.</span></span>

![Új kiskereskedelmi csatorna](media/channel-setup-retail-1.png)

<span data-ttu-id="9af71-128">A következő kép egy példát mutat a kiskereskedelmi csatornára.</span><span class="sxs-lookup"><span data-stu-id="9af71-128">The following image shows an example retail channel.</span></span>

![Kiskereskedelmi csatorna példája](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="9af71-130">Egyéb beállítások</span><span class="sxs-lookup"><span data-stu-id="9af71-130">Other settings</span></span>

<span data-ttu-id="9af71-131">Számos egyéb választható beállítás érhető el, amely a kiskereskedelmi üzlet szükségletei alapján beállítható a **Kimutatás/zárás** és a **vegyes** szakaszok között.</span><span class="sxs-lookup"><span data-stu-id="9af71-131">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="9af71-132">Ezenkívül lásd [A pénztár (POS) képernyő-elrendezései](pos-screen-layouts.md) című részt további információért az alapértelmezett képernyő-elrendezés beállításáról a **Képernyő-elrendezés** szakaszban és a [Kiskereskedelmi hardverállomás konfigurálása és telepítése](retail-hardware-station-configuration-installation.md) című részt telepítési információért a **Hardverállomások** résszel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="9af71-132">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="9af71-133">A következő kép egy példát mutat a kiskereskedelmi csatorna beállítási konfigurációjáról.</span><span class="sxs-lookup"><span data-stu-id="9af71-133">The following image shows an example retail channel setup configuration.</span></span>

![Kiskereskedelmi csatorna konfigurálása – példa](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="9af71-135">További csatornák beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-135">Additional channel set up</span></span>

<span data-ttu-id="9af71-136">További cikkek szükségesek, amelyeket be kell állítani egy olyan csatornához, amely a Művelet ablaktáblán található a **Beállítás** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="9af71-136">There are additional items that need to be set up for a channel that can be found on the Action Pane under the **Set up** section.</span></span>

<span data-ttu-id="9af71-137">Az online csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok, a készpénzbevallások, a szállítási módok, a bevételi/kiadási számlák, a szakaszok, a teljesítési csoport hozzárendelésének és a széfek beállítása.</span><span class="sxs-lookup"><span data-stu-id="9af71-137">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="9af71-138">A következő képen a kiskereskedelmi csatorna beállításainak különböző beállításai láthatók a **beállítás** lapon.</span><span class="sxs-lookup"><span data-stu-id="9af71-138">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Csatorna beállítása](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="9af71-140">Fizetési módok beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-140">Set up payment methods</span></span>

<span data-ttu-id="9af71-141">A fizetési módok beállításához a csatornán támogatott valamennyi fizetési típusnál kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9af71-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="9af71-142">A műveleti ablaktáblán válassza a **Beállítás** lapot, majd válassza ki a **Fizetési módokat**.</span><span class="sxs-lookup"><span data-stu-id="9af71-142">On the Action Pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="9af71-143">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9af71-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9af71-144">A navigációs ablakban válassza ki a kívánt fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="9af71-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="9af71-145">Az **általános** szakaszban adjon meg egy **művelet nevét**, és adja meg a kívánt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="9af71-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="9af71-146">Adja meg a fizetési típushoz szükséges további beállításokat.</span><span class="sxs-lookup"><span data-stu-id="9af71-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="9af71-147">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9af71-147">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9af71-148">A következő kép egy példát mutat a készpénzfizetési módra.</span><span class="sxs-lookup"><span data-stu-id="9af71-148">The following image shows an example of a cash payment method.</span></span>

![Fizetési módok – példa](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="9af71-150">Készpénzelszámolás beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-150">Set up cash declaration</span></span>

1. <span data-ttu-id="9af71-151">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Készpénzelszámolást**.</span><span class="sxs-lookup"><span data-stu-id="9af71-151">On the Action Pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="9af71-152">A műveleti ablaktáblán válassza az **új** parancsot, majd hozza létre az összes vonatkozó **Érme** és **Bankjegy** címletet.</span><span class="sxs-lookup"><span data-stu-id="9af71-152">On the Action Pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="9af71-153">A következő kép egy példát mutat a készpénzelszámolásra.</span><span class="sxs-lookup"><span data-stu-id="9af71-153">The following image shows an example of a cash declaration.</span></span>

![Készpénzelszámolások beállításai](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="9af71-155">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-155">Set up modes of delivery</span></span>

<span data-ttu-id="9af71-156">A konfigurált szállítási módokat a **Szállítási módok** kiválasztásával tekintheti meg a **Beállítás** lapon a Műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="9af71-156">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the Action Pane.</span></span>  

<span data-ttu-id="9af71-157">Szállítási mód módosításához vagy hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9af71-157">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="9af71-158">A navigációs ablakban nyissa meg a **Modulok \> Készletkezelés \> Szállítási módok** elemet.</span><span class="sxs-lookup"><span data-stu-id="9af71-158">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="9af71-159">A műveleti ablaktáblán válassza az **Új** elemet új szállítási mód létrehozásához, vagy válasszon meglévő módot.</span><span class="sxs-lookup"><span data-stu-id="9af71-159">On the Action Pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="9af71-160">A **kiskereskedelmi csatornák** területen válassza a **sor hozzáadása** parancsot a csatorna hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="9af71-160">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="9af71-161">Csatornák hozzáadása a szervezeti csomópontok használatával, nem pedig az egyes csatornák hozzáadásával egyszerűsítheti a csatornák hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="9af71-161">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="9af71-162">A következő kép egy példát mutat a szállítási módra.</span><span class="sxs-lookup"><span data-stu-id="9af71-162">The following image shows an example of a mode of delivery.</span></span>

![Szállítási módok beállítása](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="9af71-164">Bevételi/kiadási számla beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-164">Set up income/expense account</span></span>

<span data-ttu-id="9af71-165">A bevétel/kiadási számla beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9af71-165">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="9af71-166">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Bevételi/kiadási számla**.</span><span class="sxs-lookup"><span data-stu-id="9af71-166">On the Action Pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="9af71-167">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9af71-167">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9af71-168">A **Név** mezőbe írjon be egy nevet.</span><span class="sxs-lookup"><span data-stu-id="9af71-168">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="9af71-169">A **Keresési név** mezőbe írjon be egy keresési nevet.</span><span class="sxs-lookup"><span data-stu-id="9af71-169">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="9af71-170">A **Számlatípus** részben adja meg a számlatípust.</span><span class="sxs-lookup"><span data-stu-id="9af71-170">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="9af71-171">Szükség szerint adjon meg szöveget a következőkhöz: **Üzenet 1. sora**, **Üzenet 2. sora**, **1. bizonylatszöveg** és **2. bizonylatszöveg**.</span><span class="sxs-lookup"><span data-stu-id="9af71-171">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="9af71-172">A **feladás** területen írja be a feladási adatokat.</span><span class="sxs-lookup"><span data-stu-id="9af71-172">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="9af71-173">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9af71-173">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9af71-174">A következő kép egy példát mutat egy bevételi/kiadási számlára.</span><span class="sxs-lookup"><span data-stu-id="9af71-174">The following image shows an example of an income/expense account.</span></span>

![Bevételi/kiadási számlák beállítása](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="9af71-176">Szakaszok beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-176">Set up sections</span></span>

<span data-ttu-id="9af71-177">A szakaszok beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9af71-177">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="9af71-178">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Szakaszok**.</span><span class="sxs-lookup"><span data-stu-id="9af71-178">On the Action Pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="9af71-179">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9af71-179">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9af71-180">A **szakasz száma** mezőbe írja be a szakasz számát.</span><span class="sxs-lookup"><span data-stu-id="9af71-180">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="9af71-181">Adjon meg egy leírást a **Leírás** alatt.</span><span class="sxs-lookup"><span data-stu-id="9af71-181">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="9af71-182">A **szakaszméret** mezőbe írja be a szakaszméretet.</span><span class="sxs-lookup"><span data-stu-id="9af71-182">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="9af71-183">Szükség szerint adja meg az **Általános** és az **Értékesítési statisztikák** további beállításait.</span><span class="sxs-lookup"><span data-stu-id="9af71-183">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="9af71-184">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9af71-184">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="9af71-185">Teljesítési csoport hozzárendelésének beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-185">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="9af71-186">A teljesítési csoport hozzárendelésének beállításához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="9af71-186">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="9af71-187">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Teljesítési csoport hozzárendelése**.</span><span class="sxs-lookup"><span data-stu-id="9af71-187">On the Action Pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="9af71-188">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9af71-188">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9af71-189">A **teljesítési csoport** legördülő listából válassza ki a teljesítési csoportot.</span><span class="sxs-lookup"><span data-stu-id="9af71-189">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="9af71-190">Ha a **Leírás** legördülő listában adjon meg egy leírást.</span><span class="sxs-lookup"><span data-stu-id="9af71-190">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="9af71-191">A műveleti ablaktáblán válassza a **Mentés** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="9af71-191">On the Action Pane, select **Save**</span></span>

<span data-ttu-id="9af71-192">A következő kép egy példát mutat be a teljesítési csoport hozzárendelésének beállítására.</span><span class="sxs-lookup"><span data-stu-id="9af71-192">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Teljesítési csoport hozzárendeléseinek beállítása](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="9af71-194">Széfek beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-194">Set up safes</span></span>

<span data-ttu-id="9af71-195">A széfek beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9af71-195">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="9af71-196">A Műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **széfek**.</span><span class="sxs-lookup"><span data-stu-id="9af71-196">On the Action Pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="9af71-197">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9af71-197">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9af71-198">Adja meg a széf nevét.</span><span class="sxs-lookup"><span data-stu-id="9af71-198">Enter a name for the safe.</span></span>
1. <span data-ttu-id="9af71-199">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9af71-199">On the Action Pane, select **Save**.</span></span>

### <a name="ensure-unique-transaction-ids"></a><span data-ttu-id="9af71-200">Egyedi tranzakcióazonosítók biztosítása</span><span class="sxs-lookup"><span data-stu-id="9af71-200">Ensure unique transaction IDs</span></span>

<span data-ttu-id="9af71-201">A Commerce 10.0.18-as verziójától kezdve a pénztár számára generált tranzakcióazonosítók egymást követőek, és a következő részekből állnak:</span><span class="sxs-lookup"><span data-stu-id="9af71-201">As of the Commerce version 10.0.18 , transaction IDs generated for the point of sale (POS) are sequential and include the following parts:</span></span>

- <span data-ttu-id="9af71-202">Rögzített rész, amely az üzletazonosító és a terminálazonosító éke.</span><span class="sxs-lookup"><span data-stu-id="9af71-202">A fixed part, which is a concatenation of store ID and terminal ID.</span></span> 
- <span data-ttu-id="9af71-203">Követést jelző rész, ami egy számsorozat.</span><span class="sxs-lookup"><span data-stu-id="9af71-203">A sequential part, which is a number sequence.</span></span> 

<span data-ttu-id="9af71-204">Pontosabban a formátum a következő: *{store}-{terminal}-{numbersequence}*.</span><span class="sxs-lookup"><span data-stu-id="9af71-204">Specifically, the format is *{store}-{terminal}-{numbersequence}*.</span></span> 

<span data-ttu-id="9af71-205">Mivel a tranzakcióazonosítók offline és online módban is generálhatók, előfordult, hogy a rendszer ismétlődő tranzakcióazonosítókat hozott létre.</span><span class="sxs-lookup"><span data-stu-id="9af71-205">Because transaction IDs can be generated in offline and online modes, there have been instances of duplicate transaction IDs being generated.</span></span> <span data-ttu-id="9af71-206">Az ismétlődő tranzakcióazonosítók megszüntetése sok manuális adatjavítást igényel.</span><span class="sxs-lookup"><span data-stu-id="9af71-206">Eliminating duplicate transaction IDs requires a lot of manual data fixing.</span></span> 

<span data-ttu-id="9af71-207">A Commerce 10.0.19-es verziója esetén a tranzakcióazonosító formátuma frissült, hogy eltávolítsa a követést jelző részt, és egy 13-jegyű számot használ, amely az idő 1970 óta ezredmásodpercekben eltelt idő kiszámításával jött létre.</span><span class="sxs-lookup"><span data-stu-id="9af71-207">With Commerce version 10.0.19, the transaction ID format has been updated to remove the sequential part and instead uses a 13-digit number generated by calculating the time in milliseconds since 1970.</span></span> <span data-ttu-id="9af71-208">Ezzel a módosítással az új tranzakcióazonosító-formátum: *{store}-{terminal}-{millisecondsSince1970}*.</span><span class="sxs-lookup"><span data-stu-id="9af71-208">With this change, the new transaction ID format is *{store}-{terminal}-{millisecondsSince1970}*.</span></span> <span data-ttu-id="9af71-209">Ezzel a frissítéssel a tranzakcióazonosítók nem egymást követőek, és biztosítja, hogy a tranzakcióazonosítók mindig egyediek.</span><span class="sxs-lookup"><span data-stu-id="9af71-209">This update makes the transaction ID non-sequential and ensures that transaction IDs are always unique.</span></span> 

> [!NOTE]
> <span data-ttu-id="9af71-210">A tranzakcióazonosítókat csak a belső rendszer használja, így nem szükséges, hogy egymást követők legyenek.</span><span class="sxs-lookup"><span data-stu-id="9af71-210">Transaction IDs are meant for internal system use only, so they are not required to be sequential.</span></span> <span data-ttu-id="9af71-211">Sok ország azonban megköveteli, hogy a nyugtaazonosítók egymást követőek legyenek.</span><span class="sxs-lookup"><span data-stu-id="9af71-211">However, many countries require receipt IDs to be sequential.</span></span>

<span data-ttu-id="9af71-212">Az új tranzakcióazonosító-formátum funkciót a **Funkciókezelés** munkaterületről lehet engedélyezni.</span><span class="sxs-lookup"><span data-stu-id="9af71-212">The new transaction ID format feature can be enabled from the **Feature management** workspace.</span></span> 

<span data-ttu-id="9af71-213">Az új tranzakcióazonosítók engedélyezéséhez hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="9af71-213">To enable the use of new transaction IDs, follow these steps:</span></span>

1. <span data-ttu-id="9af71-214">A Commerce-központban lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.</span><span class="sxs-lookup"><span data-stu-id="9af71-214">In Commerce headquarters, go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="9af71-215">Szűrjön a „kiskereskedelem és kereskedelem” modulra.</span><span class="sxs-lookup"><span data-stu-id="9af71-215">Filter for the "retail and commerce" module.</span></span>
1. <span data-ttu-id="9af71-216">Keressen rá **Az új tranzakcióazonosító engedélyezése a tranzakcióazonosítók ismétlődésének elkerülése érdekében** funkció nevére.</span><span class="sxs-lookup"><span data-stu-id="9af71-216">Search for the **Enable new transaction id to avoid duplicate transaction ids** feature name.</span></span>
1. <span data-ttu-id="9af71-217">Válassza ki a funkciót, majd a jobb oldali ablaktáblán válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9af71-217">Select the feature, and then select **Enable Now** in the right pane.</span></span>  
1. <span data-ttu-id="9af71-218">Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="9af71-218">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="9af71-219">Futtassa a **1070 csatornakonfiguráció** és a **1170 pénztár feladatrögzítő** feladatokat az engedélyezett funkció üzletekkel való szinkronizálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="9af71-219">Run the **1070 Channel configuration** and **1170 POS task recorder** jobs to synchronize the enabled feature to the stores.</span></span>
1. <span data-ttu-id="9af71-220">Miután a módosításokat elküldte az üzleteknek, a pénztárterminálokat be kell zárni, majd újra meg kell nyitni, hogy az új tranzakcióazonosító-formátumot használják.</span><span class="sxs-lookup"><span data-stu-id="9af71-220">After the changes have been sent to the stores, POS terminals must be closed and reopened to use the new transaction ID format.</span></span> 

> [!NOTE]
> <span data-ttu-id="9af71-221">Az új tranzakcióazonosító-formátum funkció engedélyezése után nem tilthatja le ezt a funkciót.</span><span class="sxs-lookup"><span data-stu-id="9af71-221">After the new transaction ID format feature is enabled, you will not be able to disable this feature.</span></span> <span data-ttu-id="9af71-222">Ha le kell tiltani, forduljon a Commerce-ügyfélszolgálathoz.</span><span class="sxs-lookup"><span data-stu-id="9af71-222">If it must be disabled, please contact Commerce Support.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9af71-223">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9af71-223">Additional resources</span></span>

[<span data-ttu-id="9af71-224">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="9af71-224">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="9af71-225">Csatorna beállításainak előfeltételei</span><span class="sxs-lookup"><span data-stu-id="9af71-225">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="9af71-226">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-226">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="9af71-227">Hívásközpont csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="9af71-227">Set up a call center channel</span></span>](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
