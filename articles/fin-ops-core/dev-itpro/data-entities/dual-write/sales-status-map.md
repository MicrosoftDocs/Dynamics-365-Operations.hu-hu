---
title: Az értékesítési rendelés állapotoszlopaihoz tartozó leképezés beállítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani az értékesítési rendelés állapotoszlopait a kettős íráshoz.
author: dasani-madipalli
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9afa64df73aa17e7a15a0ee4f4529ac74bcd3c67
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750714"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a><span data-ttu-id="dd6e4-103">Az értékesítési rendelés állapotoszlopaihoz tartozó leképezés beállítása</span><span class="sxs-lookup"><span data-stu-id="dd6e4-103">Set up the mapping for the sales order status columns</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd6e4-104">Az értékesítési rendelés állapotát jelző oszlopok a Microsoft Dynamics 365 Supply Chain Management és a Dynamics 365 Sales alkalmazásban eltérő számértékekkel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-104">The columns that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="dd6e4-105">Ezeknek az oszlopoknak a leképezéséhez a kettős írásban további beállítás szükséges.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-105">Additional setup is required to map these columns in dual-write.</span></span>

## <a name="columns-in-supply-chain-management"></a><span data-ttu-id="dd6e4-106">A Supply Chain Management oszlopai</span><span class="sxs-lookup"><span data-stu-id="dd6e4-106">columns in Supply Chain Management</span></span>

<span data-ttu-id="dd6e4-107">A Supply Chain Management alkalmazásban két oszlop tükrözi az értékesítési rendelés állapotát.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-107">In Supply Chain Management, two columns reflect the status of the sales order.</span></span> <span data-ttu-id="dd6e4-108">A leképezni kívánt oszlopok az **Állapot** és a **Dokumentum állapota**.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-108">The columns that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="dd6e4-109">Az **Állapot** számozása a rendelés általános állapotát határozza meg.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="dd6e4-110">Ez az állapot jelenik meg a rendelés fejlécében.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-110">This status is shown on the order header.</span></span>

<span data-ttu-id="dd6e4-111">Az **Állapot** számozás a következő értékekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="dd6e4-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="dd6e4-112">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="dd6e4-112">Open Order</span></span>
- <span data-ttu-id="dd6e4-113">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="dd6e4-113">Delivered</span></span>
- <span data-ttu-id="dd6e4-114">Számlázva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-114">Invoiced</span></span>
- <span data-ttu-id="dd6e4-115">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-115">Cancelled</span></span>

<span data-ttu-id="dd6e4-116">A **Dokumentum állapota** felsorolása a rendeléshez létrehozott legfrissebb dokumentumot határozza meg.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="dd6e4-117">Ha például a rendelés meg van erősítve, akkor ez a dokumentum egy értékesítési rendelés visszaigazolása.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="dd6e4-118">Ha egy értékesítési rendelést részben számláznak, és a fennmaradó sor meg van erősítve, akkor a dokumentum állapota a **Számla** marad, mivel a számla később jön létre a folyamatban.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="dd6e4-119">A **Dokumentum állapota** felsorolás a következő értékekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="dd6e4-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="dd6e4-120">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="dd6e4-120">Confirmation</span></span>
- <span data-ttu-id="dd6e4-121">Kitárolási lista</span><span class="sxs-lookup"><span data-stu-id="dd6e4-121">Picking List</span></span>
- <span data-ttu-id="dd6e4-122">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="dd6e4-122">Packing Slip</span></span>
- <span data-ttu-id="dd6e4-123">Számla</span><span class="sxs-lookup"><span data-stu-id="dd6e4-123">Invoice</span></span>

## <a name="columns-in-sales"></a><span data-ttu-id="dd6e4-124">Oszlopok az Értékesítésben</span><span class="sxs-lookup"><span data-stu-id="dd6e4-124">columns in Sales</span></span>

