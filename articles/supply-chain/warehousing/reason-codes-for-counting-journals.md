---
title: Okkódok készletszámláláshoz
description: Ez a témakör ismerteti az okkódok beállítását számlálási feladatokhoz.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 6d71de53f5d24ecea03892790449c7a57c60eb55
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207301"
---
# <a name="reason-codes-for-inventory-counting"></a><span data-ttu-id="c927b-103">Okkódok készletszámláláshoz</span><span class="sxs-lookup"><span data-stu-id="c927b-103">Reason codes for inventory counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c927b-104">Az okkódok segítségével elemezheti a számlálási folyamat eredményeit és a folyamat során felmerülő esetleges eltéréseket.</span><span class="sxs-lookup"><span data-stu-id="c927b-104">Reason codes let you analyze the results of a counting process and any discrepancies that occur during that process.</span></span> <span data-ttu-id="c927b-105">Megadhatja a számlálás okait, például hogy eltört a raklap vagy a készletmintákon alapuló készletkiigazítás történt.</span><span class="sxs-lookup"><span data-stu-id="c927b-105">You can specify the reason for doing the count, such as a broken pallet or a stock adjustment that is based on inventory samples.</span></span>

## <a name="recommendation"></a><span data-ttu-id="c927b-106">Ajánlás</span><span class="sxs-lookup"><span data-stu-id="c927b-106">Recommendation</span></span>

<span data-ttu-id="c927b-107">Mielőtt beállítaná a rendszert, javasoljuk, hogy dolgozzon ki egy stratégiát az okokkódok kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="c927b-107">Before you set up the system, we recommend that you define a strategy for working with reason codes.</span></span> <span data-ttu-id="c927b-108">Próbáljon például válaszolni a következő kérdésekre:</span><span class="sxs-lookup"><span data-stu-id="c927b-108">For example, try to answer the following questions:</span></span>

- <span data-ttu-id="c927b-109">Legyenek az okkódok kötelezők a raktárak számára?</span><span class="sxs-lookup"><span data-stu-id="c927b-109">Should reason codes be mandatory on warehouses?</span></span>
- <span data-ttu-id="c927b-110">Legyenek az okkódok kötelezők vagy választhatók egyes cikkeknél?</span><span class="sxs-lookup"><span data-stu-id="c927b-110">Should reason codes be mandatory or optional on some items?</span></span>
- <span data-ttu-id="c927b-111">Hány okkódra van szükség?</span><span class="sxs-lookup"><span data-stu-id="c927b-111">How many reason codes do you require?</span></span>
- <span data-ttu-id="c927b-112">Hogyan használják a vonalkód-szkennerek felhasználói az okkódokat?</span><span class="sxs-lookup"><span data-stu-id="c927b-112">How should users of barcode scanners use reason codes?</span></span> <span data-ttu-id="c927b-113">Legyenek az okkódok előválasztottak, kötelezőek vagy nem szerkeszthetők?</span><span class="sxs-lookup"><span data-stu-id="c927b-113">Should the reason codes be preselected, mandatory, or not editable?</span></span>
- <span data-ttu-id="c927b-114">A raktári dolgozók különböző kódviselkedést igényelnek a mobil leolvasóknál?</span><span class="sxs-lookup"><span data-stu-id="c927b-114">Do warehouse workers require different reason code behavior on mobile scanners?</span></span> <span data-ttu-id="c927b-115">Ha a válasz igen, akkor több menüpontot hozhat létre, és hozzárendelheti azokat különböző emberekhez.</span><span class="sxs-lookup"><span data-stu-id="c927b-115">If the answer is yes, you can create more menu items and assign them to different people.</span></span>

## <a name="where-reason-codes-apply"></a><span data-ttu-id="c927b-116">Hol érvényesek az okkódok</span><span class="sxs-lookup"><span data-stu-id="c927b-116">Where reason codes apply</span></span>

