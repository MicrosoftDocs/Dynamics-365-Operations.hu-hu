---
title: Cikkminőségi csoportok
description: Ez a témakör azt írja le, hogyan lehet a termékek logikai csoportosítására cikkminőségi csoportokat használni és létrehozni, hogy a minőségi rendelések automatikus létrehozásához minőségi rendeléseket lehessen hozzárendelni.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 272cb748e0a2722d9744fe6b357d767a1d6aeb26
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022252"
---
# <a name="item-quality-groups"></a><span data-ttu-id="4446e-103">Cikkminőségi csoportok</span><span class="sxs-lookup"><span data-stu-id="4446e-103">Item quality groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4446e-104">A minőségi csoport a cikkekre vonatkozó közös tesztkövetelményeket képvisel.</span><span class="sxs-lookup"><span data-stu-id="4446e-104">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="4446e-105">Ez a témakör azt írja le, hogyan lehet a termékek logikai csoportosítására cikkminőségi csoportokat használni és létrehozni, hogy a minőségi rendelések automatikus létrehozásához minőségi rendeléseket lehessen hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="4446e-105">This topic describes how to use and create item quality groups to logically group products so that they can be assigned to quality associations for the automatic generation of quality orders.</span></span>

<span data-ttu-id="4446e-106">A minőségi csoporthoz rendelt cikkeket, illetve a cikkhez rendelt minőségi csoportokat lehet beállítani, módosítani és megtekinteni, ehhez menjen a **Készletkezelés \> Beállítás \> Minőségi csoportok** részhez.</span><span class="sxs-lookup"><span data-stu-id="4446e-106">To set up, edit, and view the items that are assigned to a quality group, or the quality groups that are assigned to an item, go to **Inventory management \> Setup \> Quality groups**.</span></span> <span data-ttu-id="4446e-107">Miután a **Tesztcsoportok** oldalon definiálta a tesztkövetelményeket, meghatározhatja a minőségi rendelések automatikus létrehozásának szabályait.</span><span class="sxs-lookup"><span data-stu-id="4446e-107">After you define the test requirements on the **Test groups** page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="4446e-108">A folyamat egyszerűsítése érdekében az egyes cikkekhez tartozó szabályokat Ön nem határozza meg.</span><span class="sxs-lookup"><span data-stu-id="4446e-108">To simplify the process, you don't define rules for individual items.</span></span> <span data-ttu-id="4446e-109">Ehelyett egy minőségi csoportra vonatkozó szabályokat definiálhatunk a **Minőségi társítások** oldalon.</span><span class="sxs-lookup"><span data-stu-id="4446e-109">Instead, you can define the rules for a quality group on the **Quality associations** page.</span></span>

## <a name="example-of-an-item-quality-group"></a><span data-ttu-id="4446e-110">Példa egy cikkminőségi csoportra</span><span class="sxs-lookup"><span data-stu-id="4446e-110">Example of an item quality group</span></span>

<span data-ttu-id="4446e-111">Egy gyártóvállalat több nyersanyagot is vásárol, amelyeknél a beérkezéskor szükséges vizsgálatokra ugyanazok a tesztkövetelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="4446e-111">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="4446e-112">Ezért a vállalat definiál egy minőségi csoportot, majd hozzárendeli a nyersanyagokhoz társított cikkszámokat a csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="4446e-112">Therefore, the company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="4446e-113">Később a vállalat egy új típusú nyersanyagot vásárol, amelyre az előzőekkel azonos tesztkövetelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="4446e-113">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="4446e-114">Ahelyett, hogy az új anyagra új tesztkövetelményeket állítana be, a vállalat hozzáadja az új anyag cikkszámát a meglévő minőségi csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="4446e-114">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span>

<span data-ttu-id="4446e-115">Ugyanez a vállalat olyan cikkeket is gyárt, amelyek gyártási tesztjeire ugyanazok a követelmények érvényesek, és olyan cikkeket is szállít, amelyek szállítás előtti tesztjeire ugyanolyan követelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="4446e-115">The same company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="4446e-116">Ezért a vállalat két további minőségi csoportot határoz meg, majd a megfelelő cikkszámokat hozzárendeli az egyes minőségi csoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="4446e-116">Therefore, the company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="4446e-117">Minőségi csoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="4446e-117">Create a quality group</span></span>

<span data-ttu-id="4446e-118">Minőségi csoport létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4446e-118">To create a quality group, follow these steps.</span></span>

