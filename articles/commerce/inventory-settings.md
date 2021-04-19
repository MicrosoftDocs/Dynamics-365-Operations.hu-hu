---
title: Készlet beállításainak alkalmazása
description: Ez a témakör a készlet beállításaival foglalkozik, és leírja, hogy hogyan kell alkalmazni azokat a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b2c44eb5ece74de15e22180abc6d9d0448ab401b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798889"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="337d1-103">Készletbeállítások alkalmazása</span><span class="sxs-lookup"><span data-stu-id="337d1-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="337d1-104">Ez a témakör a készlet beállításaival foglalkozik, és leírja, hogy hogyan kell alkalmazni azokat a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="337d1-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="337d1-105">A készlet beállításai határozzák meg, hogy ellenőrizni kell-e a készletet, mielőtt termékek kerülnek a kosárba.</span><span class="sxs-lookup"><span data-stu-id="337d1-105">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="337d1-106">Meghatározzák a készlettel kapcsolatos értékesítési üzeneteket is, például a "Készleten" és a "Már csak néhány maradt".</span><span class="sxs-lookup"><span data-stu-id="337d1-106">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="337d1-107">Ez a beállítás gondoskodik arról, hogy a termék nem vásárolható meg, ha elfogyott.</span><span class="sxs-lookup"><span data-stu-id="337d1-107">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="337d1-108">A Dynamics 365 Commerce becsléseket biztosít a termékek aktuális rendelkezésre állásáról.</span><span class="sxs-lookup"><span data-stu-id="337d1-108">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="337d1-109">A becsült aktuális elérhetőségek számításával kapcsolatos további tudnivalókat lásd: [Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="337d1-109">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="337d1-110">A Commerce webhelykészítőben egy termékhez vagy egy kategóriához lehet definiálni a készlet-küszöbértékeket és a -tartományokat.</span><span class="sxs-lookup"><span data-stu-id="337d1-110">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="337d1-111">Ezek határozzák meg, hogy a készlet minősíthető készleten, alacsony készlet vagy elfogyott értékkel.</span><span class="sxs-lookup"><span data-stu-id="337d1-111">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="337d1-112">További részletek: [A készletpufferek és a készlet szintjeinek konfigurálása](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="337d1-112">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="337d1-113">A Dynamics 365 Commerce 10.0.12-kiadásban elérhető a készletküszöbök és a -tartományok támogatása.</span><span class="sxs-lookup"><span data-stu-id="337d1-113">Support for inventory thresholds and ranges is available in the Dynamics 365 Commerce 10.0.12 release.</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="337d1-114">Készletbeállítások</span><span class="sxs-lookup"><span data-stu-id="337d1-114">Inventory settings</span></span>

