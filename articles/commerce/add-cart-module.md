---
title: Kosármodul
description: Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 598b35b1bd365e761d8d4c5ef214935e60b971f4
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154017"
---
# <a name="cart-module"></a><span data-ttu-id="c4a89-103">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="c4a89-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c4a89-104">Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c4a89-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c4a89-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="c4a89-105">Overview</span></span>

<span data-ttu-id="c4a89-106">A kosármodullal megjeleníthetők a kosárba tett cikkek, mielőtt az ügyfél a pénztárra lép.</span><span class="sxs-lookup"><span data-stu-id="c4a89-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="c4a89-107">A modul a rendelés összegzését is megjeleníti, és lehetővé teszi, hogy a vevő hozzáadja vagy eltávolítsa a promóciós kódokat.</span><span class="sxs-lookup"><span data-stu-id="c4a89-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="c4a89-108">A kosár modul támogatja a bejelentkezett fizetést és a vendégfizetést.</span><span class="sxs-lookup"><span data-stu-id="c4a89-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="c4a89-109">Támogatja a **Vissza a vásárláshoz** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="c4a89-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="c4a89-110">A hivatkozáshoz vezető útvonalat a **Webhely-beállítások \> Bővítmények \> Útvonala** oldalon.</span><span class="sxs-lookup"><span data-stu-id="c4a89-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="c4a89-111">A kosár modul a kosár azonosítója alapján jeleníti meg az adatokat, ami a webhely teljes területén elérhető böngésző cookie.</span><span class="sxs-lookup"><span data-stu-id="c4a89-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="c4a89-112">A kosármodul tulajdonságai és helyei</span><span class="sxs-lookup"><span data-stu-id="c4a89-112">Cart module properties and slots</span></span>

