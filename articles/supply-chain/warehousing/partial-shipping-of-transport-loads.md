---
title: Szállítási rakomány részleges szállítása
description: Ez a témakör bemutatja, hogyan lehet szállítási rakományt részben szállítani és elhalasztani a szállítmányhoz tartozó kapacitás tervezését.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 68a3d175e89e89d0909b140863b1aa61a184fce6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963285"
---
# <a name="partial-shipment-of-a-transport-load"></a><span data-ttu-id="b76cd-103">Szállítási rakomány részleges szállítása</span><span class="sxs-lookup"><span data-stu-id="b76cd-103">Partial shipment of a transport load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b76cd-104">Szállítási rakományok részleges szállításának beállításával lehet kezelni szállítmányokat akkor, ha a kapacitást nem lehet meghatározni mindaddig, amíg az összes értékesítési sor be nem került a szállítmányba.</span><span class="sxs-lookup"><span data-stu-id="b76cd-104">By setting up partial shipment of loads, you can handle loads where the capacity can't be determined until all the sales lines have been added to a load.</span></span> <span data-ttu-id="b76cd-105">A folyamat így majd akkor zárható le, ha ismert a raklapok pontos száma.</span><span class="sxs-lookup"><span data-stu-id="b76cd-105">The process can then be finalized when the exact pallet count is known.</span></span> <span data-ttu-id="b76cd-106">Így nem kell eldönteni, melyik raklapok kerüljenek mely szállítmányba, addig a pillanatig, amíg a szállítmányt fizikailag kirakodják az előkészített készletből.</span><span class="sxs-lookup"><span data-stu-id="b76cd-106">Therefore, you don't have to decide which pallets will be assigned to which transport until the moment when a transport is being physically loaded out of the staged inventory.</span></span>

<span data-ttu-id="b76cd-107">Ez a funkció alternatívát kínál a merevebb szerkezet követéséhez, amelynél meg kell határozni, hogy melyik raklapot kell hozzárendelni melyik szállítmányhoz, mielőtt a kitárolási munkát vagy a betöltési munkát létre lehetne hozni.</span><span class="sxs-lookup"><span data-stu-id="b76cd-107">This feature offers an alternative to the enforcement of a more rigid structure, where you must determine which pallets will be assigned to which transport before picking work or loading work can be created.</span></span> <span data-ttu-id="b76cd-108">Ehelyett a felhasználók beállíthatják az egyes rakományok részleges szállítmány megerősítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b76cd-108">Instead, users can configure individual loads for a partial shipment confirmation.</span></span> <span data-ttu-id="b76cd-109">Ezután e rakományoknál sor kerülhet a szállítási berakodásra.</span><span class="sxs-lookup"><span data-stu-id="b76cd-109">The transport loading processes for those loads can then occur.</span></span> <span data-ttu-id="b76cd-110">Így a szállítástervezési részleg anélkül tervezhet rakományokat, hogy figyelembe kellene venni az egyes szállítások kapacitását.</span><span class="sxs-lookup"><span data-stu-id="b76cd-110">Therefore, the transportation planning department can plan loads without having to consider the capacity of individual transports.</span></span>

<span data-ttu-id="b76cd-111">A berakodás időpontjában a dolgozók új szállítási terhelést határozhatnak meg, amelybe a raklap betölthető.</span><span class="sxs-lookup"><span data-stu-id="b76cd-111">At the time of loading, workers can define a new transport load that a pallet can be loaded to.</span></span> <span data-ttu-id="b76cd-112">Azt is megtehetik, hogy meglévő szállítási rakományt azonosítanak.</span><span class="sxs-lookup"><span data-stu-id="b76cd-112">Alternatively, they can identify an existing transport load.</span></span> <span data-ttu-id="b76cd-113">Ez az adat mobileszközön keresztül rögzíthető.</span><span class="sxs-lookup"><span data-stu-id="b76cd-113">This data can be recorded via a mobile device.</span></span> <span data-ttu-id="b76cd-114">Ezért számos raktáros betölthet készletet ugyanabból a rakományból vagy különböző rakományokból azonos targoncára.</span><span class="sxs-lookup"><span data-stu-id="b76cd-114">Therefore, several warehouse workers can load inventory from the same loads or different loads onto the same truck.</span></span> <span data-ttu-id="b76cd-115">A rakományok ezután részben vagy egészben szállíthatók.</span><span class="sxs-lookup"><span data-stu-id="b76cd-115">The loads can then be fully or partially shipped.</span></span>

> [!NOTE] 
> <span data-ttu-id="b76cd-116">Készlet rakományból adott szállítási rakományba való betöltésére munkát kell létrehozni munkasablonban található betöltési osztály használatával.</span><span class="sxs-lookup"><span data-stu-id="b76cd-116">In order to load inventory from a load to a specific transport load and partially ship the load, work must be generated by using a loading class in a work template.</span></span> <span data-ttu-id="b76cd-117">A szokásos **kitárolási** típusú kitárolási munka nem tölthető be szállítási rakományba, például teherautóba.</span><span class="sxs-lookup"><span data-stu-id="b76cd-117">Ordinary picking work of the **Picking** type can't be loaded to a transport load such as a truck.</span></span>

## <a name="set-up-transport-loads-for-partial-shipment"></a><span data-ttu-id="b76cd-118">Szállítási rakományok beállítása részleges szállításra</span><span class="sxs-lookup"><span data-stu-id="b76cd-118">Set up transport loads for partial shipment</span></span>

