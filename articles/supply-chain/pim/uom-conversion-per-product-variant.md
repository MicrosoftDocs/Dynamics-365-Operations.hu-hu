---
title: Mértékegység-átváltás termékváltozatonként
description: Ez a témakör bemutatja, hogyan lehet mértékegység-átváltásokat beállítani a termékváltozatokon.
author: johanhoffmann
manager: AnnBe
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 196b68db02867f8d864be8bcc593aa01f554f7c3
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249448"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="02f7b-103">Mértékegység-átváltás termékváltozatonként</span><span class="sxs-lookup"><span data-stu-id="02f7b-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

[!include [pivate-preview](../includes/pivate-preview-banner.md)]

<span data-ttu-id="02f7b-104">Ez a témakör bemutatja, hogyan lehet mértékegység-átváltásokat beállítani a termékváltozatokon.</span><span class="sxs-lookup"><span data-stu-id="02f7b-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="02f7b-105">Egy példát is tartalmaz a beállításra.</span><span class="sxs-lookup"><span data-stu-id="02f7b-105">It includes an example of the setup.</span></span>

<span data-ttu-id="02f7b-106">Ez a funkció lehetővé teszi a vállalatoknak, hogy különböző egységátváltásokat határozzanak meg ugyanazon termék változataira.</span><span class="sxs-lookup"><span data-stu-id="02f7b-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="02f7b-107">Ez a témakör a következő példát használja.</span><span class="sxs-lookup"><span data-stu-id="02f7b-107">The following example is used in this topic.</span></span> <span data-ttu-id="02f7b-108">Egy vállalat pólókat értékesít kicsi, közepes, nagy és extra nagy méretben.</span><span class="sxs-lookup"><span data-stu-id="02f7b-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="02f7b-109">A pólót termékként határozzuk meg, a különböző méreteket pedig a termék változataiként definiáljuk.</span><span class="sxs-lookup"><span data-stu-id="02f7b-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="02f7b-110">A pólókat dobozokba szortírozzák, egy dobozba öt póló kerül, kivéve az extra nagy méretet, mert itt csak négy pólóknak van hely egy dobozban.</span><span class="sxs-lookup"><span data-stu-id="02f7b-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="02f7b-111">A vállalat nyomon szeretné követni a pólók különböző változatait a **Darab** egyégben, de a pólókat a **Doboz** egységben forgalmazza.</span><span class="sxs-lookup"><span data-stu-id="02f7b-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="02f7b-112">A készletegység és az értékesítési egység közötti átváltás 1 doboz = 5 darab, kivéve a nagyméretű változatnál, ahol az átváltás 1 doboz = 4 darab.</span><span class="sxs-lookup"><span data-stu-id="02f7b-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

## <a name="setup"></a><span data-ttu-id="02f7b-113">Beállítás</span><span class="sxs-lookup"><span data-stu-id="02f7b-113">Setup</span></span>

