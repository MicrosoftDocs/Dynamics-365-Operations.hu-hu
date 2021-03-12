---
title: Rakományok összeállítása és szállítása – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a rakományok összeállítását és szállítását végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
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
ms.openlocfilehash: f49a91afe9281f912d6d3579ac8e52cb1d8e5b5d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994029"
---
# <a name="troubleshoot-load-building-and-shipments"></a><span data-ttu-id="4e55f-103">Rakományok összeállítása és szállítása – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="4e55f-103">Troubleshoot load building and shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4e55f-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a rakományok összeállítását és szállítását végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="4e55f-104">This topic describes how to fix common issues that you might encounter while you work with load building and shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a><span data-ttu-id="4e55f-105">A következő hibaüzenet jelenik meg: „Nem hozhat létre terheléssort ehhez a rendelési sorhoz, mert érvénytelen készletdimenziókat tartalmaz...”</span><span class="sxs-lookup"><span data-stu-id="4e55f-105">I receive the following error message: "You can't create a load line for this order line because it contains inventory dimensions that are invalid..."</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e55f-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="4e55f-106">Issue description</span></span>

<span data-ttu-id="4e55f-107">A következő hibaüzenet jelenik meg, amikor visszáruértékesítési rendelést próbál kiadni a raktárba:</span><span class="sxs-lookup"><span data-stu-id="4e55f-107">You receive the following error message when you try to release a return sales order to the warehouse:</span></span>

> <span data-ttu-id="4e55f-108">Nem hozhat létre terheléssort ehhez a rendelési sorhoz, mert érvénytelen készletdimenziókat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="4e55f-108">You can't create a load line for this order line because it contains inventory dimensions that are invalid.</span></span> <span data-ttu-id="4e55f-109">Nem hivatkozhat olyan készletdimenziókra, amelyek a helydimenzió alatt találhatók a foglalási hierarchiában.</span><span class="sxs-lookup"><span data-stu-id="4e55f-109">You can't reference inventory dimensions that are located below the location dimension in the reservation hierarchy.</span></span> <span data-ttu-id="4e55f-110">Távolítsa el az érvénytelen dimenziókat a rendelési sorból.</span><span class="sxs-lookup"><span data-stu-id="4e55f-110">Remove the invalid dimensions from the order line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e55f-111">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4e55f-111">Issue resolution</span></span>

<span data-ttu-id="4e55f-112">Sajnos a termék nem támogatja a terhelés feldolgozását az értékesítési visszárufolyamatnál.</span><span class="sxs-lookup"><span data-stu-id="4e55f-112">Unfortunately, the product doesn't support load processing for a sales return process.</span></span> <span data-ttu-id="4e55f-113">Ezért a visszáruértékesítési rendelést nem adhatja ki a raktárba.</span><span class="sxs-lookup"><span data-stu-id="4e55f-113">Therefore, you can't release the return sales order to the warehouse.</span></span>

<span data-ttu-id="4e55f-114">A rendeléstranzakciókon nem hivatkozhat olyan készletdimenziókra, amelyek a **Helydimenzió** alatt találhatók a foglalási hierarchiában.</span><span class="sxs-lookup"><span data-stu-id="4e55f-114">On sales order transactions, you can't reference inventory dimensions that are located below the **Location** dimension in the reservation hierarchy.</span></span> <span data-ttu-id="4e55f-115">Az a megoldás, hogy távolítsa el az érvénytelen dimenziókat a rendelési sorból.</span><span class="sxs-lookup"><span data-stu-id="4e55f-115">The resolution is to remove the invalid dimensions from the order line.</span></span>

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a><span data-ttu-id="4e55f-116">A következő hibaüzenet jelenik meg: „Az egyik sor már be van töltve.</span><span class="sxs-lookup"><span data-stu-id="4e55f-116">I receive the following error message: "One of the lines is already on a load.</span></span> <span data-ttu-id="4e55f-117">Nem lehet kiadni a raktárba.”</span><span class="sxs-lookup"><span data-stu-id="4e55f-117">Unable to release to warehouse."</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e55f-118">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="4e55f-118">Issue description</span></span>