<span data-ttu-id="b76cd-119">A rakományok részleges szállítására szolgáló beállítás a következő két eljárásból áll.</span><span class="sxs-lookup"><span data-stu-id="b76cd-119">The setup for partial shipment of loads consists of the following two procedures.</span></span>

### <a name="set-the-loading-strategy"></a><span data-ttu-id="b76cd-120">A berakodási stratégia beállítása</span><span class="sxs-lookup"><span data-stu-id="b76cd-120">Set the loading strategy</span></span>

<span data-ttu-id="b76cd-121">A berakodási stratégia beállításával engedélyeznie kell a részleges berakodást.</span><span class="sxs-lookup"><span data-stu-id="b76cd-121">You must enable partial loading by setting the loading strategy.</span></span> <span data-ttu-id="b76cd-122">A berakodási stratégiát rakomány létrehozása után lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="b76cd-122">You can set the loading strategy after you've created a load.</span></span>

1. <span data-ttu-id="b76cd-123">Válassza a **Raktárkezelés** \> **Rakományok** \> **Minden rakomány** elemet.</span><span class="sxs-lookup"><span data-stu-id="b76cd-123">Select **Warehouse management** \> **Loads** \> **All loads**.</span></span>
2. <span data-ttu-id="b76cd-124">Válasszon ki egy rakományt, majd kattintson a **Fejléc** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b76cd-124">Select a load, and then click **Header**.</span></span>
3. <span data-ttu-id="b76cd-125">A **Berakodási stratégia** mezőben válassza a **Részleges rakomány indítása engedélyezett** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b76cd-125">In the **Loading strategy** field, select **Partial load shipping allowed**.</span></span>

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a><span data-ttu-id="b76cd-126">Hozzon létre menüpontot szállítási rakományok berakodásához</span><span class="sxs-lookup"><span data-stu-id="b76cd-126">Create a menu item for loading of transport loads</span></span>

<span data-ttu-id="b76cd-127">Létre kell hoznia egy új menüelemet, amely engedélyezi a szállítási rakományok berakodását.</span><span class="sxs-lookup"><span data-stu-id="b76cd-127">You must create a new menu item that enables transport loads to be loaded.</span></span> <span data-ttu-id="b76cd-128">A szállítási rakomány lehetővé teszi a munkasorok csoportosítását egy vagy több rakományból.</span><span class="sxs-lookup"><span data-stu-id="b76cd-128">A transport load lets you group work lines from one load or multiple loads.</span></span> <span data-ttu-id="b76cd-129">Minden, a szállítási rakományhoz hozzáadott elem ezután elszállítható mobil leolvasó használatával.</span><span class="sxs-lookup"><span data-stu-id="b76cd-129">Everything that is added to the transport load can then be shipped by using a mobile scanner.</span></span>

1. <span data-ttu-id="b76cd-130">Válassza a **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Mobileszköz menüpontjai** pontot.</span><span class="sxs-lookup"><span data-stu-id="b76cd-130">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="b76cd-131">Válassza az **Új** elemet, majd a **Mód** mezőben válassza a **Munka** elemet.</span><span class="sxs-lookup"><span data-stu-id="b76cd-131">Select **New**, and then, in the **Mode** field, select **Work**.</span></span>
3. <span data-ttu-id="b76cd-132">A **Meglévő munka használata** lehetőséget állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="b76cd-132">Set the **Use existing work** option to **Yes**.</span></span>
4. <span data-ttu-id="b76cd-133">Az **Általános** lapon az **Irányítja** mezőben válassza a **Szállítási berakodás** elemet.</span><span class="sxs-lookup"><span data-stu-id="b76cd-133">On the **General** tab, in the **Directed by** field, select **Transport loading**.</span></span>
5. <span data-ttu-id="b76cd-134">A szállítmány mobil képolvasón való megerősítéséhez az **Engedélyezett szállítási visszaigazolás típusa** mezőben válassza a **Szállítási rakomány** elemet.</span><span class="sxs-lookup"><span data-stu-id="b76cd-134">To enable shipment confirmation on a mobile scanner, in the **Allowed ship confirmation type** field, select **Transport load**.</span></span>

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a><span data-ttu-id="b76cd-135">Az ügyféltől érkező szállítási rakományok szállításának visszaigazolása</span><span class="sxs-lookup"><span data-stu-id="b76cd-135">Confirm shipment of a transport load from the client</span></span>

<span data-ttu-id="b76cd-136">A beállítás segítségével megerősítheti a teljes rakományt vagy részleges rakományt tartalmazó szállítmányok szállításának megerősítését.</span><span class="sxs-lookup"><span data-stu-id="b76cd-136">This setup lets you confirm a transport load that includes a full load or a partially loaded load to be shipped.</span></span>

1. <span data-ttu-id="b76cd-137">Válassza a **Raktárkezelés** \> **Rakományok** \> **Szállítási rakományok** elemet.</span><span class="sxs-lookup"><span data-stu-id="b76cd-137">Select **Warehouse management** \> **Loads** \> **Transport loads**.</span></span>
2. <span data-ttu-id="b76cd-138">A műveleti ablaktábla **Indítás és fogadás** lapján lévő **Megerősítés** csoportban válassza a **Szállítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="b76cd-138">On the Action Pane, on the **Ship and receive** tab, in the **Confirm** group, select **Transport**.</span></span>