<span data-ttu-id="c927b-117">Többféle okkód-szabályzatot hozhat létre, és minden okkód-szabályzatban két számlálási okkód szabályzatot adhat meg.</span><span class="sxs-lookup"><span data-stu-id="c927b-117">You can create multiple reason code policies, and each reason code policy can have two counting reason code policies.</span></span> <span data-ttu-id="c927b-118">A számlálási okkód szabályzatok használhatók a raktár vagy a cikkek szintjén.</span><span class="sxs-lookup"><span data-stu-id="c927b-118">The counting reason code policies can be used at the warehouse level or the item level.</span></span>

## <a name="set-up-reason-code-policies"></a><span data-ttu-id="c927b-119">Okkód-szabályzatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="c927b-119">Set up reason code policies</span></span>

1. <span data-ttu-id="c927b-120">Válassza a **Készletkezelés** \> **Beállítás** \> **Készlet** \> **Leltározási okkód irányelvei** elemet, és hozzon létre egy új okkód-irányelvet.</span><span class="sxs-lookup"><span data-stu-id="c927b-120">Select **Inventory management** \> **Setup** \> **Inventory** \> **Counting reason code policies**, and create a new reason code policy.</span></span>
2. <span data-ttu-id="c927b-121">A **Leltározási okkód típusa** mezőben a következők közül választhat **Kötelező** vagy **Választható** – ezzel adhatja meg, hogy az okkód kiválasztása kötelező vagy választható legyen-e a következő leltárnaplók egyikében:</span><span class="sxs-lookup"><span data-stu-id="c927b-121">In the **Counting reason code type** field, select either **Mandatory** or **Optional** to specify whether selection of a reason code should be an optional or mandatory action in one of the following counting journals:</span></span>

    - <span data-ttu-id="c927b-122">Ciklikus leltározás (mobileszköz)</span><span class="sxs-lookup"><span data-stu-id="c927b-122">Cycle Count (mobile device)</span></span>
    - <span data-ttu-id="c927b-123">Eseti leltározás (mobileszköz)</span><span class="sxs-lookup"><span data-stu-id="c927b-123">Spot Count (mobile device)</span></span>
    - <span data-ttu-id="c927b-124">Küszöbérték-leltározás (mobileszköz)</span><span class="sxs-lookup"><span data-stu-id="c927b-124">Threshold Count (mobile device)</span></span>
    - <span data-ttu-id="c927b-125">Igazítás be (mobileszköz)</span><span class="sxs-lookup"><span data-stu-id="c927b-125">Adjustment In (mobile device)</span></span>
    - <span data-ttu-id="c927b-126">Igazítás ki (mobileszköz)</span><span class="sxs-lookup"><span data-stu-id="c927b-126">Adjustment Out (mobile device)</span></span>
    - <span data-ttu-id="c927b-127">Leltárnapló (funkciógazdag ügyfél)</span><span class="sxs-lookup"><span data-stu-id="c927b-127">Counting Journal (rich client)</span></span>

<span data-ttu-id="c927b-128">Az egyes raktárakhoz és termékekhez is létrehozhat okkódokat.</span><span class="sxs-lookup"><span data-stu-id="c927b-128">You can also set up reason codes for individual warehouses and for products.</span></span> <span data-ttu-id="c927b-129">A termékek okkódjainak beállítása figyelmen kívül hagyhatja a raktárak beállítását.</span><span class="sxs-lookup"><span data-stu-id="c927b-129">The reason code setup for products can disregard the setup for warehouses.</span></span>

## <a name="mandatory-reason-codes"></a><span data-ttu-id="c927b-130">Kötelező okkódok</span><span class="sxs-lookup"><span data-stu-id="c927b-130">Mandatory reason codes</span></span>

<span data-ttu-id="c927b-131">Ha a **Kötelező** paraméter meg van adva a raktárak vagy cikkek okkódjainak konfigurációjában, a leltárnapló nem fejezhető be és zárható le, amíg okkód nincs megadva.</span><span class="sxs-lookup"><span data-stu-id="c927b-131">If the **Mandatory** parameter is set in the configuration of reason codes for warehouses or items, the counting journal can't be completed and closed until a reason code is provided.</span></span>

