---
title: "Értékesítésirendelés-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba"
description: "A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók az értékesítési rendelések fejlécei és sorai esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: d7e4c435a3344f6a5d66e1889b633d80cda085eb
ms.contentlocale: hu-hu
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="7ec19-103">Értékesítésirendelés-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="7ec19-103">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7ec19-104">A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók az értékesítési rendelések fejlécei és sorai esetében.</span><span class="sxs-lookup"><span data-stu-id="7ec19-104">The topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="7ec19-105">Sablon és feladatok</span><span class="sxs-lookup"><span data-stu-id="7ec19-105">Template and tasks</span></span>

<span data-ttu-id="7ec19-106">A következő sablonok és alapul szolgáló feladatok vannak használatban az értékesítési rendelési fejlécek és sorok szinkronizálásához a Finance and Operations és a Sales között:</span><span class="sxs-lookup"><span data-stu-id="7ec19-106">The following templates and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="7ec19-107">**Sablon neve az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="7ec19-107">**Name of template in Data integration**</span></span> 

    - <span data-ttu-id="7ec19-108">Értékesítési rendelések (Fin és Ops a Saleshez)</span><span class="sxs-lookup"><span data-stu-id="7ec19-108">Sales Orders (Fin and Ops to Sales)</span></span>
    
- <span data-ttu-id="7ec19-109">**Feladatok nevei az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="7ec19-109">**Names of tasks in Data integration project**</span></span>

    - <span data-ttu-id="7ec19-110">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="7ec19-110">OrderHeader</span></span>
    - <span data-ttu-id="7ec19-111">OrderLine</span><span class="sxs-lookup"><span data-stu-id="7ec19-111">OrderLine</span></span>

<span data-ttu-id="7ec19-112">Az értékesítési számla fejléce és a sorok szinkronizálása előtt szükséges szinkronizálási feladatok:</span><span class="sxs-lookup"><span data-stu-id="7ec19-112">Sync tasks required prior to Sales invoice header and lines sync:</span></span>

- <span data-ttu-id="7ec19-113">Termékek (Fin és Ops a Saleshez)</span><span class="sxs-lookup"><span data-stu-id="7ec19-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="7ec19-114">Számlák (Sales a Fin and Opshoz) (ha van)</span><span class="sxs-lookup"><span data-stu-id="7ec19-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="7ec19-115">Kapcsolattartók vevőkkel (Sales a Fin and Opshoz) (ha van)</span><span class="sxs-lookup"><span data-stu-id="7ec19-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="7ec19-116">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="7ec19-116">Entity set</span></span>

| <span data-ttu-id="7ec19-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7ec19-117">Finance and Operations</span></span> |    <span data-ttu-id="7ec19-118">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="7ec19-118">Common Data Service (CDS)</span></span>         |     <span data-ttu-id="7ec19-119">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="7ec19-119">Sales</span></span>      |
|------------------------|----------------|----------------|
| <span data-ttu-id="7ec19-120">CDS értékesítési rendelési fejlécek</span><span class="sxs-lookup"><span data-stu-id="7ec19-120">CDS sales order headers</span></span>| <span data-ttu-id="7ec19-121">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="7ec19-121">SalesOrder</span></span>     | <span data-ttu-id="7ec19-122">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="7ec19-122">SalesOrders</span></span> |
| <span data-ttu-id="7ec19-123">CDS értékesítési rendelés sorai</span><span class="sxs-lookup"><span data-stu-id="7ec19-123">CDS sales order lines</span></span>  | <span data-ttu-id="7ec19-124">SalesOrderLine</span><span class="sxs-lookup"><span data-stu-id="7ec19-124">SalesOrderLine</span></span> | <span data-ttu-id="7ec19-125">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="7ec19-125">SalesOrderDetails</span></span>|

## <a name="entity-flow"></a><span data-ttu-id="7ec19-126">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="7ec19-126">Entity flow</span></span>

