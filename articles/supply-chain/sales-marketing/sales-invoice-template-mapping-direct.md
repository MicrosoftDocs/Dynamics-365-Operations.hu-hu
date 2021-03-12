---
title: Értékesítésiszámla-fejlécek és -sorok szinkronizálása közvetlenül a Supply Chain Management szolgáltatásból a Sales szolgáltatásba
description: Ez a témakör a sablonokat és alapul szolgáló feladatokat mutatja be, amelyeket használnak a számlafejlécek és sorok közvetlen szinkronizálásához a Dynamics 365 Supply Chain Management és a Dynamics 365 Sales között.
author: ChristianRytt
manager: tfehr
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: d7f104b3f2e132b5b517443577a020fda7fa9af3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975010"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="57d71-103">Értékesítésszámla-fejlécek és -sorok szinkronizálása közvetlenül a Sales szolgáltatásból a Finance and Operations Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="57d71-103">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57d71-104">Ez a témakör a sablonokat és alapul szolgáló feladatokat mutatja be, amelyeket használnak a számlafejlécek és sorok közvetlen szinkronizálásához a Dynamics 365 Supply Chain Management és a Dynamics 365 Sales között.</span><span class="sxs-lookup"><span data-stu-id="57d71-104">This topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="57d71-105">A potenciális ügyfelek készpénzre váltása adatfolyama</span><span class="sxs-lookup"><span data-stu-id="57d71-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="57d71-106">A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Supply Chain Management és a Sales példányai között.</span><span class="sxs-lookup"><span data-stu-id="57d71-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="57d71-107">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákkal kapcsolatos adatok áramlását a Supply Chain Management és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="57d71-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="57d71-108">A következő ábra bemutatja a Supply Chain Management és a Sales közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="57d71-108">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="57d71-109">[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="57d71-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="57d71-110">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="57d71-110">Templates and tasks</span></span>

