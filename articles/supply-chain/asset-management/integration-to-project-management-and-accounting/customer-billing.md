---
title: Vevő által birtokolt eszközök karbantartási számlája
description: Ez a témakör bemutatja, hogy hogyan lehet létrehozni, feldolgozni és számlázni a vevők eszközeivel kapcsolatos karbantartási munkát.
author: johanhoffmann
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a93436d101e6201c9d86279ea5b1a37fcc644fd1
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500454"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a><span data-ttu-id="4f036-103">Vevő által birtokolt eszközök karbantartási számlája</span><span class="sxs-lookup"><span data-stu-id="4f036-103">Bill for maintenance on customer-owned assets</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

<span data-ttu-id="4f036-104">A *munkarendelések számlázása* funkcióval a vevők tulajdonában levő tárgyi eszközök karbantartására vonatkozó munka hozható létre, dolgozható fel és számlázható.</span><span class="sxs-lookup"><span data-stu-id="4f036-104">The *Work order billing* feature lets you create, process, and bill maintenance work that is done on assets that your customers own.</span></span> <span data-ttu-id="4f036-105">A funkciók segítségével az alábbi műveleteket végezeti el:</span><span class="sxs-lookup"><span data-stu-id="4f036-105">This feature lets you perform the following tasks:</span></span>

- <span data-ttu-id="4f036-106">Vevők összekapcsolása a tulajdonukban levő eszközökkel.</span><span class="sxs-lookup"><span data-stu-id="4f036-106">Connect customers to the assets that they own.</span></span>
- <span data-ttu-id="4f036-107">Válasszon ki egy vevőt, és tekintse meg azokat az eszközöket, amelyek a vevő tulajdonában vannak, a munkarendelés létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="4f036-107">Select a customer and view the assets that customer owns when you create a work order.</span></span>
- <span data-ttu-id="4f036-108">Állítson be egy szülőprojektet minden vevő számára.</span><span class="sxs-lookup"><span data-stu-id="4f036-108">Set up a parent project for each customer.</span></span>
- <span data-ttu-id="4f036-109">Órák, cikkek, költségek és díjak regisztrálása a munkarendelésre, majd később számlajavaslat létrehozása a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="4f036-109">Register hours, items, expenses, and fees against the work order, and then create an invoice proposal for the customer later.</span></span>

<span data-ttu-id="4f036-110">Ezenkívül a funkció a következő funkciókat biztosítja:</span><span class="sxs-lookup"><span data-stu-id="4f036-110">In addition, the feature provides the following functionality:</span></span>

- <span data-ttu-id="4f036-111">A program automatikusan átmásolja a vevő szülőprojektből származó projektszerződést a megfelelő munkarendelési projektbe.</span><span class="sxs-lookup"><span data-stu-id="4f036-111">The project contract from a customer's parent project is automatically copied to the relevant work order project.</span></span>
- <span data-ttu-id="4f036-112">Az eszközkezelés a *díj* projekt tranzakciótípust most már mind a munkarendelési előrejelzésekben, mind a munkarendelési naplókban használhatja.</span><span class="sxs-lookup"><span data-stu-id="4f036-112">Asset management can now use the *fee* project transaction type on both work order forecasts and work order journals.</span></span>

## <a name="turn-on-the-customer-billing-feature"></a><span data-ttu-id="4f036-113">Kapcsolja be az ügyfél fizetési elemzés funkciót</span><span class="sxs-lookup"><span data-stu-id="4f036-113">Turn on the customer billing feature</span></span>

