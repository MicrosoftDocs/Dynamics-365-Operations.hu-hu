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
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997674"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a><span data-ttu-id="2eda8-103">Az értékesítési rendelés állapot mezőihez tartozó hozzárendelés beállítása</span><span class="sxs-lookup"><span data-stu-id="2eda8-103">Set up the mapping for the sales order status fields</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2eda8-104">Az értékesítési rendelés állapotát jelző mezők a Microsoft Dynamics 365 Supply Chain Management és a Dynamics 365 Sales alkalmazásban eltérő számértékekkel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="2eda8-104">The fields that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="2eda8-105">Ezeknek a mezőknek a leképezéséhez a kettős írásban további beállítás szükséges.</span><span class="sxs-lookup"><span data-stu-id="2eda8-105">Additional setup is required to map these fields in dual-write.</span></span>

## <a name="fields-in-supply-chain-management"></a><span data-ttu-id="2eda8-106">A Supply Chain Management mezői</span><span class="sxs-lookup"><span data-stu-id="2eda8-106">Fields in Supply Chain Management</span></span>

<span data-ttu-id="2eda8-107">A Supply Chain Management alkalmazásban két mező tükrözi az értékesítési rendelés állapotát.</span><span class="sxs-lookup"><span data-stu-id="2eda8-107">In Supply Chain Management, two fields reflect the status of the sales order.</span></span> <span data-ttu-id="2eda8-108">A leképezni kívánt mezők az **Állapot** és a **Dokumentum állapota**.</span><span class="sxs-lookup"><span data-stu-id="2eda8-108">The fields that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="2eda8-109">Az **Állapot** számozása a rendelés általános állapotát határozza meg.</span><span class="sxs-lookup"><span data-stu-id="2eda8-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="2eda8-110">Ez az állapot jelenik meg a rendelés fejlécében.</span><span class="sxs-lookup"><span data-stu-id="2eda8-110">This status is shown on the order header.</span></span>

<span data-ttu-id="2eda8-111">Az **Állapot** számozás a következő értékekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="2eda8-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="2eda8-112">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="2eda8-112">Open Order</span></span>
- <span data-ttu-id="2eda8-113">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="2eda8-113">Delivered</span></span>
- <span data-ttu-id="2eda8-114">Számlázva</span><span class="sxs-lookup"><span data-stu-id="2eda8-114">Invoiced</span></span>
- <span data-ttu-id="2eda8-115">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="2eda8-115">Cancelled</span></span>

<span data-ttu-id="2eda8-116">A **Dokumentum állapota** felsorolása a rendeléshez létrehozott legfrissebb dokumentumot határozza meg.</span><span class="sxs-lookup"><span data-stu-id="2eda8-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="2eda8-117">Ha például a rendelés meg van erősítve, akkor ez a dokumentum egy értékesítési rendelés visszaigazolása.</span><span class="sxs-lookup"><span data-stu-id="2eda8-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="2eda8-118">Ha egy értékesítési rendelést részben számláznak, és a fennmaradó sor meg van erősítve, akkor a dokumentum állapota a **Számla** marad, mivel a számla később jön létre a folyamatban.</span><span class="sxs-lookup"><span data-stu-id="2eda8-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice** , because the invoice is generated later in the process.</span></span>

<span data-ttu-id="2eda8-119">A **Dokumentum állapota** felsorolás a következő értékekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="2eda8-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="2eda8-120">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="2eda8-120">Confirmation</span></span>
- <span data-ttu-id="2eda8-121">Kitárolási lista</span><span class="sxs-lookup"><span data-stu-id="2eda8-121">Picking List</span></span>
- <span data-ttu-id="2eda8-122">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="2eda8-122">Packing Slip</span></span>
- <span data-ttu-id="2eda8-123">Számla</span><span class="sxs-lookup"><span data-stu-id="2eda8-123">Invoice</span></span>

## <a name="fields-in-sales"></a><span data-ttu-id="2eda8-124">A Sales mezői</span><span class="sxs-lookup"><span data-stu-id="2eda8-124">Fields in Sales</span></span>

<span data-ttu-id="2eda8-125">A Sales alkalmazásban két mező jelzi az értékesítési rendelés állapotát.</span><span class="sxs-lookup"><span data-stu-id="2eda8-125">In Sales, two fields indicate the status of the order.</span></span> <span data-ttu-id="2eda8-126">A leképezni kívánt mezők az **Állapot** és a **Feldolgozás állapota**.</span><span class="sxs-lookup"><span data-stu-id="2eda8-126">The fields that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="2eda8-127">Az **Állapot** számozása a rendelés általános állapotát határozza meg.</span><span class="sxs-lookup"><span data-stu-id="2eda8-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="2eda8-128">Az alábbi értékekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="2eda8-128">It has the following values:</span></span>

