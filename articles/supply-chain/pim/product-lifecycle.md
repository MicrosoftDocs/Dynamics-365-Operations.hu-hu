---
title: "Termékéletciklus állapota"
description: "A termékéletciklus állapota egy kiadott termék vagy termékváltozat életciklus-állapotát dokumentálja."
author: cvocph
manager: AnnBe
ms.date: 12/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: cvocph
ms.dyn365.ops.version: 7.3
ms.search.validFrom: 2017-12-31
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 8337f1dfb938f9fa69924e77a25a68ee56dbd2ac
ms.contentlocale: hu-hu
ms.lasthandoff: 01/19/2018

---

# <a name="product-lifecycle-state"></a><span data-ttu-id="72c9f-103">Termékéletciklus állapota</span><span class="sxs-lookup"><span data-stu-id="72c9f-103">Product lifecycle state</span></span> 

[!include[banner](../includes/banner.md)]


<span data-ttu-id="72c9f-104">A termékéletciklus állapota egy kiadott termék vagy termékváltozat életciklus-állapotát dokumentálja.</span><span class="sxs-lookup"><span data-stu-id="72c9f-104">A product lifecycle state documents the lifecycle state of a released product or product variant.</span></span> <span data-ttu-id="72c9f-105">A termékéletciklus-állapotokat a felhasználó határozza meg, általában egy termékmenedzser vagy egy termékalapadat-menedzser.</span><span class="sxs-lookup"><span data-stu-id="72c9f-105">Product lifecycle states are defined by the user, typically a product manager or a product master data manager.</span></span> <span data-ttu-id="72c9f-106">Adott üzleti folyamatokra, például a fő tervezésre, hatással lehet egy adott termékéletciklus-állapot.</span><span class="sxs-lookup"><span data-stu-id="72c9f-106">Specific business processes, such as master planning, can be affected by a specific lifecycle state.</span></span>   
 
<span data-ttu-id="72c9f-107">Egy kiadott termék vagy termékváltozat társítható egy termékéletciklus-állapottal, amely azt dokumentálja, hogy jelenleg milyen életciklus-állapotban van az adott termék vagy változat.</span><span class="sxs-lookup"><span data-stu-id="72c9f-107">A released product or product variant can be associated with a product lifecycle state that documents in which lifecycle state a specific product or variant is currently in.</span></span> <span data-ttu-id="72c9f-108">Tetszőleges számú termékéletciklus-állapot adható meg egy állapotnév és egy leírás hozzárendelésével.</span><span class="sxs-lookup"><span data-stu-id="72c9f-108">You can define any number of product lifecycle states by assigning a state name and description.</span></span> <span data-ttu-id="72c9f-109">Kiválasztható egy életciklus-állapot az újonnan kiadott termékek alapértelmezett állapotának.</span><span class="sxs-lookup"><span data-stu-id="72c9f-109">You can select one lifecycle state as the default state for new released products.</span></span> <span data-ttu-id="72c9f-110">A kiadott termékváltozatok öröklik termékéletciklus-állapotukat a kiadott alapterméküktől a létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="72c9f-110">Released product variants inherit their product lifecycle state from their released product master on creation.</span></span> <span data-ttu-id="72c9f-111">Egy kiadott alaptermék életciklus-állapotának módosításakor lehetőség van az összes olyan létező változat frissítésére, amelynek ugyanaz az eredeti állapota.</span><span class="sxs-lookup"><span data-stu-id="72c9f-111">When changing the lifecycle state on a released product master, you can choose to update all existing variants that have the same original state.</span></span>  

## <a name="create-a-new-product-lifecycle-state"></a><span data-ttu-id="72c9f-112">Új termékéletciklus-állapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="72c9f-112">Create a new product lifecycle state</span></span> 
 
- <span data-ttu-id="72c9f-113">Új termékéletciklus-állapot létrehozásáhaz játssza le vagy olvassa el a következő feladat-útmutatót: **Új termékéletciklus-állapot létrehozása**.</span><span class="sxs-lookup"><span data-stu-id="72c9f-113">To create a new product lifecycle state, play or read the task guide **Create a new product lifecycle state**.</span></span> 

-  <span data-ttu-id="72c9f-114">Alapértelmezett termékéletciklus-állapot létrehozásáhaz játssza le vagy olvassa el a következő feladat-útmutatót: **Alapértelmezett termékéletciklus-állapot létrehozása**.</span><span class="sxs-lookup"><span data-stu-id="72c9f-114">To create a default product lifecycle state, play or read the task guide **Create a default product lifecycle state**.</span></span>   

