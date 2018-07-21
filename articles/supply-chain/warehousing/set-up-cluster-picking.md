---
title: "Fürt beállítása"
description: "Ez a témakör leírja a fürtkitárolás beállítását, és a cikk jóváhagyásának alkalmazását a fürtkitárolással."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 52750321588d69483439873861682636c13a4936
ms.contentlocale: hu-hu
ms.lasthandoff: 07/21/2018

---

[!include[banner](../includes/banner.md)]

# <a name="set-up-cluster-picking"></a><span data-ttu-id="6a461-103">Fürt beállítása</span><span class="sxs-lookup"><span data-stu-id="6a461-103">Set up cluster picking</span></span>

<span data-ttu-id="6a461-104">Ez a témakör ismerteti, hogyan lehet engedélyezni, hogy azok tárolhat cikkek több munka rendeléshez egy helyről egy időben a mobileszközök munka fürtök, a kitárolási csoport használandó dolgozók.</span><span class="sxs-lookup"><span data-stu-id="6a461-104">This topic describes how to enable workers to use their mobile devices to group picking work into clusters, so that they can pick items from a single location for multiple work orders at the same time.</span></span> <span data-ttu-id="6a461-105">Ezt nevezik *fürtkitárolás*.</span><span class="sxs-lookup"><span data-stu-id="6a461-105">This is called *cluster picking*.</span></span>

## <a name="about-cluster-picking"></a><span data-ttu-id="6a461-106">Fürt kitárolása</span><span class="sxs-lookup"><span data-stu-id="6a461-106">About cluster picking</span></span>

<span data-ttu-id="6a461-107">Miután munkarendelések ki vannak adva a raktárba, a dolgozó használható mobileszköz rendelje hozzá a rendelések a fürthöz.</span><span class="sxs-lookup"><span data-stu-id="6a461-107">After work orders are released to the warehouse, the worker can use a mobile device to assign the orders to a cluster.</span></span> <span data-ttu-id="6a461-108">A fürt szervezi a dolgozó a kitárolási munka.</span><span class="sxs-lookup"><span data-stu-id="6a461-108">The cluster will organize the picking work for the worker.</span></span> <span data-ttu-id="6a461-109">A Munkarendelés hozzá van rendelve egy fürtből, amikor a dolgozó kell használni a fürt kitárolási a kitárolási munka a rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="6a461-109">When a work order is assigned to a cluster, the worker must use cluster picking to perform the picking work for the order.</span></span> <span data-ttu-id="6a461-110">A dolgozó egyéb kitárolási módokkal nem használható.</span><span class="sxs-lookup"><span data-stu-id="6a461-110">The worker cannot use other picking methods.</span></span> <span data-ttu-id="6a461-111">A Munkarendelés van rendelve egy fürt tévedésből, ha a dolgozó kell a fürt felbontása és ezután hozza létre újból.</span><span class="sxs-lookup"><span data-stu-id="6a461-111">If a work order is assigned to a cluster by mistake, the worker must break the cluster and then re-create it.</span></span>

<span data-ttu-id="6a461-112">Szükség esetén dolgozó lehet átadni a fürt egy másik dolgozó.</span><span class="sxs-lookup"><span data-stu-id="6a461-112">If needed, a worker can pass a cluster to another worker.</span></span> <span data-ttu-id="6a461-113">Ekkor a fürt állapotát megfelelt.</span><span class="sxs-lookup"><span data-stu-id="6a461-113">This changes the cluster status to Passed.</span></span> <span data-ttu-id="6a461-114">A dolgozó használja a mobileszköz annak jelzésére, hogy a kitárolási és betárolási csökkenés munka befejezése, ha a szállítmány vagy rakomány meg kell erősíteni őket a Dynamics 365 for Finance and Operations ügyfél.</span><span class="sxs-lookup"><span data-stu-id="6a461-114">When the worker uses a mobile device to indicate that the picking and put away work is completed, the shipment or load must be confirmed in the Dynamics 365 for Finance and Operations client.</span></span>

## <a name="set-up-cluster-picking"></a><span data-ttu-id="6a461-115">Fürt beállítása</span><span class="sxs-lookup"><span data-stu-id="6a461-115">Set up cluster picking</span></span>

