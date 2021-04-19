---
title: Alapértelmezett vevő létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce megoldásban egy csatorna létrehozásakor használandó alapértelmezett vevőt létrehozni.
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
ms.openlocfilehash: ecdf4e5618d3397527bf83977857fbe3f8dbb265
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799179"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="afbbe-103">Alapértelmezett vevő létrehozása</span><span class="sxs-lookup"><span data-stu-id="afbbe-103">Create a default customer</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="afbbe-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce megoldásban egy csatorna létrehozásakor használandó alapértelmezett vevőt létrehozni.</span><span class="sxs-lookup"><span data-stu-id="afbbe-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="afbbe-105">Csatorna létrehozásakor meg kell adni egy alapértelmezett vevőt.</span><span class="sxs-lookup"><span data-stu-id="afbbe-105">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="afbbe-106">Az alapértelmezett vevő egyszerűen létrehozható a vevőcsoport és a vevői címjegyzék létrehozása után.</span><span class="sxs-lookup"><span data-stu-id="afbbe-106">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="afbbe-107">Vevőcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="afbbe-107">Create a customer group</span></span>

<span data-ttu-id="afbbe-108">Ha még nem léteznek vevőcsoportok, létrehozhat egyet.</span><span class="sxs-lookup"><span data-stu-id="afbbe-108">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="afbbe-109">A példák lehetnek a különböző vevőcsoportok, például nagykereskedelem, kiskereskedelem, internet, alkalmazottak.</span><span class="sxs-lookup"><span data-stu-id="afbbe-109">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="afbbe-110">Ügyfélcsoport létrehozásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="afbbe-110">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="afbbe-111">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Ügyfelek \> Ügyfélcsoportok** részhez.</span><span class="sxs-lookup"><span data-stu-id="afbbe-111">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="afbbe-112">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="afbbe-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="afbbe-113">Az **Ügyfélcsoport** mezőbe írja be az ügyfélcsoport azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="afbbe-113">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="afbbe-114">Ha szükséges, akkor adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="afbbe-114">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="afbbe-115">Ha szükséges, akkor adjon meg egy értéket a **Fizetési feltételek** mezőben.</span><span class="sxs-lookup"><span data-stu-id="afbbe-115">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="afbbe-116">**A számla esedékességének dátuma és a fizetési dátum közötti idő** mezőben adja meg a megfelelő értéket.</span><span class="sxs-lookup"><span data-stu-id="afbbe-116">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="afbbe-117">Ha szükséges, az **Alapértelmezett adócsoport** mezőben adjon meg egy adócsoportot.</span><span class="sxs-lookup"><span data-stu-id="afbbe-117">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="afbbe-118">Szükség szerint jelölje be **Az árak tartalmazzák az áfát** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="afbbe-118">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="afbbe-119">Ha szükséges, írja be a megfelelő értéket az **Alapértelmezett leírási indok** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="afbbe-119">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="afbbe-120">A következő kép több konfigurált vevői csoportot mutat be.</span><span class="sxs-lookup"><span data-stu-id="afbbe-120">The following image shows several configured customer groups.</span></span>