<span data-ttu-id="dd6e4-125">A Sales alkalmazásban két oszlop jelzi az értékesítési rendelés állapotát.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-125">In Sales, two columns indicate the status of the order.</span></span> <span data-ttu-id="dd6e4-126">A leképezni kívánt oszlopok az **Állapot** és a **Feldolgozás állapota**.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-126">The columns that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="dd6e4-127">Az **Állapot** számozása a rendelés általános állapotát határozza meg.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="dd6e4-128">Az alábbi értékekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="dd6e4-128">It has the following values:</span></span>

- <span data-ttu-id="dd6e4-129">Aktív</span><span class="sxs-lookup"><span data-stu-id="dd6e4-129">Active</span></span>
- <span data-ttu-id="dd6e4-130">Elküldve</span><span class="sxs-lookup"><span data-stu-id="dd6e4-130">Submitted</span></span>
- <span data-ttu-id="dd6e4-131">Teljesített</span><span class="sxs-lookup"><span data-stu-id="dd6e4-131">Fulfilled</span></span>
- <span data-ttu-id="dd6e4-132">Számlázva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-132">Invoiced</span></span>
- <span data-ttu-id="dd6e4-133">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-133">Cancelled</span></span>

<span data-ttu-id="dd6e4-134">A **Feldolgozási állapot** számozása azért lett bevezetve, hogy az állapot pontosabban legyen megfeleltetve a Supply Chain Management alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="dd6e4-135">A következő táblázat bemutatja a Supply Chain Management **Feldolgozási állapotának** leképezését.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="dd6e4-136">Feldolgozás állapota</span><span class="sxs-lookup"><span data-stu-id="dd6e4-136">Processing Status</span></span>   | <span data-ttu-id="dd6e4-137">A Supply Chain Management állapotai</span><span class="sxs-lookup"><span data-stu-id="dd6e4-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="dd6e4-138">Dokumentum állapota a Supply Chain Management alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="dd6e4-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="dd6e4-139">Aktív</span><span class="sxs-lookup"><span data-stu-id="dd6e4-139">Active</span></span>              | <span data-ttu-id="dd6e4-140">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="dd6e4-140">Open Order</span></span>                        | <span data-ttu-id="dd6e4-141">None</span><span class="sxs-lookup"><span data-stu-id="dd6e4-141">None</span></span>                                       |
| <span data-ttu-id="dd6e4-142">Visszaigazolva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-142">Confirmed</span></span>           | <span data-ttu-id="dd6e4-143">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="dd6e4-143">Open Order</span></span>                        | <span data-ttu-id="dd6e4-144">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="dd6e4-144">Confirmation</span></span>                               |
| <span data-ttu-id="dd6e4-145">Kitárolva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-145">Picked</span></span>              | <span data-ttu-id="dd6e4-146">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="dd6e4-146">Open Order</span></span>                        | <span data-ttu-id="dd6e4-147">Kitárolási lista</span><span class="sxs-lookup"><span data-stu-id="dd6e4-147">Picking List</span></span>                               |
| <span data-ttu-id="dd6e4-148">Részlegesen kiszállítva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-148">Partially Delivered</span></span> | <span data-ttu-id="dd6e4-149">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="dd6e4-149">Open Order</span></span>                        | <span data-ttu-id="dd6e4-150">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="dd6e4-150">Packing Slip</span></span>                               |
| <span data-ttu-id="dd6e4-151">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="dd6e4-151">Delivered</span></span>           | <span data-ttu-id="dd6e4-152">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="dd6e4-152">Delivered</span></span>                         | <span data-ttu-id="dd6e4-153">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="dd6e4-153">Packing Slip</span></span>                               |
| <span data-ttu-id="dd6e4-154">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-154">Partially Invoiced</span></span>  | <span data-ttu-id="dd6e4-155">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="dd6e4-155">Delivered</span></span>                         | <span data-ttu-id="dd6e4-156">Számla</span><span class="sxs-lookup"><span data-stu-id="dd6e4-156">Invoice</span></span>                                    |
| <span data-ttu-id="dd6e4-157">Számlázva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-157">Invoiced</span></span>            | <span data-ttu-id="dd6e4-158">Számlázva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-158">Invoiced</span></span>                          | <span data-ttu-id="dd6e4-159">Számla</span><span class="sxs-lookup"><span data-stu-id="dd6e4-159">Invoice</span></span>                                    |
| <span data-ttu-id="dd6e4-160">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-160">Cancelled</span></span>           | <span data-ttu-id="dd6e4-161">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-161">Cancelled</span></span>                         | <span data-ttu-id="dd6e4-162">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="dd6e4-162">Not applicable</span></span>                             |

