---
title: Mértékegység-átváltás termékváltozatonként
description: Ez a témakör bemutatja, hogyan lehet mértékegység-átváltásokat beállítani a termékváltozatokon.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: e50be7fa6fa686a90b2dd5c5200c881e4629f019
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204493"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="066c5-103">Mértékegység-átváltás termékváltozatonként</span><span class="sxs-lookup"><span data-stu-id="066c5-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="066c5-104">Ez a témakör bemutatja, hogyan lehet mértékegység-átváltásokat beállítani a termékváltozatokon.</span><span class="sxs-lookup"><span data-stu-id="066c5-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="066c5-105">Egy példát is tartalmaz a beállításra.</span><span class="sxs-lookup"><span data-stu-id="066c5-105">It includes an example of the setup.</span></span>

<span data-ttu-id="066c5-106">Ez a funkció lehetővé teszi a vállalatoknak, hogy különböző egységátváltásokat határozzanak meg ugyanazon termék változataira.</span><span class="sxs-lookup"><span data-stu-id="066c5-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="066c5-107">Ez a témakör a következő példát használja.</span><span class="sxs-lookup"><span data-stu-id="066c5-107">The following example is used in this topic.</span></span> <span data-ttu-id="066c5-108">Egy vállalat pólókat értékesít kicsi, közepes, nagy és extra nagy méretben.</span><span class="sxs-lookup"><span data-stu-id="066c5-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="066c5-109">A pólót termékként határozzuk meg, a különböző méreteket pedig a termék változataiként definiáljuk.</span><span class="sxs-lookup"><span data-stu-id="066c5-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="066c5-110">A pólókat dobozokba szortírozzák, egy dobozba öt póló kerül, kivéve az extra nagy méretet, mert itt csak négy pólóknak van hely egy dobozban.</span><span class="sxs-lookup"><span data-stu-id="066c5-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="066c5-111">A vállalat nyomon szeretné követni a pólók különböző változatait a **Darab** egyégben, de a pólókat a **Doboz** egységben forgalmazza.</span><span class="sxs-lookup"><span data-stu-id="066c5-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="066c5-112">A készletegység és az értékesítési egység közötti átváltás 1 doboz = 5 darab, kivéve a nagyméretű változatnál, ahol az átváltás 1 doboz = 4 darab.</span><span class="sxs-lookup"><span data-stu-id="066c5-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="066c5-113">A termék beállítása egységátváltáshoz változat szerint</span><span class="sxs-lookup"><span data-stu-id="066c5-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="066c5-114">Termékváltozatokat csak az ilyen termékekhez lehet létrehozni **Termékaltípus**: **Alaptermék**.</span><span class="sxs-lookup"><span data-stu-id="066c5-114">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="066c5-115">További információ: [Alaptermék létrehozása](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="066c5-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="066c5-116">A funkció nincs engedélyezve a Tényleges súly folyamatokhoz beállított termékekhez.</span><span class="sxs-lookup"><span data-stu-id="066c5-116">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="066c5-117">A kiadott termékváltozatokkal rendelkező alaptermék létrehozásakor be lehet állítani a változatok szerinti egységátváltásokat.</span><span class="sxs-lookup"><span data-stu-id="066c5-117">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="066c5-118">Az egységátváltási lap megnyitására szolgáló menüelemet egy termék vagy termékváltozat kontextusában a következő lapokon találhatja meg.</span><span class="sxs-lookup"><span data-stu-id="066c5-118">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="066c5-119">**Termékadatok** lap</span><span class="sxs-lookup"><span data-stu-id="066c5-119">**Product details** page</span></span>
-   <span data-ttu-id="066c5-120">**Kiadott termékek részletei** lap</span><span class="sxs-lookup"><span data-stu-id="066c5-120">**Released products details** page</span></span>
-   <span data-ttu-id="066c5-121">**Kiadott termékváltozatok** lap</span><span class="sxs-lookup"><span data-stu-id="066c5-121">**Released product variants** page</span></span>

<span data-ttu-id="066c5-122">Amikor megnyitja a **Mértékegység-átváltás** lapot egy alaptermék vagy egy kiadott termékváltozat kontextusában, választhat, hogy a mértékegység-átváltást a termék vagy a termékváltozat vonatkozásában szeretné-e beállítani.</span><span class="sxs-lookup"><span data-stu-id="066c5-122">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="066c5-123">A választást a **Termékváltozat** vagy a **Termék** kiválasztásával teheti meg a **Átváltás létrehozása a következőhöz:** mezőben.</span><span class="sxs-lookup"><span data-stu-id="066c5-123">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="066c5-124">Termékváltozat</span><span class="sxs-lookup"><span data-stu-id="066c5-124">Product variant</span></span>

<span data-ttu-id="066c5-125">Ha a **Termékváltozat** lehetőséget választja, akkor a **Termékváltozat** mezőben jelölje be, hogy melyik változathoz szeretné beállítani az egységátváltást.</span><span class="sxs-lookup"><span data-stu-id="066c5-125">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="066c5-126">Termék</span><span class="sxs-lookup"><span data-stu-id="066c5-126">Product</span></span>

<span data-ttu-id="066c5-127">Ha bejelöli a **Termék** lehetőséget, akkor beállíthatja a mértékegység-átváltást az alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="066c5-127">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="066c5-128">A mértékegység-átváltás érvényes lesz minden nem definiált mértékegység-átváltással rendelkező termékváltozat esetében.</span><span class="sxs-lookup"><span data-stu-id="066c5-128">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="066c5-129">Példa</span><span class="sxs-lookup"><span data-stu-id="066c5-129">Example</span></span>