- <span data-ttu-id="2eda8-129">Aktív</span><span class="sxs-lookup"><span data-stu-id="2eda8-129">Active</span></span>
- <span data-ttu-id="2eda8-130">Elküldve</span><span class="sxs-lookup"><span data-stu-id="2eda8-130">Submitted</span></span>
- <span data-ttu-id="2eda8-131">Teljesített</span><span class="sxs-lookup"><span data-stu-id="2eda8-131">Fulfilled</span></span>
- <span data-ttu-id="2eda8-132">Számlázva</span><span class="sxs-lookup"><span data-stu-id="2eda8-132">Invoiced</span></span>
- <span data-ttu-id="2eda8-133">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="2eda8-133">Cancelled</span></span>

<span data-ttu-id="2eda8-134">A **Feldolgozási állapot** számozása azért lett bevezetve, hogy az állapot pontosabban legyen megfeleltetve a Supply Chain Management alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="2eda8-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="2eda8-135">A következő táblázat bemutatja a Supply Chain Management **Feldolgozási állapotának** leképezését.</span><span class="sxs-lookup"><span data-stu-id="2eda8-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="2eda8-136">Feldolgozás állapota</span><span class="sxs-lookup"><span data-stu-id="2eda8-136">Processing Status</span></span>   | <span data-ttu-id="2eda8-137">A Supply Chain Management állapotai</span><span class="sxs-lookup"><span data-stu-id="2eda8-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="2eda8-138">Dokumentum állapota a Supply Chain Management alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="2eda8-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="2eda8-139">Aktív</span><span class="sxs-lookup"><span data-stu-id="2eda8-139">Active</span></span>              | <span data-ttu-id="2eda8-140">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="2eda8-140">Open Order</span></span>                        | <span data-ttu-id="2eda8-141">None</span><span class="sxs-lookup"><span data-stu-id="2eda8-141">None</span></span>                                       |
| <span data-ttu-id="2eda8-142">Visszaigazolva</span><span class="sxs-lookup"><span data-stu-id="2eda8-142">Confirmed</span></span>           | <span data-ttu-id="2eda8-143">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="2eda8-143">Open Order</span></span>                        | <span data-ttu-id="2eda8-144">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="2eda8-144">Confirmation</span></span>                               |
| <span data-ttu-id="2eda8-145">Kitárolva</span><span class="sxs-lookup"><span data-stu-id="2eda8-145">Picked</span></span>              | <span data-ttu-id="2eda8-146">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="2eda8-146">Open Order</span></span>                        | <span data-ttu-id="2eda8-147">Kitárolási lista</span><span class="sxs-lookup"><span data-stu-id="2eda8-147">Picking List</span></span>                               |
| <span data-ttu-id="2eda8-148">Részlegesen kiszállítva</span><span class="sxs-lookup"><span data-stu-id="2eda8-148">Partially Delivered</span></span> | <span data-ttu-id="2eda8-149">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="2eda8-149">Open Order</span></span>                        | <span data-ttu-id="2eda8-150">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="2eda8-150">Packing Slip</span></span>                               |
| <span data-ttu-id="2eda8-151">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="2eda8-151">Delivered</span></span>           | <span data-ttu-id="2eda8-152">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="2eda8-152">Delivered</span></span>                         | <span data-ttu-id="2eda8-153">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="2eda8-153">Packing Slip</span></span>                               |
| <span data-ttu-id="2eda8-154">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="2eda8-154">Partially Invoiced</span></span>  | <span data-ttu-id="2eda8-155">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="2eda8-155">Delivered</span></span>                         | <span data-ttu-id="2eda8-156">Számla</span><span class="sxs-lookup"><span data-stu-id="2eda8-156">Invoice</span></span>                                    |
| <span data-ttu-id="2eda8-157">Számlázva</span><span class="sxs-lookup"><span data-stu-id="2eda8-157">Invoiced</span></span>            | <span data-ttu-id="2eda8-158">Számlázva</span><span class="sxs-lookup"><span data-stu-id="2eda8-158">Invoiced</span></span>                          | <span data-ttu-id="2eda8-159">Számla</span><span class="sxs-lookup"><span data-stu-id="2eda8-159">Invoice</span></span>                                    |
| <span data-ttu-id="2eda8-160">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="2eda8-160">Cancelled</span></span>           | <span data-ttu-id="2eda8-161">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="2eda8-161">Cancelled</span></span>                         | <span data-ttu-id="2eda8-162">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="2eda8-162">Not applicable</span></span>                             |

