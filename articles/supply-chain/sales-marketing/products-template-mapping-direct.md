---
title: "A termékek szinkronizálása Sales-termékekre közvetlenül a Finance and Operations szolgáltatásból"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Sales közötti termékszinkronizálásra használhatók."
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 84366a26f69a651146648d4a9bdb139fc6d2cffe
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="eff47-103">A Finance and Operations-termékek közvetlen szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="eff47-103">Synchronize products directly from Finance and Operations to products in Sales</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="eff47-104">A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie: [Dynamics 365 integráció](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="eff47-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="eff47-105">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Sales közötti közvetlen termékszinkronizálásra használhatók.</span><span class="sxs-lookup"><span data-stu-id="eff47-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Microsoft Dynamics 365 for Finance and Operations, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="eff47-106">A potenciális ügyfelek készpénzre váltása adatfolyama</span><span class="sxs-lookup"><span data-stu-id="eff47-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="eff47-107">A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között.</span><span class="sxs-lookup"><span data-stu-id="eff47-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="eff47-108">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="eff47-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="eff47-109">A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="eff47-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="eff47-110">[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="eff47-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="eff47-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="eff47-111">Templates and tasks</span></span>

<span data-ttu-id="eff47-112">A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="eff47-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="eff47-113">Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="eff47-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="eff47-114">A következő sablonokat és alapul szolgáló feladatokat használják a termékek szinkronizálásához a Finance and Operations és a Sales között:</span><span class="sxs-lookup"><span data-stu-id="eff47-114">The following template and underlying tasks are used to synchronize products from Finance and Operations to Sales.</span></span>

- <span data-ttu-id="eff47-115">**Sablon neve az adatintegrációban:** Termékek (Fin and Ops – Sales) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="eff47-115">**Name of the template in Data integration:** Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="eff47-116">**A feladat neve az adatintegrációs projektben:** Termékek</span><span class="sxs-lookup"><span data-stu-id="eff47-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="eff47-117">Szinkronizálási feladat nem szükséges a fiókszinkronizálás előtt.</span><span class="sxs-lookup"><span data-stu-id="eff47-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="eff47-118">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="eff47-118">Entity set</span></span>

| <span data-ttu-id="eff47-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="eff47-119">Finance and Operations</span></span>     | <span data-ttu-id="eff47-120">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="eff47-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="eff47-121">Értékesíthető kiadott termékek</span><span class="sxs-lookup"><span data-stu-id="eff47-121">Sellable released products</span></span> | <span data-ttu-id="eff47-122">Termékek</span><span class="sxs-lookup"><span data-stu-id="eff47-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="eff47-123">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="eff47-123">Entity flow</span></span>

<span data-ttu-id="eff47-124">A termékek kezelése a Finance and Operationsben történik, majd szinkronizálás történik a Sales programmal.</span><span class="sxs-lookup"><span data-stu-id="eff47-124">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="eff47-125">A Finance and Operations **Értékesíthető kiadott termékek** adatentitása csak *értékesíthető* termékeket exportál.</span><span class="sxs-lookup"><span data-stu-id="eff47-125">The **Sellable released products** data entity in Finance and Operations exports only products that are *sellable*.</span></span> <span data-ttu-id="eff47-126">Az értékesíthető termékek olyan termékek, amelyek rendelkeznek az általuk megkövetelt információkkal annak érdekében, hogy azokat értékesítési rendelésekben használják.</span><span class="sxs-lookup"><span data-stu-id="eff47-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="eff47-127">Ugyanazok a szabályok vonatkoznak, ha egy termék ellenőrizve van az **Érvényesítés** funkcióval a **Kiadott termék** oldalon.</span><span class="sxs-lookup"><span data-stu-id="eff47-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="eff47-128">A termékszám kulcsként használható.</span><span class="sxs-lookup"><span data-stu-id="eff47-128">The product number is used as a key.</span></span> <span data-ttu-id="eff47-129">Ezért ha a termékváltozatok szinkronizálásra kerülnek a Sales-szel, minden termékváltozat egyedi termékazonosítóval rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="eff47-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="eff47-130">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="eff47-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="eff47-131">A Sales szolgáltatásba az új **Külsőleg karbantartott** mező került a termékekhez, amely azt jelzi, hogy a terméket külsőleg tartják karban.</span><span class="sxs-lookup"><span data-stu-id="eff47-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="eff47-132">Az érték alapértelmezésben **Igen** a Sales-be való importálás során.</span><span class="sxs-lookup"><span data-stu-id="eff47-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="eff47-133">A következő értékek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="eff47-133">The following values are available:</span></span>

- <span data-ttu-id="eff47-134">**Igen** – A termék a Finance and Operations szolgáltatásból származik, és nem lesz szerkeszthető a Sales szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="eff47-134">**Yes** – The product originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="eff47-135">**Nem** – A terméket közvetlenül a Sales szolgáltatásban adták meg.</span><span class="sxs-lookup"><span data-stu-id="eff47-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="eff47-136">**(Üres)** – A termék már létezett a Sales szolgáltatásban a Potenciális ügyfelek készpénzre váltása engedélyezése előtt.</span><span class="sxs-lookup"><span data-stu-id="eff47-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="eff47-137">A **Külsőleg karbantartott** mező segít annak garantálásában, hogy csak azok az árajánlatok és értékesítési megbízások, amelyek külsőleg karbantartott termékeket tartalmaznak, szinkronizálnak a Finance and Operations szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="eff47-137">The **Is Externally Maintained** field helps guarantee that only quotations and sales orders that have externally maintained products will be synchronized to Finance and Operations.</span></span>

<span data-ttu-id="eff47-138">Külsőleg karbantartása termékek a program automatikusan hozzáadja az első érvényes árlista, ugyanabban a pénznemben.</span><span class="sxs-lookup"><span data-stu-id="eff47-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="eff47-139">Az árlisták betűrendben, név szerint vannak rendezve.</span><span class="sxs-lookup"><span data-stu-id="eff47-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="eff47-140">A Finance and Operations termékeladási ára egyben az árlistán szereplő ár.</span><span class="sxs-lookup"><span data-stu-id="eff47-140">The product sales price from Finance and Operations is used as the price on the price list.</span></span> <span data-ttu-id="eff47-141">Ezért győződjön meg arról, hogy tartozik árlista minden egyes Sales termékeladási pénznemhez a Finance and Operations szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="eff47-141">Therefore, there must be a price list in Sales for every product sales currency in Finance and Operations.</span></span> <span data-ttu-id="eff47-142">A felszabadított, eladható termékek pénznemét a jogi személy számviteli pénznemére kell beállítani, ahonnan a terméket exportálják.</span><span class="sxs-lookup"><span data-stu-id="eff47-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> <span data-ttu-id="eff47-143">A termékszinkronizálás nem fog sikerülni, hacsak nem létezik olyan árlista, amelynek megfelelő pénzneme van.</span><span class="sxs-lookup"><span data-stu-id="eff47-143">Product synchronization won't succeed unless there is a price list that has a matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="eff47-144">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="eff47-144">Preconditions and mapping setup</span></span>

- <span data-ttu-id="eff47-145">Mielőtt először futtatná a szinkronizálást, töltse ki az Egyedi terméktáblázatot a Finance and Operations meglévő termékeihez.</span><span class="sxs-lookup"><span data-stu-id="eff47-145">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Finance and Operations.</span></span> <span data-ttu-id="eff47-146">A feladat befejezéséig nem lesznek szinkronizálva a meglévő termékek.</span><span class="sxs-lookup"><span data-stu-id="eff47-146">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="eff47-147">A Finance and Operations esetén akkor a keresés kereséséhez **feltöltése egyedi termék tábla**.</span><span class="sxs-lookup"><span data-stu-id="eff47-147">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="eff47-148">Válassza az **Egyedi termék tábla feltöltése** lehetőséget a feladat futtatásához.</span><span class="sxs-lookup"><span data-stu-id="eff47-148">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="eff47-149">Ez a feladat csak egyszer futtatható.</span><span class="sxs-lookup"><span data-stu-id="eff47-149">This job must be run only one time.</span></span>

- <span data-ttu-id="eff47-150">Győződjön meg róla, hogy megvan a szükséges értékhozzárendelés az értékesítési mértékegységre vonatkozóan a Finance and Operations és a Sales között a **SalesUnitSymbol** **DefaultUnit (Name)** leképezésénél.</span><span class="sxs-lookup"><span data-stu-id="eff47-150">Make sure that the required value map for the selling unit of measure (UOM) between Finance and Operations and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="eff47-151">Frissítse az **Egységcsoport** (**defaultuomscheduleid.name**) értékleképezését, hogy megegyezzen az **Egységcsoportok** értékével a Sales-ben.</span><span class="sxs-lookup"><span data-stu-id="eff47-151">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="eff47-152">A sablon alapértéke az **Alapértelmezett egység**.</span><span class="sxs-lookup"><span data-stu-id="eff47-152">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="eff47-153">Győződjön meg arról, hogy az összes termék értékesítési mértékegysége a Finance and Operations szolgáltatásból létezik a Sales szolgáltatásban is.</span><span class="sxs-lookup"><span data-stu-id="eff47-153">Make sure that the selling UOMs for all products from Finance and Operations exist in Sales.</span></span>
- <span data-ttu-id="eff47-154">Győződjön meg arról, hogy árlisták a Finance and Operations minden termékeladási pénzneméhez léteznek a Sales szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="eff47-154">Make sure that price lists exist in Sales for every product sales currency in Finance and Operations.</span></span>
- <span data-ttu-id="eff47-155">Amikor létrejönnek a termékek a Sales szolgáltatásban, akkor állapotuk **Sablon** vagy **Aktív** lehet.</span><span class="sxs-lookup"><span data-stu-id="eff47-155">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="eff47-156">A viselkedés ellenőrzése a **Beállítások** > **Felügyelet** > **Tendszerbeállítások** > **Értékesítés** pontban történik a Sales szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="eff47-156">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="eff47-157">A létrehozásukkor **Vázlat** állapotú termékeket aktiválni kell, mielőtt azok hozzáadhatók lennének az árajánlatokhoz vagy az értékesítési rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="eff47-157">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="eff47-158">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="eff47-158">Template mapping in Data integration</span></span>

<span data-ttu-id="eff47-159">Az alábbi ábrán sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="eff47-159">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="eff47-160">A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Finance and Operations irányban.</span><span class="sxs-lookup"><span data-stu-id="eff47-160">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Sablonleképezés az adatintegrátorban](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="eff47-162">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="eff47-162">Related topics</span></span>

[<span data-ttu-id="eff47-163">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="eff47-163">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="eff47-164">A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="eff47-164">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="eff47-165">A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="eff47-165">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="eff47-166">Értékesítésirendelés-fejlécek és -sorok szinkronizálása közvetlenül a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="eff47-166">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="eff47-167">Értékesítésiszámla-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="eff47-167">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