1. <span data-ttu-id="4446e-119">Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Minőségi csoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="4446e-119">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="4446e-120">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="4446e-120">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="4446e-121">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="4446e-121">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="4446e-122">**Minőségi csoport** – Adja meg a minőségi csoport egyedi azonosítóját vagy nevét.</span><span class="sxs-lookup"><span data-stu-id="4446e-122">**Quality group** – Enter a unique ID or name for the quality group.</span></span>
    - <span data-ttu-id="4446e-123">**Leírás** – Adja meg a minőségi csoport részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="4446e-123">**Description** – Enter a detailed description of the quality group.</span></span>

1. <span data-ttu-id="4446e-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4446e-124">Close the page.</span></span>

## <a name="manually-add-items-to-a-quality-group"></a><span data-ttu-id="4446e-125">Cikkek manuális hozzáadása egy minőségi csoporthoz</span><span class="sxs-lookup"><span data-stu-id="4446e-125">Manually add items to a quality group</span></span>

<span data-ttu-id="4446e-126">A következő lépések követésével adhat hozzá cikkeket manuálisan egy minőségi csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="4446e-126">To manually add items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="4446e-127">Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Minőségi csoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="4446e-127">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="4446e-128">Annak a minőségi csoportnak a kiválasztása, amelybe cikkeket szeretne felvenni.</span><span class="sxs-lookup"><span data-stu-id="4446e-128">Select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="4446e-129">A Művelet ablaktáblán kattintson a **Cikkek** elemre.</span><span class="sxs-lookup"><span data-stu-id="4446e-129">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="4446e-130">A **Cikkek a minőségi csoportokban** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához.</span><span class="sxs-lookup"><span data-stu-id="4446e-130">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="4446e-131">Ezután az új sorhoz állítsa be a **Cikkszám** mezőt a hozzáadni kívánt cikkszámhoz.</span><span class="sxs-lookup"><span data-stu-id="4446e-131">Then, for the new row, set the **Item number** field to the item number that you want to add.</span></span>
1. <span data-ttu-id="4446e-132">Ismételje meg az előző lépést minden olyan cikkel, amit hozzá szeretne még adni.</span><span class="sxs-lookup"><span data-stu-id="4446e-132">Repeat the previous step for each additional item that must be added.</span></span>
1. <span data-ttu-id="4446e-133">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="4446e-133">Close the pages.</span></span>

## <a name="add-multiple-items-to-a-quality-group"></a><span data-ttu-id="4446e-134">Több cikk hozzáadása egy minőségi csoporthoz</span><span class="sxs-lookup"><span data-stu-id="4446e-134">Add multiple items to a quality group</span></span>

<span data-ttu-id="4446e-135">A következő lépések követésével adhat hozzá több cikkeket egy minőségi csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="4446e-135">To add multiple items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="4446e-136">Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Minőségi csoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="4446e-136">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="4446e-137">Annak a minőségi csoportnak a létehozása vagy kiválasztása, amelybe cikkeket szeretne felvenni.</span><span class="sxs-lookup"><span data-stu-id="4446e-137">Create or select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="4446e-138">A Művelet ablaktáblán kattintson a **Cikkek hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="4446e-138">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="4446e-139">A **Lekérdezés** párbeszédpanelen adja meg a hozzáadni kívánt cikkek szűrési feltételét.</span><span class="sxs-lookup"><span data-stu-id="4446e-139">In the **Inquiry** dialog box, enter the filter criteria for the items that you want to add.</span></span> <span data-ttu-id="4446e-140">Szűrheti például egy adott cikkcsoport minden cikkét.</span><span class="sxs-lookup"><span data-stu-id="4446e-140">For example, you might filter for all items in a specific item group.</span></span>
1. <span data-ttu-id="4446e-141">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4446e-141">Select **OK**.</span></span>
1. <span data-ttu-id="4446e-142">A **Cikkek hozzáadása** párbeszédpanelen egy rács jeleníti meg a lekérdezésnek megfelelő összes elemet.</span><span class="sxs-lookup"><span data-stu-id="4446e-142">In the **Add items** dialog box, a grid shows all the items that match your query.</span></span> <span data-ttu-id="4446e-143">Az eredmények áttekintése.</span><span class="sxs-lookup"><span data-stu-id="4446e-143">Review the results.</span></span>

    <span data-ttu-id="4446e-144">Ha bármilyen módosítás szükséges, akkor a **Kijelölés** gombra kattintva visszatérhet a **Lekérdezés** párbeszédpanelre, és módosíthatja a lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="4446e-144">If any changes are required, select **Select** to return to the **Inquiry** dialog box, and adjust your query.</span></span>