<span data-ttu-id="337d1-115">A Commerce alkalmazásban a készletbeállítások a **Webhelybeállítások \> Bővítmények \> Készletkezelés** alatt adhatók meg a webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="337d1-115">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="337d1-116">Négy készletbeállítás van, amelyek közül az egyik elavult:</span><span class="sxs-lookup"><span data-stu-id="337d1-116">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="337d1-117">**Készletellenőrzés engedélyezése az alkalmazásban** – Ez a beállítás bekapcsolja a termékkészlet ellenőrzését.</span><span class="sxs-lookup"><span data-stu-id="337d1-117">**Enable stock check in app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="337d1-118">A vásárlás mező, a kosár és az átvétel az üzletben modul is ellenőrzi a termék készletét, és lehetővé teszi a terméknek a kosárba történő felvételét, ha a készlet elérhető.</span><span class="sxs-lookup"><span data-stu-id="337d1-118">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="337d1-119">**Készletszint alapja** – Ez a beállítás határozza meg a készletszint számításának módját.</span><span class="sxs-lookup"><span data-stu-id="337d1-119">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="337d1-120">A rendelkezésre álló értékek a **Teljes rendelkezésre álló**, a **Rendelkezésre álló tényleges** és az **Elfogyott küszöbérték**.</span><span class="sxs-lookup"><span data-stu-id="337d1-120">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="337d1-121">A Commerce webhelykészítőben minden termékhez ás kategóriához lehet definiálni a készletküszöbértéket és -tartományokat.</span><span class="sxs-lookup"><span data-stu-id="337d1-121">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="337d1-122">A készlet API-k termékkészlet-információkat adnak vissza mind a **Teljes rendelkezésre álló** tulajdonság, mind a **Rendelkezésre álló tényleges** tulajdonság esetében.</span><span class="sxs-lookup"><span data-stu-id="337d1-122">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="337d1-123">A kiskereskedő dönti el, hogy a **Teljes rendelkezésre álló** vagy a **Rendelkezésre álló tényleges** érték kerüljön felhasználásra a készletszám és a vonatkozó raktáron és elfogyott állapotok megállapításához.</span><span class="sxs-lookup"><span data-stu-id="337d1-123">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="337d1-124">A **Készletszint alapja** beállítás **Elfogyott küszöbérték** értéke egy régi (örökölt), elavult érték.</span><span class="sxs-lookup"><span data-stu-id="337d1-124">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="337d1-125">Ha ki van választva, akkor a leltározás a **Teljes rendelkezésre álló** érték eredményei alapján történik, de a küszöbértéket a későbbiekben meghatározott **Elfogyott küszöbérték** numerikus beállítása határozza meg.</span><span class="sxs-lookup"><span data-stu-id="337d1-125">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="337d1-126">Ez a küszöbérték-beállítás minden termékre vonatkozik az e-kereskedelmi webhelyen.</span><span class="sxs-lookup"><span data-stu-id="337d1-126">This threshold setting applies to all products across an e-commerce site.</span></span> <span data-ttu-id="337d1-127">Ha a készlet nem éri el a küszöbértéket, akkor a termék elfogyottnak minősül.</span><span class="sxs-lookup"><span data-stu-id="337d1-127">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="337d1-128">Ellenkező esetben raktáron levőnek kell tekinteni.</span><span class="sxs-lookup"><span data-stu-id="337d1-128">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="337d1-129">Az **Elfogyott küszöbérték** érték képességei korlátozottak, ezért a használata nem ajánlott a 10.0.12-es és későbbi verziókban.</span><span class="sxs-lookup"><span data-stu-id="337d1-129">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="337d1-130">**Készlettartományok** – Ez a beállítás határozza meg a készlettartományokat, amelyekhez üzenetek kerülnek megjelenítésre a helyi modulok esetében.</span><span class="sxs-lookup"><span data-stu-id="337d1-130">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="337d1-131">Csak akkor alkalmazható, ha a **Teljes rendelkezésre álló** érték vagy a **Rendelkezésre álló tényleges** érték van kiválasztva a **Készletszint alapja** számára.</span><span class="sxs-lookup"><span data-stu-id="337d1-131">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="337d1-132">A rendelkezésre álló értékek a **Mind**, az **Alacsony és elfogyott**, valamint az **Elfogyott**.</span><span class="sxs-lookup"><span data-stu-id="337d1-132">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="337d1-133">Ha a **Mind** van kiválasztva, akkor a program az összes készlettartomány esetében megjelenít üzeneteket a raktáron állapottól („Elérhető üzenet”) az elfogyott állapotig („Elfogyott” üzenet).</span><span class="sxs-lookup"><span data-stu-id="337d1-133">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="337d1-134">Ha az **Alacsony és elfogyott** van kiválasztva, akkor a program az összes készlettartomány esetében megjelenít üzeneteket a raktáron állapotot („Elérhető üzenet”) kivéve.</span><span class="sxs-lookup"><span data-stu-id="337d1-134">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="337d1-135">Ha az **Elfogyott** lehetőség van kiválasztva, akkor csak az „Elfogyott” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="337d1-135">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="337d1-136">**Elfogyott küszöbérték** – Ez a régi numerikus beállítás csak akkor lép érvénybe, ha az **Elfogyott küszöbérték** érték van kiválasztva a **Készletszint alapja** beállítás számára.</span><span class="sxs-lookup"><span data-stu-id="337d1-136">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="337d1-137">Ezek a beállítások a Dynamics 365 Commerce 10.0.12-es kiadásában érhetők el.</span><span class="sxs-lookup"><span data-stu-id="337d1-137">These settings are available in the Dynamics 365 Commerce 10.0.12 release.</span></span> <span data-ttu-id="337d1-138">Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt.</span><span class="sxs-lookup"><span data-stu-id="337d1-138">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="337d1-139">Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókat lásd az [SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakörben.</span><span class="sxs-lookup"><span data-stu-id="337d1-139">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="337d1-140">A készletbeállításokat használó modulok</span><span class="sxs-lookup"><span data-stu-id="337d1-140">Modules that use inventory settings</span></span>

<span data-ttu-id="337d1-141">A vásárlásmező, kívánságlista, üzletválasztó, kosár és kosárikon modulok készletbeállításokat használnak a készlettartományok és az üzenetek megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="337d1-141">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="337d1-142">A következő képen a termék részleteit tartalmazó oldal (PDP) egy példája látható, amely egy raktáron lévő ("elérhető") üzenetet jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="337d1-142">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Egy olyan PDP-modul példája, amely tartalmaz egy készleten üzenetet.](./media/pdp-InStock.png)

<span data-ttu-id="337d1-144">A következő képen a termék részleteit tartalmazó oldal (PDP) egy példája látható, amely egy „Elfogyott” üzenetet jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="337d1-144">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Egy olyan PDP-modul példája, amely tartalmaz egy elfogyott üzenetet.](./media/pdp-outofstock.png)

<span data-ttu-id="337d1-146">A következő képen a kosár egy példája látható, amely egy raktáron („Elérhető”) üzenetet jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="337d1-146">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Egy olyan kosármodul példája, amely tartalmaz egy készleten üzenetet.](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="337d1-148">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="337d1-148">Additional resources</span></span>

[<span data-ttu-id="337d1-149">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="337d1-149">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="337d1-150">Készletpufferek és készletszintek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="337d1-150">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="337d1-151">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="337d1-151">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="337d1-152">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="337d1-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="337d1-153">Számlakezelési oldalak és modulok</span><span class="sxs-lookup"><span data-stu-id="337d1-153">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="337d1-154">Üzletválasztó modul</span><span class="sxs-lookup"><span data-stu-id="337d1-154">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="337d1-155">SDK- és modulkönyvtár-frissítések</span><span class="sxs-lookup"><span data-stu-id="337d1-155">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
