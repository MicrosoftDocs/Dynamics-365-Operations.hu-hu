---
title: Eszköz DBJ-k
description: Ez a témakör az Eszközkezelésben használt eszközök darabjegyzékét mutatja be (DBJ-j)
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetStandardSparePartsItemGroup, EntAssetObjectBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e5d6d6245f27534d176ac03ca762aff91afb0ca
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253182"
---
# <a name="asset-boms"></a><span data-ttu-id="606fa-103">Eszköz DBJ-k</span><span class="sxs-lookup"><span data-stu-id="606fa-103">Asset BOMs</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="606fa-104">Ez a témakör az Eszközkezelésben használt eszközök darabjegyzékét mutatja be (DBJ-j)</span><span class="sxs-lookup"><span data-stu-id="606fa-104">This topic describes asset bills of materials (BOMs) in Asset Management.</span></span> <span data-ttu-id="606fa-105">Az **Eszköz DBJ** oldalon látható az eszköz által a teljes élettartama alatt használt összes cikk listája (pótalkatrészek és más cikkek egyaránt).</span><span class="sxs-lookup"><span data-stu-id="606fa-105">The **Asset BOM** page shows a list of all items (spare parts and other items) that are used on an asset during its whole lifetime.</span></span> <span data-ttu-id="606fa-106">Új eszköz létrehozásakor javasoljuk az eszköz DBJ létrehozását a beállítási eljárás részeként.</span><span class="sxs-lookup"><span data-stu-id="606fa-106">When you create a new asset, you should consider setting up an asset BOM as a part of the setup procedure.</span></span> <span data-ttu-id="606fa-107">Így nyomon követheti az eszköz cikkelőzményeit a létrehozás dátumától.</span><span class="sxs-lookup"><span data-stu-id="606fa-107">In this way, you can track item history for the asset from the creation date.</span></span>

<span data-ttu-id="606fa-108">Miután befejezett egy karbantartási feladatot, és a cikkfelhasználást rögzítik a munkarendelésen, nyomon követheti a pótalkatrészek és más cikkek felhasználását, amelyeket az eszközhöz használtak.</span><span class="sxs-lookup"><span data-stu-id="606fa-108">After you've completed a maintenance job, and item consumption has been registered on a work order, you can track consumption of spare parts and other items that are used on the asset.</span></span> <span data-ttu-id="606fa-109">Ez a funkció lehetővé teszi, hogy teljes cikkfelhasználási rekordot tartson nyilván az összes eszköz számára.</span><span class="sxs-lookup"><span data-stu-id="606fa-109">This functionality lets you keep a complete item consumption record for all your assets.</span></span> <span data-ttu-id="606fa-110">A rekorddal például megfigyelheti, hogy egy adott pótalkatrészt gyakran cserélnek-e, vagy nyomon követheti a pótalkatrészeket és más cikkeket, amelyeket jelenleg az eszközön használnak.</span><span class="sxs-lookup"><span data-stu-id="606fa-110">For example, you can use the record to monitor whether a specific spare part is often replaced, or to keep track of the spare parts or other items that are currently used on an asset.</span></span>

> [!NOTE]
> <span data-ttu-id="606fa-111">A munkarendelésen a cikkfelhasználásba beletartozhatnak a pótalkatrészek, és más kiegészítő cikkek, például kenőanyagok, csavarok és tömítések.</span><span class="sxs-lookup"><span data-stu-id="606fa-111">On a work order, item consumption might include both spare parts and other, additional items, such as lubricants, bolts, and gaskets.</span></span>