1. <span data-ttu-id="4446e-145">Ha az eredmények tartalmazzák az összes hozzáadni kívánt tételt, akkor válassza az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="4446e-145">When the results include all the items that you want to add, select **OK**.</span></span>
1. <span data-ttu-id="4446e-146">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4446e-146">Close the page.</span></span>

## <a name="manually-associate-an-item-with-a-quality-group"></a><span data-ttu-id="4446e-147">Cikk manuális társítása minőségi csoporthoz</span><span class="sxs-lookup"><span data-stu-id="4446e-147">Manually associate an item with a quality group</span></span>

<span data-ttu-id="4446e-148">A következő lépések követésével társíthat cikket egy minőségi csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="4446e-148">To manually associate an item with a quality group, follow these steps.</span></span>

1. <span data-ttu-id="4446e-149">Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Cikkminőségi csoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="4446e-149">Go to **Inventory management \> Setup \> Quality control \> Item quality groups**.</span></span>
1. <span data-ttu-id="4446e-150">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="4446e-150">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="4446e-151">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="4446e-151">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="4446e-152">**Cikkszám** – Válassza ki a hozzáadni kívánt cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="4446e-152">**Item number** – Select the item number to add.</span></span>
    - <span data-ttu-id="4446e-153">**Minőségi csoport** – A cikkhez hozzárendelni kívánt minőségi csoport kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="4446e-153">**Quality group** – Select the quality group to assign to the item.</span></span>

1. <span data-ttu-id="4446e-154">Ismételje meg az előző lépést a cikk minden további, hozzáadni kívánt minőségi csoportjával.</span><span class="sxs-lookup"><span data-stu-id="4446e-154">Repeat the previous step for each additional combination of an item and a quality group that must be added.</span></span>
1. <span data-ttu-id="4446e-155">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="4446e-155">Close the pages.</span></span>

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a><span data-ttu-id="4446e-156">Minőségi csoport manuális hozzáadása a Kiadott termékek lapon</span><span class="sxs-lookup"><span data-stu-id="4446e-156">Manually add a quality group from the Released products page</span></span>

<span data-ttu-id="4446e-157">Ahhoz, hogy minőségi csoportot adjon hozzá manuálisan a **Kiadott termékek** lapon, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4446e-157">To manually add a quality group from the **Released products** page, follow these steps.</span></span>

1. <span data-ttu-id="4446e-158">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4446e-158">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="4446e-159">Jelölje ki a terméket, amelyhez minőségi csoportot kíván rendelni.</span><span class="sxs-lookup"><span data-stu-id="4446e-159">Select the product that you want to assign a quality group to.</span></span>
1. <span data-ttu-id="4446e-160">A Műveleti panelen, a **Készletkezelés lapon** a **Minőség** csoportban válassza a **Cikkminőségi csoportok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4446e-160">On the Action Pane, on the **Manage inventory** tab, in the **Quality** group, select **Item quality groups**.</span></span>
1. <span data-ttu-id="4446e-161">A **Cikkek a minőségi csoportokban** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához.</span><span class="sxs-lookup"><span data-stu-id="4446e-161">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="4446e-162">Ezután az új sornál állítsa a **Minőségi csoport** mezőt a termékhez hozzárendelni kívánt minőségi csoportra.</span><span class="sxs-lookup"><span data-stu-id="4446e-162">Then, for the new row, set the **Quality group** field to the quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="4446e-163">Ismételje meg az előző lépést a termékhez hozzárendelni kívánt további minőségi csoportokkal.</span><span class="sxs-lookup"><span data-stu-id="4446e-163">Repeat the previous step for each additional quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="4446e-164">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="4446e-164">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4446e-165">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4446e-165">Additional resources</span></span>

- [<span data-ttu-id="4446e-166">Minőségbiztosítási tesztműszerek</span><span class="sxs-lookup"><span data-stu-id="4446e-166">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="4446e-167">Minőségkezelési tesztek</span><span class="sxs-lookup"><span data-stu-id="4446e-167">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="4446e-168">Minőségbiztosítási tesztcsoportok</span><span class="sxs-lookup"><span data-stu-id="4446e-168">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="4446e-169">Minőségbiztosítási tesztváltozók</span><span class="sxs-lookup"><span data-stu-id="4446e-169">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="4446e-170">Minőségi társítások</span><span class="sxs-lookup"><span data-stu-id="4446e-170">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
