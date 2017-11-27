---
title: "Értékesítésirendelés-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, amelyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti közvetlen szinkronizálásra használhatók az értékesítési rendelések fejlécei és sorai esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="5ed62-103">Értékesítésirendelés-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="5ed62-103">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="5ed62-104">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, amelyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti közvetlen szinkronizálásra használhatók az értékesítési rendelések fejlécei és sorai esetében.</span><span class="sxs-lookup"><span data-stu-id="5ed62-104">This topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="5ed62-105">A potenciális ügyfelek készpénzre váltása adatfolyama</span><span class="sxs-lookup"><span data-stu-id="5ed62-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="5ed62-106">A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között.</span><span class="sxs-lookup"><span data-stu-id="5ed62-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="5ed62-107">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="5ed62-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="5ed62-108">A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="5ed62-108">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="5ed62-109">[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="5ed62-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="5ed62-110">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="5ed62-110">Templates and tasks</span></span>

<span data-ttu-id="5ed62-111">A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="5ed62-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="5ed62-112">Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="5ed62-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="5ed62-113">A következő sablon és alapul szolgáló feladatok vannak használatban az értékesítési rendelési fejlécek és sorok szinkronizálásához a Finance and Operations és a Sales között:</span><span class="sxs-lookup"><span data-stu-id="5ed62-113">The following template and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="5ed62-114">**Sablon neve az adatintegrációban:** Értékesítési rendelések (Fin and Ops – Sales) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="5ed62-114">**Name of the template in Data integration:** Sales Orders (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="5ed62-115">**A feladatok nevei az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="5ed62-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="5ed62-116">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="5ed62-116">OrderHeader</span></span>
    - <span data-ttu-id="5ed62-117">OrderLine</span><span class="sxs-lookup"><span data-stu-id="5ed62-117">OrderLine</span></span>

<span data-ttu-id="5ed62-118">A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési számla fejlécének és sorainak szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="5ed62-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="5ed62-119">Termékek (Fin and Ops – Sales) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="5ed62-119">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="5ed62-120">Számlák (Sales a Fin and Opshoz) – Közvetlen (ha van)</span><span class="sxs-lookup"><span data-stu-id="5ed62-120">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="5ed62-121">Kapcsolattartók vevőkkel (Sales a Fin and Opshoz) – közvetlen (ha van)</span><span class="sxs-lookup"><span data-stu-id="5ed62-121">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="5ed62-122">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="5ed62-122">Entity set</span></span>

| <span data-ttu-id="5ed62-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5ed62-123">Finance and Operations</span></span>  | <span data-ttu-id="5ed62-124">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="5ed62-124">Sales</span></span>             |
|-------------------------|-------------------|
| <span data-ttu-id="5ed62-125">CDS értékesítési rendelési fejlécek</span><span class="sxs-lookup"><span data-stu-id="5ed62-125">CDS sales order headers</span></span> | <span data-ttu-id="5ed62-126">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="5ed62-126">SalesOrders</span></span>       |
| <span data-ttu-id="5ed62-127">CDS értékesítési rendelés sorai</span><span class="sxs-lookup"><span data-stu-id="5ed62-127">CDS sales order lines</span></span>   | <span data-ttu-id="5ed62-128">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="5ed62-128">SalesOrderDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="5ed62-129">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="5ed62-129">Entity flow</span></span>

<span data-ttu-id="5ed62-130">Az értékesítési rendelések létrehozása a Finance and Operationsben történik, majd szinkronizálódnak a Sales programban.</span><span class="sxs-lookup"><span data-stu-id="5ed62-130">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="5ed62-131">A sablonban található szűrők segítenek gondoskodni róla, hogy hogy csak a megfelelő értékesítési rendelések szerepeljenek a szinkronizálásban:</span><span class="sxs-lookup"><span data-stu-id="5ed62-131">Filters in the template help guarantee that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="5ed62-132">A Sales szolgáltatásból származó értékesítési ajánlatban szereplő értékesítési és számlázási vevő is szerepelni fog a szinkronizálásban.</span><span class="sxs-lookup"><span data-stu-id="5ed62-132">On the sales order, both the ordering customer and the invoicing customer that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="5ed62-133">A Finance and Operations szolgáltatásban az **OrderingCustomerIsExternallyMaintained** és az **InvoiceCustomerIsExternallyMaintained** mezők az adatentitások szinkronizálásának nyomon követésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="5ed62-133">In Finance and Operations, the **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** fields are used to track the synchronization in the data entities.</span></span>
- <span data-ttu-id="5ed62-134">Az Értékesítési rendelést a Finance and Operations szolgáltatásban jóvá kell hagyni.</span><span class="sxs-lookup"><span data-stu-id="5ed62-134">The sales order in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="5ed62-135">Csak a megerősített értékesítési rendelések vagy magasabb, például **Szállított** vagy **Számlázott** feldolgozási állapotú értékesítési rendelések szinkronizálódnak a Sales szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="5ed62-135">Only confirmed sales orders or sales orders that have a higher processing status, such as **Shipped** or **Invoiced**, are synchronized to Sales.</span></span>
- <span data-ttu-id="5ed62-136">Értékesítési rendelés létrehozása vagy módosítása után a Finance and Operations szolgáltatásban végre kell hajtani az **Eladási összegek számítása** kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="5ed62-136">After a sales order is created or modified, the **Calculate sales totals** batch job in Finance and Operations must be run.</span></span> <span data-ttu-id="5ed62-137">Csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a Sales szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="5ed62-137">Only sales orders where sales totals are calculated will be synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="5ed62-138">A költségekhez kapcsolódó adók az Értékesítési rendelés fejlécében jelenleg nem szerepelnek a Finance and Operations szolgáltatásból a Sales szolgáltatásba történő szinkronizálásban.</span><span class="sxs-lookup"><span data-stu-id="5ed62-138">Currently, tax that is related to charges on the sales order header isn't included in the synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="5ed62-139">A Sales nem támogatja az adózási adatokat a fejléc szintjén.</span><span class="sxs-lookup"><span data-stu-id="5ed62-139">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="5ed62-140">Azonban a sorszintű díjakhoz kapcsolódó adó szerepel a szinkronizálásban.</span><span class="sxs-lookup"><span data-stu-id="5ed62-140">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="5ed62-141">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="5ed62-141">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="5ed62-142">Új mezők kerülnek hozzáadásra a **Rendelés** entitáshoz, és megjelennek a lapon:</span><span class="sxs-lookup"><span data-stu-id="5ed62-142">New fields have been added to the **Order** entity and appear on the page:</span></span>

- <span data-ttu-id="5ed62-143">**Külsőleg karbantartva** – beállítása **Igen**, ha a megrendelés a Finance and Operations szolgáltatásból érkezik.</span><span class="sxs-lookup"><span data-stu-id="5ed62-143">**Is Maintained Externally** – Set this option to **Yes** when the order is coming from Finance and Operations.</span></span>
- <span data-ttu-id="5ed62-144">**Feldolgozás állapota** – a mező a rendelés feldolgozottsági állapotát mutatja a Finance and Operations szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="5ed62-144">**Processing status** – This field shows the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="5ed62-145">A következő értékek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="5ed62-145">The following values are available:</span></span>

    - <span data-ttu-id="5ed62-146">Aktív</span><span class="sxs-lookup"><span data-stu-id="5ed62-146">Active</span></span>
    - <span data-ttu-id="5ed62-147">Visszaigazolva</span><span class="sxs-lookup"><span data-stu-id="5ed62-147">Confirmed</span></span>
    - <span data-ttu-id="5ed62-148">Csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="5ed62-148">Packing Slip</span></span>
    - <span data-ttu-id="5ed62-149">Számlázva</span><span class="sxs-lookup"><span data-stu-id="5ed62-149">Invoiced</span></span>
    - <span data-ttu-id="5ed62-150">Kitárolva</span><span class="sxs-lookup"><span data-stu-id="5ed62-150">Picked</span></span>
    - <span data-ttu-id="5ed62-151">Részben kitárolva</span><span class="sxs-lookup"><span data-stu-id="5ed62-151">Partially Picked</span></span>
    - <span data-ttu-id="5ed62-152">Részben csomagolva</span><span class="sxs-lookup"><span data-stu-id="5ed62-152">Partially Packed</span></span>
    - <span data-ttu-id="5ed62-153">Szállítva</span><span class="sxs-lookup"><span data-stu-id="5ed62-153">Shipped</span></span>
    - <span data-ttu-id="5ed62-154">Részben szállítva</span><span class="sxs-lookup"><span data-stu-id="5ed62-154">Partially Shipped</span></span>
    - <span data-ttu-id="5ed62-155">Részben számlázva</span><span class="sxs-lookup"><span data-stu-id="5ed62-155">Partially Invoiced</span></span>
    - <span data-ttu-id="5ed62-156">Visszavonva</span><span class="sxs-lookup"><span data-stu-id="5ed62-156">Cancelled</span></span>

<span data-ttu-id="5ed62-157">Az **Ajánlat csak külsőleg fenntartott termékekre vonatkozik** beállítást más értékesítési forgatókönyvekben használják (például a Sales és a Finance and Operation között történő szinkronizálás), hogy következetesen nyomon kövessék, hogy egy értékesítési megbízás teljes egészében külsőleg karbantartott termékekből áll-e.</span><span class="sxs-lookup"><span data-stu-id="5ed62-157">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (for example, synchronization from Sales to Finance and Operation) to consistently track whether a sales order consists entirely of externally maintained products.</span></span> <span data-ttu-id="5ed62-158">Ha az értékesítési rendelés csak külsőleg fenntartott termékeket tartalmaz, a termékeket a Finance and Operations kezeli.</span><span class="sxs-lookup"><span data-stu-id="5ed62-158">If a sales order consists entirely of externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="5ed62-159">Ez a beállítás garantálja, hogy nem próbálja szinkronizálni az értékesítési rendelési sorokat olyan termékekkel, amelyek ismeretlenek a Finance and Operations számára.</span><span class="sxs-lookup"><span data-stu-id="5ed62-159">This setting helps guarantee that you don't try to synchronize sales order lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="5ed62-160">A **Számla létrehozása**, **Rendelés érvénytelenítése**, **Újraszámítás**, **Termékek beszerzése** és **Keresési cím** gombok az **Értékesítési rendelés** oldalon rejtve vannak külsőleg karbantartott rendeléseknél, mivel a számlák a Finance and Operations szolgáltatásban jönnek létre, majd szinkronizálódnak a Sales szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="5ed62-160">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products**, and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders, because invoices will be created in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="5ed62-161">Ezeket a megrendeléseket nem lehet szerkeszteni, mert az értékesítési rendelési adatok szinkronizálódnak a Finance and Operations szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="5ed62-161">The order page can't be edited, because sales order information will be synchronized from Finance and Operations.</span></span>

<span data-ttu-id="5ed62-162">Az értékesítési rendelés állapota **Aktív** marad annak biztosítására, hogy a Finance and Operations módosításai átkerülhessenek az értékesítési rendelésbe a Sales szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="5ed62-162">The status of a sales order will remain **Active** to help guarantee that changes from Finance and Operations can flow to the sales order in Sales.</span></span> <span data-ttu-id="5ed62-163">Ennek vezérléséhez az alapértelmezett **Statecode \[állapot\]** értékét **Aktívra** kell állítani az adatintegrációs projektben.</span><span class="sxs-lookup"><span data-stu-id="5ed62-163">To control this behavior, set the default **Statecode \[Status\]** value to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="5ed62-164">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="5ed62-164">Preconditions and mapping setup</span></span>

<span data-ttu-id="5ed62-165">Értékesítési rendelések szinkronizálása előtt fontos frissíteni a rendszert a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="5ed62-165">Before you synchronize sales orders, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="5ed62-166">Beállítás a Salesben</span><span class="sxs-lookup"><span data-stu-id="5ed62-166">Setup in Sales</span></span>

- <span data-ttu-id="5ed62-167">Győződjön meg róla, hogy beállították az engedélyeket ahhoz a csapathoz, amelytől a Sales kapcsolatkészletének felhasználója hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="5ed62-167">Make sure that permissions are set up for the team that the user from your Sales connection set is assigned to.</span></span> <span data-ttu-id="5ed62-168">Bemutatóadatok használatakor rendszerint a felhasználó rendelkezik rendszergazdai hozzáféréssel, de nem a csoport.</span><span class="sxs-lookup"><span data-stu-id="5ed62-168">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="5ed62-169">Ha a csapatnak nincs adminisztrátori hozzáférése is, akkor ha a projektet az adatintegrálásból futtatja, hibaüzenet jelenik meg, amely azt jelzi, hogy a fő csapat hiányzik.</span><span class="sxs-lookup"><span data-stu-id="5ed62-169">If the team doesn't also have admin access, when you run the project from Data integration, you will receive an error message that states that Principal team is missing.</span></span>

    <span data-ttu-id="5ed62-170">A **Beállítások** > **Biztonság** > **Csapatok** pontnál válassza ki a megfelelő csapatot, majd a **Szerepkörök kezelése** lehetőséget, és válasszon ki egy olyan szerepkört, amely a megfelelő engedélyekkel rendelkezik, pl. **Rendszergazda**.</span><span class="sxs-lookup"><span data-stu-id="5ed62-170">Go to **Settings** > **Security** > **Teams**, select the relevant team, select **Manage Roles**, and select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="5ed62-171">Lépjen a **Beállítások** > **Adminisztráció** > **Rendszerbeállítások** > **Értékesítés** pontra, és győződjön meg róla, hogy a következő beállításokat használja:</span><span class="sxs-lookup"><span data-stu-id="5ed62-171">Go to **Settings** > **Administration** > **System settings** > **Sales**, and makes sure that the following settings are used:</span></span>

    - <span data-ttu-id="5ed62-172">A **Rendszer díjazási számítási rendszerének használata** beállítás értéke **Igen**.</span><span class="sxs-lookup"><span data-stu-id="5ed62-172">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="5ed62-173">Az **Engedményszámítási módszer** mező értéke a **Sortétel**.</span><span class="sxs-lookup"><span data-stu-id="5ed62-173">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="5ed62-174">Beállítás a Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="5ed62-174">Setup in Finance and Operations</span></span>

<span data-ttu-id="5ed62-175">Lépjen az **Értékesítés és marketing** > **Időszakos feladatok** > **Eladási összegek számítása** ponthoz, állítsa be a feladatot kötegelt futásra.</span><span class="sxs-lookup"><span data-stu-id="5ed62-175">Go to **Sales and marketing** > **Periodic tasks** > **Calculate sales totals**, and set the job to run as a batch job.</span></span> <span data-ttu-id="5ed62-176">Állítsa az **Értékesítési rendelések teljes összegének kiszámítása** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="5ed62-176">Set the **Calculate totals for sales orders** option to **Yes**.</span></span> <span data-ttu-id="5ed62-177">Ez a lépés azért fontos, mert csak a kiszámított eladási összeggel rendelkező értékesítési rendelések szinkronizálása történik meg a Sales szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="5ed62-177">This step is important, because only sales orders where sales totals are calculated will be synchronized to Sales.</span></span> <span data-ttu-id="5ed62-178">A kötegelt feladat gyakoriságát az értékesítési rendelés szinkronizálásának gyakoriságához kell igazítani.</span><span class="sxs-lookup"><span data-stu-id="5ed62-178">The frequency of the batch job should be aligned with the frequency of sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="5ed62-179">Beállítás az adatintegrációs projektben</span><span class="sxs-lookup"><span data-stu-id="5ed62-179">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="5ed62-180">SalesHeader feladat</span><span class="sxs-lookup"><span data-stu-id="5ed62-180">SalesHeader task</span></span>

- <span data-ttu-id="5ed62-181">Győződjön meg róla, hogy a szükséges leképezés létezik: **InvoiceCountryRegionId** – **BillingAddress\_Country**, továbbá **DeliveryCountryRegionId** – **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="5ed62-181">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country** and for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="5ed62-182">A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve.</span><span class="sxs-lookup"><span data-stu-id="5ed62-182">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="5ed62-183">Rendeléseknek a Sales szolgáltatásban történő létrehozásához szükség van árlistára.</span><span class="sxs-lookup"><span data-stu-id="5ed62-183">A price list is required in order to create orders in Sales.</span></span> <span data-ttu-id="5ed62-184">Frissítse a **pricelevelid.name \[Price list name\]** leképezését olyan árlistára, amelyet a Sales is használja valutánként.</span><span class="sxs-lookup"><span data-stu-id="5ed62-184">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="5ed62-185">Az alapértelmezett árlistát használhatja egy pénznemnél.</span><span class="sxs-lookup"><span data-stu-id="5ed62-185">You can use the default price list for a single currency.</span></span> <span data-ttu-id="5ed62-186">Alternatív megoldásként, ha több pénznemben van árlistája, használhat értékképpontot.</span><span class="sxs-lookup"><span data-stu-id="5ed62-186">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="5ed62-187">A sablon alapértelmezett neve **pricelevelid.name \[Árlista neve\]** – **CRM Service USA (minta)**.</span><span class="sxs-lookup"><span data-stu-id="5ed62-187">The default template value for **pricelevelid.name \[Price list name\]** is **CRM Service USA (sample)**.</span></span>

#### <a name="salesline-task"></a><span data-ttu-id="5ed62-188">SalesLine feladat</span><span class="sxs-lookup"><span data-stu-id="5ed62-188">SalesLine task</span></span>

- <span data-ttu-id="5ed62-189">Győződjön meg róla, hogy a szükséges leképezés létezik: **DeliveryCountryRegionId** – **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="5ed62-189">Make sure that the required mapping exists for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="5ed62-190">A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve.</span><span class="sxs-lookup"><span data-stu-id="5ed62-190">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="5ed62-191">Győződjön meg arról, hogy a **SalesUnitSymbol** szükséges értékmegfeleltetése meg van adva a Finance and Operations szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="5ed62-191">Make sure that the required value map for **SalesUnitSymbol** in Finance and Operations exists.</span></span>

    <span data-ttu-id="5ed62-192">Olyan sablonérték, amely rendelkezik értékmegfeleltetéssel a **SalesUnitSymbol** esetében az **Quantity\_UOM** értékkel.</span><span class="sxs-lookup"><span data-stu-id="5ed62-192">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="5ed62-193">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="5ed62-193">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="5ed62-194">A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem szerepelnek a alapértelmezett-leképezései.</span><span class="sxs-lookup"><span data-stu-id="5ed62-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="5ed62-195">Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.</span><span class="sxs-lookup"><span data-stu-id="5ed62-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="5ed62-196">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="5ed62-196">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="5ed62-197">A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Finance and Operations irányban.</span><span class="sxs-lookup"><span data-stu-id="5ed62-197">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="orderheader"></a><span data-ttu-id="5ed62-198">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="5ed62-198">OrderHeader</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a><span data-ttu-id="5ed62-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="5ed62-200">OrderLine</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="5ed62-202">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="5ed62-202">Related topics</span></span>

[<span data-ttu-id="5ed62-203">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="5ed62-203">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="5ed62-204">A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="5ed62-204">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="5ed62-205">A Finance and Operations-termékek közvetlen szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="5ed62-205">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="5ed62-206">A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="5ed62-206">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="5ed62-207">Értékesítésiszámla-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="5ed62-207">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




