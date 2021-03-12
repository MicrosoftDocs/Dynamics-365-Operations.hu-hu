---
title: Termékkonfigurációs modell létrehozása
description: Ez az eljárás bemutatja, hogyan lehet egy termékkonfigurációs modellt létrehozni, és alapvető információkat megadni, például attribútumok és alösszetevők.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1e0bea8743d6ca63538b2c84f74b6e4b1e6c2c0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999706"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="4d571-103">Termékkonfigurációs modell létrehozása</span><span class="sxs-lookup"><span data-stu-id="4d571-103">Create a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4d571-104">Ez az eljárás bemutatja, hogyan lehet egy termékkonfigurációs modellt létrehozni, és alapvető információkat megadni, például attribútumok és alösszetevők.</span><span class="sxs-lookup"><span data-stu-id="4d571-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="4d571-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="4d571-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="4d571-106">Termékmodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="4d571-106">Create a product model</span></span>
1. <span data-ttu-id="4d571-107">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="4d571-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="4d571-108">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d571-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="4d571-109">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="4d571-109">Click New.</span></span>
4. <span data-ttu-id="4d571-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d571-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="4d571-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d571-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="4d571-112">Válasszon ki egy lehetőséget a Feloldóstratégia mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d571-112">In the Solver strategy field, select an option.</span></span>
    * <span data-ttu-id="4d571-113">A feloldási stratégia határozza meg, hogy hogyan kerülnek feldolgozásra egy megszorításon alapuló termékkonfigurációs modellben a megszorítások.</span><span class="sxs-lookup"><span data-stu-id="4d571-113">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="4d571-114">Ez a választás hatással lehet a termékkonfigurációs modell teljesítményére.</span><span class="sxs-lookup"><span data-stu-id="4d571-114">This selection can have an impact on the performance of the product configuration model.</span></span>  
7. <span data-ttu-id="4d571-115">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d571-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="4d571-116">A legfelső szintű összetevő felel meg a termékkonfigurációs modellnek, de használható más termékmodellekben is.</span><span class="sxs-lookup"><span data-stu-id="4d571-116">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
8. <span data-ttu-id="4d571-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4d571-117">Click OK.</span></span>
9. <span data-ttu-id="4d571-118">Válasszon ki egy lehetőséget a Konfigurációk újbóli felhasználása mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d571-118">In the Reuse configurations field, select an option.</span></span>
    * <span data-ttu-id="4d571-119">Ha a konfigurációk újbóli használatához tartozó paraméter értéke Igen, a rendszer minden egyes konfigurációs munkamenet után ellenőrzi, hogy vannak-e azonos konfigurációk, és újrafelhasználást végez, ha pontos egyezést talál.</span><span class="sxs-lookup"><span data-stu-id="4d571-119">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="4d571-120">Attribútumok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="4d571-120">Add attributes</span></span>
1. <span data-ttu-id="4d571-121">Bontsa ki az Attribútumok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4d571-121">Expand the Attributes section.</span></span>
2. <span data-ttu-id="4d571-122">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="4d571-122">Click Add.</span></span>
3. <span data-ttu-id="4d571-123">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="4d571-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="4d571-124">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d571-124">In the Name field, type a value.</span></span>
5. <span data-ttu-id="4d571-125">Írjon be egy értéket a Feloldónév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d571-125">In the Solver name field, type a value.</span></span>
    * <span data-ttu-id="4d571-126">A feloldónevet a termékkonfiguráló a megszorításfeloldója használja.</span><span class="sxs-lookup"><span data-stu-id="4d571-126">The Solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="4d571-127">Nem tartalmazhat szóközt vagy különleges karaktert kivéve: _(aláhúzás).</span><span class="sxs-lookup"><span data-stu-id="4d571-127">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="4d571-128">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d571-128">In the Description field, type a value.</span></span>
    * <span data-ttu-id="4d571-129">A leírószöveg megjelenik a konfiguráció felhasználója számára, és ezért segítségként alkalmazható a megfelelő attribútumérték kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="4d571-129">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="4d571-130">Az „Attribútumtípus” mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d571-130">In the Attribute type field, enter or select a value.</span></span>
    * <span data-ttu-id="4d571-131">Az attribútum típusa határozza meg, hogy mely értékeket érhetők el az attribútum esetében.</span><span class="sxs-lookup"><span data-stu-id="4d571-131">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="4d571-132">Jelölje be a Felvétel az újrahasználhatók közé jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4d571-132">Select the Include in reuse check box.</span></span>
    * <span data-ttu-id="4d571-133">Ez a lehetőség csak akkor érhető el, ha a Konfigurációk újbóli használata lehetőség ki van választva.</span><span class="sxs-lookup"><span data-stu-id="4d571-133">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="4d571-134">Amennyiben az attribútumra vonatkozik az Újbóli használat jelölőnégyzet, az azt jelenti hogy a rendszer figyelembe veszi ezt az attribútumot, amikor pontos egyezést keres.</span><span class="sxs-lookup"><span data-stu-id="4d571-134">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="4d571-135">Alösszetevők hozzáadása</span><span class="sxs-lookup"><span data-stu-id="4d571-135">Add subcomponents</span></span>