### <a name="set-up-reason-codes-for-warehouses"></a><span data-ttu-id="c927b-132">Okkódok beállítása raktárakhoz</span><span class="sxs-lookup"><span data-stu-id="c927b-132">Set up reason codes for warehouses</span></span>

1. <span data-ttu-id="c927b-133">Válassza a **Készletgazdálkodás** \> **Beállítás** \> **Készlet részletezése** \> **Raktárak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c927b-133">Select **Inventory Management** \> **Setup** \> **Inventory breakdown** \> **Warehouses**.</span></span>
2. <span data-ttu-id="c927b-134">A **Raktár** lapon a **Leltározási okkód irányelve** mezőben válassza ki az egyiket a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="c927b-134">On the **Warehouse** tab, in the **Counting reason code policy** field, select one of the following options:</span></span>

    - <span data-ttu-id="c927b-135">**Üres** – A cikkhez beállított paraméter használatos annak megállapítása, hogy a leltározási naplók kötelezőek-e a termékhez.</span><span class="sxs-lookup"><span data-stu-id="c927b-135">**Blank** – The parameter that is set up for the item is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="c927b-136">**Kötelező** – a raktárban a leltárnaplóknál minden esetben szükség van okkódra.</span><span class="sxs-lookup"><span data-stu-id="c927b-136">**Mandatory** – A reason code is always required on counting journals for the warehouse.</span></span>
    - <span data-ttu-id="c927b-137">**Választható** – a raktárban a leltárnaplóknál nincs minden esetben szükség okkódra.</span><span class="sxs-lookup"><span data-stu-id="c927b-137">**Optional** – A reason code isn't required on counting journals for the warehouse.</span></span>

### <a name="set-up-reason-codes-for-products"></a><span data-ttu-id="c927b-138">Okkódok beállítása termékekhez</span><span class="sxs-lookup"><span data-stu-id="c927b-138">Set up reason codes for products</span></span>

1. <span data-ttu-id="c927b-139">Válassza a **Termékinformációk kezelése** \> **Termékek** \> **Kiadott termékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c927b-139">Select **Product information management** \> **Products** \> **Released products**.</span></span>
2. <span data-ttu-id="c927b-140">A **Termék** lapon válassza a **Leltározási okkód irányelve** elemet, majd válassza ki az egyiket a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="c927b-140">On the **Product** tab, select **Counting reason code policy**, and then select one of the following options:</span></span>

    - <span data-ttu-id="c927b-141">**Üres** – A raktárhoz beállított paraméter használatos annak megállapítása, hogy a leltározási naplók kötelezőek-e a termékhez.</span><span class="sxs-lookup"><span data-stu-id="c927b-141">**Blank** – The parameter that is set up for the warehouse is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="c927b-142">**Kötelező** – a terméknél a leltárnaplóknál minden esetben szükség van okkódra.</span><span class="sxs-lookup"><span data-stu-id="c927b-142">**Mandatory** – A reason code is always required on counting journals for the product.</span></span> <span data-ttu-id="c927b-143">Ez a beállítás felülbírálja a raktár szintjén érvényes okkód-beállításokat.</span><span class="sxs-lookup"><span data-stu-id="c927b-143">This setting overrides any reason code setting at the warehouse level.</span></span>
    - <span data-ttu-id="c927b-144">**Választható** – a terméknél a leltárnaplóknál nincs minden esetben szükség okkódra.</span><span class="sxs-lookup"><span data-stu-id="c927b-144">**Optional** – A reason code isn't required on counting journals for the product.</span></span> <span data-ttu-id="c927b-145">Ez a beállítás felülbírálja a raktár szintjén érvényes okkód-beállításokat.</span><span class="sxs-lookup"><span data-stu-id="c927b-145">This setting overrides any reason code setting at the warehouse level.</span></span>

### <a name="use-reason-codes-in-counting-journals"></a><span data-ttu-id="c927b-146">Okkódok használata leltárnaplókban</span><span class="sxs-lookup"><span data-stu-id="c927b-146">Use reason codes in counting journals</span></span>