<span data-ttu-id="606fa-112">Az eszköz DBJ-t automatikusan frissíthető az Eszközkezelés beállításainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="606fa-112">An asset BOM can be automatically updated based on the setup in Asset Management.</span></span> <span data-ttu-id="606fa-113">Ha a munkarendelés életciklus-állapotát azért hozták létre, hogy elkészült vagy befejezett munkarendeléseket kezeljen, és ha az adott munkarendelési életciklus-állapot **Eszköz DBJ frissítése** beállítása **Igen** a **Munkarendelés életciklus-állapotai** oldalon, akkor a munkarendelésen használt összes cikk automatikusan frissül az **Eszköz DBJ** oldalon, amikor a munkarendelést az adott életciklus-állapotra frissítik.</span><span class="sxs-lookup"><span data-stu-id="606fa-113">If a work order lifecycle state has been created to handle finished or completed work orders, and if the **Update asset BOM** option for that work order lifecycle state is set to **Yes** on the **Work order lifecycle states** page, all items that are used on the work order will be automatically updated on the **Asset BOM** page when the work order is updated to that lifecycle state.</span></span> 


<span data-ttu-id="606fa-114">Az Eszköz DBJ-t manuálisan is frissítheti az új cikksorok létrehozásával az **Eszköz DBJ** oldalon.</span><span class="sxs-lookup"><span data-stu-id="606fa-114">You can also manually update an asset BOM by creating new item lines on the **Asset BOM** page.</span></span>

<span data-ttu-id="606fa-115">Az **Eszköz DBJ** oldalon nyomon követheti az eszközökhöz tartozó pótalkatrész-előzményeket, miután a cikkfelhasználást rögzítették a munkarendelésen.</span><span class="sxs-lookup"><span data-stu-id="606fa-115">On the **Asset BOM** page, you can track spare parts history for assets after item consumption is registered on a work order.</span></span> <span data-ttu-id="606fa-116">A funkció használatához ki kell választania a pótalkatrészek nyilvántartásához használatos cikkcsoportot a **Pótalkatrészek cikkcsoportjai** odlalon.</span><span class="sxs-lookup"><span data-stu-id="606fa-116">To use this functionality, you must select the item groups that should be used for spare parts registration on the **Spare parts item groups** page.</span></span>

<span data-ttu-id="606fa-117">Az Eszköz DBJ funkció használatához először be kell állítania a szükséges pótalkatrész-cikkcsoportokat.</span><span class="sxs-lookup"><span data-stu-id="606fa-117">To use asset BOM functionality, you must first set up the required spare parts items groups.</span></span> <span data-ttu-id="606fa-118">Ezt követően, ha azt szeretné, hogy az Eszköz DBJ automatikusan frissüljön egy munkarendelés befejezésekor, akkor egy beállíthat egy munkarendelési életciklus-állapotot az adott frissítés kezelésére.</span><span class="sxs-lookup"><span data-stu-id="606fa-118">Then, if you want the asset BOM to be automatically updated when a work order is completed, you can set up a work order lifecycle state to handle that update.</span></span> 


## <a name="set-up-spare-parts-item-groups"></a><span data-ttu-id="606fa-119">Pótalkatrész-cikkcsoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="606fa-119">Set up spare parts item groups</span></span>

<span data-ttu-id="606fa-120">A pótalkatrészekkel kapcsolatos előzmények beállítása a **Készlet- és raktárkezelés** modulban létrehozott cikkcsoportokon alapul.</span><span class="sxs-lookup"><span data-stu-id="606fa-120">The setup of spare parts history is based on item groups that are created in the **Inventory and warehouse management** module.</span></span> <span data-ttu-id="606fa-121">Az Eszközkezelés modulban beállíthat cikkcsoportokat, így nyomon követheti a pótalkatrészek előzményeit a kiválasztott cikkcsoportokban szerepelő cikkeknél.</span><span class="sxs-lookup"><span data-stu-id="606fa-121">In Asset Management, you set up item groups so that you can track spare parts history for the items in the selected item groups.</span></span>

1. <span data-ttu-id="606fa-122">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszköz** \> **Pótalkatrészek cikkcsoportjai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="606fa-122">Select **Asset management** \> **Setup** \> **Asset** \> **Spare parts item groups**.</span></span>
2. <span data-ttu-id="606fa-123">Válassza az **Új** lehetőséget a Cikkcsoport beállításához.</span><span class="sxs-lookup"><span data-stu-id="606fa-123">Select **New** to set up an item group.</span></span>
3. <span data-ttu-id="606fa-124">A **Cikkcsoport** mezőben válassza ki a csoportot.</span><span class="sxs-lookup"><span data-stu-id="606fa-124">In the **Item group** field, select the group.</span></span> <span data-ttu-id="606fa-125">A csoport nevét a program automatikusan beírja a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="606fa-125">The name of the group is automatically entered in the **Name** field.</span></span>