<span data-ttu-id="4e55f-119">Ha manuálisan hoz létre rakományokat, vagy úgy állítja be a folyamatot, hogy a rakományok már az értékesítésrendelési sor bevitele előtt létrejönnek, akkor azt feltételezi a rendszer, hogy a későbbi kiadás manuálisan történik, és a rakományból származó útvonal és minősítés lesz használva.</span><span class="sxs-lookup"><span data-stu-id="4e55f-119">If you manually create loads, or if you set up the process so that loads are already created before sales order line entry occurs, the assumption is that the subsequent release will be done manually, and that the route and rating from the load will be used.</span></span>

<span data-ttu-id="4e55f-120">Egy másik lehetséges forgatókönyv, hogy automatikus kiadást próbál végezni a raktárba, de a hullámfolyamat nem tud munkát létrehozni.</span><span class="sxs-lookup"><span data-stu-id="4e55f-120">In another possible scenario, you're trying to do an automatic release to the warehouse, but the wave process failed to create work.</span></span> <span data-ttu-id="4e55f-121">Ezért egy nyitott szállítmány vagy rakomány továbbra is létrejön.</span><span class="sxs-lookup"><span data-stu-id="4e55f-121">Therefore, an open shipment or load is still created.</span></span> <span data-ttu-id="4e55f-122">Ez a nyitott szállítmány vagy betöltés letiltja a rendelés automatikus kiadására irányuló későbbi kísérleteket, amíg nem törli a nyitott szállítmányt vagy betöltést, vagy manuálisan fel nem dolgozza a hullámot.</span><span class="sxs-lookup"><span data-stu-id="4e55f-122">This open shipment or load then blocks subsequent attempts to automatically release the order until you either delete the open shipment or load, or manually reprocess the wave.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e55f-123">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4e55f-123">Issue resolution</span></span>

<span data-ttu-id="4e55f-124">Az értékesítési rendelés lapról kiadhatja, vagy az automatikus kiadást eszközölhet a kiadás értékesítési rendelés lapról, csakis akkor, ha nincs rakomány a raktárba történő kiadás előtt.</span><span class="sxs-lookup"><span data-stu-id="4e55f-124">You can release from the sales order page, or automatic release can be done from the release sales order page, only if no load exists before the release to the warehouse.</span></span> <span data-ttu-id="4e55f-125">A rakomány automatikusan létrejön a hullám feldolgozása után.</span><span class="sxs-lookup"><span data-stu-id="4e55f-125">The load will automatically be created after the wave is processed.</span></span>

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a><span data-ttu-id="4e55f-126">A következő hibaüzenet jelenik meg: „A szállítólevél helyesbítése nem dolgozható fel.</span><span class="sxs-lookup"><span data-stu-id="4e55f-126">I receive the following error message: "The delivery note correction can't be processed.</span></span> <span data-ttu-id="4e55f-127">A szállítólevél csak olyan cikkeket tartalmaz, amelyekre raktárkezelési folyamatok vonatkoznak, mivel ezeket a Szállítólevél helyesbítése nem támogatja."</span><span class="sxs-lookup"><span data-stu-id="4e55f-127">The delivery note only contains items that are subject to warehouse management processes, as these are not supported by Delivery Note correction."</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e55f-128">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="4e55f-128">Issue description</span></span>

<span data-ttu-id="4e55f-129">A szállítólevél kiadása után nem vonhatja vissza, mert a **Mégse** gomb nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="4e55f-129">After you post a delivery note, you can't cancel it, because the **Cancel** button is unavailable.</span></span> <span data-ttu-id="4e55f-130">A szállítólevél nem helyesbíthető.</span><span class="sxs-lookup"><span data-stu-id="4e55f-130">You also can't correct the delivery note.</span></span> <span data-ttu-id="4e55f-131">Ha megpróbálja, ez a hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="4e55f-131">If you try, you receive this error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e55f-132">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4e55f-132">Issue resolution</span></span>

<span data-ttu-id="4e55f-133">A speciális raktárkezeléshez (WMS) engedélyezett cikkek könyvelt szállítólevélének helyesbítéséhez a könyvelést a rakományból kell kiadnia, nem pedig közvetlenül a rendelésből.</span><span class="sxs-lookup"><span data-stu-id="4e55f-133">To correct posted packing slips for items that are enabled for advanced warehouse management (WMS), you must do the posting from the load, not directly from the order.</span></span>

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a><span data-ttu-id="4e55f-134">Hogyan hozhatok létre munkát a kimenő rakományokból és nem a hullámokból?</span><span class="sxs-lookup"><span data-stu-id="4e55f-134">How can I create work from outbound loads instead of waves?</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e55f-135">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="4e55f-135">Issue description</span></span>