<span data-ttu-id="2eda8-163">A következő táblázat bemutatja a **Feldolgozási állapotának** leképezését a Sales és a Supply Chain Management között.</span><span class="sxs-lookup"><span data-stu-id="2eda8-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="2eda8-164">Feldolgozás állapota</span><span class="sxs-lookup"><span data-stu-id="2eda8-164">Processing Status</span></span>   | <span data-ttu-id="2eda8-165">Állapot a Sales alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="2eda8-165">Status in Sales</span></span> | <span data-ttu-id="2eda8-166">A Supply Chain Management állapotai</span><span class="sxs-lookup"><span data-stu-id="2eda8-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="2eda8-167">Aktív</span><span class="sxs-lookup"><span data-stu-id="2eda8-167">Active</span></span>              | <span data-ttu-id="2eda8-168">Aktív</span><span class="sxs-lookup"><span data-stu-id="2eda8-168">Active</span></span>          | <span data-ttu-id="2eda8-169">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="2eda8-169">Open Order</span></span>                        |
| <span data-ttu-id="2eda8-170">Visszaigazolva</span><span class="sxs-lookup"><span data-stu-id="2eda8-170">Confirmed</span></span>           | <span data-ttu-id="2eda8-171">Elküldve</span><span class="sxs-lookup"><span data-stu-id="2eda8-171">Submitted</span></span>       | <span data-ttu-id="2eda8-172">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="2eda8-172">Open Order</span></span>                        |
| <span data-ttu-id="2eda8-173">Kitárolva</span><span class="sxs-lookup"><span data-stu-id="2eda8-173">Picked</span></span>              | <span data-ttu-id="2eda8-174">Elküldve</span><span class="sxs-lookup"><span data-stu-id="2eda8-174">Submitted</span></span>       | <span data-ttu-id="2eda8-175">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="2eda8-175">Open Order</span></span>                        |
| <span data-ttu-id="2eda8-176">Részlegesen kiszállítva</span><span class="sxs-lookup"><span data-stu-id="2eda8-176">Partially Delivered</span></span> | <span data-ttu-id="2eda8-177">Aktív</span><span class="sxs-lookup"><span data-stu-id="2eda8-177">Active</span></span>          | <span data-ttu-id="2eda8-178">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="2eda8-178">Open Order</span></span>                        |
| <span data-ttu-id="2eda8-179">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="2eda8-179">Partially Invoiced</span></span>  | <span data-ttu-id="2eda8-180">Aktív</span><span class="sxs-lookup"><span data-stu-id="2eda8-180">Active</span></span>          | <span data-ttu-id="2eda8-181">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="2eda8-181">Open Order</span></span>                        |
| <span data-ttu-id="2eda8-182">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="2eda8-182">Partially Invoiced</span></span>  | <span data-ttu-id="2eda8-183">Teljesített</span><span class="sxs-lookup"><span data-stu-id="2eda8-183">Fulfilled</span></span>       | <span data-ttu-id="2eda8-184">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="2eda8-184">Delivered</span></span>                         |
| <span data-ttu-id="2eda8-185">Számlázva</span><span class="sxs-lookup"><span data-stu-id="2eda8-185">Invoiced</span></span>            | <span data-ttu-id="2eda8-186">Számlázva</span><span class="sxs-lookup"><span data-stu-id="2eda8-186">Invoiced</span></span>        | <span data-ttu-id="2eda8-187">Számlázva</span><span class="sxs-lookup"><span data-stu-id="2eda8-187">Invoiced</span></span>                          |
| <span data-ttu-id="2eda8-188">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="2eda8-188">Cancelled</span></span>           | <span data-ttu-id="2eda8-189">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="2eda8-189">Cancelled</span></span>       | <span data-ttu-id="2eda8-190">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="2eda8-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="2eda8-191">Beállítás</span><span class="sxs-lookup"><span data-stu-id="2eda8-191">Setup</span></span>

