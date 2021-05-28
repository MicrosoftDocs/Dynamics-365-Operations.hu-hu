---
title: Adófunkció támogatása átmozgatási rendelésekhez
description: Ez a témakör ismerteti az átutalási rendelések új adózási szolgáltatásának támogatását az adószámítási szolgáltatás használatával.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3a5c2b6fb48d98ba045c77ed034d976f7d89af98
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021369"
---
# <a name="tax-feature-support-for-transfer-orders"></a><span data-ttu-id="6db2d-103">Adófunkció támogatása átmozgatási rendelésekhez</span><span class="sxs-lookup"><span data-stu-id="6db2d-103">Tax feature support for transfer orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6db2d-104">Ez a témakör az adószámításról és az átmozgatási rendelések integrációjának feladásáról nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="6db2d-104">This topic provides information about tax calculation and posting integration in transfer orders.</span></span> <span data-ttu-id="6db2d-105">Ezzel a funkcióval áfaszámítást és könyvelést állíthat be a készletáthelyezések átmozgatási rendeléseiben.</span><span class="sxs-lookup"><span data-stu-id="6db2d-105">This functionality lets you set up tax calculation and posting in transfer orders for stock transfers.</span></span> <span data-ttu-id="6db2d-106">Az Európai Unió (EU) általános forgalmi adóval (ÁFA) kapcsolatos szabályozása szerint a készletátmozgatások közösségen belüli beszállításnak és közösségen belüli beszerzéseknek minősülnek.</span><span class="sxs-lookup"><span data-stu-id="6db2d-106">Under European Union (EU) value-added tax (VAT) regulations, stock transfers are considered intra-community supply and intra-community acquisitions.</span></span>

<span data-ttu-id="6db2d-107">A funkció konfigurálásához és használathoz három fő lépést kell elvégeznie:</span><span class="sxs-lookup"><span data-stu-id="6db2d-107">To configure and use this functionality, you must complete three main steps:</span></span>

1. <span data-ttu-id="6db2d-108">**RCS beállítása:** A Regulatory Configuration Services szolgáltatásban állítsa be az adófunkciót, az adókódok és az adókódok alkalmazhatóságát az adókód meghatározására az átviteli rendelésekben.</span><span class="sxs-lookup"><span data-stu-id="6db2d-108">**RCS setup:** In Regulatory Configuration Service, set up the tax feature, tax codes, and tax codes applicability for tax code determination in transfer orders.</span></span>
2. <span data-ttu-id="6db2d-109">**Finance beállítása:** A Microsoft Dynamics 365 Finance alkalmazásban kapcsolja be az **Adó az átmozgatási rendelésben** szolgáltatást, állítsa be a készlet adószolgáltatásának paramétereit, és állítsa be az alapvető adóparamétereket.</span><span class="sxs-lookup"><span data-stu-id="6db2d-109">**Finance setup:** In Microsoft Dynamics 365 Finance, turn on the **Tax in transfer order** feature, set up the tax service parameters for inventory, and set up core tax parameters.</span></span>
3. <span data-ttu-id="6db2d-110">**Készletbeállítás:** Állítsa be az átviteli rendelési tranzakciók készletkonfigurációját.</span><span class="sxs-lookup"><span data-stu-id="6db2d-110">**Inventory setup:** Set up the inventory configuration for transfer order transactions.</span></span>

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a><span data-ttu-id="6db2d-111">Az RCS beállítása adóhoz és az átmozgatási rendelési tranzakciókhoz</span><span class="sxs-lookup"><span data-stu-id="6db2d-111">Set up RCS for tax and transfer order transactions</span></span>

<span data-ttu-id="6db2d-112">Az átmozgatási rendelésben érintett adó beállítását az alábbi lépésekkel állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="6db2d-112">Follow these steps to set up the tax that is involved in a transfer order.</span></span> <span data-ttu-id="6db2d-113">Az itt látható példában az átmozgatási rendelés Hollandiából Belgiumba irányul.</span><span class="sxs-lookup"><span data-stu-id="6db2d-113">In the example that is shown here, the transfer order is from the Netherlands to Belgium.</span></span>

