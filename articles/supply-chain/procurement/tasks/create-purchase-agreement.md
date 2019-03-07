---
title: Beszerzési szerződés létrehozása
description: Ez az eljárás végigvezeti a beszerzési szerződés létrehozásán.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b317f0a0fc8f198bad9501f325557ac2a4796989
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "338613"
---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="cb4f9-103">Beszerzési szerződés létrehozása</span><span class="sxs-lookup"><span data-stu-id="cb4f9-103">Create a purchase agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cb4f9-104">Ez az eljárás végigvezeti a beszerzési szerződés létrehozásán.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-104">This procedure guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="cb4f9-105">Ez általában egy beszerzési vezető által történik.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="cb4f9-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="cb4f9-107">A kezdés előtt létre kell hozni a beszerzési szerződés osztályozásait.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="cb4f9-108">Miután létrehozta a megállapodást, használhatja, amikor létrehoz egy beszerzési rendelést, és ez bemásolja a beszerzési szerződés feltételeit a megállapodás által érintett rendelés fejlécébe és soraiba.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="cb4f9-109">Új beszerzési szerződés létrehozása</span><span class="sxs-lookup"><span data-stu-id="cb4f9-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="cb4f9-110">Ugorjon a Beszerzés és vásárlás > Beszerzési szerződések > Beseszerzési szerződések gombra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-110">Go to Procurement and sourcing > Purchase agreements > Purchase agreements.</span></span>
2. <span data-ttu-id="cb4f9-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-111">Click New.</span></span>
3. <span data-ttu-id="cb4f9-112">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="cb4f9-113">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="cb4f9-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="cb4f9-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-114">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="cb4f9-115">A Beszerzési szerződés osztályozása mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-115">In the Purchase agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="cb4f9-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="cb4f9-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="cb4f9-118">Bontsa ki az Általános szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-118">Expand the General section.</span></span>
10. <span data-ttu-id="cb4f9-119">Adjon meg egy dátumot a Lejárati dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-119">In the Expiration date field, enter a date.</span></span>
    * <span data-ttu-id="cb4f9-120">Ez a lejárati dátum lesz az alapértelmezés az összes kötelezettségvállalási sorban, és meghatározza, mennyi ideig érvényesek a kötelezettségek.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-120">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  
11. <span data-ttu-id="cb4f9-121">A Dokumentum címe mezőbe írja be a beszerzési szerződés nevét.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-121">In the Document title field, type a name for your purchase agreement.</span></span>
    * <span data-ttu-id="cb4f9-122">Hagyja az Alapértelmezett kötelezettségvállalás mezőt Termékmennyiségi kötelezettség értéken (vagy módosítsa erre, ha nem ez az értéke).</span><span class="sxs-lookup"><span data-stu-id="cb4f9-122">Leave the Default commitment field set to Product quantity commitment (or change it if it’s not set to this).</span></span>  
    * <span data-ttu-id="cb4f9-123">Az alapértelmezett kötelezettségvállalási érték határozza meg a megállapodási sorokban látható opciókat.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-123">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="cb4f9-124">Ha új kötelezettségtípusra van szüksége a megállapodási sorok létrehozásakor, módosítsa az alapértelmezett kötelezettséget a fejlécben.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-124">If you need a new commitment type when you’re creating the agreement lines, you need to change the default commitment on the header.</span></span>  <span data-ttu-id="cb4f9-125">A kötelezettségvállalásoknak 4 típusa van: Termékmennyiségi kötelezettség – egy adott mennyiségű termékre; Termék értékére vonatkozó kötelezettség – termékösszeg adott pénznemben; Termék kategóriaértékére vonatkozó kötelezettség – egy beszerzési kategóriában lévő konkrét összeg devizában, ahol az összeg katalóguscikkre vagy a katalóguson kívüli cikkre vonatkozhat; Értékre vonatkozó kötelezettség – adott pénznemben lévő összegre, amely bármely termékre vagy beszerzési kategóriára vonatkozhat.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-125">There are 4 types of commitments: Product quantity commitment - for a specific quantity of a product; Product value commitment - for a specific currency amount of a product; Product category value commitment - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; Value commitment - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  
