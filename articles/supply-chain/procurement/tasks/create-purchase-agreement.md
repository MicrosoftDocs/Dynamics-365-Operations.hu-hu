---
title: Beszerzési szerződés létrehozása
description: Ez a témakör végigvezeti a beszerzési szerződés létrehozásán.
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1edfd4e56910376d0596eec5eff2af888f7dc98d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207738"
---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="4c898-103">Beszerzési szerződés létrehozása</span><span class="sxs-lookup"><span data-stu-id="4c898-103">Create a purchase agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4c898-104">Ez a témakör végigvezeti a beszerzési szerződés létrehozásán.</span><span class="sxs-lookup"><span data-stu-id="4c898-104">This topic guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="4c898-105">Ez általában egy beszerzési vezető által történik.</span><span class="sxs-lookup"><span data-stu-id="4c898-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="4c898-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="4c898-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="4c898-107">A kezdés előtt létre kell hozni a beszerzési szerződés osztályozásait.</span><span class="sxs-lookup"><span data-stu-id="4c898-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="4c898-108">Miután létrehozta a megállapodást, használhatja, amikor létrehoz egy beszerzési rendelést, és ez bemásolja a beszerzési szerződés feltételeit a megállapodás által érintett rendelés fejlécébe és soraiba.</span><span class="sxs-lookup"><span data-stu-id="4c898-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="4c898-109">Új beszerzési szerződés létrehozása</span><span class="sxs-lookup"><span data-stu-id="4c898-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="4c898-110">Ugorjon a **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Beszerzési szerződések > Beszerzési szerződések** elemre.</span><span class="sxs-lookup"><span data-stu-id="4c898-110">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase agreements > Purchase agreements**.</span></span>
2. <span data-ttu-id="4c898-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="4c898-111">Click **New**.</span></span>
3. <span data-ttu-id="4c898-112">A **Szállítói számla** mezőben válassza ki a legördülő menüt, majd a kívánt rekord sorát.</span><span class="sxs-lookup"><span data-stu-id="4c898-112">In the **Vendor account** field, select the drop-down menu and select the row of the desired record.</span></span>
4. <span data-ttu-id="4c898-113">A **Beszerzési szerződés osztályozása** mezőben válassza ki a legördülő menüt, majd a kívánt rekord sorát.</span><span class="sxs-lookup"><span data-stu-id="4c898-113">In the **Purchase agreement classification** field, select the drop-down menu and select the row of the desired record.</span></span>
5. <span data-ttu-id="4c898-114">Bontsa ki az **Általános** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="4c898-114">Expand the **General** FastTab.</span></span>
6. <span data-ttu-id="4c898-115">Adjon meg egy dátumot a **Lejárati dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4c898-115">In the **Expiration date** field, enter a date.</span></span>

    - <span data-ttu-id="4c898-116">Ez a lejárati dátum lesz az alapértelmezés az összes kötelezettségvállalási sorban, és meghatározza, mennyi ideig érvényesek a kötelezettségek.</span><span class="sxs-lookup"><span data-stu-id="4c898-116">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  