1. <span data-ttu-id="6db2d-114">Az **Adófunkciók** oldalon a **Verziók** lapon jelölje ki a vázlat funkcióverziót, majd kattintson a **Szerkesztés** gombra.</span><span class="sxs-lookup"><span data-stu-id="6db2d-114">On the **Tax features** page, on the **Versions** tab, select the draft feature version, and then select **Edit**.</span></span>

    ![Szerkesztés kiválasztása](../media/tax-feature-support-01.png)

2. <span data-ttu-id="6db2d-116">Az **Adófunkciók beállítása** oldal **Adókódok** lapján válassza a **Hozzáadás** lehetőséget új adókódok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6db2d-116">On the **Tax features setup** page, on the **Tax codes** tab, select **Add** to create new tax codes.</span></span> <span data-ttu-id="6db2d-117">Ebben a példában három adókód jön létre: **NL-Exempt**, **BE-RC-21** és **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="6db2d-117">For this example, three tax codes are created: **NL-Exempt**, **BE-RC-21**, and **BE-RC+21**.</span></span>

    - <span data-ttu-id="6db2d-118">Amikor egy átutalási megbízást egy hollandiai raktárból szállítanak, a holland áfamentes adókódot (**NL-exempt**) alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="6db2d-118">When a transfer order is shipped from a warehouse in the Netherlands, the Netherlands VAT exempted tax code (**NL-Exempt**) is applied.</span></span>
      
        <span data-ttu-id="6db2d-119">Hozza létre az **NL-Exempt** adókódot.</span><span class="sxs-lookup"><span data-stu-id="6db2d-119">Create the tax code **NL-Exempt**.</span></span>
        1. <span data-ttu-id="6db2d-120">Válassza a **Hozzáadás** lehetőséget, írja be az **NL-adómentes** értéket az **Adókód** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6db2d-120">Select **Add**, enter **NL-Exempt** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="6db2d-121">Válassza a **Nettó összeg szerint** lehetőséget az **Adóösszetevő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="6db2d-121">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="6db2d-122">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-122">Select **Save**.</span></span>
        4. <span data-ttu-id="6db2d-123">A **Díj** táblában válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-123">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="6db2d-124">Kapcsolja az **Adómentes** lehetőséget **Igen** értékre az **Általános** részben.</span><span class="sxs-lookup"><span data-stu-id="6db2d-124">Swtich **Is Exempt** to **Yes** in the **General** section.</span></span>

        ![NL adómentes adókód](../media/tax-feature-support-02.png)

    - <span data-ttu-id="6db2d-126">Amikor átmozgatási rendelés megérkezik egy belgiumi raktárba, a fordított adózás mechanizmusa a **BE-RC-21** és **BE-RC+21** adókódok használatával kerül alkalmazásra.</span><span class="sxs-lookup"><span data-stu-id="6db2d-126">When a transfer order is received at a Belgium warehouse, the reverse charge mechanism is applied by using the **BE-RC-21** and **BE-RC+21** tax codes.</span></span>
        
        <span data-ttu-id="6db2d-127">Hozza létre a **BE-RC-21** adókódot.</span><span class="sxs-lookup"><span data-stu-id="6db2d-127">Create the tax code **BE-RC-21**.</span></span>      
        1. <span data-ttu-id="6db2d-128">Válassza a **Hozzáadás** lehetőséget, írja be a **BE-RC-21** értéket az **Adókód** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6db2d-128">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="6db2d-129">Válassza a **Nettó összeg szerint** lehetőséget az **Adóösszetevő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="6db2d-129">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="6db2d-130">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-130">Select **Save**.</span></span>
        4. <span data-ttu-id="6db2d-131">A **Díj** táblában válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-131">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="6db2d-132">Adja meg a **-21** értéket az **Adókulcs** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6db2d-132">Enter **-21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="6db2d-133">Kapcsolja a **Fordított áfás** lehetőséget **Igen** értékre az **Általános** részben.</span><span class="sxs-lookup"><span data-stu-id="6db2d-133">Swtich **Is Reverse Charge** to **Yes** in the **General** section.</span></span>
        7. <span data-ttu-id="6db2d-134">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-134">Select **Save**.</span></span>

        ![BE-RC-21 adókód a fordított áfához](../media/tax-feature-support-03.png)
        
        <span data-ttu-id="6db2d-136">Hozza létre a **BE-RC+21** adókódot.</span><span class="sxs-lookup"><span data-stu-id="6db2d-136">Create the tax code **BE-RC+21**.</span></span>
        1. <span data-ttu-id="6db2d-137">Válassza a **Hozzáadás** lehetőséget, írja be a **BE-RC-21** értéket az **Adókód** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6db2d-137">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="6db2d-138">Válassza a **Nettó összeg szerint** lehetőséget az **Adóösszetevő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="6db2d-138">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="6db2d-139">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-139">Select **Save**.</span></span>
        4. <span data-ttu-id="6db2d-140">A **Díj** táblában válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-140">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="6db2d-141">Adja meg a **21** értéket az **Adókulcs** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6db2d-141">Enter **21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="6db2d-142">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-142">Select **Save**.</span></span>

        ![BE-RC+21 adókód a fordított áfához](../media/tax-feature-support-04.png)

