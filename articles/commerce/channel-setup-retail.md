---
title: Kiskereskedelmi csatorna beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy új kiskereskedelmi csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
ms.date: 01/27/2020
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
ms.openlocfilehash: 713cbe68c151b6893519843611089941cabf0e70
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800591"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="11f0b-103">Retail-csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-103">Set up a retail channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="11f0b-104">Ez a témakör azt mutatja be, hogyan lehet egy új kiskereskedelmi csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="11f0b-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="11f0b-105">A Dynamics 365 Commerce rendszer támogatja a többszörös kiskereskedelmi csatornák használatát.</span><span class="sxs-lookup"><span data-stu-id="11f0b-105">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="11f0b-106">Ezek a kiskereskedelmi csatornák lehetnek online áruházak, hívásközpontok és kiskereskedelmi áruházak (más néven rendes, nem online üzletek).</span><span class="sxs-lookup"><span data-stu-id="11f0b-106">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="11f0b-107">A kiskereskedelmi üzletek csatornái saját fizetési módokkal, árcsoportokkal, (POS) pénztárgépekkel, bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="11f0b-107">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="11f0b-108">Az összes ilyen elemet be kell állítania, kiskereskedelmi üzlet csatornájának létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="11f0b-108">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="11f0b-109">A kiskereskedelmi csatorna létrehozása előtt győződjön meg arról, hogy követi a [csatorna előfeltételeit](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="11f0b-109">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="11f0b-110">Új kiskereskedelmi csatorna létrehozása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="11f0b-110">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="11f0b-111">A navigációs ablaktáblán lépjen a **Modulok \> Csatornák \> Áruházak \> Minden áruház** részhez.</span><span class="sxs-lookup"><span data-stu-id="11f0b-111">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="11f0b-112">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="11f0b-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="11f0b-113">A **Név** mezőben adja meg az új csatorna nevét.</span><span class="sxs-lookup"><span data-stu-id="11f0b-113">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="11f0b-114">Az **Üzlet száma** mezőben adjon meg egy egyedi üzletszámot.</span><span class="sxs-lookup"><span data-stu-id="11f0b-114">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="11f0b-115">A számnak alfanumerikusnak kell lennie, legfeljebb 10 karakterrel.</span><span class="sxs-lookup"><span data-stu-id="11f0b-115">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="11f0b-116">A **jogi személy** legördülő listában adja meg a megfelelő jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="11f0b-116">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="11f0b-117">A **raktár** legördülő listában adja meg a megfelelő raktárat.</span><span class="sxs-lookup"><span data-stu-id="11f0b-117">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="11f0b-118">Az **Üzlet időzónája** mezőből válasszon egy megfelelő időzónát.</span><span class="sxs-lookup"><span data-stu-id="11f0b-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="11f0b-119">Az **Áfacsoport** legördülő listából válassza ki az üzlethez megfelelő áfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="11f0b-119">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="11f0b-120">A **Pénznem** mezőben válassza ki a megfelelő pénznemet.</span><span class="sxs-lookup"><span data-stu-id="11f0b-120">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="11f0b-121">Az **Ügyfél címjegyzéke** mezőben adjon meg érvényes címjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="11f0b-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="11f0b-122">Az **Alapértelmezett ügyfél** mezőben adjon meg egy érvényes alapértelmezett ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="11f0b-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="11f0b-123">A **Funkcióprofil** mezőben válasszon ki egy funkcióprofilt, ha van ilyen.</span><span class="sxs-lookup"><span data-stu-id="11f0b-123">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="11f0b-124">Az **E-mail értesítési profilja** mezőben adjon meg egy érvényes e-mail-értesítési profilt.</span><span class="sxs-lookup"><span data-stu-id="11f0b-124">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="11f0b-125">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11f0b-125">On the action pane, select **Save**.</span></span>

<span data-ttu-id="11f0b-126">A következő kép bemutatja egy új kiskereskedelmi csatorna létrehozását.</span><span class="sxs-lookup"><span data-stu-id="11f0b-126">The following image shows the creation of a new retail channel.</span></span>

![Új kiskereskedelmi csatorna](media/channel-setup-retail-1.png)

<span data-ttu-id="11f0b-128">A következő kép egy példát mutat a kiskereskedelmi csatornára.</span><span class="sxs-lookup"><span data-stu-id="11f0b-128">The following image shows an example retail channel.</span></span>