<span data-ttu-id="c927b-147">A leltárnaplóban az alábbi típusú leltározásokhoz adhat hozzá okkódokat:</span><span class="sxs-lookup"><span data-stu-id="c927b-147">In a counting journal, you can add reason codes for counts of the following types:</span></span>

- <span data-ttu-id="c927b-148">Ciklikus leltározás</span><span class="sxs-lookup"><span data-stu-id="c927b-148">Cycle Count</span></span>
- <span data-ttu-id="c927b-149">Eseti leltározás</span><span class="sxs-lookup"><span data-stu-id="c927b-149">Spot Count</span></span>
- <span data-ttu-id="c927b-150">Küszöbérték-leltározás</span><span class="sxs-lookup"><span data-stu-id="c927b-150">Threshold Count</span></span>
- <span data-ttu-id="c927b-151">Igazítás be</span><span class="sxs-lookup"><span data-stu-id="c927b-151">Adjustment In</span></span>
- <span data-ttu-id="c927b-152">Igazítás ki</span><span class="sxs-lookup"><span data-stu-id="c927b-152">Adjustment Out</span></span>

<span data-ttu-id="c927b-153">Az okkódok a **Leltárnapló** leltárnaplóknál a napló soraiba kerülnek hozzáadásra.</span><span class="sxs-lookup"><span data-stu-id="c927b-153">Reason codes are added to the journal lines in counting journals of the **Counting journal** type.</span></span>

1. <span data-ttu-id="c927b-154">Válassza a **Készletgazdálkodás** \> **Naplóbejegyzések** \> **Cikkleltár** \> **Leltár** elemet.</span><span class="sxs-lookup"><span data-stu-id="c927b-154">Select **Inventory management** \> **Journal entries** \> **Item counting** \> **Counting**.</span></span>
2. <span data-ttu-id="c927b-155">A leltárnapló sorainak részletei között a **Leltározási okkód** mezőben válasszon egy beállítást.</span><span class="sxs-lookup"><span data-stu-id="c927b-155">In the line details of the counting journal, in the **Counting reason code** field, select an option.</span></span>

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a><span data-ttu-id="c927b-156">A leltározási előzmények megtekintése a bejegyzett okkódok alapján</span><span class="sxs-lookup"><span data-stu-id="c927b-156">View the counting history as it's recorded by reason codes</span></span>

- <span data-ttu-id="c927b-157">Válassza a **Készletkezelés** \> **Lekérdezések és jelentések** \> **Leltározási előzmények** elemet, majd a a **Leltározási okkód** mezőben tekintse meg az okkódok formájában rögzített leltározási előzményeket.</span><span class="sxs-lookup"><span data-stu-id="c927b-157">Select **Inventory management** \> **Inquiries and reports** \> **Counting history**, and then, in the **Counting reason code** field, view the counting history that has been recorded through a reason code.</span></span>

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a><span data-ttu-id="c927b-158">Okkód használata mennyiség módosításához</span><span class="sxs-lookup"><span data-stu-id="c927b-158">Use a reason code for a quantity adjustment</span></span>

1. <span data-ttu-id="c927b-159">Az **Aktuális készlet** oldalon válassza a **Mennyiség módosítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c927b-159">On the **On-hand inventory** page, select **Adjust quantity**.</span></span> <span data-ttu-id="c927b-160">Többféleképpen megnyithatja az **Aktuális készlet** lapot.</span><span class="sxs-lookup"><span data-stu-id="c927b-160">You can open the **On-hand inventory** page in several ways.</span></span> <span data-ttu-id="c927b-161">Például válassza a **Készletkezelés** \> **Lekérdezések és jelentések** \> **Aktuális készlet** elemet.</span><span class="sxs-lookup"><span data-stu-id="c927b-161">For example, select **Inventory management** \> **Inquiries and reports** \> **On-hand inventory**.</span></span>
2. <span data-ttu-id="c927b-162">Válassza a **Mennyiség módosítása** elemet, majd a **Leltározási okkód** mezőben válasszon egy okkódot.</span><span class="sxs-lookup"><span data-stu-id="c927b-162">Select **Adjust quantity**, and then, in the **Counting reason code** field, select a reason code.</span></span>

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a><span data-ttu-id="c927b-163">Okkódok konfigurálása mobileszköz menüelemeihez</span><span class="sxs-lookup"><span data-stu-id="c927b-163">Configure reason codes for mobile device menu items</span></span>