3. <span data-ttu-id="6db2d-144">Adja meg az adókódok alkalmazhatóságát.</span><span class="sxs-lookup"><span data-stu-id="6db2d-144">Define the applicability of the tax codes.</span></span>

    1. <span data-ttu-id="6db2d-145">Válassza az **Oszlopok kezelése** lehetőséget, majd jelölje ki az alkalmazhatósági tábla létrehozásához használható oszlopokat.</span><span class="sxs-lookup"><span data-stu-id="6db2d-145">Select **Manage columns**, and then select columns that should be used to build the applicability table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6db2d-146">Mindenképpen adja hozzá az **Üzleti folyamat** és az **Adóirányok** oszlopokat a táblához.</span><span class="sxs-lookup"><span data-stu-id="6db2d-146">Be sure to add the **Business process** and **Tax directions** columns to the table.</span></span> <span data-ttu-id="6db2d-147">Mindkét oszlop nélkülözhetetlen az átmozgatási rendelések adófunkciójához.</span><span class="sxs-lookup"><span data-stu-id="6db2d-147">Both columns are essential to the functionality for tax in transfer orders.</span></span>

    2. <span data-ttu-id="6db2d-148">Alkalmazhatósági szabályok hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="6db2d-148">Add applicability rules.</span></span> <span data-ttu-id="6db2d-149">Ne hagyja üresen az **Adókódok**, **Adócsoport** és **Cikkáfacsoport** mezőket.</span><span class="sxs-lookup"><span data-stu-id="6db2d-149">Don't leave the **Tax codes**, **Tax group**, and **Item tax group** fields blank.</span></span>
        
        <span data-ttu-id="6db2d-150">Adjon hozzá egy új szabályt az átmozgatási rendelés szállítmányához.</span><span class="sxs-lookup"><span data-stu-id="6db2d-150">Add a new rule for transfer order shipment.</span></span>
        1. <span data-ttu-id="6db2d-151">A **Díj** táblában válassza az **Alkalmazhatósági szabályok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-151">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="6db2d-152">Az **Üzleti folyamat** mezőben válassza a **Készlet** lehetőséget, hogy a szabály alkalmazható legyen az átmozgatási rendelésre.</span><span class="sxs-lookup"><span data-stu-id="6db2d-152">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="6db2d-153">A **Szállítás országból/régióból** mezőbe írja be az **NLD** értéket.</span><span class="sxs-lookup"><span data-stu-id="6db2d-153">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="6db2d-154">A **Szállítás országa/régiója** mezőbe írja be a **BEL** értéket.</span><span class="sxs-lookup"><span data-stu-id="6db2d-154">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="6db2d-155">Az **Adó iránya** mezőben válassza a **Kimenet** lehetőséget, ha a szabályt az átmozgatási rendelés szállítmányára is alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="6db2d-155">In the **Tax direction** field, select **Output** to make the rule applicable to transfer order shipment.</span></span>
        6. <span data-ttu-id="6db2d-156">Az **Adókódok** mezőben válassza ki az **NL-Exempt** értéket.</span><span class="sxs-lookup"><span data-stu-id="6db2d-156">In the **Tax codes** field, select **NL-Exempt**.</span></span>
        7. <span data-ttu-id="6db2d-157">Az **Adócsoport** mezőben és a **Cikkáfa csoportban** adja meg a Finance rendszerben definiált kapcsolódó áfacsoportot és cikkáfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="6db2d-157">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>
        
        <span data-ttu-id="6db2d-158">Adjon hozzá egy másik szabályt az átmozgatási rendelés befogadásához.</span><span class="sxs-lookup"><span data-stu-id="6db2d-158">Add another rule for transfer order receipt.</span></span>
        1. <span data-ttu-id="6db2d-159">A **Díj** táblában válassza az **Alkalmazhatósági szabályok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-159">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="6db2d-160">Az **Üzleti folyamat** mezőben válassza a **Készlet** lehetőséget, hogy a szabály alkalmazható legyen az átmozgatási rendelésre.</span><span class="sxs-lookup"><span data-stu-id="6db2d-160">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="6db2d-161">A **Szállítás országból/régióból** mezőbe írja be az **NLD** értéket.</span><span class="sxs-lookup"><span data-stu-id="6db2d-161">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="6db2d-162">A **Szállítás országa/régiója** mezőbe írja be a **BEL** értéket.</span><span class="sxs-lookup"><span data-stu-id="6db2d-162">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="6db2d-163">Az **Adó iránya** mezőben válassza a **Bemenet** lehetőséget, ha a szabályt az átmozgatási rendelés fogadására is alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="6db2d-163">In the **Tax direction** field, select **Input** to make the rule applicable to transfer order receipt.</span></span>
        6. <span data-ttu-id="6db2d-164">Az **Adókódok** mezőben válassza a **BE-RC+21** és a **BE-RC-21** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-164">In the **Tax codes** field, select **BE-RC+21** and **BE-RC-21**.</span></span>
        7. <span data-ttu-id="6db2d-165">Az **Adócsoport** mezőben és a **Cikkáfa csoportban** adja meg a Finance rendszerben definiált kapcsolódó áfacsoportot és cikkáfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="6db2d-165">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>

        ![Alkalmazhatósági szabályok](../media/image5.png)