<span data-ttu-id="6a461-116">Ahhoz, hogy a fürtkitárolás, be kell állítania a következőket:</span><span class="sxs-lookup"><span data-stu-id="6a461-116">To enable cluster picking, you must set up the following:</span></span>

-   <span data-ttu-id="6a461-117">**Fürtprofilok** – Adja meg, hogy automatikus legyen-e a fürtazonosítók előállítása, adja meg a használandó beosztások számát, azt, hogy mikor kell eltörni a fürtöket, és hogyan kell sorrendbe állítani és ellenőrizni a kitárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="6a461-117">**Cluster profiles** – Specify whether to automatically generate cluster IDs, the number of positions to use, when to break clusters, and how to sequence and verify the picking work.</span></span>

-   <span data-ttu-id="6a461-118">**Munkasablonok** – A kitárolási munka fürthöz kitároláshoz létrehozásával meghatározása.</span><span class="sxs-lookup"><span data-stu-id="6a461-118">**Work templates** – Define how to create the picking work for cluster picking.</span></span>

-   <span data-ttu-id="6a461-119">**Helyirányelvek** – Adja meg, honnan kell kitárolni a cikkeket, és hová kell rakni őket.</span><span class="sxs-lookup"><span data-stu-id="6a461-119">**Location directives** – Specify where to pick items from, and where to put them.</span></span>

-   <span data-ttu-id="6a461-120">**Mobileszköz menüelemei** – A folyamatban lévő munkát, hogy fürtkitárolás által használandó mobileszköz menü elemeinek beállítása.</span><span class="sxs-lookup"><span data-stu-id="6a461-120">**Mobile device menu items** – Configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="6a461-121">Hozzá kell adnia majd menüelem mobileszköz menü, hogy a mobileszközök jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6a461-121">You must then add the menu item to a mobile device menu so that it is displayed on mobile devices.</span></span>

-   <span data-ttu-id="6a461-122">**Raktárkezelési paraméterek** – Adja meg a fürtök azonosítóinak létrehozásához használandó számsorozat.</span><span class="sxs-lookup"><span data-stu-id="6a461-122">**Warehouse management parameters** – Specify the number sequence to use if you want to generate identifiers for clusters.</span></span>

## <a name="set-up-a-cluster-profile"></a><span data-ttu-id="6a461-123">Nyugtaprofil beállítása</span><span class="sxs-lookup"><span data-stu-id="6a461-123">Set up a cluster profile</span></span>

<span data-ttu-id="6a461-124">Az okkód beállításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="6a461-124">To set up a cluster profile, follow these steps:</span></span>

1.  <span data-ttu-id="6a461-125">Kattintson a **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Fürtprofilok** elemre.</span><span class="sxs-lookup"><span data-stu-id="6a461-125">Click **Warehouse management** \> **Setup** \> **Mobile device** \> **Cluster profiles**.</span></span>

2.  <span data-ttu-id="6a461-126">Új mérő létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="6a461-126">Click **New** to create a new profile.</span></span>

3.  <span data-ttu-id="6a461-127">Kattintson a **Fürt létrehozása** elemre, és a **Fürtrendezés** alatt kattintson az **Új** elemre a fürt rendezési kritériumának beállításához.</span><span class="sxs-lookup"><span data-stu-id="6a461-127">Click **Create cluster** and, under **Cluster sorting**, click **New** to set up the sorting criteria for the cluster.</span></span> <span data-ttu-id="6a461-128">A rendezési kritérium sorrendjét, amelyben a dolgozó a kitárolási munka hajt végre.</span><span class="sxs-lookup"><span data-stu-id="6a461-128">The sorting criteria control the order in which the worker will perform the picking work.</span></span> <span data-ttu-id="6a461-129">Tetszőleges számú intervallumot lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="6a461-129">You can add as many criteria as needed.</span></span>

4.  <span data-ttu-id="6a461-130">A **Sorszám** mezőben adjon meg egy számot, amely meghatározza a rendezési feltételek feldolgozási sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="6a461-130">In the **Sequence number** field, enter a number to define the order in which the sorting criteria are processed.</span></span>

5.  <span data-ttu-id="6a461-131">Az a **mezőnév** mezőben, válassza ki a mezőt, amely meghatározza a rendezést.</span><span class="sxs-lookup"><span data-stu-id="6a461-131">In the **Field name** field, select the field that will determine the sorting.</span></span> <span data-ttu-id="6a461-132">Ha például bejelöli a **WMSLocationId** mezőben, a munka hely szerint lesznek rendezve.</span><span class="sxs-lookup"><span data-stu-id="6a461-132">For example, if you select the **WMSLocationId** field, the work will be sorted by location.</span></span>