12. <span data-ttu-id="cb4f9-126">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-126">Click OK.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="cb4f9-127">Kötelezettség hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cb4f9-127">Add a commitment</span></span>
1. <span data-ttu-id="cb4f9-128">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-128">Click Add line.</span></span>
2. <span data-ttu-id="cb4f9-129">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="cb4f9-130">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-130">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="cb4f9-131">Jelölje ki a terméket, amelyhez hozzá szeretné adni a kötelezettségvállalást.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-131">Select the product you want to add a commitment for.</span></span>
5. <span data-ttu-id="cb4f9-132">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-132">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="cb4f9-133">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-133">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="cb4f9-134">Ez az a teljes mennyiség, amelyeket a megállapodás szerint beszerez a szállítótól.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-134">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
7. <span data-ttu-id="cb4f9-135">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-135">In the Unit price field, enter a number.</span></span>
8. <span data-ttu-id="cb4f9-136">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-136">Expand the Line details section.</span></span>
9. <span data-ttu-id="cb4f9-137">Állítsa a Maximális kényszerítése opciót Igen-re.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-137">Set the Max is enforced option to Yes.</span></span>
    * <span data-ttu-id="cb4f9-138">A Maximum betartatása beállítás korlátozza a kötelezettségvállalás használatát.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-138">The Max is enforced option limits the use of the commitment.</span></span> <span data-ttu-id="cb4f9-139">Csak a Mennyiség mezőben megadott mennyiséget vásárolhatja meg az adott sorhoz.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-139">You can only purchase up to the quantity that's specified in the Quantity field for the line.</span></span>  
10. <span data-ttu-id="cb4f9-140">Csukja össze a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-140">Collapse the Line details section.</span></span>

## <a name="add-header-conditions"></a><span data-ttu-id="cb4f9-141">Fejlécben megadott feltételek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cb4f9-141">Add header conditions</span></span>
1. <span data-ttu-id="cb4f9-142">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-142">On the Action Pane, click Options.</span></span>
2. <span data-ttu-id="cb4f9-143">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-143">Click Change view.</span></span>
3. <span data-ttu-id="cb4f9-144">Kattintson a Fejlécnézet gombra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-144">Click Header view.</span></span>
4. <span data-ttu-id="cb4f9-145">Bontsa ki a Feltételek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-145">Expand the Terms section.</span></span>
5. <span data-ttu-id="cb4f9-146">A Fizetési mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-146">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="cb4f9-147">Alapértelmezés szerint a szállítói számla fizetési feltételei láthatók itt.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-147">The payment terms from the vendor account are shown here by default.</span></span>       
6. <span data-ttu-id="cb4f9-148">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-148">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="cb4f9-149">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-149">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="cb4f9-150">A Kiszállítási mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-150">In the Mode of delivery field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="cb4f9-151">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-151">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="cb4f9-152">A Szállítási feltételek mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-152">In the Delivery terms field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="cb4f9-153">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-153">In the list, click the link in the selected row.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="cb4f9-154">Erősítse meg és aktiválja a megállapodást</span><span class="sxs-lookup"><span data-stu-id="cb4f9-154">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="cb4f9-155">A Művelet panelen kattintson a Beszerzési szerződés elemre.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-155">On the Action Pane, click Purchase agreement.</span></span>
2. <span data-ttu-id="cb4f9-156">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-156">Click Confirmation.</span></span>
    * <span data-ttu-id="cb4f9-157">Állítsa a Szerződés megjelölése érvényesként beállítást Igen értékre.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-157">Set the Mark agreement as effective option to Yes.</span></span>  
3. <span data-ttu-id="cb4f9-158">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-158">Click OK.</span></span>
4. <span data-ttu-id="cb4f9-159">A Művelet panelen kattintson a Beszerzési szerződés elemre.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-159">On the Action Pane, click Purchase agreement.</span></span>
5. <span data-ttu-id="cb4f9-160">Kattintson a Beszerzési szerződés-visszaigazolásokra.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-160">Click Purchase agreement confirmations.</span></span>
    * <span data-ttu-id="cb4f9-161">Az Előnézet/nyomtatás beállítás lehetővé teszi a beszerzési szerződéshez dokumentum létrehozását, amelyet kinyomtathat vagy elküldhet a szállítónak.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-161">The Preview/Print option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="cb4f9-162">Ha később frissítési a szerződést, és ismételten megerősíti, mindkét verzió megjelenik itt.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-162">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="cb4f9-163">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-163">Close the page.</span></span>

