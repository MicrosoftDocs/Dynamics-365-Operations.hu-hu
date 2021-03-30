---
title: Kitárolás és csomagolás – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben kitárol és csomagol a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 01e33b63e09a035f5243bd57faf53b522737c987
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223242"
---
# <a name="troubleshoot-picking-and-packing"></a><span data-ttu-id="bb032-103">Kitárolás és csomagolás – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="bb032-103">Troubleshoot picking and packing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bb032-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben kitárol és csomagol a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="bb032-104">This topic describes how to fix common issues that you might encounter while you pick and pack in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a><span data-ttu-id="bb032-105">A következő hibaüzenet jelenik meg: „A dimenzió helye nem hagyható üresen, ha a dimenzió sorozatszáma be van állítva.”</span><span class="sxs-lookup"><span data-stu-id="bb032-105">I receive the following error message: "Dimension location can't be left blank if dimension serial number is set."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb032-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb032-106">Issue description</span></span>

<span data-ttu-id="bb032-107">Ez a hibaüzenet akkor jelenik meg, ha egy sorozatszámos cikkhez olyan raktárat hoz létre, amely engedélyezve van a speciális raktárkezelésnél (WMS), majd a munka befejezése után megpróbálja megerősíteni a szállítmányt.</span><span class="sxs-lookup"><span data-stu-id="bb032-107">You receive this error message if you create a transfer order for a serial item by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb032-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb032-108">Issue resolution</span></span>

<span data-ttu-id="bb032-109">Az **Alapértelmezett bevételezési hely** mező üres a raktár tranzitraktár „érkezési” raktárában.</span><span class="sxs-lookup"><span data-stu-id="bb032-109">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="bb032-110">A probléma megoldásához adjon meg egy alapértelmezett bevételezési helyet a tranzitraktárban.</span><span class="sxs-lookup"><span data-stu-id="bb032-110">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="bb032-111">Győződjön meg arról, hogy ez a hely azonosítótábla-vezérelt.</span><span class="sxs-lookup"><span data-stu-id="bb032-111">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a><span data-ttu-id="bb032-112">A következő hibaüzenet jelenik meg: „Érvénytelen azonosítótábla”.</span><span class="sxs-lookup"><span data-stu-id="bb032-112">I receive the following error message: "Invalid license plate."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb032-113">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb032-113">Issue description</span></span>

<span data-ttu-id="bb032-114">Ez a hibaüzenet jelenik meg a raktári alkalmazásban, amikor beolvas egy azonosítót.</span><span class="sxs-lookup"><span data-stu-id="bb032-114">You receive this error message in the warehouse app when you scan a license plate ID.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb032-115">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb032-115">Issue resolution</span></span>