<span data-ttu-id="c927b-164">Bármilyen típusú leltár okkódjait beállíthatja mobileszköz menüelemeihez.</span><span class="sxs-lookup"><span data-stu-id="c927b-164">You can configure reason codes for any type of count on a mobile device menu item.</span></span> <span data-ttu-id="c927b-165">A mobileszköz-menüpont konfigurációja a következő információkat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="c927b-165">The configuration of the mobile device menu item includes the following information:</span></span>

- <span data-ttu-id="c927b-166">Azt, hogy az okkód megjelenik-e a mobileszközön dolgozó számára leltározás közben.</span><span class="sxs-lookup"><span data-stu-id="c927b-166">Whether the reason code is shown to the mobile device worker during counting.</span></span>
- <span data-ttu-id="c927b-167">Az alapértelmezett okkódot, amely megjelenik a mobileszköz menüpontjában.</span><span class="sxs-lookup"><span data-stu-id="c927b-167">The default reason code that is shown on a mobile device menu item.</span></span>
- <span data-ttu-id="c927b-168">Azt, hogy a felhasználó szerkesztheti-e az okkódot.</span><span class="sxs-lookup"><span data-stu-id="c927b-168">Whether the user can edit the reason code.</span></span>

### <a name="set-up-reason-codes-on-a-mobile-device"></a><span data-ttu-id="c927b-169">Mobileszköz okkódjainak beállítása</span><span class="sxs-lookup"><span data-stu-id="c927b-169">Set up reason codes on a mobile device</span></span>

1. <span data-ttu-id="c927b-170">Válassza a **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Mobileszköz menüpontjai** pontot.</span><span class="sxs-lookup"><span data-stu-id="c927b-170">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="c927b-171">A **ciklikus leltár** lapon válassza a **Ciklikus leltározás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c927b-171">On the **Cycle count** tab, select **Cycle counting**.</span></span>
3. <span data-ttu-id="c927b-172">Az **Alapértelmezett leltározási okkód** mezőben állítsa be az alapértelmezett okkódot, amelyet rögzíteni kell a leltár készítésekor a mobileszköz-menüpont használatával.</span><span class="sxs-lookup"><span data-stu-id="c927b-172">In the **Default counting reason code** field, set the default reason code that should be recorded when counting is done by using the mobile device menu item.</span></span>
4. <span data-ttu-id="c927b-173">A **Leltározási okkód megjelenítése** mezőben válassza a **Sor** elemet, amelyben az okkód megjelenik az egyes különbözetet rögzítése után.</span><span class="sxs-lookup"><span data-stu-id="c927b-173">In the **Display counting reason code** field, select **Line** to show the reason code after each variance is recorded.</span></span> <span data-ttu-id="c927b-174">Másik lehetőségként válassza az **Elrejtés** elemet, ha az okkódot nem kell megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="c927b-174">Alternatively, select **Hide** if the reason code shouldn't be shown.</span></span>
5. <span data-ttu-id="c927b-175">Állítsa a **Leltározási okkód szerkesztése** lehetőséget vagy **Igen** vagy **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="c927b-175">Set the **Edit counting reason code** option to either **Yes** or **No**.</span></span> <span data-ttu-id="c927b-176">Ha ez a beállítás **Igen**, a dolgozó szerkesztheti az okkódot, amikor a leltár során megjelenik a mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="c927b-176">If you set this option to **Yes**, the worker can edit the reason code when it's shown on the mobile device during counting.</span></span>