<span data-ttu-id="57d71-111">A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [Power Apps Admin Centert](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="57d71-111">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="57d71-112">Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="57d71-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="57d71-113">A következő sablont és alapul szolgáló feladatokat használják az értékesítési számlafejlécek és sorok közvetlen szinkronizálásához a Supply Chain Management és a Sales között:</span><span class="sxs-lookup"><span data-stu-id="57d71-113">The following template and underlying tasks are used to synchronize sales invoice headers and lines from Supply Chain Management to Sales:</span></span>

- <span data-ttu-id="57d71-114">**Sablon neve az adatintegrációban:** Értékesítési számlák (Fin and Ops – Sales) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="57d71-114">**Name of the template in Data integration:** Sales Invoices (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="57d71-115">**A feladatok nevei az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="57d71-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="57d71-116">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="57d71-116">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="57d71-117">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="57d71-117">SalesInvoiceLine</span></span>

<span data-ttu-id="57d71-118">A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési számla fejlécének és sorainak szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="57d71-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="57d71-119">Termékek (Supply Chain Management – Sales) – közvetlen</span><span class="sxs-lookup"><span data-stu-id="57d71-119">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="57d71-120">Számlák (Sales – Supply Chain Management) – közvetlen (ha használatban van)</span><span class="sxs-lookup"><span data-stu-id="57d71-120">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="57d71-121">Kapcsolattartók (Sales – Supply Chain Management) – közvetlen (ha használatban van)</span><span class="sxs-lookup"><span data-stu-id="57d71-121">Contacts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="57d71-122">Értékesítési rendelés fejléce és sorai (Supply Chain Management – Sales) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="57d71-122">Sales order header and lines (Supply Chain Management to Sales) - Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="57d71-123">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="57d71-123">Entity set</span></span>

| <span data-ttu-id="57d71-124">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="57d71-124">Supply Chain Management</span></span>                              | <span data-ttu-id="57d71-125">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="57d71-125">Sales</span></span>          |
|------------------------------------------------------|----------------|
| <span data-ttu-id="57d71-126">Külsőleg karbantartott vevői értékesítésiszámla-fejlécek</span><span class="sxs-lookup"><span data-stu-id="57d71-126">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="57d71-127">Számlák</span><span class="sxs-lookup"><span data-stu-id="57d71-127">Invoices</span></span>       |
| <span data-ttu-id="57d71-128">Külsőleg karbantartott vevői értékesítésiszámla-sorok</span><span class="sxs-lookup"><span data-stu-id="57d71-128">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="57d71-129">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="57d71-129">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="57d71-130">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="57d71-130">Entity flow</span></span>

<span data-ttu-id="57d71-131">Az értékesítési számlák létrehozása a Supply Chain Management történik, majd szinkronizálódnak a Sales programban.</span><span class="sxs-lookup"><span data-stu-id="57d71-131">Sales invoices are created in Supply Chain Management and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="57d71-132">A költségekhez kapcsolódó adók az Értékesítési számla fejlécében jelenleg nem szerepelnek a Supply Chain Management szolgáltatásból a Sales szolgáltatásba történő szinkronizálásban.</span><span class="sxs-lookup"><span data-stu-id="57d71-132">Currently, tax that is related to charges on the sales invoice header isn't included in the synchronization from Supply Chain Managements to Sales.</span></span> <span data-ttu-id="57d71-133">A Sales nem támogatja az adózási adatokat a fejléc szintjén.</span><span class="sxs-lookup"><span data-stu-id="57d71-133">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="57d71-134">Azonban a sorszintű díjakhoz kapcsolódó adó szerepel a szinkronizálásban.</span><span class="sxs-lookup"><span data-stu-id="57d71-134">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="57d71-135">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="57d71-135">Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="57d71-136">Egy **Számla száma mező** hozzáadódik a **Számla** entitáshoz, és megjelenik a lapon.</span><span class="sxs-lookup"><span data-stu-id="57d71-136">An **Invoice number** field has been added to the **Invoice** entity and appears on the page.</span></span>
- <span data-ttu-id="57d71-137">A **Számla létrehozása** gomb az **Értékesítési rendelés** lapon rejtve van, mivel a számlák létrehozása a Supply Chain Management szolgáltatásban történik, és szinkronizálódik a Sales szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="57d71-137">The **Create invoice** button on the **Sales order** page is hidden, because invoices will be created in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="57d71-138">A **Számla** lap tartalma nem szerkeszthető, mert a számlák a Supply Chain Management szolgáltatásból szinkronizálódnak.</span><span class="sxs-lookup"><span data-stu-id="57d71-138">The **Invoice** page can't be edited, because invoices will be synchronized from Supply Chain Management.</span></span>
- <span data-ttu-id="57d71-139">Az **Értékesítési rendelés állapota** automatikusan **Számlázott** értékre változik, amikor a Supply Chain Management szolgáltatásból a kapcsolódó számla szinkronizálása a Sales szolgáltatásba megtörténik.</span><span class="sxs-lookup"><span data-stu-id="57d71-139">The **Sales order status** value is automatically changed to **Invoiced** when the related invoice from Supply Chain Management has been synchronized to Sales.</span></span> <span data-ttu-id="57d71-140">Az értékesítési rendelés tulajdonosa, amelyből a számlát létrehozták, hozzárendelésre kerül a számla tulajdonosaként.</span><span class="sxs-lookup"><span data-stu-id="57d71-140">Additionally, the owner of the sales order that the invoice was created from is assigned as the owner of the invoice.</span></span> <span data-ttu-id="57d71-141">Emiatt az értékesítési rendelés tulajdonosa megtekintheto a számlát.</span><span class="sxs-lookup"><span data-stu-id="57d71-141">Therefore, the owner of the sales order can view the invoice.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="57d71-142">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="57d71-142">Preconditions and mapping setup</span></span>

<span data-ttu-id="57d71-143">Értékesítési számlák szinkronizálása előtt fontos frissíteni a rendszert a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="57d71-143">Before you synchronize sales invoices, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="57d71-144">Beállítás a Salesben</span><span class="sxs-lookup"><span data-stu-id="57d71-144">Setup in Sales</span></span>

<span data-ttu-id="57d71-145">Lépjen a **Beállítások** > **Adminisztráció** > **Rendszerbeállítások** > **Értékesítés** pontra, és győződjön meg róla, hogy a következő beállításokat használja:</span><span class="sxs-lookup"><span data-stu-id="57d71-145">Go to **Settings** > **Administration** > **System settings** > **Sales**, and make sure that the following settings are used:</span></span>

- <span data-ttu-id="57d71-146">A **Rendszer díjazási számítási rendszerének használata** beállítás értéke **Igen**.</span><span class="sxs-lookup"><span data-stu-id="57d71-146">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
- <span data-ttu-id="57d71-147">Az **Engedményszámítási módszer** mező értéke a **Sortétel**.</span><span class="sxs-lookup"><span data-stu-id="57d71-147">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="57d71-148">Beállítás az adatintegrációs projektben</span><span class="sxs-lookup"><span data-stu-id="57d71-148">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="57d71-149">SalesInvoiceHeader feladat</span><span class="sxs-lookup"><span data-stu-id="57d71-149">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="57d71-150">Győződjön meg róla, hogy a szükséges leképezés létezik: **InvoiceCountryRegionId** – **BillingAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="57d71-150">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country**.</span></span>

    <span data-ttu-id="57d71-151">A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve.</span><span class="sxs-lookup"><span data-stu-id="57d71-151">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="57d71-152">Számláknak a Sales szolgáltatásban történő létrehozásához szükség van árlistára.</span><span class="sxs-lookup"><span data-stu-id="57d71-152">A price list is required in order to create invoices in Sales.</span></span> <span data-ttu-id="57d71-153">Frissítse a **pricelevelid.name \[Price list name\]** leképezését olyan árlistára, amelyet a Sales is használja valutánként.</span><span class="sxs-lookup"><span data-stu-id="57d71-153">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="57d71-154">Az alapértelmezett árlistát használhatja egy pénznemnél.</span><span class="sxs-lookup"><span data-stu-id="57d71-154">You can use the default price list for a single currency.</span></span> <span data-ttu-id="57d71-155">Alternatív megoldásként, ha több pénznemben van árlistája, használhat értékképpontot.</span><span class="sxs-lookup"><span data-stu-id="57d71-155">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="57d71-156">A **pricelevelid.name \[Price list name\]** sablon értéke az USD = CRM Service USA értékein alapul (minta).</span><span class="sxs-lookup"><span data-stu-id="57d71-156">The template value for **pricelevelid.name \[Price list name\]** is a value map that is based on currency with USD = CRM Service USA (sample).</span></span>  
    
#### <a name="salesinvoiceline-task"></a><span data-ttu-id="57d71-157">SalesInvoiceLine feladat</span><span class="sxs-lookup"><span data-stu-id="57d71-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="57d71-158">Ügyeljen arra, hogy meglegyen a szükséges leképezés a **mértékegységnél**.</span><span class="sxs-lookup"><span data-stu-id="57d71-158">Make sure that the required mapping exists for **Unit of measure**.</span></span>
- <span data-ttu-id="57d71-159">Győződjön meg arról, hogy a **SalesUnitSymbol** szükséges értékmegfeleltetése létezik a Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="57d71-159">Make sure that the required value map for **SalesUnitSymbol** in Supply Chain Management exists.</span></span>

    <span data-ttu-id="57d71-160">Olyan sablonérték, amely rendelkezik értékmegfeleltetéssel a **SalesUnitSymbol** esetében az **Quantity\_UOM** értékkel.</span><span class="sxs-lookup"><span data-stu-id="57d71-160">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="57d71-161">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="57d71-161">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="57d71-162">A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem szerepelnek a alapértelmezett-leképezései.</span><span class="sxs-lookup"><span data-stu-id="57d71-162">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="57d71-163">Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.</span><span class="sxs-lookup"><span data-stu-id="57d71-163">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="57d71-164">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="57d71-164">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="57d71-165">A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Supply Chain Management irányban.</span><span class="sxs-lookup"><span data-stu-id="57d71-165">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="salesinvoiceheader"></a><span data-ttu-id="57d71-166">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="57d71-166">SalesInvoiceHeader</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a><span data-ttu-id="57d71-168">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="57d71-168">SalesInvoiceLine</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="57d71-170">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="57d71-170">Related topics</span></span>

[<span data-ttu-id="57d71-171">A potenciális vevők készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="57d71-171">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="57d71-172">A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="57d71-172">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="57d71-173">A Supply Chain Management-termékek közvetlen szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="57d71-173">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="57d71-174">A Sales-kapcsolatok közvetlen szinkronizálása a Supply Chain Management-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="57d71-174">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="57d71-175">Értékesítési rendelés szinkronizálása közvetlenül a Sales szolgáltatás és a Supply Chain Management szolgáltatás között</span><span class="sxs-lookup"><span data-stu-id="57d71-175">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)