<span data-ttu-id="7ec19-127">Az értékesítési rendelések létrehozása a Finance and Operationsben történik, majd szinkronizálódnak a Sales programban.</span><span class="sxs-lookup"><span data-stu-id="7ec19-127">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="7ec19-128">A sablonban található szűrők gondoskodnak róla, hogy hogy csak a megfelelő értékesítési rendelések szerepeljenek a szinkronizálásban:</span><span class="sxs-lookup"><span data-stu-id="7ec19-128">Filters in the template ensure that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="7ec19-129">A Salesből származó értékesítési ajánlatban szereplő értékesítési és számlázási vevő is szerepelni fog a szinkronizálásban.</span><span class="sxs-lookup"><span data-stu-id="7ec19-129">Both ordering and invoicing customer on the sales order that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="7ec19-130">A Finance and Operationsben az **OrderingCustomerIsExternallyMaintained** és az **InvoiceCustomerIsExternallyMaintained** mezők az adatentitások szinkronizálásának nyomon követésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="7ec19-130">In Finance and Operations, the fields **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** are used to track the synchronization in the data entities.</span></span>

- <span data-ttu-id="7ec19-131">Az **Értékesítési rendelést** a Finance and Operationsben jóvá kell hagyni.</span><span class="sxs-lookup"><span data-stu-id="7ec19-131">The **Sales order** in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="7ec19-132">Csak a megerősített értékesítési rendelések vagy magasabb, például Szállított vagy Számlázott feldolgozási állapotú értékesítési rendelések szinkronizálódnak a Salesbe.</span><span class="sxs-lookup"><span data-stu-id="7ec19-132">Only the confirmed sales orders or sales orders with higher processing status, for example, Shipped or Invoiced status, are synchronized to Sales.</span></span>

- <span data-ttu-id="7ec19-133">Értékesítési rendelés létrehozása vagy módosítása után a Finance and Operationsben végre kell hajtani az **Eladási összegek számítása** kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="7ec19-133">After creating or modifying a sales order, the batch job **Calculate sales totals** in Finance and Operations must be executed.</span></span> <span data-ttu-id="7ec19-134">Csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a CDS-be és a Salesbe.</span><span class="sxs-lookup"><span data-stu-id="7ec19-134">Only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="7ec19-135">A költségekhez kapcsolódó adók az **Értékesítési rendelés fejlécében** jelenleg nem szerepelnek a Finance and Operationsből a Salesbe történő szinkronizálásban.</span><span class="sxs-lookup"><span data-stu-id="7ec19-135">Tax related to charges on the **Sales order header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="7ec19-136">Ennek oka, hogy a Sales nem támogatja az adózási adatokat a fejléc szintjén.</span><span class="sxs-lookup"><span data-stu-id="7ec19-136">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="7ec19-137">A sor szintjén a költségekhez kapcsolódó adók beletartoznak.</span><span class="sxs-lookup"><span data-stu-id="7ec19-137">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="7ec19-138">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="7ec19-138">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="7ec19-139">Új mezők kerülnek hozzáadásra a **Rendelés** entitáshoz, és megjelennek a lapon:</span><span class="sxs-lookup"><span data-stu-id="7ec19-139">New fields are added to the **Order** entity and displayed on the page:</span></span>

- <span data-ttu-id="7ec19-140">**Külsőleg karbantartva** – beállítása **Igen**, ha a megrendelés a Finance and Operationsből érkezik.</span><span class="sxs-lookup"><span data-stu-id="7ec19-140">**Is Maintained Externally** - Set to **Yes** when the order is coming from Finance and Operations.</span></span>

- <span data-ttu-id="7ec19-141">**Feldolgozás állapota** – a rendelés feldolgozottsági állapotát mutatja a Finance and Operationsben.</span><span class="sxs-lookup"><span data-stu-id="7ec19-141">**Processing status** - Used to show the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="7ec19-142">Az értékek:</span><span class="sxs-lookup"><span data-stu-id="7ec19-142">Values are:</span></span>

    - <span data-ttu-id="7ec19-143">Aktív</span><span class="sxs-lookup"><span data-stu-id="7ec19-143">Active</span></span>
    - <span data-ttu-id="7ec19-144">Visszaigazolva</span><span class="sxs-lookup"><span data-stu-id="7ec19-144">Confirmed</span></span>
    - <span data-ttu-id="7ec19-145">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="7ec19-145">Packing Slip</span></span>
    - <span data-ttu-id="7ec19-146">Számlázva</span><span class="sxs-lookup"><span data-stu-id="7ec19-146">Invoiced</span></span>
    - <span data-ttu-id="7ec19-147">Kitárolva</span><span class="sxs-lookup"><span data-stu-id="7ec19-147">Picked</span></span>
    - <span data-ttu-id="7ec19-148">Részben kitárolva</span><span class="sxs-lookup"><span data-stu-id="7ec19-148">Partially Picked</span></span>
    - <span data-ttu-id="7ec19-149">Részben csomagolva</span><span class="sxs-lookup"><span data-stu-id="7ec19-149">Partially Packed</span></span>
    - <span data-ttu-id="7ec19-150">Szállítva</span><span class="sxs-lookup"><span data-stu-id="7ec19-150">Shipped</span></span>
    - <span data-ttu-id="7ec19-151">Részben szállítva</span><span class="sxs-lookup"><span data-stu-id="7ec19-151">Partially Shipped</span></span>
    - <span data-ttu-id="7ec19-152">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="7ec19-152">Partially Invoiced</span></span>
    - <span data-ttu-id="7ec19-153">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="7ec19-153">Cancelled</span></span>

