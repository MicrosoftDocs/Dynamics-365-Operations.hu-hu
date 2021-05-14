---
title: Termékkonfigurációs modell létrehozása
description: Ez az eljárás bemutatja, hogyan lehet egy termékkonfigurációs modellt létrehozni, és alapvető információkat megadni, például attribútumok és alösszetevők.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cb9e33d7bab6ca9cd378ec40baa796d1a933ece
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921365"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="9e611-103">Termékkonfigurációs modell létrehozása</span><span class="sxs-lookup"><span data-stu-id="9e611-103">Create a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9e611-104">Ez az eljárás bemutatja, hogyan lehet egy termékkonfigurációs modellt létrehozni, és alapvető információkat megadni, például attribútumok és alösszetevők.</span><span class="sxs-lookup"><span data-stu-id="9e611-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="9e611-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="9e611-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="9e611-106">Termékmodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="9e611-106">Create a product model</span></span>

1. <span data-ttu-id="9e611-107">Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.</span><span class="sxs-lookup"><span data-stu-id="9e611-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="9e611-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e611-108">Select **New**.</span></span>
1. <span data-ttu-id="9e611-109">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9e611-109">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="9e611-110">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9e611-110">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="9e611-111">Válasszon ki egy lehetőséget a **Feloldóstratégia** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9e611-111">In the **Solver strategy** field, select an option.</span></span>
    * <span data-ttu-id="9e611-112">A feloldási stratégia határozza meg, hogy hogyan kerülnek feldolgozásra egy megszorításon alapuló termékkonfigurációs modellben a megszorítások.</span><span class="sxs-lookup"><span data-stu-id="9e611-112">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="9e611-113">Ez a választás hatással lehet a termékkonfigurációs modell teljesítményére.</span><span class="sxs-lookup"><span data-stu-id="9e611-113">This selection can have an impact on the performance of the product configuration model.</span></span>  
1. <span data-ttu-id="9e611-114">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9e611-114">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="9e611-115">A legfelső szintű összetevő felel meg a termékkonfigurációs modellnek, de használható más termékmodellekben is.</span><span class="sxs-lookup"><span data-stu-id="9e611-115">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
1. <span data-ttu-id="9e611-116">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e611-116">Select **OK**.</span></span>
1. <span data-ttu-id="9e611-117">Válasszon ki egy lehetőséget a **Konfigurációk újbóli felhasználása** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9e611-117">In the **Reuse configurations** field, select an option.</span></span>
    * <span data-ttu-id="9e611-118">Ha a konfigurációk újbóli használatához tartozó paraméter értéke Igen, a rendszer minden egyes konfigurációs munkamenet után ellenőrzi, hogy vannak-e azonos konfigurációk, és újrafelhasználást végez, ha pontos egyezést talál.</span><span class="sxs-lookup"><span data-stu-id="9e611-118">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="9e611-119">Attribútumok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="9e611-119">Add attributes</span></span>

1. <span data-ttu-id="9e611-120">Bontsa ki az **Attribútumok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="9e611-120">Expand the **Attributes** section.</span></span>
2. <span data-ttu-id="9e611-121">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e611-121">Select **Add**.</span></span>
3. <span data-ttu-id="9e611-122">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9e611-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="9e611-123">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9e611-123">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="9e611-124">Írjon be egy értéket a **Feloldónév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9e611-124">In the **Solver name** field, type a value.</span></span>
    * <span data-ttu-id="9e611-125">A feloldónevet a termékkonfiguráló a megszorításfeloldója használja.</span><span class="sxs-lookup"><span data-stu-id="9e611-125">The solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="9e611-126">Nem tartalmazhat szóközt vagy különleges karaktert kivéve: _(aláhúzás).</span><span class="sxs-lookup"><span data-stu-id="9e611-126">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="9e611-127">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9e611-127">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="9e611-128">A leírószöveg megjelenik a konfiguráció felhasználója számára, és ezért segítségként alkalmazható a megfelelő attribútumérték kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="9e611-128">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="9e611-129">Az **Attribútumtípus** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9e611-129">In the **Attribute type** field, enter or select a value.</span></span>
    * <span data-ttu-id="9e611-130">Az attribútum típusa határozza meg, hogy mely értékeket érhetők el az attribútum esetében.</span><span class="sxs-lookup"><span data-stu-id="9e611-130">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="9e611-131">Jelölje be a **Felvétel az újrahasználhatók közé** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="9e611-131">Select the **Include in reuse** check box.</span></span>
    * <span data-ttu-id="9e611-132">Ez a lehetőség csak akkor érhető el, ha a Konfigurációk újbóli használata lehetőség ki van választva.</span><span class="sxs-lookup"><span data-stu-id="9e611-132">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="9e611-133">Amennyiben az attribútumra vonatkozik az Újbóli használat jelölőnégyzet, az azt jelenti hogy a rendszer figyelembe veszi ezt az attribútumot, amikor pontos egyezést keres.</span><span class="sxs-lookup"><span data-stu-id="9e611-133">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="9e611-134">Alösszetevők hozzáadása</span><span class="sxs-lookup"><span data-stu-id="9e611-134">Add subcomponents</span></span>

