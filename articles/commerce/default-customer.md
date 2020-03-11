---
title: Alapértelmezett vevő létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce megoldásban egy csatorna létrehozásakor használandó alapértelmezett vevőt létrehozni.
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
ms.openlocfilehash: ba1d10a897f349703737068d772423f7d0292944
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057962"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="ce11b-103">Alapértelmezett vevő létrehozása</span><span class="sxs-lookup"><span data-stu-id="ce11b-103">Create a default customer</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ce11b-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce megoldásban egy csatorna létrehozásakor használandó alapértelmezett vevőt létrehozni.</span><span class="sxs-lookup"><span data-stu-id="ce11b-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ce11b-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="ce11b-105">Overview</span></span>

<span data-ttu-id="ce11b-106">Csatorna létrehozásakor meg kell adni egy alapértelmezett vevőt.</span><span class="sxs-lookup"><span data-stu-id="ce11b-106">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="ce11b-107">Az alapértelmezett vevő egyszerűen létrehozható a vevőcsoport és a vevői címjegyzék létrehozása után.</span><span class="sxs-lookup"><span data-stu-id="ce11b-107">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="ce11b-108">Vevőcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="ce11b-108">Create a customer group</span></span>

<span data-ttu-id="ce11b-109">Ha még nem léteznek vevőcsoportok, létrehozhat egyet.</span><span class="sxs-lookup"><span data-stu-id="ce11b-109">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="ce11b-110">A példák lehetnek a különböző vevőcsoportok, például nagykereskedelem, kiskereskedelem, internet, alkalmazottak.</span><span class="sxs-lookup"><span data-stu-id="ce11b-110">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="ce11b-111">Ügyfélcsoport létrehozásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="ce11b-111">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="ce11b-112">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Ügyfelek \> Ügyfélcsoportok** részhez.</span><span class="sxs-lookup"><span data-stu-id="ce11b-112">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="ce11b-113">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="ce11b-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="ce11b-114">Az **Ügyfélcsoport** mezőbe írja be az ügyfélcsoport azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="ce11b-114">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="ce11b-115">Ha szükséges, akkor adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ce11b-115">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="ce11b-116">Ha szükséges, akkor adjon meg egy értéket a **Fizetési feltételek** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ce11b-116">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="ce11b-117">**A számla esedékességének dátuma és a fizetési dátum közötti idő** mezőben adja meg a megfelelő értéket.</span><span class="sxs-lookup"><span data-stu-id="ce11b-117">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="ce11b-118">Ha szükséges, az **Alapértelmezett adócsoport** mezőben adjon meg egy adócsoportot.</span><span class="sxs-lookup"><span data-stu-id="ce11b-118">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="ce11b-119">Szükség szerint jelölje be **Az árak tartalmazzák az áfát** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="ce11b-119">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="ce11b-120">Ha szükséges, írja be a megfelelő értéket az **Alapértelmezett leírási indok** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ce11b-120">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="ce11b-121">A következő kép több konfigurált vevői csoportot mutat be.</span><span class="sxs-lookup"><span data-stu-id="ce11b-121">The following image shows several configured customer groups.</span></span>

