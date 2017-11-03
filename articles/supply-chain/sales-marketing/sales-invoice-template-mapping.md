---
title: "Értékesítésiszámla-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba"
description: "A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók az értékesítési számlák fejlécei és sorai esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 22ab02555dcac850b18aac9564af41d6c627eade
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="89e58-103">Értékesítésiszámla-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="89e58-103">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="89e58-104">A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók az értékesítési számlák fejlécei és sorai esetében.</span><span class="sxs-lookup"><span data-stu-id="89e58-104">The topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="89e58-105">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="89e58-105">Templates and tasks</span></span>

<span data-ttu-id="89e58-106">A következő sablonok és alapul szolgáló feladatok vannak használatban az értékesítési számlafejlécek és sorok szinkronizálásához a Finance and Operations és a Sales között:</span><span class="sxs-lookup"><span data-stu-id="89e58-106">The following templates and underlying tasks are used to synchronize sales invoice headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="89e58-107">**A sablon neve az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="89e58-107">**Name of the template in Data integration**</span></span> 

     - <span data-ttu-id="89e58-108">Értékesítési számlák (Fin és Ops a Saleshez)</span><span class="sxs-lookup"><span data-stu-id="89e58-108">Sales Invoices (Fin and Ops to Sales)</span></span>

- <span data-ttu-id="89e58-109">**A feladatok nevei az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="89e58-109">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="89e58-110">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="89e58-110">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="89e58-111">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="89e58-111">SalesInvoiceLine</span></span>

<span data-ttu-id="89e58-112">Szükséges szinkronizálási feladatok az értékesítési számla fejléce és a sorok szinkronizálása előtt:</span><span class="sxs-lookup"><span data-stu-id="89e58-112">Sync tasks required prior to Sales invoice header and lines synchronization:</span></span>
-   <span data-ttu-id="89e58-113">Termékek (Fin és Ops a Saleshez)</span><span class="sxs-lookup"><span data-stu-id="89e58-113">Products (Fin and Ops to Sales)</span></span>
-   <span data-ttu-id="89e58-114">Számlák (Sales a Fin and Opshoz) (ha van)</span><span class="sxs-lookup"><span data-stu-id="89e58-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="89e58-115">Kapcsolattartók (Sales a Fin and Opshoz) (ha van)</span><span class="sxs-lookup"><span data-stu-id="89e58-115">Contacts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="89e58-116">Értékesítési rendelés fejléce és sorai (Fin és Ops a Saleshez)</span><span class="sxs-lookup"><span data-stu-id="89e58-116">Sales order header and lines (Fin and Ops to Sales)</span></span>

## <a name="entity-set"></a><span data-ttu-id="89e58-117">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="89e58-117">Entity set</span></span>

| <span data-ttu-id="89e58-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="89e58-118">Finance and Operations</span></span>                               | <span data-ttu-id="89e58-119">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="89e58-119">Common Data Service (CDS)</span></span>              | <span data-ttu-id="89e58-120">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="89e58-120">Sales</span></span>          |
|------------------------------------------------------|------------------|----------------|
| <span data-ttu-id="89e58-121">Külsőleg karbantartott vevői értékesítésiszámla-fejlécek</span><span class="sxs-lookup"><span data-stu-id="89e58-121">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="89e58-122">SalesInvoice</span><span class="sxs-lookup"><span data-stu-id="89e58-122">SalesInvoice</span></span>     | <span data-ttu-id="89e58-123">Számlák</span><span class="sxs-lookup"><span data-stu-id="89e58-123">Invoices</span></span>       |
| <span data-ttu-id="89e58-124">Külsőleg karbantartott vevői értékesítésiszámla-sorok</span><span class="sxs-lookup"><span data-stu-id="89e58-124">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="89e58-125">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="89e58-125">SalesInvoiceLine</span></span> | <span data-ttu-id="89e58-126">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="89e58-126">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="89e58-127">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="89e58-127">Entity flow</span></span>

<span data-ttu-id="89e58-128">Az értékesítési számlák létrehozása a Finance and Operationsben történik, majd szinkronizálódnak a Sales programban.</span><span class="sxs-lookup"><span data-stu-id="89e58-128">Sales invoices are created in Finance and Operations and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="89e58-129">A költségekhez kapcsolódó adók az **értékesítési számla fejlécében** jelenleg nem szerepelnek a Finance and Operationsből a Salesbe történő szinkronizálásban.</span><span class="sxs-lookup"><span data-stu-id="89e58-129">Tax related to charges on the **Sales invoice header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="89e58-130">Ennek oka, hogy a Sales nem támogatja az adózási adatokat a fejléc szintjén.</span><span class="sxs-lookup"><span data-stu-id="89e58-130">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="89e58-131">A sor szintjén a költségekhez kapcsolódó adók beletartoznak.</span><span class="sxs-lookup"><span data-stu-id="89e58-131">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="89e58-132">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="89e58-132">Prospect to cash solution for Sales</span></span>