<span data-ttu-id="02f7b-114">A paramétereket beállíthatja úgy, hogy a funkció az olyan termékek esetében legyen használatban, amelyek engedélyezve vannak **Minden folyamat** számára, vagy csak az olyan terméknél, amely a **Raktárkezelési folyamatok** számára engedélyezett, a következő beállítással: **Mértékegység-átváltások engedélyezése** beállítás a **Termékinformáció paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="02f7b-114">You can configure the parameters for using the feature for products enabled for **All processes** or only for product enabled for the **Warehouse processes** by using the **Enable unit of measure conversations** option on the **Product information parameters** page.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="02f7b-115">A termék beállítása egységátváltáshoz változat szerint</span><span class="sxs-lookup"><span data-stu-id="02f7b-115">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="02f7b-116">Termékváltozatokat csak az ilyen termékekhez lehet létrehozni **Termékaltípus**: **Alaptermék**.</span><span class="sxs-lookup"><span data-stu-id="02f7b-116">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="02f7b-117">További információ: [Alaptermék létrehozása](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="02f7b-117">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="02f7b-118">A funkció nincs engedélyezve a Tényleges súly folyamatokhoz beállított termékekhez.</span><span class="sxs-lookup"><span data-stu-id="02f7b-118">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="02f7b-119">Az alaptermék létrehozása során a **Mértékegység-átváltások engedélyezése** beállítással a **Termékadatok** lapon lehet engedélyezni a mértékegység-átváltást.</span><span class="sxs-lookup"><span data-stu-id="02f7b-119">During the creation of a product master enable unit of measure conversion by using the **Enable unit of measure conversions** option on the **Product details** page.</span></span>

<span data-ttu-id="02f7b-120">A kiadott termékváltozatokkal rendelkező alaptermék létrehozásakor be lehet állítani a változatok szerinti egységátváltásokat.</span><span class="sxs-lookup"><span data-stu-id="02f7b-120">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="02f7b-121">Az egységátváltási lap megnyitására szolgáló menüelemet egy termék vagy termékváltozat kontextusában a következő lapokon találhatja meg.</span><span class="sxs-lookup"><span data-stu-id="02f7b-121">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="02f7b-122">**Termékadatok** lap</span><span class="sxs-lookup"><span data-stu-id="02f7b-122">**Product details** page</span></span>
-   <span data-ttu-id="02f7b-123">**Kiadott termékek részletei** lap</span><span class="sxs-lookup"><span data-stu-id="02f7b-123">**Released products details** page</span></span>
-   <span data-ttu-id="02f7b-124">**Kiadott termékváltozatok** lap</span><span class="sxs-lookup"><span data-stu-id="02f7b-124">**Released product variants** page</span></span>

<span data-ttu-id="02f7b-125">Amikor megnyitja a **Mértékegység-átváltás** lapot egy alaptermék vagy egy kiadott termékváltozat kontextusában, választhat, hogy a mértékegység-átváltást a termék vagy a termékváltozat vonatkozásában szeretné-e beállítani.</span><span class="sxs-lookup"><span data-stu-id="02f7b-125">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="02f7b-126">A választást a **Termékváltozat** vagy a **Termék** kiválasztásával teheti meg a **Átváltás létrehozása a következőhöz:** mezőben.</span><span class="sxs-lookup"><span data-stu-id="02f7b-126">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="02f7b-127">Termékváltozat</span><span class="sxs-lookup"><span data-stu-id="02f7b-127">Product variant</span></span>

<span data-ttu-id="02f7b-128">Ha a **Termékváltozat** lehetőséget választja, akkor a **Termékváltozat** mezőben jelölje be, hogy melyik változathoz szeretné beállítani az egységátváltást.</span><span class="sxs-lookup"><span data-stu-id="02f7b-128">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="02f7b-129">Termék</span><span class="sxs-lookup"><span data-stu-id="02f7b-129">Product</span></span>

<span data-ttu-id="02f7b-130">Ha bejelöli a **Termék** lehetőséget, akkor beállíthatja a mértékegység-átváltást az alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="02f7b-130">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="02f7b-131">A mértékegység-átváltás érvényes lesz minden nem definiált mértékegység-átváltással rendelkező termékváltozat esetében.</span><span class="sxs-lookup"><span data-stu-id="02f7b-131">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="02f7b-132">Példa</span><span class="sxs-lookup"><span data-stu-id="02f7b-132">Example</span></span>

<span data-ttu-id="02f7b-133">A **Póló** alapterméknek négy kiadott termékváltozata van: kicsi, közepes, nagy és extra nagy.</span><span class="sxs-lookup"><span data-stu-id="02f7b-133">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="02f7b-134">A pólókat dobozokba szortírozzák, egy dobozba öt póló kerül, kivéve az extra nagy méretet, mert itt csak négy pólóknak van hely egy dobozban.</span><span class="sxs-lookup"><span data-stu-id="02f7b-134">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="02f7b-135">Először nyissa meg a **Mértékegység-átváltás** lapot a **Póló** Termékkiadás részletei lapjáról.</span><span class="sxs-lookup"><span data-stu-id="02f7b-135">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="02f7b-136">A **Mértékegység-átváltás** lapon állítsa be a mértékegység-átváltást a kiadási extra nagy termékváltozatnál.</span><span class="sxs-lookup"><span data-stu-id="02f7b-136">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="02f7b-137">**Mező**</span><span class="sxs-lookup"><span data-stu-id="02f7b-137">**Field**</span></span>             | <span data-ttu-id="02f7b-138">**Beállítás**</span><span class="sxs-lookup"><span data-stu-id="02f7b-138">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="02f7b-139">Átváltás létrehozása a következőhöz:</span><span class="sxs-lookup"><span data-stu-id="02f7b-139">Create conversion for</span></span> | <span data-ttu-id="02f7b-140">Termékváltozat</span><span class="sxs-lookup"><span data-stu-id="02f7b-140">Product variant</span></span>         |
| <span data-ttu-id="02f7b-141">Termékváltozat</span><span class="sxs-lookup"><span data-stu-id="02f7b-141">Product variant</span></span>       | <span data-ttu-id="02f7b-142">Póló : : Extra nagy : :</span><span class="sxs-lookup"><span data-stu-id="02f7b-142">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="02f7b-143">Kezdő egység</span><span class="sxs-lookup"><span data-stu-id="02f7b-143">From unit</span></span>             | <span data-ttu-id="02f7b-144">Dobozok</span><span class="sxs-lookup"><span data-stu-id="02f7b-144">Boxes</span></span>                   |
| <span data-ttu-id="02f7b-145">Szorzó</span><span class="sxs-lookup"><span data-stu-id="02f7b-145">Factor</span></span>                | <span data-ttu-id="02f7b-146">4</span><span class="sxs-lookup"><span data-stu-id="02f7b-146">4</span></span>                       |
| <span data-ttu-id="02f7b-147">Záró egység</span><span class="sxs-lookup"><span data-stu-id="02f7b-147">To Unit</span></span>               | <span data-ttu-id="02f7b-148">darab</span><span class="sxs-lookup"><span data-stu-id="02f7b-148">Pieces</span></span>                  |

<span data-ttu-id="02f7b-149">A kicsi, közepes és nagy kiadott termékváltozatok esetében azonos a mértékegység-átváltás a doboz és a darab egységek között, ami azt jelenti, hogy az alapterméken meg lehet adni a mértékegység-átváltást ezekhez a termékváltozatokhoz.</span><span class="sxs-lookup"><span data-stu-id="02f7b-149">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="02f7b-150">**Mező**</span><span class="sxs-lookup"><span data-stu-id="02f7b-150">**Field**</span></span>             | <span data-ttu-id="02f7b-151">**Beállítás**</span><span class="sxs-lookup"><span data-stu-id="02f7b-151">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="02f7b-152">Átváltás létrehozása a következőhöz:</span><span class="sxs-lookup"><span data-stu-id="02f7b-152">Create conversion for</span></span> | <span data-ttu-id="02f7b-153">Termék</span><span class="sxs-lookup"><span data-stu-id="02f7b-153">Product</span></span>     |
| <span data-ttu-id="02f7b-154">Termék</span><span class="sxs-lookup"><span data-stu-id="02f7b-154">Product</span></span>               | <span data-ttu-id="02f7b-155">Póló</span><span class="sxs-lookup"><span data-stu-id="02f7b-155">T-Shirt</span></span>     |
| <span data-ttu-id="02f7b-156">Kezdő egység</span><span class="sxs-lookup"><span data-stu-id="02f7b-156">From unit</span></span>             | <span data-ttu-id="02f7b-157">Dobozok</span><span class="sxs-lookup"><span data-stu-id="02f7b-157">Boxes</span></span>       |
| <span data-ttu-id="02f7b-158">Szorzó</span><span class="sxs-lookup"><span data-stu-id="02f7b-158">Factor</span></span>                | <span data-ttu-id="02f7b-159">5</span><span class="sxs-lookup"><span data-stu-id="02f7b-159">5</span></span>           |
| <span data-ttu-id="02f7b-160">Záró egység</span><span class="sxs-lookup"><span data-stu-id="02f7b-160">To Unit</span></span>               | <span data-ttu-id="02f7b-161">darab</span><span class="sxs-lookup"><span data-stu-id="02f7b-161">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="02f7b-162">A mértékegység-átváltások frissítése az Excel programmal</span><span class="sxs-lookup"><span data-stu-id="02f7b-162">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="02f7b-163">Ha egy termék sok, különböző mértékegység-átváltású termékváltozattal rendelkezik, célszerű exportálni a mértékegység-átváltásokat a **Mértékegység-átváltás** oldalról egy Excel-táblázatba, frissíteni az átváltásokat, és aztán ismét közzétenni őket a Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="02f7b-163">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Supply Chain Mangement.</span></span>

<span data-ttu-id="02f7b-164">Az exportálás az Excel programba, majd az ismételt közzététel a módosítás után a Supply Chain Management alkalmazásban itt engedélyezhető: **Megnyitás a Microsoft Office-ban** menüelem a műveletpanelen a **Mértékegység-átváltás** lapon.</span><span class="sxs-lookup"><span data-stu-id="02f7b-164">The option to export to Excel and publish the edits back to Supply Chain Mangement is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
