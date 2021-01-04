---
title: Az értékesítési rendelés állapot mezőihez tartozó hozzárendelés beállítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani az értékesítési rendelés állapotmezőit a kettős íráshoz.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 5855581100606003c1faf6b88a0ab234ae378893
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4453365"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a><span data-ttu-id="3573e-103">Az értékesítési rendelés állapot mezőihez tartozó hozzárendelés beállítása</span><span class="sxs-lookup"><span data-stu-id="3573e-103">Set up the mapping for the sales order status fields</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3573e-104">Az értékesítési rendelés állapotát jelző mezők a Microsoft Dynamics 365 Supply Chain Management és a Dynamics 365 Sales alkalmazásban eltérő számértékekkel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="3573e-104">The fields that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="3573e-105">Ezeknek a mezőknek a leképezéséhez a kettős írásban további beállítás szükséges.</span><span class="sxs-lookup"><span data-stu-id="3573e-105">Additional setup is required to map these fields in dual-write.</span></span>

## <a name="fields-in-supply-chain-management"></a><span data-ttu-id="3573e-106">A Supply Chain Management mezői</span><span class="sxs-lookup"><span data-stu-id="3573e-106">Fields in Supply Chain Management</span></span>

<span data-ttu-id="3573e-107">A Supply Chain Management alkalmazásban két mező tükrözi az értékesítési rendelés állapotát.</span><span class="sxs-lookup"><span data-stu-id="3573e-107">In Supply Chain Management, two fields reflect the status of the sales order.</span></span> <span data-ttu-id="3573e-108">A leképezni kívánt mezők az **Állapot** és a **Dokumentum állapota**.</span><span class="sxs-lookup"><span data-stu-id="3573e-108">The fields that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="3573e-109">Az **Állapot** számozása a rendelés általános állapotát határozza meg.</span><span class="sxs-lookup"><span data-stu-id="3573e-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="3573e-110">Ez az állapot jelenik meg a rendelés fejlécében.</span><span class="sxs-lookup"><span data-stu-id="3573e-110">This status is shown on the order header.</span></span>

<span data-ttu-id="3573e-111">Az **Állapot** számozás a következő értékekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="3573e-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="3573e-112">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="3573e-112">Open Order</span></span>
- <span data-ttu-id="3573e-113">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="3573e-113">Delivered</span></span>
- <span data-ttu-id="3573e-114">Számlázva</span><span class="sxs-lookup"><span data-stu-id="3573e-114">Invoiced</span></span>
- <span data-ttu-id="3573e-115">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="3573e-115">Cancelled</span></span>

<span data-ttu-id="3573e-116">A **Dokumentum állapota** felsorolása a rendeléshez létrehozott legfrissebb dokumentumot határozza meg.</span><span class="sxs-lookup"><span data-stu-id="3573e-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="3573e-117">Ha például a rendelés meg van erősítve, akkor ez a dokumentum egy értékesítési rendelés visszaigazolása.</span><span class="sxs-lookup"><span data-stu-id="3573e-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="3573e-118">Ha egy értékesítési rendelést részben számláznak, és a fennmaradó sor meg van erősítve, akkor a dokumentum állapota a **Számla** marad, mivel a számla később jön létre a folyamatban.</span><span class="sxs-lookup"><span data-stu-id="3573e-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="3573e-119">A **Dokumentum állapota** felsorolás a következő értékekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="3573e-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="3573e-120">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="3573e-120">Confirmation</span></span>
- <span data-ttu-id="3573e-121">Kitárolási lista</span><span class="sxs-lookup"><span data-stu-id="3573e-121">Picking List</span></span>
- <span data-ttu-id="3573e-122">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="3573e-122">Packing Slip</span></span>
- <span data-ttu-id="3573e-123">Számla</span><span class="sxs-lookup"><span data-stu-id="3573e-123">Invoice</span></span>

## <a name="fields-in-sales"></a><span data-ttu-id="3573e-124">A Sales mezői</span><span class="sxs-lookup"><span data-stu-id="3573e-124">Fields in Sales</span></span>

