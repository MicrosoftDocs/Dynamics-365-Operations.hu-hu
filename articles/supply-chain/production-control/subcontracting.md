---
title: Alvállalkozásba adás
description: Ez a témakör segítségével létrehozhat egy bemutatót az alvállalkozói a gyártáshoz a Dynamics 365 Supply Chain Management alkalmazásban.
author: christophernread
manager: tfehr
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1cc1040393d843f39ca8c741a7c51435c7169c00
ms.sourcegitcommit: edb46dce498df42b09e8f5ad6de00f86c8022dfa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2020
ms.locfileid: "3346422"
---
# <a name="subcontracting"></a><span data-ttu-id="d74db-103">Alvállalkozásba adás</span><span class="sxs-lookup"><span data-stu-id="d74db-103">Subcontracting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d74db-104">Ez a témakör segítségével létrehozhat egy bemutatót az alvállalkozásba adásról a gyártásban a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d74db-104">This topic will help you build a walkthrough of subcontracting in manufacturing in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d74db-105">A témakör első része az adatok beállításáról szól.</span><span class="sxs-lookup"><span data-stu-id="d74db-105">The first part of this topic describes the setup of the data.</span></span> <span data-ttu-id="d74db-106">A második rész végigvezeti Önt a forgatókönyv lépésein.</span><span class="sxs-lookup"><span data-stu-id="d74db-106">The second part takes you through the steps in the walkthrough.</span></span>

## <a name="target-audience"></a><span data-ttu-id="d74db-107">Célközönség</span><span class="sxs-lookup"><span data-stu-id="d74db-107">Target audience</span></span>

<span data-ttu-id="d74db-108">Ebben a témakörben megtudhatja, hogyan állíthatja be a gyártási alvállalkozásba adást.</span><span class="sxs-lookup"><span data-stu-id="d74db-108">In this topic, you will learn how to set up subcontracting in manufacturing.</span></span> <span data-ttu-id="d74db-109">A HQUS jogi személynél lévő adatokat fogja használni az alvállalkozásba adás tevékenységfolyamatának alapvető beállításához.</span><span class="sxs-lookup"><span data-stu-id="d74db-109">You will use existing data in the HQUS legal entity to do the basic setup of a subcontracting activity flow.</span></span> <span data-ttu-id="d74db-110">A HQUS jogi személynél lévő bemutató adatok olyan beállítási paramétereket is tartalmaznak, amik az útmutató lépéseinek támogatására vannak állítva.</span><span class="sxs-lookup"><span data-stu-id="d74db-110">The demo data in the HQUS legal entity includes setup parameters that have been preset to support the steps in the walkthrough.</span></span> <span data-ttu-id="d74db-111">Annak ellenére, hogy az útmutató a kulcsfontosságú gyenge pontokat és a kihívásokat a különböző szerepkörök számára vizsgálja, a rendszergazda is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="d74db-111">Even though the walkthrough addresses key pain points and challenges for various roles, it can be completed by the system admin.</span></span>

## <a name="demo-scenario"></a><span data-ttu-id="d74db-112">Bemutató eset</span><span class="sxs-lookup"><span data-stu-id="d74db-112">Demo scenario</span></span>

<span data-ttu-id="d74db-113">A HQUS jogi személy felső kategóriás hangszórókat gyárt.</span><span class="sxs-lookup"><span data-stu-id="d74db-113">In the HQUS legal entity, high-end speakers are manufactured.</span></span> <span data-ttu-id="d74db-114">A gyártási folyamat során a hangszórók az alábbi három műveleten esnek át.</span><span class="sxs-lookup"><span data-stu-id="d74db-114">During the manufacturing process, speakers go through the following three operations.</span></span>

- <span data-ttu-id="d74db-115">**Előzetes összeállítás** – a hangszórókabinetet összeállítják.</span><span class="sxs-lookup"><span data-stu-id="d74db-115">**Pre-assembly** – The speaker cabinet is assembled.</span></span> <span data-ttu-id="d74db-116">A kabinet anyagát a művelet megkezdése előtt kiválasztják a nyersanyagraktárban.</span><span class="sxs-lookup"><span data-stu-id="d74db-116">The material for the cabinet is picked in the material warehouse before the operation is started.</span></span>
- <span data-ttu-id="d74db-117">**Bevonás** – Miután a hangszórókabinetet összeállították, bevonatot kell készíteni rá.</span><span class="sxs-lookup"><span data-stu-id="d74db-117">**Coating** – After the speaker cabinet has been assembled, it must be coated.</span></span> <span data-ttu-id="d74db-118">Ezt a műveletet egy szállító hajtja végre (alvállalkozó).</span><span class="sxs-lookup"><span data-stu-id="d74db-118">This operation is completed by a vendor (subcontractor).</span></span> <span data-ttu-id="d74db-119">Az előzetesen összeállított hangszórókabinetet két anyaggal együtt elszállítják a bevonás alvállalkozóhoz.</span><span class="sxs-lookup"><span data-stu-id="d74db-119">The pre-assembled speaker cabinet is shipped to the coating subcontractor together with two materials.</span></span>
- <span data-ttu-id="d74db-120">**Elsimítás** – Az előzetesen összeállított hangszórókabinet, miután az alvállalkozó bevonatot készített hozzá, visszakerül a HQUS jogi személyhez, és a hangszóró végső összeállítása elkezdődhet.</span><span class="sxs-lookup"><span data-stu-id="d74db-120">**Finish** – After the pre-assembled speaker cabinet has been coated by the subcontractor, it's returned to the HQUS legal entity so that final assembly of the speaker can be completed.</span></span>