<span data-ttu-id="2eda8-192">Az értékesítési rendelés állapot mezőinek leképezésének beállításához az **IsSOPIntegrationEnabled** és a **isIntegrationUser** attribútumokat engedélyeznie kell.</span><span class="sxs-lookup"><span data-stu-id="2eda8-192">To set up the mapping for the sales order status fields, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="2eda8-193">Az **IsSOPIntegrationEnabled** attribútum engedélyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2eda8-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="2eda8-194">Lépjen egy böngészőben a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations` címre.</span><span class="sxs-lookup"><span data-stu-id="2eda8-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="2eda8-195">Cserélje le a **\<test-name\>** elemet a vállalat a Sales alkalmazásra mutató hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="2eda8-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="2eda8-196">A megnyitott lapon keresse meg a **organizationid** elemet, és jegyezze fel az értéket.</span><span class="sxs-lookup"><span data-stu-id="2eda8-196">On the page that is opened, find **organizationid** , and make a note of the value.</span></span>

    ![Az organizationid megkeresése](media/sales-map-orgid.png)

3. <span data-ttu-id="2eda8-198">A Sales alkalmazásban meg a böngésző konzolt, majd futtassa a következő parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="2eda8-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="2eda8-199">A 2. lépésből használja az **organizationid** értéket.</span><span class="sxs-lookup"><span data-stu-id="2eda8-199">Use the **organizationid** value from step 2.</span></span>

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

4. <span data-ttu-id="2eda8-201">Ellenőrizze, hogy a **IsSOPIntegrationEnabled** **igaz** értékre legyen állítva.</span><span class="sxs-lookup"><span data-stu-id="2eda8-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="2eda8-202">A 1. lépésből használja az URL-címet az érték ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="2eda8-202">Use the URL from step 1 to check the value.</span></span>

    ![A IsSOPIntegrationEnabled igaz értékre van állítva](media/sales-map-integration-enabled.png)

<span data-ttu-id="2eda8-204">Az **isIntegrationUser** attribútum engedélyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2eda8-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="2eda8-205">A Sales alkalmazásban nyissa meg a **Beállítás \> Testreszabás \> Rendszer testreszabása** lehetőséget, válassz a **Felhasználói entitás** lehetőséget, és nyissa meg a **Képernyő \> Felhasználó** elemet.</span><span class="sxs-lookup"><span data-stu-id="2eda8-205">In Sales, go to **Setting \> Customization \> Customize the System** , select **User entity** , and then open **Form \> User**.</span></span>

    ![A feéhasználó képernyő megnyitása](media/sales-map-user.png)

2. <span data-ttu-id="2eda8-207">A Mezőkezelőben keresse meg **Integráció felhasználói mód** lehetőséget, majd kattintson rá duplán, hogy hozzáadja a képernyőhöz.</span><span class="sxs-lookup"><span data-stu-id="2eda8-207">In Field Explorer, find **Integration user mode** , and double-click it to add it to the form.</span></span> <span data-ttu-id="2eda8-208">Mentse el a módosítást.</span><span class="sxs-lookup"><span data-stu-id="2eda8-208">Save your change.</span></span>

    ![Az integrációs felhasználói mód mező hozzáadása a képernyőhöz](media/sales-map-field-explorer.png)

3. <span data-ttu-id="2eda8-210">Az Sales alkalmazásban nyissa meg a **Beállítás \> Biztonság \> Felhasználók** lehetőséget és a nézetet módosítsa **Engedélyezett felhasználók** helyett **Alkalmazás felhasználói** értékre.</span><span class="sxs-lookup"><span data-stu-id="2eda8-210">In Sales, go to **Setting \> Security \> Users** , and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![A nézet módosítása az Engedélyezett felhasználókról az Alkalmazás felhasználóira](media/sales-map-enabled-users.png)

4. <span data-ttu-id="2eda8-212">Válassza ki a **DualWrite IntegrationUser** két bejegyzését.</span><span class="sxs-lookup"><span data-stu-id="2eda8-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Alkalmazásfelhasználók listája](media/sales-map-user-mode.png)

5. <span data-ttu-id="2eda8-214">Módosítsa az **integrációs felhasználói mód** mező értékét **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="2eda8-214">Change the value of the **Integration user mode** field to **Yes**.</span></span>

    ![Az integrációs felhasználói mód mező értékének módosítása Igen értékre](media/sales-map-user-mode-yes.png)

<span data-ttu-id="2eda8-216">Az értékesítési rendeléseket már le vannak képezve.</span><span class="sxs-lookup"><span data-stu-id="2eda8-216">Your sales orders are now mapped.</span></span>