-  <span data-ttu-id="89e58-133">Egy **Számla száma mező** hozzáadódik a **Számla** entitáshoz és megjelenik a lapon.</span><span class="sxs-lookup"><span data-stu-id="89e58-133">An **Invoice number field** is added to the **Invoice** entity and displayed on the page.</span></span>
 
-  <span data-ttu-id="89e58-134">A **Számla létrehozása** gomb az **Értékesítési rendelés** lapon rejtve van, mivel a számlák létrehozása a Finance and Operationsben történik, és szinkronizálódik a Salesbe.</span><span class="sxs-lookup"><span data-stu-id="89e58-134">The **Create invoice** button on the **Sales order** page is hidden because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="89e58-135">A **Számla** lap tartalma nem szerkeszthető, mert a számlák a Finance and Operationsből szinkronizálódnak.</span><span class="sxs-lookup"><span data-stu-id="89e58-135">The **Invoice** page is non-editable because invoices will be synced from Finance and Operations.</span></span>
 
-  <span data-ttu-id="89e58-136">Az **Értékesítési rendelés állapota** automatikusan **Számlázott** értékre változik, amikor a Finance and Operationsből a kapcsolódó számla szinkronizálása a Salesbe megtörténik.</span><span class="sxs-lookup"><span data-stu-id="89e58-136">The **Sales order status** changes automatically to **Invoiced** when the related invoice from Finance and Operations has been  synchronized to Sales.</span></span> <span data-ttu-id="89e58-137">Az értékesítési rendelés tulajdonosa, amelyből a számlát létrehozták, hozzárendelésre kerül a számla tulajdonosaként.</span><span class="sxs-lookup"><span data-stu-id="89e58-137">Also, the owner of the sales order from which the invoice was created is assigned as the owner of the invoice.</span></span> <span data-ttu-id="89e58-138">Ez lehetővé teszi az értékesítési rendelés tulajdonosa számára a számla megtekintését.</span><span class="sxs-lookup"><span data-stu-id="89e58-138">This gives the owner of the sales order the ability to view the invoice.</span></span>
 
## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="89e58-139">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="89e58-139">Preconditions and mapping setup</span></span>

<span data-ttu-id="89e58-140">Értékesítési számlák szinkronizálása előtt fontos frissíteni a rendszert a következő beállítással:</span><span class="sxs-lookup"><span data-stu-id="89e58-140">Before synchronizing sales invoices, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="89e58-141">Beállítás a Salesben</span><span class="sxs-lookup"><span data-stu-id="89e58-141">Setup in Sales</span></span>