![Kiskereskedelmi csatorna példája](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="11f0b-130">Egyéb beállítások</span><span class="sxs-lookup"><span data-stu-id="11f0b-130">Other settings</span></span>

<span data-ttu-id="11f0b-131">Számos egyéb választható beállítás érhető el, amely a kiskereskedelmi üzlet szükségletei alapján beállítható a **Kimutatás/zárás** és a **vegyes** szakaszok között.</span><span class="sxs-lookup"><span data-stu-id="11f0b-131">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="11f0b-132">Ezenkívül lásd [A pénztár (POS) képernyő-elrendezései](pos-screen-layouts.md) című részt további információért az alapértelmezett képernyő-elrendezés beállításáról a **Képernyő-elrendezés** szakaszban és a [Kiskereskedelmi hardverállomás konfigurálása és telepítése](retail-hardware-station-configuration-installation.md) című részt telepítési információért a **Hardverállomások** résszel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="11f0b-132">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="11f0b-133">A következő kép egy példát mutat a kiskereskedelmi csatorna beállítási konfigurációjáról.</span><span class="sxs-lookup"><span data-stu-id="11f0b-133">The following image shows an example retail channel setup configuration.</span></span>

![Kiskereskedelmi csatorna konfigurálása – példa](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="11f0b-135">További csatornák beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-135">Additional channel set up</span></span>

<span data-ttu-id="11f0b-136">További cikkek szükségesek, amelyeket be kell állítani egy olyan csatornához, amely a **Művelet ablaktáblán** található a **beállítás** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="11f0b-136">There are additional items that need to be set up for a channel that can be found on the **Action pane** under the **Set up** section.</span></span>

<span data-ttu-id="11f0b-137">Az online csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok, a készpénzbevallások, a szállítási módok, a bevételi/kiadási számlák, a szakaszok, a teljesítési csoport hozzárendelésének és a széfek beállítása.</span><span class="sxs-lookup"><span data-stu-id="11f0b-137">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="11f0b-138">A következő képen a kiskereskedelmi csatorna beállításainak különböző beállításai láthatók a **beállítás** lapon.</span><span class="sxs-lookup"><span data-stu-id="11f0b-138">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Csatorna beállítása](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="11f0b-140">Fizetési módok beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-140">Set up payment methods</span></span>

<span data-ttu-id="11f0b-141">A fizetési módok beállításához a csatornán támogatott valamennyi fizetési típusnál kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="11f0b-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="11f0b-142">A műveleti ablaktáblán válassza a **Beállítás** lapot, majd válassza ki a **Fizetési módokat**.</span><span class="sxs-lookup"><span data-stu-id="11f0b-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="11f0b-143">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="11f0b-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="11f0b-144">A navigációs ablakban válassza ki a kívánt fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="11f0b-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="11f0b-145">Az **általános** szakaszban adjon meg egy **művelet nevét**, és adja meg a kívánt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="11f0b-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="11f0b-146">Adja meg a fizetési típushoz szükséges további beállításokat.</span><span class="sxs-lookup"><span data-stu-id="11f0b-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="11f0b-147">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11f0b-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="11f0b-148">A következő kép egy példát mutat a készpénzfizetési módra.</span><span class="sxs-lookup"><span data-stu-id="11f0b-148">The following image shows an example of a cash payment method.</span></span>

![Fizetési módok – példa](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="11f0b-150">Készpénzelszámolás beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-150">Set up cash declaration</span></span>

1. <span data-ttu-id="11f0b-151">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Készpénzelszámolást**.</span><span class="sxs-lookup"><span data-stu-id="11f0b-151">On the action pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="11f0b-152">A műveleti ablaktáblán válassza az **új** parancsot, majd hozza létre az összes vonatkozó **Érme** és **Bankjegy** címletet.</span><span class="sxs-lookup"><span data-stu-id="11f0b-152">On the action pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="11f0b-153">A következő kép egy példát mutat a készpénzelszámolásra.</span><span class="sxs-lookup"><span data-stu-id="11f0b-153">The following image shows an example of a cash declaration.</span></span>

![Készpénzelszámolások beállításai](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="11f0b-155">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-155">Set up modes of delivery</span></span>

<span data-ttu-id="11f0b-156">A konfigurált szállítási módokat a **Szállítási módok** kiválasztásával tekintheti meg a **Beállítás** lapon a **Műveleti ablaktáblán**.</span><span class="sxs-lookup"><span data-stu-id="11f0b-156">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="11f0b-157">Szállítási mód módosításához vagy hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="11f0b-157">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="11f0b-158">A navigációs ablakban nyissa meg a **Modulok \> Készletkezelés \> Szállítási módok** elemet.</span><span class="sxs-lookup"><span data-stu-id="11f0b-158">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="11f0b-159">A műveleti ablaktáblán válassza az **Új** elemet új szállítási mód létrehozásához, vagy válasszon meglévő módot.</span><span class="sxs-lookup"><span data-stu-id="11f0b-159">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="11f0b-160">A **kiskereskedelmi csatornák** területen válassza a **sor hozzáadása** parancsot a csatorna hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="11f0b-160">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="11f0b-161">Csatornák hozzáadása a szervezeti csomópontok használatával, nem pedig az egyes csatornák hozzáadásával egyszerűsítheti a csatornák hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="11f0b-161">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="11f0b-162">A következő kép egy példát mutat a szállítási módra.</span><span class="sxs-lookup"><span data-stu-id="11f0b-162">The following image shows an example of a mode of delivery.</span></span>

![Szállítási módok beállítása](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="11f0b-164">Bevételi/kiadási számla beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-164">Set up income/expense account</span></span>

<span data-ttu-id="11f0b-165">A bevétel/kiadási számla beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="11f0b-165">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="11f0b-166">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Bevételi/kiadási számla**.</span><span class="sxs-lookup"><span data-stu-id="11f0b-166">On the action pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="11f0b-167">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="11f0b-167">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="11f0b-168">A **Név** mezőbe írjon be egy nevet.</span><span class="sxs-lookup"><span data-stu-id="11f0b-168">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="11f0b-169">A **Keresési név** mezőbe írjon be egy keresési nevet.</span><span class="sxs-lookup"><span data-stu-id="11f0b-169">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="11f0b-170">A **Számlatípus** részben adja meg a számlatípust.</span><span class="sxs-lookup"><span data-stu-id="11f0b-170">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="11f0b-171">Szükség szerint adjon meg szöveget a következőkhöz: **Üzenet 1. sora**, **Üzenet 2. sora**, **1. bizonylatszöveg** és **2. bizonylatszöveg**.</span><span class="sxs-lookup"><span data-stu-id="11f0b-171">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="11f0b-172">A **feladás** területen írja be a feladási adatokat.</span><span class="sxs-lookup"><span data-stu-id="11f0b-172">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="11f0b-173">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11f0b-173">On the action pane, select **Save**.</span></span>

<span data-ttu-id="11f0b-174">A következő kép egy példát mutat egy bevételi/kiadási számlára.</span><span class="sxs-lookup"><span data-stu-id="11f0b-174">The following image shows an example of an income/expense account.</span></span>

![Bevételi/kiadási számlák beállítása](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="11f0b-176">Szakaszok beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-176">Set up sections</span></span>

<span data-ttu-id="11f0b-177">A szakaszok beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="11f0b-177">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="11f0b-178">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Szakaszok**.</span><span class="sxs-lookup"><span data-stu-id="11f0b-178">On the action pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="11f0b-179">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="11f0b-179">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="11f0b-180">A **szakasz száma** mezőbe írja be a szakasz számát.</span><span class="sxs-lookup"><span data-stu-id="11f0b-180">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="11f0b-181">Adjon meg egy leírást a **Leírás** alatt.</span><span class="sxs-lookup"><span data-stu-id="11f0b-181">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="11f0b-182">A **szakaszméret** mezőbe írja be a szakaszméretet.</span><span class="sxs-lookup"><span data-stu-id="11f0b-182">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="11f0b-183">Szükség szerint adja meg az **Általános** és az **Értékesítési statisztikák** további beállításait.</span><span class="sxs-lookup"><span data-stu-id="11f0b-183">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="11f0b-184">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11f0b-184">On the action pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="11f0b-185">Teljesítési csoport hozzárendelésének beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-185">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="11f0b-186">A teljesítési csoport hozzárendelésének beállításához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="11f0b-186">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="11f0b-187">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Teljesítési csoport hozzárendelése**.</span><span class="sxs-lookup"><span data-stu-id="11f0b-187">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="11f0b-188">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="11f0b-188">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="11f0b-189">A **teljesítési csoport** legördülő listából válassza ki a teljesítési csoportot.</span><span class="sxs-lookup"><span data-stu-id="11f0b-189">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="11f0b-190">Ha a **Leírás** legördülő listában adjon meg egy leírást.</span><span class="sxs-lookup"><span data-stu-id="11f0b-190">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="11f0b-191">A műveleti ablaktáblán válassza a **Mentés** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="11f0b-191">On the action pane, select **Save**</span></span>

<span data-ttu-id="11f0b-192">A következő kép egy példát mutat be a teljesítési csoport hozzárendelésének beállítására.</span><span class="sxs-lookup"><span data-stu-id="11f0b-192">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Teljesítési csoport hozzárendeléseinek beállítása](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="11f0b-194">Széfek beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-194">Set up safes</span></span>

<span data-ttu-id="11f0b-195">A széfek beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="11f0b-195">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="11f0b-196">A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **széfek**.</span><span class="sxs-lookup"><span data-stu-id="11f0b-196">On the action pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="11f0b-197">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="11f0b-197">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="11f0b-198">Adja meg a széf nevét.</span><span class="sxs-lookup"><span data-stu-id="11f0b-198">Enter a name for the safe.</span></span>
1. <span data-ttu-id="11f0b-199">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11f0b-199">On the action pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11f0b-200">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="11f0b-200">Additional resources</span></span>

[<span data-ttu-id="11f0b-201">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="11f0b-201">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="11f0b-202">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="11f0b-202">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="11f0b-203">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-203">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="11f0b-204">Hívásközpont csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="11f0b-204">Set up a call center channel</span></span>](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
