---
title: Hívásközpont csatorna beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy új hívásközpont csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 878774c8e5485211525e7e7b63973173f6874b26
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218369"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="f027f-103">Hívásközponti csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="f027f-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f027f-104">Ez a témakör azt mutatja be, hogyan lehet egy új hívásközpont csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="f027f-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f027f-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="f027f-105">Overview</span></span>


<span data-ttu-id="f027f-106">A Dynamics 365 Commerce szolgáltatásban a hívásközpont egyfajta kereskedelmi csatorna, amelyet az alkalmazásban lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="f027f-106">In Dynamics 365 Commerce, a call center is a type of Commerce channel that can be defined in the application.</span></span> <span data-ttu-id="f027f-107">Ha meghatároz egy csatornát a hívásközpont entitások számára, azzal a rendszer képes lesz specifikus adatok és megrendelések feldolgozásához tartozó alapértelmezéseket értékesítési rendelésekhez kötni.</span><span class="sxs-lookup"><span data-stu-id="f027f-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="f027f-108">Noha egy vállalat több hívásközpont-csatornát is megadhat a Commerce-ben, fontos megjegyezni, hogy egy egyéni felhasználót csak egy hívásközpont-csatornához lehet hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="f027f-108">While a company can define multiple call center channels in Commerce, it is important to note that an individual user may only be linked to one call center channel.</span></span> 