<span data-ttu-id="7ec19-154">A **Csak külsőleg karbantartott termékei vannak** beállítással értékesítési rendelési forgatókönyvek esetén (a Salesből a Finance and Operationsbe történő szinkronizációnál) következetesen nyomon követheti, hogy az értékesítési rendelés teljesen **Külsőleg karbantartott termékekből** tevődik-e össze, amely esetben termékek karbantartása a Finance and Operationsben történik.</span><span class="sxs-lookup"><span data-stu-id="7ec19-154">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (from Sales to Finance and Operation sync) to consistently keep track of whether the sales order is made up entirely of **Externally Maintained Products**, in which case products are maintained in Finance and Operations.</span></span> <span data-ttu-id="7ec19-155">Ez garantálja, hogy ne próbálja szinkronizálni az értékesítési rendelési sorokat olyan termékekkel, amelyek ismeretlenek a Finance and Operations számára.</span><span class="sxs-lookup"><span data-stu-id="7ec19-155">This ensures that you don't try to sync sales order lines with products that are unknown to Finance and Operations.</span></span>
 
<span data-ttu-id="7ec19-156">A **Számla létrehozása**, **Rendelés érvénytelenítése**, **Újraszámítás**, **Termékek beszerzése** és **Keresési cím** gombok az **Értékesítési rendelés** oldalon rejtve vannak külsőleg karbantartott rendeléseknél, mivel a számlák a Finance and Operationsben jönnek létre, majd szinkronizálódnak a Salesbe.</span><span class="sxs-lookup"><span data-stu-id="7ec19-156">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products** and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="7ec19-157">A rendelési lap tartalma nem szerkeszthető, mert az értékesítési rendelési adatok a Finance and Operationsből szinkronizálódnak.</span><span class="sxs-lookup"><span data-stu-id="7ec19-157">The order page is non-editable because sales order information will be synced from Finance and Operations.</span></span>
 
<span data-ttu-id="7ec19-158">Az **Értékesítési rendelés állapota** aktív marad annak biztosítására, hogy a Finance and Operations módosításai átkerülhessenek az **Értékesítési rendelésbe** a Salesben.</span><span class="sxs-lookup"><span data-stu-id="7ec19-158">The **Sales order status** will remain active to ensure that changes from Finance and Operations can flow to the **Sales order** in Sales.</span></span> <span data-ttu-id="7ec19-159">Ennek vezérléséhez az alapértelmezett **Statecode [állapot]** értékét **Aktívra** kell állítani az adatintegrációs projektben.</span><span class="sxs-lookup"><span data-stu-id="7ec19-159">This is controlled by setting the default **Statecode [Status]** to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="7ec19-160">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="7ec19-160">Preconditions and mapping setup</span></span> 

<span data-ttu-id="7ec19-161">Értékesítési rendelések szinkronizálása előtt fontos frissíteni a rendszert a következő beállítással:</span><span class="sxs-lookup"><span data-stu-id="7ec19-161">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="7ec19-162">Beállítás a Salesben</span><span class="sxs-lookup"><span data-stu-id="7ec19-162">Setup in Sales</span></span>