## <a name="associate-product-lifecycle-states-to-released-products"></a><span data-ttu-id="72c9f-115">Termékéletciklus-állapotok társítása kiadott termékekhez</span><span class="sxs-lookup"><span data-stu-id="72c9f-115">Associate product lifecycle states to released products</span></span>  

<span data-ttu-id="72c9f-116">Többféleképpen lehet társítani egy termékéletciklus-állapotot kiadott termékekhez vagy termékváltozatokhoz.</span><span class="sxs-lookup"><span data-stu-id="72c9f-116">There are multiple ways to associate a product lifecycle state to released products or product variants.</span></span>

-  <span data-ttu-id="72c9f-117">Új kiadott termék létrehozáskor automatikusan történik meg az alapértelmezett **Termékéletciklus-állapot** hozzárendelése.</span><span class="sxs-lookup"><span data-stu-id="72c9f-117">On creation of a new released product, the default **Product lifecycle state** is automatically assigned.</span></span> 
-  <span data-ttu-id="72c9f-118">Termék kiadásakor egy jogi személy számára automatikusan történik meg az alapértelmezett **Termékéletciklus-állapot** hozzárendelése.</span><span class="sxs-lookup"><span data-stu-id="72c9f-118">On release of a product to a legal entity, the default **Product lifecycle state** is automatically assigned.</span></span> 
-  <span data-ttu-id="72c9f-119">Termékváltozat kiadásakor egy jogi személy számára a jogi személynél a kiadott alaptermékhez társított **Termékéletciklus-állapot** automatikusan hozzá lesz rendelve az új változathoz.</span><span class="sxs-lookup"><span data-stu-id="72c9f-119">On release of a product variant to a legal entity, the **Product lifecycle state** associated to the released product master in this legal entity is automatically assigned to the new variant.</span></span> 

<span data-ttu-id="72c9f-120">A termékéletciklus-állapot manuálisan frissíthető a következők használatával:</span><span class="sxs-lookup"><span data-stu-id="72c9f-120">You can manually update the product lifecycle state by using:</span></span> 

-    <span data-ttu-id="72c9f-121">A **Kiadott termékek** listaoldal vagy a **Részletek nézet**.</span><span class="sxs-lookup"><span data-stu-id="72c9f-121">The **Released products** list page or **Details view**.</span></span> 
-  <span data-ttu-id="72c9f-122">A **Kiadott termékváltozatok** listaoldal vagy a **Részletek nézet**.</span><span class="sxs-lookup"><span data-stu-id="72c9f-122">The **Released product variants** list page or **Details view**.</span></span> 
-  <span data-ttu-id="72c9f-123">Keresse meg az elavult termékeket vagy termékváltozatokat igény alapján, és társítson hozzájuk egy életciklus-állapotot.</span><span class="sxs-lookup"><span data-stu-id="72c9f-123">Find the obsolete products or product variants based on demand and associate a lifecycle state.</span></span>  

<span data-ttu-id="72c9f-124">A termékéletciklus-állapotok társítására vonatkozó részletes tudnivalókért játssza le vagy olvassa el a következő feladat-útmutatót.</span><span class="sxs-lookup"><span data-stu-id="72c9f-124">For detailed information about how to associate product lifecycle states, play or read the following two task guides.</span></span>

-  <span data-ttu-id="72c9f-125">Egy termékéletciklus-állapot társításához egy kiadott alaptermékhez, játssza le vagy olvassa el a következő feladat-útmutatót: **Termékéletciklus-állapot társítása egy kiadott alaptermékhez**.</span><span class="sxs-lookup"><span data-stu-id="72c9f-125">To associate a product lifecycle state to a released product master, play or read the task guide **Assign a product lifecycle state to a released product master**.</span></span> 

-  <span data-ttu-id="72c9f-126">Egy termékéletciklus-állapot társításához egy kiadott termékhez, játssza le vagy olvassa el a következő feladat-útmutatót: **Termékéletciklus-állapot társítása egy kiadott termékhez**.</span><span class="sxs-lookup"><span data-stu-id="72c9f-126">To associate a product lifecycle state to a release product, play or read the task guide **Assign a product lifecycle state to a released product**.</span></span> 

## <a name="impact-on-master-planning"></a><span data-ttu-id="72c9f-127">Hatás az alaptervezésre</span><span class="sxs-lookup"><span data-stu-id="72c9f-127">Impact on master planning</span></span> 