6.  <span data-ttu-id="6a461-133">A **Rendezés** mezőben az alábbi beállítások közül választhat:</span><span class="sxs-lookup"><span data-stu-id="6a461-133">In the **Sorting** field, select one of the following options.</span></span>

| <span data-ttu-id="6a461-134">**Lehetőség**</span><span class="sxs-lookup"><span data-stu-id="6a461-134">**Option**</span></span>     | <span data-ttu-id="6a461-135">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="6a461-135">**Description**</span></span>                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="6a461-136">**Növekvő**</span><span class="sxs-lookup"><span data-stu-id="6a461-136">**Ascending**</span></span>  | <span data-ttu-id="6a461-137">A kitárolási munka van a rendezési feltételek alapján növekvő sorrendben sorrendbe állítva.</span><span class="sxs-lookup"><span data-stu-id="6a461-137">Picking work is sequenced in ascending order based on the sorting criteria.</span></span> <span data-ttu-id="6a461-138">Ha például a **WMSLocationId** feltételeit, és a hely azonosítók rendezési mező 1, 2, 3, 4, akkor program kivesz 4 helyről először.</span><span class="sxs-lookup"><span data-stu-id="6a461-138">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 4 first.</span></span> |
| <span data-ttu-id="6a461-139">**Csökkenő**</span><span class="sxs-lookup"><span data-stu-id="6a461-139">**Descending**</span></span> | <span data-ttu-id="6a461-140">A kitárolási munka van a rendezési feltételek alapján növekvő sorrendben sorrendbe állítva.</span><span class="sxs-lookup"><span data-stu-id="6a461-140">Picking work is sequenced in descending order based on the sorting criteria.</span></span> <span data-ttu-id="6a461-141">Ha például a **WMSLocationId** feltételeit, és a hely azonosítók rendezési mező 1, 2, 3, 4, akkor program kivesz 1 helyről először.</span><span class="sxs-lookup"><span data-stu-id="6a461-141">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 1 first.</span></span> |

## <a name="item-confirmation"></a><span data-ttu-id="6a461-142">Cikkmegerősítés</span><span class="sxs-lookup"><span data-stu-id="6a461-142">Item confirmation</span></span>

<span data-ttu-id="6a461-143">Ha a fürtkiválasztást alkalmazzák, a cikkek megerősítése döntő fontosságú a fürtökhöz hozzáadott cikkek ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="6a461-143">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="6a461-144">A fürtkiválasztás folyamán ellenőrizheti a fürtkiválasztás cikkeit.</span><span class="sxs-lookup"><span data-stu-id="6a461-144">You can verify items in cluster picking during the cluster picking process.</span></span> <span data-ttu-id="6a461-145">A beállítás a termékvonalkód-beállításon alapul.</span><span class="sxs-lookup"><span data-stu-id="6a461-145">The setup is based on the product bar code setup.</span></span>

### <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="6a461-146">Cikkellenőrzés beállítása a fürtkiválasztásnál</span><span class="sxs-lookup"><span data-stu-id="6a461-146">Set up item verification with cluster picking</span></span>

1.  <span data-ttu-id="6a461-147">A mobileszköz menüpontjában nyissa meg a munkamegerősítés beállítási képernyőjét: **Raktárkezelés** \> **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Mobileszköz menüpontjai**.</span><span class="sxs-lookup"><span data-stu-id="6a461-147">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** \> **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>

2.  <span data-ttu-id="6a461-148">A mobileszköz menüpontjából nyissa meg a **Munkamegerősítés beállítását**.</span><span class="sxs-lookup"><span data-stu-id="6a461-148">From the mobile device menu item, open **Work confirmation setup**.</span></span> <span data-ttu-id="6a461-149">A **Termékmegerősítés** beállítás lehetővé teszi, hogy a mobileszközről ellenőrizze a készlet minden elemét a beolvasáskor.</span><span class="sxs-lookup"><span data-stu-id="6a461-149">The **Product confirmation** option allows you to verify each piece of inventory from the mobile device when scanned.</span></span>

