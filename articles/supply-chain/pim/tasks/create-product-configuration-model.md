--- 
title: "Termékkonfigurációs modell létrehozása"
description: "Ez az eljárás bemutatja, hogyan lehet egy termékkonfigurációs modellt létrehozni, és alapvető információkat megadni, például attribútumok és alösszetevők."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0a731a2a0fedcb92523b3f345abb49a18ff0e56a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="c9001-103">Termékkonfigurációs modell létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9001-103">Create a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c9001-104">Ez az eljárás bemutatja, hogyan lehet egy termékkonfigurációs modellt létrehozni, és alapvető információkat megadni, például attribútumok és alösszetevők.</span><span class="sxs-lookup"><span data-stu-id="c9001-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="c9001-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="c9001-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="c9001-106">Termékmodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9001-106">Create a product model</span></span>
1. <span data-ttu-id="c9001-107">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="c9001-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="c9001-108">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9001-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="c9001-109">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="c9001-109">Click New.</span></span>
4. <span data-ttu-id="c9001-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c9001-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="c9001-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9001-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="c9001-112">Válasszon ki egy lehetőséget a Feloldóstratégia mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9001-112">In the Solver strategy field, select an option.</span></span>
    * <span data-ttu-id="c9001-113">A feloldási stratégia határozza meg, hogy hogyan kerülnek feldolgozásra egy megszorításon alapuló termékkonfigurációs modellben a megszorítások.</span><span class="sxs-lookup"><span data-stu-id="c9001-113">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="c9001-114">Ez a választás hatással lehet a termékkonfigurációs modell teljesítményére.</span><span class="sxs-lookup"><span data-stu-id="c9001-114">This selection can have an impact on the performance of the product configuration model.</span></span>  
7. <span data-ttu-id="c9001-115">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c9001-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="c9001-116">A legfelső szintű összetevő felel meg a termékkonfigurációs modellnek, de használható más termékmodellekben is.</span><span class="sxs-lookup"><span data-stu-id="c9001-116">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
8. <span data-ttu-id="c9001-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c9001-117">Click OK.</span></span>
9. <span data-ttu-id="c9001-118">Válasszon ki egy lehetőséget a Konfigurációk újbóli felhasználása mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9001-118">In the Reuse configurations field, select an option.</span></span>
    * <span data-ttu-id="c9001-119">Ha a konfigurációk újbóli használatához tartozó paraméter értéke Igen, a rendszer minden egyes konfigurációs munkamenet után ellenőrzi, hogy vannak-e azonos konfigurációk, és újrafelhasználást végez, ha pontos egyezést talál.</span><span class="sxs-lookup"><span data-stu-id="c9001-119">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="c9001-120">Attribútumok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c9001-120">Add attributes</span></span>
1. <span data-ttu-id="c9001-121">Bontsa ki az Attribútumok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c9001-121">Expand the Attributes section.</span></span>
2. <span data-ttu-id="c9001-122">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="c9001-122">Click Add.</span></span>
3. <span data-ttu-id="c9001-123">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c9001-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="c9001-124">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c9001-124">In the Name field, type a value.</span></span>
5. <span data-ttu-id="c9001-125">Írjon be egy értéket a Feloldónév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c9001-125">In the Solver name field, type a value.</span></span>
    * <span data-ttu-id="c9001-126">A feloldónevet a termékkonfiguráló a megszorításfeloldója használja.</span><span class="sxs-lookup"><span data-stu-id="c9001-126">The Solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="c9001-127">Nem tartalmazhat szóközt vagy különleges karaktert kivéve: _(aláhúzás).</span><span class="sxs-lookup"><span data-stu-id="c9001-127">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="c9001-128">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9001-128">In the Description field, type a value.</span></span>
    * <span data-ttu-id="c9001-129">A leírószöveg megjelenik a konfiguráció felhasználója számára, és ezért segítségként alkalmazható a megfelelő attribútumérték kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="c9001-129">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="c9001-130">Az „Attribútumtípus” mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9001-130">In the Attribute type field, enter or select a value.</span></span>
    * <span data-ttu-id="c9001-131">Az attribútum típusa határozza meg, hogy mely értékeket érhetők el az attribútum esetében.</span><span class="sxs-lookup"><span data-stu-id="c9001-131">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="c9001-132">Jelölje be a Felvétel az újrahasználhatók közé jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c9001-132">Select the Include in reuse check box.</span></span>
    * <span data-ttu-id="c9001-133">Ez a lehetőség csak akkor érhető el, ha a Konfigurációk újbóli használata lehetőség ki van választva.</span><span class="sxs-lookup"><span data-stu-id="c9001-133">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="c9001-134">Amennyiben az attribútumra vonatkozik az Újbóli használat jelölőnégyzet, az azt jelenti hogy a rendszer figyelembe veszi ezt az attribútumot, amikor pontos egyezést keres.</span><span class="sxs-lookup"><span data-stu-id="c9001-134">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="c9001-135">Alösszetevők hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c9001-135">Add subcomponents</span></span>
