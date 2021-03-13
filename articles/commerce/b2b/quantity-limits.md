---
title: Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez
description: Ez a témakör azt ismerteti, hogyan állíthat be termékmennyiség-korlátokat a vállalkozások közötti (B2B) e-kereskedelmi webhelyekhez.
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e70648da2cc1c526625b6e34fd0867d40abb5a85
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035917"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a><span data-ttu-id="45f13-103">Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez</span><span class="sxs-lookup"><span data-stu-id="45f13-103">Set product quantity limits for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="45f13-104">Ez a témakör azt ismerteti, hogyan állíthat be termékmennyiség-korlátokat a vállalkozások közötti (B2B) e-kereskedelmi webhelyekhez.</span><span class="sxs-lookup"><span data-stu-id="45f13-104">This topic describes how to set product quantity limits for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="45f13-105">A legtöbb terméknek van egy mértékegysége, amely meghatározza a csoportosításukat.</span><span class="sxs-lookup"><span data-stu-id="45f13-105">Most products have a unit of measure that defines their grouping.</span></span> <span data-ttu-id="45f13-106">A csoportosítás befolyásolja a termékek értékesítésének módját.</span><span class="sxs-lookup"><span data-stu-id="45f13-106">The grouping affects how the products can be sold.</span></span> <span data-ttu-id="45f13-107">Egyes termékek további, mennyiségi csoportosítást tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="45f13-107">Some products might have an additional grouping for quantities.</span></span> <span data-ttu-id="45f13-108">Ez a csoportosítás határozza meg, hogy a termékek egyedi egységként vagy többszörösként értékesíthetők-e, és hogy van-e minimális vagy maximális rendelési mennyiségi korlát, amelyet be kell tartani.</span><span class="sxs-lookup"><span data-stu-id="45f13-108">This grouping determines whether the products can be sold as individual units or multiples, and whether there is a minimum or maximum order quantity limit that must be followed.</span></span>

<span data-ttu-id="45f13-109">A mennyiségkorlátozó szolgáltatás biztosítja, hogy a Microsoft Dynamics 365 Commerce rendszerben (az alapértelmezett rendelési beállításokban vagy a Commerce webhelykészítő webhelybeállításaiban) konfigurált minimális, maximális, többszörös és szabványos mennyiségeket alkalmazza a rendszer az e-kereskedelmi webhelyeken leadott vevői rendelésekre.</span><span class="sxs-lookup"><span data-stu-id="45f13-109">The quantity limiting feature ensures that the minimum, maximum, multiple, and standard quantities that are configured in Microsoft Dynamics 365 Commerce (in the default order settings or the Commerce site builder site settings) are applied to customer orders that are placed on an e-commerce site.</span></span> <span data-ttu-id="45f13-110">A termékmennyiség-korlátok jelenleg nem támogatottak pénztár és a hívásközpontok esetében.</span><span class="sxs-lookup"><span data-stu-id="45f13-110">Product quantity limits aren't currently supported for the point of sale (POS) and call centers.</span></span>

<span data-ttu-id="45f13-111">Számos kiskereskedő biztosít lehetőséget vevői rendelésekre (más néven speciális rendelésekre), hogy így elégítsen ki termékkel és teljesítéssel kapcsolatos különböző igényeket.</span><span class="sxs-lookup"><span data-stu-id="45f13-111">Many retailers provide the option of customer orders (also known as special orders) to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="45f13-112">Íme néhány tipikus forgatókönyv:</span><span class="sxs-lookup"><span data-stu-id="45f13-112">Here are some typical scenarios:</span></span>

- <span data-ttu-id="45f13-113">Az ügyfél azt szeretné, hogy a meghatározott változatokból álló termékeket kevés többszörösében értékesítsék.</span><span class="sxs-lookup"><span data-stu-id="45f13-113">A customer wants products of specific variants to be sold in multiples of a few.</span></span>
- <span data-ttu-id="45f13-114">Egy vevő egy olyan üzetben vagy helyen szeretné átvenni a termékeket, amely eltér attól az üzlettől vagy helytől, ahol az ügyfél megvásárolta az adott termékeket.</span><span class="sxs-lookup"><span data-stu-id="45f13-114">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span> <span data-ttu-id="45f13-115">Az üzletek csomagolási szabványai azonban eltérnek az online forgalmazására vonatkozó csomagolási szabványoktól.</span><span class="sxs-lookup"><span data-stu-id="45f13-115">However, the packing standards for the stores differ from the packing standards for online sales distribution.</span></span>
- <span data-ttu-id="45f13-116">Az ügyfél limitált kiadású terméket szeretne vásárolni, amely maximális mennyiségkorláttal rendelkezik a megvásárolható cikkekre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="45f13-116">A customer wants to buy a limited-edition product that has a maximum quantity limit for items that can be purchased.</span></span>

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a><span data-ttu-id="45f13-117">Az alapértelmezett rendelésbeállítások funkció bekapcsolása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="45f13-117">Turn on the default order settings feature in Commerce headquarters</span></span>

<span data-ttu-id="45f13-118">A termékmennyiség-korlátok beállítása előtt az alapértelmezett rendelésbeállítások funkciót be kell kapcsolni a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="45f13-118">Before you can set product quantity limits, the default order settings feature must be turned on in Commerce headquarters.</span></span>

<span data-ttu-id="45f13-119">Hajtsa végre az alábbi lépéseket az alapértelmezett rendelésbeállítások bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="45f13-119">To turn on the default order settings feature, follow these steps.</span></span>