<span data-ttu-id="c4a89-113">A kosár modulnak van egy **Címsor** tulajdonsága, amelyet olyan értékekre állíthat, mint **Bevásárlótáska** vagy **Kosárban levő cikkek**.</span><span class="sxs-lookup"><span data-stu-id="c4a89-113">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="c4a89-114">A kosármodulban használható modulok</span><span class="sxs-lookup"><span data-stu-id="c4a89-114">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="c4a89-115">**Szövegblokk** – Ez a modul a kosár modulban használható egyéni üzenetküldést támogatja.</span><span class="sxs-lookup"><span data-stu-id="c4a89-115">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="c4a89-116">Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli.</span><span class="sxs-lookup"><span data-stu-id="c4a89-116">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="c4a89-117">Bármilyen üzenet megadható, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”.</span><span class="sxs-lookup"><span data-stu-id="c4a89-117">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="c4a89-118">**Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők.</span><span class="sxs-lookup"><span data-stu-id="c4a89-118">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="c4a89-119">Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják.</span><span class="sxs-lookup"><span data-stu-id="c4a89-119">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="c4a89-120">A modullal kapcsolatos további tudnivalókat lásd: [Üzletkiválasztó modul](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="c4a89-120">For more information on this module, see [Store Selector module](store-selector.md).</span></span>

## <a name="cart-module-settings"></a><span data-ttu-id="c4a89-121">Kosármodul beállításai</span><span class="sxs-lookup"><span data-stu-id="c4a89-121">Cart module settings</span></span>

<span data-ttu-id="c4a89-122">A kosár-modulok beállításai a **Webhelybeállítások \> Bővítmények** pontban konfigurálhatók:</span><span class="sxs-lookup"><span data-stu-id="c4a89-122">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="c4a89-123">**Maximális mennyiség** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát.</span><span class="sxs-lookup"><span data-stu-id="c4a89-123">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="c4a89-124">Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.</span><span class="sxs-lookup"><span data-stu-id="c4a89-124">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="c4a89-125">**Készletellenőrzés** – Ha **Igaz** értékre van beállítva, akkor a program a kosárba csak azután veszi fel a cikket, hogy a vásárlásmező modul meggyőződött róla, hogy az adott termék készleten van.</span><span class="sxs-lookup"><span data-stu-id="c4a89-125">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="c4a89-126">Ez a készletellenőrzés végrehajtásra kerül azokban az esetekben, amikor a cikk kiszállításra kerül, mind azokban az esetekben, amikor a vevő az áruházban veszi fel.</span><span class="sxs-lookup"><span data-stu-id="c4a89-126">This inventory check is done for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="c4a89-127">Ha **Hamis** értékre van állítva, akkor a program nem végez készletellenőrzést, mielőtt a cikkeket felveszi a kosárba, és a rendelés leadásra kerül.</span><span class="sxs-lookup"><span data-stu-id="c4a89-127">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="c4a89-128">**Készletpuffer** – ez a tulajdonság a készlethez tartozó pufferméret meghatározására szolgál.</span><span class="sxs-lookup"><span data-stu-id="c4a89-128">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="c4a89-129">A készlet leltározása valós időben történik, és sok vevői rendelés esetén nehéz a készlet pontos leltározása.</span><span class="sxs-lookup"><span data-stu-id="c4a89-129">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="c4a89-130">A készletellenőrzés során, ha a készlet kisebb, mint a puffermennyiség, akkor a rendszer a terméket kifogyottként kezeli.</span><span class="sxs-lookup"><span data-stu-id="c4a89-130">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="c4a89-131">Ezért ha az értékesítések gyorsabban történnek több csatornán keresztül, és a leltározás nem teljes mértékben szinkronizált, akkor kisebb a kockázata annak, hogy a kifogyott cikkek eladásra kerülnek.</span><span class="sxs-lookup"><span data-stu-id="c4a89-131">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="c4a89-132">**Vissza a vásárláshoz** – a tulajdonság a **Vissza a vásárláshoz** linkhez megadott útvonal meghatározására szolgál.</span><span class="sxs-lookup"><span data-stu-id="c4a89-132">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="c4a89-133">Az útvonal a webhely szintjén konfigurálható, amely lehetővé teszi, hogy a kiskereskedők visszavigyék a vevőt a kezdőlapra vagy más lapjára.</span><span class="sxs-lookup"><span data-stu-id="c4a89-133">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="c4a89-134">Commerce Scale Unit-interakció</span><span class="sxs-lookup"><span data-stu-id="c4a89-134">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="c4a89-135">A kosármodul a termék adatait a Commerce Scale Unit API-k használatával olvassa be.</span><span class="sxs-lookup"><span data-stu-id="c4a89-135">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="c4a89-136">A böngésző cookie-jából származó kosárazonosító szolgál az összes termékadat beolvasására a Commerce Scale Unitról.</span><span class="sxs-lookup"><span data-stu-id="c4a89-136">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="c4a89-137">Kosármodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="c4a89-137">Add a cart module to a page</span></span>

<span data-ttu-id="c4a89-138">A kosármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c4a89-138">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="c4a89-139">Hozzon létre egy **Kosártöredék** nevű töredéket, majd adjon hozzá egy új töredéket.</span><span class="sxs-lookup"><span data-stu-id="c4a89-139">Create a fragment named **Cart fragment**, and add a cart module to the new fragment.</span></span>
1. <span data-ttu-id="c4a89-140">Adjon hozzá egy fejlécet a kosármodulhoz.</span><span class="sxs-lookup"><span data-stu-id="c4a89-140">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="c4a89-141">Adjon hozzá egy üzletválasztó modult a kosár modulhoz.</span><span class="sxs-lookup"><span data-stu-id="c4a89-141">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="c4a89-142">Mentse a töredéket, fejezze be a szerkesztését, majd tegye közzé a töredéket.</span><span class="sxs-lookup"><span data-stu-id="c4a89-142">Save the fragment, finish editing, and then publish the fragment.</span></span>
1. <span data-ttu-id="c4a89-143">Hozzon létre egy **Kosársablon** nevű sablont, és adja hozzá a most létrehozott kosártöredéket.</span><span class="sxs-lookup"><span data-stu-id="c4a89-143">Create a template named **Cart template**, and add the cart fragment that you just created.</span></span>
1. <span data-ttu-id="c4a89-144">Mentse a sablont, fejezze be a szerkesztését, majd tegye közzé a sablont.</span><span class="sxs-lookup"><span data-stu-id="c4a89-144">Save the template, finish editing, and then publish the template.</span></span>
1. <span data-ttu-id="c4a89-145">Hozzon létre egy olyan oldalt, amely az új sablont használja.</span><span class="sxs-lookup"><span data-stu-id="c4a89-145">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="c4a89-146">Mentse a lapot, és tekintse meg az előnézetét.</span><span class="sxs-lookup"><span data-stu-id="c4a89-146">Save and preview the page.</span></span>
1. <span data-ttu-id="c4a89-147">Fejezze be az oldal szerkesztését, majd tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="c4a89-147">Finish editing the page, and then publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c4a89-148">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c4a89-148">Additional resources</span></span>

[<span data-ttu-id="c4a89-149">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="c4a89-149">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c4a89-150">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="c4a89-150">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="c4a89-151">Üzletkiválasztó modul</span><span class="sxs-lookup"><span data-stu-id="c4a89-151">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="c4a89-152">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="c4a89-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="c4a89-153">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="c4a89-153">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c4a89-154">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="c4a89-154">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="c4a89-155">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="c4a89-155">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="c4a89-156">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="c4a89-156">Footer module</span></span>](author-footer-module.md)