1. <span data-ttu-id="c9001-136">Bontsa ki az Alösszetevők szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c9001-136">Expand the Subcomponents section.</span></span>
2. <span data-ttu-id="c9001-137">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="c9001-137">Click Add.</span></span>
3. <span data-ttu-id="c9001-138">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c9001-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="c9001-139">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c9001-139">In the Name field, type a value.</span></span>
5. <span data-ttu-id="c9001-140">Írjon be egy értéket a Feloldónév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c9001-140">In the Solver name field, type a value.</span></span>
6. <span data-ttu-id="c9001-141">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9001-141">In the Description field, type a value.</span></span>
7. <span data-ttu-id="c9001-142">Az Összetevő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9001-142">In the Component field, enter or select a value.</span></span>
    * <span data-ttu-id="c9001-143">Minden alösszetevőnek hivatkoznia kell egy összetevő-definícióra.</span><span class="sxs-lookup"><span data-stu-id="c9001-143">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="c9001-144">Ez a tervezés támogatja az újrafelhasználható összetevőket, és gondoskodik arról, hogy összetevő a definiálása után sok termékmodellekben alkalmazható legyen.</span><span class="sxs-lookup"><span data-stu-id="c9001-144">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="c9001-145">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c9001-145">Click Save.</span></span>
9. <span data-ttu-id="c9001-146">Kattintson az Anyagjegyzéksor részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9001-146">Click BOM line details.</span></span>
    * <span data-ttu-id="c9001-147">Az Anyagjegyzéksor részletei űrlap lehetővé teszi, hogy a felhasználó kiválaszthassa az alösszetevő tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="c9001-147">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="c9001-148">Minden tulajdonságnak lehet egy rögzített értéket adni, vagy hozzá lehet rendelni őket egy-egy attribútumhoz.</span><span class="sxs-lookup"><span data-stu-id="c9001-148">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="c9001-149">Attribútumhoz rendeléskor az Anyagjegyzéksor tulajdonság értéke eltérő lesz a kiválasztott konfigurációtól függően.</span><span class="sxs-lookup"><span data-stu-id="c9001-149">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="c9001-150">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9001-150">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="c9001-151">Az egyes alösszetevők egy megszorításon alapuló konfigurációs technológiát használó konfigurálható alapterméket jelentenek.</span><span class="sxs-lookup"><span data-stu-id="c9001-151">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="c9001-152">A hivatkozás a cikkszámon keresztül történik.</span><span class="sxs-lookup"><span data-stu-id="c9001-152">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="c9001-153">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c9001-153">Select the Set check box.</span></span>
12. <span data-ttu-id="c9001-154">Válassza ki az Igen lehetőséget a Számítás mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9001-154">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="c9001-155">A számítási beállítást megadva lehet biztosítani, hogy a rendszer figyelembe vegye a terméket, amikor a termék költségszámítását végzi.</span><span class="sxs-lookup"><span data-stu-id="c9001-155">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="c9001-156">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="c9001-156">Click the Setup tab.</span></span>
14. <span data-ttu-id="c9001-157">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c9001-157">Select the Set check box.</span></span>
15. <span data-ttu-id="c9001-158">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9001-158">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="c9001-159">A mennyiség mező meghatározza, hogy ebből a termékből mennyi kerül felhasználásra a konfigurált termékben.</span><span class="sxs-lookup"><span data-stu-id="c9001-159">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="c9001-160">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c9001-160">Select the Set check box.</span></span>
17. <span data-ttu-id="c9001-161">A Sorozatonként mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="c9001-161">In the Per series field, enter a number.</span></span>
18. <span data-ttu-id="c9001-162">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c9001-162">Click OK.</span></span>