4. <span data-ttu-id="6db2d-167">Töltse ki és tegye közzé az új adófunkció-verziót.</span><span class="sxs-lookup"><span data-stu-id="6db2d-167">Complete and publish the new tax feature version.</span></span>

    <span data-ttu-id="6db2d-168">[![Az új verzió állapotának módosítása](../media/image6.png)](../media/image6.png)</span><span class="sxs-lookup"><span data-stu-id="6db2d-168">[![Changing the status of the new version](../media/image6.png)](../media/image6.png)</span></span>

## <a name="set-up-finance-for-transfer-order-transactions"></a><span data-ttu-id="6db2d-169">A Finance beállítása adóhoz és az átmozgatási rendelési tranzakciókhoz</span><span class="sxs-lookup"><span data-stu-id="6db2d-169">Set up Finance for transfer order transactions</span></span>

<span data-ttu-id="6db2d-170">Kövesse ezeket a lépseket az adók beállításához és engedélyezéséhez az értékesítési rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="6db2d-170">Follow these steps to enable and set up taxes for transfer orders.</span></span>

1. <span data-ttu-id="6db2d-171">A Finance-ben ugorjon **Munkaterületek** \> **Funkciókezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6db2d-171">In Finance, go to **Workspaces** \> **Feature management**.</span></span>
2. <span data-ttu-id="6db2d-172">A listában keresse meg és válassza az **Adó átmozgatási rendelésben** funkciót, majd az **Engedélyezés most** lehetőséget a bekapcsoláshoz.</span><span class="sxs-lookup"><span data-stu-id="6db2d-172">In the list, find and select the **Tax in transfer order** feature, and then select **Enable now** to turn it on.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6db2d-173">Az **Adó az átmozgatási rendelésben** funkció teljes mértékben függ az adószolgáltatástól.</span><span class="sxs-lookup"><span data-stu-id="6db2d-173">The **Tax in transfer order** feature is fully dependent on the tax service.</span></span> <span data-ttu-id="6db2d-174">Ezért csak az adó szolgáltatás telepítése után kapcsolható be.</span><span class="sxs-lookup"><span data-stu-id="6db2d-174">Therefore, it can be turned on only after you've installed the tax service.</span></span>

    ![Adó az átmozgatási rendelés funkcióban](../media/image7.png)