- <span data-ttu-id="7ec19-163">Biztosítja az engedélyeket a csapat számára, amelyhez a felhasználó (a Sales **Beállított kapcsolat** paraméterével) hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="7ec19-163">Ensure permissions for the team that the user (from your Sales **Connection set**) is assigned to.</span></span> <span data-ttu-id="7ec19-164">Bemutatóadatok használatakor általában a felhasználó rendelkezik rendszergazdai hozzáféréssel, de nem a csoport.</span><span class="sxs-lookup"><span data-stu-id="7ec19-164">If you are using demo data, usually the user has admin access, but not the team.</span></span> <span data-ttu-id="7ec19-165">Enélkül a projekt az adatintegrátorból történő futtatásakor hibaüzenetet kap, amely szerint a fő csoport nincs megadva.</span><span class="sxs-lookup"><span data-stu-id="7ec19-165">Without this you will get an error that Principal team is missing when running the project from Data integrator.</span></span> 

    - <span data-ttu-id="7ec19-166">A **Beállítások** > **Biztonság** > **Csapatok** pontban, válassza ki az érintett csapatot, kattintson a **Szerepkörök kezelése** elemre, és válassza ki a kívánt engedélyekkel rendelkező szerepkört (például rendszergazda).</span><span class="sxs-lookup"><span data-stu-id="7ec19-166">Under **Settings** > **Security** > **Teams**, select the relevant team, click **Manage Roles** and select a role with the desired permissions e.g. System Administrator.</span></span>

- <span data-ttu-id="7ec19-167">A **Beállítások** > **Felügyelet** > **Rendszerbeállítások** > **Sales** menüpontban a **Rendszer díjazási számítási rendszerének használata** paramétert állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="7ec19-167">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="7ec19-168">A **Beállítások** > **Felügyelet** > **Tendszerbeállítások** > **Sales** menüpontban az **Engedményszámítási módszer** paramétert állítsa **Sortétel** értékre.</span><span class="sxs-lookup"><span data-stu-id="7ec19-168">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="7ec19-169">Beállítás a Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="7ec19-169">Setup in Finance and Operations</span></span>

<span data-ttu-id="7ec19-170">Állítsa az **Értékesítés és marketing** > **Időszakos feladatok** > **Eladási összegek számítása** elemet kötegelt feladatként történő futtatásra, és az **Értékesítési rendelések teljes összegének kiszámítása** elemet állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="7ec19-170">Set **Sales and marketing** > **Periodic tasks** > **Calculate sales totals** to run as a batch job, with **Calculate totals for sales orders** set to **Yes**.</span></span> <span data-ttu-id="7ec19-171">Ez azért fontos, mert csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a CDS-be és a Salesbe.</span><span class="sxs-lookup"><span data-stu-id="7ec19-171">This is important because only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span> <span data-ttu-id="7ec19-172">A kötegelt feladat gyakoriságát az értékesítési rendelés szinkronizálásának gyakoriságához kell igazítani.</span><span class="sxs-lookup"><span data-stu-id="7ec19-172">The frequency of the batch job should be alligned with the frequency of the sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="7ec19-173">Beállítás az adatintegrációs projektben</span><span class="sxs-lookup"><span data-stu-id="7ec19-173">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="7ec19-174">SalesHeader feladat</span><span class="sxs-lookup"><span data-stu-id="7ec19-174">SalesHeader task</span></span>