- <span data-ttu-id="89e58-142">A **Beállítások** > **Felügyelet** > **Rendszerbeállítások** > **Sales** menüpontban a **Rendszer díjazási számítási rendszerének használata** paramétert állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="89e58-142">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="89e58-143">A **Beállítások** > **Felügyelet** > **Tendszerbeállítások** > **Sales** menüpontban az **Engedményszámítási módszer** paramétert állítsa **Sortétel** értékre.</span><span class="sxs-lookup"><span data-stu-id="89e58-143">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="89e58-144">Beállítás az adatintegrációs projektben</span><span class="sxs-lookup"><span data-stu-id="89e58-144">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="89e58-145">SalesInvoiceHeader feladat</span><span class="sxs-lookup"><span data-stu-id="89e58-145">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="89e58-146">Frissítse a **CDS-szervezetazonosítót** a **Forrás pontban** > **CDS** értékre.</span><span class="sxs-lookup"><span data-stu-id="89e58-146">Update the mapping for **CDS Organization ID** in **Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="89e58-147">A sablon alapértelmezett **SalesOrder_Organization_OrganizationId** értéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="89e58-147">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="89e58-148">A sablon alapértelmezett **Account_Organization_OrganizationId** értéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="89e58-148">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="89e58-149">A sablon alapértelmezett **Organization_OrganizationId** értéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="89e58-149">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="89e58-150">Ügyeljen, hogy meglegyen a **Forrás** > **InvoiceCountryRegionId CDS-e** szükséges leképezése a **BillingAddress_Country**-hoz.</span><span class="sxs-lookup"><span data-stu-id="89e58-150">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId** to **BillingAddress_Country**.</span></span>

    -  <span data-ttu-id="89e58-151">A sablon értéke **ValueMap** az országok számával leképezve.</span><span class="sxs-lookup"><span data-stu-id="89e58-151">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="89e58-152">Számlák a Salesben történő létrehozásához szükség van **Árlistára**.</span><span class="sxs-lookup"><span data-stu-id="89e58-152">**Price list** is required to create invoices in Sales.</span></span> <span data-ttu-id="89e58-153">Frissítse a **ValueMap** elemet a **CDS** > **pricelevelid.name [Árlista neve] célhelye** helyen a Salesben pénznemenként használt **Árlistára**.</span><span class="sxs-lookup"><span data-stu-id="89e58-153">Update the **ValueMap** in **CDS** > **Destination for pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="89e58-154">Használhatja az alapértelmezett **Árlistát** egyetlen pénznemhez, vagy egy **ValueMap** elemet, ha több pénznemben vannak **Árlisták**.</span><span class="sxs-lookup"><span data-stu-id="89e58-154">You can either use the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>

    -  <span data-ttu-id="89e58-155">A **pricelevelid.name [Árlista neve]** sablonértéke **ValueMap** a **Pénznem** alapján.</span><span class="sxs-lookup"><span data-stu-id="89e58-155">Template value for **pricelevelid.name [Price List Name]** is **ValueMap** based on **Currency**.</span></span>
    -  <span data-ttu-id="89e58-156">usd: CRM szolgáltatás USA (minta).</span><span class="sxs-lookup"><span data-stu-id="89e58-156">usd: CRM Service USA (sample).</span></span> 

#### <a name="salesinvoiceline-task"></a><span data-ttu-id="89e58-157">SalesInvoiceLine feladat</span><span class="sxs-lookup"><span data-stu-id="89e58-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="89e58-158">Ellenőrizze, hogy létezik-e a szükséges leképezés a **Forrás** > **Mértékegység-CDS** helyen.</span><span class="sxs-lookup"><span data-stu-id="89e58-158">Ensure that the needed mapping exists in **Source** > **CDS for Unit of measure**.</span></span>

- <span data-ttu-id="89e58-159">Győződjön meg arról, hogy a Finance and Operationsben a szükséges **ValueMap** a **SalesUnitSymbol** elemhez létezik a **Forrás** > **CDS-hozzárendelés** helyen.</span><span class="sxs-lookup"><span data-stu-id="89e58-159">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span> 
    
    - <span data-ttu-id="89e58-160">A **ValueMap** sablonérték meghatározása a **SalesUnitSymbol to Quantity_UOM** révén történik.</span><span class="sxs-lookup"><span data-stu-id="89e58-160">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>
    
-  <span data-ttu-id="89e58-161">Frissítse a leképezést a következőre: **CDS-szervezetazonosító forrásban** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="89e58-161">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="89e58-162">A sablon alapértelmezett **SalesInvoicer_Organization_OrganizationId** értéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="89e58-162">Default template value for **SalesInvoicer_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="89e58-163">A sablon alapértelmezett **Product_Organization_OrganizationId** értéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="89e58-163">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>
 
## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="89e58-164">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="89e58-164">Template mapping in Data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="89e58-165">A **Fizetési feltételek**, **Szállítási feltételek**, **Kiszállítási feltételek**, **Szállítási mód** és **Kézbesítés módja** nem találhatók meg az alapértelmezett leképezésekben.</span><span class="sxs-lookup"><span data-stu-id="89e58-165">**Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** are not part of the default mappings.</span></span> <span data-ttu-id="89e58-166">Ezen mezők megfeleltetéséhez be kell állítani az értékek olyan leképezését, amely konkrétan azon szervezetek adataira vonatkozik, amelyek között az entitás szinkronizálása megtörténik.</span><span class="sxs-lookup"><span data-stu-id="89e58-166">Mapping of these fields requires value mapping to be set up, which is specific to the data in the organizations between which the entity is synchronized.</span></span>

<span data-ttu-id="89e58-167">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="89e58-167">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Sablonleképezés az adatintegrátorban](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="89e58-172">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="89e58-172">Related topics</span></span>

[<span data-ttu-id="89e58-173">A Finance and Operations-termékek szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="89e58-173">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="89e58-174">A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="89e58-174">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="89e58-175">A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="89e58-175">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="89e58-176">Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="89e58-176">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="89e58-177">Értékesítésirendelés-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="89e58-177">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)