<span data-ttu-id="3573e-125">A Sales alkalmazásban két mező jelzi az értékesítési rendelés állapotát.</span><span class="sxs-lookup"><span data-stu-id="3573e-125">In Sales, two fields indicate the status of the order.</span></span> <span data-ttu-id="3573e-126">A leképezni kívánt mezők az **Állapot** és a **Feldolgozás állapota**.</span><span class="sxs-lookup"><span data-stu-id="3573e-126">The fields that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="3573e-127">Az **Állapot** számozása a rendelés általános állapotát határozza meg.</span><span class="sxs-lookup"><span data-stu-id="3573e-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="3573e-128">Az alábbi értékekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="3573e-128">It has the following values:</span></span>

- <span data-ttu-id="3573e-129">Aktív</span><span class="sxs-lookup"><span data-stu-id="3573e-129">Active</span></span>
- <span data-ttu-id="3573e-130">Elküldve</span><span class="sxs-lookup"><span data-stu-id="3573e-130">Submitted</span></span>
- <span data-ttu-id="3573e-131">Teljesített</span><span class="sxs-lookup"><span data-stu-id="3573e-131">Fulfilled</span></span>
- <span data-ttu-id="3573e-132">Számlázva</span><span class="sxs-lookup"><span data-stu-id="3573e-132">Invoiced</span></span>
- <span data-ttu-id="3573e-133">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="3573e-133">Cancelled</span></span>

<span data-ttu-id="3573e-134">A **Feldolgozási állapot** számozása azért lett bevezetve, hogy az állapot pontosabban legyen megfeleltetve a Supply Chain Management alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="3573e-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="3573e-135">A következő táblázat bemutatja a Supply Chain Management **Feldolgozási állapotának** leképezését.</span><span class="sxs-lookup"><span data-stu-id="3573e-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="3573e-136">Feldolgozás állapota</span><span class="sxs-lookup"><span data-stu-id="3573e-136">Processing Status</span></span>   | <span data-ttu-id="3573e-137">A Supply Chain Management állapotai</span><span class="sxs-lookup"><span data-stu-id="3573e-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="3573e-138">Dokumentum állapota a Supply Chain Management alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="3573e-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="3573e-139">Aktív</span><span class="sxs-lookup"><span data-stu-id="3573e-139">Active</span></span>              | <span data-ttu-id="3573e-140">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="3573e-140">Open Order</span></span>                        | <span data-ttu-id="3573e-141">None</span><span class="sxs-lookup"><span data-stu-id="3573e-141">None</span></span>                                       |
| <span data-ttu-id="3573e-142">Visszaigazolva</span><span class="sxs-lookup"><span data-stu-id="3573e-142">Confirmed</span></span>           | <span data-ttu-id="3573e-143">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="3573e-143">Open Order</span></span>                        | <span data-ttu-id="3573e-144">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="3573e-144">Confirmation</span></span>                               |
| <span data-ttu-id="3573e-145">Kitárolva</span><span class="sxs-lookup"><span data-stu-id="3573e-145">Picked</span></span>              | <span data-ttu-id="3573e-146">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="3573e-146">Open Order</span></span>                        | <span data-ttu-id="3573e-147">Kitárolási lista</span><span class="sxs-lookup"><span data-stu-id="3573e-147">Picking List</span></span>                               |
| <span data-ttu-id="3573e-148">Részlegesen kiszállítva</span><span class="sxs-lookup"><span data-stu-id="3573e-148">Partially Delivered</span></span> | <span data-ttu-id="3573e-149">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="3573e-149">Open Order</span></span>                        | <span data-ttu-id="3573e-150">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="3573e-150">Packing Slip</span></span>                               |
| <span data-ttu-id="3573e-151">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="3573e-151">Delivered</span></span>           | <span data-ttu-id="3573e-152">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="3573e-152">Delivered</span></span>                         | <span data-ttu-id="3573e-153">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="3573e-153">Packing Slip</span></span>                               |
| <span data-ttu-id="3573e-154">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="3573e-154">Partially Invoiced</span></span>  | <span data-ttu-id="3573e-155">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="3573e-155">Delivered</span></span>                         | <span data-ttu-id="3573e-156">Számla</span><span class="sxs-lookup"><span data-stu-id="3573e-156">Invoice</span></span>                                    |
| <span data-ttu-id="3573e-157">Számlázva</span><span class="sxs-lookup"><span data-stu-id="3573e-157">Invoiced</span></span>            | <span data-ttu-id="3573e-158">Számlázva</span><span class="sxs-lookup"><span data-stu-id="3573e-158">Invoiced</span></span>                          | <span data-ttu-id="3573e-159">Számla</span><span class="sxs-lookup"><span data-stu-id="3573e-159">Invoice</span></span>                                    |
| <span data-ttu-id="3573e-160">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="3573e-160">Cancelled</span></span>           | <span data-ttu-id="3573e-161">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="3573e-161">Cancelled</span></span>                         | <span data-ttu-id="3573e-162">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="3573e-162">Not applicable</span></span>                             |