<span data-ttu-id="066c5-130">A **Póló** alapterméknek négy kiadott termékváltozata van: kicsi, közepes, nagy és extra nagy.</span><span class="sxs-lookup"><span data-stu-id="066c5-130">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="066c5-131">A pólókat dobozokba szortírozzák, egy dobozba öt póló kerül, kivéve az extra nagy méretet, mert itt csak négy pólóknak van hely egy dobozban.</span><span class="sxs-lookup"><span data-stu-id="066c5-131">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="066c5-132">Először nyissa meg a **Mértékegység-átváltás** lapot a **Póló** Termékkiadás részletei lapjáról.</span><span class="sxs-lookup"><span data-stu-id="066c5-132">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="066c5-133">A **Mértékegység-átváltás** lapon állítsa be a mértékegység-átváltást a kiadási extra nagy termékváltozatnál.</span><span class="sxs-lookup"><span data-stu-id="066c5-133">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="066c5-134">**Mező**</span><span class="sxs-lookup"><span data-stu-id="066c5-134">**Field**</span></span>             | <span data-ttu-id="066c5-135">**Beállítás**</span><span class="sxs-lookup"><span data-stu-id="066c5-135">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="066c5-136">Átváltás létrehozása a következőhöz:</span><span class="sxs-lookup"><span data-stu-id="066c5-136">Create conversion for</span></span> | <span data-ttu-id="066c5-137">Termékváltozat</span><span class="sxs-lookup"><span data-stu-id="066c5-137">Product variant</span></span>         |
| <span data-ttu-id="066c5-138">Termékváltozat</span><span class="sxs-lookup"><span data-stu-id="066c5-138">Product variant</span></span>       | <span data-ttu-id="066c5-139">Póló : : Extra nagy : :</span><span class="sxs-lookup"><span data-stu-id="066c5-139">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="066c5-140">Kezdő egység</span><span class="sxs-lookup"><span data-stu-id="066c5-140">From unit</span></span>             | <span data-ttu-id="066c5-141">Dobozok</span><span class="sxs-lookup"><span data-stu-id="066c5-141">Boxes</span></span>                   |
| <span data-ttu-id="066c5-142">Szorzó</span><span class="sxs-lookup"><span data-stu-id="066c5-142">Factor</span></span>                | <span data-ttu-id="066c5-143">4</span><span class="sxs-lookup"><span data-stu-id="066c5-143">4</span></span>                       |
| <span data-ttu-id="066c5-144">Záró egység</span><span class="sxs-lookup"><span data-stu-id="066c5-144">To Unit</span></span>               | <span data-ttu-id="066c5-145">darab</span><span class="sxs-lookup"><span data-stu-id="066c5-145">Pieces</span></span>                  |

<span data-ttu-id="066c5-146">A kicsi, közepes és nagy kiadott termékváltozatok esetében azonos a mértékegység-átváltás a doboz és a darab egységek között, ami azt jelenti, hogy az alapterméken meg lehet adni a mértékegység-átváltást ezekhez a termékváltozatokhoz.</span><span class="sxs-lookup"><span data-stu-id="066c5-146">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="066c5-147">**Mező**</span><span class="sxs-lookup"><span data-stu-id="066c5-147">**Field**</span></span>             | <span data-ttu-id="066c5-148">**Beállítás**</span><span class="sxs-lookup"><span data-stu-id="066c5-148">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="066c5-149">Átváltás létrehozása a következőhöz:</span><span class="sxs-lookup"><span data-stu-id="066c5-149">Create conversion for</span></span> | <span data-ttu-id="066c5-150">Termék</span><span class="sxs-lookup"><span data-stu-id="066c5-150">Product</span></span>     |
| <span data-ttu-id="066c5-151">Termék</span><span class="sxs-lookup"><span data-stu-id="066c5-151">Product</span></span>               | <span data-ttu-id="066c5-152">Póló</span><span class="sxs-lookup"><span data-stu-id="066c5-152">T-Shirt</span></span>     |
| <span data-ttu-id="066c5-153">Kezdő egység</span><span class="sxs-lookup"><span data-stu-id="066c5-153">From unit</span></span>             | <span data-ttu-id="066c5-154">Dobozok</span><span class="sxs-lookup"><span data-stu-id="066c5-154">Boxes</span></span>       |
| <span data-ttu-id="066c5-155">Szorzó</span><span class="sxs-lookup"><span data-stu-id="066c5-155">Factor</span></span>                | <span data-ttu-id="066c5-156">5</span><span class="sxs-lookup"><span data-stu-id="066c5-156">5</span></span>           |
| <span data-ttu-id="066c5-157">Záró egység</span><span class="sxs-lookup"><span data-stu-id="066c5-157">To Unit</span></span>               | <span data-ttu-id="066c5-158">darab</span><span class="sxs-lookup"><span data-stu-id="066c5-158">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="066c5-159">A mértékegység-átváltások frissítése az Excel programmal</span><span class="sxs-lookup"><span data-stu-id="066c5-159">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="066c5-160">Ha egy termék sok, különböző mértékegység-átváltású termékváltozattal rendelkezik, célszerű exportálni a mértékegység-átváltásokat a **Mértékegység-átváltás** oldalról egy Excel-táblázatba, frissíteni az átváltásokat, és aztán ismét közzétenni őket a Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="066c5-160">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Supply Chain Mangement.</span></span>

<span data-ttu-id="066c5-161">Az exportálás az Excel programba, majd az ismételt közzététel a módosítás után a Supply Chain Management alkalmazásban itt engedélyezhető: **Megnyitás a Microsoft Office-ban** menüelem a műveletpanelen a **Mértékegység-átváltás** lapon.</span><span class="sxs-lookup"><span data-stu-id="066c5-161">The option to export to Excel and publish the edits back to Supply Chain Mangement is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