1. <span data-ttu-id="45f13-120">Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.</span><span class="sxs-lookup"><span data-stu-id="45f13-120">Go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="45f13-121">Keresse meg és válassza ki a **Webhely és az Alapértelmezett rendelésbeállítások támogatása a vevői rendelésben** funkciót.</span><span class="sxs-lookup"><span data-stu-id="45f13-121">Find and select the **Support the Site and Default order settings in the customer order** feature.</span></span>
1. <span data-ttu-id="45f13-122">A jobb oldali ablaktábla alján válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f13-122">At the bottom of the right pane, select **Enable now**.</span></span> 

## <a name="define-quantity-settings"></a><span data-ttu-id="45f13-123">Mennyiségi beállítások meghatározása</span><span class="sxs-lookup"><span data-stu-id="45f13-123">Define quantity settings</span></span> 

<span data-ttu-id="45f13-124">A mennyiségi beállításokat az **Alapértelmezett rendelésbeállítások** oldalon lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="45f13-124">You can define the quantity settings on the **Default order settings** page.</span></span>

<span data-ttu-id="45f13-125">A mennyiségi beállítások meghatározásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="45f13-125">To define the quantity settings, follow these steps.</span></span> 

1. <span data-ttu-id="45f13-126">Nyissa meg a következőt a Termék menüben: **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Felszabadított termékek kategóriák szerint**.</span><span class="sxs-lookup"><span data-stu-id="45f13-126">Go to Product **Retail and Commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="45f13-127">Válasszon ki egy kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="45f13-127">Select a released product.</span></span>
1. <span data-ttu-id="45f13-128">A Művelet ablaktáblán a **Készlet kezelése** lapon a **Rendelés beállításai** csoportban válassza az **Alapértelmezett rendelési beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f13-128">On the Action Pane, on the **Manage inventory** tab, in the **Order settings** group, select **Default order settings**.</span></span> 
1. <span data-ttu-id="45f13-129">Az **Alapértelmezett rendelésbeállítások** oldal **Értékesítési rendelés** gyorslapjának **Értékesítési mennyiség** pontjában állítsa be a termék értékesítési mennyiségeit:</span><span class="sxs-lookup"><span data-stu-id="45f13-129">On the **Default order settings** page, on the **Sales order** FastTab, in the **Sales quantity** section, set the product sales quantities:</span></span>

    - <span data-ttu-id="45f13-130">**Többszörös** – az a mennyiség, amellyel a termék többszörsen megvásárolható.</span><span class="sxs-lookup"><span data-stu-id="45f13-130">**Multiple** – The quantity that the product can be bought in multiples of.</span></span>
    - <span data-ttu-id="45f13-131">**Minimális rendelési mennyiség** – a bevásárláshoz minimálisan szükséges termékek száma.</span><span class="sxs-lookup"><span data-stu-id="45f13-131">**Minimum Order Quantity** – The minimum number of products that must be purchased.</span></span>
    - <span data-ttu-id="45f13-132">**Maximális rendelési mennyiség** – a bevásárláshoz maximálisan engedélyezett termékek száma.</span><span class="sxs-lookup"><span data-stu-id="45f13-132">**Maximum Order Quantity** – The maximum number of products that can be purchased.</span></span>
    - <span data-ttu-id="45f13-133">**Szokásos rendelési mennyiség** – a termék kiválasztásakor automatikusan megadott alapértelmezett mennyiség.</span><span class="sxs-lookup"><span data-stu-id="45f13-133">**Standard Order Quantity** – The default quantity that is automatically entered when the product is selected.</span></span>

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a><span data-ttu-id="45f13-134">Kapcsolja be a B2B rendelési mennyiségi korlátok funkciót a Commerce webhelykészítőben</span><span class="sxs-lookup"><span data-stu-id="45f13-134">Turn on the B2B order quantity limits feature in Commerce site builder</span></span>

<span data-ttu-id="45f13-135">A B2B rendelési mennyiségi korlátok funkció Commerce webhelykészítőben való bekapcsolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="45f13-135">To turn on the B2B order quantity limits feature in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="45f13-136">Lépjen a **Webhelybeállítások \> Bővítmények** pontra</span><span class="sxs-lookup"><span data-stu-id="45f13-136">Go to **Site settings \> Extensions**</span></span>
1. <span data-ttu-id="45f13-137">A **Rendelési mennyiségi korlátok engedélyezése** pontban a legördülő menüben válassza az **Engedélyezve B2B-vevők esetében** beállítást.</span><span class="sxs-lookup"><span data-stu-id="45f13-137">Under **Enable Order Quantity Limits**, select **Enabled for B2B customers** in the drop-down menu.</span></span> 

> [!NOTE] 
> <span data-ttu-id="45f13-138">A frissített webhelykészítői beállítások csak az app.settings.json fájl frissítése után lépnek hatályba.</span><span class="sxs-lookup"><span data-stu-id="45f13-138">Updated site builder settings take effect only after the app.settings.json file has been updated.</span></span> <span data-ttu-id="45f13-139">A további tudnivalókat lásd itt: [SDK- és modultár-frissítések](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="45f13-139">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45f13-140">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="45f13-140">Additional resources</span></span>

[<span data-ttu-id="45f13-141">B2B e-kereskedelmi webhely beállítása</span><span class="sxs-lookup"><span data-stu-id="45f13-141">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="45f13-142">Szervezeti modellezési hierarchiák létrehozása B2B szervezetek számára</span><span class="sxs-lookup"><span data-stu-id="45f13-142">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="45f13-143">Üzleti partner típusú felhasználók kezelése a B2B e-kereskedelmi webhelyeken</span><span class="sxs-lookup"><span data-stu-id="45f13-143">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="45f13-144">A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása</span><span class="sxs-lookup"><span data-stu-id="45f13-144">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)