<span data-ttu-id="d74db-121">A következő ábrán a három művelet és az általuk igényelt anyagok láthatóak.</span><span class="sxs-lookup"><span data-stu-id="d74db-121">The following illustration shows the three operations and the materials that they consume.</span></span>

![Az előzetes összeállítás, bevonás, elsimítás műveletek és az általuk felhasználandó anyagok](./media/subcontract01_operations-materials.png)

## <a name="setup"></a><span data-ttu-id="d74db-123">Beállítás</span><span class="sxs-lookup"><span data-stu-id="d74db-123">Setup</span></span>

<span data-ttu-id="d74db-124">Az útmutató elkezdése előtt be kell állítania az adatokat.</span><span class="sxs-lookup"><span data-stu-id="d74db-124">Before you start the walkthrough, you must set up the data.</span></span>

### <a name="set-up-the-finished-product"></a><span data-ttu-id="d74db-125">Elkészült termék beállítása</span><span class="sxs-lookup"><span data-stu-id="d74db-125">Set up the finished product</span></span>

<span data-ttu-id="d74db-126">Ez az eljárás végigvezeti Önt a kiadott D8100 termék, a "Bevont kabinet" beállításán.</span><span class="sxs-lookup"><span data-stu-id="d74db-126">This procedure takes you through the setup of released product D8100, "Coated Cabinet."</span></span>

1. <span data-ttu-id="d74db-127">Válassza ki a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** opciót a **Kiadott termék részletei** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-127">Select **Product information management \> Products \> Released products** to open the **Released product details** page.</span></span>
2. <span data-ttu-id="d74db-128">A gyors szűrő mezőjébe írja be a **D8100** kódot a meglévő kiadott termék megtalálásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-128">In the quick filter field, enter **D8100** to find the existing released product.</span></span>

    ![A D8100 kiadott termék szűrése a kiadott termék részletei oldalon](./media/subcontract02_filtering-released-products.png)

3. <span data-ttu-id="d74db-130">A műveleti ablakon, a **Mérnök** lapon válassza ki az **Útvonal** opciót az **Útvonal** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-130">On the Action Pane, on the **Engineer** tab, select **Route** to open the **Route** page.</span></span>

    <span data-ttu-id="d74db-131">Az **Útvonal** oldal megjeleníti a kiadott D8100 termék nyolc útvonalverzióját.</span><span class="sxs-lookup"><span data-stu-id="d74db-131">The **Route** page shows the eight route versions for released product D8100.</span></span> <span data-ttu-id="d74db-132">A nyolc útvonalverzió négy-négy útvonalra van osztva az 1-es hely és az 5-ös hely között.</span><span class="sxs-lookup"><span data-stu-id="d74db-132">The eight route versions are divided among four routes on site 1 and site 5.</span></span> <span data-ttu-id="d74db-133">A 000400 útvonal a költségszámításhoz használható, a 00041 útvonal a bevonási művelethez mint belső művelet használható, és a 00042 útvonal a bevonási művelethez mint külső művelet használható.</span><span class="sxs-lookup"><span data-stu-id="d74db-133">Route 000400 is used for costing, route 00041 is used when the Coating operation is an internal operation, and route 00042 is used when the Coating operation is an external operation.</span></span>

    ![Nyolc útvonalverzió az útvonal oldalon](./media/subcontract03_route-page.png)

4. <span data-ttu-id="d74db-135">A felső ablakban, a **verziók** rácsban, jelölje be a **00042** útvonalverziót az **5-ös** helyhez.</span><span class="sxs-lookup"><span data-stu-id="d74db-135">In the upper pane, in the **Versions** grid, select route version **00042** for site **5**.</span></span>
5. <span data-ttu-id="d74db-136">Az alsó ablakban ,az **áttekintés** fülön, jelölje be a **20-as** (**Cbnt CtSc**) műveletet a rácsban.</span><span class="sxs-lookup"><span data-stu-id="d74db-136">In the lower pane, on the **Overview** tab, select operation **20** (**Cbnt CtSc**) in the grid.</span></span>

    ![A 20-as művelet kiválasztva az 5-ös hely 00042 útvonalverzióhoz](./media/subcontract04_route-version-operation.png)

6. <span data-ttu-id="d74db-138">Válassza ki az **Általános** fület.</span><span class="sxs-lookup"><span data-stu-id="d74db-138">Select the **General** tab.</span></span>

    <span data-ttu-id="d74db-139">Figyelje meg, hogy az **útvonaltípus** mező értéke **szállító**.</span><span class="sxs-lookup"><span data-stu-id="d74db-139">Notice that the field **Route type** field is set to **Vendor**.</span></span> <span data-ttu-id="d74db-140">Ez az érték jelzi, hogy a 20-as (Cbnt CtSc) művelet egy alvállalkozói művelet.</span><span class="sxs-lookup"><span data-stu-id="d74db-140">This value indicates that operation 20 (Cbnt CtSc) is a subcontracted operation.</span></span>

    ![Az útvonaltípus mező értéke szállító az általános fülön](./media/subcontract05_general-tab.png)

7. <span data-ttu-id="d74db-142">Válassza ki az **Erőforrás-követelmények** fület.</span><span class="sxs-lookup"><span data-stu-id="d74db-142">Select the **Resource requirements** tab.</span></span>

    <span data-ttu-id="d74db-143">A képességek használatba kerülnek majd egy alkalmazható erőforrás megkeresésére a termelési ütemezés közben.</span><span class="sxs-lookup"><span data-stu-id="d74db-143">Capabilities will be used to find an applicable resource during production scheduling.</span></span> <span data-ttu-id="d74db-144">A 20-as művelet (Cbnt CtSc) esetében figyelje meg, hogy olyan erőforrásra van szükség, amelynek két képessége van, a **bevonás** és a **bevont kabinetek**.</span><span class="sxs-lookup"><span data-stu-id="d74db-144">For operation 20 (Cbnt CtSc), notice that a resource that has two capabilities, **Coating** and **Coated cabinets**, is required.</span></span>

    ![Bevonás és bevont kabinetek képességek az erőforrás-követelményeknek fülön](./media/subcontract06_resource-requirements-tab.png)