<span data-ttu-id="4f036-114">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="4f036-114">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="4f036-115">A rendszergazdák használhatják a [funkciókezelési](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="4f036-115">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="4f036-116">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="4f036-116">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="4f036-117">**Modul:** *Projektvezetés és könyvelés*</span><span class="sxs-lookup"><span data-stu-id="4f036-117">**Module:** *Project management and accounting*</span></span>
- <span data-ttu-id="4f036-118">**Funkció neve:** *Munkarendelés számlázása*</span><span class="sxs-lookup"><span data-stu-id="4f036-118">**Feature name:** *Work order billing*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="4f036-119">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="4f036-119">Example scenario</span></span>

<span data-ttu-id="4f036-120">A funkció működését a következő példaesetben lehet megismerni.</span><span class="sxs-lookup"><span data-stu-id="4f036-120">To learn how this feature works, work through the following example scenario.</span></span>

<span data-ttu-id="4f036-121">Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="4f036-121">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="4f036-122">Az **USMF** jogi személyt ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="4f036-122">You must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="4f036-123">A forgatókönyvet a gyártási rendszerben végzett munka során a funkció használatához útmutatásként is használhatja.</span><span class="sxs-lookup"><span data-stu-id="4f036-123">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="4f036-124">Ebben az esetben azonban a saját értékeit kell helyettesítenie, és előfordulhat, hogy bizonyos típusú kötelező rekordok hiányoznak, amelyeket a szabvány demóadatok biztosítanak.</span><span class="sxs-lookup"><span data-stu-id="4f036-124">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a><span data-ttu-id="4f036-125">1. lépés: Új projektszerződés létrehozása a vevő számára</span><span class="sxs-lookup"><span data-stu-id="4f036-125">Step 1: Create a new project contract for the customer</span></span>

1. <span data-ttu-id="4f036-126">Lépjen a **Projektvezetés és könyvelés \> Projektek \> Projektszerződések** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="4f036-126">Go to **Project management and accounting \> Projects \> Project contracts**.</span></span>
1. <span data-ttu-id="4f036-127">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="4f036-127">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="4f036-128">Az **Új projektszerződés** párbeszédpanelen a következő értékeket állíthatja be:</span><span class="sxs-lookup"><span data-stu-id="4f036-128">In the **New project contract** dialog box, set the following values:</span></span>

    - <span data-ttu-id="4f036-129">**Név:** *Pelikán Nagykereskedelem*</span><span class="sxs-lookup"><span data-stu-id="4f036-129">**Name:** *Pelican Wholesales*</span></span>
    - <span data-ttu-id="4f036-130">**Finanszírozás típusa:** *Vevő*</span><span class="sxs-lookup"><span data-stu-id="4f036-130">**Funding type:** *Customer*</span></span>
    - <span data-ttu-id="4f036-131">**Finanszírozási forrás:** *US-013* (*Pelikán Nagykereskedelem*)</span><span class="sxs-lookup"><span data-stu-id="4f036-131">**Funding source:** *US-013* (*Pelican Wholesales*)</span></span>

1. <span data-ttu-id="4f036-132">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4f036-132">Select **OK**.</span></span>

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a><span data-ttu-id="4f036-133">2. lépés: Új szülőprojekt létrehozása a vevő számára</span><span class="sxs-lookup"><span data-stu-id="4f036-133">Step 2: Create a new parent project for the customer</span></span>

<span data-ttu-id="4f036-134">Az itt létrehozott szülőprojektet használja a program a vevői munkarendelések létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="4f036-134">The parent project that you create here will be used when work orders for the customer are created.</span></span>

1. <span data-ttu-id="4f036-135">Ugorjon a **Projektvezetés és könyvelés \> Projektek \> Minden projekt** pontra.</span><span class="sxs-lookup"><span data-stu-id="4f036-135">Go to **Project management and accounting \> Projects \> All projects**.</span></span>
1. <span data-ttu-id="4f036-136">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="4f036-136">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="4f036-137">Az **Új projekt** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="4f036-137">In the **New project** dialog box, set the following values:</span></span>

    - <span data-ttu-id="4f036-138">**Projekt típusa:** *Idő és anyag*</span><span class="sxs-lookup"><span data-stu-id="4f036-138">**Project type:** *Time and material*</span></span>
    - <span data-ttu-id="4f036-139">**Projekt neve:** *Pelikán Nagykereskedelem munkarendelések*</span><span class="sxs-lookup"><span data-stu-id="4f036-139">**Project name:** *Pelican Wholesales work orders*</span></span>
    - <span data-ttu-id="4f036-140">**Projektcsoport:** *TM*</span><span class="sxs-lookup"><span data-stu-id="4f036-140">**Project group:** *TM*</span></span>
    - <span data-ttu-id="4f036-141">**Projektszerződés azonosítója:** *Pelikán Nagykereskedelem* (a korábban létrehozott szerződés)</span><span class="sxs-lookup"><span data-stu-id="4f036-141">**Project contract ID:** *Pelican Wholesales* (the contract that you created earlier)</span></span>
    - <span data-ttu-id="4f036-142">**Kezdő dátum:** válassza ki a mai napot.</span><span class="sxs-lookup"><span data-stu-id="4f036-142">**Start date:** Select today's date.</span></span>

1. <span data-ttu-id="4f036-143">Válassza a **Projekt létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="4f036-143">Select **Create project**.</span></span>
1. <span data-ttu-id="4f036-144">Az új projekt megnyílik.</span><span class="sxs-lookup"><span data-stu-id="4f036-144">The new project is opened.</span></span> <span data-ttu-id="4f036-145">Jegyezze fel a **Projektazonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="4f036-145">Make a note of the **Project ID** value.</span></span> <span data-ttu-id="4f036-146">Ezt később kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="4f036-146">You will have to enter it later.</span></span>

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a><span data-ttu-id="4f036-147">3. lépés: Új munkarendelés-típus létrehozása az Eszközkezelésben</span><span class="sxs-lookup"><span data-stu-id="4f036-147">Step 3: Create a new work order type in Asset management</span></span>

1. <span data-ttu-id="4f036-148">Válassza ki az **Eszközkezelés \> Beállítás \> Munkarendelések \> Munkarendelés-típusai** elemet.</span><span class="sxs-lookup"><span data-stu-id="4f036-148">Go to **Asset management \> Setup \> Work order \> Work order types**.</span></span>
1. <span data-ttu-id="4f036-149">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="4f036-149">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="4f036-150">A program új rekordot ad hozzá a listához.</span><span class="sxs-lookup"><span data-stu-id="4f036-150">A new record is added to the list.</span></span> <span data-ttu-id="4f036-151">A következő értékeket állítsa be hozzá:</span><span class="sxs-lookup"><span data-stu-id="4f036-151">Set the following values for it:</span></span>

    - <span data-ttu-id="4f036-152">**Munkarendelés típusa:** *Szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="4f036-152">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="4f036-153">**Név:** *Szolgáltatási munkarendelés*</span><span class="sxs-lookup"><span data-stu-id="4f036-153">**Name:** *Service work orders*</span></span>
    - <span data-ttu-id="4f036-154">**Munkarendelés életciklus-állapot:** *Standard*</span><span class="sxs-lookup"><span data-stu-id="4f036-154">**Work order lifecycle state:** *Standard*</span></span>

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a><span data-ttu-id="4f036-155">4. lépés: A vevőszámla csatolása a szülőprojekthez</span><span class="sxs-lookup"><span data-stu-id="4f036-155">Step 4: Link the customer account to the parent project</span></span>

<span data-ttu-id="4f036-156">A vevői számlát most az Eszközkezelés projektbeállításában kell a szülőprojekthez csatolni.</span><span class="sxs-lookup"><span data-stu-id="4f036-156">You must now link the customer account to the parent project in the project setup in Asset management.</span></span>

1. <span data-ttu-id="4f036-157">Válassza ki az **Eszközkezelés \> Beállítás \> Munkarendelések \> Projektbeállítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="4f036-157">Go to **Asset management \> Setup \> Work orders \> Project setup**.</span></span>
1. <span data-ttu-id="4f036-158">A **Szülőprojekt** lapon válassza a **Hozzáadás** lehetőséget új sor hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="4f036-158">On the **Parent project** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="4f036-159">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="4f036-159">On the new line, set the following values:</span></span>

    - <span data-ttu-id="4f036-160">**Vevői számla:** *US-013* (*Pelikán Nagykereskedelem*)</span><span class="sxs-lookup"><span data-stu-id="4f036-160">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="4f036-161">**Projektazonosító:** Adja meg annak a projektnek az azonosítóját, amelyről korábban megjegyzést készített.</span><span class="sxs-lookup"><span data-stu-id="4f036-161">**Project ID:** Enter the project ID that you made a note of earlier.</span></span>

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a><span data-ttu-id="4f036-162">5. lépés: A projektcsoport és a típus összekapcsolása és munkarendelési projekttel</span><span class="sxs-lookup"><span data-stu-id="4f036-162">Step 5: Link the project group and type to the work order project</span></span>

<span data-ttu-id="4f036-163">Továbbra is a **Projekt beállítása** lapon kell lennie (**Eszközkezelés \> Beállítás \> Munkarendelések \> Projekt beállítása**).</span><span class="sxs-lookup"><span data-stu-id="4f036-163">You should still be on the **Project setup** page (**Asset management \> Setup \> Work orders \> Project setup**).</span></span>

1. <span data-ttu-id="4f036-164">A **Projektcsoport** lapon válassza a **Hozzáadás** lehetőséget új sor hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="4f036-164">On the **Project group** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="4f036-165">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="4f036-165">On the new line, set the following values:</span></span>

    - <span data-ttu-id="4f036-166">**Munkarendelés típusa:** *Szolgáltatás* (a korábban létrehozott munkarendelés-típus)</span><span class="sxs-lookup"><span data-stu-id="4f036-166">**Work order type:** *Service* (the work order type that you created earlier)</span></span>
    - <span data-ttu-id="4f036-167">**Projektcsoport:** *TM*</span><span class="sxs-lookup"><span data-stu-id="4f036-167">**Project group:** *TM*</span></span>

> [!NOTE]
> <span data-ttu-id="4f036-168">A munkarendelési projekt projektszerződése mindig a szülőprojekttől öröklődik.</span><span class="sxs-lookup"><span data-stu-id="4f036-168">The project contract on the work order project is always inherited from the parent project.</span></span>

### <a name="step-6-link-an-asset-to-the-customer-id"></a><span data-ttu-id="4f036-169">6. lépés: Eszköz csatolása a vevőazonosítóhoz</span><span class="sxs-lookup"><span data-stu-id="4f036-169">Step 6: Link an asset to the customer ID</span></span>

1. <span data-ttu-id="4f036-170">Lépjen az **Eszközkezelés \> Eszközök \> Aktív eszközök** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f036-170">Go to **Asset management \> Assets \> Active assets**.</span></span>
1. <span data-ttu-id="4f036-171">A **Szűrő** mezőben adja meg a *VE-102* értékét, és válassza az **Eszköz** szerinti szűrést.</span><span class="sxs-lookup"><span data-stu-id="4f036-171">In the **Filter** field, enter *VE-102*, and select to filter by **Asset**.</span></span>
1. <span data-ttu-id="4f036-172">Válassza ki az eszközt a beállításai megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4f036-172">Select the asset to open its settings.</span></span>
1. <span data-ttu-id="4f036-173">A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-013* (*Pelikán Nagykereskedelem*) értékhez.</span><span class="sxs-lookup"><span data-stu-id="4f036-173">On the **Customer** FastTab, set the **Customer account** field to *US-013* (*Pelican Wholesales*).</span></span>

    <span data-ttu-id="4f036-174">A **Név** mező automatikusan frissítve lesz a *Pelikán Nagykereskedelem* névre.</span><span class="sxs-lookup"><span data-stu-id="4f036-174">The **Name** field is automatically updated to *Pelican Wholesales*.</span></span>

### <a name="step-7-create-a-new-work-order-on-the-asset"></a><span data-ttu-id="4f036-175">7. lépés: Új munkarendelés létrehozása az eszközhöz</span><span class="sxs-lookup"><span data-stu-id="4f036-175">Step 7: Create a new work order on the asset</span></span>

1. <span data-ttu-id="4f036-176">Válassza ki az **Eszközkezelés \> Munkarendelések \> Aktív munkarendelések** elemet.</span><span class="sxs-lookup"><span data-stu-id="4f036-176">Go to **Asset management \> Work orders \> Active work orders**.</span></span>
1. <span data-ttu-id="4f036-177">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="4f036-177">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="4f036-178">A **Munkarendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="4f036-178">In the **Create work order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="4f036-179">**Munkarendelés típusa:** *Szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="4f036-179">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="4f036-180">**Leírás:** *Teherautó javítása*</span><span class="sxs-lookup"><span data-stu-id="4f036-180">**Description:** *Repair Truck*</span></span>
    - <span data-ttu-id="4f036-181">**Vevői számla:** *US-013* (*Pelikán Nagykereskedelem*)</span><span class="sxs-lookup"><span data-stu-id="4f036-181">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="4f036-182">**Eszköz:** *VE-102*</span><span class="sxs-lookup"><span data-stu-id="4f036-182">**Asset:** *VE-102*</span></span>

        > [!NOTE]
        > <span data-ttu-id="4f036-183">A keresés csak azokat az eszközöket jeleníti meg, amelyek a kiválasztott vevői számlához vannak kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="4f036-183">The lookup shows only assets that are linked to the selected customer account.</span></span>

    - <span data-ttu-id="4f036-184">**Karbantartási feladat típusa:** *Javítás*</span><span class="sxs-lookup"><span data-stu-id="4f036-184">**Maintenance job type:** *Repair*</span></span>
    - <span data-ttu-id="4f036-185">**Szakma:** *Autószerelő*</span><span class="sxs-lookup"><span data-stu-id="4f036-185">**Trade:** *Mechanic*</span></span>
    - <span data-ttu-id="4f036-186">**Szolgáltatásszint:** *4*</span><span class="sxs-lookup"><span data-stu-id="4f036-186">**Service level:** *4*</span></span>

1. <span data-ttu-id="4f036-187">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4f036-187">Select **OK**.</span></span>

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a><span data-ttu-id="4f036-188">8. lépés: Tekintse át a munkarendelést, és indítsa el a munkát</span><span class="sxs-lookup"><span data-stu-id="4f036-188">Step 8: Review the work order and start to work on it</span></span>

<span data-ttu-id="4f036-189">Ebben a szakaszban az előző szakaszban létrehozott munkarendelésen fog dolgozni.</span><span class="sxs-lookup"><span data-stu-id="4f036-189">In this section, you will work on the work order that you created in the previous section.</span></span>

1. <span data-ttu-id="4f036-190">A következő lépések szerint ellenőrizze, hogy a szülőprojekt a *Pelikán Nagykereskedelem* projekt-e:</span><span class="sxs-lookup"><span data-stu-id="4f036-190">Follow these steps to verify that the parent project is the *Pelican wholesales Work order* project:</span></span>

    1. <span data-ttu-id="4f036-191">Válasszon ki egy sort a **Munkarendelés karbantartási feladatai** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="4f036-191">In the **Work order maintenance jobs** section, select a line.</span></span>
    1. <span data-ttu-id="4f036-192">A **Sor részletei** gyorslapon vizsgálja meg a **Projektazonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="4f036-192">On the **Line details** FastTab, inspect the **Project ID** value.</span></span> <span data-ttu-id="4f036-193">Kötőjelezett számnak kell lennie a következő formátumban: *\<Parent-Project-ID\>-\<Project-ID\>*.</span><span class="sxs-lookup"><span data-stu-id="4f036-193">It should be a hyphenated number in the form *\<Parent-Project-ID\>-\<Project-ID\>*.</span></span> <span data-ttu-id="4f036-194">Ez az érték egy hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="4f036-194">This value is a link.</span></span>
    1. <span data-ttu-id="4f036-195">Válassza ki a projektazonosító hivatkozását egy olyan lap megnyitásához, ahol megtekinthetők a szülőprojektek és a projektnevek.</span><span class="sxs-lookup"><span data-stu-id="4f036-195">Select the project ID link to open a page where you can view the parent project and project names.</span></span>

1. <span data-ttu-id="4f036-196">A Művelet ablaktábla **Munkarendelés** lapjának **Életciklus-állapot** csoportjában válassza a **Munkarendelés állapotának frissítése** elemet.</span><span class="sxs-lookup"><span data-stu-id="4f036-196">On the Action Pane, on the **Work order** tab, in the **Lifecycle state** group, select **Update work order state**.</span></span>
1. <span data-ttu-id="4f036-197">A **Munkarendelés állapotának frissítése** párbeszédpanel **Kijelölés** oszlopában jelölje be annak a sornak a jelölőnégyzetét, ahol az **Életciklus-állapot** mező beállítása a *Folyamatban*.</span><span class="sxs-lookup"><span data-stu-id="4f036-197">In the **Update work order state** dialog box, in the **Select** column, select the check box for the row where the **Lifecycle state** field is set to *In progress*.</span></span>
1. <span data-ttu-id="4f036-198">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4f036-198">Select **OK**.</span></span>
1. <span data-ttu-id="4f036-199">Az **Életciklus-állapot: Folyamatban** párbeszédpanelen válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="4f036-199">In the **Lifecycle state: InProgress** dialog box, select **OK**.</span></span>

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a><span data-ttu-id="4f036-200">9. lépés: A munkarendelésre fordított órák feladása, és új számlajavaslat létrehozása</span><span class="sxs-lookup"><span data-stu-id="4f036-200">Step 9: Post the hours that were spent on the work order and create a new invoice proposal</span></span>

<span data-ttu-id="4f036-201">Ebben a szakaszban az előző szakaszban létrehozott munkarendelésen fogja folytatni a munkát.</span><span class="sxs-lookup"><span data-stu-id="4f036-201">In this section, you will continue to work on the work order that you worked on in the previous section.</span></span>

1. <span data-ttu-id="4f036-202">A Műveleti ablaktáblán, a **Munkarendelés** lapon a **Projekt** csoportban kattintson a **Naplók** elemre.</span><span class="sxs-lookup"><span data-stu-id="4f036-202">On the Action Pane, on the **Work order** tab, in the **Project** group, select **Journals**.</span></span>

    <span data-ttu-id="4f036-203">Megjelenik a **Munkarendelési naplók** lap.</span><span class="sxs-lookup"><span data-stu-id="4f036-203">The **Work order journals** page appears.</span></span> <span data-ttu-id="4f036-204">Itt regisztrálhatja a munkarendelésre fordított időt.</span><span class="sxs-lookup"><span data-stu-id="4f036-204">Here, you can register the time that you spent on the work order.</span></span>

1. <span data-ttu-id="4f036-205">Az **Órák** gyorslapon válassza a **Sor hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4f036-205">On the **Hours** FastTab, select **Add line**.</span></span>
1. <span data-ttu-id="4f036-206">Az új sorban állítsa **Órák** mezőt a *4* értékre.</span><span class="sxs-lookup"><span data-stu-id="4f036-206">On the new, line, set the **Hours** field to *4*.</span></span>
1. <span data-ttu-id="4f036-207">A Művelet ablaktáblán válassza ki a **Naplók feladása** elemet.</span><span class="sxs-lookup"><span data-stu-id="4f036-207">On the Action Pane, select **Post journals**.</span></span>
1. <span data-ttu-id="4f036-208">A munkarendelésre való visszatéréshez zárja be a **Munkarendelési naplók** lapot.</span><span class="sxs-lookup"><span data-stu-id="4f036-208">Close the **Work order journals** page to return to the work order.</span></span>
1. <span data-ttu-id="4f036-209">A Művelet panel **Számlázás** lapján válassza az **Új számlajavaslat** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="4f036-209">On the Action Pane, on the **Invoicing** tab, select **New invoice proposal**.</span></span>
1. <span data-ttu-id="4f036-210">A **Számlajavaslat létrehozása** párbeszédpanel **Projekttranzakciók** szakaszában minden számlázni kívánt sor esetében jelölje be a **Kijelölés** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4f036-210">In the **Create invoice proposal** dialog box, in the **Project transactions** section, select the **Select** check box for every line  that you want to invoice.</span></span>
1. <span data-ttu-id="4f036-211">Válassza az **OK** gombot a párbeszédpanel bezárásához és az új számlajavaslat megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="4f036-211">Select **OK** to close the dialog box and view the new invoice proposal.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]