## <a name="view-and-update-asset-boms"></a><span data-ttu-id="606fa-126">Eszköz DBJ megtekintése és frissítése</span><span class="sxs-lookup"><span data-stu-id="606fa-126">View and update asset BOMs</span></span>

<span data-ttu-id="606fa-127">Miután bejegyezte a cikkfelhasználást egy munkarendelésen, megtekintheti a rögzített cikkfelhasználást az **Eszköz DBJ** oldalon.</span><span class="sxs-lookup"><span data-stu-id="606fa-127">After you post item consumption on a work order, you can view the registered item consumption on the **Asset BOM** page.</span></span>

1. <span data-ttu-id="606fa-128">Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Aktív eszközök** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="606fa-128">Select **Asset management** \> **Common** \> **Assets** \> **Active assets**.</span></span> <span data-ttu-id="606fa-129">Válassza ki az eszközt a listában, majd válassza az **Eszköz DBJ** értéket.</span><span class="sxs-lookup"><span data-stu-id="606fa-129">Select the asset in the list, and then select **Asset BOM**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="606fa-130">Ha az összes eszközre vonatkozó összes cikkfelhasználási nyilvántartást meg szeretné tekinteni,válassza az **Eszközkezelés** \> **Lekérdezések** \> **Eszközök** \> **Eszköz DBJ** elemet.</span><span class="sxs-lookup"><span data-stu-id="606fa-130">To view all item consumption registrations on all assets, select **Asset management** \> **Inquiries** \> **Assets** \> **Asset BOM**.</span></span>

2. <span data-ttu-id="606fa-131">Válassza az **Eszköz DBJ frissítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="606fa-131">Select **Update asset BOM**.</span></span> <span data-ttu-id="606fa-132">Igény szerint hozzáadhat eszközöket, eszköztípusokat és erőforrásokat a frissítéshez a **Kiválasztás** elemmel.</span><span class="sxs-lookup"><span data-stu-id="606fa-132">You can add assets, asset types, and resources to the update as you require by selecting **Select**.</span></span> <span data-ttu-id="606fa-133">A frissítés az **OK** gombot választva indítható el.</span><span class="sxs-lookup"><span data-stu-id="606fa-133">Select **OK** to start the update.</span></span> <span data-ttu-id="606fa-134">A Frissítés funkciót kötegelt feladatként is beállíthatja.</span><span class="sxs-lookup"><span data-stu-id="606fa-134">You can also set up the Update function as a batch job.</span></span>
3. <span data-ttu-id="606fa-135">Ha a cikkekhez kapcsolódó további információkat szeretne látni, készletdimenziókat is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="606fa-135">If you want to see more information that is related to the items, you can add inventory dimensions.</span></span> <span data-ttu-id="606fa-136">Válassza a **Készlet** \> **Dimenziók megjelenítése** elemet, majd jelölje be a látni kívánt dimenziók melletti jelölőnégyzeteket.</span><span class="sxs-lookup"><span data-stu-id="606fa-136">Select **Inventory** \> **Dimensions display**, and then select the check boxes for the dimensions that you want to see.</span></span> <span data-ttu-id="606fa-137">Ha ezt a beállítást meg szeretné őrizni az **Eszköz DBJ** lapon lévő összes eszközre vonatkozóan, állítsa a **Beállítás mentése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="606fa-137">To keep this setup for all assets on the **Asset BOM** page, set the **Save setup** option to **Yes**.</span></span>
4. <span data-ttu-id="606fa-138">Ha szeretne áttekintést kapni arról, hogy az Eszközkezelésben hol használják a kiválasztott sorban található cikk az eszközökkel, alapértelmezett feladattípusokkal, pótalkatrészekkel és munkarendelésekkel kapcsolatban, válassza a **Cikket hol használják** elemet.</span><span class="sxs-lookup"><span data-stu-id="606fa-138">To get an overview of where in Asset Management the item on the selected line is used, in relation to assets, job type defaults, spare parts, and work orders, select **Item where used**.</span></span> 
5. <span data-ttu-id="606fa-139">Ha csak az aktív cikksorokat szeretné látni, válassza a **Megtekintés** \> **Aktuális** elemet.</span><span class="sxs-lookup"><span data-stu-id="606fa-139">If you want to see only active item lines, select **View** \> **Current**.</span></span> <span data-ttu-id="606fa-140">Az összes cikksor megtekintéséhez, beleértve azokat a sorokat is, amelyeknél a lejárat dátuma korábbi az aktuális dátumnál, válassza a **Megtekintés** \> **Összes** elemet.</span><span class="sxs-lookup"><span data-stu-id="606fa-140">To see all item lines, including lines where the expiration date is earlier than the current date, select **View** \> **All**.</span></span>