7. <span data-ttu-id="4c898-117">A **Dokumentum címe** mezőbe írja be a beszerzési szerződés nevét.</span><span class="sxs-lookup"><span data-stu-id="4c898-117">In the **Document title** field, type a name for your purchase agreement.</span></span>

    - <span data-ttu-id="4c898-118">Hagyja az **Alapértelmezett kötelezettségvállalás** mezőt **Termékmennyiségi kötelezettség** értéken (vagy módosítsa erre, ha nem ez az értéke).</span><span class="sxs-lookup"><span data-stu-id="4c898-118">Leave the **Default commitment** field set to **Product quantity commitment** (or change it if it's not set to this).</span></span>  
    - <span data-ttu-id="4c898-119">Az alapértelmezett kötelezettségvállalási érték határozza meg a megállapodási sorokban látható opciókat.</span><span class="sxs-lookup"><span data-stu-id="4c898-119">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="4c898-120">Ha új kötelezettségtípusra van szüksége a megállapodási sorok létrehozásakor, módosítsa az alapértelmezett kötelezettséget a fejlécben.</span><span class="sxs-lookup"><span data-stu-id="4c898-120">If you need a new commitment type when you're creating the agreement lines, you need to change the default commitment on the header.</span></span> <span data-ttu-id="4c898-121">A kötelezettségvállalásoknak 4 típusa van: **Termékmennyiségi kötelezettség** – egy adott mennyiségű termékre; **Termék értékére vonatkozó kötelezettség** – termékösszeg adott pénznemben; **Termék kategóriaértékére vonatkozó kötelezettség** – egy beszerzési kategóriában lévő konkrét összeg devizában, ahol az összeg katalóguscikkre vagy a katalóguson kívüli cikkre vonatkozhat; **Értékre vonatkozó kötelezettség** – adott pénznemben lévő összegre, amely bármely termékre vagy beszerzési kategóriára vonatkozhat.</span><span class="sxs-lookup"><span data-stu-id="4c898-121">There are 4 types of commitments: **Product quantity commitment** - for a specific quantity of a product; **Product value commitment** - for a specific currency amount of a product; **Product category value commitment** - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; **Value commitment** - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  

8. <span data-ttu-id="4c898-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4c898-122">Select **OK**.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="4c898-123">Kötelezettség hozzáadása</span><span class="sxs-lookup"><span data-stu-id="4c898-123">Add a commitment</span></span>
1. <span data-ttu-id="4c898-124">Válassza a **Sor hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4c898-124">Select **Add line**.</span></span>
2. <span data-ttu-id="4c898-125">A **Cikkszám** mezőben válassza ki a kívánt rekordot a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="4c898-125">In the **Item number** field, select the desired record from the drop-down menu.</span></span>
3. <span data-ttu-id="4c898-126">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4c898-126">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="4c898-127">Ez az a teljes mennyiség, amelyeket a megállapodás szerint beszerez a szállítótól.</span><span class="sxs-lookup"><span data-stu-id="4c898-127">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
4. <span data-ttu-id="4c898-128">Adjon meg egy számot az **Egységár** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4c898-128">In the **Unit price** field, enter a number.</span></span>
5. <span data-ttu-id="4c898-129">Bontsa ki a **Sorrészletek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4c898-129">Expand the **Line details** section.</span></span>
6. <span data-ttu-id="4c898-130">Állítsa a **Maximális kényszerítése** opciót **Igen**-re.</span><span class="sxs-lookup"><span data-stu-id="4c898-130">Set the **Max is enforced** option to **Yes**.</span></span> <span data-ttu-id="4c898-131">A **Maximum betartatása** beállítás korlátozza a kötelezettségvállalás használatát.</span><span class="sxs-lookup"><span data-stu-id="4c898-131">The **Max is enforced** option limits the use of the commitment.</span></span> <span data-ttu-id="4c898-132">Csak a **Mennyiség** mezőben megadott mennyiséget vásárolhatja meg az adott sorhoz.</span><span class="sxs-lookup"><span data-stu-id="4c898-132">You can only purchase up to the quantity that's specified in the **Quantity** field for the line.</span></span>  

## <a name="add-header-conditions"></a><span data-ttu-id="4c898-133">Fejlécben megadott feltételek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="4c898-133">Add header conditions</span></span>
1. <span data-ttu-id="4c898-134">A műveleti ablaktáblán válassza ki a **Beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="4c898-134">On the Action Pane, select **Options**.</span></span>
2. <span data-ttu-id="4c898-135">Válassza ki a **Nézetváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4c898-135">Select **Change view**.</span></span>
3. <span data-ttu-id="4c898-136">Válassza ki a **Fejlécnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="4c898-136">Select **Header view**.</span></span>
4. <span data-ttu-id="4c898-137">Bontsa ki a **Feltételek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4c898-137">Expand the **Terms** section.</span></span>
5. <span data-ttu-id="4c898-138">A **Fizetési mód** mezőben válassza ki a kívánt rekordot a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="4c898-138">In the **Method of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="4c898-139">Alapértelmezés szerint a szállítói számla fizetési feltételei láthatók itt.</span><span class="sxs-lookup"><span data-stu-id="4c898-139">The payment terms from the vendor account are shown here by default.</span></span>  
6. <span data-ttu-id="4c898-140">A **Szállítási mód** mezőben válassza ki a kívánt rekordot a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="4c898-140">In the **Mode of delivery** field, select the desired record in the drop-down menu.</span></span>
7. <span data-ttu-id="4c898-141">A **Szállítási feltételek** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4c898-141">In the **Delivery terms** field, select the drop-down button to open the lookup.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="4c898-142">Erősítse meg és aktiválja a megállapodást</span><span class="sxs-lookup"><span data-stu-id="4c898-142">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="4c898-143">A Művelet panelen kattintson a **Beszerzési szerződés** elemre.</span><span class="sxs-lookup"><span data-stu-id="4c898-143">On the Action Pane, select **Purchase agreement**.</span></span>
2. <span data-ttu-id="4c898-144">Válassza ki a **Visszaigazolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4c898-144">Select **Confirmation**.</span></span> <span data-ttu-id="4c898-145">Állítsa a **Szerződés megjelölése érvényesként** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="4c898-145">Set the **Mark agreement as effective** option to **Yes**.</span></span>  
3. <span data-ttu-id="4c898-146">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4c898-146">Select **OK**.</span></span>
4. <span data-ttu-id="4c898-147">A Művelet panelen kattintson a **Beszerzési szerződés** elemre.</span><span class="sxs-lookup"><span data-stu-id="4c898-147">On the Action Pane, select **Purchase agreement**.</span></span>
5. <span data-ttu-id="4c898-148">Válassza a **Beszerzésiszerződés-visszaigazolások** elemet.</span><span class="sxs-lookup"><span data-stu-id="4c898-148">Select **Purchase agreement confirmations**.</span></span> <span data-ttu-id="4c898-149">Az **Előnézet/nyomtatás** beállítás lehetővé teszi a beszerzési szerződéshez dokumentum létrehozását, amelyet kinyomtathat vagy elküldhet a szállítónak.</span><span class="sxs-lookup"><span data-stu-id="4c898-149">The **Preview/Print** option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="4c898-150">Ha később frissítési a szerződést, és ismételten megerősíti, mindkét verzió megjelenik itt.</span><span class="sxs-lookup"><span data-stu-id="4c898-150">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="4c898-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4c898-151">Close the page.</span></span>