> [!NOTE]
> <span data-ttu-id="c927b-177">A **Ciklikus leltározás** gomb engedélyezhető bármely mobileszköz-menüpontban, ahol leltározás végezhető.</span><span class="sxs-lookup"><span data-stu-id="c927b-177">The **Cycle counting** button can be enabled on any mobile device menu item where counting can be done.</span></span> <span data-ttu-id="c927b-178">Példa: menüelemek eseti leltározáshoz, felhasználó által irányított munkához és a rendszer által irányított munkához.</span><span class="sxs-lookup"><span data-stu-id="c927b-178">Example include the menu items for spot counts, user-directed work, and system-directed work.</span></span>

## <a name="cycle-count-approvals"></a><span data-ttu-id="c927b-179">Ciklikus leltári jóváhagyások</span><span class="sxs-lookup"><span data-stu-id="c927b-179">Cycle count approvals</span></span>

<span data-ttu-id="c927b-180">A leltár jóváhagyása előtt a felhasználó módosíthatja a leltárhoz társított okkódot.</span><span class="sxs-lookup"><span data-stu-id="c927b-180">Before a count is approved, the user can change the reason code that is associated with the count.</span></span> <span data-ttu-id="c927b-181">A leltár jóváhagyásakor az okkód bekerül a leltárnapló soraiba.</span><span class="sxs-lookup"><span data-stu-id="c927b-181">When the count is approved, the reason code is entered on the counting journal lines.</span></span>

### <a name="modify-cycle-count-approvals"></a><span data-ttu-id="c927b-182">Ciklikus leltári jóváhagyások módosítása</span><span class="sxs-lookup"><span data-stu-id="c927b-182">Modify cycle count approvals</span></span>

1. <span data-ttu-id="c927b-183">Válassza a **Raktárkezelés** \> **Ciklikus leltározás** \> **Ciklikus leltározási munka ellenőrzése függőben** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c927b-183">Select **Warehouse management** \> **Cycle counting** \> **Cycle count work pending review**.</span></span>
2. <span data-ttu-id="c927b-184">Válassza a **Ciklikus leltározás** elemet, majd az **Okkód** mezőben válasszon egy új okkódot.</span><span class="sxs-lookup"><span data-stu-id="c927b-184">Select **Cycle counting**, and then, in the **Reason code** field, select a new reason code.</span></span>

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a><span data-ttu-id="c927b-185">A mobileszköz-menüpont módosítása igazítás be és igazítás ki folyamathoz</span><span class="sxs-lookup"><span data-stu-id="c927b-185">Modify the mobile device menu item for Adjustment in and Adjustment out</span></span>

1. <span data-ttu-id="c927b-186">Válassza a **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Mobileszköz menüpontjai** elemet, majd válassza ki a **Igazítás be és ki** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c927b-186">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**, and then select **Adjustment in and out**.</span></span>
2. <span data-ttu-id="c927b-187">A **Meglévő munka használata** lehetőséget állítsa **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="c927b-187">Set the **Use existing work** option to **No**.</span></span>
3. <span data-ttu-id="c927b-188">A **Munka-létrehozási folyamat** mezőben válassza az **Igazítás be** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c927b-188">In the **Work creation process** field, select **Adjustment in**.</span></span>

<span data-ttu-id="c927b-189">A következő mezők hozzáadódnak a mobileszköz menüelemeihez, amikor az **Igazítás be** vagy **Igazítás ki** van kiválasztva a munka-létrehozási folyamat során:</span><span class="sxs-lookup"><span data-stu-id="c927b-189">The following fields will be added to the mobile device menu item when **Adjustment in** or **Adjustment out** is selected during the work creation process:</span></span>

- <span data-ttu-id="c927b-190">Alapértelmezett leltározási okkód</span><span class="sxs-lookup"><span data-stu-id="c927b-190">Default counting reason code</span></span>
- <span data-ttu-id="c927b-191">Leltározási okkód megjelenítése</span><span class="sxs-lookup"><span data-stu-id="c927b-191">Display counting reason code</span></span>
- <span data-ttu-id="c927b-192">Leltározási okkód szerkesztése</span><span class="sxs-lookup"><span data-stu-id="c927b-192">Edit counting reason code</span></span>