![Vevőcsoportok](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="ce11b-123">Új ügyfélcímjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="ce11b-123">Create a customer address book</span></span>

<span data-ttu-id="ce11b-124">A vevőnek címjegyzékhez kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="ce11b-124">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="ce11b-125">Ha még nincs létrehozva, akkor létre kell hozni egyet.</span><span class="sxs-lookup"><span data-stu-id="ce11b-125">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="ce11b-126">Ügyfélcímjegyzék létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ce11b-126">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="ce11b-127">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Címjegyzékek** részhez.</span><span class="sxs-lookup"><span data-stu-id="ce11b-127">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="ce11b-128">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="ce11b-128">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="ce11b-129">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="ce11b-129">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="ce11b-130">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ce11b-130">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="ce11b-131">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ce11b-131">On the action pane, select **Save**.</span></span>

<span data-ttu-id="ce11b-132">A következő kép egy példát mutat a címjegyzékre.</span><span class="sxs-lookup"><span data-stu-id="ce11b-132">The following image shows an example address book.</span></span>

![Címjegyzék](media/address-book.png)

## <a name="create-a-default-customer"></a><span data-ttu-id="ce11b-134">Alapértelmezett vevő létrehozása</span><span class="sxs-lookup"><span data-stu-id="ce11b-134">Create a default customer</span></span>

<span data-ttu-id="ce11b-135">Alapértelmezett ügyfél létrehozásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="ce11b-135">To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id="ce11b-136">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Minden ügyfél \> Ügyfélcsoportok** részhez.</span><span class="sxs-lookup"><span data-stu-id="ce11b-136">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="ce11b-137">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="ce11b-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="ce11b-138">A **Típus** legördülő listán válassza a Személy elemet.</span><span class="sxs-lookup"><span data-stu-id="ce11b-138">In the **Type** drop-down list, select "Person".</span></span>
1. <span data-ttu-id="ce11b-139">A **Vevőfiók** legördülő listából válassza ki vagy adja meg a számlaszámot (például "100001").</span><span class="sxs-lookup"><span data-stu-id="ce11b-139">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="ce11b-140">Az **Utónév** legördülő listából válassza ki vagy írja be a nevet (például "Alapértelmezett").</span><span class="sxs-lookup"><span data-stu-id="ce11b-140">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="ce11b-141">A **Középső név** legördülő listából válassza ki vagy írja be a nevet (például "Kiskereskedelmi").</span><span class="sxs-lookup"><span data-stu-id="ce11b-141">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="ce11b-142">A **Vezetéknév** legördülő listából válassza ki vagy írja be a nevet (például "Ügyfél").</span><span class="sxs-lookup"><span data-stu-id="ce11b-142">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="ce11b-143">A **Pénznem** legördülő listából válassza ki vagy írja be a pénznem nevét (például "USD").</span><span class="sxs-lookup"><span data-stu-id="ce11b-143">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="ce11b-144">A **Pénznem** legördülő listában válassza ki a korábban létrehozott ügyfélcsoportot.</span><span class="sxs-lookup"><span data-stu-id="ce11b-144">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="ce11b-145">A **Címjegyzékek** legördülő listából válasszon ki egy meglévő vevői címjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="ce11b-145">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="ce11b-146">A mentéshez válassza a **Mentés** parancsot, majd térjen vissza a vevő adatainak képernyőjére az új vevő számára.</span><span class="sxs-lookup"><span data-stu-id="ce11b-146">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="ce11b-147">Nem szükséges hozzáadni egy alapértelmezett vevő címét.</span><span class="sxs-lookup"><span data-stu-id="ce11b-147">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="ce11b-148">A következő kép egy példát mutat az ügyféllétrehozásra.</span><span class="sxs-lookup"><span data-stu-id="ce11b-148">The following image shows an example of customer creation.</span></span>

![Alapértelmezett vevő létrehozása](media/default-customer-creation.png)

<span data-ttu-id="ce11b-150">A következő kép egy alapértelmezett vevői konfigurációt mutat be.</span><span class="sxs-lookup"><span data-stu-id="ce11b-150">The following image shows a default customer configuration.</span></span>

![Vevői mintakonfiguráció](media/default-customer-configuration1.png)

<span data-ttu-id="ce11b-152">A vevő részletek képernyőjén található alapértelmezett értékek többsége maradhat, de a két értéket módosítani kell.</span><span class="sxs-lookup"><span data-stu-id="ce11b-152">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="ce11b-153">A vevő részletes adatai képernyő bontsa ki a **Értékesítési rendelés alapértelmezései** elemet.</span><span class="sxs-lookup"><span data-stu-id="ce11b-153">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="ce11b-154">A **Webhely** legördülő listából válassza ki vagy adja meg az előre konfigurált webhelyet.</span><span class="sxs-lookup"><span data-stu-id="ce11b-154">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="ce11b-155">A **Raktár** legördülő listából válassza ki vagy adja meg az előre konfigurált raktárat.</span><span class="sxs-lookup"><span data-stu-id="ce11b-155">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="ce11b-156">A következő kép egy példát mutat az ügyfélkonfigurációra.</span><span class="sxs-lookup"><span data-stu-id="ce11b-156">The following image shows an example customer configuration.</span></span>

![Példa ügyfélkonfiguráció](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="ce11b-158">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ce11b-158">Additional resources</span></span>

[<span data-ttu-id="ce11b-159">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="ce11b-159">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="ce11b-160">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="ce11b-160">Channel setup prerequisites</span></span>](channels-prerequisites.md)