> [!NOTE]
> <span data-ttu-id="606fa-141">Amikor befejezett egy unkarendelést, és a kapcsolódó eszközhöz kapcsolódó cikkek vagy pótalkatrészek egy része lejárt vagy lecserélték már cikkekre vagy pótalkatrészekre, javasoljuk, hogy ennek megfelelően frissítse az Eszköz DBJ-t.</span><span class="sxs-lookup"><span data-stu-id="606fa-141">When you've completed a work order, if some items or spare parts that are related to the related asset have expired or have been replaced by other items or spare parts, we recommend that you update the asset BOM accordingly.</span></span>

## <a name="create-a-new-item-line-in-an-asset-bom"></a><span data-ttu-id="606fa-142">Új cikksor létrehozása egy eszköz DBJ-ben</span><span class="sxs-lookup"><span data-stu-id="606fa-142">Create a new item line in an asset BOM</span></span>

<span data-ttu-id="606fa-143">Az eszközök cikksorait manuálisan is létrehozhatja.</span><span class="sxs-lookup"><span data-stu-id="606fa-143">You can manually create item lines for assets.</span></span>

1. <span data-ttu-id="606fa-144">Az **Eszköz DBJ** oldalon válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="606fa-144">On the **Asset BOM** page, select **New**.</span></span>
2. <span data-ttu-id="606fa-145">Az **Eszköz** mezőben válassza ki azt az eszközt, amelyhez cikksort szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="606fa-145">In the **Asset** field, select the asset to add an item line for.</span></span>
3. <span data-ttu-id="606fa-146">A **Sor száma** mezőben adjon meg egy sorrendben következő sorszámot.</span><span class="sxs-lookup"><span data-stu-id="606fa-146">In the **Line number** field, enter a sequential line number.</span></span>
4. <span data-ttu-id="606fa-147">A **Hatályos** mezőben válassza ki az cikk kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="606fa-147">In the **Effective** field, enter a start date for the item.</span></span>
5. <span data-ttu-id="606fa-148">Ha a cikknek van lejárata, a **Lejárat** mezőben adjon meg egy befejezési dátumot.</span><span class="sxs-lookup"><span data-stu-id="606fa-148">If the item will expire, in the **Expiration** field, enter an end date.</span></span>
6. <span data-ttu-id="606fa-149">Válasszon egy cikket a **Cikkszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="606fa-149">In the **Item number** field, select the item.</span></span> <span data-ttu-id="606fa-150">A nevet a program automatikusan beírja a **Terméknév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="606fa-150">The name is automatically entered in the **Product name** field.</span></span>
7. <span data-ttu-id="606fa-151">A **Mennyiség** mezőbe írja be a használt mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="606fa-151">In the **Quantity** field, enter the quantity that is used.</span></span> <span data-ttu-id="606fa-152">A **Kiszerelés** mező frissítése automatikusan történik.</span><span class="sxs-lookup"><span data-stu-id="606fa-152">The **Unit** field is automatically updated.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]