<span data-ttu-id="72c9f-128">A termékéletciklus-állapotnak egyetlen vezérlőjelzője van: **Aktív a tervezéshez**.</span><span class="sxs-lookup"><span data-stu-id="72c9f-128">The product lifecycle state has only one control flag: **Is active for planning**.</span></span> <span data-ttu-id="72c9f-129">Alapértelmezés szerint a beállított értéke **Igen** az összes létrehozott termékéletciklus-állapotra, de meg is változtatható **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="72c9f-129">By default, this is set to **Yes** for all created product lifecycle states, but it can be changed to **No**.</span></span> <span data-ttu-id="72c9f-130">Ha a beállítás **Nem**, a társított kiadott termékek és kiadott termékváltozatok:</span><span class="sxs-lookup"><span data-stu-id="72c9f-130">When set to **No**, the associated released products or released product variants are:</span></span> 

-  <span data-ttu-id="72c9f-131">Ki vannak zárva az alaptervezésből.</span><span class="sxs-lookup"><span data-stu-id="72c9f-131">Excluded from master planning.</span></span> 
-  <span data-ttu-id="72c9f-132">Ki vannak zárva az anyagjegyzékszint-számításból.</span><span class="sxs-lookup"><span data-stu-id="72c9f-132">Excluded from BOM-level calculation.</span></span> 

<span data-ttu-id="72c9f-133">Részletes információkért arról, hogyan lehet a termékéletciklus-állapotot termékek kizárására használni az alaptervezésből és az anyagjegyzékszint-számításból, játssza le vagy olvassa el a következő feladat-útmutatót: **Termékéletciklus-állapot létrehozása termékek kizárására az alaptervezésből**.</span><span class="sxs-lookup"><span data-stu-id="72c9f-133">For detailed information about how to use product lifecycle state to exclude products from master planning and BOM-level calculation, play or read the task guide **Create a product lifecycle state to exclude products from Master planning**.</span></span>

> [!NOTE]
> <span data-ttu-id="72c9f-134">A megfelelő teljesítmény érdekében ajánlott társítani az összes elavult kiadott terméket vagy termékváltozatot, különösen, ha nem újrahasználható termékkonfigurációs változatokkal dolgozik, az alaptervezéshez inaktivált termékéletciklus-állapottal.</span><span class="sxs-lookup"><span data-stu-id="72c9f-134">For performance reasons, it is highly recommended to associate all obsolete released products or product variants, especially when working with non-reusable product configuration variants, with a product lifecycle state that is deactivated for master planning.</span></span>  
 
## <a name="default-migration-import-and-export"></a><span data-ttu-id="72c9f-135">Alapértelmezett áttelepítés, importálás és exportálás</span><span class="sxs-lookup"><span data-stu-id="72c9f-135">Default migration, import, and export</span></span> 

<span data-ttu-id="72c9f-136">Az adatentitások nem támogatják a termékéletciklus-állapotokat, és az életciklus-állapot nem állítható be változó állapotra a kiadott termék-adatentitásokon keresztül.</span><span class="sxs-lookup"><span data-stu-id="72c9f-136">The product lifecycle states are not supported by data entities, and the lifecycle state cannot be set to a variable state through the released product data entities.</span></span>

-  <span data-ttu-id="72c9f-137">A korábbi verziókról való áttelepítés esetében az összes termék és a termékváltozat életciklus-állapota üres lesz.</span><span class="sxs-lookup"><span data-stu-id="72c9f-137">On migration from previous releases, the lifecycle state of all products and product variants will be blank.</span></span>  
-  <span data-ttu-id="72c9f-138">Kiadott termékek importálásakor egy adatentitáson keresztül, a rendszer az alapértelmezett életciklus-állapot fogja alkalmazni a létrehozáskor.</span><span class="sxs-lookup"><span data-stu-id="72c9f-138">When importing released products through a data entity, the default lifecycle state will be applied on creation.</span></span>  
-  <span data-ttu-id="72c9f-139">Kiadott termékváltozatok importálásakor egy adatentitáson keresztül, a rendszer a kiadott alaptermék életciklus-állapotát fogja importálni.</span><span class="sxs-lookup"><span data-stu-id="72c9f-139">When importing released product variants through a data entity, the product lifecycle state of the released product master will be imported.</span></span>   
 
## <a name="find-obsolete-products-and-products-variants"></a><span data-ttu-id="72c9f-140">Elavult termékek és termékváltozatok keresése</span><span class="sxs-lookup"><span data-stu-id="72c9f-140">Find obsolete products and products variants</span></span> 
 