<span data-ttu-id="3573e-163">A következő táblázat bemutatja a **Feldolgozási állapotának** leképezését a Sales és a Supply Chain Management között.</span><span class="sxs-lookup"><span data-stu-id="3573e-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="3573e-164">Feldolgozás állapota</span><span class="sxs-lookup"><span data-stu-id="3573e-164">Processing Status</span></span>   | <span data-ttu-id="3573e-165">Állapot a Sales alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="3573e-165">Status in Sales</span></span> | <span data-ttu-id="3573e-166">A Supply Chain Management állapotai</span><span class="sxs-lookup"><span data-stu-id="3573e-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="3573e-167">Aktív</span><span class="sxs-lookup"><span data-stu-id="3573e-167">Active</span></span>              | <span data-ttu-id="3573e-168">Aktív</span><span class="sxs-lookup"><span data-stu-id="3573e-168">Active</span></span>          | <span data-ttu-id="3573e-169">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="3573e-169">Open Order</span></span>                        |
| <span data-ttu-id="3573e-170">Visszaigazolva</span><span class="sxs-lookup"><span data-stu-id="3573e-170">Confirmed</span></span>           | <span data-ttu-id="3573e-171">Elküldve</span><span class="sxs-lookup"><span data-stu-id="3573e-171">Submitted</span></span>       | <span data-ttu-id="3573e-172">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="3573e-172">Open Order</span></span>                        |
| <span data-ttu-id="3573e-173">Kitárolva</span><span class="sxs-lookup"><span data-stu-id="3573e-173">Picked</span></span>              | <span data-ttu-id="3573e-174">Elküldve</span><span class="sxs-lookup"><span data-stu-id="3573e-174">Submitted</span></span>       | <span data-ttu-id="3573e-175">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="3573e-175">Open Order</span></span>                        |
| <span data-ttu-id="3573e-176">Részlegesen kiszállítva</span><span class="sxs-lookup"><span data-stu-id="3573e-176">Partially Delivered</span></span> | <span data-ttu-id="3573e-177">Aktív</span><span class="sxs-lookup"><span data-stu-id="3573e-177">Active</span></span>          | <span data-ttu-id="3573e-178">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="3573e-178">Open Order</span></span>                        |
| <span data-ttu-id="3573e-179">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="3573e-179">Partially Invoiced</span></span>  | <span data-ttu-id="3573e-180">Aktív</span><span class="sxs-lookup"><span data-stu-id="3573e-180">Active</span></span>          | <span data-ttu-id="3573e-181">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="3573e-181">Open Order</span></span>                        |
| <span data-ttu-id="3573e-182">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="3573e-182">Partially Invoiced</span></span>  | <span data-ttu-id="3573e-183">Teljesített</span><span class="sxs-lookup"><span data-stu-id="3573e-183">Fulfilled</span></span>       | <span data-ttu-id="3573e-184">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="3573e-184">Delivered</span></span>                         |
| <span data-ttu-id="3573e-185">Számlázva</span><span class="sxs-lookup"><span data-stu-id="3573e-185">Invoiced</span></span>            | <span data-ttu-id="3573e-186">Számlázva</span><span class="sxs-lookup"><span data-stu-id="3573e-186">Invoiced</span></span>        | <span data-ttu-id="3573e-187">Számlázva</span><span class="sxs-lookup"><span data-stu-id="3573e-187">Invoiced</span></span>                          |
| <span data-ttu-id="3573e-188">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="3573e-188">Cancelled</span></span>           | <span data-ttu-id="3573e-189">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="3573e-189">Cancelled</span></span>       | <span data-ttu-id="3573e-190">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="3573e-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="3573e-191">Beállítás</span><span class="sxs-lookup"><span data-stu-id="3573e-191">Setup</span></span>