8. <span data-ttu-id="d74db-146">Válassza ki az **Alkalmazható erőforrások** opciót az **Alkalmazható erőforrások** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-146">Select **Applicable resources** to open the **Applicable resources** dialog box.</span></span>

    <span data-ttu-id="d74db-147">Három erőforrás található, amely megfelel a művelethez tartozó erőforrás-követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="d74db-147">Three resources are found that match the resource requirements for the operation.</span></span> <span data-ttu-id="d74db-148">Figyelje meg, a 8851 és 8852 erőforrások **szállító** típusúak.</span><span class="sxs-lookup"><span data-stu-id="d74db-148">Notice that resources 8851 and 8852 are of the **Vendor** type.</span></span>

    ![Három kívánt erőforrás a megfelelő erőforrások párbeszédpanelen](./media/subcontract07_applicable-resources-dialog.png)

9. <span data-ttu-id="d74db-150">Válassza ki az **OK** opciót az **Alkalmazható erőforrások** párbeszédpanel bezárásához és az **Útvonal** oldalra való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="d74db-150">Select **OK** to close the **Applicable resources** dialog box and return to the **Route** page.</span></span>
10. <span data-ttu-id="d74db-151">Zárja be az **Útvonal** oldalt a **Kiadott termék részletei** oldalra való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="d74db-151">Close the **Route** page to return to the **Released product details** page.</span></span>

    ![Megjelent termék részletei oldal](./media/subcontract08_released-product-details-page.png)

11. <span data-ttu-id="d74db-153">A műveleti ablakon, a **Mérnök** lapon válassza ki az **Anyajegyzék verziók** opciót az **Anyajegyzék verziók** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-153">On the Action Pane, on the **Engineer** tab, select **BOM versions** to open the **BOM versions** page.</span></span>

    <span data-ttu-id="d74db-154">Az **Anyagjegyzék-verziók** oldal megjeleníti a négy anyagjegyzéket (BOM), amik a kiadott D8100 termékhez tartoznak.</span><span class="sxs-lookup"><span data-stu-id="d74db-154">The **BOM versions** page shows the four bill of materials (BOM) versions for released product D8100.</span></span> <span data-ttu-id="d74db-155">A 000400 anyajegyzék a költségszámításhoz és a tervezéshez használható, a 00041 anyajegyzék a házon belüli bevonási művelethez használható, és a 00042, valamint a 000043 anyajegyzék az alvállalkozói bevonási művelethez használható.</span><span class="sxs-lookup"><span data-stu-id="d74db-155">BOM 000040 is used for costing and planning, BOM 000041 is used if the Coating operation is done in-house, and BOMs 000042 and 000043 are used if the Coating operation is subcontracted.</span></span>

    <span data-ttu-id="d74db-156">Figyelje meg, hogy az S8050 cikk egy **Szolgáltatás** elemtípusú termék.</span><span class="sxs-lookup"><span data-stu-id="d74db-156">Notice that item S8050 is a product of the **Service** item type.</span></span> <span data-ttu-id="d74db-157">Ez a cikk az alvállalkozói munkát jelöli.</span><span class="sxs-lookup"><span data-stu-id="d74db-157">This item represents the subcontracted work.</span></span>

    ![A négy anyagjegyzék-verzió az anyagjegyzék-verziók oldalon](./media/subcontract09_bom-versions-page.png)