<span data-ttu-id="4e55f-136">Itt van egy módja, hogyan reprodukálja ezt a problémát.</span><span class="sxs-lookup"><span data-stu-id="4e55f-136">Here is one way to reproduce this issue.</span></span>

1. <span data-ttu-id="4e55f-137">Hozzon létre értékesítési vagy átmozgatási rendelést kimenő rakomány létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4e55f-137">Create an outbound load by using a sales order or transfer order.</span></span>
2. <span data-ttu-id="4e55f-138">A rakomány kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="4e55f-138">Release the load to the warehouse.</span></span>
3. <span data-ttu-id="4e55f-139">Figyelje meg, hogy még nem jött létre kitárolási munka.</span><span class="sxs-lookup"><span data-stu-id="4e55f-139">Notice that no picking work has yet been generated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e55f-140">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4e55f-140">Issue resolution</span></span>

<span data-ttu-id="4e55f-141">Ha a munkát azonnal létre kell hozni a rakomány kiadásakor, ennek megfelelően kell konfigurálnia a hullámsablont.</span><span class="sxs-lookup"><span data-stu-id="4e55f-141">If work must be generated immediately when the load is released, you must configure the wave template accordingly.</span></span> <span data-ttu-id="4e55f-142">A hullámsablonon állítsa a következő beállításokat *Igen* értékre:</span><span class="sxs-lookup"><span data-stu-id="4e55f-142">On the wave template, set the following options to *Yes*:</span></span>

- <span data-ttu-id="4e55f-143">Hullámlétrehozás automatizálása</span><span class="sxs-lookup"><span data-stu-id="4e55f-143">Automate wave creation</span></span>
- <span data-ttu-id="4e55f-144">Hullám feldolgozása a raktárba történő kiadáskor</span><span class="sxs-lookup"><span data-stu-id="4e55f-144">Process wave at release to warehouse</span></span>
- <span data-ttu-id="4e55f-145">Hullámkiadás automatizálása</span><span class="sxs-lookup"><span data-stu-id="4e55f-145">Automate wave release</span></span>

## <a name="i-cant-re-release-a-partially-shipped-load"></a><span data-ttu-id="4e55f-146">Nem tudok újra kiadni egy részlegesen szállított rakományt.</span><span class="sxs-lookup"><span data-stu-id="4e55f-146">I can't re-release a partially shipped load.</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e55f-147">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="4e55f-147">Issue description</span></span>

<span data-ttu-id="4e55f-148">Nem adhat ki részlegesen szállított rakomány a raktárba.</span><span class="sxs-lookup"><span data-stu-id="4e55f-148">You can't release a partially shipped load to the warehouse.</span></span> <span data-ttu-id="4e55f-149">Amikor elvégzi a kiadást a raktárba, megjelenik egy „Művelet befejezve” üzenet, de nem történik semmi, és nem jön létre munka a fennmaradó mennyiséghez.</span><span class="sxs-lookup"><span data-stu-id="4e55f-149">When you do the release to the warehouse, an "Operation complete" message appears, but nothing happens, and no work is created for the remaining quantity.</span></span> <span data-ttu-id="4e55f-150">Ez a probléma akkor fordul elő, ha a szállítási rakomány funkciót használja, és hiányos a foglalás.</span><span class="sxs-lookup"><span data-stu-id="4e55f-150">This issue occurs when you use transport load functionality and there is an incomplete reservation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e55f-151">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4e55f-151">Issue resolution</span></span>

<span data-ttu-id="4e55f-152">A [KB 470069 számú probléma](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) („A részlegesen szállított rakományok újrahullámosíthatók és újra feldolgozhatók”) [a 10.0.15 kiadásban](../get-started/whats-new-scm-10-0-15.md) lett kijavítva.</span><span class="sxs-lookup"><span data-stu-id="4e55f-152">[KB issue 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Partially shipped loads can be re-waved and re-processed") is fixed in [release 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span></span>