3. <span data-ttu-id="6db2d-176">Engedélyezze az adószolgáltatást, és válassza ki a **Készlet** üzleti folyamatot.</span><span class="sxs-lookup"><span data-stu-id="6db2d-176">Enable the tax service, and select the **Inventory** business process.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6db2d-177">Ezt a lépést minden olyan jogi személynél el kell végeznie a Finance-ben, ahol az adószolgáltatást és az átmozgatási rendelések adófunkcióit elérhetővé szeretné tenni.</span><span class="sxs-lookup"><span data-stu-id="6db2d-177">You must complete this step for each legal entity in Finance where you want the tax service and the functionality for tax in transfer orders to be available.</span></span>

    1. <span data-ttu-id="6db2d-178">Ugrás az **Adó** \> **Beállítás** \> **Adókonfiguráció** \> **Adószolgáltatás beállítása** lapra.</span><span class="sxs-lookup"><span data-stu-id="6db2d-178">Go to **Tax** \> **Setup** \> **Tax configuration** \> **Tax service setup**.</span></span>
    2. <span data-ttu-id="6db2d-179">Az **Üzleti folyamat** mezőben válassza a **Készlet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6db2d-179">In the **Business process** field, select **Inventory**.</span></span>

    ![Az Üzleti folyamat mező beállítása](../media/image8.png)

4. <span data-ttu-id="6db2d-181">Ellenőrizze, hogy a fordított áfa mechanizmus be van-e állítva.</span><span class="sxs-lookup"><span data-stu-id="6db2d-181">Verify that the reverse charge mechanism is set up.</span></span> <span data-ttu-id="6db2d-182">Válassza a **Főkönyv** \> **Beállítás** \> **Paraméterek** lapot, majd a **Fordított áfa** lapon ellenőrizze, hogy a **Fordított áfa engedélyezése** beállítás **Igen** értékű-e.</span><span class="sxs-lookup"><span data-stu-id="6db2d-182">Go to **General ledger** \> **Setup** \> **Parameters**, and then, on the **Reverse charge** tab, verify that the **Enable reverse charge** option is set to **Yes**.</span></span>

    ![Fordított áfa engedélyezése beállítás](../media/image9.png)