12. <span data-ttu-id="d74db-159">Az **Anyagjegyzéksorok** gyorslapon válassza a **Szerkesztés** opciót az **Anyagjegyzéksor szerkesztése** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-159">On the **Bill of materials lines** FastTab, select **Edit** to open the **Edit BOM line** dialog box.</span></span>

    <span data-ttu-id="d74db-160">Amikor egy termelési rendelés létrehozásra és becslésre kerül a kiadott D8100 termékről, az auotomatikusan generál egy beszerzési rendelést az S8050 cikkről.</span><span class="sxs-lookup"><span data-stu-id="d74db-160">When a production order is created and estimated for released product D8100, a purchase order will be automatically generated for item S8050.</span></span> <span data-ttu-id="d74db-161">Ez a beszerzési rendelés a termelési rendeléshez lesz kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="d74db-161">This purchase order will be linked to the production order.</span></span> <span data-ttu-id="d74db-162">A beszerzési rendelések automatikus létrehozásához a **Sortípus** mezőt **Szállító** értékre kell állítani, és ki kell választani az alvállalkozó szállítói számláját.</span><span class="sxs-lookup"><span data-stu-id="d74db-162">For purchase orders to be automatically generated, the **Line type** field must be set to **Vendor**, and the vendor account for the subcontractor must be selected.</span></span> <span data-ttu-id="d74db-163">Ebben az esetben a szállítói számla USA-801.</span><span class="sxs-lookup"><span data-stu-id="d74db-163">In this case, the vendor account is US-801.</span></span>

    <span data-ttu-id="d74db-164">Figyelje meg, hogy az anyajegyzéksor a műveleti számon (ebben az esetben az 20) keresztül kapcsolódik a bevonás művelethez.</span><span class="sxs-lookup"><span data-stu-id="d74db-164">Notice that the BOM line is connected to the Coating operation through the operation number (in this case, 20).</span></span>

    ![anyajegyzéksor párbeszédpanel szerkesztése](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a><span data-ttu-id="d74db-166">Jelszó létrehozása a raktári dolgozóknak</span><span class="sxs-lookup"><span data-stu-id="d74db-166">Create a password for warehouse workers</span></span>

<span data-ttu-id="d74db-167">Meg kell adni egy jelszót a kéziszámítógépet használó raktári dolgozóknak.</span><span class="sxs-lookup"><span data-stu-id="d74db-167">You must define a password for the warehouse workers who use the hand-held device.</span></span>

1. <span data-ttu-id="d74db-168">Válassza ki a **Raktárkezelés \> Beállítás \> Dolgozó** opciót a **Munkafelhasználók** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-168">Select **Warehouse management \> Setup \> Worker** to open the **Work users** page.</span></span>
2. <span data-ttu-id="d74db-169">A **Felhasználók** gyorslapon válassza ki az **51-es**felhasználó sorát.</span><span class="sxs-lookup"><span data-stu-id="d74db-169">On the **Users** FastTab, select the row for user **51**.</span></span>

    ![Munkafelhasználók oldal](./media/subcontract11_work-users-page.png)

3. <span data-ttu-id="d74db-171">Válassza ki az **Új jelszó létrehozása** opciót.</span><span class="sxs-lookup"><span data-stu-id="d74db-171">Select **Reset password**.</span></span>
4. <span data-ttu-id="d74db-172">A **Jelszó** és a **Jelszó megerősítése** mezőkben adja meg az **1** értéket.</span><span class="sxs-lookup"><span data-stu-id="d74db-172">In the **Password** and **Confirm password** fields, enter **1**.</span></span>
5. <span data-ttu-id="d74db-173">Válassza ki a **Jelszó beállítása** opciót.</span><span class="sxs-lookup"><span data-stu-id="d74db-173">Select **Set password**.</span></span>

## <a name="step-by-step-walkthrough"></a><span data-ttu-id="d74db-174">Útmutató lépésről lépésre</span><span class="sxs-lookup"><span data-stu-id="d74db-174">Step-by-step walkthrough</span></span>

<span data-ttu-id="d74db-175">**Eset és háttér**</span><span class="sxs-lookup"><span data-stu-id="d74db-175">**Scenario and background**</span></span>

<span data-ttu-id="d74db-176">Egy 10 darabos termelési rendelés jön létre a D8100, "Bevont kabinet" termékre.</span><span class="sxs-lookup"><span data-stu-id="d74db-176">A production order of 10 pieces is created for product D8100, "Coated Cabinet."</span></span> <span data-ttu-id="d74db-177">A kabinetek bevonása egy alvállalkozói művelet, amit az US-801 szállító, a Perfect Coating Solutions végez.</span><span class="sxs-lookup"><span data-stu-id="d74db-177">The coating of the cabinets is a sub-contracted operation that is done at vendor US-801, Perfect Coating Solutions.</span></span> <span data-ttu-id="d74db-178">A termelési rendelés három műveletből áll.</span><span class="sxs-lookup"><span data-stu-id="d74db-178">The production order consists of three operations.</span></span> <span data-ttu-id="d74db-179">Az első művelet esetében a kabinet előzetes összeállításra kerül házon belül.</span><span class="sxs-lookup"><span data-stu-id="d74db-179">In the first operation, the cabinet is pre-assembled as an in-house operation.</span></span> <span data-ttu-id="d74db-180">Az előzetes összeállításhoz szükséges anyagok elérhetővé válnak kiválasztásra a nyersanyag raktárban.</span><span class="sxs-lookup"><span data-stu-id="d74db-180">The material for the pre-assembly is released for picking in the raw material warehouse.</span></span> <span data-ttu-id="d74db-181">Az előzetes összeállítás befejezése után az előzetesen összeállított kabinetet a Perfect Coating Solutions-höz küldik két nyersanyaggal együtt, amelyek szükségesek a bevonás művelethez.</span><span class="sxs-lookup"><span data-stu-id="d74db-181">After the pre-assembly is completed, the pre-assembled cabinet is sent to Perfect Coating Solutions together with two materials that are required for the Coating operation.</span></span> <span data-ttu-id="d74db-182">Amikor a bevont kabinet visszaérkezik a szállítótól, akkor az átesik egy végső házon belüli összeállításon, mielőtt befejezettként jelentik.</span><span class="sxs-lookup"><span data-stu-id="d74db-182">When the coated cabinet is received back from the vendor, it goes through a final in-house assembly operation before it's reported as finished.</span></span>

1. <span data-ttu-id="d74db-183">Válassza ki a **Gyártásvezérlés \> Termelési rendelések \> Minden termelési rendelés** opciót a **Minden termelési rendelés** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-183">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
2. <span data-ttu-id="d74db-184">A műveleti ablakon válassza ki az **Új termelési rendelés** opciót a **Termelési rendelés létrehozása** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-184">On the Action Pane, select **New production order** to open the **Create production order** dialog box.</span></span>

    ![Termelési rendelés létrehozása párbeszédpanel](./media/subcontract12_create-production-order-dialog.png)

3. <span data-ttu-id="d74db-186">A **Cikkszám** mezőben válassza ki a **D8100** cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="d74db-186">In the **Item number** field, select **D8100**.</span></span>
4. <span data-ttu-id="d74db-187">A cikkszám kiválasztása után eltűnnek a készletdimenzió-mezők.</span><span class="sxs-lookup"><span data-stu-id="d74db-187">After you select the item number, fields for the inventory dimensions appear.</span></span> <span data-ttu-id="d74db-188">A **Szín** mezőben válassza ki a **Chrome** opciót.</span><span class="sxs-lookup"><span data-stu-id="d74db-188">In the **Color** field, select **Chrome**.</span></span>

    <span data-ttu-id="d74db-189">Megjelenik egy üzenetpanel, amely rákérdez, hogy az anyagjegyzék és az útvonal aktív verzióit be kell-e szúrni.</span><span class="sxs-lookup"><span data-stu-id="d74db-189">A message box appears that asks whether the active versions for the BOM and route should be inserted.</span></span>

    ![Üzenetpanel](./media/subcontract13_message-box.png)

5. <span data-ttu-id="d74db-191">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d74db-191">Select **Yes**.</span></span> 

    <span data-ttu-id="d74db-192">A **Termelési rendelés létrehozása** párbeszédpanelen a D8100 termék anyagjegyzékének és útvonalának aktív verziói automatikusan kiválasztódnak az **Anyagjegyzékszám** és az **Útvonalszám** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="d74db-192">In the **Create production order** dialog box, the active versions of the BOM and route for product D8100 are automatically selected in the **BOM number** and **Route number** fields, respectively.</span></span> <span data-ttu-id="d74db-193">Ebben az esetben a **000040** anyajegyzék és a **000040** útvonal vannak kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="d74db-193">In this case, BOM **000040** and route **000040** are selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d74db-194">Az anyagjegyzék és az útvonal esetében is a 000040 verzió használatos a költségszámításhoz és a tervezéshez.</span><span class="sxs-lookup"><span data-stu-id="d74db-194">For both the BOM and the route, version 000040 is used for costing and planning.</span></span>

6. <span data-ttu-id="d74db-195">A **Site** mezőben válasszon ki a **5** értéket.</span><span class="sxs-lookup"><span data-stu-id="d74db-195">In the **Site** field, select **5**.</span></span>
7. <span data-ttu-id="d74db-196">A **Raktár** mezőben válassza ki az **51** értéket.</span><span class="sxs-lookup"><span data-stu-id="d74db-196">In the **Warehouse** field, select **51**.</span></span>
8. <span data-ttu-id="d74db-197">Az **Anyagjegyzékszám** és az **Útvonalszám** mezők értékét változtassa az automatikusan kiválasztottról a **000042** értékre.</span><span class="sxs-lookup"><span data-stu-id="d74db-197">In the **BOM number** and **Route number** fields, change the value that was automatically selected to **000042**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d74db-198">Az anyagjegyzék és az útvonal esetében is a 000042 verzió használatos a kabinetbevonás US-801 szállítóhoz való alvállalkozásba adásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-198">For both the BOM and the route, version 000042 is used to subcontract the coating of the cabinet to vendor US-801.</span></span>

    ![A termelési rendelés létrehozása párbeszédpanelen beállított értékek](./media/subcontract14_create-production-order-dialog-set.png)

9. <span data-ttu-id="d74db-200">Válassza ki a **Létrehozás** opciót a termelési rendelés létrehozásához, és térjen vissza a **Minden termelési rendelés** oldalra.</span><span class="sxs-lookup"><span data-stu-id="d74db-200">Select **Create** to create the production order and return to the **All production orders** page.</span></span>

    ![Új termelési rendelés a minden termelési rendelés oldalon](./media/subcontract15_new-production-order.png)

10. <span data-ttu-id="d74db-202">A műveleti ablakon, a **Termelési rendelés** lapon válassza ki a **Becslés** opciót a **Becslés** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-202">On the Action Pane, on the **Production order** tab, select **Estimate** to open the **Estimate** dialog box.</span></span>

    ![Becslés párbeszédpanel](./media/subcontract16_estimate-dialog.png)

11. <span data-ttu-id="d74db-204">Válassza ki az **OK** opciót a becslés megerősítéséhez, és térjen vissza a **Minden termelési rendelés** oldalra.</span><span class="sxs-lookup"><span data-stu-id="d74db-204">Select **OK** to confirm the estimate and return to the **All production orders** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d74db-205">A termelési rendelés becslésekor létrejön az USA-801 szállító számára egy beszerzési rendelés, amely az S8050 szolgáltatási tételről szól.</span><span class="sxs-lookup"><span data-stu-id="d74db-205">When the production order is estimated, the purchase order for service item S8050 is generated for vendor US-801.</span></span>

12. <span data-ttu-id="d74db-206">A műveleti panelen, a **Termelési rendelés** lapon válassza az **Anyagjegyzék** elemet az **Anyagjegyzék** lap megnyitásához, amelyen megtekintheti az anyagjegyzéksorokat a termelési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="d74db-206">On the Action Pane, on the **Production order** tab, select **BOM** to open the **BOM** page, where you can view the BOM lines for the production order.</span></span>

    <span data-ttu-id="d74db-207">Figyelje meg az S8050 szolgáltatási tételnél, hogy van egy hivatkozás a beszerzési rendelésre, amely akkor generálódott, amikor a termelési rendelést megbecsülték.</span><span class="sxs-lookup"><span data-stu-id="d74db-207">For service item S8050, notice that there is a reference to the purchase order that was generated when the production order was estimated.</span></span>

    ![Termelési rendelések anyagjegyzéksorai az Anyagjegyzék lapon](./media/subcontract17_production-order-bom-lines.png)

13. <span data-ttu-id="d74db-209">Zárja be az **Anyagjegyzék** lapot a **Minden termelési rendelés** lapra való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="d74db-209">Close the **BOM** page to return to the **All production orders** page.</span></span>
14. <span data-ttu-id="d74db-210">A mműveleti ablaktábla **Ütemezés** lapján válassza ki a **Munkák ütemezése** opciót a **Feladatütemezés** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-210">On the Action Pane, on the **Schedule** tab, select **Schedule jobs** to open the **Job scheduling** dialog box.</span></span>
15. <span data-ttu-id="d74db-211">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="d74db-211">Specify the following values:</span></span>

    - <span data-ttu-id="d74db-212">Az **Ütemezés iránya** mezőben válassza ki a **Holnaptól továbbítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d74db-212">In the **Scheduling direction** field, select **Forward from tomorrow**.</span></span>
    - <span data-ttu-id="d74db-213">Állítsa a **Véges kapacitás** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="d74db-213">Set the **Finite capacity** option to **Yes**.</span></span>

    ![Feladatütemezés párbeszédpanel](./media/subcontract18_job-scheduling-dialog.png)

16. <span data-ttu-id="d74db-215">Válassza ki az **OK** opciót az **Feladatütemezés** párbeszédpanel bezárásához és a **Minden termelési rendelés** oldalra való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="d74db-215">Select **OK** to close the **Job scheduling** dialog box and return to the **All production orders** page.</span></span>
17. <span data-ttu-id="d74db-216">A műveleti ablaktáblán, az **Ütemezés** lapon válassza a **Gantt** elemet a **Gantt-diagram – erőforrás nézet** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-216">On the Action Pane, on the **Schedule** tab, select **Gantt** to open the **Gantt chart - Resource view** page.</span></span>

    <span data-ttu-id="d74db-217">A Gantt-diagram vizuálisan jeleníti meg a termelési feladatok erőforrás-ütemezését.</span><span class="sxs-lookup"><span data-stu-id="d74db-217">The Gantt chart provides a visual overview of how the production jobs are scheduled on the resources.</span></span> <span data-ttu-id="d74db-218">Figyelje meg, hogy a Külső bevonás művelete három feladatból áll: egy feldolgozási feladatból, egy szállítási feladatból és egy várakozási idő típusú feladatból.</span><span class="sxs-lookup"><span data-stu-id="d74db-218">Notice that the external Coating operation consists of three jobs: a process job, a transport job, and a queue time job.</span></span>

    ![Gantt-diagram a Gantt-diagramon – Erőforrás nézet lap](./media/subcontract19_gantt-chart.png)

18. <span data-ttu-id="d74db-220">Zárja be a **Gantt-diagram – Erőforrás nézet** lapot a **Minden termelési rendelés** lapra való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="d74db-220">Close the **Gantt chart - Resource view** page to return to the **All production orders** page.</span></span>
19. <span data-ttu-id="d74db-221">A műveleti ablakon, a **Termelési rendelés** lapon válassza ki a **Kiadás** opciót a **Kiadás** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-221">On the Action Pane, on the **Production order** tab, select **Release** to open the **Release** dialog box.</span></span>

    ![Kiadás párbeszédpanel](./media/subcontract20_release-dialog.png)

20. <span data-ttu-id="d74db-223">Kattintson az **OK** gombra a **Kiadás** párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-223">Select **OK** to close the **Release** dialog box.</span></span>
21. <span data-ttu-id="d74db-224">Válassza ki a **Gyártásvezérlés \> Időszakos feladatok \> Kiadás raktárba \> Darabjegyzék és receptúrasorok automatikus kiadása** lehetőséget a **Darabjegyzék és receptúrasorok automatikus kiadása** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-224">Select **Production control \> Periodic tasks \> Release to warehouse \> Automatic release of BOM and formula lines** to open the **Automatic release of BOM and formula lines** dialog box.</span></span>

    ![Darabjegyzék és receptúrasorok automatikus kiadása párbeszédpanel](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. <span data-ttu-id="d74db-226">Válassza az **OK** lehetőséget az Anyagjegyzék és receptúrasorok automatikus kiadása feladat futtatásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-226">Select **OK** to run the Automatic release of BOM and formula lines job.</span></span>

    <span data-ttu-id="d74db-227">Ez a feladat felszabadítja a nyersanyagok raktárba való kitárolásának munkáját.</span><span class="sxs-lookup"><span data-stu-id="d74db-227">This job releases pick work for raw materials to the warehouse.</span></span>

23. <span data-ttu-id="d74db-228">Válassza ki a **Gyártásvezérlés \> Termelési rendelések \> Minden termelési rendelés** opciót a **Minden termelési rendelés** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-228">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
24. <span data-ttu-id="d74db-229">A gyorsszűrés mező segítségével válassza ki azt a termelési rendelést, amelyen dolgozik.</span><span class="sxs-lookup"><span data-stu-id="d74db-229">Use the quick filter field to select the production order that you've been working on.</span></span>
25. <span data-ttu-id="d74db-230">A műveleti ablaktáblán, a **Raktár** lapon válassza ki a **Munka részletes adatai** opciót a **Munka** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-230">On the Action Pane, on the **Warehouse** tab, select **Work details** to open the **Work** page.</span></span>

    <span data-ttu-id="d74db-231">Figyelje meg, hogy a lap kétféle munkát jelenít meg a nyersanyag kitárolásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-231">Notice that the page shows two sets of work for raw material picking.</span></span> <span data-ttu-id="d74db-232">Az első munka az M8100 és M8101 anyagokra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d74db-232">The first work is for materials M8100 and M8101.</span></span> <span data-ttu-id="d74db-233">Ezeket az anyagokat a 10-es művelet használja fel.</span><span class="sxs-lookup"><span data-stu-id="d74db-233">These materials are consumed by operation 10.</span></span> <span data-ttu-id="d74db-234">A másodi munka az M8202 és M8250 anyagokra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d74db-234">The second work is for materials M8202 and M8250.</span></span> <span data-ttu-id="d74db-235">Ezek az anyagok a 20-as művelet során kerülnek felhasználásra, amely egy alvállalkozói művelet.</span><span class="sxs-lookup"><span data-stu-id="d74db-235">These materials are consumed by operation 20, which is the subcontracted operation.</span></span>

    ![A Munka lap kétféle munkát jelenít meg a nyersanyag kitárolásához.](./media/subcontract22_work-page.png)

26. <span data-ttu-id="d74db-237">Indítsa el a raktár alkalmazást a 10-es művelet raktári munkájának feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-237">Start the warehouse app to process the warehouse work for operation 10.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. <span data-ttu-id="d74db-238">Válassza ki a **Gyártásvezérlés \> Termelési rendelések \> Minden termelési rendelés** opciót a **Minden termelési rendelés** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-238">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
28. <span data-ttu-id="d74db-239">A gyorsszűrés mező segítségével válassza ki azt a termelési rendelést, amelyen dolgozik.</span><span class="sxs-lookup"><span data-stu-id="d74db-239">Use the quick filter field to select the production order that you've been working on.</span></span>
29. <span data-ttu-id="d74db-240">A műveleti ablakon, a **Termelési rendelés** lapon válassza ki az **Indítás** opciót az **Indítás** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-240">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
30. <span data-ttu-id="d74db-241">Az **Általános** lapon adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="d74db-241">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="d74db-242">A **Kezdő műveletszám**</span><span class="sxs-lookup"><span data-stu-id="d74db-242">In the **From Oper. No.**</span></span> <span data-ttu-id="d74db-243">mezőben válassza a **10** értéket.</span><span class="sxs-lookup"><span data-stu-id="d74db-243">field, select **10**.</span></span>
    - <span data-ttu-id="d74db-244">A **Záró műveletszám**</span><span class="sxs-lookup"><span data-stu-id="d74db-244">In the **To Oper. No.**</span></span> <span data-ttu-id="d74db-245">mezőben válassza a **10** értéket.</span><span class="sxs-lookup"><span data-stu-id="d74db-245">field, select **10**.</span></span>

    ![Az Általános lapon beállított értékek](./media/subcontract23_start-dialog.png)

31. <span data-ttu-id="d74db-247">Válassza ki az **OK** opciót az **Indítás** párbeszédpanel bezárásához és a **Minden termelési rendelés** oldalra való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="d74db-247">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="d74db-248">Vegye figyelembe, hogy a termelési rendelés állapota ekkor **Elindítva**.</span><span class="sxs-lookup"><span data-stu-id="d74db-248">Notice that the status of the production order is now **Started**.</span></span> <span data-ttu-id="d74db-249">A 10-es művelet anyagait a kitárolási lista naplójának automatikus feladása használja el.</span><span class="sxs-lookup"><span data-stu-id="d74db-249">The materials for operation 10 are consumed by an automatic posting of the picking list journal.</span></span> <span data-ttu-id="d74db-250">A 10-es művelet időfelhasználásának elszámolása egy útvonalkártya-napló automatikus feladásával történik.</span><span class="sxs-lookup"><span data-stu-id="d74db-250">Time consumption for operation 10 is accounted for by an automatic posting of a route card journal.</span></span>

32. <span data-ttu-id="d74db-251">Indítsa el a raktár alkalmazást a 20-as művelet raktári munkájának feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-251">Start the warehouse app to process the warehouse work for operation 20.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. <span data-ttu-id="d74db-252">A műveleti ablakon, a **Termelési rendelés** lapon válassza ki az **Indítás** opciót az **Indítás** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-252">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
34. <span data-ttu-id="d74db-253">Az **Általános** lapon adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="d74db-253">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="d74db-254">A **Kezdő műveletszám**</span><span class="sxs-lookup"><span data-stu-id="d74db-254">In the **From Oper. No.**</span></span> <span data-ttu-id="d74db-255">mezőben válassza a **20** értéket.</span><span class="sxs-lookup"><span data-stu-id="d74db-255">field, select **20**.</span></span>
    - <span data-ttu-id="d74db-256">A **Záró műveletszám**</span><span class="sxs-lookup"><span data-stu-id="d74db-256">In the **To Oper. No.**</span></span> <span data-ttu-id="d74db-257">mezőben válassza a **20** értéket.</span><span class="sxs-lookup"><span data-stu-id="d74db-257">field, select **20**.</span></span>
    - <span data-ttu-id="d74db-258">Írja be a **10** értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d74db-258">In the **Quantity** field, enter **10**.</span></span>
    - <span data-ttu-id="d74db-259">Válassza a **Nem** lehetőséget a **Kitárolási lista feladása most** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d74db-259">Set the **Post picking list now** option to **No**.</span></span>

    ![Az Általános lapon beállított értékek](./media/subcontract24_general-tab.png)

35. <span data-ttu-id="d74db-261">Válassza ki az **OK** opciót az **Indítás** párbeszédpanel bezárásához és a **Minden termelési rendelés** oldalra való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="d74db-261">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="d74db-262">Létrejön egy kitárolási lista a külső bevonás műveletének anyagaihoz és a szolgáltatási tételhez.</span><span class="sxs-lookup"><span data-stu-id="d74db-262">A picking list is created for the materials that are used for the Coating operation, and for the service item.</span></span> <span data-ttu-id="d74db-263">A szolgáltatási tétel az alvállalkozói művelet költségét jelenti.</span><span class="sxs-lookup"><span data-stu-id="d74db-263">The service item represents the cost of the subcontracted operation.</span></span>

36. <span data-ttu-id="d74db-264">A műveleti ablaktáblán, a **Nézet** lapon válassza a **Kitárolási lista** elemet a **Kitárolási lista** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-264">On the Action Pane, on the **View** tab, select **Picking list** to open the **Picking list** page.</span></span>
37. <span data-ttu-id="d74db-265">Válassza ki azt a kitárolási listát, amely nincs feladva, majd válassza ki a napló számát a naplósorok megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="d74db-265">Select the picking list that isn't posted, and then select the journal number to view the journal lines.</span></span>

    ![Naplósorok a Kitárolási lista lapon](./media/subcontract25_picking-list.png)

38. <span data-ttu-id="d74db-267">A Műveleti ablaktáblán válassza a **Nyomtatás**\>**Kitárolási lista jelentése** pontot a **Kitárolási lista jelentése** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-267">On the Action Pane, select **Print** \> **Picking list report** to open the **Picking list report** dialog box.</span></span>
39. <span data-ttu-id="d74db-268">Állítsa a **Szállítólevél-elrendezés használata** opciót **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="d74db-268">Set the **Use delivery note layout** option to **Yes**.</span></span>

    ![Kitárolási lista jelentésének párbeszédpanele](./media/subcontract26_picking-list-report-dialog.png)

40. <span data-ttu-id="d74db-270">Válassza az **OK** lehetőséget egy **Kitárolási lista** jelentés készítéséhez.</span><span class="sxs-lookup"><span data-stu-id="d74db-270">Select **OK** to generate a **Picking list** report.</span></span>

    <span data-ttu-id="d74db-271">Ebben az esetben a szállítói szállítólevél nyomtatása a termelési kitárolási lista naplójából történik.</span><span class="sxs-lookup"><span data-stu-id="d74db-271">In this case, a vendor delivery note is printed from the production picking list journal.</span></span> <span data-ttu-id="d74db-272">A szállítólevél meghatározza azokat az anyagokat, amelyek a külső bevonást elvégző szállítóhoz elszállítottak.</span><span class="sxs-lookup"><span data-stu-id="d74db-272">The delivery note specifies the materials that are shipped to the vendor who will do the Coating operation.</span></span>

    ![Kitárolási lista jelentése](./media/subcontract27_picking-list-report.png)

41. <span data-ttu-id="d74db-274">Zárja be a **Kitárolási lista** jelentést, ha vissza szeretne térni a **Kitárolási lista** oldalra.</span><span class="sxs-lookup"><span data-stu-id="d74db-274">Close the **Picking list** report to return to the **Picking list** page.</span></span>
42. <span data-ttu-id="d74db-275">A műveleti ablaktáblán kattintson a **Feladás** gombra a **Napló feladása** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-275">On the Action Pane, select **Post** to open the **Post journal** dialog box.</span></span>

    ![Napló feladása párbeszédpanel](./media/subcontract28_post-journal-dialog.png)

43. <span data-ttu-id="d74db-277">Kattintson az **OK** gombra a **Napló feladása** párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-277">Select **OK** to close the **Post journal** dialog box.</span></span>
44. <span data-ttu-id="d74db-278">Nyissa meg a beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="d74db-278">Open the purchase order.</span></span>

    ![Beszerzési rendelés lap](./media/subcontract29_purchase-order-page.png)

45. <span data-ttu-id="d74db-280">A **Beszerzés** lap műveleti ablaktáblájában kattintson a **Megerősítés** pontra.</span><span class="sxs-lookup"><span data-stu-id="d74db-280">On the Action Pane, on the **Purchase** tab, select **Confirm**.</span></span>
46. <span data-ttu-id="d74db-281">Kattintson a **Feladás** gombra a **Napló feladása** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d74db-281">Select **Post** to open the **Post journal** dialog box.</span></span>
47. <span data-ttu-id="d74db-282">Válassza ki az **OK** opciót a **Napló feladása** párbeszédpanel bezárásához és a **Beszerzési rendelés** oldalra való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="d74db-282">Select **OK** to close the **Post journal** dialog box and return to the **Purchase order** page.</span></span>
48. <span data-ttu-id="d74db-283">Módosítsa az egységárat **33** értékről **40** értékre.</span><span class="sxs-lookup"><span data-stu-id="d74db-283">Change the unit price from **33** to **40**.</span></span>

    ![Módosult az egységár a Beszerzési rendelés lapon](./media/subcontract30_unit-price.png)

49. <span data-ttu-id="d74db-285">Erősítse meg újra a beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="d74db-285">Confirm the purchase order again.</span></span>
50. <span data-ttu-id="d74db-286">Termékbevételezés.</span><span class="sxs-lookup"><span data-stu-id="d74db-286">Product receipt.</span></span>

    ![Termékbevételezés feladásának párbeszédpanele](./media/subcontract31_posting-product-receipt-dialog.png)

51. <span data-ttu-id="d74db-288">Beszerzési számla.</span><span class="sxs-lookup"><span data-stu-id="d74db-288">Purchase invoice.</span></span>
52. <span data-ttu-id="d74db-289">Egyeztetési állapot frissítése.</span><span class="sxs-lookup"><span data-stu-id="d74db-289">Update the match status.</span></span>

    ![Szállítói számla lapja](./media/subcontract32_vendor-invoice-page.png)

53. <span data-ttu-id="d74db-291">Készként jelentés.</span><span class="sxs-lookup"><span data-stu-id="d74db-291">Report as finished.</span></span>

    ![Jlentés készként párbeszédpanel](./media/subcontract33_report-as-finished-dialog.png)

54. <span data-ttu-id="d74db-293">Vége.</span><span class="sxs-lookup"><span data-stu-id="d74db-293">End.</span></span>

    ![Vége párbeszédpanel](./media/subcontract34_end-dialog.png)

55. <span data-ttu-id="d74db-295">Költség összehasonlítása.</span><span class="sxs-lookup"><span data-stu-id="d74db-295">Cost comparison.</span></span>

    ![Költség-összehasonlítás diagramjai](./media/subcontract35_cost-comparison-charts.png)

<span data-ttu-id="d74db-297">Hiányzó beállítás az adatoknál.</span><span class="sxs-lookup"><span data-stu-id="d74db-297">Missing setup in data.</span></span>