<span data-ttu-id="3573e-192">Az értékesítési rendelés állapot mezőinek leképezésének beállításához az **IsSOPIntegrationEnabled** és a **isIntegrationUser** attribútumokat engedélyeznie kell.</span><span class="sxs-lookup"><span data-stu-id="3573e-192">To set up the mapping for the sales order status fields, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="3573e-193">Az **IsSOPIntegrationEnabled** attribútum engedélyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3573e-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="3573e-194">Lépjen egy böngészőben a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations` címre.</span><span class="sxs-lookup"><span data-stu-id="3573e-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="3573e-195">Cserélje le a **\<test-name\>** elemet a vállalat a Sales alkalmazásra mutató hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3573e-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="3573e-196">A megnyitott lapon keresse meg a **organizationid** elemet, és jegyezze fel az értéket.</span><span class="sxs-lookup"><span data-stu-id="3573e-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Az organizationid megkeresése](media/sales-map-orgid.png)

3. <span data-ttu-id="3573e-198">A Sales alkalmazásban meg a böngésző konzolt, majd futtassa a következő parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="3573e-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="3573e-199">A 2. lépésből használja az **organizationid** értéket.</span><span class="sxs-lookup"><span data-stu-id="3573e-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![JavaScript-kód a böngésző konzolján](media/sales-map-script.png)

4. <span data-ttu-id="3573e-201">Ellenőrizze, hogy a **IsSOPIntegrationEnabled** **igaz** értékre legyen állítva.</span><span class="sxs-lookup"><span data-stu-id="3573e-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="3573e-202">A 1. lépésből használja az URL-címet az érték ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="3573e-202">Use the URL from step 1 to check the value.</span></span>

    ![A IsSOPIntegrationEnabled igaz értékre van állítva](media/sales-map-integration-enabled.png)

<span data-ttu-id="3573e-204">Az **isIntegrationUser** attribútum engedélyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3573e-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="3573e-205">A Sales alkalmazásban nyissa meg a **Beállítás \> Testreszabás \> Rendszer testreszabása** lehetőséget, válassz a **Felhasználói entitás** lehetőséget, és nyissa meg a **Képernyő \> Felhasználó** elemet.</span><span class="sxs-lookup"><span data-stu-id="3573e-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User entity**, and then open **Form \> User**.</span></span>

    ![A feéhasználó képernyő megnyitása](media/sales-map-user.png)

2. <span data-ttu-id="3573e-207">A Mezőkezelőben keresse meg **Integráció felhasználói mód** lehetőséget, majd kattintson rá duplán, hogy hozzáadja a képernyőhöz.</span><span class="sxs-lookup"><span data-stu-id="3573e-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="3573e-208">Mentse el a módosítást.</span><span class="sxs-lookup"><span data-stu-id="3573e-208">Save your change.</span></span>

    ![Az integrációs felhasználói mód mező hozzáadása a képernyőhöz](media/sales-map-field-explorer.png)

3. <span data-ttu-id="3573e-210">Az Sales alkalmazásban nyissa meg a **Beállítás \> Biztonság \> Felhasználók** lehetőséget és a nézetet módosítsa **Engedélyezett felhasználók** helyett **Alkalmazás felhasználói** értékre.</span><span class="sxs-lookup"><span data-stu-id="3573e-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![A nézet módosítása az Engedélyezett felhasználókról az Alkalmazás felhasználóira](media/sales-map-enabled-users.png)

4. <span data-ttu-id="3573e-212">Válassza ki a **DualWrite IntegrationUser** két bejegyzését.</span><span class="sxs-lookup"><span data-stu-id="3573e-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Alkalmazásfelhasználók listája](media/sales-map-user-mode.png)

5. <span data-ttu-id="3573e-214">Módosítsa az **integrációs felhasználói mód** mező értékét **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="3573e-214">Change the value of the **Integration user mode** field to **Yes**.</span></span>

    ![Az integrációs felhasználói mód mező értékének módosítása Igen értékre](media/sales-map-user-mode-yes.png)

<span data-ttu-id="3573e-216">Az értékesítési rendeléseket már le vannak képezve.</span><span class="sxs-lookup"><span data-stu-id="3573e-216">Your sales orders are now mapped.</span></span>