<span data-ttu-id="f027f-109">Új hívásközpont-csatorna létrehozása előtt győződjön meg arról, hogy végrehajtotta a [Csatornbeállítás előfeltételeit](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="f027f-109">Before you create a new call center channel, ensure that you have completed the [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="f027f-110">Új hívásközpont csatorna létrehozása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f027f-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="f027f-111">Új hívásközpont csatorna létrehozásához és konfigurálásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f027f-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="f027f-112">A navigációs panelen ugorjon a következő oldalra: **Kiskereskedelem és kereskedelem \> Csatornák \> Hívásközpontok \> Összes hívásközpont**.</span><span class="sxs-lookup"><span data-stu-id="f027f-112">In the navigation pane, go to **Retail and Commerce \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="f027f-113">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="f027f-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f027f-114">A **Név** mezőben adja meg az új csatorna nevét.</span><span class="sxs-lookup"><span data-stu-id="f027f-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="f027f-115">Válassza ki a megfelelő **Jogi személyt** a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="f027f-115">Select the appropriate **Legal entity** from the drop-down.</span></span>
1. <span data-ttu-id="f027f-116">Válassza ki a megfelelő **Raktár** helyet a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="f027f-116">Select the appropriate **Warehouse** location from the drop-down.</span></span> <span data-ttu-id="f027f-117">Ezt a helyet használja a rendszer alapértelmezettként az adott hívásközpont-csatornához létrehozott értékesítési rendeléseknél, hacsak az ügyfél vagy a cikk szintjén nincs más alapértelmezés meghatározva.</span><span class="sxs-lookup"><span data-stu-id="f027f-117">This location will be used as the default on sales orders created for this call center channel, unless other defaults have been defined at the customer or item level.</span></span>
1. <span data-ttu-id="f027f-118">Az **Alapértelmezett ügyfél** mezőben adjon meg egy érvényes alapértelmezett ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="f027f-118">In the **Default customer** field, provide a valid default customer.</span></span> <span data-ttu-id="f027f-119">Ezek az adatok az új vevői rekordok létrehozásakor az alapértelmezések automatikus feltöltésekor segítenek.</span><span class="sxs-lookup"><span data-stu-id="f027f-119">This data is used to assist in autopopulating defaults when new customer records are created.</span></span> <span data-ttu-id="f027f-120">A hívásközpont rendelések létrehozásakor nem tanácsos rendeléseket létrehozni az alapértelmezett vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="f027f-120">When creating call center orders, it is not advisable to create orders for the default customer.</span></span>
1. <span data-ttu-id="f027f-121">Az **E-mail értesítési profilja** mezőben adjon meg egy érvényes e-mail-értesítési profilt.</span><span class="sxs-lookup"><span data-stu-id="f027f-121">In the **Email notification profile** field, provide a valid email notification profile.</span></span> <span data-ttu-id="f027f-122">A hívásközpont-rendelések létrehozásakor és feldolgozásakor a rendszer az e-mail értesítési profilt használja a vevők számára a rendelési állapottal kapcsolatos automatikus figyelmeztetéséhez.</span><span class="sxs-lookup"><span data-stu-id="f027f-122">As call center orders are created and processed, the email notification profile is used to trigger automated email alerts to customers with information about their order status.</span></span>
1. <span data-ttu-id="f027f-123">Adja meg az **Ár-felülbírálás** infókódot.</span><span class="sxs-lookup"><span data-stu-id="f027f-123">Provide a **Price override** info code.</span></span> <span data-ttu-id="f027f-124">Elképzelhető, hogy először létre kell hoznia egy információs kódot.</span><span class="sxs-lookup"><span data-stu-id="f027f-124">You may need to create an info code for this first.</span></span> <span data-ttu-id="f027f-125">Ez az információs kód olyan okkódok csoportját biztosítja, amelyet a felhasználó a hívási központ árának felülbírálási funkciójának használata esetén a programtól megadhat.</span><span class="sxs-lookup"><span data-stu-id="f027f-125">This info code provides the set of reason codes that the user will be prompted to choose from when using the price override functionality on a call center order.</span></span>
1. <span data-ttu-id="f027f-126">Adja meg a **Várakoztatási kód** infókódot.</span><span class="sxs-lookup"><span data-stu-id="f027f-126">Provide a **Hold code** info code.</span></span> <span data-ttu-id="f027f-127">Elképzelhető, hogy először létre kell hoznia egy információs kódot.</span><span class="sxs-lookup"><span data-stu-id="f027f-127">You may need to create an info code for this first.</span></span> <span data-ttu-id="f027f-128">Ez az információs kód olyan nem kötelező okkódok csoportját biztosítja, amelynek kiválasztására a rendszer felszólítja a felhasználót, amikor várakoztatott állapotba helyez egy megrendelést.</span><span class="sxs-lookup"><span data-stu-id="f027f-128">This info code provides the set of optional reason codes that the user will be prompted to choose from when placing an order on hold.</span></span>
1. <span data-ttu-id="f027f-129">Adja meg a **Hitel** infókódot.</span><span class="sxs-lookup"><span data-stu-id="f027f-129">Provide a **Credit** info code.</span></span> <span data-ttu-id="f027f-130">Elképzelhető, hogy először létre kell hoznia egy információs kódot.</span><span class="sxs-lookup"><span data-stu-id="f027f-130">You may need to create an info code for this first.</span></span> <span data-ttu-id="f027f-131">Ez az információs kód olyan okkódkészletet biztosít, amelyből a felhasználónak választania kell a hívásközpont megrendelési jóváírás funkciójának használatakor, ahol egyéb jellegű visszatérítést kell adni az ügyfélnek ügyfélszolgálati okokból.</span><span class="sxs-lookup"><span data-stu-id="f027f-131">This info code provides the set of reason codes that the user can choose from when using the order credit functionality of call center to give misc refunds to the customer for customer service reasons.</span></span>
1. <span data-ttu-id="f027f-132">Nem kötelező: A **Pénzügyi dimenziók** gyorslapon adjon meg pénzügyi dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="f027f-132">Optional: set up financial dimensions on the **Financial dimensions** FastTab.</span></span> <span data-ttu-id="f027f-133">Az itt megadott dimenziók alapértelmezett értékként jelennek meg a hívásközpont-csatornában létrehozott értékesítési rendeléseken.</span><span class="sxs-lookup"><span data-stu-id="f027f-133">The dimensions entered here will default on any sales order created in this call center channel.</span></span>
1. <span data-ttu-id="f027f-134">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="f027f-134">Click **Save**.</span></span>

<span data-ttu-id="f027f-135">A következő kép bemutatja egy új hívásközpont csatorna létrehozását.</span><span class="sxs-lookup"><span data-stu-id="f027f-135">The following image shows the creation of a new call center channel.</span></span>

![Új hívásközponti csatorna](media/channel-setup-callcenter-1.png)

<span data-ttu-id="f027f-137">A következő kép egy példát mutat a hívásközpont csatornára.</span><span class="sxs-lookup"><span data-stu-id="f027f-137">The following image shows an example call center channel.</span></span>

![Hívásközponti csatorna – példa](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="f027f-139">További csatornák beállítása</span><span class="sxs-lookup"><span data-stu-id="f027f-139">Additional channel setup</span></span>

<span data-ttu-id="f027f-140">A hívásközpont csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok és szállítási módok beállítása.</span><span class="sxs-lookup"><span data-stu-id="f027f-140">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="f027f-141">A következő képen láthatók a **Szállítási módok** és a **Fizetési módok** beállított lehetőségei a **Beállítás** lapon.</span><span class="sxs-lookup"><span data-stu-id="f027f-141">The following image shows **Modes of delivery** and **Payment methods** setup options on the **Set up** tab.</span></span>

![További hívásközpont-csatorna-beállítási műveletek](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="f027f-143">Fizetési módok beállítása</span><span class="sxs-lookup"><span data-stu-id="f027f-143">Set up payment methods</span></span>

<span data-ttu-id="f027f-144">A fizetési módok beállításához a csatornán támogatott valamennyi fizetési típusnál kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f027f-144">To set up payment methods, follow these steps for each payment type supported on this channel.</span></span> <span data-ttu-id="f027f-145">A felhasználóknak be kell jelölni az előre definiált fizetési módokat, hogy a hívásközpont csatornához kapcsolják őket.</span><span class="sxs-lookup"><span data-stu-id="f027f-145">Users will be required to select from pre-defined payment methods to link them to the call center channel.</span></span> <span data-ttu-id="f027f-146">Mielőtt beállítja a hívásközpont fizetési módszereit, először állítsa be a fizetés alapvető módszereit a **Kiskereskedelem és kereskedelem \> Csatornabeállítás \> Fizetési módszerek \> Fizetési módszerek** pontban.</span><span class="sxs-lookup"><span data-stu-id="f027f-146">Before setting up your call center payment methods, first set up your master methods of payment in **Retail and Commerce \> Channel setup \> Payment methods \> Payment methods**.</span></span>

1. <span data-ttu-id="f027f-147">A műveleti ablaktáblán válassza a **Beállítás** lapot, majd válassza ki a **Fizetési módokat**.</span><span class="sxs-lookup"><span data-stu-id="f027f-147">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="f027f-148">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="f027f-148">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f027f-149">A navigációs ablakban válasszon ki egy fizetési módot az előre meghatározott kifizetésekhez.</span><span class="sxs-lookup"><span data-stu-id="f027f-149">In the navigation pane, select a payment method from the pre-defined payments available.</span></span>
1. <span data-ttu-id="f027f-150">Adja meg a fizetési típushoz szükséges további beállításokat.</span><span class="sxs-lookup"><span data-stu-id="f027f-150">Configure any additional settings as required for the payment type.</span></span> <span data-ttu-id="f027f-151">Hitelkártyák, ajándékutalványok vagy törzsvásárlói kártyák esetében a **kártya beállítási** funkciójának kiválasztásával további beállításokat kell megadni.</span><span class="sxs-lookup"><span data-stu-id="f027f-151">For credit cards, gift cards, or loyalty cards, additional setup is required by selecting the **Card setup** function.</span></span> 
1. <span data-ttu-id="f027f-152">A **feladás** szakasz kifizetési típusához konfigurálja a megfelelő feladási fiókokat.</span><span class="sxs-lookup"><span data-stu-id="f027f-152">Configure proper posting accounts for the payment type in the **Posting** section.</span></span>
1. <span data-ttu-id="f027f-153">A Művelet panelen kattintson a **Mentés** elemre.</span><span class="sxs-lookup"><span data-stu-id="f027f-153">On the action pane, click **Save**.</span></span>

<span data-ttu-id="f027f-154">A következő kép egy példát mutat a készpénzfizetési módra.</span><span class="sxs-lookup"><span data-stu-id="f027f-154">The following image shows an example of a cash payment method.</span></span>

![Fizetési módok – példa](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="f027f-156">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="f027f-156">Set up modes of delivery</span></span>

<span data-ttu-id="f027f-157">A konfigurált szállítási módokat a **Szállítási módok** kiválasztásával tekintheti meg a **Beállítás** lapon a **Műveleti ablaktáblán**.</span><span class="sxs-lookup"><span data-stu-id="f027f-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="f027f-158">Ha módosítani szeretné vagy hozzáadna egy szállítási módot, amelyet a hívásközpont-csatornához társítana, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f027f-158">To change or add a mode of delivery to be associated to the call center channel, follow these steps.</span></span>

1. <span data-ttu-id="f027f-159">A hívásközpont szállítási módok képernyőjén válassza a **Szállítási módok kezelése** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="f027f-159">From the Call center modes of delivery form, select **Manage modes of delivery**</span></span>
1. <span data-ttu-id="f027f-160">A műveleti ablaktáblán válassza az **Új** elemet új szállítási mód létrehozásához, vagy válasszon meglévő módot.</span><span class="sxs-lookup"><span data-stu-id="f027f-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="f027f-161">A **kiskereskedelmi csatornák** területen válassza a **sor hozzáadása** parancsot a hívásközpont-csatorna hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="f027f-161">In the **Retail channels** section, click **Add line** to add the call center channel.</span></span> <span data-ttu-id="f027f-162">Csatornák hozzáadása a szervezeti csomópontok használatával, nem pedig az egyes csatornák hozzáadásával egyszerűsítheti a csatornák hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="f027f-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>
1. <span data-ttu-id="f027f-163">Ellenőrizze, hogy a szállítási mód be van-e állítva a **termékek** gyorslap és a **címek** gyorslap adataival.</span><span class="sxs-lookup"><span data-stu-id="f027f-163">Ensure the mode of delivery has been configured with data on the **Products** FastTab and the **Addresses** FastTab.</span></span> <span data-ttu-id="f027f-164">Ha a szállítási mód esetében nem érvényes egyik termék vagy szállítási cím sem, akkor a rendelésbevitel során a rendszer hibákat eredményez.</span><span class="sxs-lookup"><span data-stu-id="f027f-164">If no products or delivery addresses are valid for the mode of delivery, choosing it during order entry will result in errors.</span></span>
1. <span data-ttu-id="f027f-165">Miután bármilyen módosítás történt a hívásközpont szállításimód-konfigurációknál, a **Szállítási módok feldolgozása** feladatot futtatni kell a módosítási mátrix alábontásához.</span><span class="sxs-lookup"><span data-stu-id="f027f-165">After any changes have been made to the call center mode of delivery configurations, the **Process delivery modes** job must be run to explode the change matrix.</span></span> <span data-ttu-id="f027f-166">Ez a feladat a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Szállítási módok feldolgozása** pontban található.</span><span class="sxs-lookup"><span data-stu-id="f027f-166">This job can be found by navigating to **Retail and Commerce \> Retail and Commerce IT \> Process delivery modes**.</span></span>

<span data-ttu-id="f027f-167">A következő kép egy példát mutat a szállítási módra.</span><span class="sxs-lookup"><span data-stu-id="f027f-167">The following image shows an example of a mode of delivery.</span></span>

![Szállítási módok beállítása](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a><span data-ttu-id="f027f-169">Csatornafelhasználók beállítása</span><span class="sxs-lookup"><span data-stu-id="f027f-169">Set up channel users</span></span>

<span data-ttu-id="f027f-170">Ha a Commerce központból a hívásközpont-csatornához kapcsolódó értékesítési rendelést szeretne létrehozni, akkor az értékesítési rendelést létrehozó felhasználónak a hívásközpont csatornához kell kapcsolódnia.</span><span class="sxs-lookup"><span data-stu-id="f027f-170">To create a sales order that is linked to the call center channel from Commerce Headquarters, the user creating the sales order must be linked to the call center channel.</span></span> <span data-ttu-id="f027f-171">A felhasználó nem kapcsolhat manuálisan a Commerce központ alkalmazásban létrehozott értékesítési rendelést a hívásközpont csatornához.</span><span class="sxs-lookup"><span data-stu-id="f027f-171">The user cannot manually link a sales order created in Commerce Headquarters to the call center channel.</span></span> <span data-ttu-id="f027f-172">A hivatkozás rendszerezett, és a felhasználónm és a felhasználó kapcsolatán alapul a hívásközpont-csatornával.</span><span class="sxs-lookup"><span data-stu-id="f027f-172">The link is systematic, and is based on the user and the user's relationship to the call center channel.</span></span> <span data-ttu-id="f027f-173">Egy felhasználó csak egy hívásközpont-csatornához kapcsolható.</span><span class="sxs-lookup"><span data-stu-id="f027f-173">A user may only be linked to one call center channel.</span></span>

1. <span data-ttu-id="f027f-174">A műveleti ablaktáblán válassza a **Csatorna** lapot, és válassza ki a **Csatornafelhasználókat**.</span><span class="sxs-lookup"><span data-stu-id="f027f-174">On the action pane, select the **Channel** tab, and then select **Channel users**.</span></span>
1. <span data-ttu-id="f027f-175">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="f027f-175">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f027f-176">Egy meglévő **Felhasználói azonosító** kiválasztásával a legördülő listából összekapcsolhatja a felhasználót a hívási központ csatornával</span><span class="sxs-lookup"><span data-stu-id="f027f-176">Choose an existing **User ID** from the dropdown selection list to link this user to the call center channel</span></span>

<span data-ttu-id="f027f-177">Miután kész a csatornafelhasználó beállítása, és a felhasználó létrehoz egy új értékesítési rendelést a Commerce központban, a rendszer az értékesítési rendelést hozzákapcsolja a társított hívásközpont-csatornához.</span><span class="sxs-lookup"><span data-stu-id="f027f-177">After the channel user setup is done and the user creates a new sales order in Commerce Headquarters, the sales order will be linked to their associated call center channel.</span></span> <span data-ttu-id="f027f-178">A csatorna minden konfigurációját módszeresen fogja alkalmazni az értékesítési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="f027f-178">Any configurations for this channel will be applied systematically to the sales order.</span></span> <span data-ttu-id="f027f-179">A felhasználó megadhatja, hogy az értékesítési rendelés melyik hívásközpont-csatornához kapcsolódik, és az értékesítési rendelés fejlécében megtekinti a csatorna nevének hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="f027f-179">A user can confirm which call center channel the sales order is linked to by viewing the channel name reference on the sales order header.</span></span>


### <a name="set-up-price-groups"></a><span data-ttu-id="f027f-180">Árcsoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="f027f-180">Set up price groups</span></span>

<span data-ttu-id="f027f-181">Az árcsoport megadása nem kötelező, de ha megadja, szabályozhatja, hogy mely eladási árakat ajánlja fel a program a hívásközpont-csatornában a vevők számára.</span><span class="sxs-lookup"><span data-stu-id="f027f-181">Price groups are optional, but if used, can control which sales prices will be offered to customers placing orders in the call center channel.</span></span> <span data-ttu-id="f027f-182">Ha nincs beállítva árcsoport a vevőhöz, vagy ha a katalógusban szereplő árcsoport nem az értékesítési rendelésen van alkalmazva (a hívásközpont rendelési fejléc **forráskód-azonosító** mezője alapján), akkor a csatorna árcsoport a cikkek árának megtalálására szolgál.</span><span class="sxs-lookup"><span data-stu-id="f027f-182">If a price group has not been configured for the customer, or if catalog price groups are not being applied to the sales order (using the **Source code ID** field on the call center order header), then the channel price group is used to locate item prices.</span></span> <span data-ttu-id="f027f-183">Ha egy árcsoport nem található a hívásközpont csatornán, akkor a rendszer az alapértelmezett cikkek alapárát használja.</span><span class="sxs-lookup"><span data-stu-id="f027f-183">If a price group is not found on the call center channel, the default item master prices are used.</span></span> 

<span data-ttu-id="f027f-184">Egy árcsoport beállításához hajtsa végre a következő műveleteket.</span><span class="sxs-lookup"><span data-stu-id="f027f-184">To set up a price group, do the following.</span></span>

1. <span data-ttu-id="f027f-185">A műveleti ablaktáblán válassza a **Csatorna** lapot, és válassza ki az **Árcsoportokat**.</span><span class="sxs-lookup"><span data-stu-id="f027f-185">On the action pane, click the **Channel** tab, and then select **Price groups**.</span></span>
1. <span data-ttu-id="f027f-186">A műveleti panelen kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="f027f-186">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="f027f-187">**Kiskereskedelmi árcsoport** kiválasztása a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="f027f-187">Select a **Retail price group** from the dropdown selection list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f027f-188">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f027f-188">Additional resources</span></span>

[<span data-ttu-id="f027f-189">Csatorna beállításainak előfeltételei</span><span class="sxs-lookup"><span data-stu-id="f027f-189">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="f027f-190">Hívásközpont értékesítési funkciói</span><span class="sxs-lookup"><span data-stu-id="f027f-190">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="f027f-191">Hívásközpont rendelésfeldolgozási beállításainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="f027f-191">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="f027f-192">Hívásközpont-katalógusok</span><span class="sxs-lookup"><span data-stu-id="f027f-192">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="f027f-193">Csalással kapcsolatos figyelmeztetések beállítása és használata</span><span class="sxs-lookup"><span data-stu-id="f027f-193">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="f027f-194">Folytonossági programok beállítása hívásközpontok számára</span><span class="sxs-lookup"><span data-stu-id="f027f-194">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]