<span data-ttu-id="72c9f-141">Lefuttatható egy elemzésszimuláció az elavult kiadott termékek vagy termékváltozatok felkutatására, és ezt követően frissíthető a termékéletciklus-állapotuk.</span><span class="sxs-lookup"><span data-stu-id="72c9f-141">You can run a simulation analysis to find the obsolete released products or product variants and then update their product lifecycle status.</span></span> <span data-ttu-id="72c9f-142">Az elavult termékek felkutatásához játssza le vagy olvassa el a következő feladat-útmutatót: **Elavult termékváltozatok keresése és termékéletciklus-állapot hozzárendelése**.</span><span class="sxs-lookup"><span data-stu-id="72c9f-142">To find obsolete products, play and read the task guide **Find obsolete product variants and assign a product lifecycle state**.</span></span> <span data-ttu-id="72c9f-143">Ez a feladat-útmutató bemutatja, hogyan lehet megkeresni az elavult kiadott termékeket vagy termékváltozatokat, és hogyan lehet termékéletciklus-állapotot társítani az elavult termékekhez.</span><span class="sxs-lookup"><span data-stu-id="72c9f-143">This task guide shows how to find obsolete released products or product variants and how to associate a product lifecycle state to the obsolete products.</span></span> <span data-ttu-id="72c9f-144">Azt is bemutatja, hogyan lehet megtekinteni a szimulációs eredményeket, és kiértékeli, hogy hány termékhez és termékváltozathoz lesz új termékéletciklus-állapot társítva, ha a frissítést szimuláció nélkül futtatjuk.</span><span class="sxs-lookup"><span data-stu-id="72c9f-144">It also shows hot to view the simulation results and assess how many products and product variants will be associated with a new product lifecycle state when running the update without simulation.</span></span>  
 
<span data-ttu-id="72c9f-145">Az elemzés szimulációs üzemmódban való futtatásával az elavultként azonosított termékek és termékváltozatok egy erre a célra szolgáló képernyőn jelennek meg, ahol egyszerűen ellenőrizhetők.</span><span class="sxs-lookup"><span data-stu-id="72c9f-145">By running the analysis in a simulation mode, the products and product variants identified as obsolete are displayed in a specific form, where they can easily be reviewed.</span></span> <span data-ttu-id="72c9f-146">Az elemzés tranzakciókat és alapadatokat keres azzal a céllal, hogy azonosítsa azokat a termékeket, amelyek iránt nincs igény egy változtatható időperióduson belül, és nincs igényt eredményező alapadat.</span><span class="sxs-lookup"><span data-stu-id="72c9f-146">The analysis searches for transactions and specific master data to identify products that have no demand within a variable period and no master data that can result in demand.</span></span> <span data-ttu-id="72c9f-147">Az elemzésből ki lehet zárni a beállítható időn belül újonnan kiadott termékeket.</span><span class="sxs-lookup"><span data-stu-id="72c9f-147">New released products within a variable period can be excluded from the analysis.</span></span> <span data-ttu-id="72c9f-148">Amikor az elemzésszimuláció visszaadja a várt eredményt, a felhasználó lefuttathatja az elemzést, és új termékéletciklus-állapotot állíthat be az összes, az elemzés által elavultként azonosított termékhez.</span><span class="sxs-lookup"><span data-stu-id="72c9f-148">When the analysis simulation returns the expected result, the user can run the analysis and set a new product lifecycle state to all products identified as obsolete by the analysis.</span></span>  
 
> [!NOTE]
> <span data-ttu-id="72c9f-149">Vegye figyelembe, hogy minden elemzést és frissítést ugyanazon a jogi személyen belül kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="72c9f-149">Note that all analysis and updates must be done within the same legal entity.</span></span>  
 
## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a><span data-ttu-id="72c9f-150">Feltételek a kiadott termékek vagy termékváltozatok kiválasztásához és frissítéséhez</span><span class="sxs-lookup"><span data-stu-id="72c9f-150">Criteria to select and update released products or product variants</span></span> 
 
<span data-ttu-id="72c9f-151">Használja a következő feltételeket a kiadott termékek vagy termékváltozatok kiválasztásához és frissítéséhez:</span><span class="sxs-lookup"><span data-stu-id="72c9f-151">Use the following criteria to select and update the released products and product variants:</span></span> 