1. <span data-ttu-id="9e611-135">Bontsa ki az **Alösszetevők** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="9e611-135">Expand the **Subcomponents** section.</span></span>
2. <span data-ttu-id="9e611-136">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e611-136">Select **Add**.</span></span>
3. <span data-ttu-id="9e611-137">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9e611-137">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="9e611-138">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9e611-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="9e611-139">Írjon be egy értéket a **Feloldónév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9e611-139">In the **Solver name** field, type a value.</span></span>
6. <span data-ttu-id="9e611-140">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9e611-140">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="9e611-141">Az **Összetevő** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9e611-141">In the **Component** field, enter or select a value.</span></span>
    * <span data-ttu-id="9e611-142">Minden alösszetevőnek hivatkoznia kell egy összetevő-definícióra.</span><span class="sxs-lookup"><span data-stu-id="9e611-142">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="9e611-143">Ez a tervezés támogatja az újrafelhasználható összetevőket, és gondoskodik arról, hogy összetevő a definiálása után sok termékmodellekben alkalmazható legyen.</span><span class="sxs-lookup"><span data-stu-id="9e611-143">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="9e611-144">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e611-144">Select **Save**.</span></span>
9. <span data-ttu-id="9e611-145">Válassza ki az **Anyagjegyzéksor részletei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e611-145">Select **BOM line details**.</span></span>
    * <span data-ttu-id="9e611-146">Az Anyagjegyzéksor részletei űrlap lehetővé teszi, hogy a felhasználó kiválaszthassa az alösszetevő tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="9e611-146">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="9e611-147">Minden tulajdonságnak lehet egy rögzített értéket adni, vagy hozzá lehet rendelni őket egy-egy attribútumhoz.</span><span class="sxs-lookup"><span data-stu-id="9e611-147">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="9e611-148">Attribútumhoz rendeléskor az Anyagjegyzéksor tulajdonság értéke eltérő lesz a kiválasztott konfigurációtól függően.</span><span class="sxs-lookup"><span data-stu-id="9e611-148">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="9e611-149">Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9e611-149">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="9e611-150">Az egyes alösszetevők egy megszorításon alapuló konfigurációs technológiát használó konfigurálható alapterméket jelentenek.</span><span class="sxs-lookup"><span data-stu-id="9e611-150">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="9e611-151">A hivatkozás a cikkszámon keresztül történik.</span><span class="sxs-lookup"><span data-stu-id="9e611-151">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="9e611-152">Jelölje be a **Beállít** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="9e611-152">Select the **Set** check box.</span></span>
12. <span data-ttu-id="9e611-153">Válassza ki az **Igen** lehetőséget a **Számítás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9e611-153">Select **Yes** in the **Calculation** field.</span></span>
    * <span data-ttu-id="9e611-154">A számítási beállítást megadva lehet biztosítani, hogy a rendszer figyelembe vegye a terméket, amikor a termék költségszámítását végzi.</span><span class="sxs-lookup"><span data-stu-id="9e611-154">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="9e611-155">Válassza ki a **Beállítás** fület.</span><span class="sxs-lookup"><span data-stu-id="9e611-155">Select the **Setup** tab.</span></span>
14. <span data-ttu-id="9e611-156">Jelölje be a **Beállít** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="9e611-156">Select the **Set** check box.</span></span>
15. <span data-ttu-id="9e611-157">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9e611-157">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="9e611-158">A mennyiség mező meghatározza, hogy ebből a termékből mennyi kerül felhasználásra a konfigurált termékben.</span><span class="sxs-lookup"><span data-stu-id="9e611-158">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="9e611-159">Jelölje be a **Beállít** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="9e611-159">Select the **Set** check box.</span></span>
17. <span data-ttu-id="9e611-160">A **Sorozatonként** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="9e611-160">In the **Per series** field, enter a number.</span></span>
18. <span data-ttu-id="9e611-161">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e611-161">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]