<span data-ttu-id="dd6e4-163">A következő táblázat bemutatja a **Feldolgozási állapotának** leképezését a Sales és a Supply Chain Management között.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="dd6e4-164">Feldolgozás állapota</span><span class="sxs-lookup"><span data-stu-id="dd6e4-164">Processing Status</span></span>   | <span data-ttu-id="dd6e4-165">Állapot a Sales alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="dd6e4-165">Status in Sales</span></span> | <span data-ttu-id="dd6e4-166">A Supply Chain Management állapotai</span><span class="sxs-lookup"><span data-stu-id="dd6e4-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="dd6e4-167">Aktív</span><span class="sxs-lookup"><span data-stu-id="dd6e4-167">Active</span></span>              | <span data-ttu-id="dd6e4-168">Aktív</span><span class="sxs-lookup"><span data-stu-id="dd6e4-168">Active</span></span>          | <span data-ttu-id="dd6e4-169">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="dd6e4-169">Open Order</span></span>                        |
| <span data-ttu-id="dd6e4-170">Visszaigazolva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-170">Confirmed</span></span>           | <span data-ttu-id="dd6e4-171">Elküldve</span><span class="sxs-lookup"><span data-stu-id="dd6e4-171">Submitted</span></span>       | <span data-ttu-id="dd6e4-172">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="dd6e4-172">Open Order</span></span>                        |
| <span data-ttu-id="dd6e4-173">Kitárolva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-173">Picked</span></span>              | <span data-ttu-id="dd6e4-174">Elküldve</span><span class="sxs-lookup"><span data-stu-id="dd6e4-174">Submitted</span></span>       | <span data-ttu-id="dd6e4-175">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="dd6e4-175">Open Order</span></span>                        |
| <span data-ttu-id="dd6e4-176">Részlegesen kiszállítva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-176">Partially Delivered</span></span> | <span data-ttu-id="dd6e4-177">Aktív</span><span class="sxs-lookup"><span data-stu-id="dd6e4-177">Active</span></span>          | <span data-ttu-id="dd6e4-178">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="dd6e4-178">Open Order</span></span>                        |
| <span data-ttu-id="dd6e4-179">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-179">Partially Invoiced</span></span>  | <span data-ttu-id="dd6e4-180">Aktív</span><span class="sxs-lookup"><span data-stu-id="dd6e4-180">Active</span></span>          | <span data-ttu-id="dd6e4-181">Nyitott rendelés</span><span class="sxs-lookup"><span data-stu-id="dd6e4-181">Open Order</span></span>                        |
| <span data-ttu-id="dd6e4-182">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-182">Partially Invoiced</span></span>  | <span data-ttu-id="dd6e4-183">Teljesített</span><span class="sxs-lookup"><span data-stu-id="dd6e4-183">Fulfilled</span></span>       | <span data-ttu-id="dd6e4-184">Teljesítve</span><span class="sxs-lookup"><span data-stu-id="dd6e4-184">Delivered</span></span>                         |
| <span data-ttu-id="dd6e4-185">Számlázva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-185">Invoiced</span></span>            | <span data-ttu-id="dd6e4-186">Számlázva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-186">Invoiced</span></span>        | <span data-ttu-id="dd6e4-187">Számlázva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-187">Invoiced</span></span>                          |
| <span data-ttu-id="dd6e4-188">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-188">Cancelled</span></span>           | <span data-ttu-id="dd6e4-189">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="dd6e4-189">Cancelled</span></span>       | <span data-ttu-id="dd6e4-190">Érvénytelenített</span><span class="sxs-lookup"><span data-stu-id="dd6e4-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="dd6e4-191">Beállítás</span><span class="sxs-lookup"><span data-stu-id="dd6e4-191">Setup</span></span>