- <span data-ttu-id="7ec19-175">Frissítse a leképezést a következőre: **CDS-szervezetazonosító forrásban** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="7ec19-175">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span>

    - <span data-ttu-id="7ec19-176">A sablon alapértelmezett **Account_Organization_OrganizationId** értéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="7ec19-176">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="7ec19-177">A sablon alapértelmezett **InvoiceAccount_Organization_OrganizationId** értéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="7ec19-177">Default template value for **InvoiceAccount_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="7ec19-178">A sablon alapértelmezett **Organization_OrganizationId** értéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="7ec19-178">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="7ec19-179">Ellenőrizze, hogy létezik-e a szükséges leképezés a **Forrás** > **CDS for InvoiceCountryRegionId to BillingAddress_Country** és a **DeliveryCountryRegionId to DeliveryAddress_Country** között.</span><span class="sxs-lookup"><span data-stu-id="7ec19-179">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId to BillingAddress_Country** and for **DeliveryCountryRegionId to DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="7ec19-180">A sablon értéke **ValueMap** az országok számával leképezve.</span><span class="sxs-lookup"><span data-stu-id="7ec19-180">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="7ec19-181">Rendelések a Salesben történő létrehozásához szükség van **Árlistára**.</span><span class="sxs-lookup"><span data-stu-id="7ec19-181">**Price list** is required to create orders in Sales.</span></span> <span data-ttu-id="7ec19-182">Frissítse a **pricelevelid.name [Árlista neve]** elemet illető **ValueMap** értéket a **CDS** > **Célhely** helyen a Salesben pénznemenként használt **Árlistára**.</span><span class="sxs-lookup"><span data-stu-id="7ec19-182">Update the **ValueMap** in **CDS** > **Destination** for **pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="7ec19-183">Használhatja az alapértelmezett **Árlistát** egyetlen pénznemhez, vagy egy **ValueMap** elemet, ha több pénznemben vannak **Árlisták**.</span><span class="sxs-lookup"><span data-stu-id="7ec19-183">You can either used the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>
    
    - <span data-ttu-id="7ec19-184">A sablon alapértelmezett **pricelevelid.name [Árlista neve]** értéke CRM Service USA (minta).</span><span class="sxs-lookup"><span data-stu-id="7ec19-184">Default template value for **pricelevelid.name [Price List Name]** is CRM Service USA (sample).</span></span> 

#### <a name="salesline-task"></a><span data-ttu-id="7ec19-185">SalesLine feladat</span><span class="sxs-lookup"><span data-stu-id="7ec19-185">SalesLine task</span></span>

- <span data-ttu-id="7ec19-186">Frissítse a leképezést a következőre: **CDS-szervezetazonosító forrásban** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="7ec19-186">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 
    
    - <span data-ttu-id="7ec19-187">A sablon alapértelmezett **SalesOrder_Organization_OrganizationId** értéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="7ec19-187">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="7ec19-188">A sablon alapértelmezett **Product_Organization_OrganizationId** értéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="7ec19-188">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="7ec19-189">Ügyeljen, hogy meglegyen a szükséges leképezés a **Forrás** > **CDS** helyen a **DeliveryCountryRegionId** és a **DeliveryAddress_Country** között.</span><span class="sxs-lookup"><span data-stu-id="7ec19-189">Ensure that the needed mapping exists in **Source** > **CDS** for **DeliveryCountryRegionId** to **DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="7ec19-190">A sablon értéke **ValueMap** az országok számával leképezve.</span><span class="sxs-lookup"><span data-stu-id="7ec19-190">Template value is **ValueMap** with a number of countries mapped.</span></span>
    
- <span data-ttu-id="7ec19-191">Győződjön meg arról, hogy a Finance and Operationsben a szükséges **ValueMap** a **SalesUnitSymbol** elemhez létezik a **Forrás** > **CDS-hozzárendelés** helyen.</span><span class="sxs-lookup"><span data-stu-id="7ec19-191">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span>

    - <span data-ttu-id="7ec19-192">A **ValueMap** sablonérték meghatározása a **SalesUnitSymbol to Quantity_UOM** révén történik.</span><span class="sxs-lookup"><span data-stu-id="7ec19-192">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="7ec19-193">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="7ec19-193">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="7ec19-194">A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem találhatók meg a alapértelmezett-leképezései.</span><span class="sxs-lookup"><span data-stu-id="7ec19-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="7ec19-195">Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.</span><span class="sxs-lookup"><span data-stu-id="7ec19-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="7ec19-196">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="7ec19-196">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="orderheader"></a><span data-ttu-id="7ec19-197">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="7ec19-197">OrderHeader</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-order-template-mapping-data-integrator-1.png)

![Sablonleképezés az adatintegrátorban](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a><span data-ttu-id="7ec19-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="7ec19-200">OrderLine</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-order-template-mapping-data-integrator-3.png)

![Sablonleképezés az adatintegrátorban](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="7ec19-203">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="7ec19-203">Related topics</span></span>

[<span data-ttu-id="7ec19-204">A Finance and Operations-termékek szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="7ec19-204">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="7ec19-205">A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="7ec19-205">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="7ec19-206">A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="7ec19-206">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="7ec19-207">Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="7ec19-207">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="7ec19-208">Értékesítésiszámla-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="7ec19-208">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