![Vevőcsoportok](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="afbbe-122">Új ügyfélcímjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="afbbe-122">Create a customer address book</span></span>

<span data-ttu-id="afbbe-123">A vevőnek címjegyzékhez kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="afbbe-123">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="afbbe-124">Ha még nincs létrehozva, akkor létre kell hozni egyet.</span><span class="sxs-lookup"><span data-stu-id="afbbe-124">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="afbbe-125">Ügyfélcímjegyzék létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="afbbe-125">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="afbbe-126">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Címjegyzékek** részhez.</span><span class="sxs-lookup"><span data-stu-id="afbbe-126">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="afbbe-127">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="afbbe-127">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="afbbe-128">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="afbbe-128">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="afbbe-129">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="afbbe-129">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="afbbe-130">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="afbbe-130">On the action pane, select **Save**.</span></span>

<span data-ttu-id="afbbe-131">A következő kép egy példát mutat a címjegyzékre.</span><span class="sxs-lookup"><span data-stu-id="afbbe-131">The following image shows an example address book.</span></span>

![Címjegyzék](media/address-book.png)

## <a name="create-a-default-customer&quot;></a><span data-ttu-id=&quot;afbbe-133&quot;>Alapértelmezett vevő létrehozása</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;afbbe-133&quot;>Create a default customer</span></span>

<span data-ttu-id=&quot;afbbe-134&quot;>Alapértelmezett ügyfél létrehozásához tegye a következőket.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;afbbe-134&quot;>To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id=&quot;afbbe-135&quot;>A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Minden ügyfél \> Ügyfélcsoportok** részhez.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;afbbe-135&quot;>In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id=&quot;afbbe-136&quot;>A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;afbbe-136&quot;>On the action pane, select **New**.</span></span>
1. <span data-ttu-id=&quot;afbbe-137&quot;>A **Típus** legördülő listán válassza a Személy elemet.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;afbbe-137&quot;>In the **Type** drop-down list, select &quot;Person&quot;.</span></span>
1. <span data-ttu-id=&quot;afbbe-138&quot;>A **Vevőfiók** legördülő listából válassza ki vagy adja meg a számlaszámot (például &quot;100001").</span><span class="sxs-lookup"><span data-stu-id="afbbe-138">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="afbbe-139">Az **Utónév** legördülő listából válassza ki vagy írja be a nevet (például "Alapértelmezett").</span><span class="sxs-lookup"><span data-stu-id="afbbe-139">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="afbbe-140">A **Középső név** legördülő listából válassza ki vagy írja be a nevet (például "Kiskereskedelmi").</span><span class="sxs-lookup"><span data-stu-id="afbbe-140">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="afbbe-141">A **Vezetéknév** legördülő listából válassza ki vagy írja be a nevet (például "Ügyfél").</span><span class="sxs-lookup"><span data-stu-id="afbbe-141">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="afbbe-142">A **Pénznem** legördülő listából válassza ki vagy írja be a pénznem nevét (például "USD").</span><span class="sxs-lookup"><span data-stu-id="afbbe-142">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="afbbe-143">A **Pénznem** legördülő listában válassza ki a korábban létrehozott ügyfélcsoportot.</span><span class="sxs-lookup"><span data-stu-id="afbbe-143">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="afbbe-144">A **Címjegyzékek** legördülő listából válasszon ki egy meglévő vevői címjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="afbbe-144">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="afbbe-145">A mentéshez válassza a **Mentés** parancsot, majd térjen vissza a vevő adatainak képernyőjére az új vevő számára.</span><span class="sxs-lookup"><span data-stu-id="afbbe-145">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="afbbe-146">Nem szükséges hozzáadni egy alapértelmezett vevő címét.</span><span class="sxs-lookup"><span data-stu-id="afbbe-146">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="afbbe-147">A következő kép egy példát mutat az ügyféllétrehozásra.</span><span class="sxs-lookup"><span data-stu-id="afbbe-147">The following image shows an example of customer creation.</span></span>

![Alapértelmezett vevő létrehozása](media/default-customer-creation.png)

<span data-ttu-id="afbbe-149">A következő kép egy alapértelmezett vevői konfigurációt mutat be.</span><span class="sxs-lookup"><span data-stu-id="afbbe-149">The following image shows a default customer configuration.</span></span>

![Vevői mintakonfiguráció](media/default-customer-configuration1.png)

<span data-ttu-id="afbbe-151">A vevő részletek képernyőjén található alapértelmezett értékek többsége maradhat, de a két értéket módosítani kell.</span><span class="sxs-lookup"><span data-stu-id="afbbe-151">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="afbbe-152">A vevő részletes adatai képernyő bontsa ki a **Értékesítési rendelés alapértelmezései** elemet.</span><span class="sxs-lookup"><span data-stu-id="afbbe-152">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="afbbe-153">A **Webhely** legördülő listából válassza ki vagy adja meg az előre konfigurált webhelyet.</span><span class="sxs-lookup"><span data-stu-id="afbbe-153">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="afbbe-154">A **Raktár** legördülő listából válassza ki vagy adja meg az előre konfigurált raktárat.</span><span class="sxs-lookup"><span data-stu-id="afbbe-154">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="afbbe-155">A következő kép egy példát mutat az ügyfélkonfigurációra.</span><span class="sxs-lookup"><span data-stu-id="afbbe-155">The following image shows an example customer configuration.</span></span>

![Példa ügyfélkonfiguráció](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="afbbe-157">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="afbbe-157">Additional resources</span></span>

[<span data-ttu-id="afbbe-158">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="afbbe-158">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="afbbe-159">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="afbbe-159">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