<span data-ttu-id="bb032-116">Győződjön meg arról, hogy az azonosítótábla-azonosító szerepel az azonosítótáblák táblázatában, és hogy az azonosítótáblán lévő cikkek és mennyiségek elérhetők (más szóval nincsenek zárolva).</span><span class="sxs-lookup"><span data-stu-id="bb032-116">Make sure that the license plate ID exists in the license plates table, and that the items and quantities on the license plate are available (in other words, they aren't blocked).</span></span>

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a><span data-ttu-id="bb032-117">A következő hibaüzenet jelenik meg: „A „Szállítmány súlya” (=-%1) mező csak pozitív számokat tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="bb032-117">I receive the following error message: "Field 'Load weight'(=-%1) can only contain positive numbers.</span></span> <span data-ttu-id="bb032-118">A frissítés meg lett szakítva.”</span><span class="sxs-lookup"><span data-stu-id="bb032-118">Update has been canceled."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb032-119">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb032-119">Issue description</span></span>

<span data-ttu-id="bb032-120">Ez a hibaüzenet akkor jelenik meg, ha a munka csomagolási helyekről átmeneti helyekre, illetve az átmeneti helyekről a dokkolóhelyekre történő feldolgozáskor van egy nyitott munka.</span><span class="sxs-lookup"><span data-stu-id="bb032-120">You receive this error message if there is open work when you process work from packing locations to staging locations, or from staging locations to dock locations.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb032-121">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb032-121">Issue resolution</span></span>

<span data-ttu-id="bb032-122">A probléma megoldásához menjen a **Rendszerfelügyelet \> Időszakos feladatok \> Adatbázis \> Konzisztencia ellenőrzése** lehetőségre, majd futtassa a **Raktári rakománysúly konzisztencia ellenőrzése** folyamatot.</span><span class="sxs-lookup"><span data-stu-id="bb032-122">To fix this issue, go to **System administration \> Periodic tasks \> Database \> Consistency check**, and run the process for **Warehouse load weight consistency check**.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="bb032-123">A következő hibaüzenet jelenik meg: „A mennyiség nem érvényes az %1 egységre”.</span><span class="sxs-lookup"><span data-stu-id="bb032-123">I receive the following error message: "The quantity is not valid for unit %1."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb032-124">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb032-124">Issue description</span></span>

<span data-ttu-id="bb032-125">Ez a hibaüzenet akkor jelenik meg, amikor több köteg között próbál *kitárolásokat szétosztani*.</span><span class="sxs-lookup"><span data-stu-id="bb032-125">You receive this error message when you try to perform a *split pick* across multiple batches.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb032-126">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb032-126">Issue resolution</span></span>

<span data-ttu-id="bb032-127">A raktári dolgozónak a *Rövid kitárolási* folyamatot kell használnia a raktározási alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="bb032-127">The warehouse worker must use the *Short picking* process in the warehouse app.</span></span> <span data-ttu-id="bb032-128">Ha több köteget próbál kiválasztani ugyanarról a helyről, használhatja a raktári alkalmazásban a **Teljes** lehetőséget is.</span><span class="sxs-lookup"><span data-stu-id="bb032-128">If you're trying to pick multiple batches from the same location, you can also use the **Full** option in the warehouse app.</span></span>

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a><span data-ttu-id="bb032-129">Nem tudom áthelyezni a készletet olyan helyre, amely azonosítótábla-vezérelt.</span><span class="sxs-lookup"><span data-stu-id="bb032-129">I can't move inventory to a location that is license plate–controlled.</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb032-130">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb032-130">Issue description</span></span>

<span data-ttu-id="bb032-131">A kitárolt mennyiségek nem csökkenthetők a rakományon.</span><span class="sxs-lookup"><span data-stu-id="bb032-131">You can't reduce picked quantities on a load.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb032-132">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb032-132">Issue resolution</span></span>

<span data-ttu-id="bb032-133">A régebbi verziókban a kitárolt mennyiségek nem csökkenthetők a rakományon.</span><span class="sxs-lookup"><span data-stu-id="bb032-133">In earlier versions, you can't reduce picked quantities on a load.</span></span> <span data-ttu-id="bb032-134">Most azonban már visszatárolhatja az azonosítótábla-vezérelt helyre.</span><span class="sxs-lookup"><span data-stu-id="bb032-134">However, you can now unpick to a license plate–controlled location.</span></span> <span data-ttu-id="bb032-135">A kitárolt mennyiség csökkentése lapon meg kell adnia a **Hely** értéket és a rakomány sor **Azonosítótábla** értékét a **Csökkentett kitárolt mennyiség** oldalon.</span><span class="sxs-lookup"><span data-stu-id="bb032-135">You must specify both a **Location** value and a **License plate** value for the load line on the **Reduce picked quantity** page.</span></span>

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a><span data-ttu-id="bb032-136">Nyomtathatok szállítólevelet vagy csomagolási tartalmat raktáronként?</span><span class="sxs-lookup"><span data-stu-id="bb032-136">Can I print a delivery note or packing content by warehouse?</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb032-137">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb032-137">Issue description</span></span>

<span data-ttu-id="bb032-138">Szállítólevelet vagy csomagolási tartalmat szeretne nyomtatni raktár vagy hely szerint a **Munkavizsgálati sablonsor frissítés** lapon.</span><span class="sxs-lookup"><span data-stu-id="bb032-138">You want to print a delivery note or packing content by warehouse or site on the **Work audit template line update** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb032-139">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb032-139">Issue resolution</span></span>

<span data-ttu-id="bb032-140">Ha a nyomtatáskezelési beállításokkal nyomtat egy dokumentumot, korlátozza a hatókört (hely/raktár) a Nyomtatáskezelés segítségével, ne a **Nyomtatási beállítások szerkesztése** lehetőséget használja a **Munkanaplózási sablonsor frissítési** lapon.</span><span class="sxs-lookup"><span data-stu-id="bb032-140">When you print a document by using Print management settings, limit the scope (site/warehouse) through Print management instead of by selecting **Edit print settings** on the **Work audit template line update** page.</span></span>

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a><span data-ttu-id="bb032-141">Nem tudom törölni a szállítólevelet, miután ki lett adva egy értékesítési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="bb032-141">I can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb032-142">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb032-142">Issue description</span></span>

<span data-ttu-id="bb032-143">Ha a WMS-hez engedélyezve vannak a kitárolási és szállítási folyamatok, akkor nem vonhatja vissza a szállítólevelet, miután azt az értékesítési rendelésből kiadta.</span><span class="sxs-lookup"><span data-stu-id="bb032-143">When picking and shipping processes are enabled for WMS, you can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb032-144">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb032-144">Issue resolution</span></span>

<span data-ttu-id="bb032-145">A WMS-hez engedélyezett cikkek könyvelt szállítólevélének helyesbítéséhez a könyvelést a rakományból kell kiadnia, nem pedig közvetlenül a rendelésből.</span><span class="sxs-lookup"><span data-stu-id="bb032-145">To correct posted packing slips for items that are enabled for WMS, the posting must occur from the load, not from the order.</span></span> <span data-ttu-id="bb032-146">A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás.</span><span class="sxs-lookup"><span data-stu-id="bb032-146">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="bb032-147">A raktárkezelési folyamatokon keresztül kitárolt és szállított értékesítési rendelés általában a rakományból vagy a szállítmányból és magából az értékesítési rendelésbizonylatból frissíthető.</span><span class="sxs-lookup"><span data-stu-id="bb032-147">In general, a sales order that has been picked and shipped through warehouse management processes can be packing slip–updated from the load or shipment and the sales order document itself.</span></span> <span data-ttu-id="bb032-148">Ha azonban az értékesítési rendelés bizonylatából frissíti az értékesítési rendelést, a csomagjegyzék sztornírozása még mindig nem végezhető el a rakományból vagy értékesítési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="bb032-148">However, if you packing slip–update the sales order from the sales order document, packing slip reversal still can't be done from the load or sales order.</span></span> <span data-ttu-id="bb032-149">Ezért azt javasoljuk, hogy használja a szállítólevél kiadást a rakományból.</span><span class="sxs-lookup"><span data-stu-id="bb032-149">Therefore, we recommend that you use the packing slip posting from the load.</span></span> <span data-ttu-id="bb032-150">Ebben az esetben a betöltésből elvégzendő sztornírozás engedélyezve lesz.</span><span class="sxs-lookup"><span data-stu-id="bb032-150">In this case, the reversal that must be done from the load will be enabled.</span></span>

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a><span data-ttu-id="bb032-151">A következő hibaüzenet jelenik meg: „A fürthöz nincs elegendő munka.”</span><span class="sxs-lookup"><span data-stu-id="bb032-151">I receive the following error message: "Not enough work can be found for cluster."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb032-152">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb032-152">Issue description</span></span>

<span data-ttu-id="bb032-153">A *Rendszer által irányított fürtkitárolás* folyamat használatakor, ha olyan fürtprofilt állít be, amelyben például 10 pozíció tárolható ki, a folyamat a tervek szerint működik, ha elegendő munka áll rendelkezésre a 10 pozíció kitárolásához.</span><span class="sxs-lookup"><span data-stu-id="bb032-153">When you use the *System directed cluster picking* process, if you configure a cluster profile where, for example, 10 positions can be picked, the process works as planned when there is enough work to pick to 10 positions.</span></span> <span data-ttu-id="bb032-154">Ha azonban csak nyolc pozíciót lehet kitárolni, akkor ez a hibaüzenet jelenik meg, mert nincs elég munka egy fürthöz.</span><span class="sxs-lookup"><span data-stu-id="bb032-154">However, if there are only eight positions to pick, you receive this error message, because there isn't enough work for one cluster.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb032-155">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb032-155">Issue resolution</span></span>

<span data-ttu-id="bb032-156">A probléma megoldásához szerkesztse a fürtprofilt, és állítsa a **Pozíciók aktiválása** lehetőséget *Nem* értékre.</span><span class="sxs-lookup"><span data-stu-id="bb032-156">To fix this issue, edit the cluster profile, and set the **Activate positions** option to *No*.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]