1. <span data-ttu-id="4d571-136">Bontsa ki az Alösszetevők szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4d571-136">Expand the Subcomponents section.</span></span>
2. <span data-ttu-id="4d571-137">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="4d571-137">Click Add.</span></span>
3. <span data-ttu-id="4d571-138">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="4d571-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="4d571-139">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d571-139">In the Name field, type a value.</span></span>
5. <span data-ttu-id="4d571-140">Írjon be egy értéket a Feloldónév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d571-140">In the Solver name field, type a value.</span></span>
6. <span data-ttu-id="4d571-141">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d571-141">In the Description field, type a value.</span></span>
7. <span data-ttu-id="4d571-142">Az Összetevő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d571-142">In the Component field, enter or select a value.</span></span>
    * <span data-ttu-id="4d571-143">Minden alösszetevőnek hivatkoznia kell egy összetevő-definícióra.</span><span class="sxs-lookup"><span data-stu-id="4d571-143">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="4d571-144">Ez a tervezés támogatja az újrafelhasználható összetevőket, és gondoskodik arról, hogy összetevő a definiálása után sok termékmodellekben alkalmazható legyen.</span><span class="sxs-lookup"><span data-stu-id="4d571-144">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="4d571-145">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4d571-145">Click Save.</span></span>
9. <span data-ttu-id="4d571-146">Kattintson az Anyagjegyzéksor részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d571-146">Click BOM line details.</span></span>
    * <span data-ttu-id="4d571-147">Az Anyagjegyzéksor részletei űrlap lehetővé teszi, hogy a felhasználó kiválaszthassa az alösszetevő tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="4d571-147">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="4d571-148">Minden tulajdonságnak lehet egy rögzített értéket adni, vagy hozzá lehet rendelni őket egy-egy attribútumhoz.</span><span class="sxs-lookup"><span data-stu-id="4d571-148">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="4d571-149">Attribútumhoz rendeléskor az Anyagjegyzéksor tulajdonság értéke eltérő lesz a kiválasztott konfigurációtól függően.</span><span class="sxs-lookup"><span data-stu-id="4d571-149">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="4d571-150">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d571-150">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="4d571-151">Az egyes alösszetevők egy megszorításon alapuló konfigurációs technológiát használó konfigurálható alapterméket jelentenek.</span><span class="sxs-lookup"><span data-stu-id="4d571-151">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="4d571-152">A hivatkozás a cikkszámon keresztül történik.</span><span class="sxs-lookup"><span data-stu-id="4d571-152">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="4d571-153">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4d571-153">Select the Set check box.</span></span>
12. <span data-ttu-id="4d571-154">Válassza ki az Igen lehetőséget a Számítás mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d571-154">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="4d571-155">A számítási beállítást megadva lehet biztosítani, hogy a rendszer figyelembe vegye a terméket, amikor a termék költségszámítását végzi.</span><span class="sxs-lookup"><span data-stu-id="4d571-155">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="4d571-156">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="4d571-156">Click the Setup tab.</span></span>
14. <span data-ttu-id="4d571-157">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4d571-157">Select the Set check box.</span></span>
15. <span data-ttu-id="4d571-158">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d571-158">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="4d571-159">A mennyiség mező meghatározza, hogy ebből a termékből mennyi kerül felhasználásra a konfigurált termékben.</span><span class="sxs-lookup"><span data-stu-id="4d571-159">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="4d571-160">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4d571-160">Select the Set check box.</span></span>
17. <span data-ttu-id="4d571-161">A Sorozatonként mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="4d571-161">In the Per series field, enter a number.</span></span>
18. <span data-ttu-id="4d571-162">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4d571-162">Click OK.</span></span>