<span data-ttu-id="dd6e4-192">Az értékesítési rendelés állapot oszlopainak leképezésének beállításához az **IsSOPIntegrationEnabled** és az **isIntegrationUser** attribútumokat engedélyeznie kell.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-192">To set up the mapping for the sales order status columns, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="dd6e4-193">Az **IsSOPIntegrationEnabled** attribútum engedélyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="dd6e4-194">Lépjen egy böngészőben a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations` címre.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="dd6e4-195">Cserélje le a **\<test-name\>** elemet a vállalat a Sales alkalmazásra mutató hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="dd6e4-196">A megnyitott lapon keresse meg a **organizationid** elemet, és jegyezze fel az értéket.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Az organizationid megkeresése](media/sales-map-orgid.png)

3. <span data-ttu-id="dd6e4-198">A Sales alkalmazásban meg a böngésző konzolt, majd futtassa a következő parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="dd6e4-199">A 2. lépésből használja az **organizationid** értéket.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on row update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![JavaScript-kód a böngésző konzolján](media/sales-map-script.png)

4. <span data-ttu-id="dd6e4-201">Ellenőrizze, hogy a **IsSOPIntegrationEnabled** **igaz** értékre legyen állítva.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="dd6e4-202">A 1. lépésből használja az URL-címet az érték ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-202">Use the URL from step 1 to check the value.</span></span>

    ![A IsSOPIntegrationEnabled igaz értékre van állítva](media/sales-map-integration-enabled.png)

<span data-ttu-id="dd6e4-204">Az **isIntegrationUser** attribútum engedélyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="dd6e4-205">A Sales alkalmazásban nyissa meg a **Beállítás \> Testreszabás \> Rendszer testreszabása** lehetőséget, válassz a **Felhasználói tábla** lehetőséget, és nyissa meg a **Képernyő \> Felhasználó** elemet.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User table**, and then open **Form \> User**.</span></span>

    ![A feéhasználó képernyő megnyitása](media/sales-map-user.png)

2. <span data-ttu-id="dd6e4-207">A Mezőkezelőben keresse meg **Integráció felhasználói mód** lehetőséget, majd kattintson rá duplán, hogy hozzáadja a képernyőhöz.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="dd6e4-208">Mentse el a módosítást.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-208">Save your change.</span></span>

    ![Az integrációs felhasználói mód oszlop hozzáadása a képernyőhöz](media/sales-map-field-explorer.png)

3. <span data-ttu-id="dd6e4-210">Az Sales alkalmazásban nyissa meg a **Beállítás \> Biztonság \> Felhasználók** lehetőséget és a nézetet módosítsa **Engedélyezett felhasználók** helyett **Alkalmazás felhasználói** értékre.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![A nézet módosítása az Engedélyezett felhasználókról az Alkalmazás felhasználóira](media/sales-map-enabled-users.png)

4. <span data-ttu-id="dd6e4-212">Válassza ki a **DualWrite IntegrationUser** két bejegyzését.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Alkalmazásfelhasználók listája](media/sales-map-user-mode.png)

5. <span data-ttu-id="dd6e4-214">Módosítsa az **Integrációs felhasználói mód** oszlop értékét **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-214">Change the value of the **Integration user mode** column to **Yes**.</span></span>

    ![Az integrációs felhasználói mód oszlop értékének módosítása Igen értékre](media/sales-map-user-mode-yes.png)

<span data-ttu-id="dd6e4-216">Az értékesítési rendeléseket már le vannak képezve.</span><span class="sxs-lookup"><span data-stu-id="dd6e4-216">Your sales orders are now mapped.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]