5. <span data-ttu-id="6db2d-184">Ellenőrizze, hogy a kapcsolódó adókódok, adócsoportok, cikkadócsoportok és áfaregisztrációs számok az adószolgáltatási útmutatónak megfelelően vannak-e beállítva a Finance-ben.</span><span class="sxs-lookup"><span data-stu-id="6db2d-184">Verify that the related tax codes, tax groups, item tax groups, and VAT registration numbers have been set up in Finance according to the tax service guidance.</span></span>
6. <span data-ttu-id="6db2d-185">Ideiglenes tranzitszámla beállítása.</span><span class="sxs-lookup"><span data-stu-id="6db2d-185">Set up an interim transit account.</span></span> <span data-ttu-id="6db2d-186">Erre a lépésre csak akkor van szükség, ha az átutalási megbízásra alkalmazott adó nem alkalmazható adómentes vagy fordított adózású mechanizmusra.</span><span class="sxs-lookup"><span data-stu-id="6db2d-186">This step is required only when the tax that is applied to a transfer order isn't applicable to a tax exempted or reverse charge mechanism.</span></span>

    1. <span data-ttu-id="6db2d-187">Lépjen az **Adó** \> **Beállítás** \> **Áfa** \> **Főkönyvi feladási csoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="6db2d-187">Go to **Tax** \> **Setup** \> **Sales tax** \> **Ledger posting groups**.</span></span>
    2. <span data-ttu-id="6db2d-188">Az **Ideigelens tranzit** mezőben jelöljön ki egy főkönyvi számlát.</span><span class="sxs-lookup"><span data-stu-id="6db2d-188">In the **Interim transit** field, select a ledger account.</span></span>

    ![Ideiglenes tranzitszámla kiválasztása](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a><span data-ttu-id="6db2d-190">Alapleltár beállítása adóhoz és az átmozgatási rendelési tranzakciókhoz</span><span class="sxs-lookup"><span data-stu-id="6db2d-190">Set up basic inventory for transfer order transactions</span></span>

<span data-ttu-id="6db2d-191">Az alábbi lépésekkel állíthatja be az alapkészletet az átmozgatási rendelési tranzakciók engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="6db2d-191">Follow these steps to set up basic inventory to enable transfer order transactions.</span></span>

1. <span data-ttu-id="6db2d-192">Hozzon létre szállítás kiindulási és szállítási célhelyeket a raktárakhoz különböző országokban vagy régiókban, és adja hozzá az egyes helyek elsődleges címét.</span><span class="sxs-lookup"><span data-stu-id="6db2d-192">Create ship-from and ship-to sites for your warehouses in different countries or regions, and add the primary address for each site.</span></span>

    1. <span data-ttu-id="6db2d-193">Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Raktár** \> **Helyek** elemre.</span><span class="sxs-lookup"><span data-stu-id="6db2d-193">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Sites**.</span></span>
    2. <span data-ttu-id="6db2d-194">Válassza az **Új** lehetőséget egy hely létrehozásához, amit később hozzárendelhet egy raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="6db2d-194">Select **New** to create the site that you will assign to a warehouse later.</span></span>
    3. <span data-ttu-id="6db2d-195">Ismételje meg a 2. lépés minden más helyhez, amit létre kell hozna.</span><span class="sxs-lookup"><span data-stu-id="6db2d-195">Repeat step 2 for all the other sites that you must create.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6db2d-196">A létrehozott helyek egyikének **Tranzitnak** kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6db2d-196">One of the sites that you create should be named **Transit**.</span></span> <span data-ttu-id="6db2d-197">Az eljárás későbbi lépéseiben hozzárendeli ezt a helyet az árutovábbítási raktárhoz, hogy az adóval kapcsolatos készletutalványok feladásra kerülnek a "szállítási" és "fogadási" tranzakciókban az átadási rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="6db2d-197">In later steps of this procedure, you will assign this site to the transit warehouse, so that tax-related inventory vouchers can be posted in "ship" and "receive" transactions for transfer orders.</span></span> <span data-ttu-id="6db2d-198">A tranzithelyszín címe az adószámítás szempontjából irreleváns.</span><span class="sxs-lookup"><span data-stu-id="6db2d-198">The address of the transit site is irrelevant to tax calculation.</span></span> <span data-ttu-id="6db2d-199">Ezért akár üresen is hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="6db2d-199">Therefore, you can leave it blank.</span></span>

    ![Helyszínek beállításai](../media/image11.png)

2. <span data-ttu-id="6db2d-201">Hozzon létre kiindulási, tranzit- és szállítási raktárakat.</span><span class="sxs-lookup"><span data-stu-id="6db2d-201">Create ship-from, transit, and ship-to warehouses.</span></span> <span data-ttu-id="6db2d-202">A raktárban megtartott címadatok felülírják a hely címét az adó kiszámítása során.</span><span class="sxs-lookup"><span data-stu-id="6db2d-202">Any address information that is maintained in a warehouse will override the site address during tax calculation.</span></span>

    1. <span data-ttu-id="6db2d-203">Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Raktár** \> **Raktárak** pontra.</span><span class="sxs-lookup"><span data-stu-id="6db2d-203">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Warehouses**.</span></span>
    2. <span data-ttu-id="6db2d-204">Válassza az **Új** lehetőséget egy hely létrehozásához, és rendelje hozzá egy kapcsolódó helyhez.</span><span class="sxs-lookup"><span data-stu-id="6db2d-204">Select **New** to create a warehouse, and assign it to the corresponding site.</span></span>
    3. <span data-ttu-id="6db2d-205">Ismételje meg a 2. lépést egy raktár létrehozásához mindegyik helyszínhez igény szerint.</span><span class="sxs-lookup"><span data-stu-id="6db2d-205">Repeat step 2 to create a warehouse for each site as required.</span></span>

    ![Raktárak beállítása](../media/image12.png)

    > [!NOTE]
    > <span data-ttu-id="6db2d-207">Feladó raktár esetén a tranzitraktárt a **Tranzit raktár** mezőben kell kiválasztani az átmozgatási rendelési tranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="6db2d-207">For a ship-from warehouse, a transit warehouse must be selected in the **Transit warehouse** field for transfer order transactions.</span></span>
    >
    > ![Tranzitraktár kiválasztása](../media/image13.png)

3. <span data-ttu-id="6db2d-209">Ellenőrizze, hogy a készletfeladás konfigurációja be van-e állítva az átmozgatási rendelési tranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="6db2d-209">Verify that the inventory posting configuration is set up for transfer order transactions.</span></span>

    1. <span data-ttu-id="6db2d-210">Nyissa meg a **Készletkezelés** \> **Beállítás** \> **Feladás** \> **Feladás** menüt.</span><span class="sxs-lookup"><span data-stu-id="6db2d-210">Go to **Inventory management** \> **Setup** \> **Posting** \> **Posting**.</span></span>
    2. <span data-ttu-id="6db2d-211">A **Készlet** lapon ellenőrizze, hogy a főkönyvi számla be van-e állítva mind a **Készletkiadás**, mind a **Készletbevételezés** feladásához.</span><span class="sxs-lookup"><span data-stu-id="6db2d-211">On the **Inventory** tab, verify that a ledger account is set up for both **Inventory issue** and **Inventory receipt** posting.</span></span>

        ![Készletkiadás és készletbevételezés feladásának beállítása](../media/image14.png)

    3. <span data-ttu-id="6db2d-213">Ellenőrizze, hogy a főkönyvi számla be van-e állítva a **Egységközi kötelezettségek** könyveléséhez.</span><span class="sxs-lookup"><span data-stu-id="6db2d-213">Verify that a ledger account is set up for **Inter-unit payable** posting.</span></span>

        ![Egységközi kötelezettségek könyvelésének beállítása](../media/image15.png)

    4. <span data-ttu-id="6db2d-215">Ellenőrizze, hogy a főkönyvi számla be van-e állítva a **Egységközi követelések** könyveléséhez.</span><span class="sxs-lookup"><span data-stu-id="6db2d-215">Verify that a ledger account is set up for **Inter-unit receivable** posting.</span></span>

        ![Egységközi követelések könyvelésének beállítása](../media/image16.png)