-    <span data-ttu-id="72c9f-152">A termék vagy termékváltozat termékéletciklus-állapotának különböznie kell az új kívánt állapottól.</span><span class="sxs-lookup"><span data-stu-id="72c9f-152">The product lifecycle state of the product or product variant must be different from the new desired state.</span></span> 
-  <span data-ttu-id="72c9f-153">A termék vagy termékváltozat létrehozása bizonyos számú napja történt, annak a napszámnak az alapján, amelyet a kiválasztási párbeszédpanelen írt be.</span><span class="sxs-lookup"><span data-stu-id="72c9f-153">The product or product variant was created some days ago based on the number of days that you enter in the selection dialog box.</span></span> 
-  <span data-ttu-id="72c9f-154">Nincsenek nyitott termelési rendelések (= állapot < befejezett) a termékre vagy termékváltozatra nézve.</span><span class="sxs-lookup"><span data-stu-id="72c9f-154">There are no open production orders (= status < ended) for the product or product variant.</span></span> 
-  <span data-ttu-id="72c9f-155">Nincsenek nyitott készlettranzakciók (= állapotprobléma a ReservPhysical és QuotationIssue skálán, vagy állapotfogadás a Regisztrált és QuotationReceipt skálán) a termékre vagy a termékváltozatra.</span><span class="sxs-lookup"><span data-stu-id="72c9f-155">There are no open inventory transactions (= status issue ReservPhysical to QuotationIssue or status receipt Registrered to QuotationReceipt) for the product or product variant.</span></span> 
-  <span data-ttu-id="72c9f-156">Az utóbbi napokban nincsenek készlettranzakciók a termékre vagy termékváltozatra.</span><span class="sxs-lookup"><span data-stu-id="72c9f-156">There are no inventory transactions within the last number of days for the product or product variant.</span></span> 
-  <span data-ttu-id="72c9f-157">Nem áll fenn jövőbeli igény vagy ellátási előrejelzés a termékre vagy termékváltozatra.</span><span class="sxs-lookup"><span data-stu-id="72c9f-157">There is no future demand or supply forecast for the product or product variant.</span></span>  
-  <span data-ttu-id="72c9f-158">Nincs minimális készletszint beállítva a termékre vagy termékváltozatra a cikkfedezetben.</span><span class="sxs-lookup"><span data-stu-id="72c9f-158">No minimum stock level has been set in item coverage for the product or product variant.</span></span> 
-  <span data-ttu-id="72c9f-159">Nincs aktív fix mennyiségi kanbanszabály a termékre vagy termékváltozatra.</span><span class="sxs-lookup"><span data-stu-id="72c9f-159">No active fixed quantity kanban rule for the product or product variant.</span></span>  
-  <span data-ttu-id="72c9f-160">Nincs szervizrendeléssor a termékre vagy a termékváltozatra nézve.</span><span class="sxs-lookup"><span data-stu-id="72c9f-160">No service order line for the product or product variant.</span></span> 
-  <span data-ttu-id="72c9f-161">Nincs aktív vagy jövőbeli értékesítési vagy beszerzésiszerződés-sor a termékre vagy a termékváltozatra.</span><span class="sxs-lookup"><span data-stu-id="72c9f-161">No active or future sales or purchase agreement lines for the product or product variant.</span></span> 
-  <span data-ttu-id="72c9f-162">A termék vagy a termékváltozat nincs használatban egy olyan anyagjegyzékben, amely társítva van egy le nem járt, jóváhagyott, tervezéshez aktív anyagjegyzék-verzióhoz a termékre vagy a termékváltozatra nézve.</span><span class="sxs-lookup"><span data-stu-id="72c9f-162">The product or product variant is not used in a BOM that is associated with a non-expired approved BOM version for a product or variant that is active for planning.</span></span>

## <a name="related-topics"></a><span data-ttu-id="72c9f-163">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="72c9f-163">Related topics</span></span>

-  <span data-ttu-id="72c9f-164">Új termékéletciklus-állapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="72c9f-164">Create a new product lifecycle state</span></span>
-  <span data-ttu-id="72c9f-165">Alapértelmezett új termékéletciklus-állapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="72c9f-165">Create a default new product lifecycle state</span></span>
-  <span data-ttu-id="72c9f-166">Termékéletciklus-állapot hozzárendelése egy kiadott alaptermékhez</span><span class="sxs-lookup"><span data-stu-id="72c9f-166">Assign a product lifecycle state to a released product master</span></span>
-  <span data-ttu-id="72c9f-167">Termékéletciklus-állapot hozzárendelése egy kiadott termékhez</span><span class="sxs-lookup"><span data-stu-id="72c9f-167">Assign a product lifecycle state to a released product</span></span>
-  <span data-ttu-id="72c9f-168">Az elavult termékváltozatok megkeresése, és egy termékéletciklus-állapot hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="72c9f-168">Find obsolete product variants and assign a product lifecycle state</span></span>
-  <span data-ttu-id="72c9f-169">Termékéletciklus-állapot létrehozása a termékek kizárásához az alaptervezésből</span><span class="sxs-lookup"><span data-stu-id="72c9f-169">Create a product lifecycle state to exclude products from Master planning</span></span>

